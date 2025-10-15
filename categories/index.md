---
layout: default
title: "Categories"
permalink: /categories/
---

<h1 style="font-weight:700;">Categories</h1>

{% assign sorted_categories = site.categories | sort %}
{% for category in sorted_categories %}
  <div class="category-section">
    <h2 class="category-title">{{ category[0] | capitalize }} <span class="category-count">({{ category[1].size }})</span></h2>
    <ul class="post-list">
      {% for post in category[1] %}
        <li>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span>
        </li>
      {% endfor %}
    </ul>
  </div>
{% endfor %}

<style>
.category-section {
  margin-bottom: 2.5rem;
  border-bottom: 1px solid #ddd;
  padding-bottom: 1.5rem;
}

.category-title {
  font-size: 1.5em;
  font-weight: 700;
  color: #222;
  margin-bottom: 0.5rem;
}

.category-count {
  color: #888;
  font-size: 0.9em;
}

.post-list {
  list-style: none;
  padding-left: 0;
  margin-top: 0.5rem;
}

.post-list li {
  margin-bottom: 0.4rem;
}

.post-list a {
  color: #006d77;
  font-weight: 500;
  text-decoration: none;
}

.post-list a:hover {
  text-decoration: underline;
}

.post-date {
  font-size: 0.8em;
  color: #888;
  margin-left: 0.5rem;
}
</style>
