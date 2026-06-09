---
title: 'Add-ons: Overview'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
/* ── HOST-THEME BACKGROUND OVERRIDE ── */
body { background: #ffffff !important; }

/* ── GLOBAL CSS IMMUNITY BLOCK ── */
/* G-2: Hero h1 yellow underline */
.rc-guide h1 { border-bottom: none !important; padding-bottom: 0 !important; }
/* G-1: Polar font — wildcard ensures all descendants use it */
.rc-guide, .rc-guide * { font-family: "Polar", "Helvetica Neue", Helvetica, arial, sans-serif !important; }
/* FA6 font restore — (0,0,2,0) beats wildcard (0,0,1,0); must follow wildcard */
.rc-guide [class^="fa-"],
.rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide .fa-brands,
.rc-guide [class*="fa-brands"] { font-family: "Font Awesome 6 Brands" !important; }

/* ── NAVIGATE MASTER ARMOR ── (0,0,7,1) beats global section 1.1 rule (0,0,6,2)
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

/* ── FA6 ICON HELPERS ── */
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
.rc-announce-bar { display: none; background: #FFD706; color: #0D0D0B; align-items: center; justify-content: space-between; padding: 10px 20px; font-size: .88rem; font-weight: 600; border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4; }
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 10px; flex: 1; flex-wrap: wrap; }
/* Announce link — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-announce-link { color: #0D0D0B !important; font-weight: 800; white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; transition: background 0.2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-announce-link:hover { background: rgba(0,0,0,0.20); color: #0D0D0B !important; }

/* ── HERO ── */
.rc-hero { background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)), url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center; background-color: #0D0D0B; background-size: cover; color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0; }
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,215,6,0.20); border: 1px solid rgba(255,215,6,0.45); color: #FFD706; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: #FFFDF2; margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: #CCC9B8; line-height: 1.6; }
.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: #FFD706; line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: #CCC9B8; line-height: 1.3; }

/* ── NAV — non-sticky, open by default (Micro-Path) ── */
details.rc-sticky-nav-wrap { position: relative; z-index: 1; background-color: var(--yellow); box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px; border-radius: 12px; border: 1px solid rgba(0,0,0,0.08); overflow: hidden; }
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
.rc-guide a.rc-sticky-link { color: #0D0D0B !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
/* Hover: semi-transparent overlay, text stays offblack */
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
/* Badge inverts on hover so it stays visible against the darker overlay */
.rc-guide a.rc-sticky-link:hover .rc-step-badge { background: var(--yellow); color: var(--offblack); }
/* Active item — no persistent background; map pin icon identifies current page */
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }

/* ── CONTENT SECTIONS ── */
.rc-lp-section { margin-bottom: 52px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }
.rc-lp-section p:last-child { margin-bottom: 0; }

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
/* Callout inline links — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-callout-body a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide .rc-callout-body a:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* ── CARD GRID — 2-col ── */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: var(--yellow); box-shadow: 0 4px 16px rgba(255,215,6,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; color: var(--offblack); }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }
.rc-feature-tag { display: inline-block; margin-top: 4px; padding: 3px 10px; border-radius: 20px; font-size: .7rem; font-weight: 700; letter-spacing: .5px; background: var(--offblack); color: var(--yellow); width: fit-content; }

