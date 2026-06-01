---
permalink: /aboutme
---

<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Portfolio — Student Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=Geist+Mono:wght@300;400;500&family=Geist:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}

:root{
  --paper:#faf9f6;
  --paper2:#f3f1ec;
  --ink:#1c1a16;
  --ink2:#4a4640;
  --ink3:#8a8680;
  --rule:#d4d0c8;
  --rule2:#e8e5de;
  --blue:#1a4bcc;
  --blue-lt:#e8edfb;
  --blue-mid:#9baee8;
  --red:#cc2a1a;
  --red-lt:#fbeae8;
  --green:#1a7a45;
  --green-lt:#e8f5ee;
  --amber:#8a5a0a;
  --amber-lt:#fdf3e0;
  --grid-size:28px;
}

html{scroll-behavior:smooth}

body{
  font-family:'Geist',sans-serif;
  background:var(--paper);
  color:var(--ink);
  line-height:1.6;
  /* engineering grid background */
  background-image:
    linear-gradient(var(--rule2) 1px, transparent 1px),
    linear-gradient(90deg, var(--rule2) 1px, transparent 1px),
    linear-gradient(var(--rule) 1px, transparent 1px),
    linear-gradient(90deg, var(--rule) 1px, transparent 1px);
  background-size:
    var(--grid-size) var(--grid-size),
    var(--grid-size) var(--grid-size),
    calc(var(--grid-size)*4) calc(var(--grid-size)*4),
    calc(var(--grid-size)*4) calc(var(--grid-size)*4);
  background-position:0 0, 0 0, -1px -1px, -1px -1px;
}

/* ── HEADER STRIP ── */
.header-strip{
  position:sticky;top:0;z-index:100;
  background:var(--ink);
  color:var(--paper);
  height:44px;
  display:flex;align-items:center;
  padding:0 2rem;
  gap:2rem;
  font-family:'Geist Mono',monospace;
  font-size:0.72rem;
  font-weight:300;
  letter-spacing:0.05em;
  border-bottom:2px solid var(--blue);
}
.header-strip .logo{
  font-weight:500;
  font-size:0.8rem;
  letter-spacing:0.1em;
  text-transform:uppercase;
  color:white;
  margin-right:auto;
}
.header-strip .corner-tag{
  color:var(--blue-mid);
}
.header-strip nav{display:flex;gap:2rem;}
.header-strip nav a{
  color:rgba(255,255,255,0.55);
  text-decoration:none;
  transition:color 0.15s;
  letter-spacing:0.08em;
  text-transform:uppercase;
  font-size:0.68rem;
}
.header-strip nav a:hover{color:white;}

/* ── HERO ── */
.hero{
  min-height:92vh;
  display:grid;
  grid-template-columns:1fr 320px;
  gap:0;
  max-width:1100px;
  margin:0 auto;
  padding:5rem 2rem 4rem;
  align-items:center;
  position:relative;
}

/* big ruled annotation lines */
.hero::before{
  content:'';
  position:absolute;
  left:0;top:50%;
  width:100%;height:1px;
  background:var(--rule);
  pointer-events:none;
}

.hero-left{position:relative;}

.field-label{
  font-family:'Geist Mono',monospace;
  font-size:0.68rem;
  font-weight:400;
  color:var(--ink3);
  letter-spacing:0.12em;
  text-transform:uppercase;
  display:flex;align-items:center;gap:8px;
  margin-bottom:1.25rem;
}
.field-label::before{
  content:'';
  width:20px;height:1px;
  background:var(--blue);
  display:inline-block;
}

h1{
  font-family:'Instrument Serif',serif;
  font-size:clamp(3rem,7vw,5.5rem);
  line-height:1.0;
  letter-spacing:-0.03em;
  color:var(--ink);
  margin-bottom:2rem;
}
h1 .italic{font-style:italic;color:var(--blue);}
h1 .strike{
  position:relative;
  color:var(--ink3);
}
h1 .strike::after{
  content:'';
  position:absolute;
  left:0;top:50%;
  width:100%;height:2px;
  background:var(--red);
  transform:rotate(-2deg);
}

