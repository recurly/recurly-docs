---
title: 'Welcome to Navigate: Home Page'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Welcome to Navigate | Recurly</title>
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'Plus Jakarta Sans', sans-serif;
    background: #FFFDF2;
    color: #0D0D0B;
  }

  /* ── HERO ───────────────────────────────────────────────── */
  .nav-hero {
    background: #0D0D0B;
    padding: 64px 40px 56px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .nav-hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background-image:
      radial-gradient(ellipse 120% 60% at 50% 110%, rgba(255,215,6,0.06) 0%, transparent 70%),
      repeating-radial-gradient(ellipse at 50% 50%, transparent 0px, transparent 38px, rgba(255,215,6,0.04) 39px, transparent 40px),
      repeating-radial-gradient(ellipse at 50% 50%, transparent 0px, transparent 68px, rgba(255,215,6,0.03) 69px, transparent 70px),
      repeating-radial-gradient(ellipse at 50% 50%, transparent 0px, transparent 98px, rgba(255,215,6,0.025) 99px, transparent 100px);
    pointer-events: none;
  }

  .nav-hero-logo {
    display: block;
    margin: 0 auto 28px;
    max-height: 56px;
    width: auto;
    position: relative;
    z-index: 1;
  }

  .nav-hero-eyebrow {
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 0.16em;
    text-transform: uppercase;
    color: #FFD706;
    margin-bottom: 14px;
    position: relative;
    z-index: 1;
  }

  .nav-hero h1 {
    font-size: clamp(2rem, 4vw, 3rem);
    font-weight: 800;
    color: #FFFDF2;
    line-height: 1.15;
    margin-bottom: 20px;
    position: relative;
    z-index: 1;
  }

  .nav-hero h1 span {
    color: #FFD706;
  }

  .nav-hero-copy {
    font-size: 17px;
    font-weight: 400;
    color: #CCC9B8;
    max-width: 620px;
    margin: 0 auto;
    line-height: 1.75;
    position: relative;
    z-index: 1;
  }

  /* ── ABOUT STRIP ───────────────────────────────────────── */
  .nav-about {
    background: #F1EFE3;
    padding: 44px 40px;
    text-align: center;
  }

  .nav-about-inner {
    max-width: 760px;
    margin: 0 auto;
  }

  .nav-about h2 {
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: #807D73;
    margin-bottom: 12px;
  }

  .nav-about p {
    font-size: 16px;
    color: #32312D;
    line-height: 1.75;
  }

  .nav-flywheel-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: #FFD706;
    color: #0D0D0B;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    padding: 6px 14px;
    border-radius: 100px;
    margin-bottom: 16px;
  }

  /* ── SECTION LABEL ─────────────────────────────────────── */
  .nav-section {
    padding: 48px 40px 56px;
    background: #FFFDF2;
  }

  .nav-section-label {
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: #807D73;
    margin-bottom: 24px;
    text-align: center;
  }

  /* ── CARDS GRID ────────────────────────────────────────── */
  .nav-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
    max-width: 960px;
    margin: 0 auto;
  }

  @media (max-width: 768px) {
    .nav-grid { grid-template-columns: repeat(2, 1fr); }
    .nav-hero, .nav-about, .nav-section { padding-left: 20px; padding-right: 20px; }
  }

  @media (max-width: 480px) {
    .nav-grid { grid-template-columns: 1fr; }
  }

  .nav-card {
    display: flex;
    flex-direction: column;
    background: #0D0D0B;
    border-radius: 12px;
    padding: 28px 24px 24px;
    text-decoration: none;
    color: inherit;
    border: 1.5px solid #232321;
    transition: border-color 0.2s ease, transform 0.2s ease;
    position: relative;
    overflow: hidden;
  }

  .nav-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: #FFD706;
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.25s ease;
  }

  .nav-card:hover {
    border-color: rgba(255,215,6,0.45);
    transform: translateY(-3px);
  }

  .nav-card:hover::after {
    transform: scaleX(1);
  }

  .nav-card-icon {
    width: 48px;
    height: 48px;
    object-fit: contain;
    margin-bottom: 18px;
  }

  .nav-card-icon-svg {
    width: 48px;
    height: 48px;
    margin-bottom: 18px;
    flex-shrink: 0;
  }

  .nav-card-title {
    font-size: 18px;
    font-weight: 700;
    color: #FFD706;
    margin-bottom: 8px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .nav-card-title .arrow {
    font-size: 16px;
    color: #807D73;
    transition: color 0.2s, transform 0.2s;
  }

  .nav-card:hover .arrow {
    color: #FFD706;
    transform: translateX(3px);
  }

  .nav-card-desc {
    font-size: 13.5px;
    color: #807D73;
    line-height: 1.65;
    flex: 1;
  }

  /* ── OFFICE HOURS CTA ──────────────────────────────────── */
  .nav-cta {
    background: #FFD706;
    padding: 52px 40px;
    text-align: center;
  }

  .nav-cta-inner {
    max-width: 660px;
    margin: 0 auto;
  }

  .nav-cta-eyebrow {
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 0.16em;
    text-transform: uppercase;
    color: rgba(13,13,11,0.55);
    margin-bottom: 12px;
  }

  .nav-cta h2 {
    font-size: clamp(1.5rem, 3vw, 2.1rem);
    font-weight: 800;
    color: #0D0D0B;
    line-height: 1.2;
    margin-bottom: 14px;
  }

  .nav-cta p {
    font-size: 15.5px;
    color: #32312D;
    line-height: 1.7;
    margin-bottom: 28px;
  }

  .nav-cta-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: #0D0D0B;
    color: #FFD706;
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-size: 14px;
    font-weight: 700;
    letter-spacing: 0.04em;
    padding: 13px 28px;
    border-radius: 8px;
    text-decoration: none;
    border: none;
    cursor: pointer;
    transition: background 0.2s, transform 0.15s;
  }

  .nav-cta-btn:hover {
    background: #32312D;
    transform: translateY(-1px);
  }

  .nav-cta-btn svg {
    width: 16px;
    height: 16px;
  }

  /* ── FOOTER STRIP ─────────────────────────────────────── */
  .nav-footer {
    background: #0D0D0B;
    padding: 22px 40px;
    text-align: center;
  }

  .nav-footer p {
    font-size: 12px;
    color: #807D73;
  }

  .nav-footer a {
    color: #CCC9B8;
    text-decoration: none;
  }

  .nav-footer a:hover {
    color: #FFD706;
  }
