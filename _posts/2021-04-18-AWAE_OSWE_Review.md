---
title: "AWAE/OSWE Review"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - exploit development
  - web application
  - certifications
  - offsec
  - oswe
---
![image](https://github.com/x0rb3l/robelcampbell/blob/master/assets/images/oswe_passing_email.png?raw=true)

After a bit of a hiatus from studying for certifications, I became interested in the new certification [bundle](https://www.offensive-security.com/courses-and-certifications/bundles/) by Offensive Security. The new OSCE3 is obtained by passing OSWE, OSEP, and OSED. I am already an OSCE but it's outdated now and I felt the need to get the new one since I like to stay relevant and I'm up for the challenge.

![image](https://raw.githubusercontent.com/x0rb3l/robelcampbell/master/assets/images/offsec_bundle.png)

Fortunately, my employer paid for the bundle and I decided to start with AWAE (Advanced Web Attacks and Exploitation) which comes with an exam voucher for the OSWE (Offensive Security Web Expert). 

At this time in my career I had a pretty solid foundation in web application hacking through bug bounties, however, I felt that I needed a more in-depth understanding and I wanted more experience in white box testing i.e source code review. AWAE takes the white box approach to hacking a web application and takes it from authentication bypass to remote code execution.

### Prep
Before starting the course, I used [Z-r0crypt's](https://z-r0crypt.github.io/blog/2020/01/22/oswe/awae-preparation/) blog which has a solid listing of resources to go over before and after the course.

### The Course
I felt the course was well put together. It provided clear and concise instructions and explanations on the approach to white box testing. I have read other reviews that expressed a desire for more instruction on how to find vulnerabilities rather than just exploiting them but I felt the way the course approached each case study was sufficient enough in developing my own methods. 

There is no need for me to dive into what the course teaches as anyone can tell by reading the [syllabus](https://www.offensive-security.com/documentation/awae-syllabus.pdf).

In all, it took me about 3 weeks to get through the material with a full-time job, wife, 22-month-year-old and having another baby in the middle of it. This was just my experience and I am by no means claiming this can be achieved by anyone.

### The Exam
My original plan for the exam was to casually take it to get a feel for it and not worry about failing. Since having a new baby, I knew it would be darn near impossible to take a 48-hour exam, however, my wife's mother stayed with us for a week and I was able to "get away" for a couple days (I promise I am a good father). Moving on...

I was presented with a couple of target web applications and specific instructions on how to obtain the full amount of points for each. The first target wasn't too bad but still took me about 12 hours to finish. (*NOTE: Make sure you are taking all your notes as you go*) The second target was a bit of a different story and took me much longer to find the initial vulnerability. Eventually, I wrapped up all the points with at least 12 hours to spare. It was around 2:00 A.M. when I finished gathering all my screenshots and refining my notes. I wrote the report the next day. In all it was about 40 pages.

### Tips
- [Stacktrac3's](https://stacktrac3.co/oswe-review-awae-course/) blog has some good nuggets for what to look for and how to go about doing it. You should think about what it is you are trying to accomplish and focus on the code that handles that functionality.

- You do not have to venture out much for techniques, as everything you need to pass the exam is in the course material. Just make sure you know one scripting language well and its web request library. This leads me to my next point...

- Make sure you take really good notes during the course and document/backup all of your proof-of-concept code. I used One Note for my note taking but recently started using [Obsidian](https://obsidian.md/) (using it for ETBD/OSEP right now) and I like it a lot better. I ran a script from my Windows host machine through WSL that copied all work files from my Kali instance, zipped it up and saved it on my One Drive using scp. This is just in case your Kali vm crashes and you lose all your work. Below is the script I made:

```bash

```

### Conclusion
I know some reviews go into much more detail but I really just wanted to share a few tips and resources I used for this exam. I hope this was informative and helped someone with their studies.

If anyone needs more info, advice, or mentoring, please don't hesitate to connect with me on LinkedIn and/or email me.

God bless
