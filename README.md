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
      background: linear-gradient(135deg, #667eea, #764ba2);
      font-family: Arial, sans-serif;
    }

    .calculator {
      background: #1c1c1c;
      padding: 20px;
      border-radius: 20px;
      width: 260px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.4);
    }

    input {
      width: 100%;
      height: 60px;
      font-size: 26px;
      text-align: right;
      border: none;
      border-radius: 10px;
      margin-bottom: 15px;
      padding-right: 10px;
    }

    button {
      width: 55px;
      height: 55px;
      margin: 5px;
      font-size: 20px;
      border: none;
      border-radius: 50%;
      cursor: pointer;
    }

    .num { background: #333; color: white; }
    .op { background: orange; color: white; }
    .clear { background: red; color: white; }

    button:hover {
      opacity: 0.8;
    }
  </style>
</head>
<body>

<div class="calculator">
  <input id="display" disabled>

  <button class="clear" onclick="clearDisplay()">C</button>
  <button class="op" onclick="back()">⌫</button>
  <button class="op" onclick="add('%')">%</button>
  <button class="op" onclick="add('/')">÷</button><br>

  <button class="num" onclick="add('7')">7</button>
  <button class="num" onclick="add('8')">8</button>
  <button class="num" onclick="add('9')">9</button>
  <button class="op" onclick="add('*')">×</button><br>

  <button class="num" onclick="add('4')">4</button>
  <button class="num" onclick="add('5')">5</button>
  <button class="num" onclick="add('6')">6</button>
  <button class="op" onclick="add('-')">−</button><br>

  <button class="num" onclick="add('1')">1</button>
  <button class="num" onclick="add('2')">2</button>
  <button class="num" onclick="add('3')">3</button>
  <button class="op" onclick="add('+')">+</button><br>

  <button class="num" onclick="add('0')">0</button>
  <button class="num" onclick="add('.')">.</button>
  <button class="op" onclick="calculate()">=</button>
</div>

<script>
  function add(v) {
    display.value += v;
  }
  function clearDisplay() {
    display.value = "";
  }
  function back() {
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
