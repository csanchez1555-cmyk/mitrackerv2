<!DOCTYPE html>

<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mi Progreso · CDMX</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=JetBrains+Mono:wght@300;400;500&display=swap');

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
–bg:      #080810;
–sur:     #0f0f1a;
–sur2:    #181826;
–brd:     #252535;
–lime:    #d4ff3a;
–coral:   #ff5f5f;
–sky:     #38b6ff;
–violet:  #b03aff;
–mint:    #3affb0;
–text:    #eeeef8;
–muted:   #5a5a78;
–fn:      ‘Syne’, sans-serif;
–mono:    ‘JetBrains Mono’, monospace;
}

body {
background: var(–bg);
color: var(–text);
font-family: var(–fn);
min-height: 100vh;
overflow-x: hidden;
}

/* subtle grid */
body::before {
content: ‘’;
position: fixed;
inset: 0;
background:
linear-gradient(rgba(212,255,58,.025) 1px, transparent 1px),
linear-gradient(90deg, rgba(212,255,58,.025) 1px, transparent 1px);
background-size: 44px 44px;
pointer-events: none;
z-index: 0;
}

.app {
position: relative;
z-index: 1;
max-width: 980px;
margin: 0 auto;
padding: 28px 18px 80px;
}

/* ── HEADER ─────────────────────────────── */
header {
display: flex;
align-items: flex-start;
justify-content: space-between;
flex-wrap: wrap;
gap: 12px;
margin-bottom: 28px;
padding-bottom: 20px;
border-bottom: 1px solid var(–brd);
}

header h1 {
font-size: clamp(1.5rem, 5vw, 2.1rem);
font-weight: 800;
letter-spacing: -.04em;
line-height: 1;
}
header h1 span { color: var(–lime); }

.sub {
font-family: var(–mono);
font-size: .65rem;
color: var(–muted);
letter-spacing: .1em;
text-transform: uppercase;
margin-top: 7px;
}

.date-badge {
font-family: var(–mono);
font-size: .65rem;
color: var(–muted);
background: var(–sur);
border: 1px solid var(–brd);
padding: 7px 13px;
border-radius: 7px;
white-space: nowrap;
margin-top: 2px;
}

/* ── SECTION LABEL ──────────────────────── */
.slabel {
font-family: var(–mono);
font-size: .6rem;
letter-spacing: .14em;
text-transform: uppercase;
color: var(–muted);
margin-bottom: 11px;
padding-left: 2px;
}

/* ── STREAK CHIPS ───────────────────────── */
.chips {
display: flex;
gap: 9px;
flex-wrap: wrap;
margin-bottom: 26px;
}

.chip {
display: flex;
align-items: center;
gap: 8px;
background: var(–sur);
border: 1px solid var(–brd);
border-radius: 9px;
padding: 9px 15px;
font-family: var(–mono);
font-size: .7rem;
flex: 1;
min-width: 150px;
}
.chip .cv {
font-family: var(–fn);
font-size: 1.15rem;
font-weight: 700;
margin-left: auto;
}

/* ── PROGRESS CARDS ─────────────────────── */
.pgrid {
display: grid;
grid-template-columns: repeat(auto-fill, minmax(210px, 1fr));
gap: 11px;
margin-bottom: 28px;
}

.pcard {
background: var(–sur);
border: 1px solid var(–brd);
border-radius: 13px;
padding: 16px;
transition: border-color .18s;
}
.pcard:hover { border-color: var(–lime); }

.pcard .plbl { font-size: .72rem; color: var(–muted); margin-bottom: 4px; }
.pcard .pval {
font-size: 1.7rem;
font-weight: 800;
letter-spacing: -.05em;
line-height: 1;
margin-bottom: 10px;
}
.pbar {
height: 4px;
background: var(–sur2);
border-radius: 99px;
overflow: hidden;
}
.pfill {
height: 100%;
border-radius: 99px;
transition: width .55s cubic-bezier(.22,1,.36,1);
}
.pcard .psub {
font-family: var(–mono);
font-size: .58rem;
color: var(–muted);
margin-top: 7px;
}

