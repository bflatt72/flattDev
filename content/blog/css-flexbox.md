---
layout: post
title: Learning CSS Flexbox and Progress Update
date: 2017-09-26
category: posts
tags: [Tutorial, CSS, HTML, Flexbox]

---



For the past week or so I've been working through [Shay Howe's HTML/CSS Tutorial](learn.shayhowe.com) and last night I completed it. Instead of just reading through it though and trying to retain as much as possible,  I actually coded his example website along with the tutorial making sure never to use copy and paste except for color codes and long paragraph sections. All the code was done by hand, code along style.  
<!--more--> 
### My Thoughts  

Shay Howe's tutorial is a really great resource for a birds eye view of HTML and CSS and it gets you to build a pretty complex multi page website for a Styles Conference complete with a schedule of events and a Google map of the location. 

My iteration of the website can be seen at [Styles Conference](https://bflatt72.github.io/projects/shayhowe)

To build out the full website there are about a dozen or more speakers to include on the speakers page along with their bios. I did not build out all of the speakers as I figured after doing a few of them I would know how to do it and it's not a real production website anyway. 

This tutorial was also written before Flexbox and CSS Grid layout and also does not go into frameworks like Bootstrap at all. This was how websites were built prior to all of that but but with CSS involved, one didn't have to use HTML tables anymore to build layouts. You do use tables though to build the schedule page. 

You also create a grid for the layout of major sections and then use floats and inline block to move the elements within the grid, however this is not the new CSS Grid implementation that everyone is now talking about in 2017. 

The way this was done prior to Flexbox and all of that was done by first defining the grid as follows:

```
.container,
 grid {
	margin: 0 auto
	width: 960px;
}

.container {
	padding-left: 30px;
	padding-right: 30px;
}

.col-1-3 {
	width: 33.3%;
}

.col-2-3 {
	width: 66.66%
}

.col-1-3,
.col-2-3 {
	display: inline-block;
	vertical-align: top;
}

.grid,
.col-1-3,
.col-2-3 {
	padding-left: 15px;
	padding-right: 15px;
}

```

This is quite a lot but essentially its saying that an element with a class of col-1-3 will take up 33.3% of the page and an element with a class of col-2-3, twice that or 66.66% and sets some styling to the grid and sets display to inline block so that elements follow each other inline and don't stack up on the page. 

There's also a clearfix added to the CSS due to the use of floats. 

Now in the HTML you can layout the page like this:

```
<section class="row">
	<div class="grid">

<section class="teaser col-1-3">
	<h5>Speaker</h5>
	<a href="speakers.html">
		<img src="assets/images/home/speakers.jpg" alt="Professional Speaker">
		<h3>World Class Speakers</h3>
	</a>

	<p>Dadadadadada Lorem Ipsum </p>

	</section><!--

--><section class="teaser col-1-3">
      etc etc

```

Notice how we had to comment out the spaces between the teaser sections. This was because of the way we were doing the layout with inline-block. Without this commenting out in between, then the sections would have spaces between them and would then wrap to next line if they overflowed the line. Using inline block allows us to layout the 3 teaser sections on same line next to each other instead of the default block behavior where they stack up below each other however if we don't comment out the spaces in between then it wont' all fit on one line and the third section will wrap to next line. 

As they say in web developement circles, this all worked but it was "hacky". It was a hack, a way around the limited layout capabilities of CSS at the time. They didn't have to use tables or anything but if you wanted to layout sections on the page like this you had to use inline block and the comment hack. 

With Flexbox this would all be done away with quite simply.  

The logo of the page is floated to the left and the navbar is set to inline block and text aligned to the right. Because of the use of the float we have to apply the clearfix (yet another hack) to the nearest parent element by adding the group class to it. 

This was all great and you can have a look at the finished website and it's all quite nice and works. As I said this was the way layouts were done before Flexbox and CSS Grid. You had to hack around the limitations of CSS at the time. 

But then with Flexbox things became so much easier and after familiarizing myself with it, what I decided to do was to create another branch in my repo and call it flex-box. On that branch I refactored the website using flexbox instead of the old inline blocks and grid layout. With the use of flexbox all of that can be deleted. Mine still has some of the old code in it though because I just wanted to demonstrate my new found knowledge of Flexbox. 

You can look at my repos and the two branches by going to[master](https://github.com/bflatt72/projects/tree/master/shayhowe) and [flexbox](https://github.com/bflatt72/projects/tree/flex-box/shayhowe). 

But watch what we can do now. We can delete that entire section in the CSS creating the grid, we can delete the clearfix because we aren't using floats anymore and we can delete the old group class for the clearfix and the row class and grid class. Pretty amazing. And watch what we do now. Like the old Outkast song [So Fresh and so Clean](https://youtu.be/-JfEJq56IwI) haha. 

Now we just set a flex container around the elements we want to layout and then the elements inside the container become flex items. For my nav bar at top for example:

``` 
	<nav class="primary-nav">
		<ul class="nav">
			<li><a href="index.html">Home</a></li>
			<li><a href="speakers.html">Speakers</a></li>
			<li><a href="schedule.html">Schedule</a></li>
			<li><a href="venue.html">Venue</a></li>
			<li><a href="register.html">Register</a></li>
		</ul>
	</nav>

```

	
Then in the CSS:



```
 	.nav {
 		display: flex;
 		justify-content: flex-end;
 }

```
 And that's it. The nav bar links now are side by side in the header and align to the right side of the screen and then we can apply some margin and padding properties to align it precisely how we want. 

 There's actually a whole lot more involved with Flexbox than that and a whole lot more that you can do. This is just scratching the surface but you can see how powerful it is and how we no longer have to use floats and clearfixes or inline-block and comment hack. 

 Some great resources I used to learn Flexbox were:

 1. [Understanding Flexbox by Ohans Emmanuel](https://github.com/bflatt72/Understanding-Flexbox)
 2. [The Net Ninja Flexbox Tutorial vids on Youtube](https://www.youtube.com/playlist?list=PL4cUxeGkcC9i3FXJSUfmsNOx8E7u6UuhG). I can't recommend all of his vidoes enough. I have also gone through his Git/Github tutorials and they are quite simply amazing. He's currently doing a series on the new CSS Grid implementation. 
 3. [MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)
 4. [CSS-Tricks A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

 After this, my plan going forward is as follows: 

 1. I am going to do the video code along series by Wes Bos called [What the Flexbox](https://flexbox.io)
 2. Do the first couple front end development projects on FreeCodeCamp
 3. Re do the Google home page project from the Odin Project

 And then I'm gonna move on to Javascript. 



 Things I've learned over the last couple of weeks:

 1. Git/Github
 2. HTML/CSS
 3. Flexbox
 4. Beginning CSS Grid
 5. Bootstrap
 6. I also spent an evening tricking out my Sublime text editor with cool plugins/packages and installed an in editor tutorial on keyboard shortcuts and I've begun using them. 

 
