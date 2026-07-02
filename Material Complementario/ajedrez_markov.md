<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Caballo · Cadena de Markov</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,wght@0,400;0,500;1,400&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --ink: #1a1613;
    --paper: #f4efe6;
    --paper-warm: #ece4d3;
    --accent: #c2410c;
    --muted: #6b5d4f;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'Fraunces', Georgia, serif;
    background: var(--paper);
    color: var(--ink);
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 40px 20px;
  }

  .container {
    max-width: 1100px;
    width: 100%;
  }

  h1 {
    font-weight: 400;
    font-size: clamp(28px, 4vw, 42px);
    letter-spacing: -0.02em;
    margin-bottom: 8px;
  }

  h1 em {
    font-style: italic;
    color: var(--accent);
  }

  .subtitle {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 32px;
  }

  .layout {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 48px;
    align-items: start;
  }

  @media (max-width: 820px) {
    .layout { grid-template-columns: 1fr; gap: 32px; }
  }

  .board-wrap {
    background: var(--paper-warm);
    padding: 24px;
    border-radius: 2px;
    box-shadow: 0 20px 40px -20px rgba(42, 36, 31, 0.25);
  }

  .heatmap-board {
    display: grid;
    grid-template-columns: repeat(8, 1fr);
    aspect-ratio: 1;
    width: 100%;
    border: 2px solid var(--ink);
  }

  .heat-cell {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 500;
    transition: background-color 0.3s ease, color 0.3s ease;
    cursor: pointer;
  }

  .heat-cell.start-cell {
    outline: 3px solid var(--ink);
    outline-offset: -3px;
    z-index: 2;
  }

  .prob-label {
    pointer-events: none;
    font-feature-settings: "tnum";
  }

  .legend {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-top: 16px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
  }

  .gradient-bar {
    height: 6px;
    flex: 1;
    background: linear-gradient(to right, #f8f4e9, #eab676, #c2410c, #7c2d12);
    border-radius: 2px;
  }

  .controls {
    display: flex;
    flex-direction: column;
    gap: 28px;
  }

  .control-group {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .control-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
    display: flex;
    justify-content: space-between;
    align-items: baseline;
  }

  .control-value {
    font-family: 'Fraunces', serif;
    font-size: 32px;
    font-weight: 400;
    color: var(--accent);
    font-style: italic;
    font-feature-settings: "tnum";
  }

  input[type="range"] {
    -webkit-appearance: none;
    appearance: none;
    width: 100%;
    height: 2px;
    background: var(--ink);
    outline: none;
    cursor: pointer;
  }

  input[type="range"]::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 20px;
    height: 20px;
    background: var(--accent);
    cursor: pointer;
    border-radius: 50%;
    border: 3px solid var(--paper);
    box-shadow: 0 0 0 1px var(--accent);
  }

  input[type="range"]::-moz-range-thumb {
    width: 16px;
    height: 16px;
    background: var(--accent);
    cursor: pointer;
    border-radius: 50%;
    border: 3px solid var(--paper);
  }

  .ticks {
    display: flex;
    justify-content: space-between;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    margin-top: 4px;
  }

  .hint {
    font-size: 14px;
    color: var(--muted);
    font-style: italic;
  }

  .slider-row {
    margin-top: 48px;
    padding-top: 32px;
    border-top: 1px solid rgba(42, 36, 31, 0.15);
    display: flex;
    flex-direction: column;
    gap: 14px;
  }

  .slider-row .control-label {
    font-size: 12px;
  }

  .slider-row .control-value {
    font-size: 40px;
  }

  .slider-row input[type="range"] {
    height: 3px;
  }

  .slider-row input[type="range"]::-webkit-slider-thumb {
    width: 26px;
    height: 26px;
  }

  .slider-row input[type="range"]::-moz-range-thumb {
    width: 22px;
    height: 22px;
  }

  .stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
    padding-top: 24px;
    border-top: 1px solid rgba(42, 36, 31, 0.15);
  }

  .stat-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 2px;
  }

  .stat-value {
    font-family: 'Fraunces', serif;
    font-size: 22px;
    font-feature-settings: "tnum";
  }

  .stat-value em {
    font-style: italic;
    color: var(--accent);
  }
</style>
</head>
<body>

<div class="container">
  <h1>El caballo en <em>cadena de Markov</em></h1>
  <div class="subtitle">Probabilidad de estar en cada casilla después de n pasos</div>

  <div class="layout">
    <div>
      <div class="board-wrap">
        <div class="heatmap-board" id="board"></div>
      </div>
      <div class="legend">
        <span>0</span>
        <div class="gradient-bar"></div>
        <span id="legend-max">max</span>
      </div>
    </div>

    <div class="controls">
      <div class="control-group">
        <div class="control-label">
          <span>Posición inicial</span>
          <span class="control-value" id="start-label">a1</span>
        </div>
        <p class="hint">Haz clic en cualquier casilla del tablero para cambiar el origen.</p>
      </div>

      <div class="stats">
        <div>
          <div class="stat-label">Casillas con p &gt; 0</div>
          <div class="stat-value" id="stat-nonzero">—</div>
        </div>
        <div>
          <div class="stat-label">¿Llega a a8?</div>
          <div class="stat-value" id="stat-reach">—</div>
        </div>
      </div>
    </div>
  </div>

  <div class="slider-row">
    <div class="control-label">
      <span>Movimientos · n</span>
      <span class="control-value" id="n-value">1</span>
    </div>
    <input type="range" id="slider-n" min="1" max="25" value="1">
    <div class="ticks">
      <span>1</span><span>5</span><span>10</span><span>15</span><span>20</span><span>25</span>
    </div>
  </div>
