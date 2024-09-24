---
layout: base
title: Student Home
description: Home Page
author: Mirabelle Anderson
hide: true
---

{% include nav/home.html %}

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
</style>
