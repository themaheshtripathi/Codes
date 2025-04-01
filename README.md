<!DOCTYPE html><html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
            font-family: Arial, sans-serif;
        }
        .calculator {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        .display {
            width: 100%;
            height: 50px;
            font-size: 1.5em;
            text-align: right;
            margin-bottom: 10px;
            padding: 5px;
            border: none;
            background: #e8e8e8;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }
        button {
            padding: 15px;
            font-size: 1.2em;
            border: none;
            cursor: pointer;
            background: #ddd;
            border-radius: 5px;
        }
        button:active {
            background: #bbb;
        }
        .equal {
            grid-column: span 2;
            background: #28a745;
            color: white;
        }
        .clear {
            background: #dc3545;
            color: white;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" class="display" id="display" disabled>
        <div class="buttons">
            <button onclick="clearDisplay()" class="clear">C</button>
            <button onclick="appendValue('/')">/</button>
            <button onclick="appendValue('*')">*</button>
            <button onclick="appendValue('-')">-</button>
            <button onclick="appendValue('7')">7</button>
            <button onclick="appendValue('8')">8</button>
            <button onclick="appendValue('9')">9</button>
            <button onclick="appendValue('+')">+</button>
            <button onclick="appendValue('4')">4</button>
            <button onclick="appendValue('5')">5</button>
            <button onclick="appendValue('6')">6</button>
            <button onclick="calculateResult()" class="equal">=</button>
            <button onclick="appendValue('1')">1</button>
            <button onclick="appendValue('2')">2</button>
            <button onclick="appendValue('3')">3</button>
            <button onclick="appendValue('0')" style="grid-column: span 2;">0</button>
            <button onclick="appendValue('.')">.</button>
        </div>
    </div>
    <script>
        function appendValue(value) {
            document.getElementById("display").value += value;
        }
        function clearDisplay() {
            document.getElementById("display").value = "";
        }
        function calculateResult() {
            try {
                document.getElementById("display").value = eval(document.getElementById("display").value);
            } catch {
                document.getElementById("display").value = "Error";
            }
        }
    </script>
</body>
</html> Codes
