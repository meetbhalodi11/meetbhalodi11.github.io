---
layout: home
---

<style>
  .home-posts {
    max-width: 800px;
    margin: 0 auto;
    /* padding: 32px 16px; */
    display: flex;
    flex-direction: column;
    gap: 24px;
  }

  .post-preview {
    border-bottom: 1px solid #eee;
    padding-bottom: 16px;
  }

  .post-preview:last-child {
    border: none;
  }

  .post-preview a {
    font-size: 1.4rem;
    font-weight: 600;
    color: #007acc;
    text-decoration: none;
  }

  .post-preview a:hover {
    text-decoration: underline;
  }

  .post-date {
    font-size: 0.85rem;
    color: #999;
    margin-bottom: 6px;
  }

  .post-desc {
    font-size: 1rem;
    color: #444;
  }
</style>

<div class="home-posts">
  {% assign all_posts = site.blogs | sort: 'date' | reverse %}
  {% for post in all_posts limit:5 %}
    <div class="post-preview">
      <div class="post-date">{{ post.date | date: "%B %d, %Y" }}</div>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <p class="post-desc">{{ post.description }}</p>
    </div>
  {% endfor %}
</div>
