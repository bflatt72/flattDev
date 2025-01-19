---
layout: post
title: How to Contribute to Open Source Projects on Github
date: 2017-09-21
category: posts
tags: [general, about, github]

---







Last night I contributed to my very first open source project on Github and it was such an amazing feeling that I want to talk a bit about it and walk through the steps involved. 
<!--more--> 
Backstory: I was searching on Github for people to follow and one person I was familiar with was [Ohans Emmanuel](https://github.com/ohansemmanuel). I knew that he writes great CSS guides and I had conversed with him briefly on Twitter about one of his paid guides. One of his free ones goes into detail about Flexbox and is entitled [Understanding Flexbox](https://github.com/ohansemmanuel/Understanding-Flexbox). As I was looking through this great resource on Github I happened to notice that many of the chapter links in the README.md file were not working. I said, "hmmm, this would be an easy fix, all Id have to do is correct the Markdown in the file. I wonder if he knows the chapter links aren't working." So I submitted an issue about it but instead of waiting for a response I figured I'd go ahead and fix it and if for some reason he didn't want me to or if there was a reason he wanted the links not working for now, all he'd have to do is not accept my pull request and not merge it. I had never contributed to anything on Github up to this point and was unsure of the etiqutte and all involved. So here was the process by which I fixed the links and submitted a pull request. 

1. I went to the project page and forked the project by clicking the fork button. This made a branch of the project into my account. 
2. Then I went to my command line and did the following:
 
``` 
mkdir Understanding-Flexbox
cd Understanding-Flexbox
git clone "URL of the fork"

```

I obtained the URL by going back to the fork and clicking on the clone or download button and copying the URL.

Now I had a copy of the entire project on my local machine and could open the readme file in my editor as follows:

```
cd Understanding-Flexbox
gedit readme.md

```

I edited the Markdown of the links to point to the correct URL's of the relevant chapters and saved the file.

Next step is to push the changes up to my fork on Github. 

```
git add --all
git commit -m "Fix broken chapter links"
git push origin master

```

At this point, I went back to the fork on Github and verified that all links now work and point to each relevant chapter. All that was left was to submit a pull request so that Ohans could merge my fixes up to the main project. 

On the main project page I clicked on the submit pull request button and filled out the title and message letting him know that I fixed the broken chapter links and thanking him for letting me contribute. 

The next morning I woke up to a message from Ohans saying he hadn't noticed the broken links and thanking me for fixing them. I thanked him for letting me contribute even if in such a small way and let him know this was my first Github project contribution. I then went to the main project page and saw that the links now worked.

None of this may seem like a big deal to most people who have been doing this for awhile, but it was exciting for me being my first open source project contribution and now I'm listed on the project as a contributor. Also, I thought this would be a good opportunity to blog about it and giving a short tutorial on the process of submitting a pull request for those who may be even greener at web development than I am. 

And to Ohans, I thank you again for allowing me to contribute and for giving me the opportunity. 
