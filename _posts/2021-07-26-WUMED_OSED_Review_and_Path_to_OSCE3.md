---
title: "WUMED/OSED Review and Obtaining OSCE3"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - exploit development
  - certifications
  - offsec
  - osed
  - windbg
  - ida pro
  - reverse engineering
  - rop chains
  - SEH overflows
  - stack overflows
  - dep bypass
  - aslr bypass
  - egghunters
  - shellcoding
  - assembly
---

![image](https://github.com/x0rb3l/robelcampbell/blob/master/assets/images/osed_passing_email.png?raw=true)

In my last two posts, I discussed my experience with AWAE/OSWE and ETBD/OSEP and how they are two of the trinity in obtaining the coveted *OSCE<sup>3</sup>* certification. This post is aimed at discussing my experience with the third and final course: *Windows User Mode Exploit Development* (WUMED) and *Offensive Security Exploit Developer* (OSED) exam. I will also briefly discuss the motivation behind obtaining all three certs within a six-month period.

WUMED focuses on identifying vulnerabilites through reverse engineering Windows applications that run in user mode. It takes it a step beyond regular stack based overflows and teaches you how to bypass common mitigations such as ASLR and DEP. It also teaches you how to create your own custom 32-bit shellcode.

You can find out more in the course [syllabus](https://www.offensive-security.com/documentation/EXP301-syllabus.pdf). 

### Prep
I have mentioned before in the last two posts that Offensive Security has adjusted their training so all you need to be successful is in the course material. This also applies to WUMED.

I came into the course already very familiar with debuggers, reverse engineering and exploit development, however, I don't typically work with Windows for my full-time job so there was definitely plenty to learn.

I tried to refresh some of my legacy CTP/OSCE skills in my home lab by replicating  some of the exploits for the applications used in the WUMED course syllabus. I didn't spend too much time doing this but I did play a little bit with the stack overflow vulnerability found in the Sync Breeze module.

The only other prep I can think of is getting comforable Windbg as this is used throughout the course and is expected of you to use in the exam. There is a whole chapter dedicated to it and I created a little cheat sheet for reference when I couldn't remember specific syntax for a command. Here is a link to the cheat sheet : [Windbg Cheat Sheet](https://github.com/x0rb3l/osed_windbg_cheat_sheet/blob/44582051e58e46445dc75de378ad41a67a0631f8/windbg_cheat_sheet.md)

### The Course
The course materials come with a 600+ page pdf and videos for each module. I thought the training was once again top notch. Offsec doesn't just teach you what you need to know to pass the exam, they go in depth about different topics such as creating custom shellcode, process structures and their purpose, the *Structure Exception Handling* process, etc... 

As always they provide you with plenty of extra mile exercises that test your understanding of the module you just completed. I suggest doing as many extra miles as possible in this course because it helps work out a lot of the little nuances you come across in exploit development, such as stack alignment and read/write protections. There are also several challenge exercises that I would suggest completing if possible. I was only able to complete 2 out of the 3 challenges which, in my experience, was enough since I did most of the extra mile exercises. Your mileage may vary.

I have seen in the official Offsec discord many people complaining about the lack of 64-bit exploitation and how this course doesn't really prepare you for AWE/OSEE even though it is stated as such on the Offsec website. In my opinion, the argument makes some sense in that Offsec could make multiple exploit development courses and go into topics like 64-bit exploitation and exploiting the heap which would in fact prepare you better for AWE/OSEE, however, I think there is a fair amount of preparatory resources available to folks online that want to take on the AWE course and OSEE exam. I am of the opinion that you really learn something when you are forced to do your own research. The website simply states that WUMED "...serves to build a solid foundation for students wanting too pursue AWE." which I interpret as the bare minimum before starting AWE.

### The Exam
...is hard. But not so much if you follow my guidance above.

You are given a set of assignments to accomplish, each with specific criteria. Failure to complete each task within an assignment will result in zero points for that assignment. You only need 2 out of 3 assignments to pass.

Don't make the mistake I made of skipping parts of the course material. I decided to jump over different parts of the course thinking that A.) it either wasn't on the exam or B.) that I already knew enough about it. It ended up costing me precious time in the exam and I ended having to "learn on the job". Its no fun being blindsided with a task and having to go study it while the clock is ticking.

Despite dealing with this and my washing machine's hose popping off while running which leaked water all in the room upstairs, I managed to get 2 out of the 3 assignments complete with 10 hours to spare.

I found out that I work really well under pressure. Must be all that wrestling I did growing up.

### Tips
- Go through ALL the course material thoroughly
- Do as many extra miles as possible (there is one really hard one that might not be doable with limited lab time. I suggest trying that only if you have completed everything else)
- Try and complete challenge 1 and 2
- Take really good notes!

There is no secret sauce to passing the exam. You just have to buckle down, study and take really good notes.

### OSCE<sup>3</sup> Certified!

![image](https://github.com/x0rb3l/robelcampbell/blob/master/assets/images/osce3_email.png?raw=true)

After submitting my OSED report on a Wednesday, I received the passing email as well as the OSCE<sup>3</sup> email on Sunday. I had successfully completed OSWE, OSEP, and OSED all within six months, which wasn't something I had planned to do. 

Originally I wasn't interested in doing more Offsec certifications, however, once I found out I could purchase the bundle through work, I had to complete them. I was also on a time crunch since I was to deploy very soon.

Of course, none of this would have been possible without my amazing wife. Despite cutting into our already short time together, she was very supportive all the way. She has been there since I began in cyber security and knows the time it takes to complete these certifications. Thanks babe, I love you!

### Conclusion
This whole experience was really tough but highly rewarding and I thank God for graciously providing me with the ability to accomplish it.

What's next? I will definitely be taking a long break from any type of certification as I ramp up for this deployment. Lately I have been trying to decide what I really want to specialize in and I think I am leaning towards IoT and embedded security. I just purchased the book [Practical IoT Hacking](https://nostarch.com/practical-iot-hacking) and so far its pretty awesome. I have already done a little bit hardware hacking and firmware reverse engineering and hopefully I can do more security research blog post in the near future.

God bless