/* ── WEEK CHART ─────────────────────────── */
.chart-wrap {
background: var(–sur);
border: 1px solid var(–brd);
border-radius: 13px;
padding: 20px;
margin-bottom: 28px;
}
.bars {
display: flex;
align-items: flex-end;
gap: 7px;
height: 96px;
margin-bottom: 6px;
}
.bcol {
flex: 1;
display: flex;
flex-direction: column;
align-items: center;
justify-content: flex-end;
height: 100%;
gap: 5px;
}
.bfill {
width: 100%;
border-radius: 5px 5px 0 0;
transition: height .5s cubic-bezier(.22,1,.36,1);
min-height: 3px;
}
.blbl {
font-family: var(–mono);
font-size: .6rem;
}
.bnum {
font-family: var(–mono);
font-size: .55rem;
color: var(–muted);
}

/* ── HABIT CALENDAR ─────────────────────── */
.habit-section { margin-bottom: 28px; }

.hrow {
display: flex;
align-items: center;
gap: 10px;
margin-bottom: 7px;
}

.hname {
font-size: .75rem;
width: 135px;
flex-shrink: 0;
display: flex;
align-items: center;
gap: 7px;
}

.hdots { display: flex; gap: 3px; flex-wrap: wrap; }

.hdot {
width: 17px;
height: 17px;
border-radius: 4px;
cursor: pointer;
transition: transform .1s;
flex-shrink: 0;
border: none;
outline: none;
position: relative;
}
.hdot:hover { transform: scale(1.3); }
.hdot.off  { background: var(–sur2); border: 1px solid var(–brd); }
/* today marker */
.hdot.today-dot::after {
content: ‘’;
position: absolute;
bottom: -4px;
left: 50%;
transform: translateX(-50%);
width: 4px;
height: 4px;
border-radius: 50%;
background: var(–lime);
}

/* ── CHECKLIST ──────────────────────────── */
.checklist { margin-bottom: 28px; }

.titem {
display: flex;
align-items: center;
gap: 11px;
padding: 11px 13px;
background: var(–sur);
border: 1px solid var(–brd);
border-radius: 10px;
margin-bottom: 7px;
user-select: none;
transition: background .12s, border-color .12s;
}
.titem:hover { background: var(–sur2); }
.titem.done { opacity: .4; }
.titem.done .ttext { text-decoration: line-through; color: var(–muted); }

.tchk {
width: 20px; height: 20px;
border-radius: 6px;
border: 2px solid var(–brd);
flex-shrink: 0;
display: flex; align-items: center; justify-content: center;
font-size: .7rem;
cursor: pointer;
transition: background .12s, border-color .12s;
background: transparent;
color: #000;
}
.titem.done .tchk { background: var(–lime); border-color: var(–lime); }

.ttext { font-size: .83rem; flex: 1; cursor: pointer; }

.ttag {
font-family: var(–mono);
font-size: .58rem;
padding: 2px 8px;
border-radius: 99px;
letter-spacing: .05em;
text-transform: uppercase;
flex-shrink: 0;
}

.tdel {
background: none;
border: none;
color: var(–muted);
font-size: 1rem;
cursor: pointer;
padding: 2px 4px;
border-radius: 4px;
transition: color .12s, background .12s;
line-height: 1;
flex-shrink: 0;
}
.tdel:hover { color: var(–coral); background: rgba(255,95,95,.1); }

/* add task row */
.add-row {
display: flex;
gap: 8px;
margin-top: 10px;
flex-wrap: wrap;
}
.add-row input {
flex: 1;
min-width: 160px;
background: var(–sur);
border: 1px solid var(–brd);
border-radius: 8px;
padding: 10px 13px;
color: var(–text);
font-family: var(–fn);
font-size: .8rem;
outline: none;
transition: border-color .13s;
}
.add-row input:focus { border-color: var(–lime); }
.add-row input::placeholder { color: var(–muted); }

.add-row select {
background: var(–sur);
border: 1px solid var(–brd);
border-radius: 8px;
padding: 10px 9px;
color: var(–text);
font-family: var(–mono);
font-size: .7rem;
outline: none;
cursor: pointer;
}

