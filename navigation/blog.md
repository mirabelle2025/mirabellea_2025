---
layout: blogs 
title: Blogs
search_exclude: true
permalink: /blogs/
---

<input type="text" id="searchInput" placeholder="Search blog posts..." style="width: 100%; padding: 0.5em; margin: 1em 0;">
<ul id="searchResults"></ul>

<script>
  const posts = [
    { title: "Math Notebook", url: "/notebooks/math", tags: "calculus algebra" },
    { title: "AI & ML", url: "/notebooks/ai", tags: "machine learning python" },
    { title: "Science Stuff", url: "/notebooks/science", tags: "physics chemistry" },
    // Add more here!
  ];

  const input = document.getElementById("searchInput");
  const results = document.getElementById("searchResults");

  input.addEventListener("input", function() {
    const query = this.value.toLowerCase();
    results.innerHTML = '';
    posts.forEach(post => {
      if (post.title.toLowerCase().includes(query) || post.tags.toLowerCase().includes(query)) {
        const li = document.createElement('li');
        li.innerHTML = `<a href="${post.url}">${post.title}</a>`;
        results.appendChild(li);
      }
    });
  });
</script>
