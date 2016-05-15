---
layout: post
title:  "Creating a Blog Part 1"
---

I decided that to practice my writing to improve my thesis and overall graduate level writing ability, I would create a blog.  This would allow me to practice my writing, share ideas and learn to edit out the errors in my writing.  Looking over traditional options however left me very unsatified.  I had heard of people using github to run blogs so I decided to give it a shot.

Gitgub blogs are not like traditional blogs.  While you have the option to use HTML and CSS, you also have the option to run Markdown for your pages and Jekyll for your style.  I encountered Markdown for R and really liked how simple it was to use, but Jekyll seemed really scary for someone who never got into the Git itself.  Instructions said to use Git to get Ruby then Ruby to get Jekyll and suddenly I would have a whole lot of new stuff to learn.  But it turns out you do not have to go that way.

To get started I went to my Github page and renamed it to OswaldAnalytics with the intention of using it as more than a copy machine for code.  Next, I installed GitHub for Windows on my computer.  I had it but it needed an update.  Also I am not sold entirely on it.  Finally I needed a markdown editer.  I planned to use Notepad++, but Haroopad was suggested so I figured I would give it a try since it offered a live preview.  I then grabbed a Markdown cheatsheet:

http://media02.hongkiat.com/blogger-cheatsheet-resources/markdown-cheatsheet.jpg

Next step was to set up the blog space online.
Now I have the space I needed a blog.  Git, Rudy and Jeykll offered the complex, command line option but I wanted something simplier.  Much simplier.  Barry Clark gave me a great solution and this guide follows his:

https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/

I went to http://jekyllthemes.org/ and found Hyde which offered a nice column and page style I liked.  Simple elegent and lacking unneeded junk.  Now to make this mine.  I went to their github page and forked it.  Now I have a copy of it in my own Github folder.  Here I rename the repository oswaldanalytics.github.io.  Now I am hosting an exact copy of the Hyde theme page as my blog.

Since I did not want a theme page but a blog it is time to make some edits.

Prior research told me th The _config.yml file contains the information I would need to change for the blog to display my infomation instead of Mark Otto's, who created Hyde.

The file is fairly easy to understand.  Look for infomation and change it out to my information.


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


Now the file looks like this for mine after editing:


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
  Feed: '/atom.xml'

github:
  repo:           https://github.com/oswaldanalytics
```


Some changes in there not listed so far.  First I changed markdown language to kramdown and the highlighter to rouge.  If you do not github will glady send hundreds of emails suggesting you do.  Also get rid of permalinks.  Github does not like them anymore.  The rest is straight forward.  Replace and add in your information.  I removed some I did not use like twitter

Now change page_list to what you want to display in the column part of your page.  I wanted an about section, a place to view my old posts and my CV.  I also added feed, but I will deal with that in a different blog.  Commit this (save for Github).  Do not worry if you mess up, Github has version control, so all previous versions are recorded and you can also revert back to the original.

Now this is set up, we can move onto changing up the rest of the site.  This will be talked about in the next post.
