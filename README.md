# jaan-its-only-for-you-
love you pucchhu
<!DOCTYPE html>
<html>
<head>
    <title>Funny Light Question</title>

    <!-- Confetti Library -->
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

    <style>
        body {
            text-align: center;
            font-family: Arial;
            background: linear-gradient(to right, #1e3c72, #2a5298);
            color: white;
            margin-top: 100px;
            overflow: hidden;
        }

        h1 {
            font-size: 32px;
        }

        button {
            padding: 12px 25px;
            font-size: 18px;
            margin: 20px;
            cursor: pointer;
            border: none;
            border-radius: 8px;
        }

        #yesBtn {
            background-color: #00c853;
            color: white;
        }

        #noBtn {
            background-color: #d50000;
            color: white;
            position: absolute;
        }

        #celebration {
            display: none;
            font-size: 40px;
            margin-top: 30px;
            animation: pop 1s ease infinite alternate;
        }

        @keyframes pop {
            from { transform: scale(1); }
            to { transform: scale(1.2); }
        }
    </style>
</head>

<body>

    <h1>ham light on kar rahe hay 💡</h1>

    <button id="yesBtn" onclick="celebrate()">hmm yaar on hi karenge</button>
    <button id="noBtn" onmouseover="moveButton()">nahi ham nahi on karenge</button>

    <div id="celebration">🎉🔥 LIGHT ON PARTY 🔥🎉</div>

    <script>
        function moveButton() {
            let x = Math.random() * (window.innerWidth - 150);
            let y = Math.random() * (window.innerHeight - 100);

            let btn = document.getElementById("noBtn");
            btn.style.left = x + "px";
            btn.style.top = y + "px";
        }

        function celebrate() {
            document.getElementById("celebration").style.display = "block";

            // Fireworks effect (confetti)
            let duration = 3000;
            let end = Date.now() + duration;

            (function frame() {
                confetti({
                    particleCount: 7,
                    angle: Math.random() * 360,
                    spread: 70,
                    origin: {
                        x: Math.random(),
                        y: Math.random() - 0.2
                    }
                });

                if (Date.now() < end) {
                    requestAnimationFrame(frame);
                }
            })();
        }
    </script>

</body>
</html>
