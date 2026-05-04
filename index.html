<?php
if (isset($_GET['action']) && $_GET['action'] === 'get_cartas') {
    header('Content-Type: application/json');
    $carpeta = __DIR__ . '/cartas';
    $cartas = [];
    if (is_dir($carpeta)) {
        $extensiones = ['jpg', 'jpeg', 'png', 'gif', 'webp'];
        $archivos = scandir($carpeta);
        foreach ($archivos as $archivo) {
            $ext = strtolower(pathinfo($archivo, PATHINFO_EXTENSION));
            if (in_array($ext, $extensiones)) {
                $nombre = pathinfo($archivo, PATHINFO_FILENAME);
                $nombreLimpio = preg_replace('/^[\d\-_]+/', '', $nombre);
                $nombreLimpio = str_replace(['-', '_'], ' ', $nombreLimpio);
                $nombreLimpio = ucwords(strtolower($nombreLimpio));
                $cartas[] = [
                    'archivo' => $archivo,
                    'nombre'  => $nombreLimpio ?: $nombre,
                    'ruta'    => 'cartas/' . $archivo,
                ];
            }
        }
    }
    echo json_encode($cartas);
    exit;
}
?>
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <meta name="mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <title> Lotería</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --rojo: #C0392B;
            --rojo-oscuro: #922B21;
            --dorado: #D4AC0D;
            --dorado-claro: #F4D03F;
            --crema: #FDF6E3;
            --cafe: #5D4037;
            --cafe-oscuro: #3E2723;
            --verde-claro: #2E7D32;
            --verde: #1B5E20;
        }

        *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

        html, body { height: 100%; overscroll-behavior: none; }

        body {
            background-color: var(--cafe-oscuro);
            background-image:
                repeating-linear-gradient(45deg,  transparent, transparent 20px, rgba(212,172,13,0.03) 20px, rgba(212,172,13,0.03) 40px),
                repeating-linear-gradient(-45deg, transparent, transparent 20px, rgba(192,57,43,0.03)  20px, rgba(192,57,43,0.03)  40px);
            font-family: 'Playfair Display', Georgia, serif;
            color: var(--crema);
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100dvh;
            padding: env(safe-area-inset-top) env(safe-area-inset-right) env(safe-area-inset-bottom) env(safe-area-inset-left);
        }

        /* ────── LAYOUT ────── */
        main {
            width: 100%;
            max-width: 600px;
            flex: 1;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 12px 12px 16px;
            gap: 10px;
        }

        /* ────── CARTA GRANDE ────── */
        #carta-display {
            width: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            flex: 1;
            min-height: 0;
        }

        .marco-carta {
            position: relative;
            flex: 1;
            min-height: 0;
            max-height: 74vh;
            width: 100%;
            max-width: min(100%, calc(74vh * 2 / 3));
            aspect-ratio: 2 / 3;
            border: 2px solid var(--dorado);
            border-radius: 10px;
            background: #000;
            box-shadow: 0 8px 32px rgba(0,0,0,0.7);
            overflow: hidden;
        }
        .marco-carta.animando { animation: flipCarta 0.45s ease-in-out; }
        @keyframes flipCarta {
            0%  { transform: rotateY(0deg)  scale(1);    }
            50% { transform: rotateY(90deg) scale(0.96); }
            100%{ transform: rotateY(0deg)  scale(1);    }
        }

        #carta-img {
            width: 100%; height: 100%;
            object-fit: contain; object-position: center;
            display: block;
            background: #fff;
        }

        .carta-placeholder {
            width: 100%; height: 100%;
            display: flex; flex-direction: column;
            align-items: center; justify-content: center;
            background: linear-gradient(135deg, var(--crema), #f0e6c8);
            gap: 14px; padding: 20px;
        }
        .carta-placeholder .icono { font-size: clamp(3rem, 15vw, 6rem); }
        .carta-placeholder p {
            font-size: clamp(1rem, 4vw, 1.4rem);
            color: var(--cafe); text-align: center;
        }



        /* ────── PROGRESO ────── */
        .barra-progreso-wrap {
            width: 100%;
            display: flex; flex-direction: column; align-items: center; gap: 5px;
        }
        .progreso-texto {
            font-size: clamp(0.8rem, 3vw, 1rem);
            color: var(--dorado-claro); letter-spacing: 1px;
        }
        .barra-bg {
            width: 100%; height: 8px;
            background: rgba(0,0,0,0.4);
            border-radius: 8px;
            border: 1px solid rgba(212,172,13,0.5);
            overflow: hidden;
        }
        .barra-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--rojo), var(--dorado));
            border-radius: 8px;
            transition: width 0.5s ease;
            width: 0%;
        }



        /* ────── BOTONES ────── */
        .controles {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr;
            gap: 10px;
            width: 100%;
        }
        .btn {
            font-family: 'Playfair Display', serif;
            font-size: clamp(0.85rem, 3.2vw, 1.05rem);
            font-weight: 700;
            letter-spacing: 0.5px;
            text-transform: uppercase;
            min-height: 52px;
            padding: 12px 6px;
            border: 3px solid var(--dorado);
            border-radius: 10px;
            cursor: pointer;
            display: flex; align-items: center; justify-content: center; gap: 5px;
            transition: filter 0.15s, transform 0.1s;
            -webkit-tap-highlight-color: transparent;
            touch-action: manipulation;
        }
        .btn:active { transform: scale(0.95); filter: brightness(0.82); }

        .btn-pausa     { background: var(--verde-claro); color: var(--crema);        box-shadow: 0 4px 14px rgba(46,125,50,0.45);  }
        .btn-reiniciar { background: var(--rojo);        color: var(--crema);        box-shadow: 0 4px 14px rgba(192,57,43,0.45); }
        .btn-config    { background: var(--cafe);        color: var(--dorado-claro); box-shadow: 0 4px 14px rgba(93,64,55,0.45);   }

        /* ────── GALERÍA ────── */
        .seccion-galeria { width: 100%; }
        .seccion-titulo {
            font-size: clamp(0.75rem, 2.8vw, 0.95rem);
            color: var(--dorado); text-align: center;
            margin-bottom: 8px; letter-spacing: 2px; text-transform: uppercase;
            border-bottom: 1px solid rgba(212,172,13,0.3); padding-bottom: 5px;
        }
        .galeria-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(66px, 1fr));
            gap: 6px;
        }
        .miniatura {
            aspect-ratio: 2 / 3;
            border-radius: 6px; overflow: hidden;
            border: 2px solid rgba(212,172,13,0.25);
            transition: border-color 0.3s, filter 0.3s, transform 0.3s;
            position: relative; background: rgba(0,0,0,0.3);
        }
        .miniatura img { width: 100%; height: 100%; object-fit: cover; display: block; }
        .miniatura.cantada {
            border-color: rgba(212,172,13,0.5);
            filter: grayscale(65%) brightness(0.65);
        }
        .miniatura.cantada::after {
            content: '✓'; position: absolute; inset: 0;
            display: flex; align-items: center; justify-content: center;
            color: var(--dorado-claro); font-size: 1.4rem; font-weight: bold;
            text-shadow: 0 0 8px rgba(0,0,0,0.9);
        }
        .miniatura.actual {
            border-color: var(--dorado-claro);
            box-shadow: 0 0 10px var(--dorado);
            transform: scale(1.07); z-index: 2;
        }
        .miniatura-placeholder {
            width: 100%; height: 100%;
            display: flex; align-items: center; justify-content: center;
            font-size: 1.3rem;
            background: linear-gradient(135deg, rgba(93,64,55,0.5), rgba(62,39,35,0.5));
        }

        /* ────── MODAL CONFIG ────── */
        .modal-overlay {
            position: fixed; inset: 0;
            background: rgba(0,0,0,0.78);
            display: none; align-items: center; justify-content: center;
            z-index: 200; backdrop-filter: blur(5px); padding: 16px;
        }
        .modal-overlay.abierto { display: flex; }
        .modal {
            background: linear-gradient(145deg, var(--cafe-oscuro), #2a1a15);
            border: 3px solid var(--dorado); border-radius: 16px;
            padding: 28px 24px; width: 100%; max-width: 400px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.85);
        }
        .modal h2 {
            color: var(--dorado-claro);
            font-size: clamp(1.2rem, 5vw, 1.6rem);
            text-align: center; margin-bottom: 22px; letter-spacing: 2px;
        }
        .config-item { margin-bottom: 20px; }
        .config-item label {
            display: block; color: var(--crema);
            font-size: clamp(0.9rem, 3.5vw, 1.05rem);
            margin-bottom: 8px; letter-spacing: 0.5px;
        }
        .config-item .valor { color: var(--dorado-claro); font-weight: 700; }
        input[type="range"] {
            width: 100%; -webkit-appearance: none;
            height: 6px; border-radius: 3px;
            background: rgba(212,172,13,0.2); outline: none;
            border: 1px solid rgba(212,172,13,0.4);
        }
        input[type="range"]::-webkit-slider-thumb {
            -webkit-appearance: none; width: 28px; height: 28px;
            border-radius: 50%; background: var(--dorado);
            cursor: pointer; border: 3px solid var(--rojo);
            box-shadow: 0 2px 8px rgba(0,0,0,0.4);
        }
        input[type="range"]::-moz-range-thumb {
            width: 28px; height: 28px; border-radius: 50%;
            background: var(--dorado); cursor: pointer;
            border: 3px solid var(--rojo);
        }
        .btn-cerrar {
            width: 100%; margin-top: 6px;
            background: var(--rojo); border-color: var(--dorado);
            color: var(--crema); min-height: 52px;
        }

        /* ────── PANTALLAS MUY PEQUEÑAS ────── */
        @media (max-width: 360px) {
            .controles { gap: 7px; }
            .btn { font-size: 0.78rem; min-height: 46px; padding: 10px 4px; }
            .galeria-grid { grid-template-columns: repeat(auto-fill, minmax(52px, 1fr)); }
        }

        /* ────── LANDSCAPE MÓVIL ────── */
        @media (max-height: 500px) and (orientation: landscape) {
            main { flex-direction: row; flex-wrap: wrap; padding: 8px; gap: 8px; }
            #carta-display { width: 42%; flex: none; }
            .marco-carta { max-height: 90vh; }
            .nombre-carta { max-width: 100%; }
            .controles { grid-template-columns: 1fr; width: 18%; flex: none; gap: 7px; }
            .barra-progreso-wrap, #estado-msg { width: 38%; }
            .seccion-galeria { width: 100%; }
            .galeria-grid { grid-template-columns: repeat(auto-fill, minmax(50px, 1fr)); }
        }
    </style>
