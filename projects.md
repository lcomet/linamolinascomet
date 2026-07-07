---
layout: default
title: Projects
permalink: /projects/
---
<section class="block wrap" style="border-top:none; padding-top:56px;">
  <span class="eyebrow">Work</span>
  <h2>Projects</h2>
  <div class="card-grid">
    {% assign proj_posts = site.posts | where_exp: "p", "p.categories contains 'projects'" %}
    {% for post in proj_posts %}
    <a class="entry-card" href="{{ post.url | relative_url }}">
      <div>
        <div class="entry-date">{{ post.date | date: "%b %-d, %Y" }}</div>
        <div class="entry-title">{{ post.title }}</div>
      </div>
      <span class="arrow">&rarr;</span>
    </a>
    {% else %}
    <!-- Fallback: your original theme listed project entries the same way as
         blog posts (from _posts/). If your "my project" entry doesn't show up
         above, it likely isn't tagged with a "projects" category — add
         `categories: [projects]` to that post's front matter, or replace this
         whole fallback block with a manual list like the one below. -->
    <a class="entry-card" href="{{ '/someproject/' | relative_url }}">
      <div>
        <div class="entry-date">Nov 27, 2023</div>
        <div class="entry-title">my project</div>
      </div>
      <span class="arrow">&rarr;</span>
    </a>
    {% endfor %}
  </div>
</section>
