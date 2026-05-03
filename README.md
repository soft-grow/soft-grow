<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Softgrowtechsolution – GitHub Profile</title>
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #06090f;
      --surface: #0d1320;
      --border: #1a2540;
      --accent: #00d4ff;
      --accent2: #7c3aed;
      --accent3: #10b981;
      --text: #e2e8f0;
      --muted: #64748b;
      --glow: 0 0 24px rgba(0,212,255,0.18);
    }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'DM Mono', monospace;
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* Animated grid background */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(0,212,255,0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,212,255,0.03) 1px, transparent 1px);
      background-size: 40px 40px;
      pointer-events: none;
      z-index: 0;
    }

    .container {
      max-width: 900px;
      margin: 0 auto;
      padding: 48px 24px 80px;
      position: relative;
      z-index: 1;
    }

    /* ── LOGO HEADER ── */
    .header {
      display: flex;
      align-items: center;
      gap: 24px;
      margin-bottom: 48px;
      animation: fadeDown 0.8s ease both;
    }

    .logo-wrap {
      position: relative;
      flex-shrink: 0;
    }

    .logo-ring {
      position: absolute;
      inset: -6px;
      border-radius: 50%;
      border: 2px solid var(--accent);
      opacity: 0.4;
      animation: spin 8s linear infinite;
    }

    .logo-svg {
      width: 80px;
      height: 80px;
      display: block;
    }

    .brand-block {
      display: flex;
      flex-direction: column;
      gap: 4px;
    }

    .brand-name {
      font-family: 'Syne', sans-serif;
      font-size: 2rem;
      font-weight: 800;
      letter-spacing: -0.5px;
      line-height: 1;
      background: linear-gradient(90deg, #00d4ff 0%, #a855f7 60%, #10b981 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .brand-tagline {
      font-size: 0.72rem;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--muted);
    }

    .github-badge {
      margin-left: auto;
      display: flex;
      align-items: center;
      gap: 8px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 8px 14px;
      font-size: 0.75rem;
      color: var(--accent);
      text-decoration: none;
      transition: border-color 0.2s, box-shadow 0.2s;
    }
    .github-badge:hover { border-color: var(--accent); box-shadow: var(--glow); }
    .github-badge svg { width: 18px; height: 18px; fill: var(--accent); }

    /* ── HERO BANNER ── */
    .hero {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 40px 36px;
      margin-bottom: 28px;
      position: relative;
      overflow: hidden;
      animation: fadeUp 0.9s ease 0.1s both;
    }

    .hero::before {
      content: '';
      position: absolute;
      top: -60px; right: -60px;
      width: 220px; height: 220px;
      background: radial-gradient(circle, rgba(0,212,255,0.12) 0%, transparent 70%);
      pointer-events: none;
    }
    .hero::after {
      content: '';
      position: absolute;
      bottom: -40px; left: -40px;
      width: 180px; height: 180px;
      background: radial-gradient(circle, rgba(124,58,237,0.1) 0%, transparent 70%);
      pointer-events: none;
    }

    .hero-label {
      font-size: 0.65rem;
      letter-spacing: 4px;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 12px;
    }

    .hero-title {
      font-family: 'Syne', sans-serif;
      font-size: 1.7rem;
      font-weight: 700;
      line-height: 1.3;
      margin-bottom: 16px;
    }

    .hero-desc {
      font-size: 0.82rem;
      line-height: 1.9;
      color: var(--muted);
      max-width: 600px;
    }

    .highlight { color: var(--accent); }
    .highlight2 { color: #a855f7; }
    .highlight3 { color: var(--accent3); }

    /* ── STAT ROW ── */
    .stats-row {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 16px;
      margin-bottom: 28px;
      animation: fadeUp 0.9s ease 0.2s both;
    }

    .stat-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 22px 16px;
      text-align: center;
      transition: border-color 0.2s, transform 0.2s;
      cursor: default;
    }
    .stat-card:hover { border-color: var(--accent); transform: translateY(-3px); box-shadow: var(--glow); }

    .stat-value {
      font-family: 'Syne', sans-serif;
      font-size: 1.8rem;
      font-weight: 800;
      color: var(--accent);
      display: block;
    }
    .stat-label {
      font-size: 0.65rem;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--muted);
      margin-top: 4px;
    }

    /* ── SECTION TITLE ── */
    .section-title {
      font-family: 'Syne', sans-serif;
      font-size: 0.7rem;
      letter-spacing: 4px;
      text-transform: uppercase;
      color: var(--muted);
      margin-bottom: 16px;
      display: flex;
      align-items: center;
      gap: 10px;
    }
    .section-title::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--border);
    }

    /* ── TECH STACK ── */
    .tech-section {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 28px 28px 24px;
      margin-bottom: 28px;
      animation: fadeUp 0.9s ease 0.3s both;
    }

    .tech-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }

    .tech-chip {
      display: flex;
      align-items: center;
      gap: 7px;
      background: rgba(255,255,255,0.04);
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 6px 12px;
      font-size: 0.72rem;
      color: var(--text);
      letter-spacing: 0.5px;
      transition: border-color 0.2s, background 0.2s;
    }
    .tech-chip:hover { border-color: var(--accent); background: rgba(0,212,255,0.06); }
    .dot { width: 7px; height: 7px; border-radius: 50%; flex-shrink: 0; }
    .c-blue  { background: #00d4ff; }
    .c-green { background: #10b981; }
    .c-purple{ background: #a855f7; }
    .c-orange{ background: #f97316; }
    .c-red   { background: #ef4444; }
    .c-yellow{ background: #eab308; }

    /* ── SERVICES ── */
    .services-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 16px;
      margin-bottom: 28px;
      animation: fadeUp 0.9s ease 0.4s both;
    }

    .service-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 14px;
      padding: 24px 22px;
      transition: border-color 0.2s, box-shadow 0.2s;
      position: relative;
      overflow: hidden;
    }
    .service-card:hover { border-color: var(--accent2); box-shadow: 0 0 20px rgba(124,58,237,0.12); }

    .service-icon {
      font-size: 1.6rem;
      margin-bottom: 10px;
      display: block;
    }
    .service-name {
      font-family: 'Syne', sans-serif;
      font-size: 0.95rem;
      font-weight: 700;
      margin-bottom: 6px;
      color: var(--text);
    }
    .service-desc {
      font-size: 0.72rem;
      line-height: 1.7;
      color: var(--muted);
    }

    /* ── ACTIVITY / CONTRIB ── */
    .activity-section {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 28px 28px 24px;
      margin-bottom: 28px;
      animation: fadeUp 0.9s ease 0.45s both;
    }

    .contrib-grid {
      display: grid;
      grid-template-columns: repeat(52, 1fr);
      gap: 3px;
    }

    .contrib-cell {
      aspect-ratio: 1;
      border-radius: 2px;
      background: var(--border);
      transition: transform 0.1s;
    }
    .contrib-cell:hover { transform: scale(1.4); }
    .contrib-cell.l1 { background: rgba(0,212,255,0.2); }
    .contrib-cell.l2 { background: rgba(0,212,255,0.45); }
    .contrib-cell.l3 { background: rgba(0,212,255,0.7); }
    .contrib-cell.l4 { background: var(--accent); }

    /* ── FOOTER ── */
    .footer {
      text-align: center;
      padding-top: 20px;
      animation: fadeUp 0.9s ease 0.55s both;
    }

    .footer-line {
      font-size: 0.68rem;
      letter-spacing: 2px;
      color: var(--muted);
    }

    .cta-btn {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      margin-top: 20px;
      background: linear-gradient(135deg, #00d4ff, #7c3aed);
      color: #fff;
      border: none;
      border-radius: 8px;
      padding: 12px 28px;
      font-family: 'Syne', sans-serif;
      font-size: 0.85rem;
      font-weight: 700;
      letter-spacing: 1px;
      cursor: pointer;
      text-decoration: none;
      transition: opacity 0.2s, transform 0.2s;
    }
    .cta-btn:hover { opacity: 0.85; transform: translateY(-2px); }

    /* ── ANIMATIONS ── */
    @keyframes fadeDown {
      from { opacity: 0; transform: translateY(-20px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes spin {
      from { transform: rotate(0deg); }
      to   { transform: rotate(360deg); }
    }

    /* Responsive */
    @media (max-width: 640px) {
      .stats-row { grid-template-columns: repeat(2,1fr); }
      .services-grid { grid-template-columns: 1fr; }
      .brand-name { font-size: 1.4rem; }
      .contrib-grid { grid-template-columns: repeat(26, 1fr); }
      .header { flex-wrap: wrap; }
      .github-badge { margin-left: 0; }
    }
  </style>
</head>
<body>
<div class="container">

  <!-- ── HEADER ── -->
  <div class="header">
    <div class="logo-wrap">
      <div class="logo-ring"></div>
      <!-- SVG Logo: circuit + growth arrow -->
      <svg class="logo-svg" viewBox="0 0 80 80" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle cx="40" cy="40" r="38" fill="#0d1320" stroke="#1a2540" stroke-width="1.5"/>
        <!-- Circuit paths -->
        <path d="M16 40 H28" stroke="#00d4ff" stroke-width="1.5" stroke-linecap="round"/>
        <path d="M52 40 H64" stroke="#00d4ff" stroke-width="1.5" stroke-linecap="round"/>
        <path d="M40 16 V28" stroke="#7c3aed" stroke-width="1.5" stroke-linecap="round"/>
        <path d="M40 52 V64" stroke="#7c3aed" stroke-width="1.5" stroke-linecap="round"/>
        <!-- Center hexagon -->
        <polygon points="40,26 52,33 52,47 40,54 28,47 28,33" fill="none" stroke="#00d4ff" stroke-width="1.5" opacity="0.6"/>
        <!-- Growth arrow -->
        <polyline points="28,48 36,38 42,44 52,30" stroke="#10b981" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" fill="none"/>
        <polygon points="52,30 46,29 49,35" fill="#10b981"/>
        <!-- Nodes -->
        <circle cx="16" cy="40" r="2.5" fill="#00d4ff"/>
        <circle cx="64" cy="40" r="2.5" fill="#00d4ff"/>
        <circle cx="40" cy="16" r="2.5" fill="#7c3aed"/>
        <circle cx="40" cy="64" r="2.5" fill="#7c3aed"/>
      </svg>
    </div>

    <div class="brand-block">
      <span class="brand-name">Softgrowtechsolution</span>
      <span class="brand-tagline">Engineering the future, one commit at a time</span>
    </div>

    <a class="github-badge" href="https://github.com/Softgrowtechsolution" target="_blank">
      <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <path d="M12 .3C5.4.3 0 5.7 0 12.3c0 5.3 3.4 9.8 8.2 11.4.6.1.8-.3.8-.6v-2c-3.3.7-4-1.6-4-1.6-.5-1.4-1.3-1.8-1.3-1.8-1.1-.7.1-.7.1-.7 1.2.1 1.8 1.2 1.8 1.2 1 1.8 2.8 1.3 3.4 1 .1-.8.4-1.3.7-1.6-2.7-.3-5.5-1.3-5.5-5.9 0-1.3.5-2.4 1.2-3.2-.1-.3-.5-1.5.1-3.2 0 0 1-.3 3.3 1.2a11.5 11.5 0 0 1 6 0C17 4.2 18 4.5 18 4.5c.6 1.7.2 2.9.1 3.2.8.8 1.2 1.9 1.2 3.2 0 4.6-2.8 5.6-5.5 5.9.4.4.8 1.1.8 2.2v3.3c0 .3.2.7.8.6C20.6 22.1 24 17.6 24 12.3 24 5.7 18.6.3 12 .3z"/>
      </svg>
      github.com/Softgrowtechsolution
    </a>
  </div>

  <!-- ── HERO BANNER ── -->
  <div class="hero">
    <div class="hero-label">// about us</div>
    <h1 class="hero-title">
      Building <span class="highlight">Scalable</span> &amp; <span class="highlight2">Intelligent</span><br/>
      Software Solutions
    </h1>
    <p class="hero-desc">
      We are <span class="highlight">Softgrowtechsolution</span> — a full-stack IT company crafting 
      cutting-edge digital products. From enterprise web applications to AI-driven systems, 
      we engineer solutions that <span class="highlight3">grow your business</span> with precision, 
      performance, and passion.
    </p>
  </div>

  <!-- ── STATS ── -->
  <div class="stats-row">
    <div class="stat-card">
      <span class="stat-value">50+</span>
      <span class="stat-label">Projects Shipped</span>
    </div>
    <div class="stat-card">
      <span class="stat-value">30+</span>
      <span class="stat-label">Repositories</span>
    </div>
    <div class="stat-card">
      <span class="stat-value">10+</span>
      <span class="stat-label">Tech Domains</span>
    </div>
    <div class="stat-card">
      <span class="stat-value">100%</span>
      <span class="stat-label">Open to Collab</span>
    </div>
  </div>

  <!-- ── TECH STACK ── -->
  <div class="tech-section">
    <div class="section-title">⚙ tech stack</div>
    <div class="tech-grid">
      <span class="tech-chip"><span class="dot c-yellow"></span>JavaScript</span>
      <span class="tech-chip"><span class="dot c-blue"></span>TypeScript</span>
      <span class="tech-chip"><span class="dot c-green"></span>Node.js</span>
      <span class="tech-chip"><span class="dot c-blue"></span>React.js</span>
      <span class="tech-chip"><span class="dot c-blue"></span>Next.js</span>
      <span class="tech-chip"><span class="dot c-purple"></span>Python</span>
      <span class="tech-chip"><span class="dot c-blue"></span>Django</span>
      <span class="tech-chip"><span class="dot c-red"></span>Laravel / PHP</span>
      <span class="tech-chip"><span class="dot c-orange"></span>React Native</span>
      <span class="tech-chip"><span class="dot c-blue"></span>Flutter</span>
      <span class="tech-chip"><span class="dot c-green"></span>MongoDB</span>
      <span class="tech-chip"><span class="dot c-blue"></span>PostgreSQL</span>
      <span class="tech-chip"><span class="dot c-orange"></span>AWS</span>
      <span class="tech-chip"><span class="dot c-blue"></span>Docker</span>
      <span class="tech-chip"><span class="dot c-purple"></span>AI / ML</span>
      <span class="tech-chip"><span class="dot c-green"></span>GraphQL</span>
      <span class="tech-chip"><span class="dot c-red"></span>Redis</span>
      <span class="tech-chip"><span class="dot c-yellow"></span>CI/CD</span>
    </div>
  </div>

  <!-- ── SERVICES ── -->
  <div class="section-title" style="animation: fadeUp 0.9s ease 0.35s both;">🚀 what we build</div>
  <div class="services-grid">
    <div class="service-card">
      <span class="service-icon">🌐</span>
      <div class="service-name">Web Applications</div>
      <div class="service-desc">Full-stack web platforms, SaaS products, and enterprise portals built for performance and scale.</div>
    </div>
    <div class="service-card">
      <span class="service-icon">📱</span>
      <div class="service-name">Mobile Development</div>
      <div class="service-desc">Cross-platform iOS &amp; Android apps with React Native and Flutter — pixel-perfect &amp; production-ready.</div>
    </div>
    <div class="service-card">
      <span class="service-icon">🤖</span>
      <div class="service-name">AI &amp; Automation</div>
      <div class="service-desc">Smart integrations, AI-powered features, LLM pipelines, and intelligent workflow automation.</div>
    </div>
    <div class="service-card">
      <span class="service-icon">☁️</span>
      <div class="service-name">Cloud &amp; DevOps</div>
      <div class="service-desc">AWS/GCP infrastructure, containerised deployments, CI/CD pipelines, and 24/7 system monitoring.</div>
    </div>
  </div>

  <!-- ── CONTRIBUTION GRAPH ── -->
  <div class="activity-section">
    <div class="section-title">📊 contribution activity</div>
    <div class="contrib-grid" id="contribGrid"></div>
    <div style="margin-top:12px; display:flex; gap:8px; align-items:center; font-size:0.65rem; color:var(--muted);">
      <span>Less</span>
      <span class="dot" style="background:var(--border); width:10px; height:10px; border-radius:2px;"></span>
      <span class="dot" style="background:rgba(0,212,255,0.2); width:10px; height:10px; border-radius:2px;"></span>
      <span class="dot" style="background:rgba(0,212,255,0.45); width:10px; height:10px; border-radius:2px;"></span>
      <span class="dot" style="background:rgba(0,212,255,0.7); width:10px; height:10px; border-radius:2px;"></span>
      <span class="dot" style="background:var(--accent); width:10px; height:10px; border-radius:2px;"></span>
      <span>More</span>
    </div>
  </div>

  <!-- ── FOOTER ── -->
  <div class="footer">
    <p class="footer-line">// Softgrowtechsolution &nbsp;·&nbsp; building what matters &nbsp;·&nbsp; 2024–2026</p>
    <a class="cta-btn" href="https://github.com/Softgrowtechsolution" target="_blank">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="white">
        <path d="M12 .3C5.4.3 0 5.7 0 12.3c0 5.3 3.4 9.8 8.2 11.4.6.1.8-.3.8-.6v-2c-3.3.7-4-1.6-4-1.6-.5-1.4-1.3-1.8-1.3-1.8-1.1-.7.1-.7.1-.7 1.2.1 1.8 1.2 1.8 1.2 1 1.8 2.8 1.3 3.4 1 .1-.8.4-1.3.7-1.6-2.7-.3-5.5-1.3-5.5-5.9 0-1.3.5-2.4 1.2-3.2-.1-.3-.5-1.5.1-3.2 0 0 1-.3 3.3 1.2a11.5 11.5 0 0 1 6 0C17 4.2 18 4.5 18 4.5c.6 1.7.2 2.9.1 3.2.8.8 1.2 1.9 1.2 3.2 0 4.6-2.8 5.6-5.5 5.9.4.4.8 1.1.8 2.2v3.3c0 .3.2.7.8.6C20.6 22.1 24 17.6 24 12.3 24 5.7 18.6.3 12 .3z"/>
      </svg>
      View on GitHub
    </a>
  </div>

</div>

<script>
  // Generate contribution graph
  const grid = document.getElementById('contribGrid');
  const levels = ['', 'l1', 'l2', 'l3', 'l4'];
  const weights = [40, 25, 18, 12, 5];

  function weightedRandom() {
    const r = Math.random() * 100;
    let acc = 0;
    for (let i = 0; i < weights.length; i++) {
      acc += weights[i];
      if (r < acc) return levels[i];
    }
    return '';
  }

  for (let i = 0; i < 52 * 7; i++) {
    const cell = document.createElement('div');
    cell.className = 'contrib-cell ' + weightedRandom();
    grid.appendChild(cell);
  }
</script>
</body>
</html>
