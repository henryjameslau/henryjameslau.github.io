---
layout: page
title: All blog articles
---
<br>
<ul>
  {% for post in site.posts %}
    <li>
      <h5><a href="{{ post.url }}">{{ post.title }}</a>  <small>{{post.date | date_to_string}}</small></h5>
    </li>
  {% endfor %}
</ul>