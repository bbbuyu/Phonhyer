<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CALCBT</title>
    <style>
        *{
            margin: 0%;
            padding: 0%;
        }
        .fundo{
            text-align: center;
            background-image: linear-gradient(45deg,black,crimson);
            height: 100vh;
            color:azure;
            font-family: fantasy;
        }
        .CALCBT{
            position: absolute;
            background-color: rgba(0,0,0,0.7);
            top: 50%;
            left: 50%;
            transform: translate(-50%,-50%);
            border-radius: 15px;
            padding: 15px;

        }
        .btn{
            margin: 3px;
            width: 50px;
            height: 50px;
            font-size: 30px;
            cursor: pointer;
            background-color: rgb(31,31,31);
            color: blanchedalmond;
        }
        .btn:hover{
            background-color: black;
        }
        #resultado{
            background-color: white;
            width: 215px;
            height: 30px;
            margin: 5px;
            font-size: 25px;
            color: black;
            text-align: right;
            padding: 5px;
        }
    </style>
</head>
<body>
    <div class="fundo">
        <h1>PHONHYER</h1>
        <div class="CALCBT">
            <h1>CALCBT</h1>
            <p id="resultado"></p>
            <table>
                <tr>
                    <td><button class="btn" onclick="clean()">D</button></td>
                    <td><button class="btn" onclick="back()"><</button></td>
                    <td><button class="btn" onclick="insert('/')">/</button></td>
                    <td><button class="btn" onclick="insert('x')">X</button></td>
                </tr>
                <tr>
                    <td><button class="btn" onclick="insert('7')">7</button></td>
                    <td><button class="btn" onclick="insert('8')">8</button></td>
                    <td><button class="btn" onclick="insert('9')">9</button></td>
                    <td><button class="btn" onclick="insert('-')">-</button></td>
                </tr>
                <tr>
                    <td><button class="btn" onclick="insert('4')">4</button></td>
                    <td><button class="btn" onclick="insert('5')">5</button></td>
                    <td><button class="btn" onclick="insert('6')">6</button></td>
                    <td><button class="btn" onclick="insert('+')">+</button></td>
                    <tr>
                        <td><button class="btn" onclick="insert('1')">1</button></td>
                        <td><button class="btn" onclick="insert('2')">2</button></td>
                        <td><button class="btn" onclick="insert('3')">3</button></td>
                        <td rowspan="2"><button class="btn" style="height: 106px;" onclick="calcular()">=</button></td>
                    </tr>
                    <tr>
                        <td colspan="2"><button class="btn" style="width: 106px;" onclick="insert('0')">0</button></td>
                        <td><button class="btn" onclick="insert('.')">.</button></td>
                    </tr>
                </tr>
            </table>
        </div>
    </div>
    <script>
        function insert(num){
            var numero = document.getElementById('resultado').innerHTML;
            document.getElementById('resultado').innerHTML = numero + num;
        }
        function clean(){
            document.getElementById('resultado').innerHTML = "";
        }
        function back(){
            var resultado = document.getElementById('resultado').innerHTML;
            document.getElementById('resultado').innerHTML = resultado.substring(0, resultado.length -1)
        }
        function calcular(){
            var resultado = document.getElementById('resultado').innerHTML;
            if(resultado){
                document.getElementById('resultado').innerHTML = eval(resultado);
            }
            else{
                document.getElementById('resultado').innerHTML = "0"
            }
        }
    </script>
</body>
</html>