.btn {
background: var(–lime);
color: #080810;
border: none;
border-radius: 8px;
padding: 10px 20px;
font-family: var(–fn);
font-weight: 700;
font-size: .8rem;
cursor: pointer;
transition: opacity .13s, transform .1s;
white-space: nowrap;
}
.btn:hover { opacity: .85; transform: translateY(-1px); }
.btn:active { transform: translateY(0); }

/* ── GOAL SLIDERS ───────────────────────── */
.sliders {
background: var(–sur);
border: 1px solid var(–brd);
border-radius: 13px;
padding: 20px;
margin-bottom: 28px;
}
.srow {
display: flex;
align-items: center;
gap: 10px;
margin-bottom: 11px;
flex-wrap: wrap;
}
.srow:last-child { margin-bottom: 0; }
.srow label {
font-family: var(–mono);
font-size: .65rem;
color: var(–muted);
width: 170px;
flex-shrink: 0;
}
.srow input[type=range] {
flex: 1;
min-width: 100px;
accent-color: var(–lime);
cursor: pointer;
}
.srow input[type=range]:disabled { opacity: .35; cursor: default; }
.sval {
font-family: var(–mono);
font-size: .72rem;
color: var(–lime);
width: 52px;
text-align: right;
}
.auto-badge {
font-family: var(–mono);
font-size: .55rem;
color: var(–muted);
border: 1px solid var(–brd);
border-radius: 4px;
padding: 1px 5px;
text-transform: uppercase;
letter-spacing: .06em;
}

/* ── TOAST ──────────────────────────────── */
#toast {
position: fixed;
bottom: 24px;
right: 24px;
background: var(–lime);
color: #080810;
font-family: var(–mono);
font-size: .72rem;
font-weight: 500;
padding: 10px 18px;
border-radius: 8px;
opacity: 0;
transform: translateY(8px);
transition: opacity .25s, transform .25s;
pointer-events: none;
z-index: 999;
}
#toast.show { opacity: 1; transform: translateY(0); }

/* ── RESPONSIVE ─────────────────────────── */
@media (max-width: 520px) {
.hname { width: 100px; font-size: .68rem; }
.hdot  { width: 13px; height: 13px; border-radius: 3px; }
.srow label { width: 100%; }
.chips { gap: 6px; }
}
</style>

</head>
<body>
<div class="app">

  <!-- HEADER -->

  <header>
    <div>
      <h1>Mi <span>Progreso</span></h1>
      <div class="sub">Tracker personal · CDMX · 18-month roadmap</div>
    </div>
    <div class="date-badge" id="dateBadge">—</div>
  </header>

  <!-- CHIPS -->

  <div class="slabel">⚡ Estado actual</div>
  <div class="chips" id="chips"></div>

  <!-- PROGRESS -->

  <div class="slabel">📊 Métricas de objetivos</div>
  <div class="pgrid" id="pgrid"></div>

  <!-- WEEK CHART -->

  <div class="slabel">📅 Hábitos completados — última semana</div>
  <div class="chart-wrap">
    <div class="bars" id="bars"></div>
  </div>

  <!-- HABIT CALENDAR -->

  <div class="slabel">🔲 Calendario de hábitos — últimos 30 días</div>
  <div class="habit-section" id="habitSection"></div>

  <!-- CHECKLIST -->

  <div class="slabel">✅ Checklist de hoy</div>
  <div class="checklist">
    <div id="taskList"></div>
    <div class="add-row">
      <input type="text" id="taskInput" placeholder="Nueva tarea..." />
      <select id="taskCat">
        <option value="study">📚 Estudio</option>
        <option value="work">💼 Trabajo</option>
        <option value="health">💪 Salud</option>
        <option value="habit">⚡ Hábito</option>
      </select>
      <button class="btn" id="addBtn">+ Agregar</button>
    </div>
  </div>

  <!-- SLIDERS -->

  <div class="slabel">🎯 Ajustar metas</div>
  <div class="sliders" id="sliders"></div>

