---

title: "New Year 2019"
date: "2019-01-02"
description: "New Year Resolutions"
author: "Brian Flatt"
---

# New Year 2019 and coding education update

So I've been quite productive as of late with my coding education progress and thought I'd share a few cool things. 

1. 100DaysofCode doesn't really seem to work for me. Not that I havent been coding everyday but I don't always have time to or I forget to post it to twitter everyday. 
2. I got an A in my Computer Science I class which used C++
3. I'm on pset3 in CS50. I believe it's pset3, the music files in c. 
4. I successfully ported my final exam from CS1 from C++ to Python just because. In addition to my formal educaton in CS at local community college, I'm also trying to learn as much as I can on my own and this includes Python. So after learning the basic synstax, I figured what better to truly immerse myself in the language than to try to port my final exam to Python. If I didn't know how to do something I just googled it. I had some issues with the difference between arrays in C++ and lists in Python and how they are implemented differently but I finally got it and finished the project. I uploaded both solutions to my github and can be seen at: 

[C++ solution:](https://github.com/bflatt72/projects/blob/master/CISP1010/FinalExam.cpp)

[Python solution:](https://github.com/bflatt72/projects/blob/master/CISP1010/LoanSched.py)

5. And maybe the most exciting for me is that I created my very first Python script that does something useful for my workflow. I was about to write this blog post in Jekyll when I realized, "Hey, I bet I could write a python script to automate the task of creating the file with the YAML header and all and open the file in my editor." So I got down to the business of writing such a script with the help of Google and this is what I came up with and it works. This was truly an eye opener for me. It was like a light switch. Not just doing endless tutorials and learning syntax I could do something useful and learn at the same time. Amazing. 

```

#!/usr/local/bin/ python3

import time, os, glob, subprocess


title = input("Title:   ")
cat = input("Category:  ")
tags = input("Tags:  ")
d = time.strftime('%Y-%m-%d')

path = "/Users/FlattDev/Documents/Blog/bflatt72.github.io/_posts"

os.chdir(path)

f = open("%s-%s.md" % (d, title), "w+")

print("------", file=f)
print("Title:%s\r" % title, file=f)

if cat: print("Categories: %s\r" % cat, file=f)
if tags: print("Tags: %s\r" % tags, file=f)
print("------", file=f)
f.close()

list_of_files = glob.glob('/users/FlattDev/Documents/Blog/bflatt72.github.io/_posts/*.md')
latest_file = max(list_of_files, key=os.path.getctime)

subprocess.call(['vim', latest_file])

```

What the script does is the following: 

- prompt for post title, category and tags.
- sets the current date
- gets the path to the _posts folder
- changes to that directory
- opens the file with the correctly formatted title
- prints the YAML header information to the file
- closes the file
- gets a list of all .md files in that folder
- gets the last file added to that folder
- opens that file in Vim for editing. 

Pretty damn cool. 

Then I made a shell alias that points to the script so that it can be executed by just typing the name of the file. 

I've been using Vim a lot and getting pretty handy with it but then I downloaded VS Code and was blown away by it. Wow! Game changer. Installed Python extensions and wrote this blog post in it. Set up my terminal to open a file in VS Code by just typing code. 

6. Another related epiphany is that the best way to learn is to do and to build instead of endless tutorials. However, tutorials that actually have you build something are great. Currently working through the Mega Flask tutorial by [Miguel Grinberg](blog.miguelgrinberg.com). It's a great tutorial that actually has you build a functioning web app. 

That's all for now. 

Happy coding. 
