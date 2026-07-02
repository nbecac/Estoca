<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Matrix Power Evolution</title>
<style>
  * { box-sizing: border-box; }
  body { font-family: monospace; background: #1a1a2e; color: #eee; padding: 20px; margin: 0; }
  h1 { color: #a8d8ea; text-align: center; margin-bottom: 4px; }

  /* Layout */
  .top-row { display: flex; justify-content: center; gap: 40px; align-items: flex-start; margin-bottom: 16px; flex-wrap: wrap; }

  /* Editable matrix P */
  .p-editor { background: #16213e; border-radius: 10px; padding: 16px 24px; text-align: center; }
  .p-editor h3 { color: #f7d794; margin: 0 0 10px; font-size: 1em; }
  .p-editor-inner { display: flex; align-items: center; gap: 8px; }
  .p-bracket { font-size: 2.4em; color: #a8d8ea; line-height: 1; }
  .p-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 6px; }
  .p-input {
    width: 64px; padding: 5px 6px; background: #2d3561; color: #fff;
    border: 1px solid #a8d8ea; border-radius: 4px; font-size: 1em;
    font-family: monospace; text-align: center;
  }
  .p-input:focus { outline: none; border-color: #f7d794; }
  .p-input.invalid { border-color: #e17055; }
  .apply-btn {
    margin-top: 10px; background: #a8d8ea; color: #1a1a2e; border: none;
    padding: 6px 18px; border-radius: 6px; cursor: pointer; font-size: 0.9em; font-weight: bold;
  }
  .apply-btn:hover { background: #f7d794; }

  /* Matrix result display */
  .matrix-display { display: flex; justify-content: center; align-items: center; font-size: 1.4em; }
  .matrix-box { border-left: 3px solid #a8d8ea; border-right: 3px solid #a8d8ea; padding: 10px 24px; }
  .matrix-row { display: flex; gap: 30px; justify-content: center; }
  .cell { width: 90px; text-align: right; transition: color 0.3s, font-weight 0.3s; cursor: pointer; border-radius: 4px; padding: 2px 4px; }
  .cell:hover { background: #2d3561; }
  .cell.selected { background: #2d3561; outline: 2px solid #f7d794; }
  .cell.hot { color: #e17055; }
  .cell.cold { color: #74b9ff; }

  /* Controls */
  .controls { text-align: center; margin: 12px 0; }
  input[type=range] { width: 400px; accent-color: #a8d8ea; }
  .n-label { font-size: 1.4em; color: #f7d794; margin: 0 10px; }
  .anim-btn {
    background: #a8d8ea; color: #1a1a2e; border: none;
    padding: 8px 24px; border-radius: 6px; cursor: pointer;
    font-size: 1em; font-weight: bold; margin-left: 16px;
  }
  .anim-btn:hover { background: #f7d794; }

  /* Chart area */
  .chart-wrap { position: relative; width: 100%; max-width: 860px; margin: 0 auto; }
  canvas { display: block; width: 100%; border-radius: 8px; }

  /* Zoom controls */
  .zoom-controls { text-align: center; margin: 8px 0; display: flex; justify-content: center; gap: 10px; align-items: center; }
  .zoom-btn {
    background: #2d3561; color: #eee; border: 1px solid #a8d8ea;
    width: 32px; height: 32px; border-radius: 6px; cursor: pointer; font-size: 1.1em;
  }
  .zoom-btn:hover { background: #a8d8ea; color: #1a1a2e; }
  .zoom-info { color: #aaa; font-size: 0.85em; }

  /* Legend */
  .legend { display: flex; justify-content: center; gap: 20px; margin-top: 8px; font-size: 0.85em; flex-wrap: wrap; }
  .legend-item { cursor: pointer; padding: 3px 8px; border-radius: 4px; border: 2px solid transparent; transition: border 0.2s; }
  .legend-item.selected { border-color: #f7d794; }
  .legend-item.muted { opacity: 0.35; }
  .dot { display: inline-block; width: 12px; height: 12px; border-radius: 50%; margin-right: 5px; }

  /* Tooltip */
  #tooltip {
    position: fixed; background: #16213e; border: 1px solid #a8d8ea;
    padding: 6px 12px; border-radius: 6px; font-size: 0.85em;
    pointer-events: none; display: none; z-index: 100;
  }
</style>
</head>
<body>

<h1>P<sup>n</sup> — Evolución de la Matriz</h1>

<div class="top-row">
  <!-- Editable P -->
  <div class="p-editor">
    <h3>Matriz P (editable)</h3>
    <div class="p-editor-inner">
      <span class="p-bracket">(</span>
      <div class="p-grid">
        <input class="p-input" id="p00" value="0.1">
        <input class="p-input" id="p01" value="0.9">
        <input class="p-input" id="p10" value="0.8">
        <input class="p-input" id="p11" value="0.2">
      </div>
      <span class="p-bracket">)</span>
    </div>
    <div id="p-error" style="color:#e17055; font-size:0.8em; min-height:18px; margin-top:4px;"></div>
    <button class="apply-btn" id="applyBtn">Aplicar</button>
  </div>

  <!-- P^n result -->
  <div>
    <div style="text-align:center; color:#aaa; margin-bottom:8px; font-size:0.9em;">
      Click en celda para resaltar en gráfico
    </div>
    <div class="matrix-display">
      <div style="margin-right:10px;">P<sup id="expLabel">1</sup> =</div>
      <div class="matrix-box">
        <div class="matrix-row">
          <span class="cell" id="c00" data-idx="0"></span>
          <span class="cell" id="c01" data-idx="1"></span>
        </div>
        <div class="matrix-row" style="margin-top:10px;">
          <span class="cell" id="c10" data-idx="2"></span>
          <span class="cell" id="c11" data-idx="3"></span>
        </div>
      </div>
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

<!-- Zoom controls -->
<div class="zoom-controls">
  <button class="zoom-btn" id="zoomIn">+</button>
  <button class="zoom-btn" id="zoomOut">−</button>
  <button class="zoom-btn" id="zoomReset" title="Reset zoom">⟳</button>
  <span class="zoom-info" id="zoomInfo">rango: n 1–50</span>
  <span class="zoom-info" style="color:#555">| scroll sobre gráfico para zoom</span>
</div>

<!-- Chart -->
<div class="chart-wrap">
  <canvas id="chart" width="860" height="340"></canvas>
</div>

<!-- Legend -->
<div class="legend" id="legend">
  <span class="legend-item" data-idx="0"><span class="dot" style="background:#e17055"></span>P[0][0]</span>
  <span class="legend-item" data-idx="1"><span class="dot" style="background:#74b9ff"></span>P[0][1]</span>
  <span class="legend-item" data-idx="2"><span class="dot" style="background:#55efc4"></span>P[1][0]</span>
  <span class="legend-item" data-idx="3"><span class="dot" style="background:#fdcb6e"></span>P[1][1]</span>
</div>

<div id="tooltip"></div>

<script>
const MAX_N = 50;
const COLORS = ['#e17055','#74b9ff','#55efc4','#fdcb6e'];
const LABELS = ['P[0][0]','P[0][1]','P[1][0]','P[1][1]'];

let P = [[0.1, 0.9], [0.8, 0.2]];
let powers = [];
let series = [[], [], [], []];
let selectedSeries = new Set([0, 1, 2, 3]);
let selectedCell = null; // index 0-3

// Zoom state: visible n range [zStart, zEnd]
let zStart = 1, zEnd = MAX_N;

function matMul(X, Y) {
  return [
    [X[0][0]*Y[0][0] + X[0][1]*Y[1][0], X[0][0]*Y[0][1] + X[0][1]*Y[1][1]],
    [X[1][0]*Y[0][0] + X[1][1]*Y[1][0], X[1][0]*Y[0][1] + X[1][1]*Y[1][1]]
  ];
}

function recompute() {
  powers = [null];
  let M = P.map(r => [...r]);
  powers.push(M);
  for (let n = 2; n <= MAX_N; n++) {
    M = matMul(powers[n-1], P);
    powers.push(M);
  }
  series = [[], [], [], []];
  for (let n = 1; n <= MAX_N; n++) {
    series[0].push(powers[n][0][0]);
    series[1].push(powers[n][0][1]);
    series[2].push(powers[n][1][0]);
    series[3].push(powers[n][1][1]);
  }
}

recompute();

const slider = document.getElementById('slider');
const nVal = document.getElementById('nVal');
const expLabel = document.getElementById('expLabel');
const canvas = document.getElementById('chart');
const ctx = canvas.getContext('2d');
const tooltip = document.getElementById('tooltip');

function colorClass(v) {
  if (v > 0.6) return 'hot';
  if (v < 0.3) return 'cold';
  return '';
}

function updateMatrix(n) {
  const mat = powers[n];
  const defs = [
    [mat[0][0], 'c00', 0], [mat[0][1], 'c01', 1],
    [mat[1][0], 'c10', 2], [mat[1][1], 'c11', 3]
  ];
  defs.forEach(([v, id, idx]) => {
    const el = document.getElementById(id);
    el.textContent = v.toFixed(6);
    el.className = 'cell ' + colorClass(v) + (selectedCell === idx ? ' selected' : '');
  });
  expLabel.textContent = n;
  nVal.textContent = n;
}

const PAD = { top: 24, bottom: 44, left: 54, right: 24 };

function nToX(n, W) {
  const cW = W - PAD.left - PAD.right;
  return PAD.left + ((n - zStart) / (zEnd - zStart)) * cW;
}

function valToY(v, H) {
  const cH = H - PAD.top - PAD.bottom;
  // Dynamic Y range from visible data
  return PAD.top + (1 - (v - yMin) / (yMax - yMin)) * cH;
}

let yMin = 0, yMax = 1;

function computeYRange() {
  let mn = Infinity, mx = -Infinity;
  series.forEach((s, si) => {
    if (!selectedSeries.has(si)) return;
    for (let i = zStart - 1; i < zEnd; i++) {
      mn = Math.min(mn, s[i]);
      mx = Math.max(mx, s[i]);
    }
  });
  if (!isFinite(mn)) { mn = 0; mx = 1; }
  const pad = (mx - mn) * 0.1 || 0.05;
  yMin = Math.max(0, mn - pad);
  yMax = Math.min(1, mx + pad);
}

function drawChart(n) {
  const W = canvas.width, H = canvas.height;
  const cW = W - PAD.left - PAD.right;
  const cH = H - PAD.top - PAD.bottom;

  computeYRange();

  ctx.clearRect(0, 0, W, H);
  ctx.fillStyle = '#16213e';
  ctx.fillRect(0, 0, W, H);

  // Grid Y
  const ySteps = 5;
  for (let i = 0; i <= ySteps; i++) {
    const v = yMin + (yMax - yMin) * (1 - i / ySteps);
    const y = PAD.top + (i / ySteps) * cH;
    ctx.strokeStyle = '#2d3561'; ctx.lineWidth = 1;
    ctx.beginPath(); ctx.moveTo(PAD.left, y); ctx.lineTo(PAD.left + cW, y); ctx.stroke();
    ctx.fillStyle = '#aaa'; ctx.font = '11px monospace'; ctx.textAlign = 'right';
    ctx.fillText(v.toFixed(3), PAD.left - 5, y + 4);
  }

  // Grid X
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

  // Clip to chart area
  ctx.save();
  ctx.beginPath();
  ctx.rect(PAD.left, PAD.top, cW, cH);
  ctx.clip();

  // Lines
  series.forEach((s, si) => {
    if (!selectedSeries.has(si)) return;
    const isFocus = selectedCell === si;
    ctx.beginPath();
    ctx.strokeStyle = COLORS[si];
    ctx.lineWidth = isFocus ? 3.5 : 1.8;
    ctx.globalAlpha = isFocus ? 1 : (selectedCell === null ? 0.85 : 0.25);
    let first = true;
    for (let i = zStart - 1; i < zEnd; i++) {
      const px = nToX(i + 1, W);
      const py = valToY(s[i], H);
      first ? ctx.moveTo(px, py) : ctx.lineTo(px, py);
      first = false;
    }
    ctx.stroke();
    ctx.globalAlpha = 1;
  });

  ctx.restore();

  // Cursor
  if (n >= zStart && n <= zEnd) {
    const cx2 = nToX(n, W);
    ctx.strokeStyle = '#fff'; ctx.lineWidth = 1.5; ctx.setLineDash([4, 3]);
    ctx.beginPath(); ctx.moveTo(cx2, PAD.top); ctx.lineTo(cx2, PAD.top + cH); ctx.stroke();
    ctx.setLineDash([]);

    series.forEach((s, si) => {
      if (!selectedSeries.has(si)) return;
      const v = s[n - 1];
      const py = valToY(v, H);
      ctx.beginPath();
      ctx.arc(cx2, py, si === selectedCell ? 7 : 5, 0, Math.PI * 2);
      ctx.fillStyle = COLORS[si];
      ctx.globalAlpha = selectedCell === null || selectedCell === si ? 1 : 0.3;
      ctx.fill();
      ctx.globalAlpha = 1;
    });
  }
}

function update(n) {
  updateMatrix(n);
  drawChart(n);
}

// Zoom helpers
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

// Scroll to zoom on canvas
canvas.addEventListener('wheel', (e) => {
  e.preventDefault();
  const rect = canvas.getBoundingClientRect();
  const cW = canvas.width - PAD.left - PAD.right;
  const mouseX = (e.clientX - rect.left) * (canvas.width / rect.width);
  const frac = Math.max(0, Math.min(1, (mouseX - PAD.left) / cW));
  const focusN = zStart + frac * (zEnd - zStart);

  const factor = e.deltaY > 0 ? 1.25 : 0.8;
  const newRange = Math.max(2, Math.round((zEnd - zStart) * factor));
  zStart = Math.round(focusN - frac * newRange);
  zEnd = zStart + newRange;
  clampZoom();
  update(+slider.value);
}, { passive: false });

// Hover tooltip on canvas
canvas.addEventListener('mousemove', (e) => {
  const rect = canvas.getBoundingClientRect();
  const mx = (e.clientX - rect.left) * (canvas.width / rect.width);
  const my = (e.clientY - rect.top) * (canvas.height / rect.height);
  const cW = canvas.width - PAD.left - PAD.right;
  if (mx < PAD.left || mx > PAD.left + cW) { tooltip.style.display = 'none'; return; }

  const frac = (mx - PAD.left) / cW;
  const n = Math.round(zStart + frac * (zEnd - zStart));
  if (n < 1 || n > MAX_N) { tooltip.style.display = 'none'; return; }

  let html = `<b>n = ${n}</b><br>`;
  series.forEach((s, si) => {
    if (!selectedSeries.has(si)) return;
    html += `<span style="color:${COLORS[si]}">${LABELS[si]}</span>: ${s[n-1].toFixed(6)}<br>`;
  });
  tooltip.innerHTML = html;
  tooltip.style.display = 'block';
  tooltip.style.left = (e.clientX + 14) + 'px';
  tooltip.style.top = (e.clientY - 10) + 'px';
});
canvas.addEventListener('mouseleave', () => { tooltip.style.display = 'none'; });

// Slider
slider.addEventListener('input', () => update(+slider.value));

// Cell selection
document.querySelectorAll('.cell').forEach(el => {
  el.addEventListener('click', () => {
    const idx = +el.dataset.idx;
    selectedCell = selectedCell === idx ? null : idx;
    update(+slider.value);
    updateLegend();
  });
});

// Legend click = toggle series visibility
function updateLegend() {
  document.querySelectorAll('.legend-item').forEach(el => {
    const idx = +el.dataset.idx;
    el.classList.toggle('muted', !selectedSeries.has(idx));
    el.classList.toggle('selected', selectedCell === idx);
  });
}

document.querySelectorAll('.legend-item').forEach(el => {
  el.addEventListener('click', () => {
    const idx = +el.dataset.idx;
    if (selectedSeries.has(idx) && selectedSeries.size > 1) selectedSeries.delete(idx);
    else selectedSeries.add(idx);
    // Also set as selected cell for highlight
    selectedCell = selectedCell === idx ? null : idx;
    updateLegend();
    update(+slider.value);
  });
});

// Apply edited P matrix
document.getElementById('applyBtn').addEventListener('click', () => {
  const ids = ['p00','p01','p10','p11'];
  const vals = ids.map(id => parseFloat(document.getElementById(id).value));
  const errEl = document.getElementById('p-error');

  ids.forEach((id, i) => {
    const el = document.getElementById(id);
    el.classList.toggle('invalid', isNaN(vals[i]) || vals[i] < 0 || vals[i] > 1);
  });

  if (vals.some(v => isNaN(v) || v < 0 || v > 1)) {
    errEl.textContent = 'Valores deben ser 0–1'; return;
  }
  errEl.textContent = '';

  P = [[vals[0], vals[1]], [vals[2], vals[3]]];
  recompute();
  zStart = 1; zEnd = MAX_N;
  clampZoom();
  update(+slider.value);
});

// Enter key on inputs = apply
document.querySelectorAll('.p-input').forEach(el => {
  el.addEventListener('keydown', e => { if (e.key === 'Enter') document.getElementById('applyBtn').click(); });
});

// Animation
let animId = null, animN = 1;
const animBtn = document.getElementById('animBtn');
animBtn.addEventListener('click', () => {
  if (animId) {
    clearInterval(animId); animId = null;
    animBtn.textContent = '▶ Animar'; return;
  }
  animN = zStart;
  animBtn.textContent = '■ Parar';
  animId = setInterval(() => {
    slider.value = animN; update(animN); animN++;
    if (animN > zEnd) {
      clearInterval(animId); animId = null;
      animBtn.textContent = '▶ Animar';
    }
  }, 80);
});

updateLegend();
update(1);
</script>
</body>
</html>