</head>
<body>
<main>

    <!-- CARTA PRINCIPAL -->
    <div id="carta-display">
        <div class="marco-carta" id="marco">
            <div class="carta-placeholder">
                <span class="icono"></span>
                <p>Presiona INICIAR para comenzar</p>
            </div>
        </div>

    </div>

    <!-- PROGRESO -->
    <div class="barra-progreso-wrap">
        <div class="progreso-texto" id="progreso-texto">0 / 0 cartas</div>
        <div class="barra-bg"><div class="barra-fill" id="barra-fill"></div></div>
    </div>



    <!-- BOTONES -->
    <div class="controles">
        <button class="btn btn-pausa"     id="btn-pausa"  onclick="togglePausa()">▶ INICIAR</button>
        <button class="btn btn-reiniciar"                 onclick="reiniciar()">↺ REINICIAR</button>
        <button class="btn btn-config"                    onclick="abrirConfig()">⚙ Config</button>
    </div>

    <!-- GALERÍA -->
    <div class="seccion-galeria">
        <div class="seccion-titulo">✦ Todas las cartas ✦</div>
        <div class="galeria-grid" id="galeria"></div>
    </div>

</main>

<!-- MODAL CONFIGURACIÓN -->
<div class="modal-overlay" id="modal-config">
    <div class="modal">
        <h2>⚙ Configuración</h2>
        <div class="config-item">
            <label>🔊 Volumen: <span class="valor" id="val-volumen">80%</span></label>
            <input type="range" id="rng-volumen" min="0" max="100" value="80"
                   oninput="document.getElementById('val-volumen').textContent=this.value+'%'; ajustarVolumen(this.value)">
        </div>
        <div class="config-item">
            <label>⏱ Tiempo entre CARTAS: <span class="valor" id="val-tiempo">5 seg</span></label>
            <input type="range" id="rng-tiempo" min="2" max="20" value="5"
                   oninput="document.getElementById('val-tiempo').textContent=this.value+' seg'; tiempoEntreCarta=this.value*1000">
        </div>
        <button class="btn btn-cerrar" onclick="cerrarConfig()">✓ Guardar y cerrar</button>
        <br>
        <h3>Created by Ing. Luis Lopez</h3>
