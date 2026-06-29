<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="calculator">
    <input type="text" id="display" readonly>

    <div class="buttons">
        <button onclick="clearDisplay()" class="clear">AC</button>
        <button onclick="deleteLast()">DEL</button>
        <button onclick="appendValue('%')">%</button>
        <button onclick="appendValue('/')">/</button>

        <button onclick="appendValue('7')">7</button>
        <button onclick="appendValue('8')">8</button>
        <button onclick="appendValue('9')">9</button>
        <button onclick="appendValue('*')">×</button>

        <button onclick="appendValue('4')">4</button>
        <button onclick="appendValue('5')">5</button>
        <button onclick="appendValue('6')">6</button>
        <button onclick="appendValue('-')">-</button>

        <button onclick="appendValue('1')">1</button>
        <button onclick="appendValue('2')">2</button>
        <button onclick="appendValue('3')">3</button>
        <button onclick="appendValue('+')">+</button>

        <button onclick="appendValue('0')" class="zero">0</button>
        <button onclick="appendValue('.')">.</button>
        <button onclick="calculate()" class="equal">=</button>
    </div>
</div>

<script src="script.js"></script>

</body>
</html> 
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial,sans-serif;
}

body{
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    background:linear-gradient(135deg,#141e30,#243b55);
}

.calculator{
    background:#1f2937;
    padding:20px;
    border-radius:20px;
    box-shadow:0 10px 25px rgba(0,0,0,.4);
    width:350px;
}

#display{
    width:100%;
    height:70px;
    border:none;
    outline:none;
    border-radius:10px;
    margin-bottom:20px;
    padding:15px;
    font-size:30px;
    text-align:right;
    background:#111827;
    color:#fff;
}

.buttons{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:10px;
}

button{
    height:65px;
    border:none;
    border-radius:10px;
    font-size:22px;
    cursor:pointer;
    background:#374151;
    color:white;
    transition:.3s;
}

button:hover{
    background:#4b5563;
    transform:scale(1.05);
}

.equal{
    background:#f59e0b;
}

.equal:hover{
    background:#d97706;
}

.clear{
    background:#ef4444;
}

.clear:hover{
    background:#dc2626;
}

.zero{
    grid-column:span 2;
}  
let display = document.getElementById("display");

function appendValue(value){
    display.value += value;
}

function clearDisplay(){
    display.value = "";
}

function deleteLast(){
    display.value = display.value.slice(0,-1);
}

function calculate(){
    try{
        display.value = eval(display.value);
    }
    catch{
        display.value = "Error";
    }
}
