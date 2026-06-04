---
title: 'Plan Price Increase: How to communicate it'
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
/* G-2: Hero h1 yellow underline */
.rc-guide h1 { border-bottom: none !important; padding-bottom: 0 !important; }
/* G-1: Polar font — wildcard ensures all descendants use it */
.rc-guide, .rc-guide * { font-family: "Polar", "Helvetica Neue", Helvetica, arial, sans-serif !important; }
/* FA6 FONT RESTORE — (0,0,2,0) beats wildcard (0,0,1,0); must follow wildcard */
.rc-guide [class^="fa-"],
.rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide .fa-brands,
.rc-guide [class*="fa-brands"] { font-family: "Font Awesome 6 Brands" !important; }

/* ── NAVIGATE MASTER ARMOR ──
   Global CSS section 1.1 rule → (0,0,6,2) !important. This armor → (0,0,7,1).
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
.rc-fa-dark     { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light    { color: #0D0D0B; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section  { color: #0D0D0B; font-size: 1rem; }

/* ── TOP NAV / BACK LINK ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

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

/* ── NAVIGATION — non-sticky, open on load (Micro-Path / Course page) ── */
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
/* Nav links — (0,0,8,1); semi-transparent hover on yellow nav */
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link { color: #0D0D0B !important; font-weight: 700; font-size: .83rem; letter-spacing: .4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-sticky-link:hover .rc-step-badge { background: var(--yellow); color: var(--offblack); }
/* Active item — no persistent background; map pin replaces badge */
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }

