<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Paras Joshi — Backend Engineer</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600;700&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #0d1117;
      --bg2: #161b22;
      --bg3: #21262d;
      --border: #30363d;
      --text: #e6edf3;
      --muted: #7d8590;
      --purple: #a855f7;
      --purple-dark: #7c3aed;
      --orange: #f97316;
      --green: #16a34a;
      --blue: #2563eb;
      --red: #dc2626;
      --radius: 12px;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'DM Sans', sans-serif;
      line-height: 1.6;
      min-height: 100vh;
    }

    /* ─── HEADER ─── */
    .header {
      background: linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%);
      padding: 4rem 1.5rem 3rem;
      text-align: center;
      position: relative;
      overflow: hidden;
    }
    .header::before {
      content: '';
      position: absolute;
      inset: 0;
      background: radial-gradient(ellipse at 30% 50%, rgba(124,58,237,0.15) 0%, transparent 60%),
                  radial-gradient(ellipse at 70% 50%, rgba(249,115,22,0.08) 0%, transparent 60%);
    }
    .header-content { position: relative; z-index: 1; }
    .header h1 {
      font-family: 'Fira Code', monospace;
      font-size: clamp(2rem, 8vw, 4rem);
      font-weight: 700;
      background: linear-gradient(135deg, #fff 30%, #a855f7 70%, #f97316 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      margin-bottom: 0.5rem;
    }
    .header-sub {
      font-size: clamp(0.8rem, 2.5vw, 1rem);
      color: rgba(255,255,255,0.6);
      letter-spacing: 0.05em;
      margin-bottom: 1.5rem;
    }
    .typing-line {
      font-family: 'Fira Code', monospace;
      color: var(--purple);
      font-size: clamp(0.75rem, 2.5vw, 0.95rem);
      margin-bottom: 2rem;
      min-height: 1.4em;
    }
    .typing-line span { border-right: 2px solid var(--purple); padding-right: 2px; animation: blink 0.8s step-end infinite; }

    @keyframes blink { 50% { border-color: transparent; } }

    /* ─── BADGES ─── */
    .badges {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 0.5rem;
      margin-top: 1.5rem;
    }
    .badge {
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      padding: 0.4rem 0.9rem;
      border-radius: 6px;
      font-size: 0.78rem;
      font-weight: 600;
      text-decoration: none;
      letter-spacing: 0.02em;
      transition: opacity 0.2s, transform 0.2s;
    }
    .badge:hover { opacity: 0.85; transform: translateY(-1px); }
    .badge-portfolio { background: #1a1a2e; color: #fff; border: 1px solid #444; }
    .badge-linkedin  { background: #0a66c2; color: #fff; }
    .badge-gmail     { background: #ea4335; color: #fff; }
    .badge-views     { background: #1d1040; color: var(--purple); border: 1px solid var(--purple-dark); }

    /* ─── SECTION WRAPPER ─── */
    .container { max-width: 900px; margin: 0 auto; padding: 0 1.25rem; }
    .section { padding: 2.5rem 0; border-bottom: 1px solid var(--border); }
    .section:last-child { border-bottom: none; }
    .section-title {
      font-size: clamp(1.1rem, 3vw, 1.3rem);
      font-weight: 600;
      margin-bottom: 1.5rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }
    .section-title span { font-size: 1.2em; }

    /* ─── ABOUT ─── */
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.5rem;
      align-items: start;
    }
    @media (max-width: 620px) {
      .about-grid { grid-template-columns: 1fr; }
    }

    .code-block {
      background: var(--bg2);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 1.25rem 1.5rem;
      font-family: 'Fira Code', monospace;
      font-size: clamp(0.72rem, 1.8vw, 0.85rem);
      line-height: 1.9;
      overflow-x: auto;
    }
    .code-key   { color: #79c0ff; }
    .code-val   { color: #a5d6ff; }
    .code-str   { color: #a5d6ff; }
    .code-list  { color: var(--purple); }
    .code-comment { color: var(--muted); }
    .code-section { color: #ff7b72; }

    .about-gif {
      border-radius: var(--radius);
      overflow: hidden;
      background: var(--bg2);
      border: 1px solid var(--border);
      display: flex;
      align-items: center;
      justify-content: center;
      min-height: 180px;
      padding: 2rem;
    }
    .gif-placeholder {
      text-align: center;
      color: var(--muted);
    }
    .dev-icon { font-size: 5rem; line-height: 1; margin-bottom: 0.75rem; }
    .dev-icon-row { display: flex; gap: 0.5rem; justify-content: center; font-size: 2.2rem; }

    /* ─── IMPACT CARDS ─── */
    .impact-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(170px, 1fr));
      gap: 1rem;
    }
    .impact-card {
      background: var(--bg2);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 1.25rem 1rem;
      text-align: center;
      transition: border-color 0.2s, transform 0.2s;
    }
    .impact-card:hover { border-color: var(--purple); transform: translateY(-2px); }
    .impact-card .metric {
      font-family: 'Fira Code', monospace;
      font-size: clamp(0.7rem, 2vw, 0.82rem);
      padding: 0.3rem 0.7rem;
      border-radius: 6px;
      display: inline-block;
      margin-bottom: 0.7rem;
    }
    .metric-green  { background: rgba(22,163,74,0.15);  color: #4ade80; }
    .metric-blue   { background: rgba(37,99,235,0.15);  color: #60a5fa; }
    .metric-orange { background: rgba(234,88,12,0.15);  color: #fb923c; }
    .metric-red    { background: rgba(220,38,38,0.15);  color: #f87171; }
    .impact-label  { font-size: 0.85rem; font-weight: 600; color: var(--text); }

    /* ─── TECH STACK ─── */
    .stack-group { margin-bottom: 1.5rem; }
    .stack-group:last-child { margin-bottom: 0; }
    .stack-group-label {
      font-size: 0.8rem;
      font-weight: 600;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.08em;
      margin-bottom: 0.75rem;
    }
    .tech-pills {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
    }
    .pill {
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      padding: 0.35rem 0.85rem;
      border-radius: 99px;
      font-size: 0.8rem;
      font-weight: 500;
      background: var(--bg2);
      border: 1px solid var(--border);
      color: var(--text);
      transition: border-color 0.2s, background 0.2s;
    }
    .pill:hover { border-color: var(--purple); background: rgba(168,85,247,0.08); }
    .pill-dot {
      width: 7px; height: 7px;
      border-radius: 50%;
      flex-shrink: 0;
    }

    /* ─── FOCUS TABLE ─── */
    .focus-table {
      width: 100%;
      border-collapse: collapse;
    }
    .focus-table tr {
      border-bottom: 1px solid var(--border);
    }
    .focus-table tr:last-child { border-bottom: none; }
    .focus-table td {
      padding: 0.85rem 0.5rem;
      font-size: 0.88rem;
      vertical-align: top;
    }
    .focus-table td:first-child {
      font-weight: 600;
      white-space: nowrap;
      padding-right: 1.5rem;
      color: var(--purple);
      font-size: 0.82rem;
    }
    @media (max-width: 480px) {
      .focus-table, .focus-table tbody, .focus-table tr, .focus-table td {
        display: block;
        width: 100%;
      }
      .focus-table td:first-child { padding-bottom: 0.2rem; }
      .focus-table td { padding: 0.4rem 0; }
      .focus-table tr { padding: 0.75rem 0; }
    }

    /* ─── PROJECTS ─── */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
      gap: 1rem;
    }
    .project-card {
      background: var(--bg2);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 1.25rem;
      transition: border-color 0.2s, transform 0.2s;
    }
    .project-card:hover { border-color: var(--purple); transform: translateY(-2px); }
    .project-title {
      font-weight: 600;
      font-size: 0.95rem;
      margin-bottom: 0.4rem;
      display: flex;
      align-items: center;
      gap: 0.4rem;
    }
    .project-desc {
      font-size: 0.8rem;
      color: var(--muted);
      margin-bottom: 0.8rem;
    }
    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.35rem;
      margin-bottom: 0.75rem;
    }
    .tag {
      font-family: 'Fira Code', monospace;
      font-size: 0.7rem;
      padding: 0.15rem 0.5rem;
      border-radius: 4px;
      background: rgba(168,85,247,0.12);
      color: var(--purple);
      border: 1px solid rgba(168,85,247,0.2);
    }
    .project-features {
      font-size: 0.75rem;
      color: var(--muted);
    }

    /* ─── GITHUB STATS CARDS ─── */
    .stats-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
    }
    @media (max-width: 520px) {
      .stats-grid { grid-template-columns: 1fr; }
    }
    .stat-embed {
      border-radius: var(--radius);
      overflow: hidden;
      background: var(--bg2);
      border: 1px solid var(--border);
    }
    .stat-embed img { width: 100%; display: block; }

    .streak-embed {
      margin-top: 1rem;
      border-radius: var(--radius);
      overflow: hidden;
      background: var(--bg2);
      border: 1px solid var(--border);
    }
    .streak-embed img { width: 100%; display: block; }

    .activity-embed {
      margin-top: 1rem;
      border-radius: var(--radius);
      overflow: hidden;
      background: var(--bg2);
      border: 1px solid var(--border);
    }
    .activity-embed img { width: 100%; display: block; }

    /* ─── LEETCODE ─── */
    .leetcode-wrap {
      display: flex;
      justify-content: center;
    }
    .leetcode-wrap img {
      max-width: 100%;
      border-radius: var(--radius);
    }

    /* ─── PHILOSOPHY ─── */
    .philosophy-box {
      background: var(--bg2);
      border: 1px solid var(--border);
      border-left: 3px solid var(--purple);
      border-radius: var(--radius);
      padding: 1.5rem;
      font-family: 'Fira Code', monospace;
      font-size: clamp(0.72rem, 2vw, 0.88rem);
      text-align: center;
    }
    .philosophy-flow {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      align-items: center;
      gap: 0.3rem;
      margin-bottom: 1rem;
      font-weight: 600;
    }
    .philo-step {
      background: rgba(168,85,247,0.15);
      color: var(--purple);
      padding: 0.3rem 0.75rem;
      border-radius: 6px;
    }
    .philo-arrow { color: var(--orange); font-size: 1.1em; }
    .philosophy-quote { color: var(--muted); font-style: italic; font-size: 0.82rem; }

    /* ─── CONNECT ─── */
    .connect-grid {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 0.6rem;
    }

    /* ─── FOOTER ─── */
    footer {
      background: linear-gradient(135deg, #24243e 0%, #302b63 50%, #0f0c29 100%);
      padding: 2.5rem 1.5rem;
      text-align: center;
    }
    footer p { color: rgba(255,255,255,0.45); font-size: 0.82rem; font-style: italic; margin-top: 1rem; }

    /* ─── DIVIDER ─── */
    .divider { height: 1px; background: var(--border); margin: 0; }

    /* ─── SCROLL ANIMATION ─── */
    .fade-in { opacity: 0; transform: translateY(16px); transition: opacity 0.5s ease, transform 0.5s ease; }
    .fade-in.visible { opacity: 1; transform: none; }
  </style>
</head>
<body>

<!-- ══════════════════ HEADER ══════════════════ -->
<header class="header">
  <div class="header-content">
    <h1>Paras Joshi</h1>
    <p class="header-sub">Backend Engineer &nbsp;•&nbsp; Systems Thinker &nbsp;•&nbsp; Performance Obsessed</p>
    <div class="typing-line" id="typing"><span id="typed"></span></div>
    <div class="badges">
      <a class="badge badge-portfolio" href="https://parasjoshi.com" target="_blank">🌐 Portfolio</a>
      <a class="badge badge-linkedin"  href="https://www.linkedin.com/in/parasjoshi24" target="_blank">in LinkedIn</a>
      <a class="badge badge-gmail"     href="mailto:p.joshi2402@gmail.com">✉ Gmail</a>
      <span class="badge badge-views">👁 Profile Views</span>
    </div>
  </div>
</header>

<!-- ══════════════════ ABOUT ══════════════════ -->
<div class="container">
  <section class="section fade-in">
    <h2 class="section-title"><span>👨‍💻</span> About Me</h2>
    <div class="about-grid">
      <div class="code-block">
        <div><span class="code-key">name</span><span class="code-comment">:</span> <span class="code-str">Paras Joshi</span></div>
        <div><span class="code-key">role</span><span class="code-comment">:</span> <span class="code-str">Backend Engineer @ B2B SaaS</span></div>
        <div><span class="code-key">location</span><span class="code-comment">:</span> <span class="code-str">India 🇮🇳</span></div>
        <div><span class="code-key">portfolio</span><span class="code-comment">:</span> <span class="code-str">parasjoshi.com</span></div>
        <br/>
        <div><span class="code-section">focus</span><span class="code-comment">:</span></div>
        <div>&nbsp;&nbsp;<span class="code-comment">-</span> <span class="code-list">Production Systems &amp; REST APIs</span></div>
        <div>&nbsp;&nbsp;<span class="code-comment">-</span> <span class="code-list">Performance Engineering</span></div>
        <div>&nbsp;&nbsp;<span class="code-comment">-</span> <span class="code-list">Database Design &amp; Optimization</span></div>
        <div>&nbsp;&nbsp;<span class="code-comment">-</span> <span class="code-list">Distributed Systems</span></div>
        <br/>
        <div><span class="code-section">currently</span><span class="code-comment">:</span></div>
        <div>&nbsp;&nbsp;<span class="code-comment">-</span> <span class="code-list">Scaling backend services</span></div>
        <div>&nbsp;&nbsp;<span class="code-comment">-</span> <span class="code-list">Deep-diving System Design</span></div>
        <div>&nbsp;&nbsp;<span class="code-comment">-</span> <span class="code-list">Amazon SDE Prep</span></div>
        <br/>
        <div><span class="code-key">philosophy</span><span class="code-comment">:</span></div>
        <div class="code-comment">&nbsp;&nbsp;<span class="code-str">"Make it work → correct → fast → scalable"</span></div>
      </div>

      <div class="about-gif">
        <div class="gif-placeholder">
          <div class="dev-icon">💻</div>
          <div class="dev-icon-row">⚡🔧🚀📊🛢️</div>
          <p style="margin-top:1rem; font-size:0.8rem; color:var(--muted);">Building systems that scale</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ══════════════════ IMPACT ══════════════════ -->
  <section class="section fade-in">
    <h2 class="section-title"><span>📊</span> Engineering Impact</h2>
    <div class="impact-grid">
      <div class="impact-card">
        <div class="metric metric-green">1300ms → 40ms</div>
        <div class="impact-label">⚡ 96% Faster APIs</div>
      </div>
      <div class="impact-card">
        <div class="metric metric-blue">100K+ Users</div>
        <div class="impact-label">🌐 Real Scale</div>
      </div>
      <div class="impact-card">
        <div class="metric metric-orange">+30% DB Perf</div>
        <div class="impact-label">🗄️ Optimized</div>
      </div>
      <div class="impact-card">
        <div class="metric metric-red">Zero Data Loss</div>
        <div class="impact-label">✅ Reliable Deploys</div>
      </div>
    </div>
  </section>

  <!-- ══════════════════ TECH STACK ══════════════════ -->
  <section class="section fade-in">
    <h2 class="section-title"><span>🛠️</span> Tech Stack</h2>

    <div class="stack-group">
      <div class="stack-group-label">Languages</div>
      <div class="tech-pills">
        <span class="pill"><span class="pill-dot" style="background:#178600"></span>C#</span>
        <span class="pill"><span class="pill-dot" style="background:#f34b7d"></span>C++</span>
        <span class="pill"><span class="pill-dot" style="background:#b07219"></span>Java</span>
        <span class="pill"><span class="pill-dot" style="background:#3572A5"></span>Python</span>
        <span class="pill"><span class="pill-dot" style="background:#f1e05a"></span>JavaScript</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-label">Backend & Frameworks</div>
      <div class="tech-pills">
        <span class="pill"><span class="pill-dot" style="background:#512bd4"></span>.NET</span>
        <span class="pill"><span class="pill-dot" style="background:#68a063"></span>Node.js</span>
        <span class="pill"><span class="pill-dot" style="background:#aaa"></span>Express</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-label">Databases & Messaging</div>
      <div class="tech-pills">
        <span class="pill"><span class="pill-dot" style="background:#4479A1"></span>MySQL</span>
        <span class="pill"><span class="pill-dot" style="background:#47A248"></span>MongoDB</span>
        <span class="pill"><span class="pill-dot" style="background:#DC382D"></span>Redis</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-label">Tools & Platforms</div>
      <div class="tech-pills">
        <span class="pill"><span class="pill-dot" style="background:#f05032"></span>Git</span>
        <span class="pill"><span class="pill-dot" style="background:#FCC624"></span>Linux</span>
        <span class="pill"><span class="pill-dot" style="background:#FF6C37"></span>Postman</span>
        <span class="pill"><span class="pill-dot" style="background:#007ACC"></span>VS Code</span>
        <span class="pill"><span class="pill-dot" style="background:#5C2D91"></span>Visual Studio</span>
        <span class="pill"><span class="pill-dot" style="background:#181717"></span>GitHub</span>
      </div>
    </div>
  </section>

  <!-- ══════════════════ CURRENTLY WORKING ON ══════════════════ -->
  <section class="section fade-in">
    <h2 class="section-title"><span>🎯</span> Currently Working On</h2>
    <table class="focus-table">
      <tbody>
        <tr>
          <td>🏗️ System Design</td>
          <td>Distributed systems, CAP theorem, consensus algorithms</td>
        </tr>
        <tr>
          <td>⚡ Performance</td>
          <td>Low-latency APIs, caching strategies, async processing</td>
        </tr>
        <tr>
          <td>📦 Backend</td>
          <td>Microservices, message queues, event-driven architecture</td>
        </tr>
        <tr>
          <td>🧠 DSA</td>
          <td>Daily LeetCode grind — graphs, DP, trees</td>
        </tr>
        <tr>
          <td>🎯 Interview Prep</td>
          <td>Amazon SDE — LP principles + technical depth</td>
        </tr>
      </tbody>
    </table>
  </section>

  <!-- ══════════════════ PROJECTS ══════════════════ -->
  <section class="section fade-in">
    <h2 class="section-title"><span>🔥</span> Featured Projects</h2>
    <div class="projects-grid">

      <div class="project-card">
        <div class="project-title">🧾 BillStack</div>
        <div class="project-desc">Billing &amp; inventory platform</div>
        <div class="project-tags">
          <span class="tag">React</span>
          <span class="tag">Node.js</span>
          <span class="tag">MongoDB</span>
        </div>
        <div class="project-features">Auth · Billing Engine · Analytics</div>
      </div>

      <div class="project-card">
        <div class="project-title">💸 Expense Tracker</div>
        <div class="project-desc">Production finance tracker</div>
        <div class="project-tags">
          <span class="tag">.NET</span>
          <span class="tag">MySQL</span>
        </div>
        <div class="project-features">Expense Analytics · REST APIs</div>
      </div>

      <div class="project-card">
        <div class="project-title">🔗 URL Shortener</div>
        <div class="project-desc">Low-latency shortening service</div>
        <div class="project-tags">
          <span class="tag">Node.js</span>
          <span class="tag">Redis</span>
        </div>
        <div class="project-features">Custom Aliases · Analytics · Cache</div>
      </div>

    </div>
  </section>

  <!-- ══════════════════ GITHUB STATS ══════════════════ -->
  <section class="section fade-in">
    <h2 class="section-title"><span>📊</span> GitHub Stats</h2>

    <div class="stats-grid">
      <div class="stat-embed">
        <img
          src="https://github-readme-stats.anuraghazra1.vercel.app/api?username=paarasjoshi&show_icons=true&hide_border=true&count_private=true&bg_color=161b22&title_color=a855f7&icon_color=a855f7&text_color=c9d1d9"
          alt="GitHub stats"
          loading="lazy"
        />
      </div>
      <div class="stat-embed">
        <img
          src="https://github-readme-stats.anuraghazra1.vercel.app/api/top-langs/?username=paarasjoshi&layout=compact&hide_border=true&bg_color=161b22&title_color=a855f7&text_color=c9d1d9&langs_count=8"
          alt="Top languages"
          loading="lazy"
        />
      </div>
    </div>

    <div class="streak-embed">
      <img
        src="https://streak-stats.demolab.com?user=paarasjoshi&theme=tokyonight-duo&hide_border=true&background=161B22&stroke=a855f7&ring=a855f7&fire=f97316&currStreakNum=ffffff&sideNums=ffffff&currStreakLabel=a855f7&sideLabels=a855f7&dates=888888"
        alt="GitHub streak"
        loading="lazy"
        style="width:100%; display:block;"
      />
    </div>

    <div class="activity-embed">
      <img
        src="https://github-readme-activity-graph.vercel.app/graph?username=paarasjoshi&bg_color=161b22&color=a855f7&line=7c3aed&point=f97316&area=true&hide_border=true"
        alt="Activity graph"
        loading="lazy"
        style="width:100%; display:block;"
      />
    </div>
  </section>

  <!-- ══════════════════ LEETCODE ══════════════════ -->
  <section class="section fade-in">
    <h2 class="section-title"><span>💻</span> LeetCode</h2>
    <div class="leetcode-wrap">
      <img
        src="https://leetcard.jacoblin.cool/parasjoshi24?theme=dark&font=Baloo_2&ext=heatmap&border=0&radius=16"
        alt="LeetCode stats"
        loading="lazy"
        style="max-width:500px; width:100%;"
      />
    </div>
  </section>

  <!-- ══════════════════ PHILOSOPHY ══════════════════ -->
  <section class="section fade-in">
    <h2 class="section-title"><span>💡</span> Philosophy</h2>
    <div class="philosophy-box">
      <div class="philosophy-flow">
        <span class="philo-step">Make it work</span>
        <span class="philo-arrow">→</span>
        <span class="philo-step">Make it correct</span>
        <span class="philo-arrow">→</span>
        <span class="philo-step">Make it fast</span>
        <span class="philo-arrow">→</span>
        <span class="philo-step">Make it scale</span>
      </div>
      <div class="philosophy-quote">"I like working on problems where performance actually matters."</div>
    </div>
  </section>

  <!-- ══════════════════ CONNECT ══════════════════ -->
  <section class="section fade-in">
    <h2 class="section-title"><span>🤝</span> Connect</h2>
    <div class="connect-grid">
      <a class="badge badge-gmail"     href="mailto:p.joshi2402@gmail.com">✉ Gmail</a>
      <a class="badge badge-linkedin"  href="https://www.linkedin.com/in/parasjoshi24" target="_blank">in LinkedIn</a>
      <a class="badge badge-portfolio" href="https://parasjoshi.com" target="_blank">🌐 Portfolio</a>
      <a class="badge" style="background:#181717;color:#fff;border:1px solid #444;" href="https://github.com/paarasjoshi" target="_blank">🐙 GitHub</a>
      <a class="badge" style="background:#FFA116;color:#000;font-weight:700;" href="https://leetcode.com/parasjoshi24" target="_blank">⚡ LeetCode</a>
      <a class="badge" style="background:#00EA64;color:#000;font-weight:700;" href="https://www.hackerrank.com/p_joshi2402" target="_blank">HR HackerRank</a>
      <a class="badge" style="background:#2F8D46;color:#fff;" href="https://www.geeksforgeeks.org/profile/parasjoshi2402" target="_blank">GFG GeeksForGeeks</a>
    </div>
  </section>
</div><!-- /container -->

<!-- ══════════════════ FOOTER ══════════════════ -->
<footer>
  <div style="font-family:'Fira Code',monospace; font-size:0.75rem; color:rgba(255,255,255,0.25); letter-spacing:0.05em;">paarasjoshi</div>
  <p>"I have not come this far only to come this far."</p>
</footer>

<script>
  /* ── Typing animation ── */
  const lines = [
    "Building systems that don't break 🔥",
    "1300ms → 40ms API latency reduction ⚡",
    "100K+ users served in production 🚀",
    "Scaling backends that actually scale 📈"
  ];
  let li = 0, ci = 0, deleting = false;
  const el = document.getElementById('typed');
  function type() {
    const cur = lines[li];
    if (!deleting) {
      el.textContent = cur.slice(0, ci++);
      if (ci > cur.length) { deleting = true; setTimeout(type, 1800); return; }
    } else {
      el.textContent = cur.slice(0, ci--);
      if (ci < 0) { deleting = false; li = (li + 1) % lines.length; ci = 0; }
    }
    setTimeout(type, deleting ? 30 : 55);
  }
  type();

  /* ── Scroll fade-in ── */
  const obs = new IntersectionObserver(entries => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); obs.unobserve(e.target); } });
  }, { threshold: 0.1 });
  document.querySelectorAll('.fade-in').forEach(el => obs.observe(el));
</script>
</body>
</html>
