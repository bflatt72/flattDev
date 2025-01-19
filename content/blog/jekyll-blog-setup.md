---
layout: post
title: Jekyll Blog Setup
date: 2017-09-14
category: posts
tags: [tutorial, blog]

---

Last night I spent a few hours learning how to set up a Jekyll blog and deploying it with Github Pages. I had wanted to start a blog about my experiences in learning web development, but I haven't actually blogged in quite some time. In my research <!--more--> I came across Jekyll and read this article on Smashing Magazine [Build a Blog With Jekyll and Github Pages](https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/). What I liked about the concept of blogging with Jekyll was the control I would have over it and the fact that I could host it for free with Github pages. I would also be able to practice my Git skills and the blog would have version control. Since I needed to set up a blog again anyway, now seemed like a good time to learn Jekyll. Other sources I used to help me in this process were: 



* [Hongkiat-How to Create a Blog with Jekyll - A Beginner's Guide](http://www.hongkiat.com/blog/blog-with-jekyll/)

* [Jekyll Documentation - Quick Start Guide](https://jekyllrb.com/docs/quickstart/)

Things learned or reviewed through this process:

* Git, Github and Github Pages
* Linux (Ubuntu)
* Jekyll
* Ruby?
* Markdown

#### The first step in this process was to install Jekyll from the command line as follows: 

```
sudo gem install jekyll

```

and then to check the installation using:

```
jekyll -v

```

However, upon doing this I received errors stating that it could not find the gem so I tried, as per the Jekyll quick start documentation:

```
sudo gem install jekyll bundler

```

which also did not work. Consulting Google I found I had to do this first:

```
sudo gem install pygments.rb
gem install bundler
bundle install

```

and then the install again and this worked. 

#### The second step was to: 

```
jekyll new myblog
cd myblog
bundle exec jekyll serve

```

This created all the files and folders needed along with the minima theme which is installed by default. I later figured out how to install a new theme, which I did by installing the [Rifyll theme](https://github.com/itsrifat/rifyll), which I will discuss further later. 

Another way to install a Jekyll blog on your machine is to fork and clone a theme repository into your myblog folder. That's how I installed the theme, but not before realizing that by cloning it into the myblog folder it was installing it on top of the already installed minima theme and had to manually rm the minima theme folders and files. 

#### The third step to creating a blog was to change any layout settings in the _config.yml file 

#### Fourth step was to create a blog post in the _posts folder using standard jekyll file naming convention as follows. 

2017-09-14-Blog-Post-Title.md

Markdown can be used to format the post. Once the file is saved, you can run:

```
jekyll serve

```

and point your browser to localhost:4000 to see the blog. 

Oh, the very first thing that needs to be done before anything else is to cd to the myblog folder and run:

```
git init

```

This will set up git version control on the blog and is needed in order to push the blog to your repository. 

Speaking of your repository, you need to head to your Github account and make a repository by clicking the + symbol in upper right hand corner and setting the name of the repository which has to be in the form of username.github.io Trying myblog did not work as username didn't either. Trusty Google pointed me in the right direction. Then copy and paste the repository name and head back to the command line and run the following:

```
git clone git@github.com:yourusername/yourusername.github.io.git

```

Now, after writing a post in the _posts folder with the proper YAML heading as can be found by reading [Front Matter](https://jekyllrb.com/docs/frontmatter/)

Then you can:

```
git add --all
git commit -m "commit message"
git push origin master

```

and voila your blog will be live at username.github.io

Pat yourself on the back because you've created a blog and learned and practiced git commands in the process. The entire process may have taken several hours with googling error messages but you can be proud you've done something, created a blog from scratch, that most people using Wordpress.com will never do. 
 
