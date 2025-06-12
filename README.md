<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Happy Birthday, Princess Billuni</title>
  <style>
    html {
      scroll-behavior: smooth;
    }
    body {
      margin: 0;
      padding: 0;
      font-family: 'Georgia', serif;
      background: linear-gradient(to bottom, #000000 0%, #1a1a1a 20%, #2e2e2e 40%, #555555 60%, #888888 80%, #f0f0f0 100%);
      background-attachment: fixed;
      background-size: cover;
      color: #ffffff;
      overflow-x: hidden;
    }
    section {
      min-height: 100vh;
      padding: 60px 30px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      position: relative;
      z-index: 1;
      opacity: 0;
      transform: translateY(50px);
      animation: fadeInUp 1.2s ease-out forwards;
    }
    section:nth-child(even) {
      animation-delay: 0.4s;
    }
    section:nth-child(odd) {
      animation-delay: 0.8s;
    }
    @keyframes fadeInUp {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    h1, h2 {
      font-weight: normal;
    }
    .quote {
      font-style: italic;
      opacity: 0.8;
    }
    .line {
      margin: 40px 0;
      font-size: 1.1rem;
    }
    .intersection {
      font-size: 0.95rem;
      opacity: 0.6;
      margin: 20px 0;
      font-style: italic;
    }
    .petal {
      position: fixed;
      top: -10px;
      width: 20px;
      height: 20px;
      background: white;
      border-radius: 50%;
      opacity: 0.5;
      animation: fall linear infinite;
      z-index: 0;
    }
    @keyframes fall {
      to {
        transform: translateY(110vh) rotate(360deg);
        opacity: 0;
      }
    }
    .moon {
      width: 100px;
      height: 100px;
      background: radial-gradient(circle, #cccccc 40%, #999999 60%, #666666 80%, #333333 100%);
      border-radius: 50%;
      position: absolute;
      animation: glow 3s ease-in-out infinite alternate;
      opacity: 1;
      top: 20px;
      left: 50%;
      transform: translateX(-50%);
      box-shadow: 0 0 25px #ffffff88;
    }
    @keyframes glow {
      0% {
        transform: translateX(-50%) scale(1);
        box-shadow: 0 0 15px #ffffff22;
      }
      100% {
        transform: translateX(-50%) scale(1.03);
        box-shadow: 0 0 25px #ffffff88;
      }
    }
    .popup {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) scale(0);
      background: white;
      color: black;
      padding: 20px 30px;
      border-radius: 20px;
      font-size: 1.5rem;
      z-index: 1000;
      opacity: 0;
      animation: popupAnim 0.5s forwards;
    }
    @keyframes popupAnim {
      to {
        transform: translate(-50%, -50%) scale(1);
        opacity: 1;
      }
    }
    .ripple {
      position: absolute;
      width: 100px;
      height: 100px;
      border-radius: 50%;
      background: radial-gradient(white, transparent);
      animation: rippleFade 1s ease-out;
      pointer-events: none;
      transform: translate(-50%, -50%);
    }
    @keyframes rippleFade {
      from { opacity: 0.6; transform: scale(0); }
      to { opacity: 0; transform: scale(2); }
    }
    .starfield {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: transparent;
      z-index: 0;
      pointer-events: none;
    }
    .star {
      position: absolute;
      width: 2px;
      height: 2px;
      background: white;
      border-radius: 50%;
      animation: twinkle 2s infinite ease-in-out;
    }
    @keyframes twinkle {
      0%, 100% { opacity: 0.3; }
      50% { opacity: 1; }
    }
  </style>
</head>
<body onclick="showPopup(event)">
  <div class="starfield" id="starfield"></div>
  <div class="moon"></div>

  <section>
    <h1>Happy Birthday, Billuni 🎂</h1>
    <p class="quote">
      "Nice to meet you. I don't have fancy lines to impress you,<br>
      but I will say this — you're wonderful. Sharp, calm, and quite the pro at COD."
    </p>
  </section>

  <section>
    <h2>From Me, With Quiet Wonder</h2>
    <p class="line">
      In an era of strangers, you echoed warmth—<br>
      not loud, not boastful,<br>
      but like a breeze that leaves a scent behind.
    </p>
    <div class="intersection">—Some silences linger longer than echoes—</div>
    <p class="line">
      Had we never logged into that little chatroom,<br>
      who knows what would have happened?<br>
      But paths did cross — and that mattered.
    </p>
  </section>

  <section>
    <h2>Do You Remember?</h2>
    <p class="line">
      I once said I know how every story ends.<br>
      So before any twist appears, let me pause<br>
      and wish you a joyful 20th birthday.
    </p>
    <div class="intersection">—A pause so small, yet the stars noticed—</div>
    <p class="line">
      Perhaps some questions aren’t just questions —<br>
      they’re little codes waiting to be cracked.
    </p>
  </section>

  <section>
    <h2>Last Note</h2>
    <p class="line">
      I leave you with one small piece of advice:<br>
      Don’t overthink the future, nor carry the past.<br>
      Be present. That is where life quietly glows.
    </p>
    <div class="intersection">—And sometimes, color arrives in grayscale—</div>
    <p class="line">
      Stay radiant, Mahi. 🌑
    </p>
    <p class="intersection">
      And yes, that line you once said — "I know the ending too" — still lingers in my curiosity.
    </p>
    <p class="line">
      HAPPY BIRTHDAY, MAHI.
    </p>
  </section>

  <script>
    const petalCount = 30;
    for (let i = 0; i < petalCount; i++) {
      let petal = document.createElement('div');
      petal.className = 'petal';
      petal.style.left = Math.random() * 100 + 'vw';
      petal.style.animationDuration = (Math.random() * 5 + 5) + 's';
      petal.style.animationDelay = (Math.random() * 5) + 's';
      document.body.appendChild(petal);
    }

    const starCount = 100;
    for (let i = 0; i < starCount; i++) {
      const star = document.createElement('div');
      star.className = 'star';
      star.style.top = Math.random() * 100 + '%';
      star.style.left = Math.random() * 100 + '%';
      star.style.animationDelay = Math.random() * 2 + 's';
      document.getElementById('starfield').appendChild(star);
    }

    document.body.addEventListener('click', function (e) {
      const ripple = document.createElement('div');
      ripple.className = 'ripple';
      ripple.style.left = `${e.clientX}px`;
      ripple.style.top = `${e.clientY}px`;
      document.body.appendChild(ripple);
      setTimeout(() => ripple.remove(), 1000);
    });

    function showPopup(event) {
      const popup = document.createElement('div');
      popup.className = 'popup';
      popup.innerText = 'Happy Birthday 🎉';
      document.body.appendChild(popup);
      setTimeout(() => popup.remove(), 1500);
    }
  </script>
</body>
</html>
