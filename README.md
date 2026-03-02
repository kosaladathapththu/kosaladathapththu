<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kosala Athapaththu — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;700;800;900&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #050810;
    --surface: #0b1120;
    --surface2: #0f1929;
    --border: #1a2a45;
    --accent: #00d4ff;
    --accent2: #7b5ea7;
    --accent3: #00ffa3;
    --text: #c8d8f0;
    --text-dim: #5a7090;
    --text-bright: #eef4ff;
    --glow: 0 0 20px rgba(0,212,255,0.3);
    --glow2: 0 0 20px rgba(0,255,163,0.2);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Space Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
    cursor: none;
  }

  /* Custom cursor */
  .cursor {
    width: 10px; height: 10px;
    background: var(--accent);
    border-radius: 50%;
    position: fixed;
    top: 0; left: 0;
    pointer-events: none;
    z-index: 9999;
    mix-blend-mode: screen;
    transition: transform 0.1s;
  }
  .cursor-ring {
    width: 36px; height: 36px;
    border: 1px solid rgba(0,212,255,0.4);
    border-radius: 50%;
    position: fixed;
    top: 0; left: 0;
    pointer-events: none;
    z-index: 9998;
    transition: all 0.12s ease;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,212,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,212,255,0.03) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
    z-index: 0;
  }

  /* Ambient orbs */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(100px);
    pointer-events: none;
    z-index: 0;
  }
  .orb1 { width: 500px; height: 500px; background: rgba(0,212,255,0.06); top: -100px; left: -100px; animation: drift1 18s ease-in-out infinite; }
  .orb2 { width: 400px; height: 400px; background: rgba(123,94,167,0.08); bottom: 100px; right: -50px; animation: drift2 22s ease-in-out infinite; }
  .orb3 { width: 300px; height: 300px; background: rgba(0,255,163,0.05); top: 50%; left: 50%; animation: drift3 15s ease-in-out infinite; }

  @keyframes drift1 { 0%,100%{transform:translate(0,0)} 50%{transform:translate(60px,40px)} }
  @keyframes drift2 { 0%,100%{transform:translate(0,0)} 50%{transform:translate(-40px,-60px)} }
  @keyframes drift3 { 0%,100%{transform:translate(-50%,-50%) scale(1)} 50%{transform:translate(-50%,-50%) scale(1.3)} }

  .wrapper {
    position: relative;
    z-index: 1;
    max-width: 1100px;
    margin: 0 auto;
    padding: 40px 24px 80px;
  }

  /* ── HEADER ── */
  header {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 36px;
    align-items: center;
    padding: 48px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-top: 2px solid var(--accent);
    margin-bottom: 2px;
    position: relative;
    overflow: hidden;
    animation: fadeUp 0.8s ease both;
  }
  header::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(0,212,255,0.04) 0%, transparent 60%);
    pointer-events: none;
  }

  .avatar-wrap {
    position: relative;
    width: 100px; height: 100px;
    flex-shrink: 0;
  }
  .avatar-wrap::before {
    content: '';
    position: absolute;
    inset: -4px;
    border-radius: 50%;
    background: conic-gradient(var(--accent), var(--accent2), var(--accent3), var(--accent));
    animation: spin 4s linear infinite;
  }
  .avatar-wrap::after {
    content: '';
    position: absolute;
    inset: -2px;
    border-radius: 50%;
    background: var(--surface);
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  .avatar {
    position: relative;
    z-index: 1;
    width: 100px; height: 100px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent2), var(--accent));
    display: flex; align-items: center; justify-content: center;
    font-family: 'Syne', sans-serif;
    font-size: 36px;
    font-weight: 900;
    color: var(--bg);
    letter-spacing: -1px;
  }

  .header-info h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(24px, 4vw, 40px);
    font-weight: 900;
    color: var(--text-bright);
    letter-spacing: -1px;
    line-height: 1;
    margin-bottom: 8px;
  }
  .header-info h1 span { color: var(--accent); }

  .tagline {
    font-size: 11px;
    color: var(--text-dim);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 16px;
  }

  .badge-row {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  .badge {
    padding: 4px 12px;
    border: 1px solid var(--border);
    font-size: 10px;
    letter-spacing: 1px;
    text-transform: uppercase;
    color: var(--text-dim);
    background: rgba(255,255,255,0.02);
    transition: all 0.2s;
  }
  .badge:hover { border-color: var(--accent); color: var(--accent); background: rgba(0,212,255,0.05); }
  .badge.accent { border-color: rgba(0,212,255,0.4); color: var(--accent); }
  .badge.green { border-color: rgba(0,255,163,0.4); color: var(--accent3); }

  /* ── TYPING ANIMATION ── */
  .typing-bar {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-left: 3px solid var(--accent);
    padding: 16px 24px;
    margin-bottom: 2px;
    font-size: 13px;
    animation: fadeUp 0.8s 0.2s ease both;
    min-height: 52px;
  }
  .typing-bar .prefix { color: var(--accent); }
  .cursor-blink { display: inline-block; width: 2px; height: 14px; background: var(--accent); margin-left: 2px; vertical-align: middle; animation: blink 1s step-end infinite; }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* ── GRID ── */
  .grid3 {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
    margin-bottom: 2px;
  }
  .grid2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
    margin-bottom: 2px;
  }

  .card {
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 28px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.3s;
    animation: fadeUp 0.8s ease both;
  }
  .card:hover { border-color: rgba(0,212,255,0.3); transform: translateY(-2px); }
  .card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(0,212,255,0.4), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .card:hover::before { opacity: 1; }

  .card-label {
    font-size: 9px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--text-dim);
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .card-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* STAT CARDS */
  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 48px;
    font-weight: 900;
    color: var(--text-bright);
    line-height: 1;
    letter-spacing: -2px;
  }
  .stat-num span { color: var(--accent); font-size: 24px; }
  .stat-label { font-size: 10px; color: var(--text-dim); letter-spacing: 2px; text-transform: uppercase; margin-top: 8px; }

  /* TECH STACK */
  .tech-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
    gap: 10px;
  }
  .tech-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    padding: 14px 8px;
    border: 1px solid var(--border);
    background: rgba(255,255,255,0.01);
    transition: all 0.2s;
    cursor: default;
  }
  .tech-item:hover {
    border-color: rgba(0,212,255,0.4);
    background: rgba(0,212,255,0.04);
    transform: translateY(-3px);
    box-shadow: 0 8px 24px rgba(0,0,0,0.3);
  }
  .tech-icon { font-size: 24px; filter: grayscale(0.3); }
  .tech-name { font-size: 9px; letter-spacing: 1px; color: var(--text-dim); text-transform: uppercase; }

  /* PROJECTS */
  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: all 0.3s;
    margin-bottom: 2px;
    animation: fadeUp 0.8s ease both;
  }
  .project-card:hover { border-color: rgba(0,212,255,0.3); background: rgba(11,17,32,0.95); }
  .project-card:hover .project-glow { opacity: 1; }
  .project-glow {
    position: absolute;
    top: 0; right: 0;
    width: 200px; height: 200px;
    background: radial-gradient(circle at top right, rgba(0,212,255,0.06), transparent 70%);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .project-num {
    font-family: 'Syne', sans-serif;
    font-size: 64px;
    font-weight: 900;
    color: rgba(0,212,255,0.07);
    position: absolute;
    top: 8px; right: 20px;
    line-height: 1;
    letter-spacing: -3px;
  }
  .project-header {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    margin-bottom: 12px;
  }
  .project-icon { font-size: 28px; }
  .project-name {
    font-family: 'Syne', sans-serif;
    font-size: 16px;
    font-weight: 800;
    color: var(--text-bright);
    line-height: 1.2;
  }
  .project-sub { font-size: 10px; color: var(--accent); letter-spacing: 2px; text-transform: uppercase; margin-top: 2px; }
  .project-desc { font-size: 12px; color: var(--text-dim); line-height: 1.8; margin-bottom: 14px; }
  .tag-row { display: flex; flex-wrap: wrap; gap: 6px; }
  .tag {
    padding: 3px 10px;
    font-size: 9px;
    letter-spacing: 1px;
    text-transform: uppercase;
    border: 1px solid var(--border);
    color: var(--text-dim);
  }

  /* CONTRIBUTION GRID */
  .contrib-grid {
    display: grid;
    grid-template-columns: repeat(52, 1fr);
    gap: 2px;
  }
  .contrib-cell {
    aspect-ratio: 1;
    border-radius: 1px;
    background: var(--surface2);
  }

  /* BAR CHART */
  .bar-chart { display: flex; align-items: flex-end; gap: 4px; height: 80px; }
  .bar-wrap { flex: 1; display: flex; flex-direction: column; align-items: center; gap: 4px; }
  .bar {
    width: 100%;
    background: var(--accent);
    border-radius: 2px 2px 0 0;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }
  .bar::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(to top, transparent, rgba(255,255,255,0.15));
  }
  .bar:hover { filter: brightness(1.3); }
  .bar-month { font-size: 8px; color: var(--text-dim); letter-spacing: 1px; }

  /* LANG BARS */
  .lang-item { margin-bottom: 14px; }
  .lang-row { display: flex; justify-content: space-between; margin-bottom: 6px; }
  .lang-name { font-size: 11px; color: var(--text); }
  .lang-pct { font-size: 11px; color: var(--text-dim); font-family: 'Space Mono', monospace; }
  .lang-track { height: 3px; background: var(--surface2); border-radius: 2px; overflow: hidden; }
  .lang-fill { height: 100%; border-radius: 2px; }

  /* SOCIAL LINKS */
  .social-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
  .social-link {
    display: flex; align-items: center; gap: 10px;
    padding: 12px 16px;
    border: 1px solid var(--border);
    text-decoration: none;
    color: var(--text-dim);
    font-size: 11px;
    letter-spacing: 1px;
    transition: all 0.2s;
  }
  .social-link:hover { border-color: rgba(0,212,255,0.5); color: var(--accent); background: rgba(0,212,255,0.04); }
  .social-icon { font-size: 18px; }

  /* ACTIVITY LOG */
  .activity-item {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 12px 0;
    border-bottom: 1px solid rgba(26,42,69,0.5);
    font-size: 11px;
  }
  .activity-item:last-child { border-bottom: none; }
  .activity-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--accent); flex-shrink: 0; }
  .activity-dot.green { background: var(--accent3); }
  .activity-dot.purple { background: var(--accent2); }
  .activity-time { color: var(--text-dim); margin-left: auto; font-size: 10px; }

  /* STATUS INDICATOR */
  .status-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--accent3);
    display: inline-block;
    margin-right: 8px;
    box-shadow: 0 0 8px var(--accent3);
    animation: pulse 2s infinite;
  }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.4} }

  /* SNAKE ANIMATION */
  .snake-track {
    position: relative;
    height: 40px;
    overflow: hidden;
    border: 1px solid var(--border);
    background: var(--surface2);
    margin-top: 8px;
  }
  .snake {
    position: absolute;
    height: 8px;
    background: linear-gradient(90deg, transparent, var(--accent3), var(--accent));
    border-radius: 4px;
    top: 50%;
    transform: translateY(-50%);
    animation: snakeMove 4s ease-in-out infinite;
    box-shadow: 0 0 12px var(--accent3);
  }
  .snake-head {
    position: absolute;
    right: 0;
    width: 10px; height: 10px;
    background: var(--accent3);
    border-radius: 50%;
    top: 50%;
    transform: translateY(-50%);
    box-shadow: 0 0 16px var(--accent3);
  }
  @keyframes snakeMove {
    0% { left: -30%; width: 30%; }
    50% { left: 35%; width: 30%; }
    100% { left: 100%; width: 30%; }
  }

  /* FOOTER */
  footer {
    text-align: center;
    padding: 40px;
    font-size: 10px;
    color: var(--text-dim);
    letter-spacing: 3px;
    text-transform: uppercase;
    border-top: 1px solid var(--border);
    margin-top: 2px;
  }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .card:nth-child(1) { animation-delay: 0.1s; }
  .card:nth-child(2) { animation-delay: 0.2s; }
  .card:nth-child(3) { animation-delay: 0.3s; }
  .project-card:nth-child(1) { animation-delay: 0.15s; }
  .project-card:nth-child(2) { animation-delay: 0.25s; }
  .project-card:nth-child(3) { animation-delay: 0.35s; }
  .project-card:nth-child(4) { animation-delay: 0.45s; }

  /* RESPONSIVE */
  @media (max-width: 700px) {
    header { grid-template-columns: 1fr; text-align: center; }
    .badge-row { justify-content: center; }
    .grid3 { grid-template-columns: 1fr; }
    .grid2 { grid-template-columns: 1fr; }
    .social-grid { grid-template-columns: 1fr; }
  }

  /* SCANLINE EFFECT */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,0,0,0.03) 2px, rgba(0,0,0,0.03) 4px);
    pointer-events: none;
    z-index: 0;
  }

  /* TOOLTIP */
  [data-tip] { position: relative; }
  [data-tip]:hover::after {
    content: attr(data-tip);
    position: absolute;
    bottom: 110%;
    left: 50%;
    transform: translateX(-50%);
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 4px 10px;
    font-size: 10px;
    white-space: nowrap;
    color: var(--text);
    z-index: 100;
  }
