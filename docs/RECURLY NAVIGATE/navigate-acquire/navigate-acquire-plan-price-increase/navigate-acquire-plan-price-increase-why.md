---
title: 'Plan Price Increase: Why increase prices'
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

/* GLOBAL CSS IMMUNITY BLOCK */
.rc-guide h1 { border-bottom: none !important; padding-bottom: 0 !important; }
.rc-guide, .rc-guide * { font-family: "Polar", "Helvetica Neue", Helvetica, arial, sans-serif !important; }
/* FA6 font restore — (0,0,2,0) beats wildcard (0,0,1,0); must follow wildcard */
.rc-guide [class^="fa-"],
.rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide .fa-brands,
.rc-guide [class*="fa-brands"] { font-family: "Font Awesome 6 Brands" !important; }

/* NAVIGATE MASTER ARMOR — (0,0,7,1) beats global section 1.1 rule (0,0,6,2).
   All .rc-guide a.[class] overrides must be declared AFTER this block. */
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

.rc-guide {
  --yellow:    #FFD706;
  --orange:    #FF8200;
  --offblack:  #0D0D0B;
  --darkgray:  #32312D;
  --gray:      #807D73;
  --lightgray: #CCC9B8;
  --brightgray:#F1EFE3;
  --offwhite:  #FFFDF2;
  color: #32312D !important;
  background: #ffffff;
}
.rc-guide * { box-sizing: border-box; }

/* ── FONT AWESOME ICON HELPERS ── */
.rc-fa-announce { color: #0D0D0B; font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark  { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: #0D0D0B; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: #0D0D0B; font-size: 1rem; }

/* ── LAYOUT ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Back link — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

/* ── ANNOUNCEMENT BAR ── */
.rc-announce-bar { display: none; background: var(--yellow); color: var(--offblack); align-items: center; justify-content: space-between; padding: 10px 20px; font-size: .88rem; font-weight: 600; border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4; }
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 10px; flex: 1; flex-wrap: wrap; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-announce-link { color: #0D0D0B !important; font-weight: 800; white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; transition: background .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-announce-link:hover { background: rgba(0,0,0,0.20); color: #0D0D0B !important; }

/* ── HERO ── */
.rc-hero { background: linear-gradient(rgba(13,13,11,0.82),rgba(13,13,11,0.82)), url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center; background-color: var(--offblack); background-size: cover; color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0; }
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,215,6,0.20); border: 1px solid rgba(255,215,6,0.45); color: #FFD706; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: var(--lightgray); line-height: 1.6; }
.rc-hero-stats { display: grid; grid-template-columns: repeat(3,1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); line-height: 1.3; }

/* ── NAV — non-sticky, open (Course page) ── */
details.rc-sticky-nav-wrap { position: relative; z-index: 1; background-color: var(--yellow); box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px; border-radius: 12px; border: 1px solid rgba(0,0,0,0.08); overflow: hidden; }
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: .6px; text-transform: uppercase; color: var(--offblack); }
.rc-nav-chevron { font-size: .72rem; color: var(--offblack); opacity: 0.55; line-height: 1; transition: transform .25s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows .3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link { color: #0D0D0B !important; font-weight: 700; font-size: .83rem; letter-spacing: .4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-sticky-link:hover .rc-step-badge { background: var(--yellow); color: var(--offblack); }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }

/* ── CONTENT SECTIONS ── */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* Content stat strip */
.rc-stat-strip { display: grid; grid-template-columns: repeat(3,1fr); background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 0 0 32px; }
.rc-stat-tile { padding: 24px 20px; text-align: center; }
.rc-stat-tile + .rc-stat-tile { border-left: 1px solid var(--lightgray); }
.rc-stat-tile-num { font-size: 2rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 4px; }
.rc-stat-tile-label { font-size: .7rem; font-weight: 700; letter-spacing: .8px; text-transform: uppercase; color: var(--gray); margin-bottom: 10px; }
.rc-stat-tile-context { font-size: .8rem; color: var(--darkgray); line-height: 1.5; padding-top: 10px; border-top: 1px solid var(--brightgray); }

/* Card grid */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: var(--yellow); box-shadow: 0 4px 16px rgba(255,215,6,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; color: var(--offblack); }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }
.rc-feature-tag { display: inline-block; margin-top: 4px; padding: 3px 10px; border-radius: 20px; font-size: .7rem; font-weight: 700; letter-spacing: .5px; background: var(--offblack); color: var(--yellow); width: fit-content; }

/* Plain card */
.rc-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 0 0 20px; }
.rc-card-title { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 10px; display: flex; align-items: center; gap: 8px; }
.rc-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-card p:last-child { margin-bottom: 0; }
.rc-card ul { font-size: .92rem; color: var(--gray); line-height: 1.75; padding-left: 20px; margin: 0; }
.rc-card ul li { margin-bottom: 4px; }
.rc-card ul li strong { color: var(--darkgray); }

