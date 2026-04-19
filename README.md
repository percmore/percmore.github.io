
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="P.E.R.C. — Positive Emotional Reinforcement Companion. A calm, ethical AI companion designed to guide you through life's challenges." />
  <meta property="og:title" content="P.E.R.C. — Find Calm Clarity" />
  <meta property="og:description" content="A gentle, ethical AI companion for emotional support and reflection." />
  <meta property="og:type" content="website" />
  <title>P.E.R.C. — Positive Emotional Reinforcement Companion</title>
 
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400&family=Lato:wght@300;400;700&display=swap" rel="stylesheet" />
 
  <style>
    /* ── Reset & Base ── */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
 
    :root {
      --cream:        #fff4ea;
      --warm-light:   #fff1e1;
      --brown-dark:   #5a2f1f;
      --brown-mid:    #7a4b34;
      --brown-light:  #a0614a;
      --orange-start: #f28a2f;
      --orange-end:   #dc6527;
      --card-bg:      rgba(255, 241, 225, 0.92);
      --shadow:       0 6px 20px rgba(140, 63, 47, 0.12);
      --radius:       18px;
    }
 
    html { scroll-behavior: smooth; }
 
   body {
  background-image: url('sunset.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed; /* parallax-like scroll effect */
}
 
    /* ── Layout Wrapper ── */
    .wrapper {
      max-width: 1000px;
      margin: 0 auto;
      padding: 60px 24px 50px;
      text-align: center;
    }
 
    /* ── Logo ── */
    .logo {
      font-family: 'Cormorant Garamond', serif;
      font-size: 22px;
      font-weight: 600;
      letter-spacing: 0.22em;
      text-transform: uppercase;
      color: var(--orange-end);
      margin-bottom: 32px;
      opacity: 0;
      animation: fadeUp 0.6s ease forwards 0.1s;
    }
 
    /* ── Hero ── */
    .hero-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(36px, 6vw, 58px);
      font-weight: 600;
      line-height: 1.1;
      color: var(--brown-dark);
      margin-bottom: 20px;
      opacity: 0;
      animation: fadeUp 0.7s ease forwards 0.25s;
    }
 
    .hero-subtitle {
      max-width: 720px;
      margin: 0 auto 48px;
      font-size: clamp(16px, 2.2vw, 20px);
      font-weight: 300;
      line-height: 1.65;
      color: var(--brown-mid);
      opacity: 0;
      animation: fadeUp 0.7s ease forwards 0.4s;
    }
 
    /* ── Divider ── */
    .divider {
      display: flex;
      align-items: center;
      gap: 14px;
      max-width: 420px;
      margin: 0 auto 48px;
      opacity: 0;
      animation: fadeUp 0.6s ease forwards 0.5s;
    }
    .divider::before,
    .divider::after {
      content: '';
      flex: 1;
      height: 1px;
      background: linear-gradient(90deg, transparent, var(--brown-light), transparent);
    }
    .divider span {
      font-family: 'Cormorant Garamond', serif;
      font-style: italic;
      color: var(--brown-light);
      font-size: 18px;
      white-space: nowrap;
    }
 
    /* ── Two-Column Cards ── */
    .cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 22px;
      margin-bottom: 52px;
    }
 
    .card {
      background: var(--card-bg);
      border: 1px solid rgba(160, 97, 74, 0.15);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding: 28px 26px;
      text-align: left;
      opacity: 0;
      animation: fadeUp 0.7s ease forwards;
    }
    .card:nth-child(1) { animation-delay: 0.55s; }
    .card:nth-child(2) { animation-delay: 0.7s;  }
 
    .card h3 {
      font-family: 'Cormorant Garamond', serif;
      font-size: 24px;
      font-weight: 600;
      text-align: center;
      color: var(--brown-dark);
      margin-bottom: 16px;
    }
 
    .card ul {
      list-style: none;
      padding: 0;
    }
    .card ul li {
      font-size: 16px;
      font-weight: 300;
      line-height: 1.7;
      color: var(--brown-mid);
      padding: 6px 0;
      border-bottom: 1px solid rgba(160, 97, 74, 0.1);
      display: flex;
      align-items: flex-start;
      gap: 10px;
    }
    .card ul li:last-child { border-bottom: none; }
    .card ul li::before {
      content: '✦';
      color: var(--orange-start);
      font-size: 11px;
      margin-top: 5px;
      flex-shrink: 0;
    }
 
    /* ── Message Block ── */
    .message {
      max-width: 660px;
      margin: 0 auto 40px;
      font-family: 'Cormorant Garamond', serif;
      font-style: italic;
      font-size: clamp(18px, 2.5vw, 22px);
      line-height: 1.65;
      color: var(--brown-mid);
      opacity: 0;
      animation: fadeUp 0.7s ease forwards 0.85s;
    }
 
    /* ── CTA Button ── */
    .cta-wrap {
      margin-bottom: 52px;
      opacity: 0;
      animation: fadeUp 0.7s ease forwards 1s;
    }
 
    .cta-btn {
      display: inline-block;
      padding: 16px 34px;
      background: linear-gradient(160deg, var(--orange-start), var(--orange-end));
      color: #fff;
      text-decoration: none;
      border-radius: 12px;
      font-family: 'Lato', sans-serif;
      font-size: 17px;
      font-weight: 700;
      letter-spacing: 0.04em;
      box-shadow: 0 6px 18px rgba(140, 63, 47, 0.25);
      transition: transform 0.18s ease, box-shadow 0.18s ease, filter 0.18s ease;
    }
    .cta-btn:hover {
      transform: translateY(-3px);
      box-shadow: 0 10px 26px rgba(140, 63, 47, 0.32);
      filter: brightness(1.06);
    }
    .cta-btn:active {
      transform: translateY(0);
      box-shadow: 0 4px 12px rgba(140, 63, 47, 0.2);
    }
 
    /* ── Footer ── */
    footer {
      font-size: 13px;
      color: var(--brown-light);
      line-height: 1.7;
      opacity: 0;
      animation: fadeUp 0.6s ease forwards 1.1s;
    }
    footer p + p { margin-top: 10px; }
    footer a {
      color: var(--orange-end);
      text-decoration: none;
      border-bottom: 1px solid rgba(220,101,39,0.3);
      transition: border-color 0.15s;
    }
    footer a:hover { border-color: var(--orange-end); }
 
    /* ── Animations ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(18px); }
      to   { opacity: 1; transform: translateY(0);    }
    }
 
    /* ── Responsive ── */
    @media (max-width: 600px) {
      .wrapper { padding: 44px 18px 40px; }
      .cards   { grid-template-columns: 1fr; }
    }
  </style>
