---
layout: post
title:  "Creating a Blog Part 1 - Preparation and Set-Up"
---


I decided that to practice my writing I would create a blog.  I had a few blogs in the past but each one either required knowledge of HTML and CSS or used a template I had no control over.  I had heard of people using Github to run blogs so I decided to give the blog another try.

Github blogs are not like traditional blogs.  While there is the option to use HTML and CSS, there is also the option to run Markdown for the pages and Jekyll for the style.  I encountered Markdown for R and really liked how simple it was to use, but Jekyll seemed really scary for someone who never got into the command line programming itself.  Instructions said to use Cygwin to get Git, then Git to get Ruby, and then Ruby to get Jekyll. That was a whole lot of command line stuff and three languages before anything was done with making a blog.  But it turns out I did not have to go that way.

First I decided to get the programs I would need in advance.  I downloaded (or updated since I already had them) Sublime Text, Haroopad, and Github for Windows.  Sublime Text I would use as my generic file editor and spell-checker, Haroopad for typesetting in Markdown as it has a live preview and Github for Windows to update my Github without having to go to the website repeatedly.  Finally, I got a Markdown cheatsheet as it has been a while since I really used it.

http://media02.hongkiat.com/blogger-cheatsheet-resources/markdown-cheatsheet.jpg

The next step was to set up the blog space online. 
Git, Rudy and Jekyll offered the complex, command line option but I found something simpler.  Barry Clark had created a guide to create a Github blog, with almost no coding and my guide will follows his fairly closely:

https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/

The first step was to find a Jekyll theme I wanted to use for my blog's layout. I went to http://jekyllthemes.org/ and found Hyde which offered a nice column and page style I liked.  Now to make this mine.  I went the Github page for the style and forked it.  Forking is a way of copying things in Github from someone else's public account to your own.  Now I had a copy of it in my own Github folder.  Here I rename the repository (or repo for short) oswaldanalytics.github.io.  Format for this is username.github.io.  Now I am hosting an exact copy of the Hyde style page as my blog.

Next I needed to start editing stuff to make the page become my page. or at least have my information.  The _config.yml file contains the information I would need to change to tell the blog who I was.

The file is fairly easy to understand.  Look for information and change it out to my information.


```
# Dependencies
markdown:         redcarpet
highlighter:      pygments

# Permalinks
permalink:        pretty
relative_permalinks: true

# Setup
title:            Hyde
tagline:          'A Jekyll theme'
description:      'A brazen two-column <a href="http://jekyllrb.com" target="_blank">Jekyll</a> theme that pairs a prominent sidebar with uncomplicated content. Made by <a href="https://twitter.com/mdo" target="_blank">@mdo</a>.'
url:              http://hyde.getpoole.com
baseurl:          /

author:
  name:           'Mark Otto'
  url:            https://twitter.com/mdo

paginate:         5

# Custom vars
version:          2.1.0

github:
  repo:           https://github.com/poole/hyde
```

After editing the file with my information it looks like this: 


```
#Dependencies
markdown:         kramdown
highlighter:      rouge

# Setup
title:            Oswald Analytics
tagline:          A blog on academia, statistics, research and life.
description:      A blog on academia, statistics, research and life.
url:               http://oswaldanalytics.github.io 
baseurl:          /

author:
  name:           'Christopher Oswald'
  url:             http://oswaldanalytics.github.io 

paginate:         10

pages_list:       
  About: '/about'
  Archive: '/archive'
  CV: '/cv'

github:
  repo:           https://github.com/oswaldanalytics
```


Three other changes were needed.  First I changed Markdown language to Kramdown and the code highlighter to Rouge.  If you do not Github will gladly send hundreds of emails suggesting you do.  Also I got rid of the lines about permalinks.  Github also emails warnings about them.  The rest is straight forward.  Replace and add in your information.  I removed somethings I did not use like twitter.

Now I created the column part of the blog.  To do this I edited the page_list to what I wanted to be always accessible.  I wanted an About section, my CV and what would later become an Archive for old posts.  
When I was finished editing I hit commit, and the page changed looking more like a page of my own.  

Next post I will discuss how to the pages that I wanted my blog to have.