</div>

<div id="toast"></div>

<script>
// ═══════════════════════════════════════════════════
// CONSTANTS
// ═══════════════════════════════════════════════════

const STORAGE_KEY = 'tracker_v2';

const CAT = {
  study:  { color: '#38b6ff', label: 'Estudio'  },
  work:   { color: '#d4ff3a', label: 'Trabajo'  },
  health: { color: '#b03aff', label: 'Salud'    },
  habit:  { color: '#ff5f5f', label: 'Hábito'   },
};

const HABITS = [
  { key: 'python',     icon: '🐍', label: 'Python / IA',  color: '#38b6ff' },
  { key: 'math',       icon: '📐', label: 'Matemáticas',  color: '#d4ff3a' },
  { key: 'english',    icon: '🇬🇧', label: 'Inglés',      color: '#b03aff' },
  { key: 'exercise',   icon: '🏃', label: 'Ejercicio',    color: '#ff5f5f' },
  { key: 'noJunkFood', icon: '🥗', label: 'Comida sana',  color: '#3affb0' },
];

// Days Mon-Sun (CDMX locale)
const DAY_NAMES = ['Lun','Mar','Mié','Jue','Vie','Sáb','Dom'];

// ═══════════════════════════════════════════════════
// DATE HELPERS
// ═══════════════════════════════════════════════════

const NOW   = new Date();
const TODAY = toISO(NOW);

function toISO(d) {
  return d.toISOString().split('T')[0];
}

// Returns Mon=0 … Sun=6  (local day, Mexico City)
function isoWeekday(d) {
  return (d.getDay() + 6) % 7;
}

// Offset today by -n days → ISO string
function isoOffset(n) {
  const d = new Date(NOW);
  d.setDate(d.getDate() - n);
  return toISO(d);
}

// ═══════════════════════════════════════════════════
// PERSISTENCE  (localStorage with in-memory fallback)
// ═══════════════════════════════════════════════════

let _memStore = null; // fallback when localStorage unavailable

function loadRaw() {
  try {
    const raw = localStorage.getItem(STORAGE_KEY);
    return raw ? JSON.parse(raw) : null;
  } catch (_) {
    return _memStore;
  }
}

function saveRaw(obj) {
  try {
    localStorage.setItem(STORAGE_KEY, JSON.stringify(obj));
  } catch (_) {
    _memStore = obj;
  }
}

// ═══════════════════════════════════════════════════
// DEFAULT STATE
// ═══════════════════════════════════════════════════

function buildDefaultState() {
  // habits[key] = { [ISO_DATE]: true/false }
  const habits = {};
  HABITS.forEach(h => { habits[h.key] = {}; });

  return {
    version: 2,
    goals: {
      studyHrsDay:      1,
      monthIncomeGoal:  800,
      monthIncomeNow:   0,
      exerciseDaysGoal: 4,
      phaseMonth:       1,
    },
    habits,
    tasks: [
      { id: 1, text: 'Estudiar Pre-Álgebra — Khan Academy (1h)', cat: 'study',  done: false },
      { id: 2, text: 'Completar turno DiDi / Uber',              cat: 'work',   done: false },
      { id: 3, text: '30 min de ejercicio',                      cat: 'health', done: false },
      { id: 4, text: 'Revisar noticias geopolíticas (15 min)',    cat: 'habit',  done: false },
      { id: 5, text: 'Practicar vocabulario en inglés',           cat: 'habit',  done: false },
    ],
    taskDate: TODAY,   // tasks reset daily
    nextId: 6,
    lastWeekReset: TODAY, // tracks weekly goal resets
  };
}

// ═══════════════════════════════════════════════════
// STATE INIT & MIGRATION
// ═══════════════════════════════════════════════════

let state;

(function initState() {
  const saved = loadRaw();

  if (!saved || saved.version !== 2) {
    // Fresh start or old v1 format → discard
    state = buildDefaultState();
    saveRaw(state);
    return;
  }

  state = saved;

  // ── Daily reset: if taskDate ≠ today, reset tasks done flags
  if (state.taskDate !== TODAY) {
    state.tasks = state.tasks.map(t => ({ ...t, done: false }));
    state.taskDate = TODAY;
    saveRaw(state);
  }
})();