/* ── CONTENT SECTIONS ── */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* ── STEPS ── */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 0 0 24px; }
/* auto 1fr accommodates both circle badges and time-label badges */
.rc-step { display: grid; grid-template-columns: auto 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-num-time { min-width: 56px; height: 36px; padding: 0 12px; border-radius: 20px; background: var(--offblack); color: var(--yellow); display: inline-flex; align-items: center; justify-content: center; font-size: .72rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; letter-spacing: .3px; white-space: nowrap; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0 0 8px; }
.rc-step-content p:last-child { margin-bottom: 0; }
.rc-step-content strong { color: var(--darkgray); }
.rc-step-content code { background: var(--brightgray); color: var(--offblack); padding: 2px 7px; border-radius: 4px; font-size: .82rem; }
/* Inline links in step content — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide .rc-step-content a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-step-content a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide .rc-step-content a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide .rc-step-content a:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* ── EMAIL PREVIEW ── */
.rc-email-preview { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 20px 0 32px; }
.rc-email-header { background: var(--offblack); padding: 14px 20px; display: flex; align-items: center; gap: 10px; }
.rc-email-header span { font-size: .78rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: var(--yellow); }
.rc-email-body { padding: 24px 28px; }
.rc-email-body p { font-size: .9rem; color: var(--darkgray); line-height: 1.7; margin: 0 0 14px; }
.rc-email-body p:last-child { margin-bottom: 0; }
.rc-email-body strong { color: var(--offblack); }

/* ── CALLOUTS ── */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout + .rc-callout { margin-top: 12px; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
/* Direct child > keeps inline <strong> inside <p> from breaking to block */
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-tip     { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body > strong { color: var(--offblack); }
.rc-callout-caution { background: rgba(255,130,0,0.08); border-left: 4px solid var(--orange); }
.rc-callout-caution .rc-callout-body > strong { color: var(--darkgray); }
/* Callout inline links — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-callout-body a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide .rc-callout-body a:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* ── PATH NAV BUTTONS ── */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
/* rc-btn-prev — (0,0,8,1); hex border values required */
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; color: #0D0D0B !important; }
/* rc-btn-path — (0,0,8,1); hex border values required */
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path { background: #FFD706; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: #0D0D0B !important; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }

/* ── RESOURCES ── */
.rc-resources { background: var(--brightgray); border-left: 4px solid #FFD706; border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
/* Resource links — (0,0,8,1); intentional underline overrides armor */
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link { color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-decoration-color: #FFD706 !important; text-underline-offset: 3px !important; }

/* ── FOOTER NAV ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link { color: #807D73 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-footer-link:hover { color: #FF8200 !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s; }
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
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase" class="rc-back-link">← Back to Path Start</a>
  </div>

  <div class="rc-content-wrap">

    <!-- ANNOUNCEMENT BAR — add rc-active class to show; no close button (ReadMe strips onclick) -->
    <div class="rc-announce-bar">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Join our CSMs for a live pricing strategy session.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
    </div>

    <!-- HERO -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Plan Price Increase
      </div>
      <div class="rc-lp-hero-title"><h1>Communicate it</h1></div>
      <p>What you say, when you say it, and how to use Recurly's email and webhook tools to reach every subscriber cohort at the right moment.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">30–90</div><div class="rc-hero-stat-label">Days notice — the window that separates good and great communication</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">3</div><div class="rc-hero-stat-label">Notification touchpoints recommended in a standard rollout</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">Subject line</div><div class="rc-hero-stat-label">The single biggest variable in subscriber open rates</div></div>
      </div>
    </div>

    <!-- NAV — non-sticky + open on load (Micro-Path page)
         Order: Navigate Home first · numbered pages · Back to Path Start last -->
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
	<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-considerations" class="rc-sticky-link">
          <span class="rc-step-badge">2</span> Things to consider
        </a>
 <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-how" class="rc-sticky-link">
          <span class="rc-step-badge">3</span> How to execute it
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-communicate" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> 
           How to communicate it
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


    <!-- SECTION: Notification timeline -->
    <div class="rc-lp-section">
      <h2><i class="fa-regular fa-clock rc-fa-section"></i> Notification timeline</h2>
      <p>A well-timed communication sequence does three things: it gives subscribers enough runway to make a decision, it keeps your support inbox from flooding on the day of the change, and it reinforces the value narrative at every touchpoint.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num-time">Day 0</div>
          <div class="rc-step-content">
            <h4>Initial announcement — 30–90 days before change</h4>
            <p>Your primary notification. This is the email that explains the why, states the new price clearly, and gives the effective date. It's the most important message in the sequence — give it the most attention. Personalize by plan name and current price where possible.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-time">Day 14</div>
          <div class="rc-step-content">
            <h4>Reminder — 2 weeks out</h4>
            <p>A shorter follow-up for subscribers who didn't open or act on the initial email. Keep this brief: one paragraph restating the change and the date. Include a link to your FAQ or support page if you've created one.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-time">Day 28</div>
          <div class="rc-step-content">
            <h4>Final notice — 48–72 hours before renewal</h4>
            <p>Triggered at renewal time, this message arrives just before the subscriber's invoice processes at the new price. It's not a surprise — it's a final confirmation. Keep it factual: "Your subscription renews on [date] at [new price]."</p>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>Use Recurly webhooks to trigger renewal-time emails</strong>
          <p>Recurly fires a <code>subscription_renewal_invoice_created</code> webhook event before each renewal processes. Connect this to your email platform (Braze, Iterable, Klaviyo, etc.) to send the Day 28 notice automatically — no manual list management needed.</p>
        </div>
      </div>
    </div>

    <!-- SECTION: Email template — initial announcement -->
    <div class="rc-lp-section">
      <h2><i class="fa-regular fa-envelope rc-fa-section"></i> Email template — initial announcement</h2>
      <p>This template is a starting point. Customize the value bullet points with your actual product improvements and fill in the specifics.</p>

      <div class="rc-email-preview">
        <div class="rc-email-header">
          <i class="fa-regular fa-envelope" style="color:#FFD706;font-size:.9rem;"></i>
          <span>Email template · Initial announcement</span>
        </div>
        <div class="rc-email-body">
          <p><strong>Subject:</strong> An update to your [Product Name] subscription pricing</p>
          <p>Hi [First Name],</p>
          <p>We're writing to let you know that the price of your [Plan Name] subscription will increase from <strong>[current price]</strong> to <strong>[new price]</strong> effective <strong>[effective date]</strong>.</p>
          <p>Since you joined, we've shipped a lot — including:</p>
          <p>— [Feature or improvement 1]<br>— [Feature or improvement 2]<br>— [Feature or improvement 3]</p>
          <p>This price update reflects the continued investment we're making in [Product Name] and aligns us with the value we're delivering today.</p>
          <p>Your subscription will renew at the new price starting <strong>[effective date]</strong>. No action is required on your end — your billing will update automatically.</p>
          <p>If you have questions, you can reply to this email or visit [support link]. We appreciate you being a subscriber.</p>
          <p>[Your name or team]</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-caution">
        <div class="rc-callout-icon"><i class="fa-solid fa-triangle-exclamation"></i></div>
        <div class="rc-callout-body">
          <strong>Personalize the value bullets — don't leave them generic</strong>
          <p>"We've been working hard to improve your experience" does not land with subscribers. List specific features, integrations, or capabilities that have shipped since their subscription started. Three concrete examples outperform five vague ones.</p>
        </div>
      </div>
    </div>

    <!-- SECTION: Email template — final renewal notice -->
    <div class="rc-lp-section">
      <h2><i class="fa-regular fa-envelope rc-fa-section"></i> Email template — final renewal notice</h2>
      <p>This one is short by design. It's a confirmation, not a pitch — subscribers already know the change is coming.</p>

      <div class="rc-email-preview">
        <div class="rc-email-header">
          <i class="fa-regular fa-envelope" style="color:#FFD706;font-size:.9rem;"></i>
          <span>Email template · Final renewal notice</span>
        </div>
        <div class="rc-email-body">
          <p><strong>Subject:</strong> Your [Product Name] subscription renews on [date]</p>
          <p>Hi [First Name],</p>
          <p>Just a heads-up: your [Plan Name] subscription renews on <strong>[renewal date]</strong> at the updated price of <strong>[new price]</strong>.</p>
          <p>If you'd like to make any changes to your subscription before renewal, you can do so at [account link] or by replying to this email.</p>
          <p>[Your name or team]</p>
        </div>
      </div>
    </div>

    <!-- SECTION: Using Recurly email templates -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-paper-plane rc-fa-section"></i> Using Recurly email templates</h2>
      <p>Recurly's built-in email system lets you configure and send subscription-related emails directly from the platform — no external tool required for simple rollouts.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Configure email templates in the UI</h4>
            <p>Go to <strong>Configuration → Email Templates</strong>. Recurly has pre-built templates for subscription events including upcoming renewals and billing updates. Customize the body and subject line with your messaging.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Use merge variables for personalization</h4>
            <p>Recurly templates support merge variables including <code>{{ subscriber.first_name }}</code>, <code>{{ subscription.plan.name }}</code>, <code>{{ subscription.unit_amount }}</code>, and <code>{{ subscription.current_period_ends_at }}</code>. Use these to personalize at scale without manual list segmentation.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Or use webhooks to trigger your ESP</h4>
            <p>If you use an email service provider (Braze, Iterable, Klaviyo, HubSpot), subscribe to Recurly's <code>subscription_updated</code> and <code>subscription_renewal_invoice_created</code> webhook events to trigger your own templates with full design control.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- PATH NAV BUTTONS -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-how" class="rc-btn-prev">← How to execute it</a>
      <span class="rc-lp-nav-indicator">4 of 5</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-impact" class="rc-btn-path">Next: Track the impact →</a>
    </div>

    <!-- RESOURCES -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/docs/email-templates" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Email templates</a>
        <a href="https://docs.recurly.com/docs/webhooks" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Webhooks</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
      </div>
    </div>

    <!-- FOOTER NAV — grouped sections -->
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
            <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
          </a>
          <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
        </div>

      </div>
    </div>

  </div><!-- /.rc-content-wrap -->
</div><!-- /.rc-guide -->
`}</HTMLBlock>

<br />
