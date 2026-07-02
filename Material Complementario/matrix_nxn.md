<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Matrix Power NxN</title>
<style>
  * { box-sizing: border-box; }
  body { font-family: monospace; background: #1a1a2e; color: #eee; padding: 20px; margin: 0; }
  h1 { color: #a8d8ea; text-align: center; margin-bottom: 4px; }

  /* Size selector */
  .size-selector { display: flex; justify-content: center; gap: 12px; margin-bottom: 18px; }
  .size-btn {
    background: #2d3561; color: #eee; border: 2px solid #2d3561;
    padding: 7px 22px; border-radius: 6px; cursor: pointer; font-size: 1em; font-family: monospace;
  }
  .size-btn.active { border-color: #a8d8ea; color: #a8d8ea; background: #16213e; }
  .size-btn:hover { border-color: #74b9ff; }

  .top-row { display: flex; justify-content: center; gap: 32px; align-items: flex-start; margin-bottom: 14px; flex-wrap: wrap; }

  /* Editor */
  .p-editor { background: #16213e; border-radius: 10px; padding: 14px 20px; text-align: center; }
  .p-editor h3 { color: #f7d794; margin: 0 0 10px; font-size: 0.95em; }
  .p-editor-inner { display: flex; align-items: center; gap: 8px; }
  .p-bracket { font-size: 2.2em; color: #a8d8ea; line-height: 1; }
  .p-grid { display: grid; gap: 5px; }
  .p-input {
    width: 58px; padding: 4px 5px; background: #2d3561; color: #fff;
    border: 1px solid #555; border-radius: 4px; font-size: 0.9em;
    font-family: monospace; text-align: center;
  }
  .p-input:focus { outline: none; border-color: #a8d8ea; }
  .p-input.invalid { border-color: #e17055; }
  .row-btns { display: flex; justify-content: center; gap: 10px; margin-top: 8px; }
  .apply-btn {
    background: #a8d8ea; color: #1a1a2e; border: none;
    padding: 5px 16px; border-radius: 6px; cursor: pointer; font-size: 0.88em; font-weight: bold;
  }
  .apply-btn:hover { background: #f7d794; }
  .rand-btn {
    background: #2d3561; color: #eee; border: 1px solid #74b9ff;
    padding: 5px 12px; border-radius: 6px; cursor: pointer; font-size: 0.88em;
  }
  .rand-btn:hover { background: #74b9ff; color: #1a1a2e; }

  /* Result matrix */
  .result-wrap { display: flex; flex-direction: column; align-items: center; }
  .result-wrap h3 { color: #f7d794; margin: 0 0 8px; font-size: 0.95em; text-align: center; }
  .hint { color: #888; font-size: 0.78em; margin-bottom: 6px; }
  .matrix-display { display: flex; align-items: center; font-size: 1.1em; }
  .matrix-box { border-left: 3px solid #a8d8ea; border-right: 3px solid #a8d8ea; padding: 8px 16px; }
  .matrix-row { display: flex; gap: 6px; justify-content: center; margin: 3px 0; }
  .cell {
    width: 86px; text-align: right; cursor: pointer; padding: 3px 6px; border-radius: 4px;
    border: 2px solid transparent; transition: all 0.2s; font-size: 0.92em;
  }
  .cell:hover { background: #2d3561; }
  .cell.selected { border-color: var(--sel-color, #f7d794); background: #2d3561; font-weight: bold; }
  .cell.maxed { cursor: not-allowed; opacity: 0.5; }
  .cell.maxed:hover { background: transparent; }

  /* Controls */
  .controls { text-align: center; margin: 10px 0; }
  input[type=range] { width: 380px; accent-color: #a8d8ea; }
  .n-label { font-size: 1.3em; color: #f7d794; margin: 0 8px; }
  .anim-btn {
    background: #a8d8ea; color: #1a1a2e; border: none;
    padding: 7px 20px; border-radius: 6px; cursor: pointer; font-size: 0.95em; font-weight: bold; margin-left: 12px;
  }
  .anim-btn:hover { background: #f7d794; }

  /* Zoom */
  .zoom-controls { text-align: center; margin: 6px 0; display: flex; justify-content: center; gap: 8px; align-items: center; }
  .zoom-btn {
    background: #2d3561; color: #eee; border: 1px solid #a8d8ea;
    width: 30px; height: 30px; border-radius: 6px; cursor: pointer; font-size: 1.05em;
  }
  .zoom-btn:hover { background: #a8d8ea; color: #1a1a2e; }
  .zoom-info { color: #aaa; font-size: 0.82em; }

  /* Chart */
  .chart-wrap { max-width: 860px; margin: 0 auto; }
  canvas { display: block; width: 100%; border-radius: 8px; cursor: crosshair; }

  /* Legend / selection panel */
  .sel-panel { max-width: 860px; margin: 10px auto 0; background: #16213e; border-radius: 8px; padding: 12px 16px; }
  .sel-panel-title { color: #aaa; font-size: 0.82em; margin-bottom: 8px; }
  .sel-chips { display: flex; flex-wrap: wrap; gap: 6px; }
  .chip {
    padding: 4px 10px; border-radius: 12px; border: 2px solid #2d3561;
    cursor: pointer; font-size: 0.8em; background: #2d3561; transition: all 0.15s;
    user-select: none;
  }
  .chip:hover { border-color: #74b9ff; }
  .chip.active { border-color: var(--chip-color); background: color-mix(in srgb, var(--chip-color) 20%, #16213e); font-weight: bold; }
  .chip.maxed-chip { opacity: 0.4; cursor: not-allowed; }
  .sel-counter { color: #888; font-size: 0.8em; margin-top: 8px; }

  /* Tooltip */
  #tooltip {
    position: fixed; background: #0f1629; border: 1px solid #a8d8ea;
    padding: 7px 13px; border-radius: 7px; font-size: 0.82em;
    pointer-events: none; display: none; z-index: 100; line-height: 1.6;
  }
</style>
</head>
<body>

<h1>P<sup>n</sup> — Matriz NxN</h1>

<!-- Size toggle -->
<div class="size-selector">
  <button class="size-btn" data-size="3">3×3</button>
  <button class="size-btn active" data-size="4">4×4</button>
</div>

<div class="top-row">
  <!-- Editor -->
  <div class="p-editor">
    <h3>Matriz P (editable)</h3>
    <div class="p-editor-inner">
      <span class="p-bracket">(</span>
      <div class="p-grid" id="pGrid"></div>
      <span class="p-bracket">)</span>
    </div>
    <div id="p-error" style="color:#e17055;font-size:0.78em;min-height:16px;margin-top:4px;"></div>
    <div class="row-btns">
      <button class="apply-btn" id="applyBtn">Aplicar</button>
      <button class="rand-btn" id="randBtn">Aleatoria</button>
    </div>
  </div>

  <!-- Result -->
  <div class="result-wrap">
    <h3>P<sup id="expLabel">1</sup></h3>
    <div class="hint">Click en celda para agregar al gráfico (máx 4)</div>
    <div class="matrix-display">
      <div class="matrix-box" id="matBox"></div>
    </div>
  </div>
</div>

<!-- Slider -->
<div class="controls">
  <span class="n-label">n =</span>
  <input type="range" id="slider" min="1" max="50" value="1">
  <span class="n-label" id="nVal">1</span>
  <button class="anim-btn" id="animBtn">▶ Animar</button>
</div>

<!-- Zoom -->
<div class="zoom-controls">
  <button class="zoom-btn" id="zoomIn">+</button>
  <button class="zoom-btn" id="zoomOut">−</button>
  <button class="zoom-btn" id="zoomReset">⟳</button>
  <span class="zoom-info" id="zoomInfo">rango: n 1–50</span>
  <span class="zoom-info" style="color:#444">| scroll sobre gráfico</span>
</div>

<!-- Chart -->
<div class="chart-wrap">
  <canvas id="chart" width="860" height="340"></canvas>
</div>

<!-- Selection panel -->
<div class="sel-panel">
  <div class="sel-panel-title">Seleccionar valores a mostrar en gráfico — <span id="selCounter">0</span>/4 seleccionados</div>
  <div class="sel-chips" id="selChips"></div>
</div>

<div id="tooltip"></div>

<script>
const MAX_N = 50;
const COLORS = ['#e17055','#74b9ff','#55efc4','#fdcb6e'];

// Default matrices
const DEFAULTS = {
  3: [
    [0, 0, 0],
    [0, 0, 0],
    [0, 0, 0]
  ],
  4: [
    [0, 0, 0, 0],
    [0, 0, 0, 0],
    [0, 0, 0, 0],
    [0, 0, 0, 0]
  ]
};

let DIM = 4;
let P = DEFAULTS[DIM].map(r => [...r]);
let powers = [];
let selected = []; // array of {r,c} max 4, in order of selection
let zStart = 1, zEnd = MAX_N;

// --- Matrix math ---
function matMul(A, B) {
  const n = A.length;
  return Array.from({length: n}, (_, i) =>
    Array.from({length: n}, (_, j) =>
      A[i].reduce((s, _, k) => s + A[i][k] * B[k][j], 0)
    )
  );
}

function recompute() {
  powers = [null];
  let M = P.map(r => [...r]);
  powers.push(M);
  for (let n = 2; n <= MAX_N; n++) {
    M = matMul(powers[n-1], P);
    powers.push(M);
  }
}

// --- Selection helpers ---
function selKey(r, c) { return `${r},${c}`; }
function isSelected(r, c) { return selected.some(s => s.r === r && s.c === c); }
function selIndex(r, c) { return selected.findIndex(s => s.r === r && s.c === c); }
function selColor(r, c) {
  const idx = selIndex(r, c);
  return idx >= 0 ? COLORS[idx] : null;
}

function toggleSelection(r, c) {
  const idx = selIndex(r, c);
  if (idx >= 0) {
    selected.splice(idx, 1);
  } else {
    if (selected.length >= 4) return false;
    selected.push({r, c});
  }
  return true;
}

// --- Build editor grid ---
function buildEditor() {
  const grid = document.getElementById('pGrid');
  grid.style.gridTemplateColumns = `repeat(${DIM}, 1fr)`;
  grid.innerHTML = '';
  for (let r = 0; r < DIM; r++) {
    for (let c = 0; c < DIM; c++) {
      const inp = document.createElement('input');
      inp.type = 'text';
      inp.className = 'p-input';
      inp.id = `p${r}${c}`;
      inp.value = P[r][c].toFixed(2);
      inp.addEventListener('keydown', e => { if (e.key === 'Enter') document.getElementById('applyBtn').click(); });
      grid.appendChild(inp);
    }
  }
}

// --- Build result matrix ---
function buildResultMatrix() {
  const box = document.getElementById('matBox');
  box.innerHTML = '';
  for (let r = 0; r < DIM; r++) {
    const row = document.createElement('div');
    row.className = 'matrix-row';
    for (let c = 0; c < DIM; c++) {
      const cell = document.createElement('span');
      cell.className = 'cell';
      cell.id = `cell_${r}_${c}`;
      cell.dataset.r = r;
      cell.dataset.c = c;
      cell.addEventListener('click', () => {
        const wasSelected = isSelected(r, c);
        if (!wasSelected && selected.length >= 4) return;
        toggleSelection(r, c);
        // sync chip panel
        buildChips();
        update(+document.getElementById('slider').value);
      });
      row.appendChild(cell);
    }
    box.appendChild(row);
  }
}

function updateResultMatrix(n) {
  const mat = powers[n];
  document.getElementById('expLabel').textContent = n;
  document.getElementById('nVal').textContent = n;
  for (let r = 0; r < DIM; r++) {
    for (let c = 0; c < DIM; c++) {
      const el = document.getElementById(`cell_${r}_${c}`);
      el.textContent = mat[r][c].toFixed(5);
      const color = selColor(r, c);
      if (color) {
        el.style.setProperty('--sel-color', color);
        el.className = 'cell selected';
      } else if (selected.length >= 4) {
        el.className = 'cell maxed';
        el.style.removeProperty('--sel-color');
      } else {
        el.className = 'cell';
        el.style.removeProperty('--sel-color');
      }
    }
  }
}

// --- Chip panel ---
function buildChips() {
  const container = document.getElementById('selChips');
  container.innerHTML = '';
  for (let r = 0; r < DIM; r++) {
    for (let c = 0; c < DIM; c++) {
      const chip = document.createElement('span');
      chip.className = 'chip';
      chip.textContent = `P[${r}][${c}]`;
      const isSel = isSelected(r, c);
      const color = selColor(r, c);
      if (isSel && color) {
        chip.classList.add('active');
        chip.style.setProperty('--chip-color', color);
      } else if (!isSel && selected.length >= 4) {
        chip.classList.add('maxed-chip');
      }
      chip.addEventListener('click', () => {
        if (!isSelected(r, c) && selected.length >= 4) return;
        toggleSelection(r, c);
        buildChips();
        update(+document.getElementById('slider').value);
      });
      container.appendChild(chip);
    }
  }
  document.getElementById('selCounter').textContent = selected.length;
}

// --- Chart ---
const canvas = document.getElementById('chart');
const ctx = canvas.getContext('2d');
const PAD = { top: 24, bottom: 44, left: 60, right: 24 };

function nToX(n, W) {
  const cW = W - PAD.left - PAD.right;
  return PAD.left + ((n - zStart) / (zEnd - zStart)) * cW;
}

let yMin = 0, yMax = 1;
function computeYRange() {
  if (selected.length === 0) { yMin = 0; yMax = 1; return; }
  let mn = Infinity, mx = -Infinity;
  selected.forEach(({r, c}) => {
    for (let i = zStart - 1; i < zEnd; i++) {
      mn = Math.min(mn, powers[i+1][r][c]);
      mx = Math.max(mx, powers[i+1][r][c]);
    }
  });
  const pad = (mx - mn) * 0.12 || 0.05;
  yMin = Math.max(0, mn - pad);
  yMax = Math.min(1, mx + pad);
}

function valToY(v, H) {
  const cH = H - PAD.top - PAD.bottom;
  return PAD.top + (1 - (v - yMin) / (yMax - yMin)) * cH;
}

function drawChart(n) {
  const W = canvas.width, H = canvas.height;
  const cW = W - PAD.left - PAD.right;
  const cH = H - PAD.top - PAD.bottom;

  computeYRange();
  ctx.clearRect(0, 0, W, H);
  ctx.fillStyle = '#16213e';
  ctx.fillRect(0, 0, W, H);

  // Y grid
  const ySteps = 5;
  for (let i = 0; i <= ySteps; i++) {
    const v = yMin + (yMax - yMin) * (1 - i / ySteps);
    const y = PAD.top + (i / ySteps) * cH;
    ctx.strokeStyle = '#2d3561'; ctx.lineWidth = 1;
    ctx.beginPath(); ctx.moveTo(PAD.left, y); ctx.lineTo(PAD.left + cW, y); ctx.stroke();
    ctx.fillStyle = '#aaa'; ctx.font = '11px monospace'; ctx.textAlign = 'right';
    ctx.fillText(v.toFixed(3), PAD.left - 5, y + 4);
  }

  // X grid + labels
  const xRange = zEnd - zStart;
  const xStep = xRange <= 10 ? 1 : xRange <= 25 ? 5 : 10;
  for (let x = zStart; x <= zEnd; x++) {
    if ((x - 1) % xStep !== 0 && x !== zStart && x !== zEnd) continue;
    const px = nToX(x, W);
    ctx.strokeStyle = '#2d3561'; ctx.lineWidth = 0.5;
    ctx.beginPath(); ctx.moveTo(px, PAD.top); ctx.lineTo(px, PAD.top + cH); ctx.stroke();
    ctx.fillStyle = '#aaa'; ctx.textAlign = 'center'; ctx.font = '11px monospace';
    ctx.fillText(x, px, H - PAD.bottom + 16);
  }
  ctx.fillStyle = '#aaa'; ctx.textAlign = 'center';
  ctx.fillText('n (potencia)', PAD.left + cW / 2, H - 4);

  if (selected.length === 0) {
    ctx.fillStyle = '#555'; ctx.textAlign = 'center'; ctx.font = '14px monospace';
    ctx.fillText('Selecciona celdas abajo o en la matriz', PAD.left + cW / 2, PAD.top + cH / 2);
    return;
  }

  // Clip
  ctx.save();
  ctx.beginPath();
  ctx.rect(PAD.left, PAD.top, cW, cH);
  ctx.clip();

  // Lines
  selected.forEach(({r, c}, si) => {
    const color = COLORS[si];
    ctx.beginPath();
    ctx.strokeStyle = color;
    ctx.lineWidth = 2.5;
    let first = true;
    for (let i = zStart - 1; i < zEnd; i++) {
      const px = nToX(i + 1, W);
      const py = valToY(powers[i+1][r][c], H);
      first ? ctx.moveTo(px, py) : ctx.lineTo(px, py);
      first = false;
    }
    ctx.stroke();
  });
  ctx.restore();

  // Cursor
  if (n >= zStart && n <= zEnd) {
    const cx2 = nToX(n, W);
    ctx.strokeStyle = '#ffffff88'; ctx.lineWidth = 1.5; ctx.setLineDash([4, 3]);
    ctx.beginPath(); ctx.moveTo(cx2, PAD.top); ctx.lineTo(cx2, PAD.top + cH); ctx.stroke();
    ctx.setLineDash([]);

    selected.forEach(({r, c}, si) => {
      const py = valToY(powers[n][r][c], H);
      ctx.beginPath();
      ctx.arc(cx2, py, 6, 0, Math.PI * 2);
      ctx.fillStyle = COLORS[si];
      ctx.fill();
      ctx.strokeStyle = '#fff'; ctx.lineWidth = 1.5;
      ctx.stroke();
    });
  }
}

function update(n) {
  updateResultMatrix(n);
  drawChart(n);
}

// --- Zoom ---
function clampZoom() {
  zStart = Math.max(1, Math.min(zStart, MAX_N - 1));
  zEnd = Math.max(zStart + 1, Math.min(zEnd, MAX_N));
  document.getElementById('zoomInfo').textContent = `rango: n ${zStart}–${zEnd}`;
}

document.getElementById('zoomIn').addEventListener('click', () => {
  const mid = Math.round((zStart + zEnd) / 2);
  const half = Math.max(2, Math.round((zEnd - zStart) / 4));
  zStart = mid - half; zEnd = mid + half;
  clampZoom(); update(+slider.value);
});
document.getElementById('zoomOut').addEventListener('click', () => {
  const mid = Math.round((zStart + zEnd) / 2);
  const half = Math.round((zEnd - zStart));
  zStart = mid - half; zEnd = mid + half;
  clampZoom(); update(+slider.value);
});
document.getElementById('zoomReset').addEventListener('click', () => {
  zStart = 1; zEnd = MAX_N;
  clampZoom(); update(+slider.value);
});

canvas.addEventListener('wheel', (e) => {
  e.preventDefault();
  const rect = canvas.getBoundingClientRect();
  const mx = (e.clientX - rect.left) * (canvas.width / rect.width);
  const frac = Math.max(0, Math.min(1, (mx - PAD.left) / (canvas.width - PAD.left - PAD.right)));
  const focusN = zStart + frac * (zEnd - zStart);
  const factor = e.deltaY > 0 ? 1.25 : 0.8;
  const newRange = Math.max(2, Math.round((zEnd - zStart) * factor));
  zStart = Math.round(focusN - frac * newRange);
  zEnd = zStart + newRange;
  clampZoom(); update(+slider.value);
}, { passive: false });

// Tooltip
const tooltip = document.getElementById('tooltip');
canvas.addEventListener('mousemove', (e) => {
  if (selected.length === 0) { tooltip.style.display = 'none'; return; }
  const rect = canvas.getBoundingClientRect();
  const mx = (e.clientX - rect.left) * (canvas.width / rect.width);
  const cW = canvas.width - PAD.left - PAD.right;
  if (mx < PAD.left || mx > PAD.left + cW) { tooltip.style.display = 'none'; return; }
  const frac = (mx - PAD.left) / cW;
  const n = Math.round(zStart + frac * (zEnd - zStart));
  if (n < 1 || n > MAX_N) { tooltip.style.display = 'none'; return; }
  let html = `<b>n = ${n}</b><br>`;
  selected.forEach(({r, c}, si) => {
    html += `<span style="color:${COLORS[si]}">P[${r}][${c}]</span>: ${powers[n][r][c].toFixed(6)}<br>`;
  });
  tooltip.innerHTML = html;
  tooltip.style.display = 'block';
  tooltip.style.left = (e.clientX + 14) + 'px';
  tooltip.style.top = (e.clientY - 10) + 'px';
});
canvas.addEventListener('mouseleave', () => { tooltip.style.display = 'none'; });

// Slider
const slider = document.getElementById('slider');
slider.addEventListener('input', () => update(+slider.value));

// Animation
let animId = null, animN = 1;
const animBtn = document.getElementById('animBtn');
animBtn.addEventListener('click', () => {
  if (animId) { clearInterval(animId); animId = null; animBtn.textContent = '▶ Animar'; return; }
  animN = zStart;
  animBtn.textContent = '■ Parar';
  animId = setInterval(() => {
    slider.value = animN; update(animN); animN++;
    if (animN > zEnd) { clearInterval(animId); animId = null; animBtn.textContent = '▶ Animar'; }
  }, 80);
});

// Apply
document.getElementById('applyBtn').addEventListener('click', () => {
  const vals = [];
  let hasError = false;
  for (let r = 0; r < DIM; r++) {
    for (let c = 0; c < DIM; c++) {
      const el = document.getElementById(`p${r}${c}`);
      const v = parseFloat(el.value);
      el.classList.toggle('invalid', isNaN(v) || v < 0 || v > 1);
      if (isNaN(v) || v < 0 || v > 1) hasError = true;
      vals.push(v);
    }
  }
  const errEl = document.getElementById('p-error');
  if (hasError) { errEl.textContent = 'Valores deben ser 0–1'; return; }
  errEl.textContent = '';
  P = Array.from({length: DIM}, (_, r) => Array.from({length: DIM}, (_, c) => vals[r * DIM + c]));
  // Remove selections that are out of range (shouldn't happen but be safe)
  selected = selected.filter(s => s.r < DIM && s.c < DIM);
  recompute();
  zStart = 1; zEnd = MAX_N; clampZoom();
  buildChips();
  update(+slider.value);
});

// Random matrix (row-stochastic)
document.getElementById('randBtn').addEventListener('click', () => {
  const newP = Array.from({length: DIM}, () => {
    const row = Array.from({length: DIM}, () => Math.random());
    const sum = row.reduce((a, b) => a + b, 0);
    return row.map(v => v / sum);
  });
  P = newP;
  for (let r = 0; r < DIM; r++)
    for (let c = 0; c < DIM; c++)
      document.getElementById(`p${r}${c}`).value = P[r][c].toFixed(3);
  recompute();
  buildChips();
  update(+slider.value);
});

// Size toggle
document.querySelectorAll('.size-btn').forEach(btn => {
  btn.addEventListener('click', () => {
    DIM = +btn.dataset.size;
    document.querySelectorAll('.size-btn').forEach(b => b.classList.toggle('active', b === btn));
    P = DEFAULTS[DIM].map(r => [...r]);
    selected = [];
    recompute();
    buildEditor();
    buildResultMatrix();
    buildChips();
    zStart = 1; zEnd = MAX_N; clampZoom();
    update(1);
    slider.value = 1;
  });
});

// Init
recompute();
buildEditor();
buildResultMatrix();
buildChips();
update(1);
</script>
</body>
</html>
