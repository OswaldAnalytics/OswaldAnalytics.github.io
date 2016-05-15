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


Finally I wanted an RSS feed.  I found some code for this as well.  Create a file called Atom.XML and paste this into it:

```
---
layout: null
---

<?xml version="1.0" encoding="utf-8"?>
<feed xmlns="http://www.w3.org/2005/Atom">

 <title>{{ site.title }}</title>
 <link href="{{ site.url }}/atom.xml" rel="self"/>
 <link href="{{ site.url }}/"/>
 <updated>{{ site.time | date_to_xmlschema }}</updated>
 <id>{{ site.url }}</id>
 <author>
   <name>{{ site.author.name }}</name>
   <email>{{ site.author.email }}</email>
 </author>

 {% for post in site.posts %}
 <entry>
   <title>{{ post.title }}</title>
   <link href="{{ site.url }}{{ post.url }}"/>
   <updated>{{ post.date | date_to_xmlschema }}</updated>
   <id>{{ site.url }}{{ post.id }}</id>
   <content type="html">{{ post.content | xml_escape }}</content>
 </entry>
 {% endfor %}

</feed>
Status API Training Shop Blog About
© 2016 GitHub, Inc. Terms Privacy Security Co
```language
```

Now for some cleanup.  I dropped the license.md file as I did not need this.  I edited the readme.md file to my name and the template for the blog I used.  Then I editted my 404 file for fun replacing the text there with some silly stuff.

Now I do own a web domain so I change the CNAME file and change the Hyde URL to my own URL.  Now I go to namecheap, my host, and tell www.oswaldanalytics.com to redirect to http://oswaldanalytics.github.io

With this the basic site is created.  As a final step to prepare the site for blog posts of my own I go to the _posts folder of my repo and delete the three files there from the Jeykll blog.

Next post will detail how to first and post blogs.