</style>
</head>
<body>

<div class="cursor" id="cur"></div>
<div class="cursor-ring" id="ring"></div>

<div class="orb orb1"></div>
<div class="orb orb2"></div>
<div class="orb orb3"></div>

<div class="wrapper">

  <!-- HEADER -->
  <header>
    <div class="avatar-wrap">
      <div class="avatar">KA</div>
    </div>
    <div class="header-info">
      <div class="tagline">Software Engineering · NIBM · Colombo</div>
      <h1>Kosala <span>Athapaththu</span></h1>
      <div class="badge-row">
        <span class="badge accent">⚡ Available for work</span>
        <span class="badge green"><span class="status-dot"></span>Open to collab</span>
        <span class="badge">Full-Stack</span>
        <span class="badge">Backend</span>
        <span class="badge">Android</span>
        <span class="badge">IoT</span>
      </div>
    </div>
  </header>

  <!-- TYPING BAR -->
  <div class="typing-bar">
    <span class="prefix">$ </span>
    <span id="typed"></span><span class="cursor-blink"></span>
  </div>

  <!-- STAT CARDS -->
  <div class="grid3">
    <div class="card">
      <div class="card-label">Repositories</div>
      <div class="stat-num" id="repoCount">0<span>+</span></div>
      <div class="stat-label">Public Projects</div>
    </div>
    <div class="card">
      <div class="card-label">Contributions</div>
      <div class="stat-num" id="contribCount">0<span>+</span></div>
      <div class="stat-label">This Year</div>
    </div>
    <div class="card">
      <div class="card-label">Streak</div>
      <div class="stat-num" id="streakCount">0<span>d</span></div>
      <div class="stat-label">Longest Streak</div>
    </div>
  </div>

  <!-- TECH STACK + LANGS -->
  <div class="grid2">
    <div class="card" style="animation-delay:0.2s">
      <div class="card-label">Tech Stack</div>
      <div class="tech-grid">
        <div class="tech-item" data-tip="Java"><div class="tech-icon">☕</div><div class="tech-name">Java</div></div>
        <div class="tech-item" data-tip="Spring Boot"><div class="tech-icon">🌱</div><div class="tech-name">Spring</div></div>
        <div class="tech-item" data-tip="React"><div class="tech-icon">⚛️</div><div class="tech-name">React</div></div>
        <div class="tech-item" data-tip="PHP"><div class="tech-icon">🐘</div><div class="tech-name">PHP</div></div>
        <div class="tech-item" data-tip="JavaScript"><div class="tech-icon">🟨</div><div class="tech-name">JS</div></div>
        <div class="tech-item" data-tip="MySQL"><div class="tech-icon">🗄️</div><div class="tech-name">MySQL</div></div>
        <div class="tech-item" data-tip="MongoDB"><div class="tech-icon">🍃</div><div class="tech-name">Mongo</div></div>
        <div class="tech-item" data-tip="Android"><div class="tech-icon">🤖</div><div class="tech-name">Android</div></div>
        <div class="tech-item" data-tip="Arduino"><div class="tech-icon">⚡</div><div class="tech-name">Arduino</div></div>
        <div class="tech-item" data-tip="Python"><div class="tech-icon">🐍</div><div class="tech-name">Python</div></div>
        <div class="tech-item" data-tip="Git"><div class="tech-icon">🔀</div><div class="tech-name">Git</div></div>
        <div class="tech-item" data-tip="Microservices"><div class="tech-icon">🔲</div><div class="tech-name">Micro</div></div>
      </div>
    </div>

    <div class="card" style="animation-delay:0.3s">
      <div class="card-label">Top Languages</div>
      <div id="langs">
        <div class="lang-item">
          <div class="lang-row"><span class="lang-name">Java</span><span class="lang-pct">42%</span></div>
          <div class="lang-track"><div class="lang-fill" style="width:42%;background:linear-gradient(90deg,#f89820,#e76c00)"></div></div>
        </div>
        <div class="lang-item">
          <div class="lang-row"><span class="lang-name">JavaScript</span><span class="lang-pct">22%</span></div>
          <div class="lang-track"><div class="lang-fill" style="width:22%;background:linear-gradient(90deg,#f7df1e,#e0b800)"></div></div>
        </div>
        <div class="lang-item">
          <div class="lang-row"><span class="lang-name">PHP</span><span class="lang-pct">18%</span></div>
          <div class="lang-track"><div class="lang-fill" style="width:18%;background:linear-gradient(90deg,#7a86b8,#4f5b93)"></div></div>
        </div>
        <div class="lang-item">
          <div class="lang-row"><span class="lang-name">Python</span><span class="lang-pct">10%</span></div>
          <div class="lang-track"><div class="lang-fill" style="width:10%;background:linear-gradient(90deg,#3776ab,#ffd343)"></div></div>
        </div>
        <div class="lang-item">
          <div class="lang-row"><span class="lang-name">C++ / Arduino</span><span class="lang-pct">8%</span></div>
          <div class="lang-track"><div class="lang-fill" style="width:8%;background:linear-gradient(90deg,#00599c,#004482)"></div></div>
        </div>
      </div>

      <div style="margin-top:28px;">
        <div class="card-label">Monthly Activity</div>
        <div class="bar-chart" id="barChart">
          <div class="bar-wrap"><div class="bar" style="height:35%"></div><div class="bar-month">M</div></div>
          <div class="bar-wrap"><div class="bar" style="height:55%"></div><div class="bar-month">A</div></div>
          <div class="bar-wrap"><div class="bar" style="height:40%"></div><div class="bar-month">M</div></div>
          <div class="bar-wrap"><div class="bar" style="height:70%"></div><div class="bar-month">J</div></div>
          <div class="bar-wrap"><div class="bar" style="height:45%"></div><div class="bar-month">J</div></div>
          <div class="bar-wrap"><div class="bar" style="height:80%"></div><div class="bar-month">A</div></div>
          <div class="bar-wrap"><div class="bar" style="height:60%"></div><div class="bar-month">S</div></div>
          <div class="bar-wrap"><div class="bar" style="height:90%"></div><div class="bar-month">O</div></div>
          <div class="bar-wrap"><div class="bar" style="height:75%"></div><div class="bar-month">N</div></div>
          <div class="bar-wrap"><div class="bar" style="height:100%;background:var(--accent3)"></div><div class="bar-month">D</div></div>
          <div class="bar-wrap"><div class="bar" style="height:65%"></div><div class="bar-month">J</div></div>
          <div class="bar-wrap"><div class="bar" style="height:85%"></div><div class="bar-month">F</div></div>
        </div>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div style="margin-bottom:2px;">
    <div class="project-card">
      <div class="project-glow"></div>
      <div class="project-num">01</div>
      <div class="project-header">
        <div class="project-icon">🏨</div>
        <div>
          <div class="project-name">Hotel Management System</div>
          <div class="project-sub">Microservices · Enterprise</div>
        </div>
      </div>
      <div class="project-desc">
        Distributed microservices architecture with dedicated UI service. Handles room booking, billing, guest management, and reporting across independent scalable services.
      </div>
      <div class="tag-row">
        <span class="tag">Spring Boot</span><span class="tag">React</span><span class="tag">MySQL</span><span class="tag">Microservices</span><span class="tag">REST API</span>
      </div>
    </div>

    <div class="project-card">
      <div class="project-glow"></div>
      <div class="project-num">02</div>
      <div class="project-header">
        <div class="project-icon">🏠</div>
        <div>
          <div class="project-name">Hostel Management System</div>
          <div class="project-sub">Full-Stack · Admin Portal</div>
        </div>
      </div>
      <div class="project-desc">
        Comprehensive matron/admin workflows with inventory tracking, payroll processing, room allocation, and detailed reporting modules.
      </div>
      <div class="tag-row">
        <span class="tag">PHP</span><span class="tag">MySQL</span><span class="tag">XAMPP</span><span class="tag">Bootstrap</span>
      </div>
    </div>

    <div class="project-card">
      <div class="project-glow"></div>
      <div class="project-num">03</div>
      <div class="project-header">
        <div class="project-icon">🤖</div>
        <div>
          <div class="project-name">River Trash Collector Robot</div>
          <div class="project-sub">IoT · Hardware · Robotics</div>
        </div>
      </div>
      <div class="project-desc">
        Autonomous river cleanup robot with ultrasonic sensors, servo control, LCD status display, and real-time battery monitoring for field deployment.
      </div>
      <div class="tag-row">
        <span class="tag">Arduino</span><span class="tag">C++</span><span class="tag">IoT</span><span class="tag">Sensors</span><span class="tag">Servo</span>
      </div>
    </div>

    <div class="project-card">
      <div class="project-glow"></div>
      <div class="project-num">04</div>
      <div class="project-header">
        <div class="project-icon">🧠</div>
        <div>
          <div class="project-name">Fraud Detection ML System</div>
          <div class="project-sub">Machine Learning · Data Science</div>
        </div>
      </div>
      <div class="project-desc">
        End-to-end ML pipeline for fraud detection with SMOTE oversampling, feature engineering, preprocessing, and comprehensive model evaluation.
      </div>
      <div class="tag-row">
        <span class="tag">Python</span><span class="tag">Scikit-learn</span><span class="tag">SMOTE</span><span class="tag">Pandas</span>
      </div>
    </div>
  </div>

  <!-- CONTRIBUTION + ACTIVITY -->
  <div class="grid2">
    <div class="card" style="animation-delay:0.35s">
      <div class="card-label">Contribution Graph</div>
      <div class="contrib-grid" id="contribGrid"></div>
      <div class="snake-track" style="margin-top:12px;">
        <div class="snake"><div class="snake-head"></div></div>
      </div>
      <div style="font-size:10px;color:var(--text-dim);margin-top:8px;letter-spacing:1px;">▲ Contribution snake (live on GitHub)</div>
    </div>

    <div class="card" style="animation-delay:0.45s">
      <div class="card-label">Recent Activity</div>
      <div id="activityLog">
        <div class="activity-item">
          <div class="activity-dot"></div>
          <div>Pushed to <strong>hotel-microservices</strong> — feat: booking service</div>
          <div class="activity-time">2h ago</div>
        </div>
        <div class="activity-item">
          <div class="activity-dot green"></div>
          <div>Opened PR in <strong>hostel-mgmt</strong> — fix payroll calc</div>
          <div class="activity-time">1d ago</div>
        </div>
        <div class="activity-item">
          <div class="activity-dot purple"></div>
          <div>Created repo <strong>fraud-detection-ml</strong></div>
          <div class="activity-time">3d ago</div>
        </div>
        <div class="activity-item">
          <div class="activity-dot"></div>
          <div>Starred <strong>spring-boot-examples</strong></div>
          <div class="activity-time">4d ago</div>
        </div>
        <div class="activity-item">
          <div class="activity-dot green"></div>
          <div>Merged PR — river-robot sensor calibration</div>
          <div class="activity-time">6d ago</div>
        </div>
        <div class="activity-item">
          <div class="activity-dot"></div>
          <div>Commented on issue <strong>#14</strong> — auth service</div>
          <div class="activity-time">1w ago</div>
        </div>
      </div>
    </div>
  </div>

  <!-- SOCIAL + CONTACT -->
  <div class="card" style="animation-delay:0.5s;margin-bottom:2px;">
    <div class="card-label">Links & Contact</div>
    <div class="social-grid">
      <a href="https://www.linkedin.com/in/kosala-d-athapaththu-a453b9248/" target="_blank" class="social-link">
        <span class="social-icon">💼</span>
        <span>LinkedIn · Kosala D Athapaththu</span>
      </a>
      <a href="https://x.com/KAthapathtu" target="_blank" class="social-link">
        <span class="social-icon">✖</span>
        <span>Twitter · @KAthapathtu</span>
      </a>
      <a href="mailto:kosalaathapaththu1234@gmail.com" class="social-link">
        <span class="social-icon">✉️</span>
        <span>kosalaathapaththu1234@gmail.com</span>
      </a>
      <a href="https://github.com/kosaladathapththu" target="_blank" class="social-link">
        <span class="social-icon">⌥</span>
        <span>GitHub · kosaladathapththu</span>
      </a>
    </div>
  </div>

  <footer>
    Built with ♥ · Kosala Daneshwara Athapaththu · Colombo, Sri Lanka · 2025
  </footer>

