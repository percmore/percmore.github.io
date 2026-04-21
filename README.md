<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>P.E.R.C. | Personal Emotional Reflection Companion</title>
  <style>
    :root {
      --bg-dark: #2b120f;
      --bg-deep-red: #4a1714;
      --bg-rust: #7a3a23;
      --bg-amber: #b36a3c;
      --bg-cream: #f3e6d0;
      --panel: rgba(20, 12, 10, 0.72);
      --panel-light: rgba(255, 255, 255, 0.07);
      --border: rgba(255, 255, 255, 0.12);
      --text-main: #fff6ea;
      --text-soft: #ead9c4;
      --text-muted: #cbb7a3;
      --button-dark: #201310;
      --button-light: #fff1dc;
      --button-light-text: #4d2418;
      --shadow: 0 18px 40px rgba(0, 0, 0, 0.28);
      --radius-lg: 28px;
      --radius-md: 20px;
      --radius-sm: 14px;
      --max-width: 1280px;
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      font-family: Arial, Helvetica, sans-serif;
      color: var(--text-main);
      background:
        linear-gradient(135deg,
          var(--bg-deep-red) 0%,
          var(--bg-rust) 28%,
          var(--bg-amber) 62%,
          var(--bg-cream) 100%);
      min-height: 100vh;
    }

    .overlay {
      min-height: 100vh;
      background: rgba(0, 0, 0, 0.26);
    }

    .app {
      display: flex;
      min-height: 100vh;
    }

    .sidebar {
      width: 280px;
      background: rgba(24, 14, 12, 0.84);
      border-right: 1px solid var(--border);
      backdrop-filter: blur(12px);
      display: flex;
      flex-direction: column;
      padding: 24px 18px;
    }

    .sidebar .new-btn {
      width: 100%;
      border: 0;
      border-radius: var(--radius-md);
      padding: 14px 18px;
      background: linear-gradient(90deg, #7d1f1a, #a24c22, #be7b38);
      color: var(--text-main);
      font-size: 16px;
      font-weight: 700;
      cursor: pointer;
      box-shadow: var(--shadow);
    }

    .sidebar nav {
      margin-top: 24px;
      display: grid;
      gap: 12px;
    }

    .sidebar .nav-item {
      border: 1px solid var(--border);
      background: var(--panel-light);
      color: var(--text-soft);
      text-decoration: none;
      border-radius: var(--radius-md);
      padding: 14px 16px;
      font-size: 14px;
      font-weight: 600;
      transition: background 0.2s ease;
    }

    .sidebar .nav-item:hover {
      background: rgba(255, 255, 255, 0.12);
    }

    .membership-box {
      margin-top: auto;
      border: 1px solid var(--border);
      background: var(--panel-light);
      border-radius: var(--radius-md);
      padding: 18px;
      color: var(--text-soft);
    }

    .membership-box h3 {
      margin: 0 0 10px;
      font-size: 16px;
      color: var(--text-main);
    }

    .main {
      flex: 1;
      display: flex;
      flex-direction: column;
    }

    .topbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 22px 28px;
      border-bottom: 1px solid var(--border);
      background: rgba(24, 14, 12, 0.58);
      backdrop-filter: blur(10px);
    }

    .brand h1 {
      margin: 0;
      font-size: 34px;
      line-height: 1;
      letter-spacing: 0.02em;
      color: var(--text-main);
    }

    .brand p {
      margin: 8px 0 0;
      font-size: 15px;
      color: var(--text-soft);
      font-weight: 600;
    }

    .topbar-actions {
      display: flex;
      gap: 12px;
    }

    .btn {
      border-radius: 14px;
      padding: 11px 18px;
      font-size: 14px;
      font-weight: 700;
      cursor: pointer;
      border: 1px solid var(--border);
      transition: 0.2s ease;
    }

    .btn-outline {
      background: rgba(255, 255, 255, 0.06);
      color: var(--text-main);
    }

    .btn-outline:hover {
      background: rgba(255, 255, 255, 0.12);
    }

    .btn-primary {
      background: var(--button-light);
      color: var(--button-light-text);
      border: none;
      box-shadow: var(--shadow);
    }

    .btn-primary:hover {
      filter: brightness(0.98);
    }

    .content {
      width: 100%;
      max-width: var(--max-width);
      margin: 0 auto;
      padding: 32px 24px 48px;
      display: grid;
      grid-template-columns: 1.25fr 0.75fr;
      gap: 28px;
    }

    .left-col,
    .right-col {
      display: grid;
      gap: 24px;
      align-content: start;
    }

    .card {
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: var(--radius-lg);
      padding: 28px;
      box-shadow: var(--shadow);
      backdrop-filter: blur(12px);
    }

    .eyebrow {
      margin: 0 0 10px;
      font-size: 13px;
      font-weight: 800;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      color: #ffd6a9;
    }

    .hero-title {
      margin: 0;
      font-size: 54px;
      line-height: 1.05;
      font-weight: 900;
      color: var(--text-main);
    }

    .hero-title span {
      display: block;
      color: #ffe0c2;
    }

    .hero-text {
      margin: 18px 0 0;
      font-size: 18px;
      line-height: 1.75;
      font-weight: 600;
      color: var(--text-soft);
      max-width: 850px;
    }

    .pill-row {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 22px;
    }

    .pill {
      padding: 10px 14px;
      border-radius: 999px;
      border: 1px solid var(--border);
      background: rgba(255, 255, 255, 0.08);
      font-size: 13px;
      font-weight: 700;
      color: var(--text-main);
    }

    .chat-card {
      overflow: hidden;
      padding: 0;
    }

    .chat-header {
      padding: 22px 24px;
      border-bottom: 1px solid var(--border);
      background: rgba(0, 0, 0, 0.12);
    }

    .chat-header h2 {
      margin: 0;
      font-size: 22px;
      color: var(--text-main);
    }

    .chat-header p {
      margin: 8px 0 0;
      color: var(--text-muted);
      font-size: 14px;
      font-weight: 600;
    }

    .chat-body {
      padding: 24px;
      display: grid;
      gap: 18px;
    }

    .message-row {
      display: flex;
    }

    .message-row.user {
      justify-content: flex-end;
    }

    .message-row.ai {
      justify-content: flex-start;
    }

    .bubble {
      max-width: 760px;
      padding: 18px 20px;
      border-radius: 24px;
      font-size: 16px;
      line-height: 1.7;
      box-shadow: 0 10px 24px rgba(0, 0, 0, 0.18);
    }

    .bubble.ai {
      background: rgba(18, 11, 9, 0.84);
      border: 1px solid var(--border);
      color: var(--text-main);
      border-bottom-left-radius: 8px;
    }

    .bubble.user {
      background: linear-gradient(90deg, #7d1f1a, #a64f24, #c07a38);
      color: #fff;
      border-bottom-right-radius: 8px;
      font-weight: 600;
    }

    .chat-input-wrap {
      border-top: 1px solid var(--border);
      background: rgba(0, 0, 0, 0.12);
      padding: 20px 22px 22px;
    }

    .chat-input-box {
      border-radius: 26px;
      border: 1px solid var(--border);
      background: rgba(15, 9, 8, 0.86);
      padding: 14px;
      box-shadow: var(--shadow);
    }

    textarea {
      width: 100%;
      min-height: 120px;
      resize: vertical;
      background: transparent;
      color: var(--text-main);
      border: none;
      outline: none;
      font-size: 16px;
      line-height: 1.6;
      font-family: inherit;
      padding: 10px 12px;
    }

    textarea::placeholder {
      color: var(--text-muted);
    }

    .input-footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 16px;
      flex-wrap: wrap;
      margin-top: 10px;
    }

    .small-pills {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }

    .small-pill {
      border-radius: 999px;
      border: 1px solid var(--border);
      background: rgba(255, 255, 255, 0.05);
      color: var(--text-muted);
      font-size: 12px;
      font-weight: 700;
      padding: 8px 12px;
    }

    .send-btn {
      border: none;
      border-radius: 18px;
      padding: 14px 22px;
      background: var(--button-light);
      color: var(--button-light-text);
      font-size: 15px;
      font-weight: 800;
      cursor: pointer;
      box-shadow: var(--shadow);
    }

    .send-btn:hover {
      filter: brightness(0.98);
    }

    .chat-note {
      margin: 14px 0 0;
      text-align: center;
      color: var(--text-muted);
      font-size: 13px;
      font-weight: 600;
    }

    .side-card h3 {
      margin: 0;
      font-size: 24px;
      color: var(--text-main);
    }

    .side-card p {
      margin: 14px 0 0;
      line-height: 1.8;
      font-size: 15px;
      font-weight: 600;
      color: var(--text-soft);
    }

    .feature-card h4 {
      margin: 0;
      font-size: 18px;
      color: var(--text-main);
    }

    .feature-card p {
      margin: 10px 0 0;
      color: var(--text-soft);
      line-height: 1.8;
      font-size: 15px;
      font-weight: 600;
    }

    .footer-bar {
      margin-top: 8px;
      padding: 0 24px 34px;
      text-align: center;
      color: var(--text-muted);
      font-size: 13px;
      font-weight: 700;
    }

    @media (max-width: 1100px) {
      .content {
        grid-template-columns: 1fr;
      }

      .hero-title {
        font-size: 46px;
      }
    }

    @media (max-width: 860px) {
      .sidebar {
        display: none;
      }

      .topbar {
        padding: 18px 18px;
      }

      .content {
        padding: 22px 16px 34px;
      }

      .hero-title {
        font-size: 38px;
      }

      .hero-text {
        font-size: 16px;
      }

      .bubble {
        font-size: 15px;
      }
    }

    @media (max-width: 560px) {
      .topbar {
        flex-direction: column;
        align-items: flex-start;
        gap: 16px;
      }

      .topbar-actions {
        width: 100%;
      }

      .topbar-actions .btn {
        flex: 1;
      }

      .card {
        padding: 22px 18px;
      }

      .chat-header,
      .chat-body,
      .chat-input-wrap {
        padding-left: 18px;
        padding-right: 18px;
      }

      .hero-title {
        font-size: 32px;
      }
    }
  </style>
