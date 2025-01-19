---
title: "Git Merge Conflicts"
date: "2017-10-03"
description: "How to Merge and avoid"
author: "Brian Flatt"
---


In this post I am going to talk about my first git revert I did on one of my projects tonight after learning first hand about merge conflicts and not fully understanding what to do at the time. And then I will give a few updates on my Web Dev learning progress and where I'm going from here. 
<!--more--> 
<h3 align="center">Git Merge Conflicts</h3>

So what happened was this. I had made a personal webpage project a week or so ago, my first one since learning HTML/CSS again after a few years. Then I created a branch called flex-box and I refactored the site and my Shaw Howe project using flexbox instead of inline-block and floats/clearfix. Great. All was well and I kept both branches for future reference. Last night I decided I was going to merge them and delete the flexbox branch, which I did. I got some merge errors but did what it said and I thought all was well.

Then at work last night, I was making some file edits on the Github website because I didn't want to open up my laptop at the time. Figured I'd just pull the changes down to the local repo later. Fine. I forgot though that I had also made some edits and commits on the local repo the day before. Pretty sad when you have merge conflicts and you're the only one working on the project. haha. So anyway, I knew I needed to pull my changes from the remote origin branch so I did: 

```
git pull origin master

```

and I got an error stating that my repo wasn't up to date and I couldn't merge, which is what pull does after fetch. So I then:

```
git add "filename"
git commit -m "message"

```

and try to pull again but now I get errors talking about a merge conflict. I open up the file and I see all this weird shit going on like 

```
<<<<<<<HEAD

FLEXBOX>>>>>>>

```

What the hell is that? I didn't know. So I said screw it and was manually deleting all of that when I realized, "hey wait a minute this is what git is for,all I gotta do is revert back to an older commit and I should be good." So I re watched the relevant   

 <a href="https://youtu.be/RIYrfkZjWmA">The Net Ninja</a>   

video on Youtube and I checked out an older commit to make sure it was what I wanted, because some other weird changes had taken place too with my container widths and such. I reverted back to it using git revert and all was well. 

It was then that I started reading up on the original merge issue and found out that those original weird changes in my file was git telling me what the conflict was. It was showing me the changes from both branches that were in conflict with each other. Oh well, that was done and the branch deleted. So the issue was that when I tried to pull the changes down from the remote origin it wouldn't work because my local branch wasn't up to date. And when I tried to make it up to date, there were merge conflicts because my origin and master branches had conflicting edits. I could have fixed it by just manually fixing the file but I did a git revert and fixed it that way. 

Moral of the story. Be careful. Don't edit files on Github origin and local master branches at same time unless you're careful. What you should do if you are going to edit your files online, make sure to do a git pull first thing before you edit your files locally, that way you're up to date and there won't be any conflicts. Then you can edit and commit locally and push back up to origin. Then you can edit online if you ever need to and pull it back down to master local branch. But when you mess up and have edits in both master and origin branches, conflicts will arise and when you don't know what you're looking at you'll think your local file got corrupted. 


So that was funny but a learning experience. And what's really funny is that that is actually how we learn, by making mistakes and googling and learning. Thank goodness for Stack Overflow, huh? I don't think there's an issue I've ever come across that didn't pop up on stack overflow via a google search. 

<h3 align="center">Updates</h3>

I am also going to school at the local community college getting my 2 year degree in Computer Information Technology - Programming. I'm currently taking Intro to Statistics and Intro to Computer Programming and Logic, both online with all exams taken on campus. Have had 2 exams so far, one in each class and I got a 94 in Stats and 98 in Programming. The latter consisted mostly of computer technology history, some binary number conversions and analyzing what a particular assembly language program was doing and how it worked. I really enjoyed learning the basics of Assembly because it teaches you about memory and the hardware architecture of the chipset. Cool. 

This week in Programming we have a webpage project to create a webpage using HTML/CSS and it has to include some information about our hobbies and interests and must include at least 3 to 5 photos, a few links and at least one ul or ol list. My solution can be seen at:

<a href=
"https://bflatt72.github.io/projects/CITC1301">CITC1301</a>

Yesterday I completed the Build a Tribute Page project on FreeCodeCamp. My solution can be seen at   

 <a href="https://codepen.io/bflatt72/full/zEEoWB">Dr Sheldon Cooper</a>   

It was my understanding that we were to complete the project using only bootstrap so I tried to do that as much as possible using very little custom CSS. What I found was that I don't like Bootstrap all that much. For starters it doesn't use best practices, clutters your HTML with a lot of non semantic classes and doesn't allow as much styling options. For example, with milions of colors to choose from, Bootstrap only gives you like 6 color options. But I did it and it's a very basic solution, nothing fancy. My next project will be to complete the Build a Personal Portfolio Webpage from FreeCodeCamp. 

I also need to work on getting better organized. That's always been one of my biggest issues to date. I started the #100daysofcode challenge and have that downloaded from Github to a local repo and I try to update that on a regular basis. I also want to add some files to that repo where I can add resources I've come across and a progress folder detailing my exact curriculum I'm following as I complete each learning resource and project. I'm kind of doing both FreeCodeCamp and The Odin Project and have also taken great notice of a learning guide on Github that P1xt put together from a thread he originally had on Reddit. It can be found at   

<a href="https://github.com/P1xt/p1xt-guides">P1xt</a>   

He has several different guides but the one I want to work through over the next two years is the one on Web Development with Computer Science. My plan is to learn as much Web Dev as I can, on the JavaScript side of things instead of Rails while obtaining my 2 year degree in computer programming over the next two years, which will also allow me to take part in an internship towards the end of my degree and when I'm done with all of this I would love to get a job somewhere in Oak Ridge TN, maybe the lab? That would be quite awesome. My only concern is my age. I'm currently 45 and will be 47 when I get done with my degree, however various people have assured me hiring managers do hire career changers at my age. Who's gonna tell me I can't do it anyway? I'm the only one that can hold myself back. 

Peace!!! 
