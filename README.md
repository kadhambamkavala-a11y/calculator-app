<!DOCTYPE html>
<html>
<head>
  <title>Calculator</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #f2f2f2;
      font-family: Arial;
    }
    .calculator {
      background: #222;
      padding: 20px;
      border-radius: 10px;
    }
    input {
      width: 100%;
      height: 50px;
      font-size: 24px;
      margin-bottom: 10px;
      text-align: right;
    }
    button {
      width: 60px;
      height: 60px;
      font-size: 20px;
      margin: 5px;
      cursor: pointer;
    }
  </style>
</head>
<body>

<div class="calculator">
  <input type="text" id="display" disabled>
  <br>
  <button onclick="add('7')">7</button>
  <button onclick="add('8')">8</button>
  <button onclick="add('9')">9</button>
  <button onclick="add('/')">/</button><br>

  <button onclick="add('4')">4</button>
  <button onclick="add('5')">5</button>
  <button onclick="add('6')">6</button>
  <button onclick="add('*')">*</button><br>

  <button onclick="add('1')">1</button>
  <button onclick="add('2')">2</button>
  <button onclick="add('3')">3</button>
  <button onclick="add('-')">-</button><br>

  <button onclick="add('0')">0</button>
  <button onclick="clearDisplay()">C</button>
  <button onclick="calculate()">=</button>
  <button onclick="add('+')">+</button>
</div>

<script>
  function add(value) {
    document.getElementById("display").value += value;
  }
  function clearDisplay() {
    document.getElementById("display").value = "";
  }
  function calculate() {
    document.getElementById("display").value =
      eval(document.getElementById("display").value);
  }
</script>

</body>
</html>

