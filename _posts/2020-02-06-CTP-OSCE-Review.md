---
title: "CTP/OSCE Review"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - exploit development
  - certifications
  - offsec
  - osce
---
![image](https://user-images.githubusercontent.com/29740744/114961611-24a33e00-9e37-11eb-9f76-a076b1e8cdf0.png)

Let me start by thanking my wife for putting up with my obsession with all these cyber shenanigans. She has been with me since before I was working my first IT job and she has been a huge motivator (along with our son) to keep pushing my limits.

I will not start this off with a review of the course work, there's plenty of articles that do that already. Rather I will provide a list of blog posts that were extremely helpful to me while studying:

[Jhalon OSCE Review](https://jhalon.github.io/OSCE-Review/) (The resources at the bottom of this blog were the best for practicing. Make sure you do it ALL, several times....until you are a Jedi Knight.)

[From LFI to RCE via PHP Sessions](https://www.rcesecurity.com/2017/08/from-lfi-to-rce-via-php-sessions/)

[Taking Back Netcat](https://www.linkedin.com/redir/general-malware-page?url=https%3A%2F%2Fdl%2epacketstormsecurity%2enet%2Fpapers%2Fvirus%2FTaking_Back_Netcat%2epdf)

[H0mbre Blog](https://h0mbre.github.io/page4/) (Specifically the Vulnserver LTER exploit but this blog has several good writeups for Vulnserver and a couple of Exploit-DB proofs-of-concept.)

If you have taken the OSCP, then you know that in typical Offsec fashion the course materials are not enough to pass the exam. It is only a foundation for further study. Do not just follow a blog post step by step but understand every step as much as possible. I did all the Vulnserver exploits and the different variations until I was popping calc.exe in my sleep. When something didn't work, I made sure I knew why. When something did work, I made sure I knew why. Become very comfortable with each concept...there is no way around it.

#### The Exam
I came down with a cold and sore throat the day before but that didn't phase me much. The exam took me longer than I had expected. The first day I acquired 60 points in about 12 hours by knocking out the 2 heavy point tasks. I was pretty tired so I put off the rest until the next day. The next task took me a while but I finally got it later in the day. By then I didn't feel up to doing the last task and I needed to get all my documentation in order before the exam time ended. I collected all my screenshots, took a break and wrote the report that same night since the next day was a workday. My report ended being around 36 pages. I zipped it up and shot it off for review. I got confirmation that they received it several hours later. Four days later, I got the email that I had passed, which was a bit nerve-racking but worth it.

#### My Opinion
Here are just a few points I will make about the course and exam from my perspective.

- The material is dated, yes, but it is a foundation and gateway drug to learning exploitation. The reason why Offensive Security exams are so good is that it forces you to push yourself and conduct your own research which opens the door to more modern approaches. Unlike a SANS course, you won't have all the answers given to you to brain dump later on. You must have a thorough understanding.
- I mentioned it before but I will say it again. You must practice over and over and over again until its muscle memory. Do not think you can just jump into the exam after replicating a few practice exploits.
- They give you everything needed to complete the tasks. I had a list of tools prepared to upload onto the debugger machine but it turns out it was a bit overkill. I did, however, use Immunity Debugger and a little mona instead of Olly, but that is just my personal preference.
- Document and take screenshots as you go! This just makes life so much easier. You don't want the exam time to end and you forgot key screenshots, which leads to the next point...
- READ THE CONDITIONS CAREFULLY!! There are specific instructions that you must follow in order to get the full amount of points. If you leave something out, it could cost you the exam.

It was a great experience, but this is only the beginning and I aim to continue learning more about advanced exploitation techniques. I would love to one day sit for the OSEE course and exam, which is the highest level certification Offsec offers.

I know this was a short post and not very detailed so feel free to reach out for more questions and I will answer them as best I can. Thank you for reading.
