---
layout: page
title: Posts
excerpt: "An archive of articles sorted by date."
search_omit: true
permalink: /posts
---
{% include _mailchimp-sign-up.html %}
<ul class="post-list">
{% for post in site.posts %} 
  {% if post.published %} 
    <li><article><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></span>{% if   post.excerpt %} <span class="excerpt">{{ post.excerpt | remove: '\[ ... \]' | remove: '\( ... \)' | markdownify | strip_html | strip_newlines | escape_once }}</span>{% endif %}</a></article></li>  
  {% endif %} 
{% endfor %}
</ul>