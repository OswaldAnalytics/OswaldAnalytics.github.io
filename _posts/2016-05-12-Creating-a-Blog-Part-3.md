---
layout: post
title:  "Creating a Blog Part 3, Posting on the Blog"
---

To summarize the last posts, I started with an empty Github, copied a blog theme, changed the default information to my own and set up the site to support blog posts.  This post will thus deal with creating and posting blogs.

I chose Github and Jekyll for my blogs because they used Markdown.  Markdown is a simplified typesetting language.  Whereas programs like Word require you to find the setting you need in one of the many ribbon bars, Markdown you can just type the code yourself.  Since I have not memorized the coding yet, as simple as it may be, and I wanted a live previewer of what I was writing I downloaded Haroopad:

http://pad.haroopress.com/

This gives me a nice two column work environment, one where I type in my blog and format with Markdown and the second showing what it will look like when I publish it.

You can write the blogs straight in Github's editor, but Haroopad gives me a nice insert option in case I forget the code to add formatting.

Now using this blog does require a certain naming convention.  You must name files like this:

year-month-day-Title-Of-Blog.md

So year, dash, month, dash, day, dash, title of the blog with dashes between the words, and .md to make sure it saves in the Markdown format.

To finish the posts, add the following as a header:

```
---
layout: post
title:  "Creating a Blog Part 1"
---
```

This tells the site to render the page with the post style instead of just displaying the raw HTML that builds it.

I like to check my final post over in Sublime text with a spell-checker, but those with better writing skills can skip this.

Now there are several ways to take your finished posts and move them to the blog.  I take the easiest option and just upload them into the _posts folder in my Github repo for the blog. I open this in Github then can drag my posts from my desktop to the _posts folder.  Later, I will start to sync them directly with Github for Windows but for now this is the easiest way.

Next post will finish the setup of the blog by fleshing out the Archive.
