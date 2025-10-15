---
layout: page
title: Tags
icon: fas fa-tags
order: 2
---

<div class="tags-page">
  <h1 class="page-title">🏷️ Tags</h1>

  <input type="text" id="tagSearch" placeholder="🔍 Search tags..." class="tag-search"/>

  <ul class="tag-list">
    {% assign tags_list = site.tags | sort %}
    {% for tag in tags_list %}
      <li class="tag-item">
        <a href="{{ site.baseurl }}/tags/{{ tag[0] | slugify }}/" class="tag-link">
          {{ tag[0] | capitalize }}
        </a>
        <span class="tag-count">({{ tag[1].size }})</span>
      </li>
    {% endfor %}
  </ul>
</div>

<script>
  // Tag search functionality
  document.addEventListener('DOMContentLoaded', () => {
    const input = document.getElementById('tagSearch');
    input.addEventListener('keyup', () => {
      const filter = input.value.toLowerCase();
      document.querySelectorAll('.tag-item').forEach(item => {
        const text = item.textContent.toLowerCase();
        item.style.display = text.includes(filter) ? '' : 'none';
      });
    });
  });
</script>

<style>
.tags-page {
  max-width: 700px;
  margin: 2rem auto;
  text-align: center;
}
.page-title {
  color: #ff6f61;
  font-weight: 700;
  margin-bottom: 1rem;
}
.tag-search {
  width: 100%;
  padding: 0.5rem;
  margin-bottom: 1.5rem;
  border-radius: 8px;
  border: 1px solid #555;
  background-color: #111;
  color: #fff;
}
.tag-list {
  list-style: none;
  padding: 0;
}
.tag-item {
  margin: 0.5rem 0;
  font-size: 1.05rem;
}
.tag-link {
  color: #ff9966;
  text-decoration: none;
  font-weight: 600;
}
.tag-link:hover {
  text-decoration: underline;
}
.tag-count {
  color: #ccc;
  margin-left: 0.5rem;
}
</style>