</head>
 
<body>
  <main class="wrapper">
 
    <!-- Logo -->
    <div class="logo">✦ P.E.R.C. ✦</div>
 
    <!-- Hero -->
    <h1 class="hero-title">
      Find Calm Clarity with a<br />Gentle, Ethical AI Companion
    </h1>
 
    <p class="hero-subtitle">
      P.E.R.C. (Positive Emotional Reinforcement Companion) is designed to guide you
      through life's challenges in a calm, thoughtful way — standing as a supportive
      alternative to the stress and manipulation of traditional AI chatbots.
    </p>
 
    <!-- Decorative divider -->
    <div class="divider"><span>Who we are &amp; why we're different</span></div>
 
    <!-- Two-column cards -->
    <div class="cards">
      <div class="card">
        <h3>Who We Support</h3>
        <ul>
          <li>People feeling overwhelmed and needing a next step</li>
          <li>Those navigating stress, grief, or life transitions</li>
          <li>Caregivers, veterans, helpers, and diverse communities including LGBTQA+</li>
        </ul>
      </div>
 
      <div class="card">
        <h3>Why We're Different</h3>
        <ul>
          <li>A calm, ethical alternative to pressure-filled AI chatbots</li>
          <li>Focused on support, not engagement metrics</li>
          <li>Privacy and emotional safety over data collection</li>
        </ul>
      </div>
    </div>
 
    <!-- Message -->
    <p class="message">
      Step away from the pressure of data-driven AI bots.<br />
      Find a path that respects your pace and privacy.
    </p>
 
    <!-- CTA -->
    <div class="cta-wrap">
      <a href="#" class="cta-btn">Explore How P.E.R.C. Can Help</a>
    </div>
 
    <!-- Footer -->
    <footer>
      <p>P.E.R.C. provides emotional support. Not a substitute for professional care.</p>
      <p>
        <strong>Brought to you by</strong><br />
        <a href="https://SovereignSpiritsCommunicationsLLC.org" target="_blank" rel="noopener noreferrer">
          SovereignSpiritsCommunicationsLLC.org
        </a>
      </p>
    </footer>
 
  </main>
</body>
</html>
