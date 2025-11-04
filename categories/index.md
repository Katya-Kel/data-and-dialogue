---
layout: default
title: Categories
permalink: /categories/
---

<div style="max-width: 800px; margin: 0 auto; padding: 20px;">
  
  <header style="text-align: center; margin-bottom: 40px;">
    <h1 style="font-size: 2.5rem; margin-bottom: 10px;">Categories</h1>
  </header>

  <!-- Get all categories -->
  {% assign categories = site.categories | sort %}
  
  {% for category in categories %}
    {% assign category_name = category[0] %}
    {% assign category_posts = category[1] %}
    
  <div class="category-group" style="margin-bottom: 50px;">
      <h2 style="
        font-size: 1.8rem; 
        color: #e91e63; 
        border-bottom: 2px solid #e91e63; 
        padding-bottom: 10px;
        margin-bottom: 25px;
      ">
        {{ category_name }} ({{ category_posts.size }})
      </h2>
    <!-- Posts in this category -->
      {% for post in category_posts %}
        <div class="post-card" style="
          background: white;
          border-radius: 8px;
          padding: 25px;
          margin-bottom: 25px;
          box-shadow: 0 2px 10px rgba(0,0,0,0.1);
          border-left: 4px solid #e91e63;
        ">
          <h3 style="margin-top: 0; margin-bottom: 10px;">
            <a href="{{ post.url }}" style="text-decoration: none; color: #333; font-size: 1.3rem;">
              {{ post.title }}
            </a>
          </h3>
          
  <div style="color: #666; font-size: 0.9rem; margin-bottom: 15px;">
            {% assign words = post.content | number_of_words %}
            {% assign read_time = words | divided_by: 180 | at_least: 1 %}
            <span>{{ read_time }} min read</span>
            • 
            <span>{{ post.date | date: "%B %d, %Y" }}</span>
          </div>
          
   {% if post.excerpt %}
            <p style="color: #555; line-height: 1.6; margin-bottom: 0;">
              {{ post.excerpt | strip_html | truncatewords: 25 }}
            </p>
          {% endif %}
          
   <a href="{{ post.url }}" style="
            display: inline-block;
            margin-top: 15px;
            color: #e91e63;
            text-decoration: none;
            font-weight: 500;
          ">Read more →</a>
        </div>
      {% endfor %}
    </div>
  {% endfor %}

</div>
