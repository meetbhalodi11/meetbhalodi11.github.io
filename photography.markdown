---
layout: page
title: Photography
permalink: /photography/
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
    
    .photography-container {
      max-width: 900px;
      margin: 0 auto;
      /* padding: 24px; */
      display: flex;
      flex-direction: column;
      gap: 24px;
    }

    .photo-card {
      display: flex;
      flex-direction: row;
      border: 1px solid #ddd;
      border-radius: 12px;
      overflow: hidden;
      /* box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05); */
      background-color: #fff;
      /* transition: box-shadow 0.3s ease; */
    }

    /* .photo-card:hover {
      box-shadow: 0 6px 18px rgba(0, 0, 0, 0.1);
    } */

    .photo-image {
      width: 300px;
      height: 200px;
      object-fit: cover;
      display: block;
      flex-shrink: 0;
    }

    .photo-content {
      padding: 16px 20px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      flex: 1;
    }

    .photo-title {
      font-size: 1.4rem;
      font-weight: bold;
      margin: 0 0 8px;
      color: #222;
      text-decoration: none;
    }

    .photo-title:hover {
      color: #007acc;
      text-decoration: underline;
    }

    .photo-description {
      font-size: 1rem;
      color: #555;
      margin-bottom: 8px;
    }

    .photo-date {
      font-size: 0.85rem;
      color: #999;
    }

    @media (max-width: 700px) {
      .photo-card {
        flex-direction: column;
      }

      .photo-image {
        width: 100%;
        height: auto;
      }
    }
</style>

<div class="photography-container">
  {% for item in site.blogs %}
    {% if item.category == "photography" %}
      <div class="photo-card">
        <a href="{{ item.url }}">
          <img class="photo-image" src="{{ item.image }}" alt="{{ item.title }}">
        </a>
        <div class="photo-content">
          <a class="photo-title" href="{{ item.url }}">{{ item.title }}</a>
          <p class="photo-description">{{ item.description }}</p>
          <p class="photo-date">{{ item.date | date: "%B %d, %Y" }}</p>
        </div>
      </div>
    {% endif %}
  {% endfor %}
</div>
