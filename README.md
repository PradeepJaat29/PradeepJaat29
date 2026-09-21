<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pradeep Chaudhary — Software &amp; Data Engineer</title>
<meta name="description" content="Portfolio of Pradeep Chaudhary, Computer Science Engineering graduate — software development, data analytics, and AI/ML.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet">
<style>
  :root{
    bg:#05070d;
    bg-panel:rgba(13,22,38,0.55);
    bg-panel-2:rgba(18,30,50,0.65);
    line:rgba(0,229,255,0.22);
    line-soft:rgba(0,229,255,0.10);
    text:#eaf6ff;
    text-dim:#93aec4;
    text-dimmer:#516b82;
    accent:#00e5ff;
    accent-2:#ff3df0;
    radius:2px;
    mono: 'JetBrains Mono', monospace;
    display: 'Space Grotesk', sans-serif;
    glow-cyan: 0 0 16px rgba(0,229,255,0.45), 0 0 2px rgba(0,229,255,0.8);
    glow-magenta: 0 0 16px rgba(255,61,240,0.4), 0 0 2px rgba(255,61,240,0.75);
  }

  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}

  @media (prefers-reduced-motion: reduce){
    html{scroll-behavior:auto;}
    *{animation-duration:0.001ms !important; animation-iteration-count:1 !important; transition-duration:0.001ms !important;}
  }

  body{
    background:var(--bg);
    color:var(--text);
    font-family:var(--display);
    line-height:1.5;
    position:relative;
    background-image:
      radial-gradient(ellipse 900px 500px at 12% 0%, rgba(0,229,255,0.09), transparent 60%),
      radial-gradient(ellipse 700px 500px at 100% 30%, rgba(255,61,240,0.08), transparent 55%),
      linear-gradient(var(--line-soft) 1px, transparent 1px),
      linear-gradient(90deg, var(--line-soft) 1px, transparent 1px);
    background-size: auto, auto, 48px 48px, 48px 48px;
    background-position: 0 0, 0 0, -1px -1px, -1px -1px;
    overflow-x:hidden;
  }

  /* ambient scanline sweep */
  body::after{
    content:"";
    position:fixed; inset:0;
    pointer-events:none;
    z-index:1;
    background:linear-gradient(180deg, transparent 0%, rgba(0,229,255,0.06) 50%, transparent 100%);
    height:220px;
    animation: scan 9s linear infinite;
    mix-blend-mode:screen;
  }
  @keyframes scan{
    0%{transform:translateY(-220px);}
    100%{transform:translateY(100vh);}
  }
  @media (prefers-reduced-motion: reduce){
    body::after{animation:none; display:none;}
  }
  header, main, footer{position:relative; z-index:2;}

  a{color:inherit;}

  .wrap{
    max-width:1040px;
    margin:0 auto;
    padding:0 28px;
  }

  /* ---------- Top nav ---------- */
  header{
    position:sticky; top:0; z-index:50;
    background:rgba(5,7,13,0.75);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    border-bottom:1px solid var(--line);
  }
  .nav-inner{
    display:flex; align-items:center; justify-content:space-between;
    padding:16px 28px;
    max-width:1040px; margin:0 auto;
  }
  .nav-mark{
    font-family:var(--mono);
    font-size:13px;
    letter-spacing:0.06em;
    color:var(--accent-2);
    text-shadow:var(--glow-magenta);
  }
  .nav-links{
    display:flex; gap:28px;
    list-style:none;
    font-family:var(--mono);
    font-size:12px;
    letter-spacing:0.05em;
    text-transform:uppercase;
  }
  .nav-links a{
    text-decoration:none;
    color:var(--text-dim);
    padding-bottom:2px;
    border-bottom:1px solid transparent;
    transition: color 0.15s ease, border-color 0.15s ease;
  }
  .nav-links a:hover, .nav-links a:focus-visible{
    color:var(--accent);
    border-color:var(--accent);
    text-shadow:var(--glow-cyan);
    outline:none;
  }
  .nav-links li:first-child a{display:none;}
  @media (max-width:640px){
    .nav-links{gap:16px; font-size:11px;}
  }

  /* ---------- Hero ---------- */
  .hero{
    padding:88px 0 64px;
    border-bottom:1px solid var(--line);
    position:relative;
  }
  .eyebrow{
    font-family:var(--mono);
    font-size:12px;
    letter-spacing:0.14em;
    color:var(--accent-2);
    text-transform:uppercase;
    margin-bottom:22px;
    display:flex; align-items:center; gap:10px;
  }
  .eyebrow::before{
    content:"";
    width:8px; height:8px;
    border-radius:50%;
    background:var(--accent-2);
    box-shadow:var(--glow-magenta);
    display:inline-block;
    animation: blink 2.2s infinite steps(1);
  }
  .eyebrow{text-shadow:0 0 10px rgba(95,212,196,0.35);}
  @keyframes blink{ 50%{opacity:0.25;} }

  .hero h1{
    font-size:clamp(38px, 7vw, 68px);
    font-weight:700;
    letter-spacing:-0.01em;
    line-height:1.02;
    margin-bottom:18px;
    background:linear-gradient(100deg, #ffffff 0%, var(--accent) 45%, var(--accent-2) 100%);
    -webkit-background-clip:text;
    background-clip:text;
    color:transparent;
    filter:drop-shadow(0 0 22px rgba(0,229,255,0.35)) drop-shadow(0 0 40px rgba(255,61,240,0.15));
  }
  .hero .role-line{
    font-family:var(--mono);
    font-size:clamp(14px,2.4vw,18px);
    color:var(--text-dim);
    margin-bottom:34px;
    max-width:640px;
  }
  .hero .role-line .div{color:var(--accent);}

  .hero-meta{
    display:grid;
    grid-template-columns:repeat(auto-fit, minmax(160px,1fr));
    gap:1px;
    background:var(--line);
    border:1px solid var(--line);
    margin-bottom:40px;
    max-width:720px;
  }
  .hero-meta div{
    background:var(--bg-panel);
    backdrop-filter: blur(8px);
    -webkit-backdrop-filter: blur(8px);
    padding:14px 16px;
    transition: box-shadow .2s ease, border-color .2s ease;
  }
  .hero-meta div:hover{ box-shadow: inset 0 0 0 1px rgba(0,229,255,0.35); }
  .hero-meta .label{
    font-family:var(--mono);
    font-size:10px;
    letter-spacing:0.08em;
    text-transform:uppercase;
    color:var(--text-dimmer);
    margin-bottom:6px;
  }
  .hero-meta .value{
    font-size:14px;
    font-weight:500;
  }

  .hero-inner{
    display:grid;
    grid-template-columns: 1.4fr auto;
    gap:48px;
    align-items:start;
  }
  @media (max-width:760px){
    .hero-inner{grid-template-columns:1fr;}
  }

  .avatar-frame{
    justify-self:center;
    width:220px; height:220px;
    position:relative;
    margin-top:8px;
  }
  .avatar-frame .ring{
    position:absolute; inset:-10px;
    border-radius:50%;
    background:conic-gradient(from 0deg, var(--accent), var(--accent-2), var(--accent));
    animation: spin 6s linear infinite;
    filter:blur(1px);
  }
  @media (prefers-reduced-motion: reduce){
    .avatar-frame .ring{animation:none;}
  }
  @keyframes spin{ to{ transform:rotate(360deg); } }
  .avatar-frame .photo-wrap{
    position:absolute; inset:6px;
    border-radius:50%;
    overflow:hidden;
    background:var(--bg);
    box-shadow:0 0 30px rgba(0,229,255,0.3), 0 0 60px rgba(255,61,240,0.15);
  }
  .avatar-frame img{
    width:100%; height:100%;
    object-fit:cover;
    filter:grayscale(0.15) contrast(1.05);
  }
  .avatar-tag{
    text-align:center;
    font-family:var(--mono);
    font-size:10px;
    letter-spacing:0.1em;
    color:var(--accent);
    text-shadow:var(--glow-cyan);
    margin-top:16px;
    text-transform:uppercase;
  }

  .cta-row{
    display:flex; flex-wrap:wrap; gap:14px;
  }
  .btn{
    font-family:var(--mono);
    font-size:13px;
    letter-spacing:0.03em;
    text-decoration:none;
    padding:12px 22px;
    border-radius:var(--radius);
    display:inline-flex; align-items:center; gap:8px;
    transition: transform 0.15s ease, background 0.15s ease, border-color .15s ease;
  }
  .btn-primary{
    background:var(--accent);
    color:#02121a;
    font-weight:700;
    border:1px solid var(--accent);
    box-shadow:0 0 18px rgba(0,229,255,0.35);
  }
  .btn-primary:hover{transform:translateY(-1px); box-shadow:0 0 28px rgba(0,229,255,0.6);}
  .btn-ghost{
    border:1px solid var(--line);
    color:var(--text);
    background:rgba(255,255,255,0.02);
  }
  .btn-ghost:hover{border-color:var(--accent-2); color:var(--accent-2); transform:translateY(-1px); box-shadow:0 0 22px rgba(255,61,240,0.35); text-shadow:var(--glow-magenta);}
  .btn:focus-visible{outline:2px solid var(--accent-2); outline-offset:2px;}

  /* ---------- Section shell ---------- */
  section{padding:64px 0; border-bottom:1px solid var(--line);}
  .sec-head{
    display:flex; align-items:baseline; gap:16px;
    margin-bottom:36px;
  }
  .sec-num{
    font-family:var(--mono);
    color:var(--text-dimmer);
    font-size:13px;
  }
  .sec-head h2{
    font-size:clamp(22px,3vw,30px);
    font-weight:600;
    letter-spacing:-0.01em;
  }
  .sec-line{
    flex:1;
    height:1px;
    background:var(--line);
  }

  /* ---------- About ---------- */
  .about-grid{
    display:grid;
    grid-template-columns: 1.3fr 1fr;
    gap:48px;
  }
  @media (max-width:760px){ .about-grid{grid-template-columns:1fr;} }
  .about-text p{
    font-size:16px;
    color:#c9d5e0;
    margin-bottom:16px;
    max-width:56ch;
  }
  .about-text strong{color:var(--text); font-weight:600;}

  .skill-block{margin-bottom:18px;}
  .skill-block:last-child{margin-bottom:0;}
  .skill-cat{
    font-family:var(--mono);
    font-size:11px;
    letter-spacing:0.08em;
    text-transform:uppercase;
    color:var(--accent-2);
    text-shadow:0 0 10px rgba(255,61,240,0.3);
    margin-bottom:10px;
  }
  .chip-row{display:flex; flex-wrap:wrap; gap:8px;}
  .chip{
    font-family:var(--mono);
    font-size:12px;
    padding:5px 10px;
    border:1px solid var(--line);
    color:var(--text-dim);
    border-radius:var(--radius);
    background:rgba(255,255,255,0.02);
    transition: border-color .15s ease, color .15s ease, box-shadow .15s ease;
  }
  .chip:hover{
    border-color:var(--accent);
    color:var(--text);
    box-shadow:0 0 12px rgba(0,229,255,0.3);
  }

  /* ---------- Projects ---------- */
  .project{
    border:1px solid var(--line);
    background:var(--bg-panel);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    margin-bottom:24px;
    position:relative;
    transition: box-shadow .2s ease, border-color .2s ease;
  }
  .project:hover{
    border-color:rgba(0,229,255,0.5);
    box-shadow:0 0 30px rgba(0,229,255,0.12), inset 0 0 0 1px rgba(0,229,255,0.15);
  }
  .project:last-child{margin-bottom:0;}
  .project-head{
    display:flex; justify-content:space-between; align-items:flex-start;
    flex-wrap:wrap; gap:10px;
    padding:22px 26px 18px;
    border-bottom:1px solid var(--line-soft);
  }
  .project-title{
    font-size:20px;
    font-weight:600;
  }
  .project-date{
    font-family:var(--mono);
    font-size:11px;
    color:var(--text-dimmer);
    white-space:nowrap;
    padding-top:4px;
  }
  .project-body{padding:20px 26px 26px;}
  .stack-row{display:flex; flex-wrap:wrap; gap:8px; margin-bottom:18px;}
  .stack-tag{
    font-family:var(--mono);
    font-size:11px;
    padding:4px 9px;
    background:var(--bg-panel-2);
    color:var(--accent-2);
    border:1px solid rgba(255,61,240,0.25);
    text-shadow:0 0 8px rgba(255,61,240,0.25);
  }
  .project-body ul{
    list-style:none;
    display:flex; flex-direction:column; gap:9px;
  }
  .project-body li{
    font-size:14.5px;
    color:#c9d5e0;
    padding-left:18px;
    position:relative;
  }
  .project-body li::before{
    content:"›";
    position:absolute; left:0; top:-1px;
    color:var(--accent);
    font-family:var(--mono);
  }

  /* ---------- Experience ---------- */
  .timeline{border-left:1px solid var(--line); margin-left:6px;}
  .tl-item{
    position:relative;
    padding:0 0 34px 30px;
  }
  .tl-item:last-child{padding-bottom:0;}
  .tl-item::before{
    content:"";
    position:absolute; left:-5px; top:4px;
    width:9px; height:9px;
    background:var(--bg);
    border:2px solid var(--accent-2);
    border-radius:50%;
    box-shadow:var(--glow-magenta);
  }
  .tl-role{font-size:17px; font-weight:600; margin-bottom:2px;}
  .tl-org{
    font-family:var(--mono);
    font-size:12px;
    color:var(--accent-2);
    margin-bottom:4px;
  }
  .tl-date{
    font-family:var(--mono);
    font-size:11px;
    color:var(--text-dimmer);
    margin-bottom:10px;
  }
  .tl-item ul{list-style:none; display:flex; flex-direction:column; gap:7px;}
  .tl-item li{
    font-size:14px; color:#b7c4d1;
    padding-left:16px; position:relative;
  }
  .tl-item li::before{
    content:"—";
    position:absolute; left:0; color:var(--text-dimmer);
  }

  /* ---------- Education / Certs / Achievements grid ---------- */
  .three-col{
    display:grid;
    grid-template-columns:1fr 1fr 1fr;
    gap:1px;
    background:var(--line);
    border:1px solid var(--line);
  }
  @media (max-width:820px){ .three-col{grid-template-columns:1fr;} }
  .col-panel{
    background:var(--bg-panel);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    padding:26px;
    transition: box-shadow .2s ease;
  }
  .col-panel:hover{ box-shadow: inset 0 0 0 1px rgba(0,229,255,0.2); }
  .col-panel h3{
    font-family:var(--mono);
    font-size:12px;
    letter-spacing:0.08em;
    text-transform:uppercase;
    color:var(--accent);
    text-shadow:var(--glow-cyan);
    margin-bottom:18px;
  }
  .edu-entry{margin-bottom:16px;}
  .edu-entry:last-child{margin-bottom:0;}
  .edu-degree{font-size:14.5px; font-weight:600; margin-bottom:2px;}
  .edu-school{font-size:13px; color:var(--text-dim); margin-bottom:2px;}
  .edu-meta{
    font-family:var(--mono);
    font-size:11px;
    color:var(--text-dimmer);
  }
  .plain-list{list-style:none; display:flex; flex-direction:column; gap:12px;}
  .plain-list li{
    font-size:13.5px;
    color:#c9d5e0;
    padding-left:16px;
    position:relative;
  }
  .plain-list li::before{
    content:"✓";
    position:absolute; left:0; top:0;
    color:var(--accent-2);
    font-size:12px;
  }

  /* ---------- Footer / Contact ---------- */
  footer{padding:70px 0 60px; border-bottom:none;}
  .contact-inner{
    display:flex; justify-content:space-between; align-items:flex-end; flex-wrap:wrap; gap:32px;
  }
  footer h2{
    font-size:clamp(28px,5vw,44px);
    font-weight:700;
    letter-spacing:-0.01em;
    max-width:14ch;
    line-height:1.1;
    background:linear-gradient(100deg, #ffffff 0%, var(--accent-2) 60%, var(--accent) 100%);
    -webkit-background-clip:text;
    background-clip:text;
    color:transparent;
    filter:drop-shadow(0 0 20px rgba(255,61,240,0.25));
  }
  .contact-links{
    display:flex; flex-direction:column; gap:10px;
    font-family:var(--mono);
    font-size:14px;
  }
  .contact-links a{
    text-decoration:none;
    color:var(--text-dim);
    border-bottom:1px solid var(--line);
    padding-bottom:2px;
    transition:color .15s ease, border-color .15s ease;
  }
  .contact-links a:hover, .contact-links a:focus-visible{
    color:var(--accent-2); border-color:var(--accent-2); outline:none;
    text-shadow:var(--glow-magenta);
  }
  .foot-note{
    margin-top:60px;
    font-family:var(--mono);
    font-size:11px;
    color:var(--text-dimmer);
    display:flex; justify-content:space-between; flex-wrap:wrap; gap:10px;
  }
</style>
</head>
<body>

<header>
  <div class="nav-inner">
    <div class="nav-mark">PC // PORTFOLIO</div>
    <ul class="nav-links">
      <li><a href="#top">Top</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#experience">Experience</a></li>
      <li><a href="#education">Education</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </div>
</header>

<main id="top">

  <section class="hero wrap" style="border-left:1px solid var(--line); border-right:1px solid var(--line); padding-left:0; padding-right:0;">
    <div class="wrap" style="padding:88px 0 64px;">
      <div class="hero-inner">
        <div>
          <div class="eyebrow">Open to work — full-time &amp; internship roles</div>
          <h1>Pradeep Chaudhary</h1>
          <p class="role-line">Computer Science Engineering graduate <span class="div">/</span> Software development, data analytics &amp; AI-ML <span class="div">/</span> Building things that turn raw data into decisions</p>

          <div class="hero-meta">
            <div>
              <div class="label">Based in</div>
              <div class="value">India</div>
            </div>
            <div>
              <div class="label">Graduated</div>
              <div class="value">B.Tech CSE, 2026</div>
            </div>
            <div>
              <div class="label">Currently</div>
              <div class="value">Data Analytics w/ AI Intern</div>
            </div>
          </div>

          <div class="cta-row">
            <a class="btn btn-primary" href="mailto:pradeepjaat2911@gmail.com">Email me →</a>
            <a class="btn btn-ghost" href="https://www.linkedin.com/in/pradeep-chaudharycs/" target="_blank" rel="noopener">LinkedIn</a>
            <a class="btn btn-ghost" href="https://github.com/pradeepchaudhary-official" target="_blank" rel="noopener">GitHub</a>
          </div>
        </div>

        <div>
          <div class="avatar-frame">
            <div class="ring"></div>
            <div class="photo-wrap">
              <img src="profile.jpg" alt="Pradeep Chaudhary">
            </div>
          </div>
          <div class="avatar-tag">// PC_2026</div>
        </div>
      </div>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about">
    <div class="wrap">
      <div class="sec-head"><span class="sec-num">01</span><h2>About</h2><div class="sec-line"></div></div>
      <div class="about-grid">
        <div class="about-text">
          <p>I'm a <strong>Computer Science Engineering graduate</strong> from Lovely Professional University, with hands-on experience across <strong>software development, data analytics, and AI/ML</strong>. I like taking messy, real-world data and building something structured out of it — a dashboard, a pipeline, a working application.</p>
          <p>My toolkit spans <strong>Python, Java, SQL, and Git</strong>, backed by a solid foundation in OOP, data structures, and databases. I've built everything from an ML-based recognition system presented at a national conference, to a Power BI dashboard analyzing manufacturing defect data, to a Spring Boot web app.</p>
          <p>Comfortable working independently or in a team, picking up new tools fast, and documenting what I build along the way.</p>
        </div>
        <div class="skills-col">
          <div class="skill-block">
            <div class="skill-cat">Programming</div>
            <div class="chip-row">
              <span class="chip">Python</span><span class="chip">Java</span><span class="chip">SQL</span><span class="chip">OOP</span><span class="chip">DSA</span>
            </div>
          </div>
          <div class="skill-block">
            <div class="skill-cat">Data &amp; Analytics</div>
            <div class="chip-row">
              <span class="chip">Pandas</span><span class="chip">Excel</span><span class="chip">Power BI</span><span class="chip">Data Cleaning</span><span class="chip">KPI Analysis</span>
            </div>
          </div>
          <div class="skill-block">
            <div class="skill-cat">Software Dev</div>
            <div class="chip-row">
              <span class="chip">Spring Boot</span><span class="chip">HTML/CSS</span><span class="chip">Thymeleaf</span><span class="chip">REST APIs</span>
            </div>
          </div>
          <div class="skill-block">
            <div class="skill-cat">AI / ML</div>
            <div class="chip-row">
              <span class="chip">Machine Learning</span><span class="chip">Computer Vision</span><span class="chip">Generative AI</span>
            </div>
          </div>
          <div class="skill-block">
            <div class="skill-cat">Tools</div>
            <div class="chip-row">
              <span class="chip">Git</span><span class="chip">GitHub</span><span class="chip">VS Code</span><span class="chip">Maven</span><span class="chip">Linux</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projects">
    <div class="wrap">
      <div class="sec-head"><span class="sec-num">02</span><h2>Projects</h2><div class="sec-line"></div></div>

      <div class="project">
        <div class="project-head">
          <div class="project-title">Manufacturing Quality &amp; Process Analytics Dashboard</div>
          <div class="project-date">JUL 2026 — AUG 2026</div>
        </div>
        <div class="project-body">
          <div class="stack-row">
            <span class="stack-tag">Power BI</span><span class="stack-tag">Excel</span><span class="stack-tag">SQL</span><span class="stack-tag">Python</span>
          </div>
          <ul>
            <li>Cleaned, standardized, and validated operational data covering production, defects, suppliers, downtime, cost, and delivery metrics.</li>
            <li>Used Python and SQL to analyze trends, identify inconsistencies, and calculate operational KPIs.</li>
            <li>Built an interactive Power BI dashboard monitoring defect rate, production volume, downtime, supplier quality, rejection rate, and delivery performance.</li>
            <li>Investigated trends and performance variations to identify high-defect areas and process bottlenecks.</li>
          </ul>
        </div>
      </div>

      <div class="project">
        <div class="project-head">
          <div class="project-title">AI-Based Face Recognition System for Law Enforcement</div>
          <div class="project-date">JAN 2026 — MAY 2026</div>
        </div>
        <div class="project-body">
          <div class="stack-row">
            <span class="stack-tag">Python</span><span class="stack-tag">Machine Learning</span><span class="stack-tag">Computer Vision</span>
          </div>
          <ul>
            <li>Developed an AI-based face recognition solution for automated face detection and recognition.</li>
            <li>Prepared and processed image datasets for model training and evaluation.</li>
            <li>Tested the recognition pipeline against test data and debugged preprocessing and model-related issues.</li>
            <li>Presented the project at <strong style="color:var(--accent-2)">ICSAS 2026</strong>, demonstrating its practical application.</li>
          </ul>
        </div>
      </div>

      <div class="project">
        <div class="project-head">
          <div class="project-title">Career Map Generator</div>
          <div class="project-date">JUN 2025 — JUL 2025</div>
        </div>
        <div class="project-body">
          <div class="stack-row">
            <span class="stack-tag">Java</span><span class="stack-tag">Spring Boot</span><span class="stack-tag">Thymeleaf</span><span class="stack-tag">Maven</span>
          </div>
          <ul>
            <li>Built a web application generating personalized career paths from user inputs and goals.</li>
            <li>Implemented backend functionality using Java and Spring Boot with an MVC-based architecture.</li>
            <li>Developed application logic and dynamic page rendering following modular design principles.</li>
            <li>Performed functional testing and debugging to resolve application issues.</li>
          </ul>
        </div>
      </div>

    </div>
  </section>

  <!-- EXPERIENCE -->
  <section id="experience">
    <div class="wrap">
      <div class="sec-head"><span class="sec-num">03</span><h2>Experience</h2><div class="sec-line"></div></div>
      <div class="timeline">

        <div class="tl-item">
          <div class="tl-role">Data Analytics with AI Intern</div>
          <div class="tl-org">CSRBOX — IBM SkillsBuild Program · Remote</div>
          <div class="tl-date">AUG 2026 — PRESENT</div>
          <ul>
            <li>Working on practical data analytics assignments involving Python, data preprocessing, exploratory analysis, visualization, and AI-assisted workflows.</li>
            <li>Applying analytical techniques to structured datasets to identify patterns, trends, and actionable insights.</li>
          </ul>
        </div>

        <div class="tl-item">
          <div class="tl-role">Marketing Manager Intern</div>
          <div class="tl-org">Vardhman Thermopack — Onsite</div>
          <div class="tl-date">MAY 2025 — NOV 2025</div>
          <ul>
            <li>Supported marketing initiatives through planning, coordination, and execution of assigned activities.</li>
            <li>Developed practical skills in stakeholder communication, organization, and project coordination.</li>
          </ul>
        </div>

        <div class="tl-item">
          <div class="tl-role">Community Outreach Intern</div>
          <div class="tl-org">Tree Craze Foundation — Onsite</div>
          <div class="tl-date">JUN 2024 — AUG 2024</div>
          <ul>
            <li>Supported community development and outreach initiatives through coordination and execution of field activities.</li>
            <li>Worked with team members and stakeholders to support program objectives.</li>
          </ul>
        </div>

      </div>
    </div>
  </section>

  <!-- EDUCATION / CERTS / ACHIEVEMENTS -->
  <section id="education">
    <div class="wrap">
      <div class="sec-head"><span class="sec-num">04</span><h2>Education &amp; Credentials</h2><div class="sec-line"></div></div>

      <div class="three-col">
        <div class="col-panel">
          <h3>Education</h3>
          <div class="edu-entry">
            <div class="edu-degree">B.Tech, Computer Science Engineering</div>
            <div class="edu-school">Lovely Professional University, Jalandhar</div>
            <div class="edu-meta">2022 – 2026 · GPA 7.46</div>
          </div>
          <div class="edu-entry">
            <div class="edu-degree">Intermediate (PCM)</div>
            <div class="edu-school">DAV Public School (CBSE), Ghaziabad</div>
            <div class="edu-meta">2021 · 83%</div>
          </div>
          <div class="edu-entry">
            <div class="edu-degree">High School</div>
            <div class="edu-school">DAV Public School (CBSE), Ghaziabad</div>
            <div class="edu-meta">2019 · 85%</div>
          </div>
        </div>

        <div class="col-panel">
          <h3>Certifications</h3>
          <ul class="plain-list">
            <li>Introduction to Python Programming — Coursera</li>
            <li>Privacy and Security in Online Social Media — NPTEL</li>
            <li>DSA Self-Paced Program — GeeksforGeeks</li>
            <li>Gen AI for Everyone — Coursera</li>
            <li>Introduction to Git — MyGreatLearning</li>
            <li>Data Analytics with AI — IBM SkillsBuild</li>
          </ul>
        </div>

        <div class="col-panel">
          <h3>Achievements</h3>
          <ul class="plain-list">
            <li>Elite Rank in NPTEL Examination, among 11,000+ learners.</li>
            <li>Presented AI-based face recognition research at ICSAS 2026.</li>
            <li>Built hands-on projects spanning software development, data analytics, AI/ML, and computer vision.</li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <footer id="contact">
    <div class="wrap">
      <div class="contact-inner">
        <h2>Let's build something worth documenting.</h2>
        <div class="contact-links">
          <a href="mailto:pradeepjaat2911@gmail.com">pradeepjaat2911@gmail.com</a>
          <a href="tel:+917065212074">+91 70652 12074</a>
          <a href="https://www.linkedin.com/in/pradeep-chaudharycs/" target="_blank" rel="noopener">linkedin.com/in/pradeep-chaudharycs</a>
          <a href="https://github.com/pradeepchaudhary-official" target="_blank" rel="noopener">github.com/pradeepchaudhary-official</a>
        </div>
      </div>
      <div class="foot-note">
        <span>© 2026 Pradeep Chaudhary</span>
        <span>Last updated: August 2026</span>
      </div>
    </div>
  </footer>

</main>

</body>
</html>
