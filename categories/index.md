---
layout: none
title: "Categories"
permalink: /categories/
---

<h1 style="font-weight:700;">Categories</h1>

<div class="category-container">
  {% assign sorted_categories = site.categories | sort %}
  {% for category in sorted_categories %}
    <div class="category-box">
      <span class="category-name">{{ category[0] | capitalize }}</span>
      <span class="category-count">{{ category[1].size }}</span>
    </div>
  {% endfor %}
</div>

<style>
.category-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
  gap: 1rem;
  margin-top: 2rem;
}

.category-box {
  background-color: #f7f7f7;
  border-radius: 10px;
  padding: 0.75rem 1rem;
  text-align: center;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.category-name {
  display: block;
  font-weight: 600;
  font-size: 1.05em;
  color: #333;
}

.category-count {
  color: #777;
  font-size: 0.9em;
}
</style>
