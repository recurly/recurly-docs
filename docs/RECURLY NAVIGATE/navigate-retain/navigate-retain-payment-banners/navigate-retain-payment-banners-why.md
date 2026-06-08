---
title: 'Payment Banners: Why it matters '
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

/* ── NAVIGATE MASTER ARMOR — (0,0,7,1) beats global rule (0,0,6,2) ── */
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
  --yellow:    #FFD706;
  --orange:    #FF8200;
  --offblack:  #0D0D0B;
  --darkgray:  #32312D;
  --gray:      #807D73;
  --lightgray: #CCC9B8;
  --brightgray:#F1EFE3;
  --offwhite:  #FFFDF2;
  --retain:    #FF9D88;
  color: #32312D !important;
  background: #ffffff;
}

/* ── FONT AWESOME ICON HELPERS ── */
.rc-fa-announce { color: var(--offblack); font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark  { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: var(--offblack); font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: var(--offblack); font-size: 1rem; }

/* ── LAYOUT ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Back link — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

/* ── ANNOUNCEMENT BAR (hidden by default) ── */
.rc-announce-bar { display: none; background: var(--offblack); padding: 10px 40px; align-items: center; justify-content: center; gap: 12px; flex-wrap: wrap; }
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-bar p { color: var(--lightgray); font-size: .85rem; margin: 0; line-height: 1.5; }
.rc-announce-bar p strong { color: var(--yellow); }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-announce-link { color: #0D0D0B !important; background: var(--yellow); padding: 5px 14px; border-radius: 6px; font-size: .82rem; font-weight: 700; border-bottom: 0 !important; transition: opacity .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-announce-link:hover { opacity: .85; }

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
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto; color: var(--lightgray); line-height: 1.6; }

/* ── NAV — non-sticky, open (Course pages) ── */
details.rc-sticky-nav-wrap {
  position: relative; z-index: 1;
  background-color: var(--retain);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px; border-radius: 12px;
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

/* Nav links — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link {
  color: #0D0D0B !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px;
  text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s;
  white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }

/* ── CONTENT SECTIONS ── */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section > p { font-size: .97rem; line-height: 1.7; color: var(--darkgray); margin: 0 0 20px; }

/* ── CONTENT STAT STRIP ── */
.rc-stat-strip { display: grid; grid-template-columns: repeat(2, 1fr); background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 0 0 28px; }
.rc-stat-tile { padding: 24px 20px; text-align: center; }
.rc-stat-tile + .rc-stat-tile { border-left: 1px solid var(--lightgray); }
.rc-stat-tile-num { font-size: 2rem; font-weight: 800; color: var(--retain); line-height: 1; margin-bottom: 4px; }
.rc-stat-tile-label { font-size: .7rem; font-weight: 700; letter-spacing: .8px; text-transform: uppercase; color: var(--gray); margin-bottom: 10px; }
.rc-stat-tile-context { font-size: .8rem; color: var(--darkgray); line-height: 1.5; padding-top: 10px; border-top: 1px solid var(--brightgray); }

/* ── CALLOUTS ── */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout + .rc-callout { margin-top: 12px; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body > strong { color: var(--offblack); }
.rc-callout-warning { background: rgba(255,215,6,0.12); border-left: 4px solid var(--yellow); }
.rc-callout-warning .rc-callout-body > strong { color: var(--darkgray); }
/* Callout inline links */
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-callout-body a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide .rc-callout-body a:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* ── FEATURE CARD GRIDS ── */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 28px; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: #FF9D88; box-shadow: 0 4px 16px rgba(255,157,136,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; color: var(--offblack); }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }

/* ── INTERACTIVE CHECKLIST — Pure CSS (no JS) ── */
.rc-checklist { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 20px 0 0; }
.rc-checklist-header { padding: 14px 22px; background: var(--offblack); display: flex; align-items: center; gap: 10px; }
.rc-checklist-header h4 { font-size: .82rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: var(--yellow); margin: 0; }
.rc-checklist-item { padding: 14px 22px; border-bottom: 1px solid var(--brightgray); display: flex; align-items: flex-start; gap: 14px; transition: background .15s; cursor: pointer; }
.rc-checklist-item:last-child { border-bottom: none; }
.rc-checklist-item:hover { background: var(--brightgray); }
.rc-checklist-item input[type="checkbox"] { position: absolute; opacity: 0; width: 0; height: 0; pointer-events: none; }
.rc-checkbox-box { width: 22px; height: 22px; border-radius: 6px; border: 2px solid var(--lightgray); flex-shrink: 0; background: #fff; display: flex; align-items: center; justify-content: center; transition: all .18s; margin-top: 1px; }
.rc-checklist-item input[type="checkbox"]:checked + .rc-checkbox-box { background: var(--offblack); border-color: var(--offblack); }
.rc-checklist-item input[type="checkbox"]:checked + .rc-checkbox-box::after { content: '✓'; color: var(--yellow); font-size: .75rem; font-weight: 800; line-height: 1; }
.rc-checklist-item input[type="checkbox"]:checked ~ .rc-checklist-text strong { text-decoration: line-through; color: var(--gray); }
.rc-checklist-item:has(input[type="checkbox"]:checked) { background: rgba(255,157,136,0.06); }
.rc-checklist-text { flex: 1; }
.rc-checklist-text strong { font-size: .9rem; font-weight: 700; color: var(--offblack); display: block; margin-bottom: 2px; transition: color .18s; }
.rc-checklist-text span { font-size: .8rem; color: var(--gray); line-height: 1.4; display: block; }

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
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path {
  background: #FFD706; color: #0D0D0B !important; text-decoration: none !important;
  padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem;
  display: inline-flex; align-items: center; gap: 8px; transition: all .2s;
  border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
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
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-decoration-color: #FF9D88 !important; }

/* ── FOOTER NAV ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link { color: #807D73 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-footer-link:hover { color: #FF8200 !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-stat-strip { grid-template-columns: 1fr; }
  .rc-stat-tile + .rc-stat-tile { border-left: none; border-top: 1px solid var(--lightgray); }
  .rc-card-grid { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">

  <!-- Announcement bar (hidden — toggle rc-active to show) -->
  <div class="rc-announce-bar">
    <p><strong>New:</strong> Office Hours sessions run weekly for all Recurly customers.</p>
    <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
  </div>

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
        <h1>Why it matters</h1>
      </div>
      <p>Involuntary churn is silent, costly, and largely preventable. Understanding its scale is the first step to stopping it.</p>
    </div>

    <!-- Nav: non-sticky, open. Active: page 1 -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners" class="rc-sticky-link">Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-why" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Why it matters
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-use-cases" class="rc-sticky-link"><span class="rc-step-badge">2</span> Use cases</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-webhooks" class="rc-sticky-link"><span class="rc-step-badge">3</span> Webhooks setup</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage" class="rc-sticky-link"><span class="rc-step-badge">4</span> Recurly Engage setup</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-strategy" class="rc-sticky-link"><span class="rc-step-badge">5</span> Strategy &amp; best practices</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-tracking" class="rc-sticky-link"><span class="rc-step-badge">6</span> Tracking your impact</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-review" class="rc-sticky-link"><span class="rc-step-badge">7</span> Review &amp; resources</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- Section 1: The business problem -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-chart-line rc-fa-section"></i> What involuntary churn is costing you</h2>

      <p>More than half of subscriber losses aren't intentional cancellations — they're payment failures that went unresolved before the next billing cycle. These are engaged subscribers whose payment method failed, and without an in-session intervention, the subscription lapses.</p>

      <p>Dunning emails reach part of your at-risk base. Payment banners close the gap for subscribers dunning emails miss: those who are still active in your product but haven't opened your billing emails.</p>

      <div class="rc-stat-strip">
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">53%</div>
          <div class="rc-stat-tile-label">Of subscriber losses are involuntary</div>
          <div class="rc-stat-tile-context">More than half of all churn is payment failure — not intentional cancellations. (Recurly Retention Benchmarks)</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">7.2%</div>
          <div class="rc-stat-tile-label">At risk every billing cycle</div>
          <div class="rc-stat-tile-context">On average, 7.2% of your subscriber base is at risk of involuntary churn each month. (Recurly Retention Benchmarks)</div>
        </div>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon"><i class="fa-solid fa-circle-info"></i></div>
        <div class="rc-callout-body">
          <strong>Why email alone isn't enough</strong>
          <p>Dunning emails depend on the subscriber opening their inbox. The gap between your email open rate and full coverage is your payment banner opportunity — subscribers you can reach in-session while they're already inside your product.</p>
        </div>
      </div>
    </div>

    <!-- Section 2: What payment banners add -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-shield-halved rc-fa-section"></i> What payment banners add to your retention stack</h2>

      <p>Payment banners work alongside dunning and Account Updater — each layer handles what the others can't reach.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-shield-halved"></i></div>
          <h4>Reach subscribers email misses</h4>
          <p>A subscriber who logs in daily but hasn't opened a billing email in months is reachable by a banner — regardless of how well-written the dunning sequence is.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-bolt"></i></div>
          <h4>Fire early in the dunning window</h4>
          <p>Payment banners surface while the subscriber is still active and before the subscription lapses. Resolving a payment at this stage costs far less than winning back a churned subscriber.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-rotate"></i></div>
          <h4>Reinforce dunning in-session</h4>
          <p>Most merchants allow product access during dunning, so subscribers in an active dunning window are still logging in. A banner gives them a second touchpoint where they're already engaged.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-heart"></i></div>
          <h4>Let subscribers self-resolve</h4>
          <p>Banners give subscribers a direct path to fix their payment method themselves, reducing support tickets and turning a friction point into a service moment.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>Account Updater and payment banners are stronger together</strong>
          <p><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" target="_blank" rel="noopener noreferrer">Account Updater</a> silently resolves eligible card credential issues — expired cards, reissued numbers — with no subscriber action required. Payment banners handle what Account Updater can't: closed accounts, insufficient funds, or anything that requires the subscriber to step in. Together, they cover the full range of payment failure scenarios.</p>
        </div>
      </div>

      <h3 style="font-size:1rem;font-weight:800;color:var(--offblack);margin:28px 0 4px;">Quick fit check</h3>
      <p style="font-size:.92rem;color:var(--gray);margin:0 0 12px;">Each item below is a signal that payment banners would add real value for your business.</p>

      <div class="rc-checklist">
        <div class="rc-checklist-header">
          <i class="fa-solid fa-list-check" style="color: var(--yellow); font-size: 1rem;"></i>
          <h4>Quick fit check</h4>
        </div>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Subscribers log into your app or portal regularly</strong>
            <span>More sessions means more opportunities for a banner to fire at the right moment.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>You're seeing involuntary churn from expired or declined cards</strong>
            <span>Payment banners directly address this failure mode at the in-session level.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Your dunning email engagement has plateaued or declined</strong>
            <span>Banners provide recovery coverage that doesn't depend on inbox behavior.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>You have annual subscribers approaching renewal</strong>
            <span>Annual renewals represent concentrated revenue risk — proactive banners are especially valuable here.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>You want subscribers to self-resolve billing issues</strong>
            <span>Banners let subscribers fix problems themselves, reducing support tickets and team interruptions.</span>
          </div>
        </label>
      </div>
    </div>

    <!-- Path navigation -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners" class="rc-btn-prev">← Payment banners</a>
      <span class="rc-lp-nav-indicator">1 of 7</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-use-cases" class="rc-btn-path">Next: Use cases →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://recurly.com/blog/dunning/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> All about dunning — Recurly blog</a>
        <a href="https://recurly.com/research/subscriber-retention-benchmarks/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Subscriber retention benchmarks</a>
        <a href="https://support.recurly.com/hc/en-us/articles/44224955931924-What-Are-the-Best-Practices-for-Initial-and-Recurring-Payment-Failure-Recovery" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Best practices for payment failure recovery</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Account Updater learning path</a>
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