</style>
</head>
<body>

<!-- ── HERO ─────────────────────────────────────────────── -->
<section class="nav-hero">
  <img
    class="nav-hero-logo"
    src="https://drive.google.com/thumbnail?id=1CDJs5eCmTzuBKTQ4ND6filX9zKjVBBXn&sz=w600-h200"
    alt="Recurly Navigate"
    onerror="this.style.display='none'"
  />
  <p class="nav-hero-eyebrow">Customer Success Program</p>
  <h1>Welcome to <span>Navigate</span></h1>
  <p class="nav-hero-copy">
    We've created a one-of-a-kind Customer Success Program designed to help you scale smarter, navigate challenges with confidence, and celebrate the milestones ahead.
  </p>
</section>

<!-- ── ABOUT ─────────────────────────────────────────────── -->
<section class="nav-about">
  <div class="nav-about-inner">
    <div class="nav-flywheel-badge">
      <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M21 12a9 9 0 1 1-6.219-8.56"/></svg>
      Flywheel-Based Program
    </div>
    <h2>What is Navigate?</h2>
    <p>
      Navigate is Recurly's structured Customer Success program built around the subscription flywheel — a continuous cycle of <strong>Launch</strong>, <strong>Acquire</strong>, <strong>Retain</strong>, and <strong>Scale</strong>. Each stage contains curated learning paths, playbooks, and best practices to help your team move faster, reduce churn, and grow subscription revenue at every phase of the lifecycle.
    </p>
  </div>
