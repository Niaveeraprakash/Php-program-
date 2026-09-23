# Php-program-
Program 3
<!DOCTYPE html>
<html>
<head>
    <title>Arithmetic Operation</title>

    <style>
        body {
            font-family: Arial;
            text-align: center;
            margin-top: 50px;
        }

        form {
            width: 300px;
            margin: auto;
            padding: 20px;
            border: 2px solid black;
        }

        input, select {
            padding: 8px;
            margin: 8px;
        }
    </style>
</head>

<body>

<h2>Arithmetic Calculator</h2>

<form method="post">

    Number 1:
    <input type="number" name="num1" required>
    <br>

    Number 2:
    <input type="number" name="num2" required>
    <br>

    Operation:
    <select name="operation">
        <option value="add">Addition</option>
        <option value="sub">Subtraction</option>
        <option value="mul">Multiplication</option>
        <option value="div">Division</option>
    </select>
    <br>

    <input type="submit" value="Calculate">

</form>

<?php

if ($_SERVER["REQUEST_METHOD"] == "POST") {

    $num1 = $_POST["num1"];
    $num2 = $_POST["num2"];
    $operation = $_POST["operation"];

    switch ($operation) {

        case "add":
            $result = $num1 + $num2;
            echo "<h3>Result = $result</h3>";
            break;

        case "sub":
            $result = $num1 - $num2;
            echo "<h3>Result = $result</h3>";
            break;

        case "mul":
            $result = $num1 * $num2;
            echo "<h3>Result = $result</h3>";
            break;

        case "div":
            if ($num2 != 0) {
                $result = $num1 / $num2;
                echo "<h3>Result = $result</h3>";
            } else {
                echo "<h3>Cannot divide by zero</h3>";
            }
            break;
    }
}

?>

</body>
</html>

Output 
Arithmetic Calculator

Number 1: 20
Number 2: 10

Operation: Addition

[Calculate]

Result = 30
