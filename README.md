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
      background: #111;
      padding: 20px;
      border-radius: 15px;
      width: 260px;
      box-shadow: 0 10px 20px rgba(0,0,0,0.5);
    }
    input {
      width: 100%;
      height: 60px;
      font-size: 26px;
      text-align: right;
      margin-bottom: 10px;
      padding-right: 10px;
      border-radius: 8px;
      border: none;
    }
    button {
      width: 55px;
      height: 55px;
      margin: 5px;
      font-size: 18px;
      border-radius: 50%;
      cursor: pointer;
      border: none;
    }
    .num { background: #333; color: #fff; }
    .op { background: orange; color: #fff; }
    .clear { background: red; color: #fff; }
  </style>
</head>
<body>

<div class="calculator">
  <input type="text" id="display" disabled>

  <!-- First Row -->
  <button class="clear" onclick="clearDisplay()">C</button>
  <button class="op" onclick="backspace()">⌫</button>
  <button class="op" onclick="add('%')">%</button>
  <button class="op" onclick="add('/')">÷</button><br>

  <!-- Second Row -->
  <button class="num" onclick="add('7')">7</button>
  <button class="num" onclick="add('8')">8</button>
  <button class="num" onclick="add('9')">9</button>
  <button class="op" onclick="add('*')">×</button><br>

  <!-- Third Row -->
  <button class="num" onclick="add('4')">4</button>
  <button class="num" onclick="add('5')">5</button>
  <button class="num" onclick="add('6')">6</button>
  <button class="op" onclick="add('-')">−</button><br>

  <!-- Fourth Row -->
  <button class="num" onclick="add('1')">1</button>
  <button class="num" onclick="add('2')">2</button>
  <button class="num" onclick="add('3')">3</button>
  <button class="op" onclick="add('+')">+</button><br>

  <!-- Fifth Row -->
  <button class="num" onclick="add('0')">0</button>
  <button class="num" onclick="add('.')">.</button>
  <button class="op" onclick="calculate()">=</button>
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
