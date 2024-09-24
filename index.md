---
layout: base
title: Student Home
description: Home Page
author: Mirabelle Anderson
hide: true
---

{% include nav/home.html %}

<style>
body.light-theme {
  background-color: white;
  color: black;
}

body.dark-theme {
  background-color: #333;
  color: white;
}

body.blue-theme {
  background-color: #AEC6CF;
  color: white;
}

body.red-theme {
  background-color: #FDFD96;
  color: white;
}

body.green-theme {
  background-color: #C3B1E1;
  color: white;
}

body.grey-theme {
  background-color: #aaa;
  color: white;
}

/* Center the canvas and buttons */
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

/* Adjust the button-container */
.button-container {
  text-align: center;
}

.button-container button {
  padding: 10px 20px;
  margin: 5px;
  background-color: #FF1493;
  color: pink;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.button-container button:hover {
  background-color: #FFC0CB;
}

</style>

<div class="container">
  <!-- Buttons for controlling the game -->
  <div class="button-container">
    <button id="theme-btn">Switch Theme</button>
  </div>
</div>