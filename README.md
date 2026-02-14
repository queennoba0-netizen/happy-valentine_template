# happy-valentine_template[Index.html](https://github.com/user-attachments/files/25310739/Index.html)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Valentine Adventure</title>
  <style>
    body {
      background: linear-gradient(to bottom, pink, lavender);
      font-family: 'Comic Sans MS', cursive;
      text-align: center;
      overflow: hidden;
    }
    section { display: none; padding: 40px; }
    section.active { display: block; }
    h1, h2 { color: crimson; }
    button {
      margin-top: 20px;
      font-size: 1.2em;
      padding: 10px 20px;
      border: none;
      border-radius: 10px;
      background: hotpink;
      color: white;
      cursor: pointer;
      transition: transform 0.3s;
    }
    button:hover { transform: scale(1.1); }

    /* Heartbeat animation */
    .heartbeat {
      animation: heartbeat 1.5s infinite;
    }
    @keyframes heartbeat {
      0%{transform:scale(1);}25%{transform:scale(1.2);}
      50%{transform:scale(1);}75%{transform:scale(1.2);}
      100%{transform:scale(1);}
    }

    /* Floating hearts */
    .heart {
      position: absolute;
      color: red;
      font-size: 2em;
      animation: floatUp 6s linear infinite;
    }
    @keyframes floatUp {
      0%{transform:translateY(100vh);opacity:1;}
      100%{transform:translateY(-10vh);opacity:0;}
    }

    /* Love meter */
    #meter { width: 300px; height: 30px; border: 2px solid red; margin: 20px auto; }
    #fill { height: 100%; width: 0; background: red; }
  </style>
</head>
<body>
  <!-- Page 1 -->
  <section id="page1" class="active">
    <h1 class="heartbeat">Will you be my Valentine???</h1>
    <button onclick="nextPage(2)">💐 Continue</button>
  </section>

  <!-- Page 2 -->
  <section id="page2">
    <h2>Here’s a bouquet for you 💐</h2>
    <button onclick="showBouquet()">Click me!</button>
    <p id="bouquetText"></p>
    <button onclick="nextPage(3)">💍 Next</button>
  </section>

  <!-- Page 3 -->
  <section id="page3">
    <h2>💍 A ring with your initial: <span style="color:red;font-weight:bold;">[A]</span></h2>
    <button onclick="showRing()">Click the ring</button>
    <p id="ringText"></p>
    <button onclick="nextPage(4)">❤️ Next</button>
  </section>

  <!-- Page 4 -->
  <section id="page4">
    <h2>Fill the Love Meter ❤️</h2>
    <div id="meter"><div id="fill"></div></div>
    <button onclick="fillMeter()">Click to add love</button>
    <button onclick="nextPage(5)">🎆 Final</button>
  </section>

  <!-- Page 5 -->
  <section id="page5">
    <h1>🎆 Happy Valentine’s Day 🎆</h1>
    <p>You are my forever Valentine 💖</p>
    <div id="fireworks">💖💘💕💞💓💝💟</div>
  </section>

  <script>
    // Page navigation
    function nextPage(n) {
      document.querySelectorAll('section').forEach(sec => sec.classList.remove('active'));
      document.getElementById('page'+n).classList.add('active');
    }

    // Bouquet interaction
    function showBouquet() {
      document.getElementById('bouquetText').textContent = "🌹🌹🌹 A shower of roses!";
    }

    // Ring interaction
    function showRing() {
      document.getElementById('ringText').textContent = "💖 Forever yours 💖";
    }

    // Love meter
    let width=0;
    function fillMeter() {
      if(width<300){ width+=60; document.getElementById('fill').style.width=width+'px'; }
    }

    // Floating hearts
    function createHeart(){
      const heart=document.createElement('div');
      heart.className='heart';
      heart.textContent='❤️';
      heart.style.left=Math.random()*window.innerWidth+'px';
      document.body.appendChild(heart);
      setTimeout(()=>heart.remove(),6000);
    }
    setInterval(createHeart,800);
  </script>
</body>
</html>
<p> I FOREVER LOVE YOU DEAR ADOR U ARE FOREVER MINE AND LETS HOPE WE CAN CELEBRATE EVERY VALENTINES TOGETHER < 3 </p>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Teddy Bear in HTML & CSS</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #fce4ec;
    }
    .bear {
      position: relative;
      width: 200px;
      height: 200px;
      background: #8d6e63;
      border-radius: 50%;
    }
    /* ears */
    .ear {
      position: absolute;
      width: 70px;
      height: 70px;
      background: #8d6e63;
      border-radius: 50%;
      top: -30px;
    }
    .ear.left { left: -30px; }
    .ear.right { right: -30px; }
    /* inner ears */
    .ear::after {
      content: "";
      position: absolute;
      width: 40px;
      height: 40px;
      background: #a1887f;
      border-radius: 50%;
      top: 15px;
      left: 15px;
    }
    /* eyes */
    .eye {
      position: absolute;
      width: 20px;
      height: 20px;
      background: black;
      border-radius: 50%;
      top: 70px;
    }
    .eye.left { left: 50px; }
    .eye.right { right: 50px; }
    /* muzzle */
    .muzzle {
      position: absolute;
      width: 100px;
      height: 70px;
      background: #a1887f;
      border-radius: 50%;
      bottom: 40px;
      left: 50%;
      transform: translateX(-50%);
    }
    /* nose */
    .nose {
      position: absolute;
      width: 20px;
      height: 15px;
      background: black;
      border-radius: 50%;
      top: 20px;
      left: 50%;
      transform: translateX(-50%);
    }
    /* mouth */
    .mouth {
      position: absolute;
      width: 40px;
      height: 20px;
      border-bottom: 3px solid black;
      border-radius: 50%;
      bottom: 10px;
      left: 50%;
      transform: translateX(-50%);
    }
  </style>
</head>
<body>
  <div class="bear">
    <div class="ear left"></div>
    <div class="ear right"></div>
    <div class="eye left"></div>
    <div class="eye right"></div>
    <div class="muzzle">
      <div class="nose"></div>
      <div class="mouth"></div>
    </div>
  </div>
</body>
</html>