<a href="https://luis-lopez-99.github.io/portafolio/" 
   target="_blank" 
   rel="noopener noreferrer"
   style="color: #4da3ff; text-decoration: none; font-weight: bold;">
    Ver portafolio
</a>
    </div>
</div>

<script>
// ── ESTADO ───────────────────────────────────────────────
let todasCartas      = [];
let mazo             = [];
let cantadas         = new Set();
let jugando          = false;
let pausado          = false;
let timerSig         = null;
let tiempoEntreCarta = 5000;
let volumen          = 0.8;

// ── VOZ ──────────────────────────────────────────────────
let vozMexicana = null;

function cargarVoz() {
    const intentar = () => {
        const voces = window.speechSynthesis.getVoices();
        if (!voces.length) return;
        // Prioridad: voz explícitamente mexicana
        vozMexicana =
            voces.find(v => v.lang === 'es-MX') ||
            voces.find(v => v.lang.startsWith('es-MX')) ||
            voces.find(v => v.lang.startsWith('es') && /mexic|google español/i.test(v.name)) ||
            voces.find(v => v.lang.startsWith('es'));
    };
    intentar();
    if (!vozMexicana && 'onvoiceschanged' in window.speechSynthesis) {
        window.speechSynthesis.onvoiceschanged = intentar;
    }
}

