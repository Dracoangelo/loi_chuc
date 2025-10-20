<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Lời chúc 20/10 💞</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background: radial-gradient(circle at top left, #ffafbd, #ffc3a0);
      font-family: 'Segoe UI', sans-serif;
      color: #fff;
      text-align: center;
      overflow: hidden;
      animation: bgMove 10s infinite alternate;
    }

    @keyframes bgMove {
      0% { background-position: 0% 0%; }
      100% { background-position: 100% 100%; }
    }

    h1 {
      font-size: 2.5rem;
      margin-bottom: 1rem;
      text-shadow: 0 0 10px rgba(255,255,255,0.6);
      animation: fadeIn 2s ease-in-out;
    }

    #message {
      font-size: 1.3rem;
      max-width: 650px;
      line-height: 1.6;
      white-space: pre-wrap;
      border-right: 3px solid rgba(255,255,255,0.7);
      animation: caret 0.8s infinite;
    }

    @keyframes caret {
      50% { border-color: transparent; }
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .hearts {
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      overflow: hidden;
      z-index: -1;
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: rgba(255,255,255,0.7);
      transform: rotate(45deg);
      animation: float 8s infinite ease-in;
    }

    .heart::before,
    .heart::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background: rgba(255,255,255,0.7);
      border-radius: 50%;
    }

    .heart::before { top: -10px; left: 0; }
    .heart::after { left: -10px; top: 0; }

    @keyframes float {
      0% { transform: translateY(0) scale(1) rotate(45deg); opacity: 1; }
      100% { transform: translateY(-800px) scale(1.5) rotate(45deg); opacity: 0; }
    }

    button {
      margin-top: 2rem;
      padding: 10px 20px;
      border: none;
      border-radius: 25px;
      background: #fff;
      color: #ff6b81;
      font-size: 1rem;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      background: #ffe6eb;
      transform: scale(1.05);
    }
  </style>
</head>
<body>
  <div class="hearts"></div>
  <h1>💐 Chúc em thúi yêu ngày 20/10 thật hạnh phúc 💐</h1>
  <p id="message"></p>
  <button id="playBtn">💞 Phát nhạc 💞</button>

  <audio id="music" loop>
    <!-- Thay link này bằng link nhạc bạn muốn -->
    <source src="https://files.catbox.moe/8c9j1q.mp3" type="audio/mpeg">
  </audio>

  <script>
    // Hiệu ứng tim bay
    const hearts = document.querySelector('.hearts');
    setInterval(() => {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = 4 + Math.random() * 4 + 's';
      hearts.appendChild(heart);
      setTimeout(() => heart.remove(), 8000);
    }, 300);

    // Hiệu ứng đánh máy
    const text = `
Cảm ơn em vì đã đến bên anh, làm cuộc sống này trở nên ngọt ngào hơn 💗
Chúc em luôn xinh đẹp, rạng rỡ và hạnh phúc thật nhiều — 
không chỉ hôm nay mà là mỗi ngày, vì em xứng đáng với tất cả yêu thương này 💞
Anh yêu em ❤️
`;
    let i = 0;
    const message = document.getElementById('message');

    function typeEffect() {
      if (i < text.length) {
        message.textContent += text.charAt(i);
        i++;
        setTimeout(typeEffect, 50);
      }
    }
    window.onload = typeEffect;

    // Phát nhạc
    const music = document.getElementById('music');
    const playBtn = document.getElementById('playBtn');
    playBtn.onclick = () => {
      music.play();
      playBtn.textContent = "🎵 Đang phát: Hơn Cả Yêu 🎵";
      playBtn.disabled = true;
      playBtn.style.opacity = "0.8";
    };
  </script>
</body>
</html>
