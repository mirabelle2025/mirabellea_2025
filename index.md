---
layout: base
title: Student Home
description: Home Page
author: Mirabelle Anderson
hide: true
---

{% include nav/home.html %}

<iframe style="border-radius:12px" src="https://open.spotify.com/embed/playlist/0VcUuytc79fAR2M93AtfGL?utm_source=generator" width="100%" height="352" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>

<button id="theme-toggle" onclick="toggleTheme()">Switch Theme</button>

<script>
  // Function to toggle the theme
  function toggleTheme() {
    let body = document.body;
    let currentTheme = body.dataset.theme;
    
    if (currentTheme === "dark") {
      body.dataset.theme = "light";
      localStorage.setItem("theme", "light");
    } else {
      body.dataset.theme = "dark";
      localStorage.setItem("theme", "dark");
    }
    applyTheme();
  }

  // Apply the saved theme from localStorage
  function applyTheme() {
    let savedTheme = localStorage.getItem("theme") || "light";
    document.body.dataset.theme = savedTheme;
  }

  // Run theme initialization on page load
  document.addEventListener("DOMContentLoaded", applyTheme);
</script>

<style>
  body[data-theme='dark'] {
    background-color: #2e2e2e;
    color: #ffffff;
  }
  body[data-theme='light'] {
    background-color: #ffffff;
    color: #000000;
  }
    body[data-theme='blue'] {
    background-color: #AEC6CF;
    color: white;
  }
</style>
