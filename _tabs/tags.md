---
layout: tags
icon: fas fa-tags
order: 2
---
<style>
  body {
    background: #0d0d1b;
    color: #e6e6e6;
    font-family: 'Poppins', sans-serif;
  }

  h1 {
    text-align: center;
    color: #FF6F61;
    margin-top: 2rem;
  }

  .tag-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    margin: 2rem auto;
    max-width: 900px;
    gap: 1rem;
  }

  .tag {
    background: linear-gradient(135deg, #1a1a2e, #16213e);
    color: #fff;
    padding: 0.7rem 1.2rem;
    border-radius: 30px;
    font-weight: bold;
    font-size: 1rem;
    box-shadow: 0 4px 10px rgba(0,0,0,0.3);
    transition: transform 0.3s ease, background 0.3s ease;
  }

  .tag:hover {
    transform: translateY(-5px);
    background: linear-gradient(135deg, #FF6F61, #ff9f80);
  }

  .tag a {
    color: #fff;
    text-decoration: none;
  }
</style>

<h1>🏷️ Tags</h1>

<div class="tag-container">
  {% assign tags = site.tags | sort %}
  {% for tag in tags %}
  <div class="tag">
    <a href="{{ site.baseurl }}/tags/{{ tag[0] | slugify }}/">
      {{ tag[0] }} ({{ tag[1].size }})
    </a>
  </div>
  {% endfor %}
</div>
