---
layout: page
title: Blogs
permalink: /blogs/
---

<style>
    .td-none {
        text-decoration: none !important;
    }

    .resolutions-entry-date {
        font-size: 0.9rem;
        color: #888;
        margin-bottom: 12px;
    }

</style>

<div class="blogs-container">
  {% for item in site.blogs %}
    {% if item.category == "blogs" %}
      <div style="margin-top: 0.4rem">
        <a href="{{ item.url }}" class="td-none">
          <span class="resolutions-entry-date">{{ item.date | date: "%B %d, %Y" }}</span>
          <span style="margin-left: 0.4rem">{{ item.title }}</span>
        </a>
      </div>
    {% endif %}
  {% endfor %}
</div>