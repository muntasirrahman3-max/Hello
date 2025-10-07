<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Date Proposal 💖</title>

<style>
    * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    body {
        background: linear-gradient(to bottom right, #a0e9ff, #f7c6ff);
        height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        overflow: hidden;
        font-family: 'Comic Sans MS', cursive;
        position: relative;
    }

    h1 {
        color: #fff;
        font-size: 30px;
        margin-bottom: 20px;
        text-shadow: 2px 2px 5px #555;
    }

    img {
        width: 120px;
        margin-bottom: 20px;
    }

    .btn {
        padding: 10px 25px;
        margin: 10px;
        border: none;
        border-radius: 12px;
        background-color: #ff4081;
        color: white;
        font-size: 18px;
        cursor: pointer;
        transition: transform 0.2s ease, background 0.3s ease;
    }

    .btn:hover {
        background-color: #e91e63;
        transform: scale(1.1);
    }

    #noBtn {
        position: absolute;
    }

    .heart {
        position: absolute;
        color: #ff5c8d;
        font-size: 24px;
        animation: floatUp 4s linear infinite;
    }

    @keyframes floatUp {
        0% { transform: translateY(0); opacity: 1; }
        100% { transform: translateY(-800px); opacity: 0; }
    }
</style>
</head>

<body>
    <audio id="bgMusic" loop>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mp3">
    </audio>

    <h1>Will you go out on a date with me? 💞</h1>
    <img src="https://cdn-icons-png.flaticon.com/512/616/616408.png" alt="Cute bear">

    <div>
        <button class="btn" id="yesBtn" onclick="sayYes()">Yes 💕</button>
        <button class="btn" id="noBtn" onmouseover="moveButton()">No 🙈</button>
    </div>

<script>
    const noBtn = document.getElementById('noBtn');
    const music = document.getElementById('bgMusic');

    // Start music when page loads
    window.onload = () => {
        music.play().catch(() => {
            console.log("User interaction needed for autoplay.");
        });
        setInterval(createHeart, 400);
    };

    // Move the "No" button around randomly
    function moveButton() {
        const x = Math.random() * (window.innerWidth - 100);
        const y = Math.random() * (window.innerHeight - 50);
        noBtn.style.left = `${x}px`;
        noBtn.style.top = `${y}px`;
    }

    // When user clicks "Yes"
    function sayYes() {
        document.body.innerHTML = `
            <h1 style="color:#fff; font-size:32px;">Yay! ❤️ I knew you'd say yes!</h1>
            <img src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif" width="200">
            <h2 style="color:#fff; margin-top:15px;">Let’s plan our date soon! 💐</h2>
        `;
        music.src = "https://cdn.pixabay.com/download/audio/2023/03/13/audio_3b3b1d5d46.mp3?filename=romantic-music-140990.mp3";
        music.play();
    }

    // Floating hearts animation
    function createHeart() {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "💖";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDuration = Math.random() * 2 + 3 + "s";
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 5000);
    }
</script>

</body>
</html>
