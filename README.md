<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carta de Amor</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #d9e3d6;
            font-family: 'Arial', sans-serif;
        }
        .container {
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .tulip {
            position: absolute;
            width: 50px;
            height: 100px;
            background-color: transparent;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }
        .tulip::before, .tulip::after {
            content: '';
            width: 0;
            height: 0;
            border-style: solid;
            border-width: 0 25px 50px 25px;
            border-color: transparent transparent #ff1493 transparent;
            position: absolute;
        }
        .tulip::before {
            transform: rotate(-15deg);
        }
        .tulip::after {
            transform: rotate(15deg);
        }
        .stem {
            width: 5px;
            height: 50px;
            background-color: #58ae58;
            margin-top: 30px;
        }
        .tulip.left {
            left: -70px;
        }
        .tulip.right {
            right: -70px;
        }
        .envelope {
            position: relative;
            width: 400px;
            height: 300px;
            background-color: #ffcccb;
            border: 2px solid #b22222;
            border-radius: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            cursor: pointer;
            overflow: hidden;
            transition: all 0.6s ease;
        }
        .envelope.open .seal {
            display: none;
        }
        .seal {
            position: absolute;
            width: 50px;
            height: 50px;
            background-color: #b22222;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-size: 1.5rem;
            font-weight: bold;
            transition: all 0.6s ease;
            z-index: 10;
        }
        .heart {
            position: absolute;
            bottom: -30px;
            width: 50px;
            height: 45px;
            background-color: #c61719;
            transform: rotate(-45deg);
            animation: heartbeat 1s infinite;
            cursor: pointer;
            z-index: 10;
        }
        .heart::before, .heart::after {
            content: '';
            position: absolute;
            width: 50px;
            height: 45px;
            background-color: #f01b1b;
            border-radius: 50%;
        }
        .heart::before {
            top: -25px;
            left: 0;
        }
        .heart::after {
            left: 25px;
            top: 0;
        }
        @keyframes heartbeat {
            0%, 100% {
                transform: scale(1) rotate(-45deg);
            }
            50% {
                transform: scale(1.2) rotate(-45deg);
            }
        }
        .letter {
            position: absolute;
            width: 330px;
            height: 180px;
            background-color: white;
            padding: 20px;
            text-align: center;
            transform: translateY(100%);
            transition: all 0.6s ease;
            font-family: 'Cursive', serif;
        }
        .envelope.open .letter {
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="tulip left">
            <div class="stem"></div>
        </div>
        <div class="envelope" id="envelope">
            <div class="seal">❤️</div>
            <div class="letter">
                <p><em>❤️ Para mi princesita: Flor Gimena Pumacayo Llaccta ❤️,</em></p>
                <p><em>Quiero que sepas que cada día a tu lado es un regalo. Eres mi mar.. mi montaña, eres mi tempestad y mi calma.. ohhh Spanish Girl, te amo mucho mi reina.</em></p>
                <p><em>Tuyo por siempre: Jorge Luis Vargas Guevara❤️</em></p>
            </div>
            <div class="heart" id="heart"></div>
        </div>
        <div class="tulip right">
            <div class="stem"></div>
        </div>
    </div>

    <script>
        document.querySelector('.seal').addEventListener('click', function() {
            document.getElementById('envelope').classList.toggle('open');
        });
        document.getElementById('heart').addEventListener('click', function() {
            document.getElementById('envelope').classList.remove('open');
        });
    </script>
</body>
</html>
