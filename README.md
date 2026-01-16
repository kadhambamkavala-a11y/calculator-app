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
      background: #1c1c1c;
      padding: 20px;
      border-radius: 15px;
      width: 280px;
      box-shadow: 0 10px 20px rgba(0,0,0,0.5);
    }

    #display {
      width: 100%;
      height: 60px;
      font-size: 26px;
      text-align: right;
      margin-bottom: 10px;
      border-radius: 8px;
      border: none;
      padding-right: 10px;
    }

    .row {
      display: flex;
      justify-content: space-between;
      margin-bottom: 5px;
    }

    button {
      width: 60px;
      height: 60px;
      font-size: 20px;
      border: none;
      border-radius: 50%;
      cursor: pointer;
    }

    .num { background: #333; color: white; }
    .op { background: orange; color: white; }
    .clear { background: red; color: white; }
  </style>
</head>
<body>

<div class="calculator">
  <input type="text" id="display" disabled>

  <div class="row">
    <button class="clear" onclick="clearDisplay()">C</button>
    <button class="op" onclick="backspace()">⌫</button>
    <button class="op" onclick="add('%')">%</button>
    <button class="op" onclick="add('/')">÷</button>
  </div>

  <div class="row">
    <button class="num" onclick="add('7')">7</button>
    <button class="num" onclick="add('8')">8</button>
    <button class="num" onclick="add('9')">9</button>
    <button class="op" onclick="add('*')">×</button>
  </div>

  <div class="row">
    <button class="num" onclick="add('4')">4</button>
    <button class="num" onclick="add('5')">5</button>
    <button class="num" onclick="add('6')">6</button>
    <button class="op" onclick="add('-')">−</button>
  </div>

  <div class="row">
    <button class="num" onclick="add('1')">1</button>
    <button class="num" onclick="add('2')">2</button>
    <button class="num" onclick="add('3')">3</button>
    <button class="op" onclick="add('+')">+</button>
  </div>

  <div class="row">
    <button class="num" style="width: 130px;" onclick="add('0')">0</button>
    <button class="num" onclick="add('.')">.</button>
    <button class="op" onclick="calculate()">=</button>
  </div>

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
