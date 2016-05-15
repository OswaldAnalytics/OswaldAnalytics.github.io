Now the blog is up and running, there was a short break of fixing various issues that cropped up.  I then editted the blog entries to reflect these changes.  To edit a blog just go to the posts folder of my repo and open the blog post file.  Make your changes and hit commit.  This saves a new copy of the file and pushes it to your live site.  While this may not seem that interesting to many, what this also is doing is keeping track of all changes being made.  Git and Github are version control systems, so this applies to the blog as well.  If you change something and do not like it, instead of manually editing the changes to style or structure back you can just revert to an older version by hitting the history button on the Github editing page.

Now I wanted to add a new feature to my blog, an archive of to see all my posts easily.  To do this, first I went to the layouts folder and created this file archive.md:


`
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
`