function hablar(texto) {
    if (!('speechSynthesis' in window)) return;
    window.speechSynthesis.cancel();
    const u = new SpeechSynthesisUtterance(texto);
    if (vozMexicana) u.voice = vozMexicana;
    u.lang   = 'es-MX';
    u.volume = volumen;
    u.rate   = 0.82;   // un poco más pausado, como cantador de feria
    u.pitch  = 1.1;    // tono ligeramente más agudo = más expresivo
    window.speechSynthesis.speak(u);
}
function ajustarVolumen(v) { volumen = v / 100; }

// ── CARGA ─────────────────────────────────────────────────
async function cargarCartas() {
    try {
        const res = await fetch('?action=get_cartas');
        const data = await res.json();
        todasCartas = data;
        if (todasCartas.length === 0) {
            setEstado('⚠️ No se encontraron cartas en la carpeta "cartas"');
            renderGaleria(); return;
        }
        setEstado(`${todasCartas.length} cartas listas. ¡Presiona INICIAR!`);
        reiniciarMazo(); renderGaleria(); actualizarProgreso();
    } catch(e) { cargarCartasDemo(); }
}

function cargarCartasDemo() {
    const demo = ['El Gallo','El Diablito','La Dama','El Catrín','El Paraguas',
        'La Sirena','La Escalera','La Botella','El Barril','El Árbol',
        'El Melón','El Valiente','El Gorrito','La Muerte','La Pera',
        'La Bandera','El Bandolón','El Violoncello','La Garza','El Pájaro',
        'La Mano','La Bota','La Luna','El Cotorro','El Borracho',
        'El Negrito','El Corazón','La Sandía','El Tambor','El Camarón',
        'Las Jaras','El Músico','La Araña','El Soldado','La Estrella',
        'El Cazo','El Mundo','El Apache','El Nopal','El Alacrán',
        'La Rosa','La Calavera','El Cantarito','El Venado','El Sol',
        'La Corona','La Chalupa','El Pino','El Pescado','La Palma',
        'La Maceta','El Arpa','La Rana','El Escorpión'];
    todasCartas = demo.map((n,i) => ({ archivo: i+'.png', nombre: n, ruta: null }));
    setEstado(`Modo demo · ${todasCartas.length} cartas. ¡Presiona INICIAR!`);
    reiniciarMazo(); renderGaleria(); actualizarProgreso();
}

// ── MAZO ──────────────────────────────────────────────────
function reiniciarMazo() {
    mazo = [...todasCartas];
    for (let i = mazo.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [mazo[i], mazo[j]] = [mazo[j], mazo[i]];
    }
    cantadas.clear(); actualizarGaleria(null);
}

// ── JUEGO ─────────────────────────────────────────────────
function togglePausa() {
    const btn = document.getElementById('btn-pausa');
    if (!jugando) {
        jugando = true; pausado = false;
        btn.innerHTML = '⏸ Pausa'; siguiente();
    } else if (!pausado) {
        pausado = true; clearTimeout(timerSig); window.speechSynthesis.cancel();
        btn.innerHTML = '▶ Continuar'; setEstado('⏸ Juego pausado');
    } else {
        pausado = false; btn.innerHTML = '⏸ Pausa'; siguiente();
    }
}

