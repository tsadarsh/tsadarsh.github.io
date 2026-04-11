---
layout: page
title: Blog
permalink: /blog/
---

Welcome to my blog! Here I share thoughts, tutorials, and experiences from my software development journey.

{% assign grouped_posts = site.posts | group_by_exp: "post", "post.date | date: '%Y'" | sort: "name" | reverse %}

{% for year in grouped_posts %}
  <h2 class="year-header">{{ year.name }}</h2>
  <ul class="posts-list">
    {% for post in year.items %}
      <li class="post-item">
        <a href="{{ post.url }}" class="post-item-link">{{ post.title }}</a>
        <span class="post-item-date">{{ post.date | date: "%b %d" }}</span>
      </li>
    {% endfor %}
  </ul>
{% endfor %}

{% if site.posts.size == 0 %}
  <p>No blog posts yet. Check back soon!</p>
{% endif %}
