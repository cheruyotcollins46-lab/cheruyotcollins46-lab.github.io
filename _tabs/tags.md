---
title: "Tags"
layout: default
icon: fas fa-tags
order : 2
---
<div class="tags-page">
  <h1 class="page-title">🏷️ Tags</h1>
  <p class="page-description">
    Explore topics across Data Science, Machine Learning, AI, Deep Learning, and more.
  </p>

  <div class="search-container">
    <input type="text" id="tagSearch" class="search-input" placeholder="🔍 Search tags..." onkeyup="filterTags()">
  </div>

  <ul id="tagList" class="tag-list">
    <li><a href="#">🤖 Artificial Intelligence</a></li>
    <li><a href="#">📊 Data Science</a></li>
    <li><a href="#">🧠 Deep Learning</a></li>
    <li><a href="#">⚙️ Machine Learning</a></li>
    <li><a href="#">📈 Statistics</a></li>
  </ul>
</div>

<style>
.tags-page {
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem 1rem;
  color: #ddd;
  font-family: "Poppins", sans-serif;
}
.page-title {
  font-size: 2.3rem;
  color: #ff6f61;
  font-weight: 700;
  margin-bottom: 0.5rem;
}
.page-description {
  font-size: 1.1rem;
  color: #bbb;
  margin-bottom: 2rem;
}
.search-container {
  margin-bottom: 1.5rem;
}
.search-input {
  padding: 10px 14px;
  width: 70%;
  max-width: 400px;
  border-radius: 30px;
  border: 1px solid #444;
  background-color: #1e1e2f;
  color: #fff;
  outline: none;
  font-size: 1rem;
  transition: 0.3s ease;
}
.search-input:focus {
  border-color: #ff6f61;
  box-shadow: 0 0 8px #ff6f61;
}
.tag-list {
  list-style: none;
  padding: 0;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1rem;
  justify-content: center;
}
.tag-list li {
  background: linear-gradient(135deg, #29293f, #1f1f35);
  padding: 12px 18px;
  border-radius: 12px;
  transition: transform 0.2s, background 0.3s;
}
.tag-list li:hover {
  transform: translateY(-4px);
  background: linear-gradient(135deg, #ff6f61, #ff9068);
}
.tag-list a {
  color: #fff;
  text-decoration: none;
  font-weight: 600;
}
</style>

<script>
function filterTags() {
  const input = document.getElementById("tagSearch").value.toLowerCase();
  const tags = document.querySelectorAll("#tagList li");
  tags.forEach(tag => {
    const text = tag.textContent.toLowerCase();
    tag.style.display = text.includes(input) ? "block" : "none";
  });
}
</script>

