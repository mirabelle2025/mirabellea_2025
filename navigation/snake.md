---
layout: page
title: Snake
permalink: /snake/
---

{% include nav/home.html %}

<style>
/* Same existing styles */
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
  margin-bottom: 10px;
}

.button-container {
  text-align: center;
}

.button-container button {
  padding: 10px 20px;
  margin: 5px;
  background-color: #FFC0CB;
  color: pink;
  border: pink;
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
    <!-- New Restart Game button -->
    <button id="restart-btn">Restart Game</button>
  </div>
</div>

<script>
const canvas = document.getElementById("gameCanvas");
const ctx = canvas.getContext("2d");

const box = 20;
let snake, food, direction, score, speed, wallOn, game;

function initGame() {
  // Reset game variables
  snake = [{ x: 9 * box, y: 10 * box }];
  food = {
    x: Math.floor(Math.random() * 19 + 1) * box,
    y: Math.floor(Math.random() * 19 + 1) * box
  };
  direction = null;
  score = 0;
  speed = 100;
  wallOn = true;
  document.getElementById("game-over").style.display = "none";

  // Restart game loop
  if (game) clearInterval(game);
  game = setInterval(draw, speed);
}

document.addEventListener("keydown", changeDirection);

function changeDirection(event) {
  if (event.keyCode == 37 && direction != "RIGHT") {
    direction = "LEFT";
  } else if (event.keyCode == 38 && direction != "DOWN") {
    direction = "UP";
  } else if (event.keyCode == 39 && direction != "LEFT") {
    direction = "RIGHT";
  } else if (event.keyCode == 40 && direction != "UP") {
    direction = "DOWN";
  }
}

function collision(head, array) {
  for (let i = 0; i < array.length; i++) {
    if (head.x == array[i].x && head.y == array[i].y) {
      return true;
    }
  }
  return false;
}

function draw() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);

  // Draw snake
  for (let i = 0; i < snake.length; i++) {
    ctx.font = "20px Arial";
    ctx.fillText("🩷", snake[i].x, snake[i].y + box);
  }

  // Draw food
  ctx.fillStyle = "white";
  ctx.fillRect(food.x, food.y, box, box);

  let snakeX = snake[0].x;
  let snakeY = snake[0].y;

  if (direction == "LEFT") snakeX -= box;
  if (direction == "UP") snakeY -= box;
  if (direction == "RIGHT") snakeX += box;
  if (direction == "DOWN") snakeY += box;

  if (snakeX == food.x && snakeY == food.y) {
    score++;
    food = {
      x: Math.floor(Math.random() * 19 + 1) * box,
      y: Math.floor(Math.random() * 19 + 1) * box
    };
  } else {
    snake.pop();
  }

  let newHead = { x: snakeX, y: snakeY };

  if (wallOn) {
    if (snakeX < 0 || snakeY < 0 || snakeX >= canvas.width || snakeY >= canvas.height || collision(newHead, snake)) {
      document.getElementById("game-over").style.display = "block";
      clearInterval(game);
    }
  } else {
    if (snakeX < 0) snakeX = canvas.width - box;
    if (snakeX >= canvas.width) snakeX = 0;
    if (snakeY < 0) snakeY = canvas.height - box;
    if (snakeY >= canvas.height) snakeY = 0;
  }

  snake.unshift(newHead);

  ctx.fillStyle = "black";
  ctx.font = "20px Arial";
  ctx.fillText("Score: " + score, 10, 30);
}

document.getElementById("slow-btn").addEventListener("click", function() {
  clearInterval(game);
  speed = 200;
  game = setInterval(draw, speed);
});

document.getElementById("fast-btn").addEventListener("click", function() {
  clearInterval(game);
  speed = 50;
  game = setInterval(draw, speed);
});

document.getElementById("wall-btn").addEventListener("click", function() {
  wallOn = !wallOn;
});

const themes = ['light-theme', 'dark-theme', 'blue-theme', 'red-theme', 'green-theme', 'grey-theme'];
let currentTheme = 0;

document.getElementById("theme-btn").addEventListener("click", function() {
  document.body.classList.remove(themes[currentTheme]);
  currentTheme = (currentTheme + 1) % themes.length;
  document.body.classList.add(themes[currentTheme]);
});

// Restart button functionality
document.getElementById("restart-btn").addEventListener("click", initGame);

// Start the game for the first time
initGame();
</script>