.hero-desc{
  font-size:1rem;
  color:var(--ink2);
  max-width:480px;
  line-height:1.75;
  font-weight:300;
  margin-bottom:2.5rem;
}

.hero-ctas{display:flex;gap:0.75rem;flex-wrap:wrap;}
.cta{
  font-family:'Geist Mono',monospace;
  font-size:0.78rem;
  font-weight:400;
  letter-spacing:0.05em;
  text-transform:uppercase;
  padding:10px 20px;
  text-decoration:none;
  border:1.5px solid;
  transition:all 0.15s;
  display:inline-flex;align-items:center;gap:8px;
}
.cta-primary{
  background:var(--blue);
  border-color:var(--blue);
  color:white;
}
.cta-primary:hover{background:#1238b0;border-color:#1238b0;}
.cta-ghost{
  background:transparent;
  border-color:var(--rule);
  color:var(--ink2);
}
.cta-ghost:hover{border-color:var(--ink2);}

/* spec panel on right */
.spec-panel{
  border-left:1px solid var(--rule);
  padding:2rem 0 2rem 2.5rem;
  display:flex;flex-direction:column;gap:0;
}
.spec-row{
  padding:1rem 0;
  border-bottom:1px solid var(--rule2);
}
.spec-row:first-child{padding-top:0;}
.spec-key{
  font-family:'Geist Mono',monospace;
  font-size:0.65rem;
  letter-spacing:0.1em;
  text-transform:uppercase;
  color:var(--ink3);
  margin-bottom:4px;
}
.spec-val{
  font-size:0.95rem;
  font-weight:400;
  color:var(--ink);
  line-height:1.4;
}
.spec-val .accent{color:var(--blue);font-weight:500;}
.spec-num{
  font-family:'Instrument Serif',serif;
  font-size:2.2rem;
  color:var(--blue);
  line-height:1;
}

/* ── SECTION WRAPPER ── */
.section{
  max-width:1100px;
  margin:0 auto;
  padding:5rem 2rem;
  position:relative;
}

.section-head{
  display:flex;align-items:baseline;gap:1.5rem;
  margin-bottom:3rem;
  border-bottom:1px solid var(--rule);
  padding-bottom:1rem;
}
.section-num{
  font-family:'Geist Mono',monospace;
  font-size:0.68rem;
  color:var(--ink3);
  letter-spacing:0.1em;
  flex-shrink:0;
}
h2{
  font-family:'Instrument Serif',serif;
  font-size:clamp(1.6rem,3vw,2.2rem);
  font-weight:400;
  letter-spacing:-0.02em;
  color:var(--ink);
}
h2 em{font-style:italic;color:var(--blue);}
.section-rule{flex:1;height:1px;background:var(--rule2);}

/* ── ABOUT ── */
#about{background:white;}
.about-cols{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:4rem;
  align-items:start;
}
.about-body p{
  font-size:0.95rem;
  color:var(--ink2);
  line-height:1.8;
  font-weight:300;
  margin-bottom:1.1rem;
}
.about-body p b{color:var(--ink);font-weight:500;}

.annotation{
  margin-top:2rem;
  padding:1.25rem;
  background:var(--blue-lt);
  border:1px solid var(--blue-mid);
  position:relative;
}
.annotation::before{
  content:'NOTE';
  position:absolute;
  top:-9px;left:12px;
  background:var(--blue-lt);
  border:1px solid var(--blue-mid);
  font-family:'Geist Mono',monospace;
  font-size:0.6rem;
  letter-spacing:0.12em;
  color:var(--blue);
  padding:0 6px;
  line-height:1.6;
}
.annotation p{
  font-size:0.88rem;
  color:var(--blue);
  line-height:1.7;
  font-style:italic;
  font-family:'Instrument Serif',serif;
  font-size:1rem;
}

.skills-table{width:100%;border-collapse:collapse;}
.skills-table tr{border-bottom:1px solid var(--rule2);}
.skills-table tr:last-child{border-bottom:none;}
.skills-table td{padding:0.85rem 0;vertical-align:top;}
.skills-table td:first-child{
  font-family:'Geist Mono',monospace;
  font-size:0.68rem;
  letter-spacing:0.08em;
  color:var(--ink3);
  text-transform:uppercase;
  padding-right:1.5rem;
  white-space:nowrap;
  width:110px;
  padding-top:0.95rem;
}
.skill-title{font-size:0.92rem;font-weight:500;color:var(--ink);margin-bottom:2px;}
.skill-sub{font-size:0.78rem;color:var(--ink3);font-weight:300;}

/* ── PROJECTS ── */
#projects{background:var(--paper2);}

.project-list{display:flex;flex-direction:column;gap:0;}

.project-entry{
  display:grid;
  grid-template-columns:80px 1fr auto;
  gap:0;
  border-top:1px solid var(--rule);
  transition:background 0.15s;
}
.project-entry:last-child{border-bottom:1px solid var(--rule);}
.project-entry:hover{background:rgba(255,255,255,0.7);}

.project-index{
  padding:2rem 1.5rem 2rem 0;
  font-family:'Geist Mono',monospace;
  font-size:0.68rem;
  color:var(--ink3);
  letter-spacing:0.1em;
  padding-top:2.2rem;
}

.project-main{padding:2rem 2rem 2rem 0;}
.project-title{
  font-family:'Instrument Serif',serif;
  font-size:1.4rem;
  font-weight:400;
  color:var(--ink);
  letter-spacing:-0.01em;
  margin-bottom:4px;
}
.project-org{
  font-family:'Geist Mono',monospace;
  font-size:0.7rem;
  color:var(--blue);
  letter-spacing:0.06em;
  text-transform:uppercase;
  margin-bottom:0.85rem;
}
.project-desc{
  font-size:0.9rem;
  color:var(--ink2);
  line-height:1.7;
  font-weight:300;
  max-width:560px;
  margin-bottom:1rem;
}
.tags{display:flex;flex-wrap:wrap;gap:6px;}
.tag{
  font-family:'Geist Mono',monospace;
  font-size:0.65rem;
  letter-spacing:0.05em;
  padding:3px 8px;
  border:1px solid;
}
.tag-blue{background:var(--blue-lt);border-color:var(--blue-mid);color:var(--blue);}
.tag-green{background:var(--green-lt);border-color:#a0cdb5;color:var(--green);}
.tag-amber{background:var(--amber-lt);border-color:#e8c070;color:var(--amber);}
.tag-red{background:var(--red-lt);border-color:#e8b0a8;color:var(--red);}

.project-action{
  padding:2rem 0 2rem 1rem;
  display:flex;flex-direction:column;justify-content:center;align-items:flex-end;gap:0.5rem;
}
.project-link{
  font-family:'Geist Mono',monospace;
  font-size:0.72rem;
  letter-spacing:0.05em;
  color:var(--blue);
  text-decoration:none;
  text-transform:uppercase;
  display:flex;align-items:center;gap:6px;
  transition:gap 0.15s;
  white-space:nowrap;
}
.project-link:hover{gap:10px;}
.project-link svg{width:12px;height:12px;}

/* featured label */
.project-entry.featured .project-title::after{
  content:'★ Featured';
  font-family:'Geist Mono',monospace;
  font-size:0.6rem;
  letter-spacing:0.1em;
  background:var(--blue);
  color:white;
  padding:2px 7px;
  margin-left:10px;
  vertical-align:middle;
  position:relative;top:-2px;
}

/* ── EXPO ── */
#expo{background:white;}

.expo-wrapper{
  display:grid;
  grid-template-columns:1fr 300px;
  gap:0;
  border:1px solid var(--rule);
  background:var(--paper);
}

.expo-main{
  padding:2.5rem;
  border-right:1px solid var(--rule);
}
.expo-stamp{
  display:inline-flex;align-items:center;gap:8px;
  font-family:'Geist Mono',monospace;
  font-size:0.65rem;
  letter-spacing:0.12em;
  text-transform:uppercase;
  color:var(--green);
  background:var(--green-lt);
  border:1px solid #a0cdb5;
  padding:4px 12px;
  margin-bottom:1.25rem;
}
.expo-main h3{
  font-family:'Instrument Serif',serif;
  font-size:1.6rem;
  font-weight:400;
  color:var(--ink);
  letter-spacing:-0.02em;
  line-height:1.2;
  margin-bottom:1.5rem;
}
.expo-main p{
  font-size:0.92rem;
  color:var(--ink2);
  line-height:1.8;
  font-weight:300;
  margin-bottom:1rem;
}
.expo-main p:last-child{margin-bottom:0;}

.expo-sidebar{padding:2rem;}
.sidebar-section{margin-bottom:2rem;}
.sidebar-section:last-child{margin-bottom:0;}
.sidebar-label{
  font-family:'Geist Mono',monospace;
  font-size:0.62rem;
  letter-spacing:0.12em;
  text-transform:uppercase;
  color:var(--ink3);
  border-bottom:1px solid var(--rule2);
  padding-bottom:6px;
  margin-bottom:0.75rem;
}
.reviewer{
  font-size:0.88rem;
  color:var(--ink2);
  padding:5px 0;
  border-bottom:1px solid var(--rule2);
  display:flex;align-items:center;gap:8px;
}
.reviewer::before{
  content:'';
  width:4px;height:4px;
  background:var(--blue);
  display:inline-block;flex-shrink:0;
}
.reviewer:last-child{border-bottom:none;}

.callout{
  background:var(--amber-lt);
  border-left:2px solid var(--amber);
  padding:0.75rem 1rem;
  font-size:0.82rem;
  color:var(--ink2);
  line-height:1.6;
  font-style:italic;
}

.expo-footer-row{
  border-top:1px solid var(--rule);
  padding:1rem 2.5rem;
  font-family:'Geist Mono',monospace;
  font-size:0.68rem;
  color:var(--ink3);
  letter-spacing:0.06em;
  background:var(--paper2);
}

/* ── PAGE FOOTER ── */
footer{
  background:var(--ink);
  color:rgba(255,255,255,0.35);
  padding:2rem 2rem;
  max-width:100%;
  font-family:'Geist Mono',monospace;
  font-size:0.7rem;
  letter-spacing:0.05em;
  display:flex;align-items:center;justify-content:space-between;
  flex-wrap:wrap;gap:1rem;
}
footer a{color:rgba(255,255,255,0.55);text-decoration:none;}
footer a:hover{color:white;}
footer .footer-links{display:flex;gap:2rem;}

/* ── ANIMATIONS ── */
.reveal{
  opacity:0;
  transform:translateY(16px);
  transition:opacity 0.6s ease, transform 0.6s ease;
}
.reveal.visible{opacity:1;transform:none;}

@media(max-width:760px){
  .hero{grid-template-columns:1fr;padding-top:3.5rem;}
  .spec-panel{display:none;}
  .about-cols{grid-template-columns:1fr;gap:2.5rem;}
  .project-entry{grid-template-columns:1fr;padding:1.5rem 0;}
  .project-index{display:none;}
  .project-action{align-items:flex-start;padding:0;}
  .expo-wrapper{grid-template-columns:1fr;}
  .expo-main{border-right:none;border-bottom:1px solid var(--rule);}
  footer{flex-direction:column;gap:0.5rem;}
  header nav{display:none;}
}
</style>
</head>
<body>

<header class="header-strip">
  <span class="logo">DN · Eng</span>
  <span class="corner-tag">REV A · 2026</span>
  <nav>
    <a href="#about">About</a>
    <a href="#projects">Work</a>
    <a href="#expo">CTE Expo</a>
  </nav>
</header>

<!-- ═══════════ HERO ═══════════ -->
<div class="hero">
  <div class="hero-left reveal">
    <div class="field-label">Del Norte High School · San Diego CA</div>
    <h1>
      Engineering<br>
      <span class="italic">real</span> things<br>
      for real people.
    </h1>
    <p class="hero-desc">
      Student engineer passionate about hardware, software, and the space in between — building platforms that serve veterans, learners, and communities.
    </p>
    <div class="hero-ctas">
      <a href="#projects" class="cta cta-primary">View my work →</a>
      <a href="#about" class="cta cta-ghost">About me</a>
    </div>
  </div>

  <div class="spec-panel reveal">
    <div class="spec-row">
      <div class="spec-key">Institution</div>
      <div class="spec-val">Del Norte High School<br><span style="font-size:0.8rem;color:var(--ink3);">San Diego, CA</span></div>
    </div>
    <div class="spec-row">
      <div class="spec-key">Focus Areas</div>
      <div class="spec-val">Electrical &amp; <span class="accent">Mechanical Eng.</span></div>
    </div>
    <div class="spec-row">
      <div class="spec-key">Projects Shipped</div>
      <div class="spec-num">4</div>
    </div>
    <div class="spec-row">
      <div class="spec-key">Non-Profits</div>
      <div class="spec-num">1</div>
    </div>
    <div class="spec-row">
      <div class="spec-key">CTE Expo</div>
      <div class="spec-val"><span class="accent">2026 Presenter</span></div>
    </div>
    <div class="spec-row">
      <div class="spec-key">Status</div>
      <div class="spec-val" style="display:flex;align-items:center;gap:6px;">
        <span style="width:7px;height:7px;background:#1a7a45;border-radius:50%;display:inline-block;"></span>
        Active · Building
      </div>
    </div>
  </div>
</div>

<!-- ═══════════ ABOUT ═══════════ -->
<section id="about">
  <div class="section reveal">
    <div class="section-head">
      <span class="section-num">01 — ABOUT</span>
      <h2>Student. <em>Engineer.</em> Builder.</h2>
      <span class="section-rule"></span>
    </div>

    <div class="about-cols">
      <div class="about-body">
        <p>I am a student at <b>Del Norte High School</b> with a strong interest in both electrical and mechanical engineering. I'm passionate about understanding how technology works — exploring the design, construction, and optimization of systems that solve real-world problems.</p>
        <p>Through coursework and extracurriculars, I'm developing skills in mathematics, physics, programming, and engineering design. I'm particularly drawn to the intersection of <b>hardware and software</b>: robotics, electronics, automation, and innovative mechanical systems.</p>
        <p>Good technology isn't just about clean code or organized interfaces. It's about understanding the people who will actually use it. Designing for accessibility, usability, and real-world impact is just as important as technical implementation.</p>

        <div class="annotation">
          <p>"Experiences like the CTE Expo remind me why I'm passionate about engineering: building solutions that make a meaningful difference in people's lives."</p>
        </div>
      </div>

      <div>
        <table class="skills-table">
          <tr>
            <td>ELEC</td>
            <td>
              <div class="skill-title">Electrical Engineering</div>
              <div class="skill-sub">Electronics · circuits · automation</div>
            </td>
          </tr>
          <tr>
            <td>MECH</td>
            <td>
              <div class="skill-title">Mechanical Engineering</div>
              <div class="skill-sub">Design · construction · optimization</div>
            </td>
          </tr>
          <tr>
            <td>CODE</td>
            <td>
              <div class="skill-title">Programming</div>
              <div class="skill-sub">JS · Python · REST APIs · full-stack</div>
            </td>
          </tr>
          <tr>
            <td>ROBO</td>
            <td>
              <div class="skill-title">Robotics &amp; Automation</div>
              <div class="skill-sub">HW–SW integration · control systems</div>
            </td>
          </tr>
          <tr>
            <td>UX</td>
            <td>
              <div class="skill-title">User-Centered Design</div>
              <div class="skill-sub">Accessibility · usability · impact</div>
            </td>
          </tr>
          <tr>
            <td>MATH</td>
            <td>
              <div class="skill-title">Mathematics &amp; Physics</div>
              <div class="skill-sub">Engineering foundations</div>
            </td>
          </tr>
        </table>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════ PROJECTS ═══════════ -->
<section id="projects" style="padding:0;">
  <div class="section reveal" style="padding-top:5rem;padding-bottom:5rem;">
    <div class="section-head">
      <span class="section-num">02 — WORK</span>
      <h2>Projects &amp; <em>Contributions</em></h2>
      <span class="section-rule"></span>
    </div>

    <div class="project-list">

      <div class="project-entry featured">
        <div class="project-index">01</div>
        <div class="project-main">
          <div class="project-title">Poway Veterans Organization Platform</div>
          <div class="project-org">Open Coding Society · pvo.opencodingsociety.com</div>
          <p class="project-desc">Designed and developed the Volunteer Onboarding Form as part of a full site redesign. Built for speed and accessibility — under two minutes to complete, with clear role descriptions, time commitments, and group volunteer pathways. Presented at CTE Expo 2026 and refined based on feedback from veterans' advocates, including accessibility features for visual impairments.</p>
          <div class="tags">
            <span class="tag tag-blue">Full-Stack</span>
            <span class="tag tag-blue">Jekyll</span>
            <span class="tag tag-green">Non-Profit</span>
            <span class="tag tag-green">Accessibility</span>
            <span class="tag tag-amber">Volunteer UX</span>
          </div>
        </div>
        <div class="project-action">
          <a href="https://pvo.opencodingsociety.com/" target="_blank" class="project-link">
            Visit Platform
            <svg viewBox="0 0 12 12" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M2 6h8M7 2l3 4-3 4"/></svg>
          </a>
          <a href="https://pvo.opencodingsociety.com/titanic" target="_blank" class="project-link">
            Titanic Tool
            <svg viewBox="0 0 12 12" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M2 6h8M7 2l3 4-3 4"/></svg>
          </a>
        </div>
      </div>

      <div class="project-entry">
        <div class="project-index">02</div>
        <div class="project-main">
          <div class="project-title">English Essay Skills Module</div>
          <div class="project-org">Interacters · Open Coding Society</div>
          <p class="project-desc">Multi-stage interactive learning tool for English essay writing. Contributed the AI-powered chatbot integrating Gemini API — enabling news source bias analysis, thesis generation, automatic citation formatting (APA/MLA/Chicago), and voice input support for accessibility.</p>
          <div class="tags">
            <span class="tag tag-blue">Gemini API</span>
            <span class="tag tag-blue">JavaScript</span>
            <span class="tag tag-green">Education Tech</span>
            <span class="tag tag-amber">Voice Input</span>
          </div>
        </div>
        <div class="project-action">
          <a href="https://interacters.github.io/tri2changes/english_help/" target="_blank" class="project-link">
            View Module
            <svg viewBox="0 0 12 12" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M2 6h8M7 2l3 4-3 4"/></svg>
          </a>
        </div>
      </div>

      <div class="project-entry">
        <div class="project-index">03</div>
        <div class="project-main">
          <div class="project-title">AP CSP Create Performance Task</div>
          <div class="project-org">Del Norte High School · AP Computer Science Principles</div>
          <p class="project-desc">Programming project demonstrating algorithmic thinking, data abstraction, and full software development cycle — designed and built independently as part of the AP CSP curriculum.</p>
          <div class="tags">
            <span class="tag tag-blue">AP CSP</span>
            <span class="tag tag-amber">Algorithms</span>
            <span class="tag tag-blue">JavaScript</span>
          </div>
        </div>
        <div class="project-action">
          <a href="https://alicewrli009.github.io/student/CPT" target="_blank" class="project-link">
            View CPT
            <svg viewBox="0 0 12 12" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M2 6h8M7 2l3 4-3 4"/></svg>
          </a>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ═══════════ CTE EXPO ═══════════ -->
<section id="expo" style="background:var(--paper2);">
  <div class="section reveal">
    <div class="section-head">
      <span class="section-num">03 — RECOGNITION</span>
      <h2>CTE Expo <em>2026</em></h2>
      <span class="section-rule"></span>
    </div>

    <div class="expo-wrapper">
      <div class="expo-main">
        <div class="expo-stamp">✓ Presented · CTE Expo 2026</div>
        <h3>Volunteer Onboarding Form — PVO Website Redesign</h3>
        <p>Designed and developed a volunteer sign-up experience that was faster, more accessible, and focused on helping people understand their impact before asking for information. The form included clearly defined volunteer roles, time commitment expectations, pathways for group volunteers, and a streamlined process designed to complete in under two minutes.</p>
        <p>Presenting to veterans' advocates and community leaders was an incredible learning experience. Their feedback helped me see the project from a broader perspective — especially the importance of accessibility features such as adjustable font sizes and text-to-speech options for veterans with visual impairments.</p>
        <p>Hearing about the real challenges faced by an all-volunteer nonprofit reinforced that thoughtful design can directly affect how many people are able to give help — or receive it.</p>
        <p style="margin-top:1.5rem;font-style:italic;color:var(--ink3);font-size:0.88rem;">A special thank you to my teachers and mentors for their guidance, feedback, and encouragement throughout this project. Their support helped me develop both technical skills and a deeper understanding of user-centered design.</p>
      </div>

      <div class="expo-sidebar">
        <div class="sidebar-section">
          <div class="sidebar-label">Review Panel</div>
          <div class="reviewer">Bill Bauerle</div>
          <div class="reviewer">Sue McKibbin</div>
          <div class="reviewer">Amber Kimberling</div>
          <div class="reviewer">Nia Stefani</div>
        </div>
        <div class="sidebar-section">
          <div class="sidebar-label">Key Takeaway</div>
          <div class="callout">"Good technology isn't just about clean code — it's about understanding the people who will actually use it."</div>
        </div>
        <div class="sidebar-section">
          <div class="sidebar-label">Outcome</div>
          <div style="font-size:0.85rem;color:var(--ink2);line-height:1.7;">Refined implementation to include adjustable font sizes and screen-reader support based on direct feedback from veterans' advocates.</div>
        </div>
      </div>

      <div class="expo-footer-row" style="grid-column:1/-1;">
        FIELD: User-Centered Design &amp; Web Development &nbsp;·&nbsp; COURSE: Computer Science / CTE &nbsp;·&nbsp; YEAR: 2026
      </div>
    </div>
  </div>
</section>

<footer>
  <span>© 2026 · Del Norte High School · Student Engineer Portfolio</span>
  <div class="footer-links">
    <a href="https://pvo.opencodingsociety.com/">PVO Platform</a>
    <a href="https://interacters.github.io/tri2changes/english_help/">English Module</a>
    <a href="https://alicewrli009.github.io/student/CPT">CPT Project</a>
  </div>
</footer>

<script>
const obs = new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting) e.target.classList.add('visible');
  });
},{threshold:0.1});
document.querySelectorAll('.reveal').forEach(el=>obs.observe(el));
</script>
</body>
</html>