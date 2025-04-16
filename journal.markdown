---
layout: page
title: Journal
permalink: /journal/
---

<style>
    .tep {
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
    }

    .tep-2 {
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
        -webkit-line-clamp: 3;
        -webkit-box-orient: vertical;
    }

    .journal-container {
        display: flex;
        flex-direction: column;
        gap: 24px;
        max-width: 800px;
        margin: 0 auto;
        /* padding: 24px; */
    }

    .journal-entry {
        border: 1px solid #e0e0e0;
        border-radius: 12px;
        padding: 20px;
        background: #fff;
        /* box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05); */
        /* transition: box-shadow 0.2s ease; */
    }

    /* .journal-entry:hover {
        box-shadow: 0 6px 20px rgba(0, 0, 0, 0.08);
    } */

    .journal-entry-title {
        font-size: 1.4rem;
        font-weight: 600;
        margin-bottom: 6px;
        color: #333;
        text-decoration: none;
    }

    .journal-entry-title:hover {
        text-decoration: underline;
        color: #0056b3;
    }

    .journal-entry-date {
        font-size: 0.9rem;
        color: #888;
        margin-bottom: 12px;
    }

    .journal-entry-description {
        font-size: 1rem;
        line-height: 1.6;
        color: #444;
    }
</style>

<div class="journal-container">
  {% for item in site.blogs %}
    {% if item.category == "journal" %}
      <div class="journal-entry">
        <a class="journal-entry-title" href="{{ item.url }}">{{ item.title }}</a>
        <div class="journal-entry-date">{{ item.date | date: "%B %d, %Y" }}</div>
        <div class="journal-entry-description">{{ item.description }}</div>
      </div>
    {% endif %}
  {% endfor %}
</div>
