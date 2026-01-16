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
      background: #444;
      font-family: 'Arial', sans-serif;
    }

    .calculator {
      background: #000;
      padding: 20px;
      border-radius: 20px;
      width: 320px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.5);
    }

    #display {
      width: 100%;
      height: 70px;
      font-size: 32px;
      text-align: right;
      border-radius: 10px;
      margin-bottom: 15px;
      padding-right: 10px;
      border: none;
      background: #222;
      color: white;
    }

    .row {
      display: flex;
      justify-content: space-between;
      margin-bottom: 8px;
    }

    button {
      width: 70px;
      height: 70px;
      font-size: 22px;
      border-radius: 10px;
      border: none;
      cursor: pointer;
    }

    .num { background: #333; color: #fff; }
    .op { background: orange; color: #fff; }
    .clear { background: red; color: #fff; }

    button:active {
      transform: scale(0.95);
    }
  </style>
</head>
<body>

<div class="calculator">
  <input type="text" id="display" disabled>

  <!-- First Row: C, ⌫, %, ÷ -->
  <div class="row">
    <button class="clear" onclick="clearDisplay()">C</button>
    <button class="op" onclick="backspace()">⌫</button>
    <button class="op" onclick="add('%')">%</button>
    <button class="op" onclick="add('/')">÷</button>
  </div>

  <!-- Second Row: 7 8 9 × -->
  <div class="row">
    <button class="num" onclick="add('7')">7</button>
    <button class="num" onclick="add('8')">8</button>
    <button class="num" onclick="add('9')">9</button>
    <button class="op" onclick="add('*')">×</button>
  </div>

  <!-- Third Row: 4 5 6 − -->
  <div class="row">
    <button class="num" onclick="add('4')">4</button>
    <button class="num" onclick="add('5')">5</button>
    <button class="num" onclick="add('6')">6</button>
    <button class="op" onclick="add('-')">−</button>
  </div>

  <!-- Fourth Row: 1 2 3 + -->
  <div class="row">
    <button class="num" onclick="add('1')">1</button>
    <button class="num" onclick="add('2')">2</button>
    <button class="num" onclick="add('3')">3</button>
    <button class="op" onclick="add('+')">+</button>
  </div>

  <!-- Fifth Row: 0 . = -->
  <div class="row">
    <button class="num" style="width: 150px;" onclick="add('0')">0</button>
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
