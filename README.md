<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Mariem Zoughlami — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@300;400;500&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #080b14;
    --bg2: #0d1120;
    --bg3: #111827;
    --card: #131929;
    --border: rgba(99,102,241,0.15);
    --accent1: #6366f1;
    --accent2: #f472b6;
    --accent3: #34d399;
    --text: #e2e8f0;
    --muted: #64748b;
    --glow1: rgba(99,102,241,0.3);
    --glow2: rgba(244,114,182,0.2);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Outfit', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background:
      radial-gradient(ellipse 60% 40% at 20% 10%, rgba(99,102,241,0.12) 0%, transparent 60%),
      radial-gradient(ellipse 50% 35% at 80% 80%, rgba(244,114,182,0.1) 0%, transparent 60%),
      radial-gradient(ellipse 40% 30% at 60% 40%, rgba(52,211,153,0.05) 0%, transparent 50%);
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 60px 24px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    text-align: center;
    margin-bottom: 56px;
    animation: fadeUp 0.8s ease both;
  }

  .avatar-ring {
    display: inline-block;
    position: relative;
    margin-bottom: 28px;
  }

  .avatar-ring::before {
    content: '';
    position: absolute;
    inset: -3px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent1), var(--accent2), var(--accent3));
    animation: spin 4s linear infinite;
    z-index: -1;
  }

  .avatar {
    width: 110px;
    height: 110px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent1), var(--accent2));
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Syne', sans-serif;
    font-size: 42px;
    font-weight: 800;
    color: white;
    border: 3px solid var(--bg);
  }

  .status-dot {
    position: absolute;
    bottom: 6px;
    right: 6px;
    width: 18px;
    height: 18px;
    background: var(--accent3);
    border-radius: 50%;
    border: 3px solid var(--bg);
    animation: pulse 2s ease infinite;
  }

  .name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(36px, 6vw, 56px);
    font-weight: 800;
    background: linear-gradient(135deg, #fff 0%, var(--accent1) 50%, var(--accent2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    line-height: 1.1;
    margin-bottom: 10px;
  }

  .tagline {
    font-family: 'DM Mono', monospace;
    font-size: 14px;
    color: var(--accent1);
    letter-spacing: 0.08em;
    margin-bottom: 20px;
    opacity: 0.9;
  }

  .tagline span { color: var(--accent2); }

  .desc {
    font-size: 15px;
    color: var(--muted);
    max-width: 480px;
    margin: 0 auto 28px;
    line-height: 1.7;
  }

  .socials {
    display: flex;
    gap: 10px;
    justify-content: center;
    flex-wrap: wrap;
  }

  .social-btn {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    padding: 8px 18px;
    border-radius: 100px;
    font-size: 13px;
    font-weight: 500;
    text-decoration: none;
    border: 1px solid var(--border);
    background: rgba(99,102,241,0.07);
    color: var(--text);
    transition: all 0.25s ease;
    cursor: pointer;
  }

  .social-btn:hover {
    background: rgba(99,102,241,0.2);
    border-color: var(--accent1);
    transform: translateY(-2px);
    box-shadow: 0 8px 24px var(--glow1);
  }

  /* ── CODE BLOCK ── */
  .code-section {
    margin-bottom: 40px;
    animation: fadeUp 0.8s 0.1s ease both;
  }

  .section-label {
    font-family: 'Syne', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent1);
    margin-bottom: 14px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .code-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    overflow: hidden;
    box-shadow: 0 20px 60px rgba(0,0,0,0.4);
  }

  .code-header {
    background: rgba(255,255,255,0.03);
    border-bottom: 1px solid var(--border);
    padding: 12px 18px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot.r { background: #ff5f57; }
  .dot.y { background: #febc2e; }
  .dot.g { background: #28c840; }

  .code-file {
    margin-left: auto;
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    color: var(--muted);
  }

  .code-body {
    padding: 24px 28px;
    font-family: 'DM Mono', monospace;
    font-size: 13.5px;
    line-height: 2;
  }

  .kw { color: #c792ea; }
  .fn { color: #82aaff; }
  .str { color: #c3e88d; }
  .num { color: #f78c6c; }
  .key { color: #89ddff; }
  .cm { color: #546e7a; font-style: italic; }
  .br { color: #89ddff; }

  /* ── SKILLS GRID ── */
  .skills-section {
    margin-bottom: 40px;
    animation: fadeUp 0.8s 0.2s ease both;
  }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 14px;
  }

  .skill-group {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 20px;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
  }

  .skill-group::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent1), var(--accent2));
    opacity: 0;
    transition: opacity 0.3s;
  }

  .skill-group:hover { transform: translateY(-4px); box-shadow: 0 16px 40px rgba(0,0,0,0.3); }
  .skill-group:hover::before { opacity: 1; }

  .skill-group-title {
    font-family: 'Syne', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 14px;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .tag {
    font-size: 11.5px;
    padding: 4px 10px;
    border-radius: 6px;
    font-family: 'DM Mono', monospace;
    font-weight: 500;
  }

  .tag.purple { background: rgba(99,102,241,0.15); color: #a5b4fc; border: 1px solid rgba(99,102,241,0.25); }
  .tag.pink   { background: rgba(244,114,182,0.12); color: #f9a8d4; border: 1px solid rgba(244,114,182,0.2); }
  .tag.green  { background: rgba(52,211,153,0.1);  color: #6ee7b7; border: 1px solid rgba(52,211,153,0.2); }
  .tag.blue   { background: rgba(56,189,248,0.1);  color: #7dd3fc; border: 1px solid rgba(56,189,248,0.2); }
  .tag.orange { background: rgba(251,146,60,0.1);  color: #fdba74; border: 1px solid rgba(251,146,60,0.2); }

  /* ── EXPERIENCE ── */
  .exp-section {
    margin-bottom: 40px;
    animation: fadeUp 0.8s 0.3s ease both;
  }

  .exp-item {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 0 20px;
    margin-bottom: 8px;
  }

  .exp-line {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .exp-dot {
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent1), var(--accent2));
    flex-shrink: 0;
    margin-top: 6px;
    box-shadow: 0 0 12px var(--glow1);
  }

  .exp-connector {
    width: 1px;
    flex: 1;
    background: var(--border);
    margin: 4px 0;
  }

  .exp-content {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 18px 20px;
    margin-bottom: 8px;
    transition: all 0.3s ease;
  }

  .exp-content:hover {
    border-color: rgba(99,102,241,0.4);
    box-shadow: 0 8px 30px rgba(0,0,0,0.2);
  }

  .exp-top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 6px;
    flex-wrap: wrap;
    gap: 8px;
  }

  .exp-company {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 15px;
    color: white;
  }

  .exp-date {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--accent1);
    background: rgba(99,102,241,0.1);
    padding: 3px 10px;
    border-radius: 100px;
    border: 1px solid rgba(99,102,241,0.2);
  }

  .exp-role {
    font-size: 13px;
    color: var(--muted);
    margin-bottom: 10px;
  }

  .exp-tags { display: flex; flex-wrap: wrap; gap: 5px; }

  /* ── STATS ── */
  .stats-section {
    margin-bottom: 40px;
    animation: fadeUp 0.8s 0.4s ease both;
  }

  .stats-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 14px;
  }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px 16px;
    text-align: center;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
  }

  .stat-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 40px;
    background: linear-gradient(0deg, rgba(99,102,241,0.06), transparent);
  }

  .stat-card:hover { transform: translateY(-4px); box-shadow: 0 16px 40px rgba(0,0,0,0.3); }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 32px;
    font-weight: 800;
    background: linear-gradient(135deg, var(--accent1), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    display: block;
    margin-bottom: 6px;
  }

  .stat-label {
    font-size: 12px;
    color: var(--muted);
    font-weight: 500;
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding: 40px 0 20px;
    animation: fadeUp 0.8s 0.5s ease both;
  }

  .footer-quote {
    font-family: 'Syne', sans-serif;
    font-size: 15px;
    color: var(--muted);
    margin-bottom: 20px;
    font-style: italic;
  }

  .footer-quote span {
    background: linear-gradient(135deg, var(--accent1), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-style: normal;
    font-weight: 700;
  }

  .footer-wave {
    font-size: 13px;
    color: var(--muted);
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes spin {
    to { transform: rotate(360deg); }
  }

  @keyframes pulse {
    0%, 100% { box-shadow: 0 0 0 0 rgba(52,211,153,0.4); }
    50%       { box-shadow: 0 0 0 6px rgba(52,211,153,0); }
  }

  @media (max-width: 600px) {
    .skills-grid { grid-template-columns: 1fr; }
    .stats-grid  { grid-template-columns: repeat(2, 1fr); }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <header class="header">
    <div class="avatar-ring">
      <div class="avatar">MZ</div>
      <div class="status-dot"></div>
    </div>
    <h1 class="name">Mariem Zoughlami</h1>
    <p class="tagline">💼 Développeuse Web <span>@Medianet</span> · Front-End Soul ✨</p>
    <p class="desc">Transformer des idées complexes en interfaces élégantes et des architectures solides en expériences utilisateur mémorables.</p>
    <div class="socials">
      <a class="social-btn" href="/cdn-cgi/l/email-protection#771a16050e121a0d1802101f1b161a1e37101a161e1b5914181a">📧 Gmail</a>
      <a class="social-btn" href="https://linkedin.com/in/mariem-zoughlami">💼 LinkedIn</a>
      <a class="social-btn" href="https://github.com/MARYEM593">🐙 GitHub</a>
      <a class="social-btn" href="https://maryem593.github.io/MariemZoughlami.github.io/">🌐 Portfolio</a>
    </div>
  </header>

  <!-- CODE BLOCK -->
  <section class="code-section">
    <div class="section-label">$ whoami</div>
    <div class="code-card">
      <div class="code-header">
        <div class="dot r"></div><div class="dot y"></div><div class="dot g"></div>
        <span class="code-file">mariem.ts</span>
      </div>
      <div class="code-body">
        <span class="kw">const</span> <span class="fn">mariem</span><span class="br">:</span> <span class="fn">Developer</span> <span class="br">= {</span><br/>
        &nbsp;&nbsp;<span class="key">role</span><span class="br">:</span> <span class="str">"Développeuse Web @ Medianet 💼"</span><span class="br">,</span><br/>
        &nbsp;&nbsp;<span class="key">location</span><span class="br">:</span> <span class="str">"Tunis, Tunisie 🇹🇳"</span><span class="br">,</span><br/>
        &nbsp;&nbsp;<span class="key">experience</span><span class="br">:</span> <span class="str">"+3 ans d'expérience"</span><span class="br">,</span><br/>
        &nbsp;&nbsp;<span class="key">stack</span><span class="br">:</span> <span class="br">[</span><span class="str">"React.js"</span><span class="br">,</span> <span class="str">"Next.js"</span><span class="br">,</span> <span class="str">"Drupal"</span><span class="br">,</span> <span class="str">"WordPress"</span><span class="br">],</span><br/>
        &nbsp;&nbsp;<span class="key">passions</span><span class="br">:</span> <span class="br">[</span><span class="str">"UI/UX"</span><span class="br">,</span> <span class="str">"Clean Code"</span><span class="br">,</span> <span class="str">"Architecture"</span><span class="br">],</span><br/>
        &nbsp;&nbsp;<span class="key">available</span><span class="br">:</span> <span class="num">true</span><span class="br">,</span> <span class="cm">// Open to new opportunities ✨</span><br/>
        <span class="br">};</span>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section class="skills-section">
    <div class="section-label">🚀 Stack Technique</div>
    <div class="skills-grid">
      <div class="skill-group">
        <div class="skill-group-title">🎨 Front-End</div>
        <div class="tags">
          <span class="tag purple">React.js</span>
          <span class="tag purple">Next.js</span>
          <span class="tag blue">Tailwind CSS</span>
          <span class="tag blue">Bootstrap</span>
          <span class="tag pink">SASS</span>
          <span class="tag orange">JavaScript</span>
          <span class="tag orange">HTML5 / CSS3</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">🔵 CMS & Back-End</div>
        <div class="tags">
          <span class="tag blue">Drupal</span>
          <span class="tag blue">Twig</span>
          <span class="tag green">WordPress</span>
          <span class="tag purple">PHP / Laravel</span>
          <span class="tag green">Node.js</span>
          <span class="tag orange">API REST</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">🛠️ Outils</div>
        <div class="tags">
          <span class="tag orange">Git / GitHub</span>
          <span class="tag pink">Agile / Scrum</span>
          <span class="tag green">cPanel</span>
          <span class="tag purple">Postman</span>
          <span class="tag blue">SEO</span>
          <span class="tag green">OVH / Hostinger</span>
        </div>
      </div>
    </div>
  </section>

  <!-- EXPERIENCE -->
  <section class="exp-section">
    <div class="section-label">💼 Expérience</div>

    <div class="exp-item">
      <div class="exp-line"><div class="exp-dot"></div><div class="exp-connector"></div></div>
      <div class="exp-content">
        <div class="exp-top">
          <span class="exp-company">🏢 Medianet</span>
          <span class="exp-date">07/2024 → Présent</span>
        </div>
        <div class="exp-role">Développeuse Web — React.js · Next.js · Drupal Full-Cycle</div>
        <div class="exp-tags">
          <span class="tag purple">React.js</span><span class="tag purple">Next.js</span>
          <span class="tag blue">Drupal</span><span class="tag pink">Tailwind</span>
          <span class="tag orange">API REST</span><span class="tag green">Agile</span>
        </div>
      </div>
    </div>

    <div class="exp-item">
      <div class="exp-line"><div class="exp-dot"></div><div class="exp-connector"></div></div>
      <div class="exp-content">
        <div class="exp-top">
          <span class="exp-company">💻 From Com</span>
          <span class="exp-date">04/2024 → 06/2024</span>
        </div>
        <div class="exp-role">Développeuse Web Freelance — HTML · CSS · JS · WordPress · cPanel</div>
        <div class="exp-tags">
          <span class="tag orange">HTML/CSS/JS</span><span class="tag green">WordPress</span>
          <span class="tag blue">cPanel</span>
        </div>
      </div>
    </div>

    <div class="exp-item">
      <div class="exp-line"><div class="exp-dot"></div></div>
      <div class="exp-content">
        <div class="exp-top">
          <span class="exp-company">🌐 Zeta Engineering</span>
          <span class="exp-date">02/2023 → 03/2024</span>
        </div>
        <div class="exp-role">Développeuse Web — React.js · Next.js · WordPress · SEO</div>
        <div class="exp-tags">
          <span class="tag purple">React.js</span><span class="tag purple">Next.js</span>
          <span class="tag green">WordPress</span><span class="tag blue">Bootstrap</span>
          <span class="tag orange">SEO</span><span class="tag pink">Git</span>
        </div>
      </div>
    </div>
  </section>

  <!-- STATS -->
  <section class="stats-section">
    <div class="section-label">📊 En chiffres</div>
    <div class="stats-grid">
      <div class="stat-card">
        <span class="stat-num">3+</span>
        <span class="stat-label">Ans d'expérience</span>
      </div>
      <div class="stat-card">
        <span class="stat-num">15+</span>
        <span class="stat-label">Projets livrés</span>
      </div>
      <div class="stat-card">
        <span class="stat-num">10+</span>
        <span class="stat-label">Technologies</span>
      </div>
      <div class="stat-card">
        <span class="stat-num">∞</span>
        <span class="stat-label">Curiosité</span>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer">
    <p class="footer-quote">✦ Si vous êtes arrivé jusqu'ici, c'est peut-être que <span>mon profil mérite qu'on en discute !</span></p>
    <p class="footer-wave">📍 Tunis, Tunisie · 📧 <a href="/cdn-cgi/
