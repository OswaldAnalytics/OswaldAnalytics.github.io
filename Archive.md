---
layout: page
title: Archive
---

## Blog Posts

{% for page in site.pages_list %}
              &nbsp;&nbsp;&nbsp;<small><a href="{{ page[1]  }}">{{ page[0] }}</a></small>
          {% endfor %}
