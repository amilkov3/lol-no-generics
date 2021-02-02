---
title: "Posts"
layout: single
author_profile: true
permalink: /posts
comments: true
---

{% for post in site.posts %}
  <p style="margin:50px 0 0 0;font-size:15px;"><i class="far fa-calendar-alt" aria-hidden="true"></i> {{ post.date | date: "%b %d %Y" }}</p>
  {% include archive-single.html %}
{% endfor %}
