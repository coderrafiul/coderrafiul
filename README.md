<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Rafiul Razib – Full-Stack MERN Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@300;400;500&family=Instrument+Serif:ital@0;1&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --surface2: #16161f;
    --border: #1e1e2e;
    --accent: #00e5ff;
    --accent2: #7c3aed;
    --accent3: #f59e0b;
    --text: #e8e8f0;
    --muted: #6b6b8a;
    --green: #10b981;
    --radius: 12px;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Mono', monospace;
    line-height: 1.6;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Grid noise background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,255,0.03) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
    z-index: 0;
  }

  .wrapper {
    position: relative;
    z-index: 1;
    max-width: 860px;
    margin: 0 auto;
    padding: 48px 24px 80px;
  }

  /* ── HERO ── */
  .hero {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 32px;
    align-items: start;
    margin-bottom: 56px;
    padding-bottom: 48px;
    border-bottom: 1px solid var(--border);
  }

  .hero-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.18em;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .hero-eyebrow::before {
    content: '';
    display: inline-block;
    width: 24px;
    height: 1px;
    background: var(--accent);
  }

  h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.2rem, 5vw, 3.4rem);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.02em;
    color: var(--text);
    margin-bottom: 16px;
  }

  h1 span {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    color: var(--accent);
  }

  .hero-tagline {
    font-size: 13px;
    color: var(--muted);
    max-width: 520px;
    line-height: 1.8;
    margin-bottom: 24px;
  }

  .hero-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .badge {
    font-size: 10px;
    font-weight: 500;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 4px 10px;
    border-radius: 4px;
    border: 1px solid;
  }

  .badge-cyan  { color: var(--accent);  border-color: rgba(0,229,255,0.3);  background: rgba(0,229,255,0.06); }
  .badge-purple{ color: #a78bfa;        border-color: rgba(124,58,237,0.4); background: rgba(124,58,237,0.08);}
  .badge-amber { color: var(--accent3); border-color: rgba(245,158,11,0.3); background: rgba(245,158,11,0.06);}
  .badge-green { color: var(--green);   border-color: rgba(16,185,129,0.3); background: rgba(16,185,129,0.06);}

  /* avatar circle */
  .avatar {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent2) 0%, var(--accent) 100%);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Syne', sans-serif;
    font-size: 2rem;
    font-weight: 800;
    color: #fff;
    flex-shrink: 0;
    position: relative;
  }

  .avatar::after {
    content: '';
    position: absolute;
    inset: -4px;
    border-radius: 50%;
    background: conic-gradient(var(--accent), var(--accent2), var(--accent));
    z-index: -1;
    animation: spin 6s linear infinite;
  }

  @keyframes spin { to { transform: rotate(360deg); } }

  /* ── SECTION HEADER ── */
  .section-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 24px;
  }

  .section-icon {
    width: 32px;
    height: 32px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 15px;
    flex-shrink: 0;
  }

  .icon-cyan   { background: rgba(0,229,255,0.12);  }
  .icon-purple { background: rgba(124,58,237,0.15); }
  .icon-amber  { background: rgba(245,158,11,0.12); }
  .icon-green  { background: rgba(16,185,129,0.12); }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 1rem;
    font-weight: 700;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: var(--text);
  }

  section { margin-bottom: 52px; }

  /* ── TECH STACK ── */
  .stack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    overflow: hidden;
  }

  .stack-category {
    background: var(--surface);
    padding: 18px;
  }

  .stack-category:first-child {
    grid-column: 1 / -1;
    background: var(--surface2);
    padding: 14px 18px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .stack-category-label {
    font-size: 10px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--muted);
    font-weight: 500;
    margin-bottom: 10px;
  }

  .stack-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .pill {
    font-size: 11px;
    color: var(--text);
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 3px 8px;
    transition: border-color 0.2s, color 0.2s;
    white-space: nowrap;
  }

  /* Big tech row */
  .stack-full {
    border: 1px solid var(--border);
    border-radius: var(--radius);
    overflow: hidden;
  }

  .stack-row {
    display: grid;
    grid-template-columns: 120px 1fr;
    border-bottom: 1px solid var(--border);
  }

  .stack-row:last-child { border-bottom: none; }

  .stack-row-label {
    background: var(--surface2);
    padding: 16px 18px;
    font-size: 10px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
    display: flex;
    align-items: center;
    border-right: 1px solid var(--border);
  }

  .stack-row-pills {
    background: var(--surface);
    padding: 14px 18px;
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    align-items: center;
  }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(360px, 1fr));
    gap: 16px;
  }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.25s, transform 0.25s;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
  }

  .project-card.c1::before { background: linear-gradient(90deg, var(--accent), var(--accent2)); }
  .project-card.c2::before { background: linear-gradient(90deg, var(--accent2), #f43f5e); }
  .project-card.c3::before { background: linear-gradient(90deg, var(--accent3), var(--green)); }
  .project-card.c4::before { background: linear-gradient(90deg, var(--green), var(--accent)); }

  .project-emoji {
    font-size: 24px;
    margin-bottom: 12px;
    display: block;
  }

  .project-name {
    font-family: 'Syne', sans-serif;
    font-size: 1rem;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 8px;
  }

  .project-desc {
    font-size: 12px;
    color: var(--muted);
    line-height: 1.7;
    margin-bottom: 16px;
  }

  .project-tech {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
  }

  .tech-tag {
    font-size: 10px;
    color: var(--accent);
    background: rgba(0,229,255,0.08);
    border: 1px solid rgba(0,229,255,0.2);
    border-radius: 3px;
    padding: 2px 7px;
  }

  /* ── FOCUS ── */
  .focus-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 10px;
  }

  .focus-item {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 14px 16px;
    font-size: 12px;
    color: var(--muted);
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .focus-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--accent);
    flex-shrink: 0;
    box-shadow: 0 0 6px var(--accent);
  }

  /* ── CONNECT ── */
  .connect-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 12px;
  }

  .connect-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 18px 20px;
    text-decoration: none;
    color: var(--text);
    display: flex;
    align-items: center;
    gap: 14px;
    transition: border-color 0.2s, background 0.2s;
  }

  .connect-card:hover {
    border-color: var(--accent);
    background: rgba(0,229,255,0.04);
  }

  .connect-icon {
    width: 38px;
    height: 38px;
    border-radius: 8px;
    background: var(--surface2);
    border: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
    flex-shrink: 0;
  }

  .connect-label {
    font-size: 10px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 3px;
  }

  .connect-value {
    font-size: 12px;
    color: var(--text);
    font-weight: 500;
  }

  /* ── FOOTER ── */
  .footer {
    margin-top: 60px;
    padding-top: 32px;
    border-top: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 16px;
    flex-wrap: wrap;
  }

  .footer-note {
    font-size: 11px;
    color: var(--muted);
    line-height: 1.8;
    max-width: 480px;
  }

  .footer-note strong {
    color: var(--accent);
    font-style: normal;
  }

  .stat-row {
    display: flex;
    gap: 24px;
  }

  .stat {
    text-align: center;
  }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 1.4rem;
    font-weight: 800;
    color: var(--text);
    display: block;
  }

  .stat-label {
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  /* ── ABOUT ── */
  .about-box {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 24px 28px;
    font-size: 13px;
    color: var(--muted);
    line-height: 1.9;
    border-left: 3px solid var(--accent);
  }

  .about-box em {
    color: var(--text);
    font-style: normal;
    font-weight: 500;
  }

  /* responsive */
  @media (max-width: 600px) {
    .hero { grid-template-columns: 1fr; }
    .avatar { display: none; }
    .stack-row { grid-template-columns: 1fr; }
    .stack-row-label { border-right: none; border-bottom: 1px solid var(--border); }
    .projects-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>
<div class="wrapper">

  <!-- HERO -->
  <header class="hero">
    <div>
      <p class="hero-eyebrow">Open to work &amp; collaboration</p>
      <h1>Rafiul <span>Razib</span></h1>
      <p class="hero-tagline">
        Full-Stack MERN Developer from Bangladesh — engineering background,
        13 years of manufacturing leadership, now building production-ready
        web apps, AI-powered solutions, and modern digital products.
      </p>
      <div class="hero-badges">
        <span class="badge badge-cyan">React.js</span>
        <span class="badge badge-cyan">Next.js</span>
        <span class="badge badge-purple">TypeScript</span>
        <span class="badge badge-purple">Node.js</span>
        <span class="badge badge-green">MongoDB</span>
        <span class="badge badge-amber">AI Apps</span>
      </div>
    </div>
    <div class="avatar" aria-hidden="true">RR</div>
  </header>

  <!-- ABOUT -->
  <section>
    <div class="section-header">
      <div class="section-icon icon-cyan">👤</div>
      <span class="section-title">About</span>
    </div>
    <div class="about-box">
      I enjoy solving <em>real-world problems</em> through technology and continuously exploring
      new tools, frameworks, and AI technologies. My journey from <em>manufacturing leadership</em>
      to software development gives me a unique perspective on building systems that actually work
      at scale — blending engineering discipline with modern development practices.
    </div>
  </section>

  <!-- TECH STACK -->
  <section>
    <div class="section-header">
      <div class="section-icon icon-purple">🚀</div>
      <span class="section-title">Tech Stack</span>
    </div>
    <div class="stack-full">
      <div class="stack-row">
        <div class="stack-row-label">Frontend</div>
        <div class="stack-row-pills">
          <span class="pill">React.js</span>
          <span class="pill">Next.js</span>
          <span class="pill">TypeScript</span>
          <span class="pill">JavaScript ES6+</span>
          <span class="pill">HTML5</span>
          <span class="pill">CSS3</span>
          <span class="pill">Tailwind CSS</span>
          <span class="pill">Bootstrap</span>
          <span class="pill">DaisyUI</span>
          <span class="pill">Shadcn UI</span>
        </div>
      </div>
      <div class="stack-row">
        <div class="stack-row-label">Backend</div>
        <div class="stack-row-pills">
          <span class="pill">Node.js</span>
          <span class="pill">Express.js</span>
          <span class="pill">REST APIs</span>
          <span class="pill">JWT Auth</span>
          <span class="pill">NextAuth.js</span>
        </div>
      </div>
      <div class="stack-row">
        <div class="stack-row-label">Databases</div>
        <div class="stack-row-pills">
          <span class="pill">MongoDB</span>
          <span class="pill">PostgreSQL</span>
        </div>
      </div>
      <div class="stack-row">
        <div class="stack-row-label">AI &amp; Automation</div>
        <div class="stack-row-pills">
          <span class="pill">Gemini API</span>
          <span class="pill">OpenAI API</span>
          <span class="pill">AI Chatbot Dev</span>
          <span class="pill">Document Processing</span>
          <span class="pill">OCR Integration</span>
          <span class="pill">LLM Integration</span>
        </div>
      </div>
      <div class="stack-row">
        <div class="stack-row-label">Tools</div>
        <div class="stack-row-pills">
          <span class="pill">Git</span>
          <span class="pill">GitHub</span>
          <span class="pill">Postman</span>
          <span class="pill">Firebase</span>
          <span class="pill">Vercel</span>
          <span class="pill">Railway</span>
          <span class="pill">Render</span>
          <span class="pill">Stripe</span>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section>
    <div class="section-header">
      <div class="section-icon icon-amber">🌟</div>
      <span class="section-title">Featured Projects</span>
    </div>
    <div class="projects-grid">

      <div class="project-card c1">
        <span class="project-emoji">📄</span>
        <div class="project-name">AI Document Processor</div>
        <div class="project-desc">
          AI-powered document classification and data extraction system
          built with Flask, OCR, and Gemini AI.
        </div>
        <div class="project-tech">
          <span class="tech-tag">Python</span>
          <span class="tech-tag">Flask</span>
          <span class="tech-tag">Gemini AI</span>
          <span class="tech-tag">OCR</span>
          <span class="tech-tag">PyMuPDF</span>
        </div>
      </div>

      <div class="project-card c2">
        <span class="project-emoji">🛒</span>
        <div class="project-name">AN Mobiles</div>
        <div class="project-desc">
          Modern e-commerce platform for phones, laptops, tablets &amp; accessories
          with auth, payment integration, and product management.
        </div>
        <div class="project-tech">
          <span class="tech-tag">Next.js</span>
          <span class="tech-tag">Express.js</span>
          <span class="tech-tag">MongoDB</span>
          <span class="tech-tag">Stripe</span>
        </div>
      </div>

      <div class="project-card c3">
        <span class="project-emoji">🧠</span>
        <div class="project-name">Quizlytics</div>
        <div class="project-desc">
          AI-powered quiz generation platform that creates quizzes based on
          topics, articles, and custom exam configurations.
        </div>
        <div class="project-tech">
          <span class="tech-tag">React.js</span>
          <span class="tech-tag">Node.js</span>
          <span class="tech-tag">MongoDB</span>
          <span class="tech-tag">Gemini API</span>
        </div>
      </div>

      <div class="project-card c4">
        <span class="project-emoji">🎟</span>
        <div class="project-name">CPSCM Reunion System</div>
        <div class="project-desc">
          Complete event registration &amp; payment management with QR code
          verification and automated email notifications.
        </div>
        <div class="project-tech">
          <span class="tech-tag">Next.js</span>
          <span class="tech-tag">Express.js</span>
          <span class="tech-tag">MongoDB</span>
          <span class="tech-tag">SSLCommerz</span>
        </div>
      </div>

    </div>
  </section>

  <!-- CURRENT FOCUS -->
  <section>
    <div class="section-header">
      <div class="section-icon icon-green">📈</div>
      <span class="section-title">Current Focus</span>
    </div>
    <div class="focus-list">
      <div class="focus-item"><span class="focus-dot"></span>Scalable full-stack apps</div>
      <div class="focus-item"><span class="focus-dot"></span>AI-powered web solutions</div>
      <div class="focus-item"><span class="focus-dot"></span>Next.js &amp; TypeScript</div>
      <div class="focus-item"><span class="focus-dot"></span>Open-source contribution</div>
      <div class="focus-item"><span class="focus-dot"></span>Modern software architecture</div>
    </div>
  </section>

  <!-- CONNECT -->
  <section>
    <div class="section-header">
      <div class="section-icon icon-cyan">📫</div>
      <span class="section-title">Connect With Me</span>
    </div>
    <div class="connect-grid">
      <a class="connect-card" href="https://rafiul-razib.netlify.app" target="_blank" rel="noopener">
        <div class="connect-icon">🌐</div>
        <div>
          <div class="connect-label">Portfolio</div>
          <div class="connect-value">rafiul-razib.netlify.app</div>
        </div>
      </a>
      <a class="connect-card" href="https://www.linkedin.com/in/rafiul-habib" target="_blank" rel="noopener">
        <div class="connect-icon">💼</div>
        <div>
          <div class="connect-label">LinkedIn</div>
          <div class="connect-value">in/rafiul-habib</div>
        </div>
      </a>
      <a class="connect-card" href="mailto:rafiul.razib@gmail.com">
        <div class="connect-icon">📧</div>
        <div>
          <div class="connect-label">Email</div>
          <div class="connect-value">rafiul.razib@gmail.com</div>
        </div>
      </a>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer">
    <p class="footer-note">
      ⭐ Feel free to explore my repositories and connect with me.
      I'm always interested in <strong>collaborating on exciting projects</strong>
      and learning new technologies.
    </p>
    <div class="stat-row">
      <div class="stat">
        <span class="stat-num">13+</span>
        <span class="stat-label">Years Exp.</span>
      </div>
      <div class="stat">
        <span class="stat-num">4+</span>
        <span class="stat-label">Projects</span>
      </div>
      <div class="stat">
        <span class="stat-num">BD</span>
        <span class="stat-label">Based in</span>
      </div>
    </div>
  </footer>

</div>
</body>
</html>
