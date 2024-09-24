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

canvas {
  border: 1px solid #000;
  background-color: pink;
  margin-bottom: 10px; /* Add spacing between canvas and buttons */
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

#game-over {
  font-size: 2em;
  color: pink;
  text-align: center;
  display: none;
}
</style>

<h1 id="game-over">Game Over!</h1>

<div class="container">
  <canvas id="gameCanvas" width="400" height="400"></canvas>

  <!-- Buttons for controlling the game -->
  <div class="button-container">
    <button id="slow-btn">Slow Mode</button>
    <button id="fast-btn">Fast Mode</button>
    <button id="wall-btn">Wall On/Off</button>
    <button id="theme-btn">Switch Theme</button>
  </div>
</div>