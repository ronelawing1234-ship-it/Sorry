<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>I Love You 💖</title>
  <meta name="viewport"
    content="width=device-width">

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    height: 100vh;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(135deg, #17052f, #4b167a, #230b45);
    font-family: Arial, sans-serif;
}

/* Floating hearts */
.heart {
    position: absolute;
    bottom: -30px;
    color: #ffb6e6;
    opacity: 0;
    animation: floatUp linear forwards;
    pointer-events: none;
}

@keyframes floatUp {
    0% { transform: translateY(0); opacity: 0; }
    20% { opacity: 0.8; }
    100% {
        transform: translateY(-110vh) rotate(360deg);
        opacity: 0;
    }
}

/* Flower */
.container {
    text-align: center;
    position: relative;
    z-index: 2;
}

.flower {
    position: relative;
    width: 220px;
    height: 260px;
    animation: sway 4s ease-in-out infinite;
    transform-origin: bottom center;
}

@keyframes sway {
    0%, 100% { transform: rotate(-4deg); }
    50% { transform: rotate(4deg); }
}

/* Petals */
.petals {
    position: absolute;
    width: 180px;
    height: 180px;
    top: 0;
    left: 20px;
}

.petal {
    position: absolute;
    width: 65px;
    height: 95px;
    left: 57px;
    top: 0;
    border-radius: 50%;
    transform-origin: 50% 100%;

    /* Black petal outline */
    border: 2px solid #000;

    background: #ff1744;
    box-shadow: 0 0 18px rgba(255, 120, 180, 0.5);

    animation: bloom 2s ease-out forwards,
               colors 9s infinite;
}

.petal:nth-child(1) { --angle: 0deg; }
.petal:nth-child(2) { --angle: 60deg; }
.petal:nth-child(3) { --angle: 120deg; }
.petal:nth-child(4) { --angle: 180deg; }
.petal:nth-child(5) { --angle: 240deg; }
.petal:nth-child(6) { --angle: 300deg; }

@keyframes bloom {
    from {
        transform: rotate(var(--angle)) scale(0);
    }
    to {
        transform: rotate(var(--angle)) scale(1);
    }
}

/* Changing flower colors */
@keyframes colors {
    0%, 30% { background: #ff1744; }
    33%, 63% { background: #a855f7; }
    66%, 100% { background: #ff80ab; }
}

/* Flower center */
.center {
    position: absolute;
    width: 38px;
    height: 38px;
    background: radial-gradient(circle, #fff4a3, #ffb300);
    border-radius: 50%;
    top: 68px;
    left: 91px;
    z-index: 5;
    box-shadow: 0 0 20px #ffdf80;
}

/* Stem and leaves */
.stem {
    position: absolute;
    width: 9px;
    height: 125px;
    background: linear-gradient(to right, #1c8c48, #61d68a);
    top: 135px;
    left: 105px;
    border-radius: 20px;
}

.leaf {
    position: absolute;
    width: 55px;
    height: 28px;
    background: linear-gradient(45deg, #188b48, #69db89);
    border-radius: 100% 0 100% 0;
    top: 185px;
    left: 110px;
    transform: rotate(-25deg);
}

.leaf.left {
    left: 55px;
    top: 205px;
    transform: rotate(200deg);
}

/* Message */
h2 {
    color: #ffd6f4;
    margin-top: 25px;
    font-size: 25px;
    text-shadow: 0 0 15px #ff8bda;
    letter-spacing: 2px;
    animation: glow 2s ease-in-out infinite alternate;
}

@keyframes glow {
    from { text-shadow: 0 0 10px #ff8bda; }
    to { text-shadow: 0 0 25px #ff4fc8; }
}
</style>
</head>

<body>

<div class="container">
    <div class="flower">

        <div class="petals">
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="petal"></div>
        </div>

        <div class="center"></div>
        <div class="stem"></div>
        <div class="leaf"></div>
        <div class="leaf left"></div>

    </div>

    <h2>I LOVE YOU 🫶💖</h2>
</div>

<script>
function createHeart() {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "♥";

    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = (10 + Math.random() * 18) + "px";
    heart.style.animationDuration = (5 + Math.random() * 8) + "s";

    document.body.appendChild(heart);

    setTimeout(() => heart.remove(), 13000);
}

setInterval(createHeart, 400);
</script>

</body>
</html>