function save() { saveRaw(state); }

// ═══════════════════════════════════════════════════
// HABIT HELPERS  (date-keyed map, no rotation needed)
// ═══════════════════════════════════════════════════

function habitOn(key, isoDate) {
  return !!state.habits[key][isoDate];
}

function toggleHabitDate(key, isoDate) {
  state.habits[key][isoDate] = !state.habits[key][isoDate];
  save();
  renderAll();
}

// Get array of ISO dates for the last N days (index 0 = oldest)
function lastNDates(n) {
  const arr = [];
  for (let i = n - 1; i >= 0; i--) arr.push(isoOffset(i));
  return arr;
}

// Count completions for one habit in a date array
function countInDates(key, dates) {
  return dates.reduce((c, d) => c + (habitOn(key, d) ? 1 : 0), 0);
}

// For a given date, count how many habits were completed
function habitsDoneOnDate(date) {
  return HABITS.reduce((c, h) => c + (habitOn(h.key, date) ? 1 : 0), 0);
}

// Streak: consecutive completed days ending today (backwards)
function calcStreak(key) {
  let s = 0;
  let i = 0;
  while (true) {
    const d = isoOffset(i);
    if (habitOn(key, d)) { s++; i++; } else break;
  }
  return s;
}

// ═══════════════════════════════════════════════════
// DERIVED METRICS  (computed fresh, no stale data)
// ═══════════════════════════════════════════════════

function studyHrsWeek() {
  // 1 session (habit tick) = studyHrsDay hours
  const weekDates = lastNDates(7);
  const sessions = countInDates('python', weekDates)
                 + countInDates('math',   weekDates)
                 + countInDates('english', weekDates);
  return +(sessions * state.goals.studyHrsDay).toFixed(1);
}

function exerciseDaysWeek() {
  return countInDates('exercise', lastNDates(7));
}

function weekBarData() {
  // Returns array[7]: index 0 = 6 days ago, index 6 = today
  return lastNDates(7).map(d => habitsDoneOnDate(d));
}

// ═══════════════════════════════════════════════════
// RENDER HELPERS
// ═══════════════════════════════════════════════════

function $(id) { return document.getElementById(id); }

function showToast(msg) {
  const t = $('toast');
  t.textContent = msg;
  t.classList.add('show');
  clearTimeout(t._timer);
  t._timer = setTimeout(() => t.classList.remove('show'), 2200);
}

// ── DATE BADGE ──────────────────────────────────────
function renderDate() {
  $('dateBadge').textContent = NOW.toLocaleDateString('es-MX', {
    weekday: 'long', day: 'numeric', month: 'long'
  });
}

// ── STREAK CHIPS ─────────────────────────────────────
function renderChips() {
  const doneToday  = state.tasks.filter(t => t.done).length;
  const totalTasks = state.tasks.length;

  const chips = [
    { icon: '🔥', label: 'Racha Python/IA',  val: `${calcStreak('python')} días`,   color: '#38b6ff' },
    { icon: '💪', label: 'Racha ejercicio',  val: `${calcStreak('exercise')} días`, color: '#b03aff' },
    { icon: '✅', label: 'Tareas hoy',        val: `${doneToday}/${totalTasks}`,     color: '#d4ff3a' },
    { icon: '📅', label: 'Roadmap',          val: `Mes ${state.goals.phaseMonth}/18`, color: '#ff5f5f' },
  ];

  $('chips').innerHTML = chips.map(c => `
    <div class="chip">
      <span>${c.icon}</span>
      <span style="color:var(--muted)">${c.label}</span>
      <span class="cv" style="color:${c.color}">${c.val}</span>
    </div>
  `).join('');
}

