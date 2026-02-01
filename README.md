<!DOCTYPE html>
<html lang="so">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Farriin Jacayl ❤️</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@400;600&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.5.1/dist/confetti.browser.min.js"></script>
    <style>
        :root {
            --primary: #e91e63;
            --bg-grad: linear-gradient(135deg, #fce4ec 0%, #f8bbd0 100%);
        }

        body {
            background: var(--bg-grad);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: 'Poppins', sans-serif;
            overflow: hidden;
        }

        .card {
            background: rgba(255, 255, 255, 0.95);
            padding: 25px;
            border-radius: 35px;
            text-align: center;
            box-shadow: 0 25px 50px rgba(0,0,0,0.12);
            width: 85%;
            max-width: 400px;
            position: relative;
            min-height: 580px;
            display: flex;
            flex-direction: column;
            align-items: center;
            transition: all 0.3s ease;
        }

        .img-container {
            width: 100%;
            height: 360px;
            overflow: hidden;
            border-radius: 25px;
            margin-bottom: 20px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.05);
        }

        img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 25px;
            transition: transform 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        h2 {
            margin: 15px 0 30px;
            color: #880e4f;
            font-size: 22px;
            font-weight: 600;
        }

        .buttons-container {
            width: 100%;
            height: 140px;
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
        }

        button {
            border: none;
            border-radius: 50px;
            font-size: 18px;
            cursor: pointer;
            padding: 14px 35px;
            font-weight: 600;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            font-family: 'Poppins', sans-serif;
        }

        #yes {
            background: var(--primary);
            color: white;
            box-shadow: 0 8px 20px rgba(233, 30, 99, 0.3);
            z-index: 5;
        }

        #yes:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 25px rgba(233, 30, 99, 0.4);
        }

        #no {
            background: #ffffff;
            color: #555;
            border: 1px solid #eee;
            box-shadow: 0 4px 10px rgba(0,0,0,0.05);
        }

        .result-text {
            display: none;
            margin-top: 10px;
            color: var(--primary);
            animation: fadeIn 1.2s ease forwards;
        }

        .result-text h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 38px;
            margin: 0;
        }

        .result-text p {
            font-size: 18px;
            font-style: italic;
            margin-top: 10px;
            color: #ad1457;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .zoom-in {
            transform: scale(1.05);
        }
    </style>
</head>
<body>

<div class="card" id="card">
    <div class="img-container">
        <img src="https://i.ibb.co/gbJqTGYY/file-000000006534720ab107c7ea21d0e032.png" id="mainImg" alt="Jaceyl">
    </div>

    <h2 id="questionText">Ma i jeceshahay yarey fatuush? 🥺❤️</h2>

    <div class="buttons-container" id="btnContainer">
        <button id="yes">Haa ❤️</button>
        <button id="no">Maya 🙈</button>
    </div>

    <div class="result-text" id="resultText">
        <h1>Waan ogaa 😍</h1>
        <p>Inaad sa'id' ii jeceshahay,<br>fatuush teydii sido kale ku jeclaha! 😉🫶🏻</p>
    </div>
</div>

<script>
    const yesBtn = document.getElementById("yes");
    const noBtn = document.getElementById("no");
    const mainImg = document.getElementById("mainImg");
    const questionText = document.getElementById("questionText");
    const resultText = document.getElementById("resultText");
    const btnContainer = document.getElementById("btnContainer");
    const card = document.getElementById("card");

    let yesSize = 18;
    const img1 = "https://i.ibb.co/gbJqTGYY/file-000000006534720ab107c7ea21d0e032.png"; // sawirka hore
    const img2 = "https://i.ibb.co/Cp8tx88t/file-0000000027ec71f4ba4c98523ef1ae47.png";  // sawirka kadib

    yesBtn.addEventListener("click", () => {
        mainImg.src = img2;
        mainImg.classList.add("zoom-in");
        questionText.style.display = "none";
        btnContainer.style.display = "none";
        resultText.style.display = "block";

        const count = 200, defaults = { origin: { y: 0.7 } };
        function fire(particleRatio, opts) {
            confetti(Object.assign({}, defaults, opts, {
                particleCount: Math.floor(count * particleRatio)
            }));
        }
        fire(0.25, { spread: 26, startVelocity: 55 });
        fire(0.2, { spread: 60 });
        fire(0.35, { spread: 100, decay: 0.91, scalar: 0.8 });
    });

    function moveNo() {
        if (noBtn.style.position !== "absolute") noBtn.style.position = "absolute";
        
        const cardRect = card.getBoundingClientRect();
        const maxX = cardRect.width - noBtn.offsetWidth - 20;
        const maxY = cardRect.height - noBtn.offsetHeight - 40;

        noBtn.style.left = `${Math.random() * maxX}px`;
        noBtn.style.top = `${Math.random() * maxY}px`;

        yesSize += 6;
        yesBtn.style.fontSize = `${yesSize}px`;
        yesBtn.style.padding = `${yesSize/2 + 5}px ${yesSize + 10}px`;
    }

    noBtn.addEventListener("mouseover", moveNo);
    noBtn.addEventListener("touchstart", (e) => { e.preventDefault(); moveNo(); });
</script>

</body>
</html>
