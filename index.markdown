---
layout: home
---

<style>
    .td-none {
        text-decoration: none !important;
    }

    .tep {
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
    }

    .posts-listing {
        display: flex;
        flex-direction: column; 
    }


    .post-date {
        font-size: 0.85rem;
        color: #999;
        margin-bottom: 6px;
    }
    
</style>

<div class="home-container">
  <div class="section-header">
    <h2 class="section-title">Recents</h2>
  </div>
  {% assign latest_post = site.blogs | sort: 'date' | reverse %}
   <div style="posts-listing">
   {% for post in latest_post limit: 10 %}
      <div style="margin-top: 0.4rem">
        <a href="{{ post.url }}" class="td-none">
          <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span>
          <span style="margin-left: 0.4rem">{{ post.title }}</span>
        </a>
      </div>
    {% endfor %}


  <!-- Recent Journal Posts -->
  {% assign journal_entries = site.blogs | where_exp: "post", "post.url contains 'journal'" | sort: 'date' | reverse %}
  {% if journal_entries.size > 0 %}
  <div style="margin-top: 1.2rem">
    <h2>Journals</h2>
  </div>
  <div>
    {% for post in journal_entries limit: 10 %}
      <div style="margin-top: 0.4rem">
        <a href="{{ post.url }}" class="td-none">
          <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span>
          <span style="margin-left: 0.4rem">{{ post.title }}</span>
        </a>
      </div>
    {% endfor %}
  </div>
  {% endif %}
  <div>
</div>