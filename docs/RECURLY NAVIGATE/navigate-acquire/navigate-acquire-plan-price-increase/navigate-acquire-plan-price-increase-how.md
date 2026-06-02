---
title: 'Plan Price Increase: How to execute it'
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
/* G-1: Polar font — wildcard ensures all descendants */
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
  font-family: "Polar", "Helvetica Neue", Helvetica, arial, sans-serif !important;
  color: #32312D !important;
  background: #ffffff;
}
.rc-guide * { box-sizing: border-box; }

/* ── FA6 ICON HELPERS ── */
.rc-fa-announce { color: #0D0D0B; font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark  { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: #0D0D0B; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: #0D0D0B; font-size: 1rem; }

/* ── TOP NAV ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* ── ANNOUNCEMENT BAR ── */
.rc-announce-bar { display: none; background: #FFD706; color: #0D0D0B; align-items: center; justify-content: space-between; padding: 10px 20px; font-size: .88rem; font-weight: 600; border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4; }
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

/* Phase label */
.rc-phase-label { display: inline-block; background: var(--offblack); color: var(--yellow); font-size: .7rem; font-weight: 800; letter-spacing: .7px; text-transform: uppercase; padding: 4px 10px; border-radius: 6px; margin-bottom: 12px; }

/* ── STEPS ── */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 0 0 24px; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0; }
.rc-step-content strong { color: var(--darkgray); }
.rc-step-content code { background: var(--brightgray); color: var(--offblack); padding: 2px 7px; border-radius: 4px; font-size: .82rem; }
.rm-Markdown.markdown-body .rc-guide .rc-step-content a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-step-content a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide .rc-step-content a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide .rc-step-content a:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* ── CALLOUTS ── */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout + .rc-callout { margin-top: 12px; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body > strong { color: var(--offblack); }
.rc-callout-caution { background: rgba(255,130,0,0.08); border-left: 4px solid var(--orange); }
.rc-callout-caution .rc-callout-body > strong { color: var(--darkgray); }
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-callout-body a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide .rc-callout-body a:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* ── CARD ── */
.rc-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 0 0 20px; }
.rc-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-card p:last-child { margin-bottom: 0; }
.rc-card ul { font-size: .92rem; color: var(--gray); line-height: 1.75; padding-left: 20px; margin: 0; }
.rc-card ul li { margin-bottom: 6px; }
.rc-card ul li strong { color: var(--darkgray); }

/* ── PATH NAV BUTTONS ── */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path { background: var(--yellow); color: #0D0D0B !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: #0D0D0B !important; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }

/* ── RESOURCES ── */
.rc-resources { background: var(--brightgray); border-left: 4px solid #FFD706; border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link { color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FFD706 !important; }

/* ── FOOTER ── */
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

/* ── CHECKLIST ── */
.rc-checklist { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 20px 0 32px; }
.rc-checklist-header { padding: 14px 22px; background: var(--offblack); display: flex; align-items: center; gap: 10px; }
.rc-checklist-header h4 { font-size: .82rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: var(--yellow); margin: 0; }
.rc-checklist-item { padding: 14px 22px; border-bottom: 1px solid var(--brightgray); display: flex; align-items: flex-start; gap: 14px; transition: background .15s; cursor: pointer; }
.rc-checklist-item:last-of-type { border-bottom: none; }
.rc-checklist-item:hover { background: var(--brightgray); }
.rc-checklist-item input[type="checkbox"] { position: absolute; opacity: 0; width: 0; height: 0; pointer-events: none; }
.rc-checkbox-box { width: 22px; height: 22px; border-radius: 6px; border: 2px solid var(--lightgray); flex-shrink: 0; background: #fff; display: flex; align-items: center; justify-content: center; transition: all .18s; margin-top: 1px; }
.rc-checklist-item input[type="checkbox"]:checked + .rc-checkbox-box { background: var(--offblack); border-color: var(--offblack); }
.rc-checklist-item input[type="checkbox"]:checked + .rc-checkbox-box::after { content: '✓'; color: var(--yellow); font-size: .75rem; font-weight: 800; line-height: 1; }
.rc-checklist-item input[type="checkbox"]:checked ~ .rc-checklist-text strong { text-decoration: line-through; color: var(--gray); }
.rc-checklist-item:has(input[type="checkbox"]:checked) { background: rgba(255,215,6,0.06); }
.rc-checklist-text { flex: 1; }
.rc-checklist-text strong { font-size: .9rem; font-weight: 700; color: var(--offblack); display: block; margin-bottom: 2px; transition: color .18s; }
.rc-checklist-text span { font-size: .8rem; color: var(--gray); line-height: 1.4; display: block; }
.rc-checklist-footer { padding: 10px 22px; background: var(--brightgray); border-top: 1px solid var(--lightgray); font-size: .78rem; color: var(--gray); font-weight: 600; }

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-back-link">← Back to Acquire</a>
  </div>
  <div class="rc-content-wrap">

    <div class="rc-announce-bar">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Join our CSMs for a live pricing strategy session.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
    </div>

    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Plan Price Increase
      </div>
      <div class="rc-lp-hero-title"><h1>How to execute it</h1></div>
      <p>Two distinct actions: update the plan price, then migrate existing subscribers. Here's exactly how to do both.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">2</div><div class="rc-hero-stat-label">Core actions required to complete a price increase</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">UI</div><div class="rc-hero-stat-label">Plan price update — no engineering required</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">API / CSV</div><div class="rc-hero-stat-label">Subscriber migration options for bulk rollout</div></div>
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
   
	<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-why" class="rc-sticky-link">
          <span class="rc-step-badge">1</span> Why increase prices?
        </a>
 	
	<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-why" class="rc-sticky-link">
          <span class="rc-step-badge">2</span> Things to consider
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-how" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> 
           How to execute it
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
      <h2><i class="fa-solid fa-tag rc-fa-section"></i> Phase A — Update the plan price</h2>
      <p>This is the first of two required actions. Updating the plan's unit amount makes the new price active for all new subscribers immediately. It does not change existing subscriptions.</p>

      <div class="rc-phase-label">Phase A · Plan UI update</div>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Navigate to Plans in the Recurly UI</h4>
            <p>Go to <strong>Configuration → Plans</strong>. Locate the plan you want to update and click into it.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Edit the unit amount</h4>
            <p>Click <strong>Edit Plan</strong>. Update the <strong>Unit Amount</strong> field to your new price. This is the base price for new subscriptions from this point forward.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Save and verify</h4>
            <p>Click <strong>Update Plan</strong>. Verify the new price appears in the plan summary. Test by starting a new subscription on this plan in your staging environment if available.</p>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-caution">
        <div class="rc-callout-icon"><i class="fa-solid fa-triangle-exclamation"></i></div>
        <div class="rc-callout-body">
          <strong>This does not affect existing subscribers</strong>
          <p>Existing subscriptions continue renewing at their current price until you explicitly update them. Phase B handles this.</p>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-arrows-rotate rc-fa-section"></i> Phase B — Migrate existing subscribers</h2>
      <p>You have three paths for updating existing subscriptions to the new price. Choose based on your subscriber volume, technical resources, and how targeted you need to be.</p>

      <div class="rc-phase-label">Option 1 · API migration</div>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Use the Subscriptions API to update unit amounts</h4>
            <p>Make a <code>PUT</code> request to <code>/v2/subscriptions/{uuid}</code> with the updated <code>unit_amount</code> field. Set <code>timeframe: renewal</code> to apply the change at the subscriber's next billing date — this is the least disruptive approach for active subscribers.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Or set timeframe: now for an immediate change</h4>
            <p>Use <code>timeframe: now</code> only if you need the price to take effect mid-cycle, such as for a repositioned plan where you're issuing a credit for the remaining days at the old rate. Recurly will prorate automatically.</p>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>API reference</strong>
          <p>See the full <a href="https://developers.recurly.com/api/v2021-02-25/index.html#operation/update_subscription" target="_blank" rel="noopener noreferrer">Update Subscription API docs</a> for field-level detail and response codes.</p>
        </div>
      </div>

      <div class="rc-phase-label" style="margin-top:32px">Option 2 · Bulk import via CSV</div>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Export your current subscriber list</h4>
            <p>Go to <strong>Subscriptions → Export</strong> and download a CSV of active subscriptions on the plan you're updating. This becomes both your migration file and your baseline for post-change comparison.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Prepare your import file</h4>
            <p>Retain the subscription UUID column and add or update the <code>unit_amount</code> column with the new price. Remove any subscriptions you want to grandfather before importing.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Import via the Recurly importer or contact Support</h4>
            <p>Use <strong>Integrations → Import</strong> if available in your account, or contact <a href="mailto:support@recurly.com">support@recurly.com</a> for bulk subscription update assistance. Confirm the timeframe (renewal vs. immediate) before submitting.</p>
          </div>
        </div>
      </div>

      <div class="rc-phase-label" style="margin-top:32px">Option 3 · Grandfathering via subscription override</div>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Identify your grandfather list</h4>
            <p>Pull the subscription UUIDs for every account you've decided to protect. This list should come from the segment analysis you did in step 2.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Apply a custom unit amount override via API</h4>
            <p>Make a <code>PUT</code> to <code>/v2/subscriptions/{uuid}</code> with the <strong>current</strong> price as <code>unit_amount</code> and <code>timeframe: renewal</code>. This locks that subscription at its existing rate while the plan price increases for everyone else.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Document every grandfathered account</h4>
            <p>Maintain an internal record of who is grandfathered and why. This protects you if a subscriber asks questions later, and it informs future pricing decisions when these accounts come up for review.</p>
          </div>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-list-check rc-fa-section"></i> Final execution checklist</h2>
      <p>Before you go live, confirm each of these is in place.</p>
      <div class="rc-checklist">
        <div class="rc-checklist-header">
          <i class="fa-solid fa-list-check" style="color: var(--yellow); font-size: 1rem;"></i>
          <h4>Pre-launch checklist</h4>
        </div>

        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Plan price updated in Recurly UI</strong>
            <span>New subscribers will see the new price immediately.</span>
          </div>
        </label>

        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Subscriber export complete</strong>
            <span>You have a pre-change baseline CSV saved.</span>
          </div>
        </label>

        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Grandfather list finalized</strong>
            <span>Specific accounts identified and noted internally.</span>
          </div>
        </label>

        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Migration method chosen</strong>
            <span>API or import, with timeframe confirmed (renewal recommended).</span>
          </div>
        </label>

        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Contracts reviewed</strong>
            <span>Any subscriber with a price-lock clause excluded from migration.</span>
          </div>
        </label>

        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Subscriber notification sent or scheduled</strong>
            <span>Covered in step 5.</span>
          </div>
        </label>

        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Support team briefed</strong>
            <span>Your support team knows the change is coming and has talking points ready.</span>
          </div>
        </label>

        <div class="rc-checklist-footer">Tap each item to mark it complete</div>
      </div>
    </div>

    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-considerations" class="rc-btn-prev">← Things to consider</a>
      <span class="rc-lp-nav-indicator">4 of 6</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-communicate" class="rc-btn-path">Next: Communicate it →</a>
    </div>

    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/docs/plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Plans</a>
        <a href="https://docs.recurly.com/docs/subscriptions" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Subscriptions</a>
        <a href="https://developers.recurly.com/api/v2021-02-25/index.html#operation/update_subscription" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> API: Update Subscription</a>
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
