---
layout: home
---

<head>
  <link rel="shortcut icon" href="/assets/images/favicon.ico" type="image/x-icon">
  <link rel="icon" href="/assets/images/favicon.ico" type="image/x-icon">
</head>

<style>
    .tep {
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
    }

    .home-container {
        max-width: 1000px;
        margin: 0 auto;
    }

    .section-header {
        margin: 40px 0 20px 0;
        border-bottom: 1px solid #bbb;
        padding-bottom: 8px;
        display: flex;
        justify-content: space-between;
        align-items: baseline;
    }
    
    .section-title {
        font-size: 1.5rem;
        font-weight: 500;
        color: #333;
    }
    
    .section-link {
        font-size: 0.9rem;
        color: #007acc;
        text-decoration: none;
    }
    
    .section-link:hover {
        text-decoration: underline;  
    }

    .featured-post {
        margin-bottom: 40px;
        /* background-color: #f9f9f9; */
        border: 1px solid #eee;
        border-radius: 8px;
        padding: 20px;
        /* box-shadow: 0 2px 10px rgba(0,0,0,0.05); */
    }
    
    .featured-post .post-date {
        font-size: 0.9rem;
        color: #777;
    }
    
    .featured-post a {
        font-size: 1.8rem;
        font-weight: 700;
        text-decoration: none;
        display: block;
        margin: 10px 0;
    }
    
    .featured-post a:hover {
        color: #0056b3;
    }
    
    .featured-post .post-desc {
        font-size: 1.1rem;
        line-height: 1.6;
    }

    .post-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(280px));
        gap: 24px;
        margin-bottom: 40px;
    }

    .post-card {
        border: 1px solid #eee;
        border-radius: 6px;
        padding: 16px;
        transition: transform 0.2s, box-shadow 0.2s;
    }

    .post-date {
        font-size: 0.85rem;
        color: #999;
        margin-bottom: 6px;
    }

    .post-card a {
        font-size: 1.2rem;
        font-weight: 600;
        text-decoration: none;
        display: block;
        margin-bottom: 10px;
    }

    .post-card a:hover {
        color: #007acc;
    }

    .post-desc {
        font-size: 0.95rem;
        color: #444;
        line-height: 1.4;
    }
</style>

<div class="home-container">
  <!-- Featured Post (latest post) -->
  {% assign latest_post = site.blogs | sort: 'date' | reverse | first %}
  <div class="featured-post">
    <div class="post-date tep">{{ latest_post.date | date: "%B %d, %Y" }}</div>
    <a href="{{ latest_post.url }}">{{ latest_post.title }}</a>
    <p class="post-desc">{{ latest_post.description }}</p>
  </div>

  <!-- Recent Tech Posts (assuming you have a tech category) -->
  {% assign tech_posts = site.blogs | where_exp: "post", "post.url contains 'tech'" | sort: 'date' | reverse %}
  {% if tech_posts.size > 0 %}
  <div class="section-header">
    <h2 class="section-title">Tech</h2>
    <a href="/tech" class="section-link">View all tech posts →</a>
  </div>
  <div class="post-grid">
    {% for post in tech_posts limit:3 %}
      <div class="post-card">
        <div class="post-date">{{ post.date | date: "%B %d, %Y" }}</div>
        <a href="{{ post.url }}" class="tep">{{ post.title }}</a>
        <p class="post-desc">{{ post.description }}</p>
      </div>
    {% endfor %}
  </div>
  {% endif %}
  
  <!-- Recent Journal Posts -->
  {% assign journal_posts = site.blogs | where_exp: "post", "post.url contains 'journal'" | sort: 'date' | reverse %}
  {% if journal_posts.size > 0 %}
  <div class="section-header">
    <h2 class="section-title">From the Journal</h2>
    <a href="/journal" class="section-link">View all journal posts →</a>
  </div>
  <div class="post-grid">
    {% for post in journal_posts limit:3 %}
      <div class="post-card">
        <div class="post-date">{{ post.date | date: "%B %d, %Y" }}</div>
        <a href="{{ post.url }}" class="tep">{{ post.title }}</a>
        <p class="post-desc">{{ post.description }}</p>
      </div>
    {% endfor %}
  </div>
  {% endif %}
  
  <!-- Recent Photography Posts -->
  {% assign photo_posts = site.blogs | where_exp: "post", "post.url contains 'photography'" | sort: 'date' | reverse %}
  {% if photo_posts.size > 0 %}
  <div class="section-header">
    <h2 class="section-title">Photography</h2>
    <a href="/photography" class="section-link">View all photography posts →</a>
  </div>
  <div class="post-grid">
    {% for post in photo_posts limit:3 %}
      <div class="post-card">
        <div class="post-date">{{ post.date | date: "%B %d, %Y" }}</div>
        <a href="{{ post.url }}" class="tep">{{ post.title }}</a>
        <p class="post-desc">{{ post.description }}</p>
      </div>
    {% endfor %}
  </div>
  {% endif %}
</div>