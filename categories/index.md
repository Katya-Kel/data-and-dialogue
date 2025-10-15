
      layout: categories
      title: "Categories"
      permalink: /categories/



     [Coding](/categories/coding/)  [Physics](/categories/physics/) [Medicine](/categories/medicine/)[Women In STEM](/categories/women-in-stem/)
---
layout: archive
title: "Categories"
permalink: /categories/
---

{{ content }}

<div class="taxonomy__index">
  {% assign categories = site.categories | sort %}
  {% for category in categories %}
    <div class="taxonomy__item">
      <strong>{{ category[0] | capitalize }}</strong>
      <span>{{ category[1].size }}</span>
    </div>
  {% endfor %}
</div>

<style>
.taxonomy__index {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 0.75rem;
  margin-top: 1.5rem;
}

.taxonomy__item {
  background: #f7f7f7;
  border-radius: 12px;
  padding: 0.75rem 1rem;
  text-align: center;
  font-weight: 600;
  box-shadow: 0 1px 3px rgba(0,0,0,0.1);
}

.taxonomy__item strong {
  display: block;
  font-size: 1.1em;
  color: #333;
}

.taxonomy__item span {
  color: #666;
  font-weight: 400;
}
</style>
