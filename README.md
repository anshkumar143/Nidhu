<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Nidhi’s Love Diary 💖</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display&family=Sacramento&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      background: linear-gradient(to right, #ffe0ec, #ffd6e8);
      font-family: 'Playfair Display', serif;
      overflow-x: hidden;
    }

    .page {
      display: none;
      padding: 60px 20px;
      max-width: 700px;
      margin: auto;
      min-height: 100vh;
      box-sizing: border-box;
    }

    .page.active {
      display: block;
    }

    h1, h2 {
      font-family: 'Sacramento', cursive;
      font-size: 3em;
      color: #e91e63;
      text-align: center;
    }

    p {
      font-size: 1.2em;
      line-height: 1.8;
      color: #333;
      text-align: justify;
    }

    .signature {
      text-align: right;
      font-size: 1.5em;
      margin-top: 40px;
      color: #c2185b;
    }

    .nav {
      text-align: center;
      margin-top: 40px;
    }

    .nav button {
      background: #e91e63;
      color: white;
      border: none;
      padding: 12px 25px;
      border-radius: 30px;
      font-size: 1em;
      margin: 5px;
      cursor: pointer;
      box-shadow: 0 5px 15px rgba(0,0,0,0.2);
      transition: 0.3s ease;
    }

    .nav button:hover {
      background: #c2185b;
    }

    .cover, .lock-screen {
      background: linear-gradient(to bottom right, #fff0f5, #ffe6eb);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      height: 100vh;
    }

    .cover h1, .lock-screen h1 {
      font-size: 4em;
      color: #e91e63;
    }

    .cover button, .lock-screen button {
      margin-top: 30px;
      font-size: 1.3em;
      padding: 15px 40px;
      background: #ff85a2;
      border: none;
      color: white;
      border-radius: 40px;
      cursor: pointer;
      box-shadow: 0 10px 20px rgba(0,0,0,0.2);
    }

    .cover button:hover, .lock-screen button:hover {
      background: #e75376;
    }

    #countdown {
      font-size: 1.2em;
      color: #c2185b;
      margin-top: 20px;
    }

    audio {
      display: none;
    }

    .images-area img {
      max-width: 100%;
      margin: 10px 0;
      border-radius: 15px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.2);
    }
  </style>
</head>
<body>

  <!-- Lock Screen -->
  <div class="lock-screen" id="lockScreen">
    <h1>💖 Welcome to Nidhi’s Diary 💖</h1>
    <p>Please enter the password:</p>
    <input type="password" id="passwordInput" placeholder="Enter password" />
    <button onclick="checkPassword()">Unlock</button>
  </div>

  <!-- Cover Page -->
  <div class="page cover" id="page0">
    <h1>Nidhi’s Love Diary 💖</h1>
    <p>A collection of love, apologies, and endless affection...</p>
    <div id="countdown">Loading countdown...</div>
    <button onclick="goToPage(1)">Open Diary 📖</button>
  </div>

  <!-- Letter Page 1 -->
  <div class="page" id="page1">
    <h2>Letter 1: From My Heart to Yours</h2>
    <p>Dearest Nidhi Princess,</p>
    <p>
      I don’t know where to begin, because no words can truly capture how much you mean to me.
      Every moment with you is like a dream I never want to wake up from. You’ve filled my life
      with joy, light, and a kind of love I never knew was possible.
    </p>
    <p>
      I want you to know that my heart beats only for you. You are my sunshine, my moonlight, my everything.
      Let’s create beautiful memories together, laugh until we cry, and love endlessly.
    </p>
    <div class="signature">Forever Yours,<br>Your Love 💌</div>
    <div class="nav">
      <button onclick="goToPage(0)">← Back</button>
      <button onclick="goToPage(2)">Next →</button>
    </div>
  </div>

  <!-- Letter Page 2 -->
  <div class="page" id="page2">
    <h2>Letter 2: My Starry Love 💫</h2>
    <p>
      You are the poetry in my silence, the light in my dusk, the warmth in my coldest nights.
      I don’t need the stars to wish upon — I already have my brightest one, and that’s you.
    </p>
    <p>
      Every heartbeat of mine spells your name. You are not just in my life — you are my life.
    </p>
    <div class="signature">With all my love,<br>Your Forever ❤️</div>
    <div class="nav">
      <button onclick="goToPage(1)">← Back</button>
      <button onclick="goToPage(3)">Next →</button>
    </div>
  </div>

  <!-- Picture Page -->
  <div class="page" id="page3">
    <h2>📸 Our Beautiful Moments</h2>
    <input type="file" accept="image/*" onchange="handleImageUpload(event)">
    <div class="images-area" id="imageGallery"></div>
    <div class="nav">
      <button onclick="goToPage(2)">← Back</button>
    </div>
  </div>

  <!-- Background Music -->
  <audio autoplay loop>
    <source src="https://www.bensound.com/bensound-music/bensound-love.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
  </audio>

  <script>
    // Password
    const PASSWORD = "nidhu";

    function checkPassword() {
      const entered = document.getElementById("passwordInput").value;
      if (entered === PASSWORD) {
        document.getElementById("lockScreen").style.display = "none";
        document.getElementById("page0").classList.add("active");
      } else {
        alert("Wrong password! Try again.");
      }
    }

    // Page Navigation
    function goToPage(n) {
      const pages = document.querySelectorAll('.page');
      pages.forEach(page => page.classList.remove('active'));
      document.getElementById('page' + n).classList.add('active');
    }

    // Countdown
    const anniversaryDate = new Date("2025-05-12T00:00:00");
    const countdownEl = document.getElementById("countdown");

    function updateCountdown() {
      const now = new Date();
      let diff = anniversaryDate - now;
      let prefix = "Time until our anniversary: ";

      if (diff < 0) {
        diff = now - anniversaryDate;
        prefix = "Time since our anniversary: ";
      }

      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const minutes = Math.floor((diff / (1000 * 60)) % 60);
      const seconds = Math.floor((diff / 1000) % 60);

      countdownEl.innerHTML = `${prefix} ${days}d ${hours}h ${minutes}m ${seconds}s`;
    }

    updateCountdown();
    setInterval(updateCountdown, 1000);

    // Image Upload with Local Storage
    function handleImageUpload(event) {
      const file = event.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function(e) {
          const img = document.createElement("img");
         