// ── PROGRESS CARDS ──────────────────────────────────
function renderProgress() {
  const g   = state.goals;
  const shw = studyHrsWeek();
  const edw = exerciseDaysWeek();

  const cards = [
    {
      label: 'Estudio esta semana',
      val:   `${shw}h`,
      fill:  Math.min(100, (shw / Math.max(.1, g.studyHrsDay * 7)) * 100),
      color: '#38b6ff',
      sub:   `Meta: ${g.studyHrsDay}h/día · ${+(g.studyHrsDay * 7).toFixed(1)}h/sem`,
    },
    {
      label: 'Ingresos del mes (USD)',
      val:   `$${g.monthIncomeNow}`,
      fill:  Math.min(100, (g.monthIncomeNow / Math.max(1, g.monthIncomeGoal)) * 100),
      color: '#d4ff3a',
      sub:   `Meta: $${g.monthIncomeGoal} · ${Math.round((g.monthIncomeNow / Math.max(1, g.monthIncomeGoal)) * 100)}%`,
    },
    {
      label: 'Ejercicio esta semana',
      val:   `${edw}/${g.exerciseDaysGoal}d`,
      fill:  Math.min(100, (edw / Math.max(1, g.exerciseDaysGoal)) * 100),
      color: '#b03aff',
      sub:   `Meta: ${g.exerciseDaysGoal} días/semana`,
    },
    {
      label: 'Roadmap IA/Python',
      val:   `${Math.round((g.phaseMonth / 18) * 100)}%`,
      fill:  (g.phaseMonth / 18) * 100,
      color: '#ff5f5f',
      sub:   `Fase ${g.phaseMonth} de 18 meses`,
    },
  ];

  $('pgrid').innerHTML = cards.map(c => `
    <div class="pcard">
      <div class="plbl">${c.label}</div>
      <div class="pval" style="color:${c.color}">${c.val}</div>
      <div class="pbar"><div class="pfill" style="width:${c.fill}%;background:${c.color}"></div></div>
      <div class="psub">${c.sub}</div>
    </div>
  `).join('');
}

// ── WEEK BAR CHART ───────────────────────────────────
function renderBars() {
  const data  = weekBarData();   // array[7], index0 = oldest
  const max   = HABITS.length;
  const dates = lastNDates(7);   // same order

  $('bars').innerHTML = data.map((v, i) => {
    const isToday = dates[i] === TODAY;
    const pct     = max > 0 ? Math.round((v / max) * 100) : 0;
    const d       = new Date(dates[i] + 'T12:00:00');  // avoid TZ drift
    const lbl     = DAY_NAMES[isoWeekday(d)];
    return `
      <div class="bcol">
        <div class="bnum">${v || ''}</div>
        <div class="bfill" style="height:${Math.max(3, pct)}%;background:${isToday ? '#d4ff3a' : '#252535'}"></div>
        <div class="blbl" style="color:${isToday ? '#d4ff3a' : 'var(--muted)'}">${lbl}</div>
      </div>
    `;
  }).join('');
}

// ── HABIT CALENDAR ───────────────────────────────────
function renderHabits() {
  const dates = lastNDates(30); // index0=oldest, index29=today

  $('habitSection').innerHTML = HABITS.map(h => {
    const dots = dates.map((d, i) => {
      const on      = habitOn(h.key, d);
      const isToday = d === TODAY;
      const cls     = ['hdot', on ? 'on' : 'off', isToday ? 'today-dot' : ''].filter(Boolean).join(' ');
      const style   = on ? `background:${h.color}` : '';
      // Tooltip: show actual date, not a confusing "X days ago"
      const dObj = new Date(d + 'T12:00:00');
      const tip  = dObj.toLocaleDateString('es-MX', { day:'numeric', month:'short' });
      return `<button class="hdot ${cls}" style="${style}" onclick="toggleHabitDate('${h.key}','${d}')" title="${tip}"></button>`;
    }).join('');

    const streak = calcStreak(h.key);
    return `
      <div class="hrow">
        <div class="hname">
          <span>${h.icon}</span>
          <span>${h.label}</span>
        </div>
        <div class="hdots">${dots}</div>
        <div style="font-family:var(--mono);font-size:.6rem;color:${h.color};margin-left:8px;white-space:nowrap">
          🔥${streak}d
        </div>
      </div>
    `;
  }).join('');
}

