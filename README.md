
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <meta name="theme-color" content="#e91e63" />
  <title>💖 Para Jhoryina Briyidth</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Montserrat:wght@300;500&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      touch-action: pan-y;
    }

    body {
      background: linear-gradient(135deg, #fff0f8, #fdd5e7, #fbbad6, #f9a0c5);
      color: #e91e63;
      font-family: 'Montserrat', sans-serif;
      overflow: hidden;
      height: 100vh;
      width: 100vw;
      position: fixed;
      perspective: 2000px;
      font-size: 14px;
    }

    /* === PANTALLA DE CARGA === */
    .loading {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, #fff0f8, #fdd5e7, #fbbad6, #f9a0c5);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      z-index: 9999;
      color: #d81b60;
      font-family: 'Playfair Display', serif;
      text-align: center;
      padding: 15px;
    }

    .loading h1 {
      font-size: clamp(1.6rem, 4.5vw, 2.2rem);
      margin-bottom: 8px;
      color: #e91e63;
      text-shadow: 0 0 8px rgba(255, 50, 100, 0.6);
      filter: saturate(1.3);
    }

    .loading h2 {
      font-size: clamp(1.4rem, 4vw, 1.9rem);
      margin-bottom: 12px;
      color: #c2185b;
      text-shadow: 0 0 6px rgba(255, 60, 120, 0.6);
    }

    .loading p {
      font-size: clamp(0.9rem, 3vw, 1.1rem);
      color: #e91e63;
      margin-bottom: 10px;
      font-style: italic;
    }

    .loading .subtitle {
      font-size: clamp(1rem, 3.2vw, 1.2rem);
      color: #9c27b0;
      margin: 8px 0 25px;
      font-weight: 500;
    }

    .loading .credits-small {
      position: absolute;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
      font-size: clamp(0.8rem, 2.8vw, 0.9rem);
      color: #c2185b;
      opacity: 0.8;
      text-align: center;
    }

    /* Menú en carga */
    .menu-toggle-loading {
      position: absolute;
      top: 15px;
      left: 15px;
      width: 35px;
      height: 26px;
      cursor: pointer;
      z-index: 2000;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      padding: 4px;
      border-radius: 8px;
      background: rgba(233, 30, 99, 0.3);
      box-shadow: 0 0 12px rgba(233, 30, 99, 0.5);
    }

    .bar-loading {
      height: 4px;
      background: #e91e63;
      border-radius: 2px;
      box-shadow: 0 0 6px rgba(255, 50, 100, 0.7);
    }

    /* Barra de corazón */
    .progress-container {
      position: relative;
      width: 75%;
      max-width: 350px;
      height: 140px;
      margin: 12px auto;
    }

    .heart-path {
      fill: none;
      stroke: #ff1744;
      stroke-width: 5;
      stroke-linecap: round;
      filter: drop-shadow(0 0 8px rgba(255, 50, 100, 0.6));
    }

    .progress-dot {
      position: absolute;
      width: 14px;
      height: 14px;
      background: #ff1744;
      border: 2px solid white;
      border-radius: 50%;
      transform: translate(-50%, -50%);
      box-shadow: 0 0 20px rgba(255, 50, 100, 0.9);
      z-index: 10;
    }

    .progress-percent {
      font-size: clamp(1.4rem, 4.5vw, 1.9rem);
      color: #d81b60;
      margin-top: 10px;
      font-weight: bold;
      text-shadow: 0 0 5px rgba(255, 110, 136, 0.5);
    }

    /* Corazones flotantes */
    .glow-heart {
      position: absolute;
      width: 14px;
      height: 14px;
      background: #ff1744;
      transform: rotate(45deg);
      border-radius: 2px;
      z-index: 100;
      animation: float linear infinite;
      filter: brightness(1.4) saturate(1.6);
      box-shadow: 0 0 10px rgba(255, 50, 100, 0.8);
    }

    .glow-heart::before,
    .glow-heart::after {
      content: '';
      position: absolute;
      width: 14px;
      height: 14px;
      background: #ff1744;
      border-radius: 50%;
      filter: brightness(1.5);
    }

    .glow-heart::before { left: -7px; top: 0; }
    .glow-heart::after { top: -7px; left: 0; }

    @keyframes float {
      0% { transform: rotate(45deg) translateX(0) translateY(0); opacity: 0.6; }
      50% { transform: rotate(45deg) translateX(15px) translateY(-12px); opacity: 1; }
      100% { transform: rotate(45deg) translateX(0) translateY(0); opacity: 0.6; }
    }

    /* Chispas */
    .sparkle-big {
      width: 6px;
      height: 6px;
      box-shadow: 0 0 15px rgba(255, 255, 255, 0.9);
    }

    .sparkle-small {
      width: 3.5px;
      height: 3.5px;
      box-shadow: 0 0 8px rgba(255, 255, 255, 0.8);
    }

    /* === UNIVERSO 3D === */
    #universe {
      position: absolute;
      width: 100%;
      height: 100%;
      transform-style: preserve-3d;
      transform: rotateX(10deg) rotateY(0deg);
      transition: transform 0.1s ease;
      opacity: 0;
      pointer-events: none;
      z-index: 1;
    }

    #universe.active {
      opacity: 1;
      pointer-events: all;
    }

    /* Lluvia DETRÁS de la carta */
    .rain-back {
      position: absolute;
      width: 100%;
      height: 150vh;
      pointer-events: none;
      z-index: 1;
    }

    /* Lluvia DELANTE de la carta */
    .rain-front {
      position: absolute;
      width: 100%;
      height: 150vh;
      pointer-events: none;
      z-index: 4;
    }

    /* Texto cayendo */
    .char {
      position: absolute;
      font-family: 'Playfair Display', serif;
      white-space: pre;
      opacity: 0.85;
      animation: fall linear infinite;
      text-shadow: 0 0 3px rgba(255, 50, 120, 0.5);
      letter-spacing: 0.3px;
      filter: saturate(1.2);
    }

    @keyframes fall {
      0% { transform: translateY(-80px); opacity: 0; }
      10% { opacity: 1; }
      100% { transform: translateY(110vh); opacity: 0; }
    }

    .char.small { font-size: clamp(0.8rem, 3vw, 1rem); }
    .char.medium { font-size: clamp(1rem, 3.5vw, 1.2rem); }
    .char.large { font-size: clamp(1.1rem, 4vw, 1.4rem); }

    .char span {
      display: inline-block;
      color: transparent;
    }

    /* Paleta de colores */
    .char span:nth-child(1)  { color: #ff1744; }
    .char span:nth-child(2)  { color: #f50057; }
    .char span:nth-child(3)  { color: #e040fb; }
    .char span:nth-child(4)  { color: #d500f9; }
    .char span:nth-child(5)  { color: #aa00ff; }
    .char span:nth-child(6)  { color: #7c4dff; }
    .char span:nth-child(7)  { color: #536dfe; }
    .char span:nth-child(8)  { color: #448aff; }
    .char span:nth-child(9)  { color: #40c4ff; }
    .char span:nth-child(10) { color: #69f0ae; }
    .char span:nth-child(11) { color: #b2ff59; }
    .char span:nth-child(12) { color: #ffee58; }
    .char span:nth-child(13) { color: #ffca28; }
    .char span:nth-child(14) { color: #ff8a65; }
    .char span:nth-child(15) { color: #ffffff; }

    /* === CARTA BRILLANTE CON BORDES REDONDEADOS === */
    .floating-card {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) translateZ(100px);
      width: 85%;
      max-width: 500px;
      min-height: 240px;
      background: rgba(255, 255, 255, 0.25);
      backdrop-filter: blur(10px);
      border-radius: 24px; /* esquinas redondeadas */
      padding: 22px 20px;
      box-shadow: 
        0 0 20px rgba(233, 30, 99, 0.2),
        0 0 30px rgba(255, 100, 180, 0.15) inset;
      border: 2px solid rgba(233, 30, 99, 0.4);
      /* Borde brillante */
      outline: 2px solid rgba(233, 30, 99, 0.3);
      outline-offset: 2px;
      color: #c2185b;
      text-align: center;
      font-family: 'Montserrat', sans-serif;
      line-height: 1.6;
      z-index: 3;
      font-size: 0.95em;
      overflow: hidden;
    }

    /* Efecto de brillo interno */
    .floating-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: linear-gradient(45deg, 
        rgba(255, 180, 200, 0.1), 
        rgba(255, 100, 180, 0.05), 
        transparent);
      pointer-events: none;
      border-radius: 22px;
      z-index: -1;
    }

    .floating-card h2 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(1.4rem, 4.5vw, 1.8rem);
      color: #d81b60;
      margin-bottom: 12px;
      text-shadow: 0 0 4px rgba(255, 110, 136, 0.4);
    }

    .floating-card p {
      font-size: clamp(0.9rem, 3.2vw, 1rem);
      color: #880e4f;
      margin-bottom: 10px;
    }

    /* Menús */
    .menu-toggle {
      position: absolute;
      width: 35px;
      height: 26px;
      cursor: pointer;
      z-index: 20;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      padding: 4px;
      border-radius: 8px;
      background: rgba(233, 30, 99, 0.25);
      box-shadow: 0 0 10px rgba(233, 30, 99, 0.4);
      opacity: 0;
      transition: opacity 0.5s ease;
    }

    .bar {
      height: 4px;
      background: #e91e63;
      border-radius: 2px;
      box-shadow: 0 0 5px rgba(255, 50, 100, 0.6);
    }

    #menuTopLeft { top: 15px; left: 15px; transform: translateZ(50px); }
    #menuTopRight { top: 15px; right: 15px; transform: translateZ(50px); }
    #menuBottomLeft { bottom: 15px; left: 15px; transform: translateZ(50px); }
    #menuBottomRight { bottom: 15px; right: 15px; transform: translateZ(50px); }

    /* Menú desplegable */
    .menu {
      position: fixed;
      top: 0;
      right: -100%;
      width: 75%;
      max-width: 300px;
      height: 100vh;
      background: rgba(255, 255, 255, 0.95);
      backdrop-filter: blur(8px);
      box-shadow: -4px 0 20px rgba(0, 0, 0, 0.1);
      transform: translateZ(70px);
      transition: right 0.4s ease;
      z-index: 100;
      padding: 70px 15px 15px;
      border-radius: 18px 0 0 18px;
    }

    .menu.open {
      right: 0;
    }

    .menu-item {
      margin: 15px 0;
      font-size: clamp(0.9rem, 3.5vw, 1.1rem);
      color: #d81b60;
      text-decoration: none;
      display: block;
      text-align: center;
      padding: 10px;
      border-radius: 10px;
      background: rgba(233, 30, 99, 0.1);
      transition: 0.3s;
    }

    .menu-item:hover {
      background: rgba(233, 30, 99, 0.2);
      transform: scale(1.05);
    }

    /* Créditos */
    .credits {
      position: absolute;
      bottom: 15px;
      left: 50%;
      transform: translateX(-50%) translateZ(50px);
      font-size: clamp(0.8rem, 3vw, 0.95rem);
      color: #9c27b0;
      text-shadow: 0 0 4px rgba(255, 110, 136, 0.3);
      z-index: 10;
      text-align: center;
    }
  </style>
</head>
<body>

  <!-- === PANTALLA DE CARGA === -->
  <div class="loading" id="loader">
    
    <!-- Menú en carga -->
    <div class="menu-toggle-loading" id="menuTopLeftLoading">
      <div class="bar-loading"></div>
      <div class="bar-loading"></div>
      <div class="bar-loading"></div>
    </div>

    <h1>Para Jhoryina Briyidth 💖</h1>
    <h2>💗 Cargando tu universo de amor</h2>
    <p>Un detalle hecho con el corazón</p>
    <div class="subtitle">De parte de: AnthZz Berrocal</div>

    <div class="progress-container">
      <svg width="350" height="140" viewBox="0 0 350 140" xmlns="http://www.w3.org/2000/svg">
        <path class="heart-path" d="M175,140 C130,110 60,90 20,50 C0,20 15,0 50,0 C85,0 110,25 135,50 C155,30 185,30 205,50 C235,25 260,0 295,0 C335,0 350,20 310,50 C260,90 190,110 175,140 Z" />
      </svg>
      <div class="progress-dot" id="dot"></div>
    </div>

    <div class="progress-percent" id="percent">0%</div>

    <div class="credits-small">
      Desarrollado por: AnthZz Berrocal | BerMatMods
    </div>
  </div>

  <!-- === UNIVERSO 3D === -->
  <div id="universe">
    
    <!-- Lluvia detrás de la carta -->
    <div class="rain-back" id="rainBack"></div>

    <!-- Lluvia delante de la carta -->
    <div class="rain-front" id="rainFront"></div>

    <!-- === CARTA BRILLANTE CON BORDES REDONDEADOS === -->
    <div class="floating-card">
      <h2>Para mi Amor, Jhoryina 💖</h2>
      <p>Te amo con todo mi corazón, más de lo que las palabras pueden expresar.</p>
      <p>Eres especial, hermosa, y cada día contigo es un regalo que guardo en el alma.</p>
      <p>Sin darte cuenta, llenas mis días de luz y mi corazón de paz.</p>
      <p>Jhoryina, te amo más que a la vida misma.</p>
    </div>

    <!-- 4 Menús -->
    <div class="menu-toggle" id="menuTopLeft">
      <div class="bar"></div>
      <div class="bar"></div>
      <div class="bar"></div>
    </div>
    <div class="menu-toggle" id="menuTopRight">
      <div class="bar"></div>
      <div class="bar"></div>
      <div class="bar"></div>
    </div>
    <div class="menu-toggle" id="menuBottomLeft">
      <div class="bar"></div>
      <div class="bar"></div>
      <div class="bar"></div>
    </div>
    <div class="menu-toggle" id="menuBottomRight">
      <div class="bar"></div>
      <div class="bar"></div>
      <div class="bar"></div>
    </div>

    <!-- Menú desplegable -->
    <div class="menu" id="menu">
      <a href="https://wa.me/51937556459?text=Hola%20AnthZz,%20vi%20tu%20detalle%20romántico%20y%20me%20encantaría%20personalizar%20uno%20para%20mi%20pareja" class="menu-item" target="_blank">
        💬 Contactar por WhatsApp
      </a>
      <div class="menu-item" onclick="alert('Gracias por ver este detalle hecho con amor. Puedes contactar a AnthZz Berrocal - BerMatMods para crear el tuyo.')">
        ℹ️ Más información
      </div>
    </div>

    <!-- Créditos -->
    <div class="credits">
      By AnthZz Berrocal - BerMatMods
    </div>
  </div>

  <script>
    // === CARGA ===
    const loader = document.getElementById('loader');
    const dot = document.getElementById('dot');
    const percent = document.getElementById('percent');
    const path = document.querySelector('.heart-path');
    const length = path.getTotalLength();
    const heartPoints = [];

    for (let i = 0; i <= 100; i++) {
      const point = path.getPointAtLength((i / 100) * length);
      heartPoints.push({ x: point.x, y: point.y });
    }

    let progress = 0;
    const interval = setInterval(() => {
      progress++;
      percent.textContent = `${progress}%`;
      if (heartPoints[progress]) {
        dot.style.left = `${heartPoints[progress].x}px`;
        dot.style.top = `${heartPoints[progress].y}px`;
      }
      if (progress === 100) {
        clearInterval(interval);
        setTimeout(() => {
          loader.style.opacity = '0';
          setTimeout(() => loader.style.display = 'none', 500);
          document.getElementById('universe').classList.add('active');
        }, 600);
      }
    }, 60);

    // === CORAZONES FLotantes ===
    for (let i = 0; i < 18; i++) {
      const heart = document.createElement('div');
      heart.className = 'glow-heart';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.top = Math.random() * 100 + 'vh';
      heart.style.animationDuration = (2.5 + Math.random() * 2.5) + 's';
      heart.style.animationDelay = Math.random() * 5 + 's';
      loader.appendChild(heart);
    }

    // === EXPLOSIONES ===
    function createExplosion() {
      const x = Math.random() * 100;
      const y = Math.random() * 100;
      for (let i = 0; i < 10; i++) {
        const big = document.createElement('div');
        big.className = 'sparkle-big';
        big.style.left = x + '%';
        big.style.top = y + '%';
        loader.appendChild(big);
        setTimeout(() => big.remove(), 1600);

        for (let j = 0; j < 6; j++) {
          const small = document.createElement('div');
          small.className = 'sparkle-small';
          small.style.left = x + '%';
          small.style.top = y + '%';
          const angle = Math.random() * 360;
          const dist = 40 + Math.random() * 80;
          const dx = Math.cos(angle * Math.PI / 180) * dist;
          const dy = Math.sin(angle * Math.PI / 180) * dist;
          small.style.setProperty('--dx', dx + 'px');
          small.style.setProperty('--dy', dy + 'px');
          small.style.setProperty('--rot', (Math.random() * 360) + 'deg');
          small.style.animationDuration = (1.5 + Math.random() * 0.8) + 's';
          loader.appendChild(small);
          setTimeout(() => small.remove(), 1800);
        }
      }
    }

    setInterval(createExplosion, 1000);
    setTimeout(createExplosion, 400);

    // === LLUVIA DE TEXTO (más densa) ===
    const romanticLines = [
      "Te amo con cada latido",
      "Eres mi persona especial",
      "Cada día contigo es un milagro",
      "Tu sonrisa ilumina mi mundo",
      "Eres hermosa por dentro",
      "Mi amor no tiene límites",
      "Gracias por ser mi paz",
      "Contigo me siento en casa",
      "Eres mi razón para sonreír",
      "Te amo más de lo que imaginas",
      "Eres única, como ninguna otra",
      "Mi vida cambió cuando llegaste",
      "Eres mi eternidad",
      "Te amo más que a la vida misma",
      "Eres mi amor, mi amiga, mi todo"
    ];

    function createStyledText(text) {
      return text.split('').map(char => {
        const span = document.createElement('span');
        span.textContent = char;
        return span.outerHTML;
      }).join('');
    }

    const rainBack = document.getElementById('rainBack');
    const rainFront = document.getElementById('rainFront');

    const createRainDrop = (container, isFront = false) => {
      const char = document.createElement('div');
      char.className = `char ${['small', 'medium', 'large'][Math.floor(Math.random() * 3)]}`;
      const randomLine = romanticLines[Math.floor(Math.random() * romanticLines.length)];
      char.innerHTML = createStyledText(randomLine);
      char.style.left = Math.random() * 95 + '%';
      char.style.opacity = isFront ? 0.6 : 0.85;
      char.style.animationDuration = (Math.random() * 6 + 5) + 's';
      container.appendChild(char);
      setTimeout(() => char.remove(), 7000);
    };

    // Más densidad = más lluvia
    setInterval(() => createRainDrop(rainBack), 120);
    setInterval(() => createRainDrop(rainFront, true), 120);

    // === MENÚS ===
    const menus = [
      document.getElementById('menuTopLeft'),
      document.getElementById('menuTopRight'),
      document.getElementById('menuBottomLeft'),
      document.getElementById('menuBottomRight')
    ];

    const openMenu = () => document.getElementById('menu').classList.toggle('open');
    document.getElementById('menuTopLeftLoading').addEventListener('click', openMenu);
    menus.forEach(menu => menu.addEventListener('click', openMenu));

    document.addEventListener('click', (e) => {
      const menu = document.getElementById('menu');
      if (!menu.contains(e.target) && !menus.some(m => m.contains(e.target)) && !document.getElementById('menuTopLeftLoading').contains(e.target)) {
        menu.classList.remove('open');
      }
    });

    // === ROTACIÓN 3D ===
    let rotX = 10, rotY = 0;
    let isDragging = false;
    let startX, startY;

    const handleMove = (dx, dy) => {
      if (isDragging) {
        rotY += dx * 0.5;
        rotX -= dy * 0.5;
        document.getElementById('universe').style.transform = `rotateX(${rotX}deg) rotateY(${rotY}deg)`;
      }
    };

    document.addEventListener('mousedown', (e) => {
      isDragging = true;
      startX = e.clientX;
      startY = e.clientY;
    });

    document.addEventListener('mousemove', (e) => {
      if (isDragging) handleMove(e.clientX - startX, e.clientY - startY);
    });

    document.addEventListener('mouseup', () => isDragging = false);

    document.addEventListener('touchstart', (e) => {
      isDragging = true;
      startX = e.touches[0].clientX;
      startY = e.touches[0].clientY;
    }, { passive: false });

    document.addEventListener('touchmove', (e) => {
      if (isDragging) {
        const dx = e.touches[0].clientX - startX;
        const dy = e.touches[0].clientY - startY;
        handleMove(dx, dy);
        startX = e.touches[0].clientX;
        startY = e.touches[0].clientY;
      }
    }, { passive: false });

    document.addEventListener('touchend', () => isDragging = false);
  </script>
</body>
</html>