/* ── STAT STRIP (content) — uses pillar color (#FFD706 = Acquire) for numbers ── */
.rc-stat-strip { display: grid; grid-template-columns: repeat(3, 1fr); background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 0 0 32px; }
.rc-stat-tile { padding: 24px 20px; text-align: center; }
.rc-stat-tile + .rc-stat-tile { border-left: 1px solid var(--lightgray); }
.rc-stat-tile-num { font-size: 2rem; font-weight: 800; color: #FFD706; line-height: 1; margin-bottom: 4px; }
.rc-stat-tile-label { font-size: .7rem; font-weight: 700; letter-spacing: .8px; text-transform: uppercase; color: var(--gray); margin-bottom: 10px; }
.rc-stat-tile-context { font-size: .8rem; color: var(--darkgray); line-height: 1.5; padding-top: 10px; border-top: 1px solid var(--brightgray); }

/* ── COMPARE GRID ── */
.rc-compare-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-compare-card { border-radius: 12px; padding: 24px; border: 1px solid var(--lightgray); background: var(--offwhite); }
.rc-compare-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 16px; }
.rc-compare-card ul { list-style: none; padding: 0; margin: 0; display: flex; flex-direction: column; gap: 10px; }
.rc-compare-card ul li { font-size: .88rem; color: var(--darkgray); line-height: 1.5; padding-left: 20px; position: relative; }
.rc-compare-card ul li::before { content: '→'; position: absolute; left: 0; color: var(--yellow); font-weight: 800; font-size: .8rem; }
.rc-compare-label { display: inline-block; font-size: .68rem; font-weight: 800; letter-spacing: .8px; text-transform: uppercase; padding: 3px 10px; border-radius: 20px; margin-bottom: 14px; }
.rc-compare-label-plan { background: rgba(255,215,6,0.15); color: #7a6500; }
.rc-compare-label-catalog { background: rgba(13,13,11,0.08); color: var(--offblack); }

/* ── PATH NAV BUTTONS — (0,0,8,1) ── */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-btn-start { background: var(--brightgray); color: var(--gray); padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid var(--lightgray); cursor: default; display: inline-flex; align-items: center; }
/* Prev button — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path { background: var(--yellow); color: #0D0D0B !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: #0D0D0B !important; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }

/* ── RESOURCES ── */
.rc-resources { background: var(--brightgray); border-left: 4px solid #FFD706; border-radius: 10px; padding: 20px 24px; margin: 48px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
/* Resource links — (0,0,8,1); hex colors required */
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link { color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-decoration-color: #FFD706 !important; text-underline-offset: 3px !important; }

/* ── FOOTER NAV ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
/* Footer links — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link { color: #807D73 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-footer-link:hover { color: #FF8200 !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-guide a.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-card-grid { grid-template-columns: 1fr; }
  .rc-compare-grid { grid-template-columns: 1fr; }
  .rc-stat-strip { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-back-link">← Back to Path Start</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Announcement bar (hidden — add rc-active to show) -->
    <div class="rc-announce-bar">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Join our CSMs for a live Pricing &amp; Packaging Q&amp;A.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
    </div>

    <!-- Hero -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Pricing &amp; Plans 101
      </div>
      <div class="rc-lp-hero-title"><h1>Add-Ons</h1></div>
      <p>Add-ons are how you grow revenue beyond the base subscription. They let you package your product flexibly, upsell at the right moment, and give subscribers control over what they pay for.</p>
     
    </div>

    <!-- Navigation Menu — non-sticky, open on load (Micro-Path) -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <!-- Navigate Home — always first; black home icon on Acquire (yellow/light nav) -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <!-- Active page: black map pin replaces step badge; no badge shown -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Add-Ons: Overview
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons-configure" class="rc-sticky-link"><span class="rc-step-badge">2</span> Add-Ons: Configure</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons-strategy" class="rc-sticky-link"><span class="rc-step-badge">3</span> Add-Ons: Strategy</a>
        <!-- Back to Path Start — always last on Micro-Path; circle arrow icon -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- What are add-ons -->
    <div class="rc-lp-section" id="what-are-addons">
      <h2><i class="fa-solid fa-puzzle-piece rc-fa-section"></i> What are add-ons in Recurly?</h2>
      <p>An add-on is an additional charge billed alongside a subscription's base recurring charge. Where your plan defines the core billing relationship — what the subscriber pays every period — add-ons let you layer on extra charges for additional products, features, services, or usage that not every subscriber needs.</p>
      <p>This distinction matters strategically: add-ons give you a way to <strong>keep your base plan price accessible</strong> while monetising more from subscribers who want more. They're the primary mechanism for packaging flexibility, upsell revenue, and hybrid billing models in Recurly.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-box-open"></i></div>
          <h4>Optional add-ons</h4>
          <p>Subscriber-controlled extras — premium support tiers, additional seats, storage upgrades, or feature unlocks. Subscribers can add or remove these themselves on their Recurly Hosted Account page.</p>
          <span class="rc-feature-tag">Upsell</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-lock"></i></div>
          <h4>Required add-ons</h4>
          <p>Charges that are mandatory on a plan — onboarding fees, hardware costs, or compliance services that cannot be decoupled from the subscription. Subscribers cannot remove these.</p>
          <span class="rc-feature-tag">Mandatory</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-ruler-combined"></i></div>
          <h4>Fixed vs. quantity-based</h4>
          <p>Add-ons can be a flat recurring charge or quantity-based — billed per seat, per unit, or per usage interval. Editable quantity options let subscribers self-serve within configured limits.</p>
          <span class="rc-feature-tag">Flexible billing</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-chart-bar"></i></div>
          <h4>Usage-based add-ons</h4>
          <p>Metered billing for what subscribers actually consume — API calls, messages sent, GB stored. Usage records are logged via API and billed in arrears at the end of the billing period.</p>
          <span class="rc-feature-tag">Metered</span>
        </div>
      </div>
    </div>

    <!-- Plan-specific vs Item Catalog -->
    <div class="rc-lp-section" id="plan-vs-catalog">
      <h2><i class="fa-solid fa-layer-group rc-fa-section"></i> Plan-specific add-ons vs. the Item Catalog</h2>
      <p>Before you create an add-on, the most important decision is whether to build it directly on a plan or through the Item Catalog. This choice has real downstream consequences for your billing operations, reporting, and rev rec.</p>

      <div class="rc-stat-strip">
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">Plan-level</div>
          <div class="rc-stat-tile-label">Plan-specific add-ons</div>
          <div class="rc-stat-tile-context">Created directly on a plan. Only available on that specific plan. Simpler to set up but creates duplication if the same add-on is sold across multiple plans.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">Catalog</div>
          <div class="rc-stat-tile-label">Item Catalog add-ons</div>
          <div class="rc-stat-tile-context">Created once in the Item Catalog, then associated with multiple plans. Consistent accounting codes, tax settings, and rev rec treatment across your entire product.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">Both</div>
          <div class="rc-stat-tile-label">Can coexist</div>
          <div class="rc-stat-tile-context">Plans can have a mix of plan-specific and catalog-based add-ons. You don't have to choose one approach for your entire catalog.</div>
        </div>
      </div>

      <div class="rc-compare-grid">
        <div class="rc-compare-card">
          <div class="rc-compare-label rc-compare-label-plan">Plan-specific add-on</div>
          <h4>Best when</h4>
          <ul>
            <li>The add-on is truly unique to one plan</li>
            <li>You're prototyping and want to iterate quickly</li>
            <li>You have a small number of plans and add-ons</li>
            <li>You don't need consistent accounting codes across plans</li>
            <li>The add-on won't be sold in other contexts</li>
          </ul>
        </div>
        <div class="rc-compare-card">
          <div class="rc-compare-label rc-compare-label-catalog">Item Catalog add-on</div>
          <h4>Best when</h4>
          <ul>
            <li>The same add-on is sold on multiple plans (e.g., extra seats)</li>
            <li>You need consistent tax treatment across your product</li>
            <li>You're integrating with a rev rec or ERP system</li>
            <li>You want clean, queryable data for analytics and exports</li>
            <li>You're building a scalable catalog at the start</li>
          </ul>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>Default recommendation: start with the Item Catalog</strong>
          <p>Even if you only have one plan today, building add-ons through the Item Catalog gives you a cleaner foundation as your product grows. The extra 2 minutes at setup will save hours of cleanup when you add your second plan.</p>
        </div>
      </div>
    </div>

    <!-- Add-on pricing models -->
    <div class="rc-lp-section" id="pricing-models">
      <h2><i class="fa-solid fa-sliders rc-fa-section"></i> Add-on pricing models</h2>
      <p>Unlike base plans — which support Fixed and Ramp pricing — add-ons support four distinct pricing models. The model you choose determines how the add-on charge is calculated each billing period.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-dollar-sign"></i></div>
          <h4>Fixed</h4>
          <p>A flat charge per billing period, regardless of quantity or usage. Best for feature unlocks, premium support tiers, or access-based charges where the value is binary — you have it or you don't.</p>
          <span class="rc-feature-tag">Flat rate</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-chart-line"></i></div>
          <h4>Tiered</h4>
          <p>Price per unit changes based on which tier the quantity falls into. Each unit is charged at the rate for its tier. Best for seat-based models where pricing becomes more competitive at volume.</p>
          <span class="rc-feature-tag">Volume incentive</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-boxes-stacked"></i></div>
          <h4>Volume</h4>
          <p>The entire quantity is charged at the rate for the tier it falls into — all units get the same price. Best for commodity billing where you want simple, single-rate pricing at each volume band.</p>
          <span class="rc-feature-tag">Single rate</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-stairs"></i></div>
          <h4>Stairstep</h4>
          <p>Subscriber pays a flat fee for a quantity range — not per unit. Moving to the next range bumps the entire charge to that band's flat fee. Best for seat bundles (e.g., 1–5 users = $50/mo, 6–10 = $90/mo).</p>
          <span class="rc-feature-tag">Bundle pricing</span>
        </div>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon"><i class="fa-solid fa-circle-info"></i></div>
        <div class="rc-callout-body">
          <strong>Tiered, Volume, and Stairstep are add-on-only</strong>
          <p>These three pricing models are configured on add-ons, not on the base plan. If you want usage-incentivised or seat-bundle pricing as part of your subscription, you'll build it as an add-on — even if it's a required one. The base plan itself only supports Fixed and Ramp.</p>
        </div>
      </div>
    </div>

    <!-- Path nav -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-configure" class="rc-btn-prev">← Plans</a>
      <span class="rc-lp-nav-indicator">1 of 3 · Add-Ons</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons-configure" class="rc-btn-path">Next: How to configure →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/add-ons" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Add-Ons</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/item-catalog" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Item Catalog</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/-tiered-stairstep-and-volume-pricing" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Tiered, Stairstep &amp; Volume Pricing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/usage-based-pricing-guide" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Usage-Based Billing</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Support</a>
      </div>
    </div>

    <!-- Footer — grouped section structure -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Add-Ons</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-footer-link">Add-Ons: Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons-configure" class="rc-footer-link">Add-Ons: Configure</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons-strategy" class="rc-footer-link">Add-Ons: Strategy &amp; best practices</a>
        </div>
        <div class="rc-footer-section">
          <span class="rc-footer-label">Pricing &amp; Plans 101</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-footer-link">Pricing &amp; Plans 101: Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-footer-link">Plans</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-footer-link">Currency</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-footer-link">Pricing models</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-footer-link">Trials</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-footer-link">Analytics</a>
        </div>
        <div class="rc-footer-utility">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
            <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
          </a>
          <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
        </div>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
