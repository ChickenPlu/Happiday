<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">

<title>Chúc Mừng Sinh Nhật bồ 🎉</title>

<style>
    body {
        margin: 0;
        height: 100vh;
        overflow: hidden;
        background: linear-gradient(45deg, #ff9ecb, #ffd6e8, #ffe6f2, #ffb3d9);
        background-size: 600% 600%;
        animation: bgMove 10s infinite alternate;
        display: flex;
        justify-content: center;
        align-items: center;
        font-family: -apple-system, BlinkMacSystemFont, Arial;
        padding: env(safe-area-inset-top) env(safe-area-inset-right)
                 env(safe-area-inset-bottom) env(safe-area-inset-left);
    }

    @keyframes bgMove {
        0% { background-position: 0% 50%; }
        100% { background-position: 100% 50%; }
    }

    /* TRÁI TIM RỰC RỠ */
    .heart {
        width: min(35vw, 200px);
        height: min(35vw, 200px);
        background: radial-gradient(circle, #ff3d7a, #ff0055);
        position: absolute;
        transform: rotate(-45deg);
        animation: heartbeat 1.4s infinite, glow 2s infinite alternate;
        filter: drop-shadow(0 0 15px #ff1a75);
    }

    .heart:before,
    .heart:after {
        content: "";
        width: inherit;
        height: inherit;
        background: radial-gradient(circle, #ff3d7a, #ff0055);
        border-radius: 50%;
        position: absolute;
    }

    .heart:before {
        top: calc(-0.5 * min(35vw, 200px));
        left: 0;
    }

    .heart:after {
        left: calc(0.5 * min(35vw, 200px));
        top: 0;
    }

    @keyframes heartbeat {
        0% { transform: scale(1) rotate(-45deg); }
        50% { transform: scale(1.2) rotate(-45deg); }
        100% { transform: scale(1) rotate(-45deg); }
    }

    @keyframes glow {
        0% { filter: drop-shadow(0 0 5px #ff4da6); }
        100% { filter: drop-shadow(0 0 30px #ff1a75); }
    }

    /* CHỮ CHẠY */
    .run-text {
        position: absolute;
        font-size: min(7vw, 32px);
        font-weight: bold;
        color: #ff0077;
        animation: moveText 8s linear infinite;
        white-space: nowrap;
    }

    @keyframes moveText {
        0% { left: -100%; }
        100% { left: 120%; }
    }

    /* TIM BAY */
    .floating-heart {
        position: absolute;
        color: #ff0066;
        font-size: 20px;
        animation: floatUp 4s linear forwards;
        opacity: 0.8;
    }

    @keyframes floatUp {
        0% { transform: translateY(50vh) scale(1); opacity: 1; }
        100% { transform: translateY(-100vh) scale(1.8); opacity: 0; }
    }

    /* PHÁO HOA */
    .firework {
        position: absolute;
        width: 5px;
        height: 5px;
        background: yellow;
        border-radius: 50%;
        animation: explode 600ms ease-out forwards;
    }

    @keyframes explode {
        from { transform: scale(1); opacity: 1; }
        to { transform: scale(25); opacity: 0; }
    }

    /* HỘP QUÀ */
    #giftBox {
        position: absolute;
        bottom: 40px;
        background: #ff4da6;
        padding: 18px 26px;
        border-radius: 12px;
        color: white;
        font-size: 22px;
        font-weight: bold;
        cursor: pointer;
        animation: pulse 2s infinite;
    }

    @keyframes pulse {
        0% { transform: scale(1); }
        50% { transform: scale(1.1); }
        100% { transform: scale(1); }
    }

    #message {
        position: absolute;
        bottom: 110px;
        font-size: 26px;
        font-weight: bold;
        color: #ff0088;
        display: none;
    }
</style>
</head>

<body>

    <div class="heart"></div>

    <!-- 5 DÒNG CHỮ CHẠY -->
    <div class="run-text" style="top: 20%;">💖 Chúc Mừng Sinh Nhật BTrâm yêu 💖</div>
    <div class="run-text" style="top: 35%; animation-delay: 1s;">🎂 Chúc em luôn xinh đẹp và hạnh phúc 🎂</div>
    <div class="run-text" style="top: 50%; animation-delay: 2s;">✨ Gà thương Trâm nhiều lắm ✨</div>
    <div class="run-text" style="top: 65%; animation-delay: 3s;">🌸 Mong mọi điều tốt đẹp nhất đến với em 🌸</div>
    <div class="run-text" style="top: 80%; animation-delay: 4s;">🎉 Happy Birthday to youuu 🎉</div>

    <!-- HỘP QUÀ -->
    <div id="giftBox">🎁 Mở Quà</div>
    <div id="message">Chúc em một ngày sinh nhật thật tuyệt vời 💖✨</div>

    <!-- NHẠC -->
    <audio id="music" autoplay loop>
        <source src="https://cdn.pixabay.com/download/audio/2022/02/23/audio_4dfc349303.mp3?filename=happy-birthday-125417.mp3" type="audio/mpeg">
    </audio>

<script>
/* TIM BAY */
setInterval(() => {
    const heart = document.createElement("div");
    heart.className = "floating-heart";
    heart.innerText = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = (20 + Math.random() * 20) + "px";
    document.body.appendChild(heart);

    setTimeout(() => heart.remove(), 4000);
}, 400);

/* PHÁO HOA RANDOM */
setInterval(() => {
    const f = document.createElement("div");
    f.className = "firework";
    f.style.left = Math.random() * 100 + "vw";
    f.style.top = Math.random() * 100 + "vh";
    f.style.background = ["yellow", "white", "pink", "cyan"][Math.floor(Math.random()*4)];
    document.body.appendChild(f);
    setTimeout(() => f.remove(), 600);
}, 700);

/* HỘP QUÀ HIỆU ỨNG */
document.getElementById("giftBox").onclick = () => {
    document.getElementById("message").style.display = "block";
    document.getElementById("giftBox").style.display = "none";
};
</script>

</body>
</html>