/* Callouts */
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

/* ── PATH NAV BUTTONS — (0,0,8,1); hex border values ── */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; text-decoration: none !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; color: #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path { background: #FFD706; color: #0D0D0B !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; transition: all .2s; text-decoration: none !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: #0D0D0B !important; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }

/* ── RESOURCES ── */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--yellow); border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link { color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-decoration-color: #FFD706 !important; text-underline-offset: 3px; }

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
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-stat-strip { grid-template-columns: 1fr; }
  .rc-card-grid { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-back-link">← Back to Acquire</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Announcement bar — add rc-active class before publishing to show -->
    <div class="rc-announce-bar">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Join our CSMs for a live pricing strategy session.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
    </div>

    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Plan price increase
      </div>
      <div class="rc-lp-hero-title"><h1>Why increase prices?</h1></div>
      <p>The business case for a plan price increase — and how to think about timing, magnitude, and value alignment.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">3–8%</div><div class="rc-hero-stat-label">Typical revenue uplift from a price increase</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">~5%</div><div class="rc-hero-stat-label">Average annual SaaS price increase in 2023–24</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">&lt;5%</div><div class="rc-hero-stat-label">Incremental churn for a well-communicated increase</div></div>
      </div>
    </div>

    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase" class="rc-sticky-link">
          Overview
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-why" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Why increase prices?
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-considerations" class="rc-sticky-link">
          <span class="rc-step-badge">2</span> Things to consider
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-how" class="rc-sticky-link">
          <span class="rc-step-badge">3</span> How to execute it
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-communicate" class="rc-sticky-link">
          <span class="rc-step-badge">4</span> How to communicate it
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-impact" class="rc-sticky-link">
          <span class="rc-step-badge">5</span> Tracking impact
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-review" class="rc-sticky-link">
          <span class="rc-step-badge">6</span> Review &amp; resources
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-chart-line rc-fa-section"></i> The business case</h2>
      <p>Raising prices is one of the highest-leverage actions a subscription business can take — and one of the most avoided. The hesitation is understandable: you've built a relationship with your subscribers, and a price increase feels like a risk to that relationship. In reality, the bigger risk is leaving revenue on the table while your product matures and your costs grow.</p>

      <div class="rc-stat-strip">
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">3–8%</div>
          <div class="rc-stat-tile-label">Revenue uplift</div>
          <div class="rc-stat-tile-context">A modest price increase applied across your subscriber base compounds into significant MRR growth — with no additional CAC.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">&lt;5%</div>
          <div class="rc-stat-tile-label">Incremental churn</div>
          <div class="rc-stat-tile-context">Subscribers who find genuine value in your product rarely leave over a reasonable price increase — especially when it's communicated well.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">2x</div>
          <div class="rc-stat-tile-label">Revenue impact vs. acquisition</div>
          <div class="rc-stat-tile-context">Revenue from a price increase is nearly twice as efficient as adding new subscribers, because there's no acquisition cost attached.</div>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-bullseye rc-fa-section"></i> Common reasons to raise prices</h2>
      <p>A price increase is justified when the value you deliver has grown — or when your current pricing no longer reflects the market. Here are the most common triggers.</p>
      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-rocket"></i></div>
          <h4>Significant product improvements</h4>
          <p>You've shipped major features, integrations, or performance improvements since your current price was set. Your subscribers are getting more — the price should reflect it.</p>
          <span class="rc-feature-tag">Most common</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-chart-bar"></i></div>
          <h4>Costs have risen</h4>
          <p>Infrastructure, payment processing, compliance, or support costs have grown. Your pricing needs to maintain healthy unit economics as you scale.</p>
          <span class="rc-feature-tag">Operational</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-tag"></i></div>
          <h4>Market repositioning</h4>
          <p>You've moved upmarket, added enterprise features, or your competitive set has repriced. Staying at launch-era pricing signals the wrong tier to prospects.</p>
          <span class="rc-feature-tag">Strategic</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-arrows-rotate"></i></div>
          <h4>Legacy plans drifted from market rate</h4>
          <p>Long-tenure subscribers on old plans may be paying 30–50% less than newer subscribers. A structured migration brings them into alignment without dramatic jumps.</p>
          <span class="rc-feature-tag">Equity</span>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-calculator rc-fa-section"></i> How much should you increase?</h2>
      <p>There's no universal answer, but there are useful anchors. The goal is a price that reflects value without triggering meaningful churn.</p>

      <div class="rc-card">
        <div class="rc-card-title"><i class="fa-solid fa-sliders rc-fa-section"></i> Common increase ranges</div>
        <ul>
          <li><strong>5–10%:</strong> The safe zone for most subscription businesses. Corresponds roughly to inflation + incremental value. Low churn risk.</li>
          <li><strong>10–20%:</strong> Appropriate when you've shipped substantial product improvements or are repositioning upmarket. Expect some pushback; communication becomes more important.</li>
          <li><strong>20%+:</strong> Reserved for cases where pricing was significantly below market, or a major product transformation warrants it. Use grandfathering strategically and give subscribers more lead time.</li>
        </ul>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>Test before you migrate everyone</strong>
          <p>If you have a large subscriber base, consider migrating a cohort first — new subscribers at the new price, or a segment of long-tenure subscribers — before a full rollout. A few weeks of renewal data at the new price gives you real churn signal before you commit at scale.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon"><i class="fa-solid fa-triangle-exclamation"></i></div>
        <div class="rc-callout-body">
          <strong>Avoid "shock" increases</strong>
          <p>Jumps above 25–30% in a single cycle carry meaningful churn risk, especially for monthly plans where the pain is felt immediately. If you need to close a large pricing gap, consider a phased approach — one increase now, another in 12–18 months.</p>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-comment rc-fa-section"></i> Framing it for subscribers</h2>
      <p>Subscribers don't need to love a price increase — they need to understand it. The framing matters as much as the number.</p>

      <div class="rc-card">
        <div class="rc-card-title"><i class="fa-solid fa-circle-check rc-fa-section"></i> What works</div>
        <ul>
          <li><strong>Lead with value delivered:</strong> List specific features, improvements, or capabilities that have shipped since their subscription started. Make the case before announcing the number.</li>
          <li><strong>Be specific about the new price:</strong> Tell them exactly what they'll pay at their next renewal. Ambiguity creates anxiety.</li>
          <li><strong>Acknowledge the ask:</strong> A one-sentence recognition that you understand this is a change goes a long way. It doesn't have to be an apology.</li>
          <li><strong>Give them enough notice:</strong> 30 days minimum for monthly plans; 60–90 days for annual.</li>
        </ul>
      </div>

      <div class="rc-card">
        <div class="rc-card-title"><i class="fa-solid fa-circle-xmark rc-fa-section"></i> What to avoid</div>
        <ul>
          <li><strong>Vague value language:</strong> "We've been working hard to improve your experience" lands hollow. Be specific.</li>
          <li><strong>Burying the price:</strong> Don't put the new amount at the bottom of a long email. Lead with context, then state the number clearly.</li>
          <li><strong>Over-apologizing:</strong> It signals that you don't believe the increase is fair. If you've built genuine value, own it.</li>
        </ul>
      </div>
    </div>

    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase" class="rc-btn-prev">← Overview</a>
      <span class="rc-lp-nav-indicator">1 of 6</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-considerations" class="rc-btn-path">Next: Things to consider →</a>
    </div>

    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/docs/plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Plans</a>
        <a href="https://docs.recurly.com/docs/subscriptions" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Subscriptions</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
      </div>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Plan price increase</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase" class="rc-footer-link">Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-why" class="rc-footer-link">1. Why increase prices?</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-considerations" class="rc-footer-link">2. Things to consider</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-how" class="rc-footer-link">3. How to execute it</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-communicate" class="rc-footer-link">4. How to communicate it</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-impact" class="rc-footer-link">5. Tracking impact</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-review" class="rc-footer-link">6. Review &amp; resources</a>
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