function siguiente() {
    if (pausado) return;
    if (mazo.length === 0) {
        jugando = false; pausado = false;
        document.getElementById('btn-pausa').innerHTML = '▶ INICIAR';
        setEstado('¡Se cantaron todas las cartas! Reinicia para jugar de nuevo.');
        hablar('Se acabaron todas las cartas.'); return;
    }
    const carta = mazo.pop();
    cantadas.add(carta.archivo);
    mostrarCarta(carta); hablar(carta.nombre);
    actualizarProgreso(); actualizarGaleria(carta.archivo);
    timerSig = setTimeout(siguiente, tiempoEntreCarta);
}

function reiniciar() {
    clearTimeout(timerSig); window.speechSynthesis.cancel();
    jugando = false; pausado = false;
    document.getElementById('btn-pausa').innerHTML = '▶ INICIAR';
    reiniciarMazo();
    document.getElementById('marco').innerHTML =
        `<div class="carta-placeholder"><span class="icono"></span><p>¡Reiniciado! Presiona INICIAR</p></div>`;
    actualizarProgreso(); setEstado('Juego reiniciado. ¡Presiona INICIAR!');
}

// pruebas con emojis 
const emojis = ['🐓','😈','👸','🎩','☂️','🧜','🪜','🍾','🛢️','🌳','🍈','🤺','🎓','💀','🍐','🚩','🪗','🎻','🦢','🐦','✋','👢','🌙','🦜','🥴','👦','❤️','🍉','🥁','🦐','🏹','🎵','🕷️','💂','⭐','🥘','🌍','🪶','🌵','🦂','🌹','💀','🏺','🦌','☀️','👑','🛶','🌲','🐟','🌴','🪴','🎶','🐸','🦂'];

function mostrarCarta(carta) {
    const marco = document.getElementById('marco');
    marco.classList.add('animando');
    setTimeout(() => marco.classList.remove('animando'), 450);
    if (carta.ruta) {
        marco.innerHTML = `<img id="carta-img" src="${carta.ruta}" alt="${carta.nombre}"
            onerror="this.parentElement.innerHTML='<div class=\\'carta-placeholder\\'><span class=\\'icono\\'></span><p>${carta.nombre}</p></div>'">`;
    } else {
        const idx = todasCartas.findIndex(c => c.archivo === carta.archivo);
        const emoji = emojis[idx] || '';
        marco.innerHTML = `<div class="carta-placeholder">
            <span class="icono" style="font-size:clamp(4rem,18vw,8rem)">${emoji}</span>
            <p style="font-size:clamp(1.2rem,5vw,1.9rem);font-weight:700">${carta.nombre}</p>
        </div>`;
    }
}

// ── PROGRESO + ESTADO ─────────────────────────────────────
function actualizarProgreso() {
    const total = todasCartas.length, cant = cantadas.size;
    document.getElementById('progreso-texto').textContent = `${cant} / ${total} cartas`;
    document.getElementById('barra-fill').style.width = total > 0 ? (cant/total*100)+'%' : '0%';
}
function setEstado(msg) {}

// ── GALERÍA ───────────────────────────────────────────────
function renderGaleria() {
    const g = document.getElementById('galeria');
    g.innerHTML = '';
    todasCartas.forEach(carta => {
        const div = document.createElement('div');
        div.className = 'miniatura';
        div.id = 'min-' + carta.archivo.replace(/[^a-z0-9]/gi,'_');
        div.title = carta.nombre;
        div.innerHTML = carta.ruta
            ? `<img src="${carta.ruta}" alt="${carta.nombre}" loading="lazy"
                onerror="this.parentElement.innerHTML='<div class=\\'miniatura-placeholder\\'></div>'">`
            : `<div class="miniatura-placeholder"></div>`;
        g.appendChild(div);
    });
}

function actualizarGaleria(archivoActual) {
    todasCartas.forEach(carta => {
        const el = document.getElementById('min-' + carta.archivo.replace(/[^a-z0-9]/gi,'_'));
        if (!el) return;
        el.className = 'miniatura';
        if (carta.archivo === archivoActual) el.classList.add('actual');
        else if (cantadas.has(carta.archivo)) el.classList.add('cantada');
    });
}

// ── CONFIG ────────────────────────────────────────────────
function abrirConfig()  { document.getElementById('modal-config').classList.add('abierto'); }
function cerrarConfig() { document.getElementById('modal-config').classList.remove('abierto'); }
document.getElementById('modal-config').addEventListener('click', e => {
    if (e.target === e.currentTarget) cerrarConfig();
});

// ── INIT ──────────────────────────────────────────────────
cargarVoz();
cargarCartas();
</script>
</body>
</html>
