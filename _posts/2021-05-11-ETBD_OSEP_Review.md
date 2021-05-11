---
title: "ETBD/OSEP Review"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - exploit development
  - Active Directory
  - certifications
  - offsec
  - osep
  - antivirus
  - bypasses
---

![image](https://github.com/x0rb3l/robelcampbell/blob/master/assets/images/osep_passing_email.png?raw=true)

Shortly after passing OSWE, I began the course work for *Evasion Techniques and Breaching Defenses* which is another one of Offsec's *OSCE<sup>3</sup>* certifications. In my [last post](https://x0rb3l.github.io/robelcampbell/blog/AWAE_OSWE_Review/) I briefly explained the 300 level course bundle and how obtaining all three of these certifications will grant you the title *OSCE<sup>3</sup>*.

ETBD focuses on breaching a corporate network perimeter, bypassing various antivirus solutions, abusing Windows Active Directory, owning the domain and more. You can find out more in the course [syllabus](https://www.offensive-security.com/documentation/PEN300-Syllabus.pdf). 

### Prep
There wasn't a lot of prep-work for this one. I did use a few articles to gain a better understanding of what to expect with the course materials and exam. Here are a few:

- [pen_300_osep_prep](https://github.com/deletehead/pen_300_osep_prep)
- [offensive-security-experienced-penetration-tester-osep-review-and-exam](https://spaceraccoon.dev/offensive-security-experienced-penetration-tester-osep-review-and-exam)
- [getting-the-osep-certification-evasion-techniques-and-breaching-defenses-pen-300-course-review](https://casvancooten.com/posts/2021/03/getting-the-osep-certification-evasion-techniques-and-breaching-defenses-pen-300-course-review/)

I also used another resource which was probably my number one go-to blog when I needed some quick references (thank you [@CasvCooten](https://casvancooten.com/about/)):

- [windows-active-directory-exploitation-cheat-sheet-and-command-reference](https://casvancooten.com/posts/2020/11/windows-active-directory-exploitation-cheat-sheet-and-command-reference/)

### The Course
The course materials are almost twice as long as AWAE, with some 700+ pages and includes a separate lab instance for each module you work through to help you practice what you just learned. 

I found the quality of the course material and videos to be top notch and I really appreciated all the extra questions and extra miles included to help you dive deeper into a topic.

At the end of the course, there are 6 challenges that are meant incorporate just about everything that is taught in the material. In my opinion, each challenge had its own level of difficulty and didn't necessarily become more difficult if you did them in order. I found challenges 4-6 to be most similar to the exam...

This is definitely a marathon and not a sprint. I was able to complete this course and exam in about a month but I have prior Active Directory experience and I have taken a similar test. Your speed will vary.

I used [Obsidian](https://obsidian.md/) markdown editor for all my notes.

### The Exam
The exam simulates a real corporate network with a specific goal of obtaining either 100 points or obtaining the *secret.txt* flag. You can read about the exam specifics [here](https://help.offensive-security.com/hc/en-us/articles/360050293792).

I have read many posts saying they were able to clear the objectives in about 8-9 hours, however, it took me about 22 hours to obtain enough points to pass and capture the *secret.txt* flag. I'll admit that there were some things that threw me for a loop and I was stuck a lot longer than I had wished but the exam is not tricky and does not contain any surprises. I definitely had to exercise some of my OSCP muscles while taking this one.

As I went through the exam, I took notes and screenshots to reduce time on writing the report. I wanted to use Obsidian but I decided to use VSCode instead with some additional plugins so I could create my report using this Offensive Security exam report template: [OSCP-Exam-Report-Template-Markdown](https://github.com/noraj/OSCP-Exam-Report-Template-Markdown). VSCode allowed me to have a split screen to see the editor and markdown rendering without switching screens or pressing hot-keys. I did use Obsidian to take general machine notes as I pwned each one.

I actually enjoyed taking the exam and I most definitely learned a few things along the way. 

### Tips
- Do all the challenge labs and take good notes.
- Try and do all the extra miles if possible
- Save all of your code. Throughout the course you will be crafting your own payloads and tweaking them. Make sure you hold on to them and back them up as you will be using theses on the exam.
- Everything you need to know is in the course materials. I think Offsec's new model of training really helps students with having all the necessary knowledge to succeed.

### Conclusion
This was another amazing course by Offensive Security and in my opinion a must have for penetration tester's. I highly suggest pursuing this exam after the OSCP. I think the course covered many of the basic red team tactics used today and maybe in the near future Offsec will create a more advance red team course.

Once again, thank you Offsec for an amazing course and thank you to my wife who listens to my babbling about capturing flags and such.

If anyone needs more info, advice, or mentoring, please don't hesitate to connect with me on LinkedIn and/or email me.

God bless.
