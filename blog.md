---
layout: default
title: "بلاگ | آنتو (onto.ir)"
full_posts: 5
permalink: blog/
---

{% for post in site.posts %}
  {% if forloop.index < page.full_posts %}
  <div class='post'>
    <span class='date'>{{ post.date_fa }}</span>
    <h1><a href='{{post.url}}'>{{post.title}}</a></h1>
    <div class='body'>{{post.content}}</div>
  </div>
  {% else %}
    {% if forloop.index == page.full_posts %}
    <h3>پست‌های قدیمی‌تر</h3>
    <table class='post-list'>
    {% endif %}
    <tr>
      <th nowrap><a href='{{ post.url }}'>{{ post.title }}</a></th>
      <td><span class='date'>{{ post.date_fa }}</span></td>
    </tr>
  {% endif %}
{% endfor %}
</table>