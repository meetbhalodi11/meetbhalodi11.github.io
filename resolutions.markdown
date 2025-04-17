---
layout: page
title: Resolutions
permalink: /resolutions/
---

<style>
    .td-none {
        text-decoration: none !important;
    }

    .resolutions-entry-title {
        font-size: 1.4rem;
        font-weight: 600;
        margin-bottom: 6px;
        color: #333;
        text-decoration: none;
    }

    .resolutions-entry-date {
        font-size: 0.9rem;
        color: #888;
        margin-bottom: 12px;
    }

</style>

<div class="resolutions-container">
  {% for item in site.blogs %}
    {% if item.category == "resolutions" %}
      <div style="margin-top: 0.4rem">
        <a href="{{ item.url }}" class="td-none">
          <span class="resolutions-entry-date">{{ item.date | date: "%B %d, %Y" }}</span>
          <span style="margin-left: 0.4rem">{{ item.title }}</span>
        </a>
      </div>
    {% endif %}
  {% endfor %}
</div>
