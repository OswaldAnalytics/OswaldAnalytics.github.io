With the last post, I detailed the pre-blog downloads, forking a style and editting my information into the blog.  This post I will get more into setting up the blog itself.

Thus far, the blog is linked with our information, but the rest of the site is still linked to the Hyde template.  So I needed to do a series of fast edits.

First for every item in the page_list I made last time I need to actually make a page for.  This is where Jekyll and Markdown shine.  Go back to the Github Repo (short for resposatory) and create a new file.  For this I  created an about page, but this will need to be repeated everything in the page_list that you want to appear in the column part of your blog.

Create a new file and call it about.md.

Now add the following code:


```
---
layout: page
title: About
---

Profile goes here
```

This follows a simple format.  For layout, you tell it you want to use the page style, as opposed to the post style you use for blogs.  There are small differences between the two, but page style will not date the page, whereas blog post will.

Title is simply the title of the Page.  Anything before the dashed lines wil be displaced on the page.  For now I used placeholds.

I repeated this for my CV.

Now I wanted an archive section for my posts where people can review my posts in a faster manner than scrolling through them page by page.  I found some simple code that would do just this:

```
layout: page
title: Archive
---
## Blog Posts

{% for post in site.posts %}
  * {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}
```

Now for some cleanup.  I dropped the license.md file as I did not need this.  I edited the readme.md file to my name and the template for the blog I used.  Then I editted my 404 file for fun replacing the text there with some silly stuff.

Now I do own a web domain so I change the CNAME file and change the Hyde URL to my own URL.  Now I go to namecheap, my host, and tell www.oswaldanalytics.com to redirect to http://oswaldanalytics.github.io

With this the basic site is created.  As a final step to prepare the site for blog posts of my own I go to the _posts folder of my repo and delete the three files there from the Jeykll blog.

Next post will detail how to first and post blogs.
