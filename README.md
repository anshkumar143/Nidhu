<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>For Nidhi Princess 🌟</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display&family=Sacramento&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      background: radial-gradient(circle at top, #1a1a2e, #0f0f1c);
      color: #fff;
      font-family: 'Playfair Display', serif;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
      overflow: hidden;
      position: relative;
    }

    .letter-box {
      background: rgba(255, 255, 255, 0.1);
      border: 2px solid rgba(255, 255, 255, 0.2);
      padding: 40px;
      border-radius: 15px;
      backdrop-filter: blur(8px);
      box-shadow: 0 0 20px rgba(255, 255, 255, 0.1);
      max-width: 600px;
      text-align: center;
    }

    h1 {
      font-family: 'Sacramento', cursive;
      font-size: 3em;
      color: #ff9aa2;
      margin-bottom: 10px;
    }

    p {
      font-size: 1.2em;
      line-height: 1.8;
      margin: 20px 0;
      color: #f8f8f8;
    }

    .signature {
      font-family: 'Sacramento', cursive;
      font-size: 2em;
      color: #f7c8e0;
      margin-top: 40px;
    }

    .heart-glow {
      position: absolute;
      bottom: 40px;
      left: 50%;
      transform: translateX(-50%);
      width: 60px;
      height: 60px;
      background: #ff4d6d;
      transform: rotate(45deg);
      box-shadow: 0 0 25px #ff4d6d, 0 0 50px #ff4d6d;
      animation: pulse 2s infinite;
    }

    .heart-glow::before,
    .heart-glow::after {
      content: '';
      position: absolute;
      width: 60px;
      height: 60px;
      background: #ff4d6d;
      border-radius: 50%;
    }

    .heart-glow::before {
      top: -30px;
      left: 0;
    }

    .heart-glow::after {
      left: -30px;
      top: 0;
    }

    @keyframes pulse {
      0% { transform: scale(1) rotate(45deg); }
      50% { transform: scale(1.2) rotate(45deg); }
      100% { transform: scale(1) rotate(45deg); }
    }

    .stars {
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      overflow: hidden;
      z-index: 0;
    }

    .stars span {
      position: absolute;
      background: white;
      border-radius: 50%;
      animation: twinkle 5s infinite ease-in-out;
    }

    @keyframes twinkle {
      0%, 100% { opacity: 0.2; }
      50% { opacity: 1; }
    }
  </style>
</head>
<body>
  <div class="stars">
    <script>
      for (let i = 0; i < 60; i++) {
        const star = document.createElement('span');
        const size = Math.random() * 3 + 1;
        star.style.width = size + 'px';
        star.style.height = size + 'px';
        star.style.left = Math.random() * 100 + 'vw';
        star.style.top = Math.random() * 100 + 'vh';
        star.style.animationDuration = (Math.random() * 5 + 3) + 's';
        document.querySelector('.stars').appendChild(star);
      }
    </script>
  </div>

  <div class="letter-box">
    <h1>My Sweet Nidhi Princess 💫</h1>
    <p>
      You are the poetry in my silence, the light in my dusk, the warmth in my coldest nights. I don’t need the stars to wish upon — I already have my brightest one, and that’s you.
    </p>
    <p>
      Every heartbeat of mine spells your name. Every smile I wear is born from thoughts of you. You are not just in my life — you are my life.
    </p>
    <p>
      I may not be perfect, but my love for you is pure, endless, and true. Please forgive me if I’ve ever made you feel less than the queen you are. I will always cherish you, protect you, and love you beyond words.
    </p>
    <div class="signature">With all my love,<br>Your Forever ❤️</div>
  </div>

  <div class="heart-glow"></div>
</body>
</html>
