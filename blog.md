---
layout: default
title: Blog
permalink: /blog/
---
<section class="block wrap" style="border-top:none; padding-top:56px;">
  <span class="eyebrow">Writing</span>
  <h2>Blog</h2>
  <div class="card-grid">
    {% for post in site.posts %}
    <a class="entry-card" href="{{ post.url | relative_url }}">
      <div>
        <div class="entry-date">{{ post.date | date: "%b %-d, %Y" }}</div>
        <div class="entry-title">{{ post.title }}</div>
      </div>
      <span class="arrow">&rarr;</span>
    </a>
    {% else %}
    <div class="empty-note">No posts yet &mdash; check back soon.</div>
    {% endfor %}
  </div>
</section>
