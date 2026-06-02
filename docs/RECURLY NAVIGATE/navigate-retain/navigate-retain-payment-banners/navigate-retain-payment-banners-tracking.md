---
title: 'Payment Banners: Tracking your impact'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
/* HOST-THEME BACKGROUND OVERRIDE */
body { background: #ffffff !important; }

/* ── GLOBAL CSS IMMUNITY BLOCK ── */
.rc-guide h1 { border-bottom: none !important; padding-bottom: 0 !important; }
.rc-guide, .rc-guide * { font-family: "Polar", "Helvetica Neue", Helvetica, arial, sans-serif !important; }
.rc-guide [class^="fa-"],
.rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide .fa-brands,
.rc-guide [class*="fa-brands"] { font-family: "Font Awesome 6 Brands" !important; }

/* ── NAVIGATE MASTER ARMOR — (0,0,7,1) ── */
.rm-Markdown.markdown-body .rc-guide a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:hover,
.rc-guide a:active {
  text-decoration: none !important;
  text-decoration-line: none !important;
  text-decoration-color: transparent !important;
  text-underline-offset: unset !important;
  border-bottom: 0 !important;
}

html { scroll-behavior: smooth; scroll-padding-top: 80px; }

/* ── DESIGN TOKENS ── */
.rc-guide {
  --yellow: #FFD706;
  --orange: #FF8200;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
  --retain: #FF9D88;
  color: #32312D !important;
  background: #ffffff;
}

/* ── FONT AWESOME ICON HELPERS ── */
.rc-fa-section { color: var(--offblack); font-size: 1rem; }

/* ── LAYOUT ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Back link — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

/* ── ANNOUNCEMENT BAR (hidden) ── */
.rc-announce-bar { display: none; }

/* ── HERO ── */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack); background-size: cover;
  color: #fff; padding: 56px 40px 48px; text-align: center; border-radius: 16px;
}
.rc-lp-pillar-tag {
  display: inline-flex; align-items: center; gap: 7px;
  background: rgba(255,157,136,0.20); border: 1px solid rgba(255,157,136,0.45);
  color: #FF9D88; font-size: .75rem; font-weight: 800; letter-spacing: 1px;
  text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px;
}
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: var(--lightgray); line-height: 1.6; }
.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); line-height: 1.3; }