</head>
<body>
  <div class="overlay">
    <div class="app">
      <aside class="sidebar">
        <button class="new-btn">+ Start New Reflection</button>

        <nav>
          <a href="#" class="nav-item">Today felt heavy</a>
          <a href="#" class="nav-item">Help me say this calmly</a>
          <a href="#" class="nav-item">What am I carrying?</a>
          <a href="#" class="nav-item">How do I slow down?</a>
        </nav>

        <div class="membership-box">
          <h3>P.E.R.C. Membership</h3>
          <p>Private access for paying users seeking a protected, warm reflection space.</p>
        </div>
      </aside>

      <main class="main">
        <header class="topbar">
          <div class="brand">
            <h1>P.E.R.C.</h1>
            <p>Personal Emotional Reflection Companion</p>
          </div>

          <div class="topbar-actions">
            <button class="btn btn-outline">Sign In</button>
            <button class="btn btn-primary">Member Access</button>
          </div>
        </header>

        <section class="content">
          <div class="left-col">
            <section class="card">
              <p class="eyebrow">Generate Balanced Communication</p>
              <h2 class="hero-title">
                Reflect with clarity.
                <span>Respond with balance.</span>
              </h2>
              <p class="hero-text">
                P.E.R.C. helps users turn private thoughts into calm, balanced expression.
                Built with the SoulWynd Codex, this member-based experience supports
                emotional reflection, healthier communication, and steady self-awareness
                through empathy, integrity, and sustainable pace.
              </p>

              <div class="pill-row">
                <span class="pill">Non-diagnostic</span>
                <span class="pill">Private reflection</span>
                <span class="pill">Codex-guided support</span>
              </div>
            </section>

            <section class="card chat-card">
              <div class="chat-header">
                <h2>Reflection Space</h2>
                <p>ChatGPT-style conversation flow for member-only emotional reflection.</p>
              </div>

              <div class="chat-body">
                <div class="message-row ai">
                  <div class="bubble ai">
                    Hi, I’m here with you. This space is yours — no judgment, no rush.
                    What’s been sitting with you today?
                  </div>
                </div>

                <div class="message-row user">
                  <div class="bubble user">
                    I need help putting how I feel into words without sounding reactive.
                  </div>
                </div>

                <div class="message-row ai">
                  <div class="bubble ai">
                    That makes sense. We can slow it down and shape it clearly.
                    Start with one thread: what feels most important to express without
                    losing your balance?
                  </div>
                </div>
              </div>

              <div class="chat-input-wrap">
                <div class="chat-input-box">
                  <textarea placeholder="Share what is on your mind..."></textarea>

                  <div class="input-footer">
                    <div class="small-pills">
                      <span class="small-pill">Expression first</span>
                      <span class="small-pill">Calm guidance</span>
                      <span class="small-pill">Clear words</span>
                      <span class="small-pill">Private access</span>
                    </div>

                    <button class="send-btn">Send Reflection</button>
                  </div>
                </div>

                <p class="chat-note">
                  Background images and seasonal artwork can be uploaded later without changing this structure.
                </p>
              </div>
            </section>
          </div>

          <aside class="right-col">
            <section class="card side-card">
              <h3>Built from the Codex</h3>
              <p>
                SoulWynd’s core trifecta — Soul, Signal, and Soil — shapes every reflection.
                P.E.R.C. invites expression first, validates emotion without shame,
                and supports calm, balanced communication at a sustainable pace.
              </p>
            </section>

            <section class="card feature-card">
              <h4>Expression First</h4>
              <p>
                P.E.R.C. opens with reflection, validates emotion without stigma,
                and helps users move toward calm, balanced communication.
              </p>
            </section>

            <section class="card feature-card">
              <h4>Private Member Access</h4>
              <p>
                This experience is intended for paying members only, creating a more focused,
                protected space for personal reflection.
              </p>
            </section>

            <section class="card feature-card">
              <h4>SoulWynd Codex Aligned</h4>
              <p>
                Built on Soul, Signal, and Soil — empathy, integrity, and sustainable pace
                guide every interaction.
              </p>
            </section>

            <section class="card side-card">
              <h3>Design Directive</h3>
              <p>
                Use strong, bold text with high contrast at all times. All future background
                photography, leaf textures, or branded fall artwork can be uploaded later as
                layered assets while keeping this layout intact.
              </p>
            </section>
          </aside>
        </section>

        <div class="footer-bar">
          P.E.R.C. is a private emotional reflection companion designed for clear communication,
          warm support, and balanced self-expression.
        </div>
      </main>
    </div>
  </div>
</body>
</html>
