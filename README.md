<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Ansh Pandey — Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --bg: #080811;
    --bg2: #0e0e1a;
    --bg3: #13131f;
    --border: rgba(255,255,255,0.07);
    --border-hover: rgba(55,138,221,0.5);
    --blue: #378ADD;
    --blue-light: #85B7EB;
    --purple: #7F77DD;
    --purple-light: #AFA9EC;
    --teal: #1D9E75;
    --teal-light: #5DCAA5;
    --coral: #D85A30;
    --coral-light: #F0997B;
    --red: #E24B4A;
    --amber: #EF9F27;
    --green: #639922;
    --pink: #D4537E;
    --text: #e2e8f0;
    --text-muted: #64748b;
    --text-dim: #334155;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Syne', sans-serif;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    line-height: 1.6;
  }

  /* ── HERO ── */
  .hero {
    position: relative;
    padding: 56px 40px 48px;
    display: flex;
    align-items: center;
    gap: 36px;
    border-bottom: 1px solid var(--border);
    overflow: hidden;
  }

  .hero-bg {
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 60% 80% at 0% 0%, rgba(55,138,221,0.12) 0%, transparent 60%),
      radial-gradient(ellipse 40% 60% at 100% 100%, rgba(127,119,221,0.1) 0%, transparent 60%);
    pointer-events: none;
  }

  .grid-lines {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(255,255,255,0.02) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.02) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
  }

  /* Avatar */
  .avatar-wrap {
    position: relative;
    flex-shrink: 0;
    z-index: 2;
  }

  .avatar-spin {
    position: absolute;
    inset: -5px;
    border-radius: 50%;
    background: conic-gradient(var(--blue), var(--purple), var(--teal), var(--blue));
    animation: spin 5s linear infinite;
  }

  @keyframes spin { to { transform: rotate(360deg); } }

  .avatar-inner {
    position: relative;
    z-index: 1;
    width: 110px;
    height: 110px;
    border-radius: 50%;
    border: 3px solid var(--bg);
    overflow: hidden;
    background: linear-gradient(135deg, var(--blue), var(--purple));
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 38px;
    font-weight: 800;
    color: #fff;
  }

  .avatar-inner img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
  }

  .hero-text { position: relative; z-index: 2; }

  .hero-text h1 {
    font-size: 32px;
    font-weight: 800;
    color: #fff;
    letter-spacing: -0.5px;
    line-height: 1.15;
  }

  .hero-text h1 span {
    background: linear-gradient(90deg, var(--blue-light), var(--purple-light));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .role-line {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-top: 8px;
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    color: var(--blue);
  }

  .pulse-dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: var(--teal);
    animation: pulseAnim 2s ease-in-out infinite;
  }

  @keyframes pulseAnim {
    0%, 100% { opacity: 1; transform: scale(1); box-shadow: 0 0 0 0 rgba(29,158,117,0.5); }
    50% { opacity: 0.7; transform: scale(0.85); box-shadow: 0 0 0 6px rgba(29,158,117,0); }
  }

  .typing-text {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    color: #36BCF7;
    margin-top: 8px;
    border-right: 2px solid #36BCF7;
    white-space: nowrap;
    overflow: hidden;
    width: 0;
    animation: typeWriter 2.8s steps(45) 0.8s forwards, blinkCursor 0.75s step-end infinite;
  }

  @keyframes typeWriter { to { width: 28ch; } }
  @keyframes blinkCursor { 50% { border-color: transparent; } }

  .hero-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 14px;
  }

  .badge {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    padding: 4px 12px;
    border-radius: 999px;
    font-weight: 700;
    letter-spacing: 0.5px;
  }

  .badge-blue   { background: rgba(4,44,83,0.8);  border: 1px solid var(--blue);   color: var(--blue-light); }
  .badge-purple { background: rgba(38,33,92,0.8); border: 1px solid var(--purple); color: var(--purple-light); }
  .badge-teal   { background: rgba(4,52,44,0.8);  border: 1px solid var(--teal);   color: var(--teal-light); }
  .badge-coral  { background: rgba(74,27,12,0.8); border: 1px solid var(--coral);  color: var(--coral-light); }

  /* ── SECTIONS ── */
  .section {
    padding: 36px 40px;
    border-bottom: 1px solid var(--border);
  }

  .sec-title {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--purple);
    margin-bottom: 22px;
  }

  .sec-title svg { flex-shrink: 0; }

  .sec-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── GITHUB STATS ── */
  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }

  .stats-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 14px;
    overflow: hidden;
    transition: border-color 0.25s, transform 0.25s;
  }

  .stats-card:hover {
    border-color: var(--border-hover);
    transform: translateY(-3px);
  }

  .stats-card.full { grid-column: 1 / -1; }

  .stats-card img {
    width: 100%;
    height: auto;
    display: block;
    background: var(--bg2);
  }

  .stats-card .card-label {
    padding: 8px 16px 12px;
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--text-muted);
    border-top: 1px solid var(--border);
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .dot-label {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--blue);
  }

  /* ── CONTRIBUTION GRAPH ── */
  .graph-wrap {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 14px;
    overflow: hidden;
    transition: border-color 0.25s;
  }

  .graph-wrap:hover { border-color: var(--border-hover); }

  .graph-wrap img {
    width: 100%;
    height: auto;
    display: block;
  }

  /* ── TECH STACK ── */
  .tech-categories { display: flex; flex-direction: column; gap: 18px; }

  .tech-category-title {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--text-muted);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 8px;
  }

  .tech-row {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tech-pill {
    display: flex;
    align-items: center;
    gap: 7px;
    padding: 7px 14px;
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 8px;
    font-size: 13px;
    font-weight: 600;
    transition: all 0.2s;
    cursor: default;
  }

  .tech-pill:hover { transform: translateY(-2px); }
  .tech-pill:hover.lang  { border-color: var(--coral);   color: var(--coral-light); }
  .tech-pill:hover.front { border-color: var(--blue);    color: var(--blue-light); }
  .tech-pill:hover.back  { border-color: var(--teal);    color: var(--teal-light); }
  .tech-pill:hover.db    { border-color: var(--green);   color: #97C459; }
  .tech-pill:hover.tool  { border-color: var(--purple);  color: var(--purple-light); }
  .tech-pill:hover.xplor { border-color: var(--amber);   color: #FAC775; }

  .tech-icon {
    width: 18px; height: 18px;
    border-radius: 4px;
    display: flex; align-items: center; justify-content: center;
    font-size: 11px;
    font-weight: 800;
    flex-shrink: 0;
  }

  /* Language icons as colored squares */
  .ic-c      { background: #003B70; color: #85B7EB; }
  .ic-cpp    { background: #003B70; color: #AFA9EC; }
  .ic-java   { background: #3B1F0A; color: #FAC775; }
  .ic-py     { background: #0A2E1A; color: #5DCAA5; }
  .ic-js     { background: #2E2800; color: #EF9F27; }
  .ic-html   { background: #3B1000; color: #F0997B; }
  .ic-css    { background: #0A1E3B; color: #85B7EB; }
  .ic-react  { background: #003040; color: #36BCF7; }
  .ic-node   { background: #0A2000; color: #97C459; }
  .ic-exp    { background: #151515; color: #D3D1C7; }
  .ic-mongo  { background: #0A2A00; color: #5DCAA5; }
  .ic-mysql  { background: #001A2E; color: #85B7EB; }
  .ic-git    { background: #2E0800; color: #F09595; }
  .ic-vsc    { background: #001A3B; color: #85B7EB; }
  .ic-devops { background: #1A1000; color: #FAC775; }
  .ic-ai     { background: #1A0020; color: #AFA9EC; }

  /* ── ACHIEVEMENTS ── */
  .achv-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }

  .achv-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 20px;
    display: flex;
    gap: 16px;
    transition: all 0.25s;
  }

  .achv-card:hover {
    border-color: rgba(208,90,48,0.5);
    transform: translateY(-3px);
    background: var(--bg3);
  }

  .achv-emoji {
    font-size: 36px;
    line-height: 1;
    flex-shrink: 0;
  }

  .achv-name {
    font-size: 15px;
    font-weight: 700;
    color: #fff;
    margin-bottom: 6px;
  }

  .achv-desc {
    font-size: 12px;
    color: var(--text-muted);
    line-height: 1.6;
  }

  /* ── CONNECT ── */
  .connect-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
  }

  .connect-link {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 8px;
    padding: 18px 12px;
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 14px;
    color: var(--text);
    text-decoration: none;
    font-size: 12px;
    font-weight: 700;
    font-family: 'Space Mono', monospace;
    transition: all 0.25s;
  }

  .connect-link:hover { transform: translateY(-3px); }

  .connect-link svg {
    width: 24px; height: 24px;
    transition: transform 0.2s;
  }

  .connect-link:hover svg { transform: scale(1.15); }

  .connect-link.email:hover    { border-color: var(--red);    color: #F09595; }
  .connect-link.linkedin:hover { border-color: var(--blue);   color: var(--blue-light); }
  .connect-link.github:hover   { border-color: var(--purple-light); color: var(--purple-light); }
  .connect-link.insta:hover    { border-color: var(--coral);  color: var(--coral-light); }

  /* ── FOOTER ── */
  .footer {
    padding: 24px 40px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 12px;
    border-top: 1px solid var(--border);
  }

  .footer-left {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--text-dim);
  }

  .footer-left span { color: var(--red); }

  .views-pill {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--blue-light);
    background: rgba(4,44,83,0.6);
    border: 1px solid rgba(55,138,221,0.3);
    padding: 5px 14px;
    border-radius: 999px;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  /* Entry animations */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(18px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .hero           { animation: fadeUp 0.5s ease both; }
  .section:nth-child(2) { animation: fadeUp 0.5s 0.1s ease both; }
  .section:nth-child(3) { animation: fadeUp 0.5s 0.2s ease both; }
  .section:nth-child(4) { animation: fadeUp 0.5s 0.3s ease both; }
  .section:nth-child(5) { animation: fadeUp 0.5s 0.4s ease both; }
  .section:nth-child(6) { animation: fadeUp 0.5s 0.5s ease both; }

  @media (max-width: 680px) {
    .hero { flex-direction: column; padding: 36px 20px 32px; text-align: center; }
    .role-line, .hero-badges { justify-content: center; }
    .section { padding: 28px 20px; }
    .stats-grid { grid-template-columns: 1fr; }
    .achv-grid { grid-template-columns: 1fr; }
    .connect-grid { grid-template-columns: repeat(2,1fr); }
    .footer { padding: 20px; flex-direction: column; text-align: center; }
  }
</style>
</head>
<body>

<!-- ═══════════ HERO ═══════════ -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="grid-lines"></div>

  <div class="avatar-wrap">
    <div class="avatar-spin"></div>
    <div class="avatar-inner">
      <img
        src="https://github.com/anshpandey96.png"
        alt="Ansh Pandey"
        onerror="this.style.display='none'; this.parentNode.innerHTML='AP';"
      />
    </div>
  </div>

  <div class="hero-text">
    <h1>Hi 👋, I'm <span>Ansh Pandey</span></h1>
    <div class="role-line">
      <span class="pulse-dot"></span>
      MERN Stack &amp; Java Developer
    </div>
    <div class="typing-text">Java · MERN · AI · DevOps</div>
    <div class="hero-badges">
      <span class="badge badge-blue">MERN Stack</span>
      <span class="badge badge-coral">Java &amp; DSA</span>
      <span class="badge badge-teal">AI Enthusiast</span>
      <span class="badge badge-purple">DevOps Explorer</span>
    </div>
  </div>
</section>

<!-- ═══════════ GITHUB STATS ═══════════ -->
<section class="section">
  <div class="sec-title">
    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M3 3v18h18"/><path d="m19 9-5 5-4-4-3 3"/></svg>
    GitHub Stats
  </div>

  <div class="stats-grid">

    <!-- Stats Card -->
    <div class="stats-card">
      <img
        src="https://github-readme-stats.vercel.app/api?username=anshpandey96&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0e0e1a&title_color=85B7EB&icon_color=7F77DD&text_color=e2e8f0&ring_color=378ADD&border_radius=14&count_private=true"
        alt="Ansh GitHub Stats"
        loading="lazy"
      />
      <div class="card-label"><span class="dot-label"></span>Overall stats</div>
    </div>

    <!-- Top Languages -->
    <div class="stats-card">
      <img
        src="https://github-readme-stats.vercel.app/api/top-langs/?username=anshpandey96&layout=compact&theme=tokyonight&hide_border=true&bg_color=0e0e1a&title_color=85B7EB&text_color=e2e8f0&border_radius=14&langs_count=8"
        alt="Top Languages"
        loading="lazy"
      />
      <div class="card-label"><span class="dot-label" style="background:var(--purple);"></span>Top languages</div>
    </div>

    <!-- Streak — full width -->
    <div class="stats-card full">
      <img
        src="https://streak-stats.demolab.com/?user=anshpandey96&theme=tokyonight&hide_border=true&background=0e0e1a&stroke=7F77DD&ring=378ADD&fire=E24B4A&currStreakLabel=85B7EB&sideNums=e2e8f0&sideLabels=64748b&dates=64748b&border_radius=14"
        alt="GitHub Streak"
        loading="lazy"
      />
      <div class="card-label"><span class="dot-label" style="background:var(--red);"></span>Contribution streak</div>
    </div>

  </div>
</section>

<!-- ═══════════ CONTRIBUTION GRAPH ═══════════ -->
<section class="section">
  <div class="sec-title">
    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><rect x="3" y="4" width="18" height="18" rx="2"/><path d="M16 2v4M8 2v4M3 10h18"/></svg>
    Contribution Graph
  </div>

  <div class="graph-wrap">
    <img
      src="https://github-readme-activity-graph.vercel.app/graph?username=anshpandey96&theme=tokyo-night&hide_border=true&area=true&bg_color=0e0e1a&color=85B7EB&line=7F77DD&point=378ADD&area_color=378ADD"
      alt="Contribution Activity Graph"
      loading="lazy"
    />
  </div>
</section>

<!-- ═══════════ TECH STACK ═══════════ -->
<section class="section">
  <div class="sec-title">
    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
    Tech Stack
  </div>

  <div class="tech-categories">

    <div>
      <div class="tech-category-title">// Languages</div>
      <div class="tech-row">
        <div class="tech-pill lang"><span class="tech-icon ic-c">C</span> C</div>
        <div class="tech-pill lang"><span class="tech-icon ic-cpp">C++</span> C++</div>
        <div class="tech-pill lang"><span class="tech-icon ic-java">☕</span> Java</div>
        <div class="tech-pill lang"><span class="tech-icon ic-py">🐍</span> Python</div>
        <div class="tech-pill lang"><span class="tech-icon ic-js">JS</span> JavaScript</div>
      </div>
    </div>

    <div>
      <div class="tech-category-title">// Frontend</div>
      <div class="tech-row">
        <div class="tech-pill front"><span class="tech-icon ic-html">H5</span> HTML5</div>
        <div class="tech-pill front"><span class="tech-icon ic-css">C3</span> CSS3</div>
        <div class="tech-pill front"><span class="tech-icon ic-react">⚛</span> React.js</div>
      </div>
    </div>

    <div>
      <div class="tech-category-title">// Backend</div>
      <div class="tech-row">
        <div class="tech-pill back"><span class="tech-icon ic-node">⬡</span> Node.js</div>
        <div class="tech-pill back"><span class="tech-icon ic-exp">Ex</span> Express.js</div>
      </div>
    </div>

    <div>
      <div class="tech-category-title">// Database</div>
      <div class="tech-row">
        <div class="tech-pill db"><span class="tech-icon ic-mongo">🍃</span> MongoDB</div>
        <div class="tech-pill db"><span class="tech-icon ic-mysql">🐬</span> MySQL</div>
      </div>
    </div>

    <div>
      <div class="tech-category-title">// Tools</div>
      <div class="tech-row">
        <div class="tech-pill tool"><span class="tech-icon ic-git">Git</span> Git</div>
        <div class="tech-pill tool"><span class="tech-icon ic-git">GH</span> GitHub</div>
        <div class="tech-pill tool"><span class="tech-icon ic-vsc">VS</span> VS Code</div>
      </div>
    </div>

    <div>
      <div class="tech-category-title">// Currently Exploring</div>
      <div class="tech-row">
        <div class="tech-pill xplor"><span class="tech-icon ic-devops">⚙</span> DevOps</div>
        <div class="tech-pill xplor"><span class="tech-icon ic-ai">🤖</span> AI / ML</div>
      </div>
    </div>

  </div>
</section>

<!-- ═══════════ ACHIEVEMENTS ═══════════ -->
<section class="section">
  <div class="sec-title">
    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M6 9H4.5a2.5 2.5 0 0 1 0-5H6"/><path d="M18 9h1.5a2.5 2.5 0 0 0 0-5H18"/><path d="M4 22h16"/><path d="M10 14.66V17c0 .55-.47.98-.97 1.21C7.85 18.75 7 20.24 7 22"/><path d="M14 14.66V17c0 .55.47.98.97 1.21C16.15 18.75 17 20.24 17 22"/><path d="M18 2H6v7a6 6 0 0 0 12 0V2Z"/></svg>
    GitHub Achievements
  </div>

  <div class="achv-grid">
    <div class="achv-card">
      <div class="achv-emoji">🦈</div>
      <div>
        <div class="achv-name">Pull Shark</div>
        <div class="achv-desc">Opened pull requests that were successfully merged — showcasing real collaboration &amp; contribution skills.</div>
      </div>
    </div>
    <div class="achv-card">
      <div class="achv-emoji">⚡</div>
      <div>
        <div class="achv-name">Quickdraw</div>
        <div class="achv-desc">Closed an issue or PR within 5 minutes of opening — lightning-fast problem-solving instincts!</div>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════ CONNECT ═══════════ -->
<section class="section">
  <div class="sec-title">
    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"/><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"/></svg>
    Connect with Me
  </div>

  <div class="connect-grid">

    <a class="connect-link email" href="mailto:anshpandey8543@gmail.com">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
      Email
    </a>

    <a class="connect-link linkedin" href="https://www.linkedin.com/in/ansh-pandey-b1ab34333" target="_blank" rel="noopener">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect width="4" height="12" x="2" y="9"/><circle cx="4" cy="4" r="2"/></svg>
      LinkedIn
    </a>

    <a class="connect-link github" href="https://github.com/anshpandey96" target="_blank" rel="noopener">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M15 22v-4a4.8 4.8 0 0 0-1-3.2c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.4 5.4 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"/><path d="M9 18c-4.51 2-5-2-7-2"/></svg>
      GitHub
    </a>

    <a class="connect-link insta" href="https://www.instagram.com/ansh_x_85" target="_blank" rel="noopener">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>
      @ansh_x_85
    </a>

  </div>
</section>

<!-- ═══════════ FOOTER ═══════════ -->
<footer class="footer">
  <div class="footer-left">Made with <span>♥</span> by Ansh Pandey &nbsp;·&nbsp; ⭐ Star my repos if helpful!</div>
  <div class="views-pill">
    <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"/><circle cx="12" cy="12" r="3"/></svg>
    1500+ Profile Views
  </div>
</footer>

</body>
</html>
