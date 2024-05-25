<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Multiplication Table Generator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .container {
            background: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            width: 300px;
            text-align: center;
        }

        h1 {
            margin-bottom: 20px;
            color: #333;
        }

        form {
            margin-bottom: 20px;
        }

        input {
            padding: 8px;
            margin-right: 10px;
            width: 100px;
        }

        button {
            padding: 8px 16px;
            background-color: #28a745;
            border: none;
            color: white;
            cursor: pointer;
            border-radius: 4px;
        }

        button:hover {
            background-color: #218838;
        }

        #result {
            margin-top: 20px;
            text-align: left;
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        th, td {
            padding: 8px;
            text-align: center;
            border: 1px solid #ddd;
        }

        th {
            background-color: #f4f4f9;
        }

        td {
            background-color: #fff;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Multiplication Table Generator</h1>
        <form id="multiplicationForm">
            <label for="numberInput">Enter a number:</label>
            <input type="number" id="numberInput" required>
            <button type="submit">Generate Table</button>
        </form>
        <div id="result"></div>
    </div>
    <script>
        document.getElementById('multiplicationForm').addEventListener('submit', function(event) {
            event.preventDefault();
            const number = parseInt(document.getElementById('numberInput').value);
            const resultDiv = document.getElementById('result');
            
            if (isNaN(number)) {
                resultDiv.innerHTML = '<p>Please enter a valid number.</p>';
                return;
            }

            let table = '<table>';
            table += '<thead><tr><th>Number</th><th>Multiplication</th><th>Result</th></tr></thead><tbody>';
            for (let i = 1; i <= 10; i++) {
                table += `<tr><td>${number}</td><td>${number} x ${i}</td><td>${number * i}</td></tr>`;
            }
            table += '</tbody></table>';

            resultDiv.innerHTML = table;
        });
    </script>
</body>
</html>
