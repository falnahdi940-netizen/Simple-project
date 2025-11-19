<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator - Faisel Alnahdi</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .calculator {
            background-color: #fff;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }
        input[type="text"] {
            width: 100%;
            height: 50px;
            text-align: right;
            font-size: 24px;
            margin-bottom: 10px;
            border-radius: 10px;
            border: 1px solid #ccc;
            padding: 5px;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 60px);
            gap: 10px;
        }
        button {
            height: 60px;
            font-size: 18px;
            border-radius: 10px;
            border: none;
            background-color: #007BFF;
            color: white;
            cursor: pointer;
            transition: 0.2s;
        }
        button:hover {
            background-color: #0056b3;
        }
        .author {
            text-align: center;
            margin-top: 10px;
            font-weight: bold;
            color: #555;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" disabled>
        <div class="buttons">
            <button onclick="appendValue('7')">7</button>
            <button onclick="appendValue('8')">8</button>
            <button onclick="appendValue('9')">9</button>
            <button onclick="appendValue('/')">/</button>

            <button onclick="appendValue('4')">4</button>
            <button onclick="appendValue('5')">5</button>
            <button onclick="appendValue('6')">6</button>
            <button onclick="appendValue('*')">*</button>

            <button onclick="appendValue('1')">1</button>
            <button onclick="appendValue('2')">2</button>
            <button onclick="appendValue('3')">3</button>
            <button onclick="appendValue('-')">-</button>

            <button onclick="appendValue('0')">0</button>
            <button onclick="appendValue('.')">.</button>
            <button onclick="calculateResult()">=</button>
            <button onclick="appendValue('+')">+</button>

            <button onclick="clearDisplay()" style="grid-column: span 4; background-color: #dc3545;">C</button>
        </div>
        <div class="author">Faisel Alnahdi</div>
    </div>

    <script>
        const display = document.getElementById('display');

        function appendValue(value) {
            display.value += value;
        }

        function clearDisplay() {
            display.value = '';
        }

        function calculateResult() {
            try {
                display.value = eval(display.value);
            } catch {
                display.value = 'Error';
            }
        }
    </script>
</body>
</html>
