---
layout: default
title: Summer Projects
permalink: /summer-projects/
---

# Summer Projects

This section will contain summer projects, experiments, and technical work.

## Featured Summer Projects

{% assign summer_pages = site.pages | where_exp:"page","page.url contains '/summer-projects/summer/'" | sort: "url" %}
{% if summer_pages.size > 0 %}
{% for page in summer_pages %}
- [{{ page.title }}]({{ page.url }})
{% endfor %}
{% else %}
No summer project pages found yet.
{% endif %}
