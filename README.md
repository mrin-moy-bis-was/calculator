# calculator
For devsoc
<!DOCTYPE html>
<html>
<head>
    <title>Basic Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }

        #calculator {
            width: 250px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f4f4f4;
            border-radius: 5px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        input[type="text"], input[type="button"] {
            width: 50px;
            height: 40px;
            margin: 5px;
        }

        #result {
            width: 200px;
            height: 40px;
            margin: 5px;
        }

        .button-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
        }
    </style>
</head>
<body>
    <div id="calculator">
        <input type="text" id="result" value="0" disabled>
        <div class="button-grid">
            <input type="button" value="1" onclick="addToResult('1')">
            <input type="button" value="2" onclick="addToResult('2')">
            <input type="button" value="3" onclick="addToResult('3')">
            <input type="button" value="+" onclick="addToResult('+')">
            <input type="button" value="4" onclick="addToResult('4')">
            <input type="button" value="5" onclick="addToResult('5')">
            <input type="button" value="6" onclick="addToResult('6')">
            <input type="button" value="-" onclick="addToResult('-')">
            <input type="button" value="7" onclick="addToResult('7')">
            <input type="button" value="8" onclick="addToResult('8')">
            <input type="button" value="9" onclick="addToResult('9')">
            <input type="button" value="*" onclick="addToResult('*')">
            <input type="button" value="C" onclick="clearResult()">
            <input type="button" value="0" onclick="addToResult('0')">
            <input type="button" value="=" onclick="calculateResult()">
            <input type="button" value="/" onclick="addToResult('/')">
        </div>
    </div>

    <script>
        let result = document.getElementById('result');

        function addToResult(value) {
            if (result.value === '0') {
                result.value = value;
            } else {
                result.value += value;
            }
        }

        function clearResult() {
            result.value = '0';
        }

        function calculateResult() {
            try {
                result.value = eval(result.value);
            } catch (error) {
                result.value = 'Error';
            }
        }
    </script>
</body>
</html>

