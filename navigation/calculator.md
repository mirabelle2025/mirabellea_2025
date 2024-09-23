---
layout: page
title: Calculator
permalink: /calculator/
---

{% include nav/home.html %}

<h2>Calculator</h2>

<div class="calculator">
  <input type="text" id="display" disabled />
  
  <div class="row">
    <button onclick="clearDisplay()">C</button>
    <button onclick="updateDisplay('7')">7</button>
    <button onclick="updateDisplay('8')">8</button>
    <button onclick="updateDisplay('9')">9</button>
    <button onclick="updateDisplay('/')">/</button>
  </div>

  <div class="row">
    <button onclick="updateDisplay('4')">4</button>
    <button onclick="updateDisplay('5')">5</button>
    <button onclick="updateDisplay('6')">6</button>
    <button onclick="updateDisplay('*')">*</button>
  </div>

  <div class="row">
    <button onclick="updateDisplay('1')">1</button>
    <button onclick="updateDisplay('2')">2</button>
    <button onclick="updateDisplay('3')">3</button>
    <button onclick="updateDisplay('-')">-</button>
  </div>

  <div class="row">
    <button onclick="updateDisplay('0')">0</button>
    <button onclick="updateDisplay('.')">.</button>
    <button onclick="calculate()">=</button>
    <button onclick="updateDisplay('+')">+</button>
  </div>
  
  <!-- Advanced functions -->
  <div class="row">
    <button onclick="log()">log</button>
    <button onclick="ln()">ln</button>
    <button onclick="sqrt()">√</button>
    <button onclick="pow()">x²</button>
  </div>
</div>

<style>
  .calculator {
    width: 200px;
    margin: 20px auto;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 10px;
    background-color: #FFC0CB;
  }

  #display {
    width: 100%;
    height: 40px;
    font-size: 1.2em;
    margin-bottom: 10px;
    text-align: right;
    border-radius: 5px;
    border: 1px solid #ddd;
  }

  .row {
    display: flex;
    justify-content: space-between;
    margin-bottom: 5px;
  }

  button {
    width: 45px;
    height: 45px;
    font-size: 1.2em;
    margin: 2px;
    border: none;
    background-color: #ddd;
    border-radius: 5px;
    cursor: pointer;
  }

  button:hover {
    background-color: #ccc;
  }

  button:active {
    background-color: #bbb;
  }
</style>

<script>
  function updateDisplay(value) {
    document.getElementById('display').value += value;
  }

  function clearDisplay() {
    document.getElementById('display').value = '';
  }

  function calculate() {
    try {
      let result = eval(document.getElementById('display').value);
      document.getElementById('display').value = result;
    } catch (e) {
      document.getElementById('display').value = 'Error';
    }
  }

  // Logarithm (base 10)
  function log() {
    let value = parseFloat(document.getElementById('display').value);
    document.getElementById('display').value = Math.log10(value);
  }

  // Natural logarithm
  function ln() {
    let value = parseFloat(document.getElementById('display').value);
    document.getElementById('display').value = Math.log(value);
  }

  // Square root
  function sqrt() {
    let value = parseFloat(document.getElementById('display').value);
    document.getElementById('display').value = Math.sqrt(value);
  }

  // Square (x²)
  function pow() {
    let value = parseFloat(document.getElementById('display').value);
    document.getElementById('display').value = Math.pow(value, 2);
  }
</script>
