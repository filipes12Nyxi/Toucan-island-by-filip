<!DOCTYPE html>
<html lang="cs">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no, viewport-fit=cover">
  <title id="page-title">Toucan Island by Filip12</title>
  
  <!-- PWA Metadata pro instalaci na plochu -->
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
  <meta name="theme-color" content="#0d9488">

  <!-- Tailwind CSS & Lucide Icons -->
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://unpkg.com/lucide@latest"></script>
  <!-- Three.js (3D Engine) -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

  <style>
    body { touch-action: none; user-select: none; margin: 0; overflow: hidden; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
    #canvas-container { width: 100vw; height: 100vh; position: absolute; top: 0; left: 0; z-index: 1; }
    .ui-layer { position: absolute; z-index: 10; pointer-events: none; }
    .interactive { pointer-events: auto; }
    .glass-panel { background: rgba(15, 23, 42, 0.85); backdrop-filter: blur(12px); border: 1px solid rgba(255, 255, 255, 0.15); }
    .glow-text { text-shadow: 0 0 10px rgba(234, 179, 8, 0.6); }
  </style>
</head>
<body class="bg-slate-900 text-white select-none">

  <!-- 3D Canvas Container -->
  <div id="canvas-container"></div>

  <!-- UI Vrstva -->
  <div class="ui-layer inset-0 flex flex-col justify-between p-4">

    <!-- Horní Lišta (Status, Jazyk, Nastavení) -->
    <div class="flex justify-between items-center w-full">
      
      <!-- Hráčův Profil & Mince -->
      <div id="player-hud" class="glass-panel rounded-2xl px-4 py-2 flex items-center space-x-4 interactive shadow-lg hidden">
        <div class="flex items-center space-x-2">
          <div class="w-10 h-10 rounded-full bg-amber-500/20 border border-amber-400 flex items-center justify-center">
            <i data-lucide="bird" class="w-6 h-6 text-amber-400"></i>
          </div>
          <div>
            <div id="hud-username" class="font-bold text-sm text-slate-200">Hráč</div>
            <div id="hud-level" class="text-xs text-amber-400 font-semibold">Level 1</div>
          </div>
        </div>
        <div class="h-8 w-px bg-slate-700"></div>
        <div class="flex items-center space-x-2">
          <i data-lucide="coins" class="w-5 h-5 text-yellow-400 animate-bounce"></i>
          <span id="hud-coins" class="font-extrabold text-lg text-yellow-400 glow-text">0</span>
        </div>
      </div>

      <!-- Tlačítka Nastavení & Admin -->
      <div class="flex space-x-2 ml-auto interactive">
        <button id="btn-settings" class="glass-panel p-3 rounded-xl hover:bg-slate-800 transition text-amber-400">
          <i data-lucide="settings" class="w-6 h-6"></i>
        </button>
      </div>
    </div>

    <!-- Mobilní Ovládání (Joystick & Tlačítka) -->
    <div id="touch-controls" class="flex justify-between items-end w-full pb-4 interactive hidden">
      <!-- Joystick -->
      <div id="joystick-zone" class="w-32 h-32 glass-panel rounded-full relative flex items-center justify-center border-2 border-white/20">
        <div id="joystick-knob" class="w-12 h-12 bg-amber-500 rounded-full shadow-lg absolute"></div>
      </div>
      <!-- Tlačítka Skok a Let -->
      <div class="flex space-x-3">
        <button id="btn-jump" class="w-16 h-16 bg-blue-600 active:bg-blue-700 rounded-2xl flex flex-col items-center justify-center font-bold shadow-lg border border-blue-400/30">
          <i data-lucide="arrow-up" class="w-6 h-6"></i>
          <span class="text-[10px]" data-i18n="btn_jump">SKOK</span>
        </button>
        <button id="btn-fly" class="w-16 h-16 bg-amber-500 active:bg-amber-600 rounded-2xl flex flex-col items-center justify-center font-bold shadow-lg border border-amber-300/30">
          <i data-lucide="feather" class="w-6 h-6"></i>
          <span class="text-[10px]" data-i18n="btn_fly">LET (Q)</span>
        </button>
      </div>
    </div>

    <!-- Spodní Menu Klávesových Zkratek (Počítač) -->
    <div id="desktop-hud" class="hidden md:flex justify-center space-x-4 interactive pb-2">
      <div class="glass-panel px-3 py-1.5 rounded-lg text-xs flex items-center space-x-2">
        <kbd class="bg-slate-800 px-2 py-0.5 rounded border border-slate-600 text-amber-400 font-bold">WASD</kbd>
        <span data-i18n="control_move">Pohyb</span>
      </div>
      <div class="glass-panel px-3 py-1.5 rounded-lg text-xs flex items-center space-x-2">
        <kbd class="bg-slate-800 px-2 py-0.5 rounded border border-slate-600 text-amber-400 font-bold">SPACE</kbd>
        <span data-i18n="control_jump">Skok</span>
      </div>
      <div class="glass-panel px-3 py-1.5 rounded-lg text-xs flex items-center space-x-2">
        <kbd class="bg-slate-800 px-2 py-0.5 rounded border border-slate-600 text-amber-400 font-bold">Q</kbd>
        <span data-i18n="control_fly">Vzlet / Přistání</span>
      </div>
      <div class="glass-panel px-3 py-1.5 rounded-lg text-xs flex items-center space-x-2">
        <kbd class="bg-slate-800 px-2 py-0.5 rounded border border-slate-600 text-amber-400 font-bold">O</kbd>
        <span data-i18n="control_shop">Obchod</span>
      </div>
      <div class="glass-panel px-3 py-1.5 rounded-lg text-xs flex items-center space-x-2">
        <kbd class="bg-slate-800 px-2 py-0.5 rounded border border-slate-600 text-amber-400 font-bold">M</kbd>
        <span data-i18n="control_multi">Multiplayer</span>
      </div>
    </div>
  </div>

  <!-- MODÁLNÍ OKNA -->

  <!-- 1. Přihlášení / Registrace Okno -->
  <div id="modal-auth" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/70 backdrop-blur-sm interactive">
    <div class="glass-panel p-6 rounded-3xl w-full max-w-md border border-amber-500/30 text-center shadow-2xl relative">
      <!-- Skryté Admin Tlačítko (Stisknutí O nebo kliknutí na ikonu) -->
      <button id="btn-secret-admin" class="absolute top-4 left-4 text-slate-600 hover:text-amber-400 transition">
        <i data-lucide="shield" class="w-5 h-5"></i>
      </button>

      <div class="w-20 h-20 bg-gradient-to-tr from-amber-500 to-yellow-300 rounded-full mx-auto mb-4 flex items-center justify-center shadow-lg border-2 border-amber-200">
        <i data-lucide="bird" class="w-10 h-10 text-slate-900"></i>
      </div>
      <h2 id="ui-game-title" class="text-2xl font-black text-amber-400 tracking-wide mb-1">Toucan Island</h2>
      <p class="text-xs text-slate-400 mb-6" data-i18n="auth_subtitle">Prozkoumej tropické dimenze jako tukan!</p>

      <form id="form-auth" class="space-y-4">
        <div>
          <label class="block text-left text-xs font-semibold text-slate-300 mb-1" data-i18n="label_username">Přezdívka (Povinná):</label>
          <input type="text" id="input-username" required placeholder="Napiš svou přezdívku..." class="w-full bg-slate-800/80 border border-slate-700 rounded-xl px-4 py-2.5 text-sm focus:outline-none focus:border-amber-400 transition">
        </div>

        <div>
          <label class="block text-left text-xs font-semibold text-slate-300 mb-1" data-i18n="label_email">E-mail (Volitelné):</label>
          <input type="email" id="input-email" placeholder="tve-jmeno@email.cz" class="w-full bg-slate-800/80 border border-slate-700 rounded-xl px-4 py-2.5 text-sm focus:outline-none focus:border-amber-400 transition">
        </div>

        <button type="submit" class="w-full py-3 bg-gradient-to-r from-amber-500 to-yellow-500 hover:from-amber-600 hover:to-yellow-600 text-slate-950 font-extrabold rounded-xl shadow-lg transition transform active:scale-95 flex items-center justify-center space-x-2">
          <i data-lucide="play" class="w-5 h-5 fill-current"></i>
          <span data-i18n="btn_play">VSTOUPIT DO HRY</span>
        </button>
      </form>
    </div>
  </div>

  <!-- 2. Administrátorské Okno (Grafické rozhraní bez kódu) -->
  <div id="modal-admin" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/80 backdrop-blur-md interactive hidden">
    <div class="glass-panel p-6 rounded-3xl w-full max-w-2xl border border-red-500/40 shadow-2xl max-h-[90vh] overflow-y-auto">
      <div class="flex justify-between items-center mb-6 pb-3 border-b border-slate-700">
        <div class="flex items-center space-x-2">
          <i data-lucide="shield-alert" class="w-6 h-6 text-red-500"></i>
          <h2 class="text-xl font-bold text-red-400">Správa Hry (Admin Panel)</h2>
        </div>
        <button id="close-admin" class="text-slate-400 hover:text-white"><i data-lucide="x" class="w-6 h-6"></i></button>
      </div>

      <div class="space-y-6 text-sm">
        <!-- Nastavení Náznaku a Loga -->
        <div class="bg-slate-800/50 p-4 rounded-xl border border-slate-700">
          <h3 class="font-bold text-amber-400 mb-3 flex items-center space-x-2">
            <i data-lucide="type" class="w-4 h-4"></i>
            <span>Základní Nastavení Webu & Loga</span>
          </h3>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <div>
              <label class="block text-xs text-slate-300 mb-1">Název Hry:</label>
              <input type="text" id="admin-title-input" class="w-full bg-slate-900 border border-slate-700 rounded-lg p-2 text-xs">
            </div>
            <div>
              <label class="block text-xs text-slate-300 mb-1">URL Odkaz na Vlastní Logo:</label>
              <input type="text" id="admin-logo-input" placeholder="https://streda.cz/logo.png" class="w-full bg-slate-900 border border-slate-700 rounded-lg p-2 text-xs">
            </div>
          </div>
        </div>

        <!-- Správa Cen Skinů -->
        <div class="bg-slate-800/50 p-4 rounded-xl border border-slate-700">
          <h3 class="font-bold text-amber-400 mb-3 flex items-center space-x-2">
            <i data-lucide="tag" class="w-4 h-4"></i>
            <span>Ceny a Názvy Skinů v Obchodě</span>
          </h3>
          <div class="grid grid-cols-2 gap-3" id="admin-skins-list">
            <!-- Dynamicky generované položky skinů -->
          </div>
        </div>

        <!-- Generování Admin Pozvánky -->
        <div class="bg-slate-800/50 p-4 rounded-xl border border-slate-700">
          <h3 class="font-bold text-amber-400 mb-2 flex items-center space-x-2">
            <i data-lucide="user-plus" class="w-4 h-4"></i>
            <span>Pozvat Dalšího Admina (Kámoše)</span>
          </h3>
          <p class="text-xs text-slate-400 mb-3">Vygeneruj unikátní kód, který pošleš kamarádovi pro přístup k administraci.</p>
          <div class="flex space-x-2">
            <input type="text" id="admin-invite-code" readonly placeholder="Klikni na vygenerovat..." class="flex-grow bg-slate-900 border border-slate-700 rounded-lg p-2 text-xs font-mono text-amber-300">
            <button id="btn-gen-invite" class="bg-amber-500 hover:bg-amber-600 text-slate-950 px-4 py-2 rounded-lg font-bold text-xs">Vygenerovat Kód</button>
          </div>
        </div>

        <button id="btn-save-admin" class="w-full py-3 bg-red-600 hover:bg-red-700 text-white font-bold rounded-xl shadow-lg transition">Uložit Všechny Změny</button>
      </div>
    </div>
  </div>

  <!-- 3. Nastavení Panel -->
  <div id="modal-settings" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/70 backdrop-blur-sm interactive hidden">
    <div class="glass-panel p-6 rounded-3xl w-full max-w-md border border-slate-700 shadow-2xl">
      <div class="flex justify-between items-center mb-6">
        <h2 class="text-xl font-bold text-amber-400" data-i18n="settings_title">Nastavení Hry</h2>
        <button id="close-settings" class="text-slate-400 hover:text-white"><i data-lucide="x" class="w-6 h-6"></i></button>
      </div>

      <div class="space-y-4 text-sm">
        <!-- Jazyk -->
        <div class="flex justify-between items-center bg-slate-800/50 p-3 rounded-xl">
          <span data-i18n="set_lang">Jazyk (Language):</span>
          <select id="select-lang" class="bg-slate-900 border border-slate-700 rounded-lg px-3 py-1 text-xs">
            <option value="cs">Čeština 🇨🇿</option>
            <option value="en">English 🇬🇧</option>
          </select>
        </div>

        <!-- Grafika (5 Úrovní) -->
        <div class="bg-slate-800/50 p-3 rounded-xl space-y-1">
          <div class="flex justify-between">
            <span data-i18n="set_graphics">Kvalita Grafiky:</span>
            <span id="graphics-val" class="font-bold text-amber-400">Velmi Vysoká</span>
          </div>
          <input type="range" id="slider-graphics" min="1" max="5" value="5" class="w-full accent-amber-400">
        </div>

        <!-- Hlasitost Hudby -->
        <div class="bg-slate-800/50 p-3 rounded-xl space-y-1">
          <div class="flex justify-between">
            <span data-i18n="set_music">Hlasitost Hudby:</span>
            <span id="music-val" class="font-bold text-amber-400">50%</span>
          </div>
          <input type="range" id="slider-music" min="0" max="100" value="50" class="w-full accent-amber-400">
        </div>

        <!-- Denní / Noční Režim -->
        <div class="flex justify-between items-center bg-slate-800/50 p-3 rounded-xl">
          <span data-i18n="set_daynight">Denní / Noční Čas:</span>
          <button id="btn-toggle-day" class="bg-amber-500 text-slate-950 font-bold px-3 py-1 rounded-lg text-xs">Den ☀️</button>
        </div>
      </div>
    </div>
  </div>

  <!-- SCRIPT HRY -->
  <script>
    // Inicializace Lucide Ikon
    lucide.createIcons();

    // Herní Konstanty a Nastavení
    const GAME_DATA = {
      title: "Toucan Island by Filip12",
      logoUrl: null,
      coins: 0,
      level: 1,
      skin: "classic",
      lang: "cs",
      dayTime: true,
      graphicsLevel: 5,
      isAdmin: false,
      skins: {
        classic: { name: "Klasický Tukan", price: 0, color: 0xff6600, levelReq: 1 },
        golden: { name: "Zlatý Tukan", price: 50, color: 0xffd700, levelReq: 2 },
        neon: { name: "Cyber Neón", price: 150, color: 0x00ffff, levelReq: 4 },
        rainbow: { name: "Duhový Letec", price: 300, color: 0xff00ff, levelReq: 6 },
        shadow: { name: "Stínový Drak", price: 600, color: 0x222222, levelReq: 8 }
      }
    };

    // 3D Scene Variables
    let scene, camera, renderer, toucan, coinsArray = [];
    let isFlying = false;
    let keys = {};

    // Inicializace Hry
    function initEngine() {
      const container = document.getElementById('canvas-container');
      scene = new THREE.Scene();
      scene.background = new THREE.Color(0x38bdf8);
      scene.fog = new THREE.FogExp2(0x38bdf8, 0.015);

      camera = new THREE.PerspectiveCamera(60, window.innerWidth / window.innerHeight, 0.1, 1000);
      camera.position.set(0, 5, 12);

      renderer = new THREE.WebGLRenderer({ antialias: true });
      renderer.setSize(window.innerWidth, window.innerHeight);
      renderer.shadowMap.enabled = true;
      container.appendChild(renderer.domElement);

      // Světla
      const ambientLight = new THREE.AmbientLight(0xffffff, 0.7);
      scene.add(ambientLight);

      const dirLight = new THREE.DirectionalLight(0xffffff, 0.8);
      dirLight.position.set(50, 80, 30);
      dirLight.castShadow = true;
      scene.add(dirLight);

      // Vytvoření Ostrova
      createIsland();
      // Vytvoření Modelu Tukana
      createToucan();
      // Vytvoření Mincí
      spawnCoins();

      // Loop
      animate();
    }

    function createIsland() {
      // Hlavní Ostrov (Země)
      const geo = new THREE.CylinderGeometry(35, 40, 4, 32);
      const mat = new THREE.MeshStandardMaterial({ color: 0x22c55e, roughness: 0.8 });
      const island = new THREE.Mesh(geo, mat);
      island.position.y = -2;
      island.receiveShadow = true;
      scene.add(island);

      // Pláž
      const sandGeo = new THREE.CylinderGeometry(42, 45, 3.8, 32);
      const sandMat = new THREE.MeshStandardMaterial({ color: 0xfde047 });
      const sand = new THREE.Mesh(sandGeo, sandMat);
      sand.position.y = -2.1;
      scene.add(sand);
    }

    function createToucan() {
      const group = new THREE.Group();

      // Tělo
      const bodyGeo = new THREE.ConeGeometry(0.8, 2, 16);
      const bodyMat = new THREE.MeshStandardMaterial({ color: 0x111111 });
      const body = new THREE.Mesh(bodyGeo, bodyMat);
      body.rotation.x = Math.PI / 3;
      group.add(body);

      // Hlava
      const headGeo = new THREE.SphereGeometry(0.55, 16, 16);
      const head = new THREE.Mesh(headGeo, bodyMat);
      head.position.set(0, 0.7, 0.6);
      group.add(head);

      // Barevný Zobák
      const beakGeo = new THREE.ConeGeometry(0.35, 1.4, 16);
      const beakMat = new THREE.MeshStandardMaterial({ color: GAME_DATA.skins[GAME_DATA.skin].color, roughness: 0.3 });
      const beak = new THREE.Mesh(beakGeo, beakMat);
      beak.rotation.x = Math.PI / 2;
      beak.position.set(0, 0.6, 1.4);
      group.add(beak);

      toucan = group;
      toucan.position.set(0, 1, 0);
      scene.add(toucan);
    }

    function spawnCoins() {
      for (let i = 0; i < 15; i++) {
        const geo = new THREE.CylinderGeometry(0.6, 0.6, 0.15, 16);
        const mat = new THREE.MeshStandardMaterial({ color: 0xfacc15, metalness: 0.8, roughness: 0.2 });
        const coin = new THREE.Mesh(geo, mat);
        
        const angle = Math.random() * Math.PI * 2;
        const radius = Math.random() * 25;
        coin.position.set(Math.cos(angle) * radius, 1 + Math.random() * 3, Math.sin(angle) * radius);
        coin.rotation.x = Math.PI / 2;
        
        scene.add(coin);
        coinsArray.push(coin);
      }
    }

    function animate() {
      requestAnimationFrame(animate);

      // Otáčení mincí
      coinsArray.forEach(c => c.rotation.z += 0.03);

      // Pohyb Tukana
      if (toucan) {
        if (keys['KeyW']) toucan.translateZ(0.2);
        if (keys['KeyS']) toucan.translateZ(-0.15);
        if (keys['KeyA']) toucan.rotation.y += 0.04;
        if (keys['KeyD']) toucan.rotation.y -= 0.04;

        // Vzlet / Přistání (Q)
        if (isFlying) {
          toucan.position.y = THREE.MathUtils.lerp(toucan.position.y, 2.5, 0.1);
        } else {
          toucan.position.y = THREE.MathUtils.lerp(toucan.position.y, 0.8, 0.1);
        }

        // Sledování Kamerou
        const relativeCameraOffset = new THREE.Vector3(0, 4, -8);
        const cameraOffset = relativeCameraOffset.applyMatrix4(toucan.matrixWorld);
        camera.position.x = THREE.MathUtils.lerp(camera.position.x, cameraOffset.x, 0.1);
        camera.position.y = THREE.MathUtils.lerp(camera.position.y, cameraOffset.y, 0.1);
        camera.position.z = THREE.MathUtils.lerp(camera.position.z, cameraOffset.z, 0.1);
        camera.lookAt(toucan.position);
      }

      renderer.render(scene, camera);
    }

    // Event Listenery pro Klávesnici
    window.addEventListener('keydown', (e) => {
      keys[e.code] = true;
      if (e.code === 'KeyQ') isFlying = !isFlying;
      if (e.code === 'KeyO') openAdminPanel();
    });
    window.addEventListener('keyup', (e) => keys[e.code] = false);

    // Přihlášení
    document.getElementById('form-auth').addEventListener('submit', (e) => {
      e.preventDefault();
      const username = document.getElementById('input-username').value;
      if (username) {
        document.getElementById('hud-username').innerText = username;
        document.getElementById('modal-auth').classList.add('hidden');
        document.getElementById('player-hud').classList.remove('hidden');
        document.getElementById('touch-controls').classList.remove('hidden');
        initEngine();
      }
    });

    // Admin Okno
    function openAdminPanel() {
      document.getElementById('modal-admin').classList.remove('hidden');
      document.getElementById('admin-title-input').value = GAME_DATA.title;
      
      const skinsList = document.getElementById('admin-skins-list');
      skinsList.innerHTML = '';
      Object.keys(GAME_DATA.skins).forEach(key => {
        const skin = GAME_DATA.skins[key];
        skinsList.innerHTML += `
          <div class="bg-slate-900 p-2 rounded border border-slate-700">
            <div class="text-xs text-amber-400 font-bold">${skin.name}</div>
            <div class="mt-1 flex space-x-1">
              <input type="number" value="${skin.price}" class="w-full bg-slate-800 px-2 py-1 text-xs border border-slate-600 rounded">
            </div>
          </div>
        `;
      });
    }

    document.getElementById('close-admin').onclick = () => document.getElementById('modal-admin').classList.add('hidden');
    document.getElementById('btn-settings').onclick = () => document.getElementById('modal-settings').classList.remove('hidden');
    document.getElementById('close-settings').onclick = () => document.getElementById('modal-settings').classList.add('hidden');
  </script>
</body>
</html>
