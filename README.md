# LEVEL-1-TASK-3-CALCULATOR
A simple calculator web app built with HTML, CSS, and JavaScript. It features a user-friendly interface with buttons for basic arithmetic operations, a display screen for input and results, and a responsive layout using CSS Grid.



<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Basic Calculator</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    body { background: #f4f4f4; font-family: Arial, sans-serif; display: flex; justify-content: center; align-items: center; height: 100vh; }
    .calculator { background: #fff; padding: 2rem; border-radius: 10px; box-shadow: 0 0 10px #ccc; }
    .display { width: 100%; height: 40px; font-size: 1.5rem; margin-bottom: 1rem; text-align: right; padding: 0.5rem; border: 1px solid #ddd; border-radius: 5px; }
    .buttons { display: grid; grid-template-columns: repeat(4, 60px); grid-gap: 10px; }
    button { padding: 1rem; font-size: 1.2rem; border: none; border-radius: 5px; background: #e0e0e0; cursor: pointer; transition: background 0.2s; }
    button.operator { background: #1a73e8; color: #fff; }
    button.equal { background: #43a047; color: #fff; grid-column: span 2; }
    button.clear { background: #e53935; color: #fff; }
    button:active { background: #bdbdbd; }
    @media (max-width: 500px) {
      .calculator { padding: 1rem; }
      .buttons { grid-template-columns: repeat(4, 45px); }
      button { font-size: 1rem; padding: 0.7rem; }
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" class="display" id="display" disabled>
    <div class="buttons">
      <button onclick="append('7')">7</button>
      <button onclick="append('8')">8</button>
      <button onclick="append('9')">9</button>
      <button class="operator" onclick="append('/')">÷</button>
      <button onclick="append('4')">4</button>
      <button onclick="append('5')">5</button>
      <button onclick="append('6')">6</button>
      <button class="operator" onclick="append('*')">×</button>
      <button onclick="append('1')">1</button>
      <button onclick="append('2')">2</button>
      <button onclick="append('3')">3</button>
      <button class="operator" onclick="append('-')">−</button>
      <button onclick="append('0')">0</button>
      <button onclick="append('.')">.</button>
      <button class="clear" onclick="clearDisplay()">C</button>
      <button class="operator" onclick="append('+')">+</button>
      <button class="equal" onclick="calculate()">=</button>
    </div>
  </div>
  <script>
    let display = document.getElementById('display');
    function append(char) {
      display.value += char;
    }
    function clearDisplay() {
      display.value = '';
    }
    function calculate() {
      try {
        display.value = eval(display.value.replace(/÷/g, '/').replace(/×/g, '*'));
      } catch {
        display.value = 'Error';
      }
    }
  </script>
</body>
</html>
