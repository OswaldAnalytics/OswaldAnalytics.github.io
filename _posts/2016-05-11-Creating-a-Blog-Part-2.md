---
layout: post
title:  "Creating a Blog Part 2, Setting up Information Pages"
---

With the last post, I detailed the preparation downloads, forking a style and editing my information into the blog.  This post I will get more into setting up the blog itself.

Thus far, the blog is linked with our information, but the rest of the site is still based on the Hyde style page.  So I needed to do a series of fast edits.

First for every item in the page_list I made last time I need to actually make a page for.  This is where Jekyll and Markdown shine.  I just had to go back to the Github repo and create a new file for each page I would make.  So to create the About page, I created a new file and called it about.md.

Now I added the following code:


```
---
layout: page
title: About
---

Text goes here
```


This follows a simple format.  For layout, you tell it you want to use the page style, as opposed to the post style that will be used for blog posts.  The title is simply the title of the Page.  Anything after the second dashed line will be displaced on the page.  For now I used placeholders saying temp.

I repeated this for my CV, and the Archive page.  The Archive page thus far is not functional, but I will discuss setting it up in a later post.

Now for some cleanup in the repo folder itself.  I deleted the license.md file as I did not need this.  The CNAME file I deleted and set up a redirect to my blog from my domain host on my domain hosting page.  I edited the readme.md file to my name and the template for the blog I used.  This page shows when people visit my Github repo on Github.  Then I edited my 404 file for fun replacing the text there with some silly stuff.

With this the basic site is created.  As a final step to prepare the site for blog posts of my own I go to the _posts folder of my repo and delete the three files there from the Jekyll blog.

Next post will detail how to first write and then post blogs.