// ── TASK LIST ────────────────────────────────────────
function renderTasks() {
  $('taskList').innerHTML = state.tasks.map(t => {
    const c = CAT[t.cat] || CAT.habit;
    return `
      <div class="titem ${t.done ? 'done' : ''}">
        <div class="tchk" onclick="toggleTask(${t.id})">${t.done ? '✓' : ''}</div>
        <div class="ttext" onclick="toggleTask(${t.id})">${t.text}</div>
        <span class="ttag" style="background:${c.color}1a;color:${c.color}">${c.label}</span>
        <button class="tdel" onclick="deleteTask(${t.id})" title="Eliminar">✕</button>
      </div>
    `;
  }).join('') || '<p style="font-family:var(--mono);font-size:.7rem;color:var(--muted);padding:10px 0">Sin tareas. Agrega una abajo ↓</p>';
}

// ── SLIDERS ──────────────────────────────────────────
const SLIDER_CFG = [
  { key: 'studyHrsDay',      label: 'Meta horas estudio / día',  min: .5,  max: 8,    step: .5,  unit: 'h',   auto: false },
  { key: 'monthIncomeGoal',  label: 'Meta ingresos / mes (USD)', min: 100, max: 5000, step: 50,  unit: '$',   auto: false },
  { key: 'monthIncomeNow',   label: 'Ingresos actuales (USD)',   min: 0,   max: 5000, step: 50,  unit: '$',   auto: false },
  { key: 'exerciseDaysGoal', label: 'Meta ejercicio / semana',   min: 1,   max: 7,    step: 1,   unit: 'd',   auto: false },
  { key: 'phaseMonth',       label: 'Mes del roadmap',           min: 1,   max: 18,   step: 1,   unit: '/18', auto: false },
];

function renderSliders() {
  $('sliders').innerHTML = SLIDER_CFG.map(s => `
    <div class="srow">
      <label>${s.label}</label>
      <input type="range" min="${s.min}" max="${s.max}" step="${s.step}"
        value="${state.goals[s.key]}"
        oninput="onSlider('${s.key}','${s.unit}',this)"
      />
      <div class="sval" id="sv_${s.key}">${state.goals[s.key]}${s.unit}</div>
    </div>
  `).join('');
}

function onSlider(key, unit, el) {
  const v = parseFloat(el.value);
  state.goals[key] = v;
  const sv = $('sv_' + key);
  if (sv) sv.textContent = v + unit;
  save();
  renderChips();
  renderProgress();
}

// ═══════════════════════════════════════════════════
// ACTIONS
// ═══════════════════════════════════════════════════

function toggleTask(id) {
  const t = state.tasks.find(t => t.id === id);
  if (!t) return;
  t.done = !t.done;
  save();
  renderTasks();
  renderChips();
}

function deleteTask(id) {
  state.tasks = state.tasks.filter(t => t.id !== id);
  save();
  renderTasks();
  renderChips();
  showToast('Tarea eliminada');
}

function addTask() {
  const inp  = $('taskInput');
  const cat  = $('taskCat').value;
  const text = inp.value.trim();
  if (!text) { inp.focus(); return; }
  state.tasks.push({ id: state.nextId++, text, cat, done: false });
  inp.value = '';
  save();
  renderTasks();
  renderChips();
  showToast('✓ Tarea agregada');
}

// expose to onclick
window.toggleHabitDate = toggleHabitDate;
window.toggleTask      = toggleTask;
window.deleteTask      = deleteTask;
window.addTask         = addTask;
window.onSlider        = onSlider;

// ── EVENTS ───────────────────────────────────────────
$('addBtn').addEventListener('click', addTask);
$('taskInput').addEventListener('keydown', e => { if (e.key === 'Enter') addTask(); });

// ═══════════════════════════════════════════════════
// BOOT
// ═══════════════════════════════════════════════════

function renderAll() {
  renderChips();
  renderProgress();
  renderBars();
  renderHabits();
  renderTasks();
}

renderDate();
renderAll();
renderSliders();
</script>

</body>
</html>
