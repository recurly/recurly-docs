---
title: Introduction to Navigate
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
.rc-guide [class^="fa-"],
.rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide .fa-brands,
.rc-guide [class*="fa-brands"] { font-family: "Font Awesome 6 Brands" !important; }

/* NAVIGATE MASTER ARMOR — (0,0,7,1) */
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
  --yellow:     #FFD706;
  --orange:     #FF8200;
  --offblack:   #0D0D0B;
  --darkgray:   #32312D;
  --gray:       #807D73;
  --lightgray:  #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite:   #FFFDF2;
  /* Pillar colors */
  --launch:     #CCC9B8;
  --acquire:    #FFD706;
  --retain:     #FF9D88;
  --scale:      #FF5810;
  color: #32312D !important;
  background: #ffffff;
}
.rc-guide * { box-sizing: border-box; }

/* FONT AWESOME ICON HELPERS */
.rc-fa-announce { color: #0D0D0B; font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark  { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: #0D0D0B; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: #0D0D0B; font-size: 1rem; }

/* ── TOP NAV / BACK LINK ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* ── ANNOUNCEMENT BAR ── */
.rc-announce-bar {
  display: none; background: #FFD706; color: #0D0D0B;
  align-items: center; justify-content: space-between;
  padding: 10px 20px; font-size: .88rem; font-weight: 600;
  border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4;
}
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 10px; flex: 1; flex-wrap: wrap; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-announce-link { color: #0D0D0B !important; font-weight: 800; white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; transition: background 0.2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-announce-link:hover { background: rgba(0,0,0,0.20); color: #0D0D0B !important; }

/* ── HERO ── */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: #0D0D0B; background-size: cover;
  color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0;
}
.rc-brand-header { display: flex; justify-content: center; margin-bottom: 0; }
.rc-logo-image { height: 28px; display: block; }

/* Four-pillar icon row — unique to this cross-pillar course */
.rc-pillar-icon-row {
  display: flex; justify-content: center; gap: 12px;
  margin: 36px auto 24px; flex-wrap: wrap;
}
.rc-pillar-icon-chip {
  display: inline-flex; align-items: center; gap: 7px;
  padding: 7px 14px; border-radius: 20px;
  font-size: .72rem; font-weight: 800; letter-spacing: .8px; text-transform: uppercase;
}
.rc-pillar-icon-chip img { width: 14px; height: 14px; object-fit: contain; }
.rc-chip-launch  { background: rgba(204,201,184,0.20); border: 1px solid rgba(204,201,184,0.45); color: #CCC9B8; }
.rc-chip-acquire { background: rgba(255,215,6,0.20);   border: 1px solid rgba(255,215,6,0.45);   color: #FFD706; }
.rc-chip-retain  { background: rgba(255,157,136,0.20); border: 1px solid rgba(255,157,136,0.45); color: #FF9D88; }
.rc-chip-scale   { background: rgba(255,88,16,0.20);   border: 1px solid rgba(255,88,16,0.45);   color: #FF5810; }

.rc-hero h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: #FFFDF2; margin: 0 0 14px; }
.rc-hero > .rc-content-wrap > p,
.rc-hero-sub { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto; color: #CCC9B8; line-height: 1.6; }

/* ── NAV — non-sticky, open on load (Course page) ── */
details.rc-sticky-nav-wrap {
  position: relative;
  z-index: 1;
  background-color: #F1EFE3; /* Launch = brightgray */
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px; border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08); overflow: hidden;
}
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: #0D0D0B; }
.rc-nav-chevron { font-size: .72rem; color: #0D0D0B; opacity: 0.55; line-height: 1; transition: transform 0.25s ease; }
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
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: #0D0D0B; color: #FFD706; font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }

/* ── CONTENT SECTIONS ── */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: #0D0D0B; display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: #CCC9B8; }
.rc-lp-section > p { font-size: .95rem; line-height: 1.65; color: #32312D; margin: 0 0 16px; }

/* ── CARDS ── */
.rc-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 12px; padding: 24px 28px; margin-bottom: 24px; }
.rc-card h3 { font-size: 1rem; font-weight: 800; color: #0D0D0B; margin: 0 0 10px; display: flex; align-items: center; gap: 8px; }
.rc-card p { font-size: .93rem; color: #32312D; line-height: 1.65; margin: 0 0 12px; }
.rc-card p:last-child { margin-bottom: 0; }

/* ── AGENDA TABLE ── */
.rc-agenda { border-radius: 14px; overflow: hidden; border: 1px solid #CCC9B8; margin-bottom: 24px; }
.rc-agenda-header { display: grid; grid-template-columns: 52px 1fr 1fr; background: #0D0D0B; }
.rc-agenda-header span { padding: 10px 16px; font-size: .78rem; font-weight: 700; color: #CCC9B8; text-transform: uppercase; letter-spacing: .5px; }
.rc-agenda-header span:first-child { text-align: center; }
.rc-agenda-row { display: grid; grid-template-columns: 52px 1fr 1fr; border-bottom: 1px solid #F1EFE3; }
.rc-agenda-row:last-child { border-bottom: none; }
.rc-agenda-num { display: flex; align-items: center; justify-content: center; font-weight: 800; font-size: .9rem; background: #0D0D0B; color: #FFD706; flex-shrink: 0; }
.rc-agenda-name { padding: 14px 16px; font-weight: 700; font-size: .9rem; color: #0D0D0B; background: #FFFDF2; border-right: 1px solid #F1EFE3; }
.rc-agenda-desc { padding: 14px 16px; font-size: .87rem; color: #807D73; background: #FFFDF2; line-height: 1.5; }
.rc-here-badge { display: inline-block; margin-left: 8px; background: #FFD706; color: #0D0D0B; padding: 2px 8px; border-radius: 10px; font-size: .7rem; font-weight: 700; vertical-align: middle; }

/* Pillar-colored agenda number cells */
.rc-agenda-num-launch  { background: #CCC9B8; color: #0D0D0B; }
.rc-agenda-num-acquire { background: #FFD706; color: #0D0D0B; }
.rc-agenda-num-retain  { background: #FF9D88; color: #0D0D0B; }
.rc-agenda-num-scale   { background: #FF5810; color: #ffffff; }

/* ── CALLOUT ── */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: #32312D; }
.rc-callout-tip { background: #F1EFE3; border-left: 4px solid #0D0D0B; }
.rc-callout-tip .rc-callout-body > strong { color: #0D0D0B; }

/* ── PATH NAV BUTTONS ── */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: #CCC9B8; letter-spacing: .5px; }
.rc-btn-start { background: #F1EFE3; color: #807D73; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid #CCC9B8; cursor: default; display: inline-flex; align-items: center; gap: 8px; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path { background: #FFD706; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: #0D0D0B !important; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }

/* ── RESOURCES ── */
.rc-resources { background: #F1EFE3; border-left: 4px solid #CCC9B8; border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: #807D73; margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link { color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; }

/* ── FOOTER ── */
.rc-footer-nav { border-top: 1px solid #CCC9B8; padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: #32312D; background: #F1EFE3; padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link { color: #807D73 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-footer-link:hover { color: #FF8200 !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid #F1EFE3; }

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-hero h1 { font-size: 1.8rem; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-pillar-icon-row { gap: 8px; }
  .rc-agenda-header, .rc-agenda-row { grid-template-columns: 52px 1fr; }
  .rc-agenda-header span:last-child, .rc-agenda-desc { display: none; }
}
</style>

<div class="rc-guide">

  <!-- BACK LINK -->
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-back-link">← Back to Launch</a>
  </div>

  <div class="rc-content-wrap">

    <!-- ANNOUNCEMENT BAR (hidden until rc-active added) -->
    <div class="rc-announce-bar">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Join our CSMs for a live Q&amp;A session.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
    </div>

    <!-- HERO -->
    <div class="rc-hero">
      <div class="rc-brand-header">
        <img class="rc-logo-image" src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly">
      </div>

      <!-- Four pillar icon chips — this course spans all pillars -->
      <div class="rc-pillar-icon-row">
        <span class="rc-pillar-icon-chip rc-chip-launch">
          <img src="https://files.readme.io/b6c93b0c856b23bcb18d1c1f5106eb9c83d23d9b505dc37e5ce9ea0d8dcfe89b-Launch-icon-white.png" alt=""> Launch
        </span>
        <span class="rc-pillar-icon-chip rc-chip-acquire">
          <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt=""> Acquire
        </span>
        <span class="rc-pillar-icon-chip rc-chip-retain">
          <img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt=""> Retain
        </span>
        <span class="rc-pillar-icon-chip rc-chip-scale">
          <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt=""> Scale
        </span>
      </div>

      <h1>Introduction to Recurly Navigate</h1>
      <p class="rc-hero-sub">Your official orientation to Navigate: Recurly's digital Customer Success program built to help you get the most out of Recurly at every stage of your journey.</p>
    </div>

    <!-- NAV — non-sticky, open (Course page) -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <!-- Overview is the active page — map pin, no number -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Overview
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-welcome" class="rc-sticky-link"><span class="rc-step-badge">1</span> Official welcome</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-flywheel" class="rc-sticky-link"><span class="rc-step-badge">2</span> The Recurly flywheel</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-home" class="rc-sticky-link"><span class="rc-step-badge">3</span> Navigate Home</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-expect" class="rc-sticky-link"><span class="rc-step-badge">4</span> What to expect</a>
        <!-- Back to Path Start -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- SECTION: Welcome to Recurly Navigate -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-map-location-dot rc-fa-section"></i> Welcome to Recurly Navigate</h2>

      <div class="rc-card">
        <h3><i class="fa-solid fa-compass rc-fa-section"></i> What is this course?</h3>
        <p>This course is your official orientation to <strong>Recurly Navigate</strong> — a digital Customer Success program that gives you the best practices, expert guidance, and product insights you need, right when you need them.</p>
        <p>Whether you're brand new to Recurly or just joining the Navigate program, this course walks you through everything: how we support you, where to find every resource, and what to expect from us.</p>
      </div>

      <!-- AGENDA TABLE — sections colored by pillar -->
      <h3 style="font-size:1rem;font-weight:800;color:#0D0D0B;margin:0 0 14px;display:flex;align-items:center;gap:8px;"><i class="fa-solid fa-list-check rc-fa-section"></i> What you'll cover</h3>
      <div class="rc-agenda">
        <div class="rc-agenda-header">
          <span>#</span>
          <span>Section</span>
          <span>What you'll learn</span>
        </div>
        <!-- Overview row — active -->
        <div class="rc-agenda-row">
          <div class="rc-agenda-num" style="background:#FFD706;color:#0D0D0B;font-size:.8rem;">
            <i class="fa-solid fa-map-pin"></i>
          </div>
          <div class="rc-agenda-name">
            Overview <span class="rc-here-badge">You are here</span>
          </div>
          <div class="rc-agenda-desc">Program introduction and what's inside this course</div>
        </div>
        <!-- Section 1 — no pillar color; general onboarding -->
        <div class="rc-agenda-row">
          <div class="rc-agenda-num">1</div>
          <div class="rc-agenda-name">Official welcome</div>
          <div class="rc-agenda-desc">What Customer Success is and how Navigate brings it to you</div>
        </div>
        <!-- Section 2 — four pillars; use all four colors in the name -->
        <div class="rc-agenda-row">
          <div class="rc-agenda-num">2</div>
          <div class="rc-agenda-name">The Recurly flywheel</div>
          <div class="rc-agenda-desc">
            The four pillars of subscription success and how all content is organized around them:
            <span style="color:#CCC9B8;font-weight:700;">Launch</span>,
            <span style="color:#B89A00;font-weight:700;">Acquire</span>,
            <span style="color:#D4604A;font-weight:700;">Retain</span>,
            <span style="color:#CC4610;font-weight:700;">Scale</span>
          </div>
        </div>
        <!-- Section 3 -->
        <div class="rc-agenda-row">
          <div class="rc-agenda-num">3</div>
          <div class="rc-agenda-name">Navigate Home</div>
          <div class="rc-agenda-desc">Your hub for learning paths, webinars, on-demand content, and resources</div>
        </div>
        <!-- Section 4 -->
        <div class="rc-agenda-row">
          <div class="rc-agenda-num">4</div>
          <div class="rc-agenda-name">What to expect</div>
          <div class="rc-agenda-desc">Scorecards, newsletters, events, proactive outreach: how Navigate shows up for you</div>
        </div>
      </div>

      <div class="rc-card">
        <h3><i class="fa-solid fa-lightbulb rc-fa-section"></i> Why Navigate exists</h3>
        <p>Subscription businesses have a lot to manage: acquiring customers, retaining them, recovering revenue, and scaling efficiently. Navigate gives you the expertise you need without waiting for a support ticket or a scheduled call.</p>
        <p>Navigate grows alongside Recurly, with new content, events, and resources added regularly, all organized around what's most relevant to your business right now.</p>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-regular fa-clock"></i></div>
        <div class="rc-callout-body">
          <strong>Estimated time to complete</strong>
          <p>About 8 minutes. Return to any section whenever you need a refresher.</p>
        </div>
      </div>

      <!-- PATH NAV BUTTONS -->
      <div class="rc-lp-nav">
        <span class="rc-btn-start">Start</span>
        <span class="rc-lp-nav-indicator">1 of 5</span>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-welcome" class="rc-btn-path">Next: Official welcome →</a>
      </div>

    </div><!-- end section -->

    <!-- RESOURCES -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
      </div>
    </div>

    <!-- FOOTER — Course pattern: one row, course name badge + Overview + numbered pages -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">

        <div class="rc-footer-section">
          <span class="rc-footer-label">Introduction to Navigate</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro" class="rc-footer-link">Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-welcome" class="rc-footer-link">1. Official welcome</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-flywheel" class="rc-footer-link">2. The Recurly flywheel</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-home" class="rc-footer-link">3. Navigate Home</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-expect" class="rc-footer-link">4. What to expect</a>
        </div>

        <div class="rc-footer-utility">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
            <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt="Home"> Navigate Home
          </a>
          <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
        </div>

      </div>
    </div>

  </div><!-- end content-wrap -->
</div><!-- end rc-guide -->
`}</HTMLBlock>

<br />
