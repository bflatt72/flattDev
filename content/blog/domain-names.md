---
title: "Custom Domain Name"
date: "2017-10-17"
description: "How to set up"
author: "Brian Flatt"
---

So, last night I got around to purchasing a domain name for my blog/portfolio site. After researching several different domain name providers, I came across [1and1.com](http://www.1and1.com), which has an introductory offer too good to pass up, which is $.99 for the first year of your domain, provided that this is your first one. After first year it goes up to $14.99 but you could always change domain name providers if you found a cheaper offering. 

So, I purchased the domain [flattdev.com](http://flattdev.com) and proceeded to set it up with my Jekyll blog site hosted via Github pages at [bflatt72.github.io](http://bflatt72.github.io). The first step is to go to the settings page of your repo and scroll down to where it says custom domain. Type your new domain name in there and click save. 

From there, I knew that I had to set up the domain via the provider in order to point it to the site on Github. But 1and1 doesn't make this easy at all. They pretty much assume you already know what you are doing, because there is nothing to tell you exactly what you need to do. Did I need to set up forwarding to point it to the site? Or did I need to change the DNS settings? Nothing really tells you. On Github, if you click next to the custom domain setting on [Learn More](https://help.github.com/articles/using-a-custom-domain-with-github-pages), there is some helpful info, which basically boils down to, you have to check with the domain provider to find out how to do it. But it did point me in the right direction of WHAT needed to be done. 

First I tried to redirect the domain and that wasn't working, however maybe I didn't wait long enough for it to propogate? At any rate, I changed the DNS settings, changing the A Name to point to Github's IP address, which they provided in their help pages. And, bingo, my page started to work and it worked all night at work and in the morning when I got home. This evening, back at work, I checked it and it had quit working, saying there were too many redirects or something. I'm not sure. I'm not a network guy, as you can tell. But I checked back at 1and1 and found that it had been changed back to a redirect, for some strange reason. 

At this point, frustrated and just wanting someone to tell me which method I needed to employ, I called their 1-800 number and after waiting on hold for over 20 minutes, I finally reached a person, who didn't seem like he knew anymore about this shit than I do. Frustrated with him, I told him I'll figure it out myself, thanks for your help, and hung up. 

After much trial and error, and reading between the lines of what the tech support was TRYING to say, and reading [Stack Overflow](http://www.stackoverflow.com) and Google, here is what I had to do:

For the main domain, [flattdev.com](http://flattdev.com), I had to change the DNS settings to point to the IP address of Github's servers. Github says you have to change the A Name to point to two separate IP addresses but I could only find a way to point it to one, which I did and which is 192.3.252.153 and 192.30.252.154. I just set it to the first one and after a few minutes my website began to work with the new domain name. 

Then if you want to set up the domain to work with the www subdomain, you have to set that up by first creating that subdomain and using a frame redirect on it to point to your actual Github domain at username.github.io. After that change took effect, it began to work. 

Very frustrating, and I'm betting that tech support and help pages at Godaddy are probably a lot better than they are at 1and1. They say you get what you pay for, but if you know what you're doing, and now you do after reading this blog, you can't really beat a domain name for $.99: just don't expect much in the way of help from their tech support. 

<h3 align="center">Updates</h3>

- Finished the portfolio project on Free Code Camp. 

- It is now parked on a separate page of my blog at [flattdev.com](http://flattdev.com) 

- Added a button on the portfolio to point back to the blog. 

- I have read the first book Up and Running in You Don't Know JS by Kyle Simpson. 

- Working on Basic JavaScript in Free Code Camp. 

- Reading The War of Art by Stephen Pressfield

- Saw Bladerunner 2049 other day and really enjoyed it. 

- Listened to several coding podcasts on my travels to and from Raleigh from Knoxville over the weekend. Enjoying CodeNewbies and Developer Tea. Also listened to TWiT, not realizing it was still being produced. How old is Leo Laporte getting to be? 

![Leo Laporte](/img/leolaporte.png){:class="img-responsive center-block" height="150px" width="150px"}

<h3 align="center">Notable blog posts I read</h3> 

- [Developing a Writing Habit - In Just 5 Minutes a Day](https://medium.com/swlh/developing-a-writing-habit-in-just-5-minutes-a-day-865f33c13b62) by Mary Boone on Medium
- [The Art of Comments](https://css-tricks.com/the-art-of-comments) at CSS Tricks




<h3 align="center">Goals</h3> 
 
- Write for at least 15 minutes every day. 

- Continue with 100DaysofCode, currently on Day 22. 

- Start the Make a Bookmarker project that saves to local storage, using only vanilla JS by Traversy Media on Youtube.

- Next books to read:
  1. The Obstacle is the Way by Ryan Holiday.
  2. Tranform Your Habits by James Clear



Until next time, Peace!!
