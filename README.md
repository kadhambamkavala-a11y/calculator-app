<!DOCTYPE html>
<html>
<head>
  <title>Calculator</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #222;
      font-family: Arial, sans-serif;
    }
    .calculator {
      background: #000;
      padding: 20px;
      border-radius: 15px;
      width: 260px;
    }
    input {
      width: 100%;
      height: 60px;
      font-size: 26px;
      text-align: right;
      margin-bottom: 10px;
      padding-right: 10px;
    }
    button {
      width: 55px;
      height: 55px;
      margin: 5px;
      font-size: 18px;
      border-radius: 50%;
      cursor: pointer;
    }
  </style>
</head>
<body>

<div class="calculator">
  <input type="text" id="display" disabled>

  <button onclick="clearDisplay()">C</button>
  <button onclick="backspace()">⌫</button>
  <button onclick="add('%')">%</button>
  <button onclick="add('/')">÷</button><br>

  <button onclick="add('7')">7</button>
  <button onclick="add('8')">8</button>
  <button onclick="add('9')">9</button>
  <button onclick="add('*')">×</button><br>

  <button onclick="add('4')">4</button>
  <button onclick="add('5')">5</button>
  <button onclick="add('6')">6</button>
  <button onclick="add('-')">−</button><br>

  <button onclick="add('1')">1</button>
  <button onclick="add('2')">2</button>
  <button onclick="add('3')">3</button>
  <button onclick="add('+')">+</button><br>

  <button onclick="add('0')">0</button>
  <button onclick="add('.')">.</button>
  <button onclick="calculate()">=</button>
</div>

<script>
  const display = document.getElementById("display");

  function add(value) {
    display.value += value;
  }

  function clearDisplay() {
    display.value = "";
  }

  function backspace() {
    display.value = display.value.slice(0, -1);
  }

  function calculate() {
    try {
      display.value = eval(display.value);
    } catch {
      display.value = "Error";
    }
  }
</script>

</body>
</html>
