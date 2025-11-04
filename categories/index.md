---
layout: default
---

<div style="max-width: 800px; margin: 0 auto; padding: 20px;">

  <header style="text-align: center; margin-bottom: 40px;">
    <h1 style="font-size: 2.5rem; margin-bottom: 10px;">Category: {{ page.title }}</h1>
    <p style="font-size: 1.2rem; color: #666;">{{ page.posts.size }} posts</p>
  </header>

  <div class="posts-list">
    {% for post in page.posts %}
      <article class="post-card" style="
        background: white;
        border-radius: 8px;
        padding: 25px;
        margin-bottom: 25px;
        box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        border-left: 4px solid #e91e63;
      ">
        <h3 style="margin-top: 0; margin-bottom: 10px;">
          <a href="{{ post.url | relative_url }}" style="text-decoration: none; color: #333;">
            {{ post.title }}
          </a>
        </h3>
        
  <div class="post-meta" style="color: #666; font-size: 0.9rem; margin-bottom: 15px;">
          {% assign words = post.content | number_of_words %}
          {% if words < 360 %}
            {% assign read_time = '1 min read' %}
          {% else %}
            {% assign read_time = words | divided_by: 180 | append: ' min read' %}
          {% endif %}
          <span class="read-time">{{ read_time }}</span>
          • 
          <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span>
        </div>
        
  {% if post.excerpt %}
          <p class="post-excerpt" style="color: #555; line-height: 1.6; margin-bottom: 0;">
            {{ post.excerpt | strip_html | truncatewords: 30 }}
          </p>
        {% endif %}
        
  <a href="{{ post.url | relative_url }}" class="read-more" style="
          display: inline-block;
          margin-top: 15px;
          color: #e91e63;
          text-decoration: none;
          font-weight: 500;
        ">Read more →</a>
      </article>
    {% endfor %}
  </div>

</div>