/* ── NAV — non-sticky, open ── */
details.rc-sticky-nav-wrap {
  position: relative; z-index: 1; background-color: var(--retain);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px; border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08); overflow: hidden;
}
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: var(--offblack); }
.rc-nav-chevron { font-size: .72rem; color: var(--offblack); opacity: 0.55; line-height: 1; transition: transform 0.25s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link {
  color: #0D0D0B !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px;
  text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s;
  white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:hover,
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; }

/* ── CONTENT SECTIONS ── */
.rc-lp-section { margin-bottom: 52px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section > p { font-size: .97rem; line-height: 1.7; color: var(--darkgray); margin: 0 0 24px; }

/* ── FEATURE CARD GRIDS ── */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 28px; }
.rc-card-grid-3col { grid-template-columns: 1fr 1fr 1fr; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: #FF9D88; box-shadow: 0 4px 16px rgba(255,157,136,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; color: var(--offblack); }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }
.rc-feature-tag { display: inline-block; margin-top: 4px; padding: 3px 10px; border-radius: 20px; font-size: .7rem; font-weight: 700; letter-spacing: .5px; background: var(--offblack); color: var(--yellow); width: fit-content; }

/* ── NUMBERED STEPS ── */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 0 0 32px; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 20px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.65; margin: 0 0 6px; }
.rc-step-content p:last-child { margin-bottom: 0; }
.rc-step-content strong { color: var(--darkgray); }
/* Step inline links — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide .rc-step-content a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-step-content a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide .rc-step-content a:hover,
.rc-guide .rc-step-content a:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* ── ACCENT CARDS ── */
.rc-accent-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 0; }
.rc-accent-card.rc-accent-retain { border-left: 4px solid var(--retain); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 12px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.7; margin: 0 0 8px; }
.rc-accent-card p:last-child { margin-bottom: 0; }
/* Accent card inline links — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide .rc-accent-card a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-accent-card a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide .rc-accent-card a:hover,
.rc-guide .rc-accent-card a:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* ── CALLOUTS ── */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body > strong { color: var(--offblack); }
/* Callout inline links — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-callout-body a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:hover,
.rc-guide .rc-callout-body a:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* ── PATH NAV BUTTONS ── */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 44px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; text-align: center; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev {
  background: transparent; color: #0D0D0B !important; text-decoration: none !important;
  padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem;
  display: inline-flex; align-items: center; gap: 8px;
  border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s;
}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path {
  background: #FFD706; color: #0D0D0B !important; text-decoration: none !important;
  padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem;
  display: inline-flex; align-items: center; gap: 8px; transition: all .2s;
  border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:hover,
.rc-guide a.rc-btn-path:hover {
  background: transparent !important; color: #0D0D0B !important;
  border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important;
}

/* ── RESOURCES ── */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--retain); border-radius: 10px; padding: 20px 24px; margin: 40px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link {
  color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px;
  text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem;
  transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration-color: #FF9D88 !important; }

/* ── FOOTER NAV ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link { color: #807D73 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:hover,
.rc-guide a.rc-footer-link:hover { color: #FF8200 !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* ── CONSOLIDATED RESPONSIVE BLOCK ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; }
  .rc-card-grid, .rc-card-grid.rc-card-grid-3col { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">

  <div class="rc-announce-bar"></div>

  <!-- Back link -->
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-back-link">← Back to Retain</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Hero -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt="Retain">
        Retain · Payment banners
      </div>
      <div class="rc-lp-hero-title">
        <h1>Tracking your impact</h1>
      </div>
      <p>Know whether your banners are working — and what to do when they're not. Four metrics to track, a 90-day measurement framework, and a troubleshooting guide for underperforming campaigns.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">Up to 80%</div>
          <div class="rc-hero-stat-label">Recovery on failing invoices when in-app banners are added to dunning</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">40%</div>
          <div class="rc-hero-stat-label">Of all subscriber losses are involuntary — customers who didn't mean to leave</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">40%</div>
          <div class="rc-hero-stat-label">Of subscribers attempting to cancel can be saved by a well-timed in-app prompt</div>
        </div>
      </div>
    </div>

    <!-- Nav: non-sticky, open. Active: page 6 -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners" class="rc-sticky-link">Payment banners</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-why" class="rc-sticky-link"><span class="rc-step-badge">1</span> Why it matters</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-use-cases" class="rc-sticky-link"><span class="rc-step-badge">2</span> Use cases</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-webhooks" class="rc-sticky-link"><span class="rc-step-badge">3</span> Webhooks setup</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage" class="rc-sticky-link"><span class="rc-step-badge">4</span> Recurly Engage setup</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-strategy" class="rc-sticky-link"><span class="rc-step-badge">5</span> Strategy &amp; best practices</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-tracking" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Tracking your impact
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-review" class="rc-sticky-link"><span class="rc-step-badge">7</span> Review &amp; resources</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- Section 1: Four metrics -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-chart-bar rc-fa-section"></i> Four metrics that matter</h2>

      <p>Banner analytics can be deceptively noisy — lots of data points, but four core metrics tell you everything you need to know about whether your program is healthy and where the work still is.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-arrow-pointer"></i></div>
          <h4>Banner click-through rate (CTR)</h4>
          <p>The percentage of subscribers who saw the banner and clicked your CTA. CTR tells you whether your message is landing. Low CTR is almost always a messaging problem — the copy is too generic or doesn't create enough urgency.</p>
          <span class="rc-feature-tag">Target: 15–35% depending on scenario</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-check-double"></i></div>
          <h4>Completion rate</h4>
          <p>Of the subscribers who clicked through, what percentage successfully updated their billing information? Completion rate tells you about the experience after the click — friction in your update flow shows up here as drop-off, not in CTR.</p>
          <span class="rc-feature-tag">Target: 60–70% of clicks</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-arrow-trend-down"></i></div>
          <h4>Involuntary churn delta</h4>
          <p>The change in your involuntary churn rate 90 days before vs. 90 days after banner deployment. This is your primary before-and-after signal — it captures the full picture of what banners, dunning, and Account Updater are doing together to reduce payment-related losses.</p>
          <span class="rc-feature-tag">Measure at 90 days</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-coins"></i></div>
          <h4>Revenue saved</h4>
          <p>Subscribers retained through banner interactions × your average revenue per user (ARPU). This translates your CTR and completion numbers into a business impact figure — the metric that makes the case to leadership for continued investment and optimization.</p>
          <span class="rc-feature-tag">Report monthly</span>
        </div>
      </div>
    </div>

    <!-- Section 2: Where to find your data -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-database rc-fa-section"></i> Where to find your data</h2>

      <p>Where you look depends on how you implemented. Some data lives in Recurly regardless of your implementation path — other data you'll need to pull from Recurly Engage or your own analytics system.</p>

      <div class="rc-card-grid rc-card-grid-3col">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-chart-pie"></i></div>
          <h4>Recurly Analytics</h4>
          <p>Available to all merchants. Access from your Recurly admin under Reports. Covers failed transactions by date range, recovered revenue, and subscriber churn rates. This is your source for the involuntary churn delta and revenue saved calculations.</p>
          <span class="rc-feature-tag">All merchants</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-gauge-high"></i></div>
          <h4>Recurly Engage dashboard</h4>
          <p>If you implemented with Recurly Engage, each Payment Failure Guide shows impression count, CTR, and completion rate out of the box. Check the guide dashboard after 24–48 hours to confirm impressions are registering, then revisit weekly.</p>
          <span class="rc-feature-tag">Engage merchants</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-code"></i></div>
          <h4>Your custom analytics</h4>
          <p>If you implemented with webhooks, impression and CTR data lives in whatever system your engineering team built. Reconcile those numbers against Recurly's recovered revenue report to measure end-to-end impact — your system shows the click, Recurly shows the recovery.</p>
          <span class="rc-feature-tag">Webhooks merchants</span>
        </div>
      </div>
    </div>

    <!-- Section 3: 90-day measurement framework -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-calendar-days rc-fa-section"></i> The 90-day measurement framework</h2>

      <p>Banner impact doesn't show up in a single week. Card expiry cycles, billing periods, and churn patterns all operate on timescales of weeks to months — which means 90 days is the minimum window for meaningful signal. Here's how to use each phase.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Days 1–30: Setup validation</h4>
            <p>Confirm that banners are firing correctly before you start measuring performance. Check that <strong>impressions are accumulating</strong> at a rate consistent with your subscriber volume — if impressions are low or zero, something is wrong with your trigger configuration (see troubleshooting below). Verify that <strong>resolved subscribers are no longer seeing the banner</strong>. This phase is about confirming your implementation is healthy, not drawing conclusions about performance.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Days 31–60: Performance monitoring</h4>
            <p>Now you have enough data to look at CTR and completion rates with some confidence. Check CTR weekly and compare it to the targets from Section 1. <strong>If CTR is below 10%</strong>, revisit your messaging — your copy is likely too generic, or your CTA isn't clear enough. <strong>If completion rate is below 50%</strong>, the problem is post-click friction — check your billing update redirect, simplify the form if possible, and consider In-Prompt Billing if you're using Recurly Engage. If both look healthy, you're on track — let the program run.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Days 61–90: Impact measurement</h4>
            <p>Pull your <strong>involuntary churn rate</strong> for this 90-day period and compare it to the same period before banner deployment. This is your delta. Then calculate <strong>revenue saved</strong>: take the number of subscribers who updated billing after a banner interaction and multiply by your ARPU. This gives you a conservative floor for the program's value — conservative because it excludes the silent recoveries handled by Account Updater, which run in parallel. Present both numbers together for the full picture.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Section 4: Troubleshooting -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-screwdriver-wrench rc-fa-section"></i> When a banner underperforms</h2>

      <p>Most banner performance problems fall into one of four categories. Identify which symptom you're seeing, then follow the corresponding fix.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-eye-slash"></i></div>
          <h4>Impressions are very low or zero</h4>
          <p>The trigger isn't firing correctly. For webhooks, check that your server is subscribed to the right events and that your event handler is receiving payloads — check your logs for missed events. For Recurly Engage, verify that the guide is activated and that the Failed Payment segment contains subscribers.</p>
          <span class="rc-feature-tag" style="background:#FF8200;color:#fff;">Check first</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-arrow-pointer"></i></div>
          <h4>CTR is below 10%</h4>
          <p>This is almost always a messaging problem. Add specificity — reference the card last four digits or the renewal date. Sharpen the CTA to a single unambiguous action. Consider switching prompt types: a bottom banner is lower-friction but easier to ignore; a pop-up creates more urgency for high-stakes scenarios like active dunning.</p>
          <span class="rc-feature-tag" style="background:#FF8200;color:#fff;">Messaging issue</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-route"></i></div>
          <h4>High CTR but low completion rate</h4>
          <p>Subscribers are interested but dropping off after the click. Check that your redirect URL points directly to the billing update form — not to the account overview page or a settings hub that requires additional navigation. If you're using Recurly Engage, review whether In-Prompt Billing is available for your setup, since it removes the redirect step entirely.</p>
          <span class="rc-feature-tag" style="background:#FF8200;color:#fff;">Post-click friction</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-bell-slash"></i></div>
          <h4>Banner persists after issue is resolved</h4>
          <p>The dismiss trigger isn't configured. For webhooks, confirm your implementation listens for <code style="background:var(--brightgray);padding:2px 6px;border-radius:4px;font-size:.85em;">invoice.paid</code> or <code style="background:var(--brightgray);padding:2px 6px;border-radius:4px;font-size:.85em;">billing_info.updated</code> events and clears the banner state on receipt. For Recurly Engage, verify the guide exit condition is set to resolve automatically when the payment issue is cleared.</p>
          <span class="rc-feature-tag" style="background:#FF8200;color:#fff;">Implementation gap</span>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip" style="margin-top: 8px;">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>A/B test before drawing conclusions</strong>
          <p>If CTR or completion rate is consistently below target and you've already reviewed your messaging and redirect flow, consider running an A/B test before making larger changes. Small differences in copy or prompt type can produce meaningful differences in performance — and testing lets you confirm what's actually driving the result. Recurly Engage supports A/B testing prompt experiences natively. See the <a href="https://support.recurly.com/hc/en-us/articles/41994337356180-How-Can-I-A-B-Test-Different-Prompt-Experiences-in-Recurly-Engage" target="_blank" rel="noopener noreferrer">A/B testing support article</a> for setup instructions.</p>
        </div>
      </div>
    </div>

    <!-- Path navigation -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-strategy" class="rc-btn-prev">← Strategy &amp; best practices</a>
      <span class="rc-lp-nav-indicator">6 of 7</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-review" class="rc-btn-path">Next: Review &amp; resources →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://recurly.com/research/subscriber-retention-benchmarks/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Subscriber retention benchmarks — Recurly research</a>
        <a href="https://recurly.com/resources/webinar/revenue-recovery-on-demand-video/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-play-circle"></i> Revenue recovery webinar (on-demand)</a>
        <a href="https://support.recurly.com/hc/en-us/articles/41994337356180-How-Can-I-A-B-Test-Different-Prompt-Experiences-in-Recurly-Engage" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> A/B testing prompt experiences in Engage</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/webhook-notifications" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Webhook event reference</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
      </div>
    </div>

    <!-- Footer nav -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Payment banners</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners" class="rc-footer-link">Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-why" class="rc-footer-link">1. Why it matters</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-use-cases" class="rc-footer-link">2. Use cases</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-webhooks" class="rc-footer-link">3. Webhooks setup</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage" class="rc-footer-link">4. Recurly Engage setup</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-strategy" class="rc-footer-link">5. Strategy &amp; best practices</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-tracking" class="rc-footer-link">6. Tracking your impact</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-review" class="rc-footer-link">7. Review &amp; resources</a>
        </div>
        <div class="rc-footer-utility">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
            <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt="Home"> Navigate Home
          </a>
          <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
        </div>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
