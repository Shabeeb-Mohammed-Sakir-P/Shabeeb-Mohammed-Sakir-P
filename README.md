<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shabeeb Mohammed Sakir | ML Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #080b14;
    --surface: #0d1120;
    --card: #111827;
    --border: rgba(255,255,255,0.07);
    --accent1: #6ee7f7;
    --accent2: #a78bfa;
    --accent3: #f472b6;
    --accent4: #34d399;
    --accent5: #fbbf24;
    --text: #e2e8f0;
    --muted: #64748b;
    --font-display: 'Syne', sans-serif;
    --font-mono: 'Space Mono', monospace;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font-display);
    overflow-x: hidden;
  }

  /* ── Noise overlay ── */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none; z-index: 0; opacity: .5;
  }

  /* ── Grid lines ── */
  body::after {
    content: '';
    position: fixed; inset: 0;
    background-image:
      linear-gradient(rgba(110,231,247,.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(110,231,247,.03) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none; z-index: 0;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 0 24px 80px;
    position: relative; z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    padding: 80px 0 60px;
    position: relative;
  }

  .hero-label {
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--accent1);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 20px;
    opacity: 0;
    animation: fadeUp .6s ease forwards .2s;
  }

  .hero-name {
    font-size: clamp(42px, 8vw, 80px);
    font-weight: 800;
    line-height: 1;
    margin-bottom: 12px;
    opacity: 0;
    animation: fadeUp .7s ease forwards .4s;
  }

  .hero-name span {
    background: linear-gradient(135deg, var(--accent1), var(--accent2), var(--accent3));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-tagline {
    font-family: var(--font-mono);
    font-size: 16px;
    color: var(--accent4);
    margin-bottom: 28px;
    min-height: 24px;
    opacity: 0;
    animation: fadeUp .7s ease forwards .6s;
  }

  .cursor {
    display: inline-block;
    width: 2px; height: 18px;
    background: var(--accent4);
    vertical-align: middle;
    margin-left: 3px;
    animation: blink 1s step-end infinite;
  }

  .hero-bio {
    max-width: 560px;
    font-size: 15px;
    line-height: 1.8;
    color: #94a3b8;
    margin-bottom: 36px;
    opacity: 0;
    animation: fadeUp .7s ease forwards .8s;
  }

  .hero-bio strong { color: var(--accent1); font-weight: 600; }

  .hero-cta {
    display: flex; gap: 14px; flex-wrap: wrap;
    opacity: 0;
    animation: fadeUp .7s ease forwards 1s;
  }

  .btn {
    font-family: var(--font-mono);
    font-size: 12px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    padding: 12px 24px;
    border-radius: 6px;
    border: none;
    cursor: pointer;
    text-decoration: none;
    transition: transform .2s, box-shadow .2s;
    display: inline-flex; align-items: center; gap: 8px;
  }

  .btn:hover { transform: translateY(-2px); }

  .btn-primary {
    background: linear-gradient(135deg, var(--accent2), var(--accent3));
    color: #fff;
    box-shadow: 0 0 24px rgba(167,139,250,.3);
  }

  .btn-primary:hover { box-shadow: 0 0 36px rgba(167,139,250,.5); }

  .btn-outline {
    background: transparent;
    color: var(--accent1);
    border: 1px solid rgba(110,231,247,.3);
    box-shadow: 0 0 16px rgba(110,231,247,.1);
  }

  .btn-outline:hover { border-color: var(--accent1); box-shadow: 0 0 24px rgba(110,231,247,.25); }

  /* ── Floating orbs ── */
  .orb {
    position: absolute;
    border-radius: 50%;
    filter: blur(80px);
    pointer-events: none;
    z-index: -1;
  }

  .orb1 { width: 340px; height: 340px; background: rgba(167,139,250,.12); top: -60px; right: -80px; animation: float 8s ease-in-out infinite; }
  .orb2 { width: 220px; height: 220px; background: rgba(110,231,247,.08); top: 100px; right: 120px; animation: float 10s ease-in-out infinite .5s; }
  .orb3 { width: 180px; height: 180px; background: rgba(244,114,182,.08); top: 40px; right: 300px; animation: float 12s ease-in-out infinite 1s; }

  /* ── Section headings ── */
  section { margin-bottom: 64px; }

  .section-header {
    display: flex; align-items: center; gap: 16px;
    margin-bottom: 32px;
  }

  .section-tag {
    font-family: var(--font-mono);
    font-size: 11px;
    color: var(--accent2);
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  .section-title {
    font-size: 26px;
    font-weight: 700;
    color: var(--text);
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, rgba(167,139,250,.3), transparent);
  }

  /* ── Stats bar ── */
  .stats-bar {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 2px;
    margin-bottom: 64px;
    opacity: 0;
    animation: fadeUp .7s ease forwards 1.1s;
  }

  .stat-item {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 20px 16px;
    text-align: center;
  }

  .stat-item:first-child { border-radius: 10px 0 0 10px; }
  .stat-item:last-child { border-radius: 0 10px 10px 0; }

  .stat-num {
    font-size: 28px;
    font-weight: 800;
    background: linear-gradient(135deg, var(--accent1), var(--accent2));
    -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
    display: block;
  }

  .stat-label {
    font-family: var(--font-mono);
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 1.5px;
    text-transform: uppercase;
    margin-top: 4px;
  }

  /* ── Journey timeline ── */
  .timeline {
    position: relative;
    padding-left: 28px;
  }

  .timeline::before {
    content: '';
    position: absolute;
    left: 0; top: 6px; bottom: 0;
    width: 1px;
    background: linear-gradient(to bottom, var(--accent2), var(--accent3), transparent);
  }

  .tl-item {
    position: relative;
    margin-bottom: 32px;
    opacity: 0;
    transform: translateX(-12px);
    transition: opacity .5s, transform .5s;
  }

  .tl-item.visible { opacity: 1; transform: translateX(0); }

  .tl-dot {
    position: absolute;
    left: -34px; top: 4px;
    width: 12px; height: 12px;
    border-radius: 50%;
    border: 2px solid var(--accent2);
    background: var(--bg);
  }

  .tl-dot::after {
    content: '';
    position: absolute;
    inset: 2px;
    border-radius: 50%;
    background: var(--accent2);
    animation: pulse 2s ease infinite;
  }

  .tl-year {
    font-family: var(--font-mono);
    font-size: 11px;
    color: var(--accent2);
    letter-spacing: 2px;
    margin-bottom: 6px;
  }

  .tl-title {
    font-size: 16px;
    font-weight: 700;
    margin-bottom: 4px;
  }

  .tl-desc {
    font-size: 13px;
    color: #64748b;
    line-height: 1.7;
  }

  /* ── Skills ── */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 16px;
  }

  .skill-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    position: relative;
    overflow: hidden;
    transition: transform .25s, border-color .25s, box-shadow .25s;
  }

  .skill-card:hover {
    transform: translateY(-3px);
    border-color: rgba(255,255,255,.15);
    box-shadow: 0 12px 40px rgba(0,0,0,.4);
  }

  .skill-card::before {
    content: '';
    position: absolute;
    inset: 0;
    opacity: 0;
    transition: opacity .3s;
  }

  .skill-card:hover::before { opacity: 1; }

  .sk-blue::before   { background: linear-gradient(135deg, rgba(110,231,247,.05), transparent); }
  .sk-purple::before { background: linear-gradient(135deg, rgba(167,139,250,.05), transparent); }
  .sk-pink::before   { background: linear-gradient(135deg, rgba(244,114,182,.05), transparent); }
  .sk-green::before  { background: linear-gradient(135deg, rgba(52,211,153,.05), transparent); }
  .sk-amber::before  { background: linear-gradient(135deg, rgba(251,191,36,.05), transparent); }

  .skill-icon {
    font-size: 24px;
    margin-bottom: 10px;
    display: block;
  }

  .skill-name {
    font-size: 13px;
    font-weight: 700;
    margin-bottom: 10px;
    letter-spacing: .5px;
  }

  .skill-bar-track {
    height: 3px;
    background: rgba(255,255,255,.06);
    border-radius: 2px;
    overflow: hidden;
    margin-bottom: 6px;
  }

  .skill-bar-fill {
    height: 100%;
    border-radius: 2px;
    width: 0;
    transition: width 1.4s cubic-bezier(.22,1,.36,1);
  }

  .fill-blue   { background: linear-gradient(90deg, var(--accent1), #38bdf8); }
  .fill-purple { background: linear-gradient(90deg, var(--accent2), #c4b5fd); }
  .fill-pink   { background: linear-gradient(90deg, var(--accent3), #fb7185); }
  .fill-green  { background: linear-gradient(90deg, var(--accent4), #6ee7b7); }
  .fill-amber  { background: linear-gradient(90deg, var(--accent5), #fcd34d); }

  .skill-pct {
    font-family: var(--font-mono);
    font-size: 10px;
    color: var(--muted);
    text-align: right;
  }

  .skill-tags {
    display: flex; flex-wrap: wrap; gap: 5px;
    margin-top: 10px;
  }

  .tag {
    font-family: var(--font-mono);
    font-size: 10px;
    padding: 3px 8px;
    border-radius: 4px;
    border: 1px solid rgba(255,255,255,.08);
    color: var(--muted);
  }

  /* ── Projects ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 20px;
  }

  .proj-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 26px;
    position: relative;
    overflow: hidden;
    cursor: pointer;
    transition: transform .25s, box-shadow .25s, border-color .25s;
  }

  .proj-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 20px 60px rgba(0,0,0,.5);
  }

  .proj-glow {
    position: absolute;
    top: -40px; right: -40px;
    width: 120px; height: 120px;
    border-radius: 50%;
    filter: blur(40px);
    opacity: .4;
    transition: opacity .3s;
  }

  .proj-card:hover .proj-glow { opacity: .7; }

  .glow-cyan   { background: var(--accent1); }
  .glow-purple { background: var(--accent2); }
  .glow-pink   { background: var(--accent3); }
  .glow-green  { background: var(--accent4); }

  .proj-badge {
    display: inline-flex; align-items: center; gap: 6px;
    font-family: var(--font-mono);
    font-size: 10px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    padding: 4px 10px;
    border-radius: 4px;
    margin-bottom: 14px;
  }

  .badge-cyan   { background: rgba(110,231,247,.12); color: var(--accent1); border: 1px solid rgba(110,231,247,.2); }
  .badge-purple { background: rgba(167,139,250,.12); color: var(--accent2); border: 1px solid rgba(167,139,250,.2); }
  .badge-pink   { background: rgba(244,114,182,.12); color: var(--accent3); border: 1px solid rgba(244,114,182,.2); }
  .badge-green  { background: rgba(52,211,153,.12);  color: var(--accent4); border: 1px solid rgba(52,211,153,.2); }

  .proj-title {
    font-size: 18px;
    font-weight: 700;
    margin-bottom: 8px;
    line-height: 1.3;
  }

  .proj-desc {
    font-size: 13px;
    color: #64748b;
    line-height: 1.7;
    margin-bottom: 16px;
  }

  .proj-stack {
    display: flex; flex-wrap: wrap; gap: 6px;
    margin-bottom: 18px;
  }

  .stack-pill {
    font-family: var(--font-mono);
    font-size: 10px;
    padding: 4px 9px;
    border-radius: 20px;
    background: rgba(255,255,255,.04);
    border: 1px solid rgba(255,255,255,.08);
    color: #94a3b8;
  }

  .proj-metrics {
    display: flex; gap: 16px;
    padding-top: 14px;
    border-top: 1px solid var(--border);
  }

  .metric {
    font-family: var(--font-mono);
    font-size: 11px;
    color: var(--muted);
  }

  .metric strong {
    display: block;
    font-size: 14px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 1px;
  }

  /* ── GitHub stats embed ── */
  .github-section {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }

  .gh-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
  }

  .gh-card img { width: 100%; display: block; }

  .gh-langs { grid-column: 1 / -1; }

  /* ── Currently learning ── */
  .learning-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 12px;
  }

  .learn-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px;
    display: flex; align-items: flex-start; gap: 12px;
    transition: border-color .2s, transform .2s;
  }

  .learn-item:hover { border-color: rgba(255,255,255,.15); transform: translateY(-2px); }

  .learn-icon {
    width: 36px; height: 36px;
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    font-size: 18px;
    flex-shrink: 0;
  }

  .learn-text .learn-title { font-size: 13px; font-weight: 700; margin-bottom: 3px; }
  .learn-text .learn-sub { font-size: 11px; color: var(--muted); line-height: 1.5; }

  /* ── Footer ── */
  .footer {
    border-top: 1px solid var(--border);
    padding-top: 32px;
    display: flex; align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 16px;
  }

  .footer-left {
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--muted);
  }

  .footer-left span { color: var(--accent3); }

  .social-links { display: flex; gap: 12px; }

  .social-link {
    width: 36px; height: 36px;
    border: 1px solid var(--border);
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    color: var(--muted);
    text-decoration: none;
    font-size: 15px;
    transition: border-color .2s, color .2s, transform .2s;
  }

  .social-link:hover { border-color: var(--accent2); color: var(--accent2); transform: translateY(-2px); }

  /* ── Keyframes ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(18px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes float {
    0%, 100% { transform: translateY(0) scale(1); }
    50%       { transform: translateY(-20px) scale(1.04); }
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50%       { opacity: 0; }
  }

  @keyframes pulse {
    0%, 100% { transform: scale(1); opacity: 1; }
    50%       { transform: scale(1.5); opacity: .4; }
  }

  @keyframes spin-slow {
    to { transform: rotate(360deg); }
  }

  /* ── Scrollbar ── */
  ::-webkit-scrollbar { width: 5px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: rgba(167,139,250,.3); border-radius: 3px; }

  /* ── Responsive ── */
  @media (max-width: 600px) {
    .stats-bar { grid-template-columns: repeat(2,1fr); }
    .stats-bar .stat-item:first-child { border-radius: 10px 0 0 0; }
    .stats-bar .stat-item:last-child  { border-radius: 0 0 10px 0; }
    .github-section { grid-template-columns: 1fr; }
    .gh-langs { grid-column: 1; }
  }
</style>
</head>
<body>

<div class="container">

  <!-- ── HERO ── -->
  <div class="hero">
    <div class="orb orb1"></div>
    <div class="orb orb2"></div>
    <div class="orb orb3"></div>

    <p class="hero-label">// ML Engineer & Data Scientist</p>

    <h1 class="hero-name">
      <span>Shabeeb</span><br>Mohammed Sakir
    </h1>

    <p class="hero-tagline" id="tagline">
      <span id="typed-text"></span><span class="cursor"></span>
    </p>

    <p class="hero-bio">
      Started with <strong>Mathematics</strong>, ended up teaching machines how to learn.
      Building ML systems at the intersection of <strong>NLP</strong>, <strong>Computer Vision</strong>,
      and real-world impact — from resume screeners to traffic safety systems.
    </p>

    <div class="hero-cta">
      <a class="btn btn-primary" href="https://www.linkedin.com/in/shabeeb-mohammed-sakir-257895341" target="_blank">
        ↗ Connect on LinkedIn
      </a>
      <a class="btn btn-outline" href="https://github.com/Shabeeb-Mohammed-Sakir-P" target="_blank">
        ⌥ View GitHub
      </a>
    </div>
  </div>

  <!-- ── STATS ── -->
  <div class="stats-bar">
    <div class="stat-item">
      <span class="stat-num" data-target="3">0</span>
      <span class="stat-label">ML Projects</span>
    </div>
    <div class="stat-item">
      <span class="stat-num" data-target="8">0</span>
      <span class="stat-label">Tech Stack</span>
    </div>
    <div class="stat-item">
      <span class="stat-num" data-target="95">0</span>
      <span class="stat-label">Python %</span>
    </div>
    <div class="stat-item">
      <span class="stat-num" data-target="2">0</span>
      <span class="stat-label">Years Learning</span>
    </div>
  </div>

  <!-- ── JOURNEY ── -->
  <section>
    <div class="section-header">
      <span class="section-tag">01</span>
      <h2 class="section-title">My Journey</h2>
      <div class="section-line"></div>
    </div>

    <div class="timeline">
      <div class="tl-item">
        <div class="tl-dot"></div>
        <div class="tl-year">THE BEGINNING</div>
        <div class="tl-title">Mathematics → Data Science</div>
        <div class="tl-desc">Fell in love with patterns and proofs. Discovered that machines could learn from data — and never looked back. Started with Python, statistics, and an insatiable curiosity.</div>
      </div>
      <div class="tl-item">
        <div class="tl-dot" style="border-color:var(--accent3)"></div>
        <div class="tl-year" style="color:var(--accent3)">BUILDING SKILLS</div>
        <div class="tl-title">ML Foundations & EDA</div>
        <div class="tl-desc">Mastered scikit-learn, Pandas, and visualisation tools. Built end-to-end pipelines — from messy raw data to actionable insights. EDA became an art form.</div>
      </div>
      <div class="tl-item">
        <div class="tl-dot" style="border-color:var(--accent4)"></div>
        <div class="tl-year" style="color:var(--accent4)">GOING DEEP</div>
        <div class="tl-title">Deep Learning & Computer Vision</div>
        <div class="tl-desc">Dived into PyTorch and TensorFlow. Built real systems: pose estimation, traffic safety detection, and NLP-powered resume screeners. OpenCV became a daily companion.</div>
      </div>
      <div class="tl-item">
        <div class="tl-dot" style="border-color:var(--accent5)"></div>
        <div class="tl-year" style="color:var(--accent5)">NOW</div>
        <div class="tl-title">MLOps, Cloud & Beyond</div>
        <div class="tl-desc">Learning how to ship and scale — AWS, MLOps, model optimisation, deployment. Building systems that don't just work in notebooks but actually go to production.</div>
      </div>
    </div>
  </section>

  <!-- ── SKILLS ── -->
  <section>
    <div class="section-header">
      <span class="section-tag">02</span>
      <h2 class="section-title">Tech Arsenal</h2>
      <div class="section-line"></div>
    </div>

    <div class="skills-grid">
      <div class="skill-card sk-blue">
        <span class="skill-icon">🐍</span>
        <div class="skill-name">Python</div>
        <div class="skill-bar-track"><div class="skill-bar-fill fill-blue" data-pct="95"></div></div>
        <div class="skill-pct">95%</div>
        <div class="skill-tags">
          <span class="tag">scripting</span><span class="tag">OOP</span><span class="tag">pipelines</span>
        </div>
      </div>

      <div class="skill-card sk-amber">
        <span class="skill-icon">🧠</span>
        <div class="skill-name">Machine Learning</div>
        <div class="skill-bar-track"><div class="skill-bar-fill fill-amber" data-pct="85"></div></div>
        <div class="skill-pct">85%</div>
        <div class="skill-tags">
          <span class="tag">scikit-learn</span><span class="tag">EDA</span><span class="tag">regression</span>
        </div>
      </div>

      <div class="skill-card sk-purple">
        <span class="skill-icon">🔥</span>
        <div class="skill-name">Deep Learning</div>
        <div class="skill-bar-track"><div class="skill-bar-fill fill-purple" data-pct="78"></div></div>
        <div class="skill-pct">78%</div>
        <div class="skill-tags">
          <span class="tag">PyTorch</span><span class="tag">TensorFlow</span><span class="tag">CNNs</span>
        </div>
      </div>

      <div class="skill-card sk-pink">
        <span class="skill-icon">👁️</span>
        <div class="skill-name">Computer Vision</div>
        <div class="skill-bar-track"><div class="skill-bar-fill fill-pink" data-pct="80"></div></div>
        <div class="skill-pct">80%</div>
        <div class="skill-tags">
          <span class="tag">OpenCV</span><span class="tag">YOLO</span><span class="tag">MediaPipe</span>
        </div>
      </div>

      <div class="skill-card sk-green">
        <span class="skill-icon">💬</span>
        <div class="skill-name">NLP</div>
        <div class="skill-bar-track"><div class="skill-bar-fill fill-green" data-pct="72"></div></div>
        <div class="skill-pct">72%</div>
        <div class="skill-tags">
          <span class="tag">NLTK</span><span class="tag">spaCy</span><span class="tag">transformers</span>
        </div>
      </div>

      <div class="skill-card sk-blue">
        <span class="skill-icon">📊</span>
        <div class="skill-name">Data Analysis</div>
        <div class="skill-bar-track"><div class="skill-bar-fill fill-blue" data-pct="90"></div></div>
        <div class="skill-pct">90%</div>
        <div class="skill-tags">
          <span class="tag">Pandas</span><span class="tag">NumPy</span><span class="tag">SciPy</span>
        </div>
      </div>

      <div class="skill-card sk-amber">
        <span class="skill-icon">📈</span>
        <div class="skill-name">Visualisation</div>
        <div class="skill-bar-track"><div class="skill-bar-fill fill-amber" data-pct="85"></div></div>
        <div class="skill-pct">85%</div>
        <div class="skill-tags">
          <span class="tag">Matplotlib</span><span class="tag">Seaborn</span><span class="tag">Plotly</span>
        </div>
      </div>

      <div class="skill-card sk-purple">
        <span class="skill-icon">🗄️</span>
        <div class="skill-name">SQL & Databases</div>
        <div class="skill-bar-track"><div class="skill-bar-fill fill-purple" data-pct="75"></div></div>
        <div class="skill-pct">75%</div>
        <div class="skill-tags">
          <span class="tag">MySQL</span><span class="tag">queries</span><span class="tag">schema</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ── PROJECTS ── -->
  <section>
    <div class="section-header">
      <span class="section-tag">03</span>
      <h2 class="section-title">Featured Projects</h2>
      <div class="section-line"></div>
    </div>

    <div class="projects-grid">

      <div class="proj-card" style="border-color:rgba(110,231,247,.12)">
        <div class="proj-glow glow-cyan"></div>
        <div class="proj-badge badge-cyan">⚡ NLP</div>
        <h3 class="proj-title">AI Resume Screener</h3>
        <p class="proj-desc">Automated resume-to-job-description matching system using TF-IDF and semantic similarity. Ranks candidates with explainable scoring.</p>
        <div class="proj-stack">
          <span class="stack-pill">Python</span>
          <span class="stack-pill">NLTK</span>
          <span class="stack-pill">scikit-learn</span>
          <span class="stack-pill">Pandas</span>
        </div>
        <div class="proj-metrics">
          <div class="metric"><strong>87%</strong>Accuracy</div>
          <div class="metric"><strong>NLP</strong>Core Tech</div>
          <div class="metric"><strong>Real-world</strong>Use Case</div>
        </div>
      </div>

      <div class="proj-card" style="border-color:rgba(244,114,182,.12)">
        <div class="proj-glow glow-pink"></div>
        <div class="proj-badge badge-pink">🚦 CV</div>
        <h3 class="proj-title">Traffic Safety Detection</h3>
        <p class="proj-desc">Real-time computer vision system detecting unsafe driving behaviours — helmet violations, lane breaches — using YOLO on live video feeds.</p>
        <div class="proj-stack">
          <span class="stack-pill">OpenCV</span>
          <span class="stack-pill">YOLO</span>
          <span class="stack-pill">PyTorch</span>
          <span class="stack-pill">Python</span>
        </div>
        <div class="proj-metrics">
          <div class="metric"><strong>Real-time</strong>Processing</div>
          <div class="metric"><strong>YOLO</strong>Core Tech</div>
          <div class="metric"><strong>Safety</strong>Impact</div>
        </div>
      </div>

      <div class="proj-card" style="border-color:rgba(167,139,250,.12)">
        <div class="proj-glow glow-purple"></div>
        <div class="proj-badge badge-purple">🏃 CV</div>
        <h3 class="proj-title">Human Pose Estimation</h3>
        <p class="proj-desc">Skeleton keypoint detection and pose classification using MediaPipe and deep learning. Applied to fitness form analysis and gesture recognition.</p>
        <div class="proj-stack">
          <span class="stack-pill">MediaPipe</span>
          <span class="stack-pill">TensorFlow</span>
          <span class="stack-pill">OpenCV</span>
          <span class="stack-pill">NumPy</span>
        </div>
        <div class="proj-metrics">
          <div class="metric"><strong>33</strong>Keypoints</div>
          <div class="metric"><strong>MediaPipe</strong>Backbone</div>
          <div class="metric"><strong>Fitness</strong>Domain</div>
        </div>
      </div>

    </div>
  </section>

  <!-- ── CURRENTLY LEARNING ── -->
  <section>
    <div class="section-header">
      <span class="section-tag">04</span>
      <h2 class="section-title">Currently Learning</h2>
      <div class="section-line"></div>
    </div>

    <div class="learning-grid">
      <div class="learn-item">
        <div class="learn-icon" style="background:rgba(110,231,247,.1)">☁️</div>
        <div class="learn-text">
          <div class="learn-title">AWS</div>
          <div class="learn-sub">Cloud-based data engineering & ML deployment</div>
        </div>
      </div>
      <div class="learn-item">
        <div class="learn-icon" style="background:rgba(167,139,250,.1)">⚙️</div>
        <div class="learn-text">
          <div class="learn-title">MLOps</div>
          <div class="learn-sub">Model versioning, CI/CD, and monitoring</div>
        </div>
      </div>
      <div class="learn-item">
        <div class="learn-icon" style="background:rgba(244,114,182,.1)">🚀</div>
        <div class="learn-text">
          <div class="learn-title">Model Optimisation</div>
          <div class="learn-sub">Quantisation, pruning, and inference speed</div>
        </div>
      </div>
      <div class="learn-item">
        <div class="learn-icon" style="background:rgba(52,211,153,.1)">🤗</div>
        <div class="learn-text">
          <div class="learn-title">Transformers</div>
          <div class="learn-sub">Advanced NLP with HuggingFace</div>
        </div>
      </div>
    </div>
  </section>

  <!-- ── GITHUB STATS ── -->
  <section>
    <div class="section-header">
      <span class="section-tag">05</span>
      <h2 class="section-title">GitHub Activity</h2>
      <div class="section-line"></div>
    </div>

    <div class="github-section">
      <div class="gh-card">
        <img src="https://github-readme-stats.vercel.app/api?username=Shabeeb-Mohammed-Sakir-P&theme=transparent&hide_border=true&include_all_commits=true&count_private=true&title_color=a78bfa&icon_color=6ee7f7&text_color=94a3b8&bg_color=00000000" alt="GitHub Stats" loading="lazy">
      </div>
      <div class="gh-card">
        <img src="https://nirzak-streak-stats.vercel.app/?user=Shabeeb-Mohammed-Sakir-P&theme=transparent&hide_border=true&ring=a78bfa&fire=f472b6&currStreakLabel=6ee7f7&sideLabels=94a3b8&currStreakNum=e2e8f0&sideNums=e2e8f0&dates=64748b&background=00000000" alt="GitHub Streak" loading="lazy">
      </div>
      <div class="gh-card gh-langs">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Shabeeb-Mohammed-Sakir-P&theme=transparent&hide_border=true&include_all_commits=true&count_private=true&layout=compact&title_color=a78bfa&text_color=94a3b8&bg_color=00000000" alt="Top Languages" loading="lazy">
      </div>
    </div>
  </section>

  <!-- ── FOOTER ── -->
  <footer class="footer">
    <div class="footer-left">
      built with <span>♥</span> + curiosity · open to collaborate
    </div>
    <div class="social-links">
      <a class="social-link" href="https://www.linkedin.com/in/shabeeb-mohammed-sakir-257895341" target="_blank" title="LinkedIn">in</a>
      <a class="social-link" href="https://github.com/Shabeeb-Mohammed-Sakir-P" target="_blank" title="GitHub">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61-.546-1.385-1.335-1.755-1.335-1.755-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.605-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 21.795 24 17.295 24 12c0-6.63-5.37-12-12-12"/></svg>
      </a>
    </div>
  </footer>

</div><!-- /container -->

<script>
/* ── Typing animation ── */
const phrases = [
  'Building intelligent systems 🤖',
  'Turning data into insights 📊',
  'Teaching machines to see 👁️',
  'NLP • CV • Deep Learning',
  'From mathematics to ML 📐',
];
let phraseIdx = 0, charIdx = 0, deleting = false;
const el = document.getElementById('typed-text');

function type() {
  const phrase = phrases[phraseIdx];
  if (!deleting) {
    el.textContent = phrase.slice(0, ++charIdx);
    if (charIdx === phrase.length) { deleting = true; setTimeout(type, 1800); return; }
  } else {
    el.textContent = phrase.slice(0, --charIdx);
    if (charIdx === 0) { deleting = false; phraseIdx = (phraseIdx + 1) % phrases.length; }
  }
  setTimeout(type, deleting ? 45 : 85);
}
type();

/* ── Counter animation ── */
function animateCounter(el, target) {
  let current = 0;
  const duration = 1600;
  const step = target / (duration / 16);
  const timer = setInterval(() => {
    current = Math.min(current + step, target);
    el.textContent = Math.round(current) + (el.dataset.target >= 90 ? '%' : '+');
    if (current >= target) clearInterval(timer);
  }, 16);
}

const counterObs = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      const nums = document.querySelectorAll('.stat-num');
      nums.forEach(n => animateCounter(n, +n.dataset.target));
      counterObs.disconnect();
    }
  });
}, { threshold: 0.5 });
counterObs.observe(document.querySelector('.stats-bar'));

/* ── Skill bars ── */
const barObs = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      document.querySelectorAll('.skill-bar-fill').forEach(bar => {
        bar.style.width = bar.dataset.pct + '%';
      });
      barObs.disconnect();
    }
  });
}, { threshold: 0.2 });
barObs.observe(document.querySelector('.skills-grid'));

/* ── Timeline reveal ── */
const tlObs = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) e.target.classList.add('visible');
  });
}, { threshold: 0.15 });
document.querySelectorAll('.tl-item').forEach((item, i) => {
  item.style.transitionDelay = i * 120 + 'ms';
  tlObs.observe(item);
});
</script>
</body>
</html>
