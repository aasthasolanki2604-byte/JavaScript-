<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple Calculator</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #f0f0f0;
      font-family: Arial, sans-serif;
    }
    .calculator {
      background: #fff;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
    }
    .display {
      width: 100%;
      height: 40px;
      font-size: 1.5em;
      text-align: right;
      padding: 5px;
      margin-bottom: 10px;
      border: 1px solid #ccc;
      border-radius: 6px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 60px);
      gap: 10px;
    }
    button {
      padding: 15px;
      font-size: 1.2em;
      border: none;
      border-radius: 6px;
      background: #e0e0e0;
      cursor: pointer;
    }
    button.operator {
      background: #f9a825;
      color: white;
    }
    button.equal {
      background: #43a047;
      color: white;
      grid-column: span 2;
    }
    button.clear {
      background: #e53935;
      color: white;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" class="display" readonly>
    <div class="buttons">
      <button onclick="append('7')">7</button>
      <button onclick="append('8')">8</button>
      <button onclick="append('9')">9</button>
      <button class="operator" onclick="append('/')">/</button>

      <button onclick="append('4')">4</button>
      <button onclick="append('5')">5</button>
      <button onclick="append('6')">6</button>
      <button class="operator" onclick="append('*')">*</button>

      <button onclick="append('1')">1</button>
      <button onclick="append('2')">2</button>
      <button onclick="append('3')">3</button>
      <button class="operator" onclick="append('-')">-</button>

      <button onclick="append('0')">0</button>
      <button onclick="append('.')">.</button>
      <button class="equal" onclick="calculate()">=</button>
      <button class="operator" onclick="append('+')">+</button>

      <button class="clear" onclick="clearDisplay()">C</button>
    </div>
  </div>

  <script>
    const display = document.getElementById('display');

    function append(value) {
      display.value += value;
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch {
        display.value = 'Error';
      }
    }

    function clearDisplay() {
      display.value = '';
    }
  </script>
</body>
</html>
