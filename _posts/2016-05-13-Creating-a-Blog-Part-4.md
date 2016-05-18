---
layout: post
title:  "Creating a Blog Part 4"
---


Now the blog is up and running, there was a short break of fixing various issues that cropped up.  I then edited the blog entries to reflect these changes.  To edit a blog just go to the posts folder of my repo and open the blog post file.  Make your changes in the editor and hit commit.  Or you can change the files on your computer and move them into the _posts folder to replace them.  

Both of these will save a new copy of the file and pushes it to your live site.  While this may not seem that interesting to many, what this also is doing is keeping track of all changes being made.  Git and Github are version control systems, so this applies to the blog as well.  If you change something and do not like it, instead of manually editing the changes to style or structure back you can just revert to an older version by hitting the history button on the Github editing page.

Now I all that was left to do was to get the archive page working.  I replaced the temporary text I had with the following code.


{% raw %}
```
---
layout: page
title: Archive
---

<ul>
  {% for post in site.posts %}

    {% unless post.next %}
      <h3>{{ post.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h3>{{ post.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}

    <li>{{ post.date | date:"%b" }} <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

```
{% endraw %}

Now the Archive page will be an actual working Archive.  Not to fellow coders.  If you wish to embed code like that you cannot the three back-ticks you normally use in Markdown for code chunks, you must use the raw tag.  Otherwise Liquid will render the code thinking it is part of the page style.  So use the standard {% %} container with raw and endraw to subset any sections about styles that do not work with Markdown's code chunks:



