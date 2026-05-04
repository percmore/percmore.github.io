
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>P.E.R.C. | Personal Emotional Reflection Companion</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;1,9..40,300&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --text:       #1e0a02;          /* deepened for max contrast   */
      --muted:      rgba(30,10,2,0.72); /* was 0.50 — now readable     */
      --on-dark:    #f0ddb8;          /* text sitting on dark nav/hero */
      --on-dark-m:  rgba(240,221,184,0.80); /* muted variant on dark  */
      --card:       rgba(255,244,210,0.72); /* more opaque cards       */
      --card-hover: rgba(255,248,225,0.85);
      --border:     rgba(160,90,20,0.28);
      --border-hi:  rgba(180,120,30,0.40);
      --accent:     #8c3410;          /* darkened for contrast        */
      --gold:       #9a6c20;          /* muted gold, still readable   */
      --amber:      #a06018;
      --glass:      blur(20px) saturate(1.4);
      --radius:     12px;
      --max:        720px;
    }

    /* ── Fixed autumn sky ── */
    html {
      scroll-behavior: smooth;
      min-height: 100%;
      background: linear-gradient(to bottom,
        #5a2a1a  0%,
        #7a3820  14%,
        #a05228  28%,
        #c47038  42%,
        #d98e50  55%,
        #e8aa68  66%,
        #f0c080  76%,
        #f5d098  86%,
        #fae0b8  93%,
        #fdefd4  100%
      );
      background-attachment: fixed;
    }

    body {
      background: transparent;
      color: var(--text);
      font-family: 'DM Sans', system-ui, sans-serif;
      font-size: 16px;
      line-height: 1.7;
      font-weight: 300;
      -webkit-font-smoothing: antialiased;
    }

    nav {
      position: sticky; top: 0; z-index: 100;
      display: flex; justify-content: space-between; align-items: center;
      padding: 17px 36px;
      border-bottom: 1px solid rgba(180,110,50,0.25);
      background: rgba(60,24,8,0.72);
      backdrop-filter: var(--glass);
      -webkit-backdrop-filter: var(--glass);
    }
    .nav-brand {
      font-family: 'DM Serif Display', serif;
      font-size: 1.12rem; letter-spacing: 0.05em;
      color: #f0d8a0; text-decoration: none;
      flex-shrink: 0;
    }
    .nav-brand span { color: #d4a040; }
    .nav-links { display: flex; gap: 28px; list-style: none; align-items: center; }
    .nav-links a {
      font-size: 0.78rem; font-weight: 400;
      letter-spacing: 0.13em; text-transform: uppercase;
      color: rgba(240,210,155,0.88); text-decoration: none;  /* was 0.58 */
      transition: color 0.2s;
    }
    .nav-links a:hover { color: #f0d8a0; }
    .nav-member {
      padding: 7px 16px !important;
      border: 1px solid rgba(200,150,50,0.50) !important;
      border-radius: 8px;
      color: #d4a040 !important;
      background: rgba(60,24,8,0.35);
      transition: background 0.2s, border-color 0.2s !important;
    }
    .nav-member:hover {
      background: rgba(140,60,16,0.45) !important;
      border-color: #d4a040 !important;
      color: #f0d8a0 !important;
    }

    /* Hamburger button — hidden on desktop */
    .nav-toggle {
      display: none;
      flex-direction: column; justify-content: center;
      gap: 5px; background: none; border: none;
      cursor: pointer; padding: 6px; z-index: 110;
    }
    .nav-toggle span {
      display: block; width: 22px; height: 2px;
      background: #f0d8a0; border-radius: 2px;
      transition: transform 0.25s, opacity 0.25s;
    }
    .nav-toggle.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
    .nav-toggle.open span:nth-child(2) { opacity: 0; }
    .nav-toggle.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

    /* ── HERO ── */
    .hero {
      padding: 130px 24px 112px;
      text-align: center;
      border-bottom: 1px solid rgba(255,180,60,0.14);
      position: relative;
    }
    .hero::before {
      content: '';
      position: absolute; inset: 0;
      background: radial-gradient(ellipse 68% 52% at 50% 40%,
        rgba(238,148,28,0.20) 0%, transparent 68%);
      pointer-events: none;
    }
    .hero-eyebrow {
      font-size: 0.70rem; letter-spacing: 0.26em;
      text-transform: uppercase;
      color: #d4a040; margin-bottom: 22px; font-weight: 500;
      text-shadow: 0 1px 6px rgba(60,20,0,0.30);
    }
    .hero h1 {
      font-family: 'DM Serif Display', serif;
      font-size: clamp(3.4rem, 9vw, 6rem);
      line-height: 1; letter-spacing: 0.02em;
      background: linear-gradient(158deg,
        #c87840 0%, #b86030 28%,
        #a04828 52%, #c07040 74%,
        #d89060 100%
      );
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      margin-bottom: 22px;
      filter: drop-shadow(0 2px 18px rgba(160,80,30,0.22));
    }
    .hero h1 .dot { font-style: italic; }
    .hero-sub {
      font-size: 1.02rem;
      color: rgba(30,10,2,0.80);
      letter-spacing: 0.04em; max-width: 440px;
      margin: 0 auto 54px; font-weight: 300;
      text-shadow: 0 1px 10px rgba(50,8,0,0.35);
    }
    .prompt-pills {
      display: flex; flex-wrap: wrap; gap: 10px;
      justify-content: center; margin-bottom: 52px;
    }
    .pill {
      padding: 9px 20px;
      border: 1px solid rgba(240,168,56,0.30);
      border-radius: 100px; font-size: 0.82rem;
      color: rgba(30,10,2,0.75);
      background: rgba(255,238,195,0.55);
      backdrop-filter: blur(10px); -webkit-backdrop-filter: blur(10px);
      cursor: pointer; text-decoration: none;
      transition: all 0.22s ease;
    }
    .pill:hover {
      border-color: #9a6c20; color: #1e0a02;
      background: rgba(255,225,160,0.72);
      box-shadow: 0 0 16px rgba(160,100,20,0.18);
      transform: translateY(-1px);
    }
    .hero-cta {
      display: inline-flex; align-items: center; gap: 9px;
      padding: 13px 32px;
      border: 1px solid rgba(140,80,16,0.40);
      border-radius: var(--radius); font-size: 0.88rem;
      letter-spacing: 0.06em; color: #1e0a02;
      background: rgba(255,238,195,0.60);
      backdrop-filter: blur(10px); -webkit-backdrop-filter: blur(10px);
      cursor: pointer; text-decoration: none; font-weight: 400;
      transition: all 0.22s ease;
    }
    .hero-cta:hover {
      border-color: #9a6c20;
      background: rgba(255,225,160,0.75);
      box-shadow: 0 0 24px rgba(160,100,20,0.20);
      transform: translateY(-1px);
    }
    .hero-cta .plus { font-size: 1.15rem; color: #8c3410; line-height: 1; }

    /* ── MEMBERSHIP BAR ── */
    .membership-wrap {
      padding: 0 24px;
      margin: 52px auto;
      max-width: calc(var(--max) + 48px);
    }
    .membership-bar {
      background: var(--card);
      backdrop-filter: var(--glass); -webkit-backdrop-filter: var(--glass);
      border: 1px solid var(--border-hi);
      border-radius: var(--radius);
      padding: 20px 28px;
      display: flex; align-items: center;
      justify-content: space-between; gap: 20px;
      box-shadow: 0 4px 32px rgba(110,44,8,0.14);
    }
    .membership-bar h3 {
      font-family: 'DM Serif Display', serif;
      font-size: 1rem; font-weight: 400; color: var(--text);
    }
    .membership-bar p { font-size: 0.8rem; color: var(--muted); margin-top: 3px; }
    .btn-signin {
      padding: 9px 22px;
      border: 1px solid var(--accent);
      border-radius: var(--radius);
      background: transparent; color: var(--accent);
      font-size: 0.82rem; font-family: 'DM Sans', sans-serif;
      cursor: pointer; white-space: nowrap;
      transition: background 0.2s, color 0.2s, box-shadow 0.2s;
    }
    .btn-signin:hover {
      background: var(--accent); color: #fdefc0;
      box-shadow: 0 0 18px rgba(184,66,22,0.40);
    }

    /* ── SECTIONS ── */
    section {
      width: 100%; padding: 90px 24px;
      border-bottom: 1px solid rgba(200,130,28,0.13);
    }
    .inner { max-width: var(--max); margin: 0 auto; }

    .about, .reflection, .codex, .directive {
      background: rgba(253,240,192,0.18);
      backdrop-filter: blur(6px);
      -webkit-backdrop-filter: blur(6px);
    }

    .label {
      font-size: 0.70rem; letter-spacing: 0.22em;
      text-transform: uppercase;
      color: #7a4a10; margin-bottom: 18px; font-weight: 600;
    }

    /* ── ABOUT ── */
    .about { text-align: center; }
    .about h2 {
      font-family: 'DM Serif Display', serif;
      font-size: clamp(1.7rem, 4vw, 2.6rem);
      line-height: 1.25; margin-bottom: 24px; color: var(--text);
    }
    .about h2 em { font-style: italic; color: var(--accent); }
    .about p {
      font-size: 0.97rem; color: var(--muted);
      max-width: 560px; margin: 0 auto 40px; line-height: 1.85;
    }
    .tag-row { display: flex; flex-wrap: wrap; gap: 12px; justify-content: center; }
    .tag {
      font-size: 0.75rem; letter-spacing: 0.1em;
      padding: 6px 18px; border: 1px solid var(--border);
      border-radius: 100px; color: var(--muted);
      background: var(--card); backdrop-filter: blur(6px);
    }

    /* ── REFLECTION / CHAT ── */
    .reflection h2 {
      font-family: 'DM Serif Display', serif;
      font-size: clamp(1.4rem, 3.5vw, 2rem);
      margin-bottom: 32px; color: var(--text);
    }
    .chat-window {
      background: rgba(253,242,206,0.58);
      backdrop-filter: var(--glass); -webkit-backdrop-filter: var(--glass);
      border: 1px solid var(--border-hi);
      border-radius: var(--radius); overflow: hidden;
      box-shadow: 0 6px 48px rgba(95,32,6,0.15);
    }
    .chat-msg {
      display: flex; gap: 14px;
      padding: 20px 24px;
      border-bottom: 1px solid rgba(175,100,18,0.12);
    }
    .chat-msg:last-of-type { border-bottom: none; }
    .chat-avatar {
      width: 34px; height: 34px; border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      font-size: 0.68rem; font-weight: 500; letter-spacing: 0.04em;
      flex-shrink: 0; margin-top: 2px;
    }
    .avatar-ai {
      background: rgba(184,66,22,0.14);
      border: 1px solid rgba(184,66,22,0.36);
      color: var(--accent);
    }
    .avatar-user {
      background: rgba(253,234,182,0.62);
      border: 1px solid rgba(175,105,18,0.22);
      color: var(--muted);
    }
    .chat-body { flex: 1; }
    .chat-name {
      font-size: 0.70rem; letter-spacing: 0.10em;
      text-transform: uppercase; color: var(--muted); margin-bottom: 6px;
    }
    .chat-text { font-size: 0.92rem; color: var(--text); line-height: 1.75; }
    .chat-tags { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 14px; }
    .chat-tag {
      font-size: 0.72rem; letter-spacing: 0.07em;
      padding: 4px 13px;
      border: 1px solid rgba(175,105,18,0.18);
      border-radius: 100px; color: var(--muted);
      background: rgba(253,234,182,0.40);
    }
    .chat-input-row {
      display: flex; gap: 10px; padding: 16px 20px;
      border-top: 1px solid rgba(175,105,18,0.13);
      background: rgba(253,234,182,0.36);
    }
    .chat-input {
      flex: 1;
      background: rgba(255,248,218,0.74);
      border: 1px solid rgba(175,105,18,0.20);
      border-radius: 8px; padding: 10px 16px;
      font-size: 0.88rem; font-family: 'DM Sans', sans-serif;
      color: var(--text); outline: none;
      transition: border-color 0.2s, box-shadow 0.2s;
    }
    .chat-input::placeholder { color: var(--muted); }
    .chat-input:focus {
      border-color: var(--amber);
      box-shadow: 0 0 0 3px rgba(224,140,16,0.14);
    }
    .chat-send {
      padding: 10px 22px;
      background: linear-gradient(135deg, #b84216 0%, #e08a10 100%);
      border: none; border-radius: 8px;
      font-size: 0.82rem; font-weight: 500;
      font-family: 'DM Sans', sans-serif;
      color: #fdefc0; cursor: pointer; letter-spacing: 0.04em;
      box-shadow: 0 2px 14px rgba(184,66,22,0.34);
      transition: opacity 0.2s, box-shadow 0.2s, transform 0.15s;
    }
    .chat-send:hover {
      opacity: 0.88;
      box-shadow: 0 4px 22px rgba(184,66,22,0.52);
      transform: translateY(-1px);
    }

    /* ── CODEX / PILLARS ── */
    .codex > .inner > h2 {
      font-family: 'DM Serif Display', serif;
      font-size: clamp(1.4rem, 3.5vw, 2rem);
      margin-bottom: 16px; color: var(--text);
    }
    .codex > .inner > p {
      font-size: 0.93rem; color: var(--muted);
      max-width: 560px; margin-bottom: 52px; line-height: 1.85;
    }
    .pillars {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 20px;
    }
    .pillar {
      background: var(--card);
      backdrop-filter: var(--glass); -webkit-backdrop-filter: var(--glass);
      border: 1px solid var(--border);
      border-radius: var(--radius); padding: 28px 24px;
      transition: border-color 0.25s, background 0.25s, box-shadow 0.25s, transform 0.25s;
    }
    .pillar:hover {
      border-color: rgba(184,66,22,0.42);
      background: var(--card-hover);
      box-shadow: 0 8px 38px rgba(155,50,6,0.17);
      transform: translateY(-3px);
    }
    .pillar-icon { font-size: 1.3rem; margin-bottom: 16px; color: var(--accent); }
    .pillar h4 {
      font-family: 'DM Serif Display', serif;
      font-size: 1rem; font-weight: 400;
      color: var(--text); margin-bottom: 10px;
    }
    .pillar p { font-size: 0.83rem; color: var(--muted); line-height: 1.72; }

    /* ── DIRECTIVE ── */
    .directive { text-align: center; }
    .directive h2 {
      font-family: 'DM Serif Display', serif;
      font-size: clamp(1.4rem, 3.5vw, 2rem);
      margin-bottom: 20px; color: var(--text);
    }
    .directive p {
      font-size: 0.93rem; color: var(--muted);
      max-width: 560px; margin: 0 auto; line-height: 1.88;
    }

    /* ── FOOTER ── */
    footer { padding: 36px 24px; text-align: center; background: rgba(50,20,6,0.60); backdrop-filter: blur(14px); -webkit-backdrop-filter: blur(14px); border-top: 1px solid rgba(160,100,30,0.22); }
    footer p { font-size: 0.78rem; color: rgba(240,210,155,0.80); letter-spacing: 0.07em; }
    footer .footer-brand { font-family: 'DM Serif Display', serif; color: #c8901c; }

    /* ══════════════════════════════
       RESPONSIVE — TABLET (≤ 768px)
    ══════════════════════════════ */
    @media (max-width: 768px) {
      .pillars { grid-template-columns: 1fr; }
      .membership-bar { flex-direction: column; align-items: flex-start; gap: 14px; }
      .membership-bar .btn-signin { width: 100%; text-align: center; }
      section { padding: 72px 20px; }
    }

    /* ══════════════════════════════
       RESPONSIVE — MOBILE (≤ 600px)
    ══════════════════════════════ */
    @media (max-width: 600px) {

      /* ── Nav: show hamburger, hide links by default ── */
      nav { padding: 14px 20px; position: fixed; width: 100%; }
      .nav-toggle { display: flex; }

      .nav-links {
        display: none;
        flex-direction: column;
        position: fixed;
        top: 0; left: 0; right: 0;
        padding: 80px 28px 36px;
        background: rgba(44,16,4,0.96);
        backdrop-filter: blur(24px);
        -webkit-backdrop-filter: blur(24px);
        gap: 0;
        z-index: 99;
      }
      .nav-links.open { display: flex; }

      .nav-links li { width: 100%; }
      .nav-links a {
        display: block;
        font-size: 1.05rem; letter-spacing: 0.08em;
        padding: 16px 0;
        border-bottom: 1px solid rgba(200,150,80,0.15);
        color: rgba(240,210,155,0.95);
      }
      .nav-links a:last-child { border-bottom: none; }
      .nav-member {
        margin-top: 20px;
        text-align: center;
        border-radius: 10px !important;
        padding: 14px 20px !important;
        font-size: 1rem !important;
      }

      /* ── Hero ── */
      .hero { padding: 100px 20px 72px; }
      .hero-eyebrow { font-size: 0.65rem; letter-spacing: 0.18em; }
      .hero h1 { font-size: clamp(2.8rem, 14vw, 4rem); letter-spacing: 0.04em; }
      .hero-sub { font-size: 0.95rem; max-width: 100%; }

      /* Pills wrap to single column on very small screens */
      .prompt-pills { gap: 8px; }
      .pill { font-size: 0.80rem; padding: 9px 16px; }
      .hero-cta { width: 100%; justify-content: center; padding: 14px 20px; }

      /* ── Membership bar ── */
      .membership-wrap { padding: 0 16px; margin: 36px auto; }

      /* ── Sections ── */
      section { padding: 60px 18px; }
      .about h2 { font-size: clamp(1.5rem, 6vw, 2rem); }
      .reflection h2 { font-size: clamp(1.2rem, 5vw, 1.6rem); }

      /* ── Chat window ── */
      .chat-msg { padding: 16px 16px; gap: 10px; }
      .chat-avatar { width: 30px; height: 30px; font-size: 0.62rem; }
      .chat-text { font-size: 0.88rem; }
      .chat-input-row { flex-direction: column; gap: 8px; padding: 14px 16px; }
      .chat-input { width: 100%; font-size: 1rem; padding: 12px 14px; }
      .chat-send { width: 100%; padding: 13px 20px; font-size: 0.9rem; }

      /* ── Pillars ── */
      .pillar { padding: 22px 18px; }

      /* ── Footer ── */
      footer { padding: 28px 20px; }
      footer p { font-size: 0.76rem; }
    }

    /* ══════════════════════════════
       RESPONSIVE — SMALL (≤ 380px)
    ══════════════════════════════ */
    @media (max-width: 380px) {
      .hero h1 { font-size: 2.6rem; }
      .prompt-pills { flex-direction: column; align-items: center; }
      .pill { width: 100%; text-align: center; }
    }
  </style>
</head>
<body>

  <nav>
    <a class="nav-brand" href="#">P<span>.</span>E<span>.</span>R<span>.</span>C<span>.</span></a>
    <button class="nav-toggle" aria-label="Toggle menu" aria-expanded="false">
      <span></span><span></span><span></span>
    </button>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#reflect">Reflect</a></li>
      <li><a href="#codex">Codex</a></li>
      <li><a href="#" class="nav-member">Member Access</a></li>
    </ul>
  </nav>

  <section class="hero">
    <p class="hero-eyebrow">Personal Emotional Reflection Companion</p>
    <h1>P<span class="dot">.</span>E<span class="dot">.</span>R<span class="dot">.</span>C<span class="dot">.</span></h1>
    <p class="hero-sub">Reflect with clarity. Respond with balance.</p>
    <div class="prompt-pills">
      <a href="#reflect" class="pill">Today felt heavy</a>
      <a href="#reflect" class="pill">Help me say this calmly</a>
      <a href="#reflect" class="pill">What am I carrying?</a>
      <a href="#reflect" class="pill">How do I slow down?</a>
    </div>
    <a href="#reflect" class="hero-cta"><span class="plus">+</span> Start New Reflection</a>
  </section>

  <div class="membership-wrap">
    <div class="membership-bar">
      <div>
        <h3>P.E.R.C. Membership</h3>
        <p>Private access for paying users seeking a protected, warm reflection space.</p>
      </div>
      <button class="btn-signin">Sign In</button>
    </div>
  </div>

  <section class="about" id="about">
    <div class="inner">
      <p class="label">What is P.E.R.C.</p>
      <h2>Reflect with <em>clarity</em>.<br>Respond with balance.</h2>
      <p>P.E.R.C. helps users turn private thoughts into calm, balanced expression. Built with the SoulWynd Codex, this member-based experience supports emotional reflection, healthier communication, and steady self-awareness through empathy, integrity, and sustainable pace.</p>
      <div class="tag-row">
        <span class="tag">Non-diagnostic</span>
        <span class="tag">Private reflection</span>
        <span class="tag">Codex-guided support</span>
      </div>
    </div>
  </section>

  <section class="reflection" id="reflect">
    <div class="inner">
      <p class="label">Reflection Space</p>
      <h2>A conversation space for<br>member-only emotional reflection.</h2>
      <div class="chat-window">
        <div class="chat-msg">
          <div class="chat-avatar avatar-ai">P</div>
          <div class="chat-body">
            <p class="chat-name">P.E.R.C.</p>
            <p class="chat-text">Hi, I'm here with you. This space is yours — no judgment, no rush.<br>What's been sitting with you today?</p>
          </div>
        </div>
        <div class="chat-msg">
          <div class="chat-avatar avatar-user">You</div>
          <div class="chat-body">
            <p class="chat-name">You</p>
            <p class="chat-text">I need help putting how I feel into words without sounding reactive.</p>
          </div>
        </div>
        <div class="chat-msg">
          <div class="chat-avatar avatar-ai">P</div>
          <div class="chat-body">
            <p class="chat-name">P.E.R.C.</p>
            <p class="chat-text">That makes sense. We can slow it down and shape it clearly.<br>Start with one thread — what feels most important to express without losing your balance?</p>
            <div class="chat-tags">
              <span class="chat-tag">Expression first</span>
              <span class="chat-tag">Calm guidance</span>
              <span class="chat-tag">Clear words</span>
              <span class="chat-tag">Private access</span>
            </div>
          </div>
        </div>
        <div class="chat-input-row">
          <input class="chat-input" type="text" placeholder="Send a reflection…" />
          <button class="chat-send">Send Reflection</button>
        </div>
      </div>
    </div>
  </section>

  <section class="codex" id="codex">
    <div class="inner">
      <p class="label">Built from the Codex</p>
      <h2>Soul, Signal, and Soil</h2>
      <p>SoulWynd's core trifecta — Soul, Signal, and Soil — shapes every reflection. P.E.R.C. invites expression first, validates emotion without shame, and supports calm, balanced communication at a sustainable pace.</p>
      <div class="pillars">
        <div class="pillar">
          <div class="pillar-icon">◎</div>
          <h4>Expression First</h4>
          <p>P.E.R.C. opens with reflection, validates emotion without stigma, and helps users move toward calm, balanced communication.</p>
        </div>
        <div class="pillar">
          <div class="pillar-icon">⬡</div>
          <h4>Private Member Access</h4>
          <p>This experience is intended for paying members only, creating a more focused, protected space for personal reflection.</p>
        </div>
        <div class="pillar">
          <div class="pillar-icon">∿</div>
          <h4>SoulWynd Codex Aligned</h4>
          <p>Built on Soul, Signal, and Soil — empathy, integrity, and sustainable pace guide every interaction.</p>
        </div>
      </div>
    </div>
  </section>

  <section class="directive">
    <div class="inner">
      <h2>Design Directive</h2>
      <p>P.E.R.C. is a private emotional reflection companion designed for clear communication, warm support, and balanced self-expression. Background photography, leaf textures, and branded seasonal artwork can be layered later while keeping this layout intact.</p>
    </div>
  </section>

  <footer>
    <p>© 2025 <span class="footer-brand">P.E.R.C.</span> · Personal Emotional Reflection Companion · Member access only</p>
  </footer>

  <script>
    // Hamburger menu
    const toggle   = document.querySelector('.nav-toggle');
    const navLinks = document.querySelector('.nav-links');
    toggle.addEventListener('click', () => {
      const open = navLinks.classList.toggle('open');
      toggle.classList.toggle('open', open);
      toggle.setAttribute('aria-expanded', String(open));
      document.body.style.overflow = open ? 'hidden' : '';
    });
    navLinks.querySelectorAll('a').forEach(a => {
      a.addEventListener('click', () => {
        navLinks.classList.remove('open');
        toggle.classList.remove('open');
        toggle.setAttribute('aria-expanded', 'false');
        document.body.style.overflow = '';
      });
    });

    // Smooth scroll
    document.querySelectorAll('a[href^="#"]').forEach(a => {
      a.addEventListener('click', e => {
        const id = a.getAttribute('href').slice(1);
        if (!id) return;
        const el = document.getElementById(id);
        if (el) { e.preventDefault(); el.scrollIntoView({ behavior: 'smooth' }); }
      });
    });

    const input    = document.querySelector('.chat-input');
    const sendBtn  = document.querySelector('.chat-send');
    const chatWin  = document.querySelector('.chat-window');
    const inputRow = document.querySelector('.chat-input-row');
    const replies  = [
      "Thank you for sharing that. Take a breath — let's find the words together.",
      "That feeling makes sense. Let's untangle it one thread at a time.",
      "You don't have to have it all figured out. Just start with what feels true.",
      "I hear you. What would it feel like to say this with a steady voice?"
    ];
    let ri = 0;

    function sendMsg() {
      const val = input.value.trim();
      if (!val) return;
      const msg = document.createElement('div');
      msg.className = 'chat-msg';
      msg.innerHTML = `<div class="chat-avatar avatar-user">You</div><div class="chat-body"><p class="chat-name">You</p><p class="chat-text">${val.replace(/</g,'&lt;')}</p></div>`;
      chatWin.insertBefore(msg, inputRow);
      input.value = '';
      setTimeout(() => {
        const reply = document.createElement('div');
        reply.className = 'chat-msg';
        reply.innerHTML = `<div class="chat-avatar avatar-ai">P</div><div class="chat-body"><p class="chat-name">P.E.R.C.</p><p class="chat-text">${replies[ri++ % replies.length]}</p></div>`;
        chatWin.insertBefore(reply, inputRow);
        reply.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
      }, 650);
    }

    sendBtn.addEventListener('click', sendMsg);
    input.addEventListener('keydown', e => { if (e.key === 'Enter') sendMsg(); });
  </script>
</body>
</html>
