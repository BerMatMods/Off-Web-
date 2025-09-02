
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <meta name="theme-color" content="#e91e63" />
  <title>💖 Para Jhoryina Briyidth - Con Amor de AnthZz</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Montserrat:wght@300;500&display=swap" rel="stylesheet">
  <style>
    /* Reset y base */
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
      perspective: 3000px;
      -webkit-tap-highlight-color: transparent;
      font-size: 16px;
    }

    /* === PANTALLA DE CARGA === */
    .loading {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, 
        #fff0f8, 
        #fdd5e7, 
        #fbbad6, 
        #f9a0c5);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      z-index: 9999;
      color: #d81b60;
      font-family: 'Playfair Display', serif;
      text-align: center;
      padding: 20px;
    }

    .loading h1 {
      font-size: clamp(2rem, 5vw, 2.8rem);
      margin-bottom: 10px;
      color: #e91e63;
      text-shadow: 0 0 10px rgba(255, 50, 100, 0.7);
      filter: saturate(1.3) brightness(1.1);
    }

    .loading h2 {
      font-size: clamp(1.8rem, 4.5vw, 2.4rem);
      margin-bottom: 15px;
      color: #c2185b;
      text-shadow: 0 0 8px rgba(255, 60, 120, 0.7);
      filter: saturate(1.25);
    }

    .loading p {
      font-size: clamp(1.1rem, 3.5vw, 1.3rem);
      color: #e91e63;
      margin-bottom: 15px;
      font-style: italic;
      filter: saturate(1.2);
    }

    .loading .subtitle {
      font-size: clamp(1.2rem, 4vw, 1.4rem);
      color: #9c27b0;
      margin: 10px 0 30px;
      font-weight: 500;
      filter: saturate(1.3);
    }

    .loading .credits-small {
      position: absolute;
      bottom: 25px;
      left: 50%;
      transform: translateX(-50%);
      font-family: 'Montserrat', sans-serif;
      font-size: clamp(0.9rem, 3vw, 1rem);
      color: #c2185b;
      opacity: 0.8;
      text-align: center;
      filter: saturate(1.2);
    }

    /* Menú en carga */
    .menu-toggle-loading {
      position: absolute;
      top: 20px;
      left: 20px;
      width: 40px;
      height: 30px;
      cursor: pointer;
      z-index: 2000;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      padding: 5px;
      border-radius: 10px;
      background: rgba(233, 30, 99, 0.3);
      box-shadow: 0 0 15px rgba(233, 30, 99, 0.6);
    }

    .bar-loading {
      height: 5px;
      background: #e91e63;
      border-radius: 3px;
      box-shadow: 0 0 8px rgba(255, 50, 100, 0.8);
    }

    /* Barra de corazón */
    .progress-container {
      position: relative;
      width: 80%;
      max-width: 400px;
      height: 200px;
      margin: 15px auto;
    }

    .heart-path {
      fill: none;
      stroke: #ff1744;
      stroke-width: 6;
      stroke-linecap: round;
      filter: drop-shadow(0 0 10px rgba(255, 50, 100, 0.7));
    }

    .progress-dot {
      position: absolute;
      width: 18px;
      height: 18px;
      background: #ff1744;
      border: 3px solid white;
      border-radius: 50%;
      transform: translate(-50%, -50%);
      box-shadow: 0 0 25px rgba(255, 50, 100, 1), 0 0 10px white;
      z-index: 10;
    }

    .progress-percent {
      font-size: clamp(1.8rem, 5vw, 2.4rem);
      color: #d81b60;
      margin-top: 15px;
      font-weight: bold;
      text-shadow: 0 0 6px rgba(255, 110, 136, 0.6);
      filter: saturate(1.3) brightness(1.1);
    }

    /* === CORAZONES BRILLANTES FLotantes === */
    .glow-heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: #ff1744;
      transform: rotate(45deg);
      border-radius: 3px;
      z-index: 100;
      animation: float linear infinite;
      filter: brightness(1.4) saturate(1.6);
      box-shadow: 
        0 0 12px rgba(255, 50, 100, 0.9),
        0 0 25px rgba(255, 80, 130, 0.7),
        0 0 40px rgba(255, 100, 150, 0.5);
    }

    .glow-heart::before,
    .glow-heart::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background: #ff1744;
      border-radius: 50%;
      filter: brightness(1.5) saturate(1.7);
    }

    .glow-heart::before {
      left: -10px;
      top: 0;
    }

    .glow-heart::after {
      top: -10px;
      left: 0;
    }

    @keyframes float {
      0% { transform: rotate(45deg) translateX(0) translateY(0); opacity: 0.7; }
      50% { transform: rotate(45deg) translateX(25px) translateY(-20px); opacity: 1; }
      100% { transform: rotate(45deg) translateX(0) translateY(0); opacity: 0.7; }
    }

    /* Chispas grandes */
    .sparkle-big {
      position: absolute;
      width: 8px;
      height: 8px;
      background: #fff;
      border-radius: 50%;
      pointer-events: none;
      animation: sparkle-big 1.8s ease-out forwards;
      box-shadow: 0 0 20px rgba(255, 255, 255, 1);
      z-index: 1000;
    }

    @keyframes sparkle-big {
      0% { transform: scale(0); opacity: 0; }
      20% { opacity: 1; }
      100% { transform: scale(3.5) translateY(-50px) rotate(360deg); opacity: 0; }
    }

    /* Partículas pequeñas brillantes */
    .sparkle-small {
      position: absolute;
      width: 4.5px;
      height: 4.5px;
      background: #fff;
      border-radius: 50%;
      pointer-events: none;
      animation: sparkle-small 2.4s ease-out forwards;
      box-shadow: 0 0 12px rgba(255, 255, 255, 0.95);
      z-index: 999;
    }

    @keyframes sparkle-small {
      0% { transform: scale(0); opacity: 0; }
      30% { opacity: 1; }
      100% { 
        transform: scale(1.6) translate(var(--dx), var(--dy)) rotate(var(--rot)); 
        opacity: 0; 
      }
    }

    /* === UNIVERSO 3D === */
    #universe {
      position: absolute;
      width: 100%;
      height: 100%;
      transform-style: preserve-3d;
      transform: rotateX(15deg) rotateY(0deg);
      transition: transform 0.1s ease;
      opacity: 0;
      pointer-events: none;
      z-index: 1;
    }

    #universe.active {
      opacity: 1;
      pointer-events: all;
    }

    /* Lluvia DETRÁS y DELANTE */
    .rain-back, .rain-front {
      position: absolute;
      width: 100%;
      height: 150vh;
      pointer-events: none;
    }

    .rain-back { z-index: -2; }
    .rain-front { z-index: 3; }

    .char {
      position: absolute;
      font-family: 'Playfair Display', serif;
      white-space: pre;
      opacity: 0.9;
      animation: fall linear infinite;
      text-shadow: 
        0 0 4px rgba(255, 50, 120, 0.6),
        0 0 10px rgba(255, 80, 150, 0.5),
        0 0 20px rgba(255, 100, 180, 0.4);
      letter-spacing: 0.5px;
      filter: saturate(1.3) brightness(1.1);
    }

    @keyframes fall {
      0% { transform: translateY(-100px); opacity: 0; }
      10% { opacity: 1; }
      100% { transform: translateY(130vh); opacity: 0; }
    }

    .char.small { font-size: clamp(1rem, 3.5vw, 1.2rem); }
    .char.medium { font-size: clamp(1.3rem, 4.5vw, 1.6rem); }
    .char.large { font-size: clamp(1.6rem, 5.5vw, 2rem); }

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

    /* Carta central */
    .floating-card {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) translateZ(100px);
      width: 85%;
      max-width: 600px;
      min-height: 300px;
      background: rgba(255, 255, 255, 0.35);
      backdrop-filter: blur(12px);
      border-radius: 26px;
      padding: clamp(25px, 5vw, 35px);
      box-shadow: 
        0 12px 40px rgba(233, 30, 99, 0.3),
        0 0 30px rgba(255, 100, 180, 0.3) inset;
      border: 1px solid rgba(233, 30, 99, 0.5);
      color: #c2185b;
      text-align: center;
      font-family: 'Montserrat', sans-serif;
      line-height: 1.8;
      z-index: 10;
      font-style: italic;
      filter: saturate(1.2) brightness(1.05);
    }

    .floating-card h2 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 5vw, 2.6rem);
      color: #d81b60;
      margin-bottom: 15px;
      text-shadow: 0 0 6px rgba(255, 110, 136, 0.5);
    }

    .floating-card p {
      font-size: clamp(1.1rem, 3.8vw, 1.25rem);
      color: #880e4f;
      margin-bottom: 15px;
    }

    /* Menús 3D */
    .menu-toggle {
      position: absolute;
      width: 40px;
      height: 30px;
      cursor: pointer;
      transform-style: preserve-3d;
      z-index: 20;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      padding: 5px;
      border-radius: 10px;
      background: rgba(233, 30, 99, 0.25);
      box-shadow: 0 0 12px rgba(233, 30, 99, 0.5);
      opacity: 0;
      transition: opacity 0.5s ease;
    }

    .bar {
      height: 5px;
      background: #e91e63;
      border-radius: 3px;
      box-shadow: 0 0 6px rgba(255, 50, 100, 0.7);
    }

    #menuTopLeft { top: 20px; left: 20px; transform: translateZ(60px); }
    #menuTopRight { top: 20px; right: 20px; transform: translateZ(60px); }
    #menuBottomLeft { bottom: 20px; left: 20px; transform: translateZ(60px); }
    #menuBottomRight { bottom: 20px; right: 20px; transform: translateZ(60px); }

    /* Menú desplegable */
    .menu {
      position: fixed;
      top: 0;
      right: -100%;
      width: 80%;
      max-width: 320px;
      height: 100vh;
      background: rgba(255, 255, 255, 0.96);
      backdrop-filter: blur(10px);
      box-shadow: -5px 0 25px rgba(0, 0, 0, 0.15);
      transform: translateZ(80px);
      transition: right 0.4s ease;
      z-index: 100;
      padding: 80px 20px 20px;
      border-radius: 20px 0 0 20px;
    }

    .menu.open {
      right: 0;
    }

    .menu-item {
      margin: 20px 0;
      font-size: clamp(1.1rem, 4vw, 1.2rem);
      color: #d81b60;
      text-decoration: none;
      display: block;
      text-align: center;
      padding: 12px;
      border-radius: 12px;
      background: rgba(233, 30, 99, 0.12);
      transition: 0.3s;
      filter: saturate(1.2);
    }

    .menu-item:hover {
      background: rgba(233, 30, 99, 0.25);
      transform: scale(1.08);
      box-shadow: 0 0 10px rgba(233, 30, 99, 0.3);
    }

    /* Créditos */
    .credits {
      position: absolute;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%) translateZ(60px);
      font-family: 'Montserrat', sans-serif;
      font-size: clamp(0.9rem, 3.5vw, 1.1rem);
      color: #9c27b0;
      text-shadow: 0 0 6px rgba(255, 110, 136, 0.4);
      z-index: 10;
      text-align: center;
      filter: saturate(1.2);
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
    <p>Un detalle hecho con el corazón, solo para ti</p>
    <div class="subtitle">De parte de: AnthZz Berrocal</div>

    <div class="progress-container">
      <svg width="400" height="200" viewBox="0 0 400 200" xmlns="http://www.w3.org/2000/svg">
        <path class="heart-path" d="M200,180 C150,140 80,120 40,80 C0,40 20,0 60,0 C100,0 130,30 160,60 C180,40 220,40 240,60 C270,30 300,0 340,0 C380,0 400,40 360,80 C320,120 250,140 200,180 Z" />
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
    
    <!-- Lluvia detrás -->
    <div class="rain-back" id="rainBack"></div>

    <!-- Lluvia delante -->
    <div class="rain-front" id="rainFront"></div>

    <!-- Carta -->
    <div class="floating-card">
      <h2>Para mi Amor, Jhoryina 💖</h2>
      <p>Te amo con todo mi corazón, más de lo que las palabras pueden expresar. Eres mi paz, mi alegría, mi razón para sonreír cada día.</p>
      <p>Eres especial, única, hermosa por dentro y por fuera. Cada momento contigo es un regalo que atesoro en mi alma.</p>
      <p>No hay nada que desee más que verte feliz, saber que estás bien, y poder amarte cada segundo de mi vida.</p>
      <p>Sin darte cuenta, llenas mis días de luz, mis noches de calma, y mi corazón de amor verdadero.</p>
      <p>Jhoryina, te amo más que a la vida misma. Y si el universo entero se apagara, mi amor por ti seguiría brillando.</p>
    </div>

    <!-- 4 Menús 3D -->
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
      By AnthZz Berrocal - BerMatMods<br>
      <small>Proyecto Vip💖</small>
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

    // === CORAZONES BRILLANTES FLotantes ===
    for (let i = 0; i < 22; i++) {
      const heart = document.createElement('div');
      heart.className = 'glow-heart';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.top = Math.random() * 100 + 'vh';
      heart.style.animationDuration = (3 + Math.random() * 3.5) + 's';
      heart.style.animationDelay = Math.random() * 6 + 's';
      loader.appendChild(heart);
    }

    // === EXPLOSIONES DE CHISPAS ===
    function createExplosion() {
      const x = Math.random() * 100;
      const y = Math.random() * 100;

      for (let i = 0; i < 14; i++) {
        const big = document.createElement('div');
        big.className = 'sparkle-big';
        big.style.left = x + '%';
        big.style.top = y + '%';
        loader.appendChild(big);
        setTimeout(() => big.remove(), 1800);

        for (let j = 0; j < 10; j++) {
          const small = document.createElement('div');
          small.className = 'sparkle-small';
          small.style.left = x + '%';
          small.style.top = y + '%';

          const angle = Math.random() * 360;
          const dist = 70 + Math.random() * 140;
          const dx = Math.cos(angle * Math.PI / 180) * dist;
          const dy = Math.sin(angle * Math.PI / 180) * dist;

          small.style.setProperty('--dx', dx + 'px');
          small.style.setProperty('--dy', dy + 'px');
          small.style.setProperty('--rot', (Math.random() * 360) + 'deg');
          small.style.animationDuration = (2 + Math.random() * 1.4) + 's';

          loader.appendChild(small);
          setTimeout(() => small.remove(), 2400);
        }
      }
    }

    setInterval(createExplosion, 1200);
    setTimeout(createExplosion, 500);

    // === LLUVIA ROMÁNTICA ===
    const romanticLines = [
      "Te amo con cada latido",
      "Eres mi persona especial",
      "Cada día contigo es un milagro",
      "Tu sonrisa ilumina mi mundo",
      "Eres hermosa por dentro",
      "Mi amor no tiene límites",
      "Gracias por ser mi paz",
      "Contigo me siento en casa"
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
      char.style.opacity = isFront ? 0.65 : 0.9;
      char.style.animationDuration = (Math.random() * 8 + 8) + 's';
      container.appendChild(char);

      setTimeout(() => char.remove(), 10000);
    };

    setInterval(() => createRainDrop(rainBack), 170);
    setInterval(() => createRainDrop(rainFront, true), 380);

    // === MENÚS: aparecen al acercarse a esquinas ===
    const menus = [
      document.getElementById('menuTopLeft'),
      document.getElementById('menuTopRight'),
      document.getElementById('menuBottomLeft'),
      document.getElementById('menuBottomRight')
    ];

    document.addEventListener('mousemove', (e) => {
      const w = window.innerWidth;
      const h = window.innerHeight;
      const buffer = 60;

      menus[0].style.opacity = (e.clientX < buffer && e.clientY < buffer) ? '1' : '0';
      menus[1].style.opacity = (e.clientX > w - buffer && e.clientY < buffer) ? '1' : '0';
      menus[2].style.opacity = (e.clientX < buffer && e.clientY > h - buffer) ? '1' : '0';
      menus[3].style.opacity = (e.clientX > w - buffer && e.clientY > h - buffer) ? '1' : '0';
    });

    document.addEventListener('touchstart', (e) => {
      const x = e.touches[0].clientX;
      const y = e.touches[0].clientY;
      const w = window.innerWidth;
      const h = window.innerHeight;
      const buffer = 80;

      menus.forEach(m => m.style.opacity = '0');

      if (x < buffer && y < buffer) menus[0].style.opacity = '1';
      if (x > w - buffer && y < buffer) menus[1].style.opacity = '1';
      if (x < buffer && y > h - buffer) menus[2].style.opacity = '1';
      if (x > w - buffer && y > h - buffer) menus[3].style.opacity = '1';
    });

    // Función compartida para abrir menú
    const openMenu = () => document.getElementById('menu').classList.toggle('open');

    document.getElementById('menuTopLeftLoading').addEventListener('click', openMenu);
    menus.forEach(menu => menu.addEventListener('click', openMenu));

    document.addEventListener('click', (e) => {
      const menu = document.getElementById('menu');
      if (!menu.contains(e.target) && !menus.some(m => m.contains(e.target)) && !document.getElementById('menuTopLeftLoading').contains(e.target)) {
        menu.classList.remove('open');
      }
    });

    // ROTACIÓN 3D
    let rotX = 15, rotY = 0;
    let isDragging = false;
    let startX, startY;

    const handleMove = (dx, dy) => {
      if (isDragging) {
        rotY += dx * 0.6;
        rotX -= dy * 0.6;
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