</div>

<script>
function movimientosPosibles(x, y) {
  const movs = [[2,1],[2,-1],[1,2],[1,-2],[-2,1],[-2,-1],[-1,2],[-1,-2]];
  const factibles = [];
  for (const [dx, dy] of movs) {
    const nx = x + dx, ny = y + dy;
    if (nx >= 0 && nx <= 7 && ny >= 0 && ny <= 7) factibles.push([nx, ny]);
  }
  return factibles;
}

const P = Array.from({length: 64}, () => new Float64Array(64));
for (let pos = 0; pos < 64; pos++) {
  const row = Math.floor(pos / 8), col = pos % 8;
  const factibles = movimientosPosibles(row, col);
  const n = factibles.length;
  for (const [r, c] of factibles) P[pos][r * 8 + c] = 1 / n;
}

function matMul(A, B) {
  const C = Array.from({length: 64}, () => new Float64Array(64));
  for (let i = 0; i < 64; i++) {
    const Ai = A[i], Ci = C[i];
    for (let k = 0; k < 64; k++) {
      const aik = Ai[k];
      if (aik === 0) continue;
      const Bk = B[k];
      for (let j = 0; j < 64; j++) Ci[j] += aik * Bk[j];
    }
  }
  return C;
}

const powers = [null, P];
for (let n = 2; n <= 25; n++) powers[n] = matMul(powers[n-1], P);

const files = ['a','b','c','d','e','f','g','h'];
const posToAlgebraic = (pos) => files[pos % 8] + (Math.floor(pos / 8) + 1);
const visualToPos = (vrow, vcol) => (7 - vrow) * 8 + vcol;

function heatColor(value, max) {
  if (max === 0) return 'rgb(248, 244, 233)';
  const t = Math.max(0, Math.min(1, value / max));
  const stops = [[248,244,233],[234,182,118],[194,65,12],[124,45,18]];
  const interp = (a,b,t) => a.map((v,i) => Math.round(v + (b[i]-v)*t));
  let c;
  if (t < 0.33) c = interp(stops[0], stops[1], t / 0.33);
  else if (t < 0.66) c = interp(stops[1], stops[2], (t - 0.33) / 0.33);
  else c = interp(stops[2], stops[3], (t - 0.66) / 0.34);
  return `rgb(${c[0]}, ${c[1]}, ${c[2]})`;
}

const getTextColor = (value, max) => (max === 0 || value / max <= 0.5) ? '#1a1613' : '#f4efe6';

const board = document.getElementById('board');
let currentStart = 0;
let currentN = 1;

for (let vrow = 0; vrow < 8; vrow++) {
  for (let vcol = 0; vcol < 8; vcol++) {
    const pos = visualToPos(vrow, vcol);
    const cell = document.createElement('div');
    cell.className = 'heat-cell';
    cell.dataset.pos = pos;
    cell.innerHTML = '<span class="prob-label"></span>';
    cell.addEventListener('click', () => {
      currentStart = pos;
      document.getElementById('start-label').textContent = posToAlgebraic(pos);
      update();
    });
    board.appendChild(cell);
  }
}

function update() {
  const dist = powers[currentN][currentStart];
  const max = Math.max(...dist);

  let nonzero = 0;
  for (let i = 0; i < 64; i++) {
    if (dist[i] > 0) nonzero++;
  }

  // Posición a8 = columna 0, fila 7 → 7*8 + 0 = 56
  const a8Prob = dist[56];

  board.querySelectorAll('.heat-cell').forEach(cell => {
    const pos = parseInt(cell.dataset.pos);
    const val = dist[pos];
    cell.style.backgroundColor = heatColor(val, max);
    cell.style.color = getTextColor(val, max);
    const label = cell.querySelector('.prob-label');
    label.textContent = val === 0 ? '' : (val * 100).toFixed(1) + '%';
    cell.classList.toggle('start-cell', pos === currentStart);
  });

  document.getElementById('n-value').textContent = currentN;
  document.getElementById('stat-nonzero').textContent = `${nonzero}/64`;
  document.getElementById('stat-reach').textContent = a8Prob > 0 ? 'sí' : 'no';
  document.getElementById('legend-max').textContent = (max * 100).toFixed(1) + '%';
}

document.getElementById('slider-n').addEventListener('input', (e) => {
  currentN = parseInt(e.target.value);
  update();
});

update();
</script>

</body>
</html>