</section>

<!-- ── NAVIGATION CARDS ──────────────────────────────────── -->
<section class="nav-section">
  <p class="nav-section-label">Explore the Program</p>
  <div class="nav-grid">

    <!-- LAUNCH -->
    <a class="nav-card" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch">
      <img
        class="nav-card-icon"
        src="https://drive.google.com/thumbnail?id=1c8BHVB7ZoThS7I1IE6cKFz_Qib6FRaSj&sz=w200-h200"
        alt="Launch icon"
        onerror="this.outerHTML='<svg class=\'nav-card-icon-svg\' viewBox=\'0 0 48 48\' fill=\'none\' xmlns=\'http://www.w3.org/2000/svg\'><circle cx=\'24\' cy=\'24\' r=\'22\' stroke=\'#FFD706\' stroke-width=\'2\'/><path d=\'M24 34V20M17 27l7-7 7 7\' stroke=\'#FFFDF2\' stroke-width=\'2\' stroke-linecap=\'round\' stroke-linejoin=\'round\'/></svg>'"
      />
      <div class="nav-card-title">Launch <span class="arrow">→</span></div>
      <p class="nav-card-desc">Get up and running. Configuration, integrations, go-live checklists, and first-90-days essentials to power your subscription business from day one.</p>
    </a>

    <!-- ACQUIRE -->
    <a class="nav-card" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-acquire">
      <img
        class="nav-card-icon"
        src="https://drive.google.com/thumbnail?id=1MSOWNl7V9UgaV9oQHU-mMirnV02uQpjp&sz=w200-h200"
        alt="Acquire icon"
        onerror="this.outerHTML='<svg class=\'nav-card-icon-svg\' viewBox=\'0 0 48 48\' fill=\'none\' xmlns=\'http://www.w3.org/2000/svg\'><circle cx=\'24\' cy=\'24\' r=\'22\' stroke=\'#FFD706\' stroke-width=\'2\'/><path d=\'M17 24h14M28 20l4 4-4 4M20 17v-3M20 34v-3\' stroke=\'#FFFDF2\' stroke-width=\'2\' stroke-linecap=\'round\' stroke-linejoin=\'round\'/></svg>'"
      />
      <div class="nav-card-title">Acquire <span class="arrow">→</span></div>
      <p class="nav-card-desc">Attract and convert new subscribers. Best practices for checkout optimization, pricing strategy, promotions, and subscriber acquisition growth.</p>
    </a>

    <!-- RETAIN -->
    <a class="nav-card" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-retain">
      <img
        class="nav-card-icon"
        src="https://drive.google.com/thumbnail?id=16DEzXygnfOAnosP9dTcKi2hhmvNaMuY-&sz=w200-h200"
        alt="Retain icon"
        onerror="this.outerHTML='<svg class=\'nav-card-icon-svg\' viewBox=\'0 0 48 48\' fill=\'none\' xmlns=\'http://www.w3.org/2000/svg\'><circle cx=\'24\' cy=\'24\' r=\'22\' stroke=\'#FFD706\' stroke-width=\'2\'/><path d=\'M24 16c-4.4 0-8 3.6-8 8s3.6 8 8 8 8-3.6 8-8\' stroke=\'#FFFDF2\' stroke-width=\'2\' stroke-linecap=\'round\'/><path d=\'M32 16v4l-4-2\' stroke=\'#FFFDF2\' stroke-width=\'2\' stroke-linecap=\'round\' stroke-linejoin=\'round\'/></svg>'"
      />
      <div class="nav-card-title">Retain <span class="arrow">→</span></div>
      <p class="nav-card-desc">Reduce churn and keep subscribers engaged. Dunning management, pause &amp; modify strategies, failed payment recovery, and lifecycle communications.</p>
    </a>

    <!-- SCALE -->
    <a class="nav-card" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-scale">
      <img
        class="nav-card-icon"
        src="https://drive.google.com/thumbnail?id=1UsqoLYGAIZbXQALQSTILclxV2vunJXQA&sz=w200-h200"
        alt="Scale icon"
        onerror="this.outerHTML='<svg class=\'nav-card-icon-svg\' viewBox=\'0 0 48 48\' fill=\'none\' xmlns=\'http://www.w3.org/2000/svg\'><circle cx=\'24\' cy=\'24\' r=\'22\' stroke=\'#FFD706\' stroke-width=\'2\'/><path d=\'M16 32l6-6 4 4 6-10\' stroke=\'#FFFDF2\' stroke-width=\'2\' stroke-linecap=\'round\' stroke-linejoin=\'round\'/></svg>'"
      />
      <div class="nav-card-title">Scale <span class="arrow">→</span></div>
      <p class="nav-card-desc">Expand your subscription business globally. Advanced analytics, multi-currency, account hierarchy, revenue optimization, and growth strategies.</p>
    </a>

    <!-- EVENTS & OFFICE HOURS -->
    <a class="nav-card" href="https://navigate.recurly.com/event-hub/">
      <svg class="nav-card-icon-svg" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
        <rect x="10" y="13" width="28" height="26" rx="4" stroke="#FFD706" stroke-width="2"/>
        <path d="M10 21h28" stroke="#FFD706" stroke-width="2"/>
        <path d="M17 10v6M31 10v6" stroke="#FFFDF2" stroke-width="2" stroke-linecap="round"/>
        <circle cx="19" cy="29" r="2" fill="#FFFDF2"/>
        <circle cx="24" cy="29" r="2" fill="#FFD706"/>
        <circle cx="29" cy="29" r="2" fill="#FFFDF2"/>
      </svg>
      <div class="nav-card-title">Events &amp; Office Hours <span class="arrow">→</span></div>
      <p class="nav-card-desc">Connect live with the Recurly team and peers. Webinars, Customer Spotlights, product deep-dives, and Global Customer Success Office Hours.</p>
    </a>

    <!-- RESOURCES -->
    <a class="nav-card" href="#">
      <svg class="nav-card-icon-svg" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M14 12h14l6 6v20a2 2 0 0 1-2 2H14a2 2 0 0 1-2-2V14a2 2 0 0 1 2-2z" stroke="#FFD706" stroke-width="2"/>
        <path d="M28 12v6h6" stroke="#FFD706" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M18 22h12M18 27h8M18 32h10" stroke="#FFFDF2" stroke-width="2" stroke-linecap="round"/>
      </svg>
      <div class="nav-card-title">Resources <span class="arrow">→</span></div>
      <p class="nav-card-desc">Guides, templates, playbooks, and tools to support your success at every stage of the flywheel — available on-demand, whenever you need them.</p>
    </a>

  </div>
</section>

<!-- ── OFFICE HOURS CTA ───────────────────────────────────── -->
<section class="nav-cta">
  <div class="nav-cta-inner">
    <p class="nav-cta-eyebrow">Live with the Recurly Team</p>
    <h2>Join Customer Success Global Office Hours</h2>
    <p>
      Bring your questions, challenges, and ideas directly to Recurly's Customer Success team. Office Hours are open to all Recurly customers — no agenda required. Drop in, get answers, and connect with other merchants navigating the same journey.
    </p>
    <a class="nav-cta-btn" href="https://navigate.recurly.com/event-hub/">
      Register for Office Hours
      <svg viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M3 8h10M9 4l4 4-4 4" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </a>
  </div>
</section>

<!-- ── FOOTER ─────────────────────────────────────────────── -->
<footer class="nav-footer">
  <p>
    Navigate is a program by <a href="https://recurly.com">Recurly</a> Customer Success &nbsp;·&nbsp;
    Questions? Reach your <a href="https://docs.recurly.com/recurly-subscriptions/docs/customer-success-manager">Customer Success Manager</a>
  </p>
</footer>

</body>
</html>
`}</HTMLBlock>

<br />
