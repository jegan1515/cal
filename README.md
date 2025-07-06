
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f0f0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .calculator {
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
      width: 300px;
    }

    #display {
      width: 100%;
      height: 50px;
      font-size: 24px;
      text-align: right;
      padding: 10px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
      border-radius: 5px;
      box-sizing: border-box;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }

    .buttons button {
      padding: 20px;
      font-size: 18px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      background-color: #e0e0e0;
      transition: background 0.3s;
    }

    .buttons button:hover {
      background-color: #ccc;
    }

    .operator {
      background-color: #f9c74f;
    }

    .equal {
      background-color: #90be6d;
      grid-column: span 2;
    }

    .clear {
      background-color: #f94144;
      color: white;
    }
  </style>
</head>
<body>

  <div class="calculator">
    <input type="text" id="display" disabled />
    <div class="buttons">
      <button onclick="clearDisplay()" class="clear">C</button>
      <button onclick="appendValue('(')">(</button>
      <button onclick="appendValue(')')">)</button>
      <button onclick="appendValue('/')" class="operator">÷</button>

      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('*')" class="operator">×</button>

      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="appendValue('-')" class="operator">−</button>

      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="appendValue('+')" class="operator">+</button>

      <button onclick="appendValue('0')">0</button>
      <button onclick="appendValue('.')">.</button>
      <button onclick="calculate()" class="equal">=</button>
    </div>
  </div>

  <script>
    function appendValue(value) {
      document.getElementById('display').value += value;
    }

    function clearDisplay() {
      document.getElementById('display').value = '';
    }

    function calculate() {
      try {
        const result = eval(document.getElementById('display').value);
        document.getElementById('display').value = result;
      } catch {
        document.getElementById('display').value = 'Error';
      }
    }
  </script>

</body>
</html>