</div>

<script>
  // Custom cursor
  const cur = document.getElementById('cur');
  const ring = document.getElementById('ring');
  let mx = 0, my = 0, rx = 0, ry = 0;
  document.addEventListener('mousemove', e => { mx = e.clientX; my = e.clientY; cur.style.left = mx-5+'px'; cur.style.top = my-5+'px'; });
  function animRing() {
    rx += (mx - rx) * 0.12;
    ry += (my - ry) * 0.12;
    ring.style.left = rx-18+'px';
    ring.style.top = ry-18+'px';
    requestAnimationFrame(animRing);
  }
  animRing();

  // Typing animation
  const lines = [
    "echo 'Welcome to my GitHub profile!'",
    "java -jar hotel-microservices.jar --port=8080",
    "git commit -m 'feat: add fraud detection pipeline'",
    "arduino-cli compile --fqbn arduino:avr:uno river-robot/",
    "npx create-react-app my-next-big-thing",
  ];
  let li = 0, ci = 0, deleting = false;
  const typed = document.getElementById('typed');
  function type() {
    const cur = lines[li];
    if (!deleting) {
      typed.textContent = cur.slice(0, ci++);
      if (ci > cur.length) { deleting = true; setTimeout(type, 2000); return; }
    } else {
      typed.textContent = cur.slice(0, ci--);
      if (ci < 0) { deleting = false; li = (li+1)%lines.length; ci = 0; setTimeout(type, 400); return; }
    }
    setTimeout(type, deleting ? 30 : 60);
  }
  setTimeout(type, 500);

  // Animated counters
  function animCount(id, target, suffix) {
    const el = document.getElementById(id);
    let n = 0;
    const step = Math.ceil(target / 60);
    const iv = setInterval(() => {
      n = Math.min(n+step, target);
      el.innerHTML = n + '<span>' + suffix + '</span>';
      if (n >= target) clearInterval(iv);
    }, 24);
  }
  setTimeout(() => {
    animCount('repoCount', 12, '+');
    animCount('contribCount', 247, '+');
    animCount('streakCount', 21, 'd');
  }, 400);

  // Contribution grid
  const grid = document.getElementById('contribGrid');
  const colors = ['#0b1120','#0e3a2a','#1a6b47','#21a366','#00ffa3'];
  for (let i = 0; i < 52*7; i++) {
    const c = document.createElement('div');
    c.className = 'contrib-cell';
    const level = Math.random() < 0.6 ? 0 : Math.floor(Math.random()*4)+1;
    c.style.background = colors[level];
    if (level > 0) c.style.boxShadow = level > 2 ? '0 0 4px rgba(0,255,163,0.3)' : 'none';
    grid.appendChild(c);
  }
</script>
</body>
</html>
