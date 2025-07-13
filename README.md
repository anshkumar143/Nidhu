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
      animation: fadeIn 0.6s ease-in-out;
    }

    @keyframes fadeIn {
      from {opacity: 0;}
      to {opacity: 1;}
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
      margin: 20px 0;
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

    .cover {
      background: linear-gradient(to bottom right, #fff0f5, #ffe6eb);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      height: 100vh;
    }

    .cover h1 {
      font-size: 4em;
      color: #e91e63;
      text-shadow: 0 2px 4px rgba(0,0,0,0.2);
    }

    .cover button {
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

    .cover button:hover {
      background: #e75376;
    }

    #countdown {
      font-size: 1.2em;
      color: #c2185b;
      margin-top: 20px;
    }

    #imagePreview img,
    #multiImagePreview img {
      max-width: 100%;
      margin-top: 20px;
      border-radius: 10px;
    }

    #multiImagePreview img {
      max-width: 48%;
      margin: 1%;
      display: inline-block;
    }

    #passwordPage {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #ffe9f0;
    }

    #passwordPage input {
      padding: 12px 20px;
      font-size: 1em;
      margin-top: 20px;
      border-radius: 20px;
      border: 1px solid #e91e63;
      outline: none;
    }

    #passwordPage button {
      margin-top: 20px;
      padding: 10px 25px;
      font-size: 1em;
      background-color: #e91e63;
      color: white;
      border: none;
      border-radius: 20px;
      cursor: pointer;
    }

    audio {
      display: none;
    }
  </style>
</head>
<body>

  <!-- Password Page -->
  <div id="passwordPage">
    <h1>Enter Password to Open Diary 🔐</h1>
    <input type="password" id="passwordInput" placeholder="Enter password...">
    <button onclick="checkPassword()">Unlock</button>
  </div>

  <!-- Cover Page -->
  <div class="page cover" id="page0">
    <h1>Nidhi’s Love Diary 💖</h1>
    <p>A collection of love, apologies, and endless affection...</p>
    <div id="countdown">Loading countdown...</div>
    <button onclick="goToPage(1)">Open Diary 📖</button>
  </div>

  <!-- Letter 1 -->
  <div class="page" id="page1">
    <h2>Letter 1: From My Heart to Yours</h2>
    <p>Dearest Nidhi Princess,</p>
    <p>
      I don’t know where to begin, because no words can truly capture how much you mean to me. Every moment with you is like a dream I never want to wake up from. You’ve filled my life with joy, light, and a kind of love I never knew was possible.
    </p>
    <p>
      Your smile brightens my darkest days, and your voice is my favorite melody. I’m sorry for anything I’ve done to hurt you — it was never my intention. You deserve to be treated like the queen you are, my sweet Nidhi Princess.
    </p>
    <div class="signature">Forever Yours,<br>Your Love 💌</div>
    <div class="nav">
      <button onclick="goToPage(0)">← Back</button>
      <button onclick="goToPage(2)">Next →</button>
    </div>
  </div>

  <!-- Photo Page (single image) -->
  <div class="page" id="page2">
    <h2>Special Memories 📸</h2>
    <p>Select a photo to add to our diary:</p>
    <input type="file" accept="image/*" onchange="previewImage(event)">
    <div id="imagePreview"></div>
    <div class="nav">
      <button onclick="goToPage(1)">← Back</button>
      <button onclick="goToPage(4)">Next →</button>
    </div>
  </div>

  <!-- Multi-photo upload page -->
  <div class="page" id="page4">
    <h2>More Memories Together 📷</h2>
    <p>Upload multiple pictures to add more love to our diary:</p>
    <input type="file" accept="image/*" multiple onchange="previewMultipleImages(event)">
    <div id="multiImagePreview"></div>
    <div class="nav">
      <button onclick="goToPage(2)">← Back</button>
      <button onclick="goToPage(3)">Next →</button>
    </div>
  </div>

  <!-- Final Letter -->
  <div class="page" id="page3">
    <h2>Thank You, My Lucky Charm ✨</h2>
    <p>
      Thku soooo much, my lucky charm, meri life mein aane ke liye. You’ve brought color, laughter, passion, and love. I never thought someone could make me feel so complete.
    </p>
    <p style="font-size: 1.4em; text-align: center; color: #e91e63;"><strong>I love you sooo much ❤️</strong></p>
    <div class="signature">Yours always,<br>💖</div>
    <div class="nav">
      <button onclick="goToPage(4)">← Back</button>
    </div>
  </div>

  <!-- Background Music -->
  <audio autoplay loop>
    <source src="https://www.bensound.com/bensound-music/bensound-love.mp3" type="audio/mpeg">
  </audio>

  <script>
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

    // Keep photo saved using localStorage
    window.onload = function() {
      const savedImage = localStorage.getItem("savedImage");
      if (savedImage) {
        document.getElementById('imagePreview').innerHTML = `<img src="${savedImage}" alt="Saved image">`;
      }
    };

    function previewImage(event) {
      const reader = new FileReader();
      reader.onload = function () {
        const imageUrl = reader.result;
        const output = document.getElementById('imagePreview');
        output.innerHTML = `<img src="${imageUrl}" alt="Uploaded image">`;
        localStorage.setItem("savedImage", imageUrl);
      };
      reader.readAsDataURL(event.target.files[0]);
    }
  </script>

  </script>
</body>
</html>
