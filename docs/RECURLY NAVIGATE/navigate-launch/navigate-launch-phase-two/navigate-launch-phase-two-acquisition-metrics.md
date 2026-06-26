---
title: 'Section 2: Acquisition & Growth'
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

/* NAVIGATE MASTER ARMOR */
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

/* FA ICON HELPERS */
.rc-fa-announce { color: #0D0D0B; font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark  { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: #0D0D0B; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: #0D0D0B; font-size: 1rem; }

/* ANNOUNCEMENT BAR */
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

/* TOP NAV / BACK LINK */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* HERO */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: #0D0D0B; background-size: cover;
  color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0;
}
.rc-lp-pillar-tag {
  display: inline-flex; align-items: center; gap: 7px;
  background: rgba(204,201,184,0.20); border: 1px solid rgba(204,201,184,0.45);
  color: #CCC9B8; font-size: .75rem; font-weight: 800;
  letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 14px; border-radius: 20px; margin-bottom: 20px;
}
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: #FFFDF2; margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto; color: #CCC9B8; line-height: 1.6; }

/* NAV — non-sticky + open (Course page) */
details.rc-sticky-nav-wrap {
  position: relative; z-index: 1;
  background-color: #F1EFE3;
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
.rc-guide a.rc-sticky-link { color: #0D0D0B !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: #0D0D0B; color: #FFD706; font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }

/* CONTENT SECTIONS */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: #0D0D0B; display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: #CCC9B8; }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: #32312D; margin: 0 0 16px; }

/* METRIC CARDS */
.rc-metric-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 14px; padding: 22px 24px; margin-bottom: 16px; }
.rc-metric-header { display: flex; align-items: center; gap: 12px; margin-bottom: 12px; }
.rc-metric-icon { width: 40px; height: 40px; border-radius: 10px; background: #0D0D0B; color: #FF8200; font-size: 1.1rem; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
.rc-metric-card h3 { font-size: 1rem; font-weight: 800; margin: 0; color: #0D0D0B; }
.rc-metric-card p { font-size: .9rem; color: #807D73; margin: 0 0 12px; line-height: 1.6; }
.rc-formula { background: #F1EFE3; border-radius: 8px; padding: 10px 14px; font-size: .83rem; font-family: monospace !important; color: #32312D; margin-bottom: 12px; }
.rc-pills { display: flex; gap: 8px; flex-wrap: wrap; }
.rc-pill { padding: 4px 12px; border-radius: 20px; font-size: .75rem; font-weight: 700; background: #FFFDF2; border: 1px solid #CCC9B8; color: #32312D; }
.rc-pill-up { background: rgba(22,163,74,0.10); color: #15803d; border-color: #86efac; }
.rc-pill-down { background: rgba(220,38,38,0.10); color: #dc2626; border-color: #fca5a5; }

/* VIDEO CARD */
.rc-video-card { border: 1px solid #CCC9B8; border-radius: 14px; overflow: hidden; margin: 0 0 40px; }
.rc-video-header { background: #0D0D0B; padding: 16px 22px; display: flex; align-items: center; gap: 10px; }
.rc-video-header h4 { font-size: .88rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: #FFD706; margin: 0; }
.rc-video-header span { font-size: .78rem; color: #CCC9B8; margin-left: auto; }
.rc-video-embed { position: relative; overflow: hidden; aspect-ratio: 16/9; background: #0D0D0B; }
.rc-video-embed iframe { position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; }
.rc-video-caption { padding: 12px 22px; font-size: .83rem; color: #807D73; background: #F1EFE3; border-top: 1px solid #CCC9B8; line-height: 1.5; }

/* WEBINAR CLIP CARD */
.rc-clip-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 14px; padding: 22px 24px; margin: 0 0 32px; }
.rc-clip-badge { display: inline-flex; align-items: center; gap: 6px; background: #0D0D0B; color: #FF8200; border-radius: 6px; padding: 4px 10px; font-size: .73rem; font-weight: 800; text-transform: uppercase; letter-spacing: .5px; margin-bottom: 12px; }
.rc-clip-card h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B; margin: 0 0 8px; }
.rc-clip-card p { font-size: .9rem; color: #32312D; line-height: 1.6; margin: 0 0 14px; }
.rm-Markdown.markdown-body .rc-guide a.rc-clip-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-clip-link { color: #FF8200 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-clip-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-clip-link:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* CARD GRID (2-col action cards) */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-feature-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; color: #0D0D0B; }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B; margin: 0; }
.rc-feature-card p { font-size: .88rem; color: #807D73; line-height: 1.55; margin: 0; }
@media(max-width:768px){ .rc-card-grid { grid-template-columns: 1fr; } }

/* CALLOUT */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: #32312D; }
.rc-callout-tip { background: #F1EFE3; border-left: 4px solid #0D0D0B; }
  .rc-callout-tip .rc-callout-body > strong { color: #0D0D0B; }
  
/* Feature CALLOUT */
.rc-callout-feature { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-feature-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-feature-body { flex: 1; }
.rc-callout-feature-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-feature-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: #ffef9c; }
.rc-callout-feature-tip { background: #FFD706; border-left: 4px solid #0D0D0B; }
.rc-callout-feature-tip .rc-callout-feature-body > strong { color: #0D0D0B; }



/* PATH NAV BUTTONS */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: #CCC9B8; letter-spacing: .5px; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path { background: #FF8200; color: #ffffff !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid #FF8200 !important; border-bottom: 2px solid #FF8200 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: #FF8200 !important; border: 2px solid #FF8200 !important; border-bottom: 2px solid #FF8200 !important; }

/* RESOURCES */
.rc-resources { background: #F1EFE3; border-left: 4px solid #CCC9B8; border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: #807D73; margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link { color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; }

/* FOOTER NAV */
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

/* RESPONSIVE */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-card-grid { grid-template-columns: 1fr; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-back-link">← Back to Launch</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Announcement bar (hidden — add rc-active to show) -->
    <div class="rc-announce-bar">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Join our CSMs for a live Q&amp;A on your Launchpad metrics.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
    </div>

    <!-- Hero -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/b6c93b0c856b23bcb18d1c1f5106eb9c83d23d9b505dc37e5ce9ea0d8dcfe89b-Launch-icon-white.png" alt="Launch"> Launch · Launchpad Phase 2
      </div>
      <div class="rc-lp-hero-title"><h1>Subscriber acquisition &amp; sign-up decline rate</h1></div>
      <p>These two metrics tell you how effectively you're growing — and how much friction is getting in the way of subscribers who want to sign up but can't.</p>
    </div>

    <!-- Nav (non-sticky + open — Course page 2 of 5) -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two" class="rc-sticky-link">Path overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-benchmarks-dashboard" class="rc-sticky-link"><span class="rc-step-badge">1</span> Benchmarks &amp; reporting</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-acquisition-metrics" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Acquisition &amp; decline
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-churn-metrics" class="rc-sticky-link"><span class="rc-step-badge">3</span> Churn metrics</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-retention-metrics" class="rc-sticky-link"><span class="rc-step-badge">4</span> Revenue &amp; recovery</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-review" class="rc-sticky-link"><span class="rc-step-badge">5</span> Review &amp; resources</a>

      </div></div></div>
    </details>

    <!-- Section: Overview -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-arrow-trend-up rc-fa-section"></i> Growth starts at the funnel top</h2>
      <p>Acquisition rate and sign-up decline rate are your growth-layer metrics. Together they show how fast your subscriber base is expanding — and how many potential subscribers are lost before completing their first payment.</p>

      <div class="rc-video-card">
        <div class="rc-video-header">
          <h4>Trail guide: acquisition &amp; sign-up decline rate</h4>
          <span>~5 min</span>
        </div>
        <div class="rc-video-embed">
          <iframe src="https://share.synthesia.io/embeds/videos/e30354c7-9177-452e-a306-450a0471fd50" loading="lazy" title="Navigate Launchpad — Acquisition & Decline" allow="encrypted-media; fullscreen; microphone; screen-wake-lock;" allowfullscreen></iframe>
        </div>
        <div class="rc-video-caption">Where to find these metrics in the Benchmarks Dashboard — and how to calculate and act on them.</div>
      </div>
    </div>

    <!-- Section: Acquisition Rate -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-user-plus rc-fa-section"></i> Acquisition rate</h2>
      <p>Measures how effectively you're bringing in new paid subscribers each month. A rising rate means your growth strategy is working. A declining rate signals a need to investigate marketing, pricing, or checkout conversion.</p>

      <div class="rc-metric-card">
        <div class="rc-metric-header">
          <div class="rc-metric-icon"><i class="fa-solid fa-arrow-trend-up"></i></div>
          <h3>How it's calculated</h3>
        </div>
        <div class="rc-formula">New paid subscribers ÷ Active subscribers (start of period) = Acquisition rate %</div>
        <div class="rc-pills">
          <span class="rc-pill rc-pill-up">Higher is better</span>
          <span class="rc-pill">Check monthly</span>
          <span class="rc-pill">Analytics → Benchmarks Overview → scroll to Acquisition Rate</span>
        </div>
      </div>
    </div>

    <!-- Section: Sign-Up Decline Rate -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-bolt rc-fa-section"></i> Sign-up decline rate</h2>
      <p>The percentage of transaction attempts during sign-up that are declined. A high rate means real customers are trying to sign up and failing — these are missed conversions. Recurly excludes retries from this metric to give you a clear approval signal.</p>

      <div class="rc-metric-card">
        <div class="rc-metric-header">
          <div class="rc-metric-icon"><i class="fa-solid fa-bolt"></i></div>
          <h3>How it's calculated</h3>
        </div>
        <div class="rc-formula">Failed transaction attempts ÷ Total sign-up attempts = Sign-up decline rate %</div>
        <div class="rc-pills">
          <span class="rc-pill rc-pill-down">Lower is better</span>
          <span class="rc-pill">Check monthly</span>
          <span class="rc-pill">Analytics → Benchmarks Overview → scroll to Signup Decline Rate</span>
        </div>
      </div>

      <div class="rc-clip-card">
        <div class="rc-clip-badge"><i class="fa-solid fa-circle-play"></i> Where in the webinar?</div>
        <h4>Deep dive: spotting fraud &amp; early friction indicators</h4>
        <p>Fast-forward to the Sign-Up Decline Benchmarks section. Strategic CSM Dan Shipley demonstrates how to use this report to spot card-testing fraud attacks (look for sudden spikes in decline codes) and how to compare gateway performance side-by-side to optimize checkout approval rates.</p>
        <a href="https://navigate.recurly.com/lunch-and-learn/stack-up-benchmarks/" target="_blank" rel="noopener noreferrer" class="rc-clip-link"><i class="fa-solid fa-circle-play"></i> Watch "Stack up against the competition" on demand →</a>
      </div>
    </div>

    <!-- Section: What to do if declines are high -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-screwdriver-wrench rc-fa-section"></i> What to do if sign-up declines are high</h2>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-shield-halved"></i></div>
          <h4>Check for fraud patterns</h4>
          <p>Sudden spikes — especially with specific decline codes — may indicate card-testing activity. Review with your CSM and gateway team to consider fraud tools or CAPTCHA implementation.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-code-branch"></i></div>
          <h4>Compare gateway performance</h4>
          <p>Different gateways approve card types at different rates. If your decline rate is high, compare approval rates by gateway to see whether a routing change or multi-gateway strategy could help.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-credit-card"></i></div>
          <h4>Check payment method coverage</h4>
          <p>Are you accepting the methods your customers prefer? Adding PayPal, Apple Pay, or localized payment methods can reduce checkout friction — especially for international subscribers.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-mobile-screen"></i></div>
          <h4>Review 3DS and checkout UX</h4>
          <p>Confusing 3DS authentication flows often lead to abandonment, which registers as a failed attempt. Always test your checkout UX from a subscriber's mobile perspective.</p>
        </div>
  <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-scale-unbalanced"></i></div>
          <h4>Check chargeback & fraud ratios</h4>
          <p>Merchants experiencing high chargebacks may have higher controls put in place at the issuer level, resulting in more declines.</p>
        </div>
  <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-earth-americas"></i></div>
          <h4>Consider multi-currency or localized processing</h4>
          <p>Using gateways with local acquiring relationships and accepting local currencies can reduce declines significantly. Local currency support alone has been shown to decrease decline rates by 5–10%.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>A note on data timing</strong>
          <p>Mid-month rates can fluctuate significantly before traffic volume dilutes them. Always use full prior-month data in the Benchmarks Dashboard for the most accurate trend analysis.</p>
        </div>
      </div>
    </div>

    <!-- Path navigation -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-benchmarks-dashboard" class="rc-btn-prev">← Benchmarks &amp; reporting</a>
      <span class="rc-lp-nav-indicator">2 of 5</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-churn-metrics" class="rc-btn-path">Next: Churn metrics →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/docs/subscriber-benchmarks" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: subscriber benchmarks guide</a>
        <a href="https://go.recurly.com/Recurly-Navigate-Metrics-Cheatsheet.html" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Launchpad Metrics Cheatsheet</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Support</a>
      </div>
    </div>

    <!-- Footer nav — Course pattern -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">

        <div class="rc-footer-section">
          <span class="rc-footer-label">Launchpad Phase 2</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two" class="rc-footer-link">Path overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-benchmarks-dashboard" class="rc-footer-link">1. Benchmarks &amp; reporting</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-acquisition-metrics" class="rc-footer-link">2. Acquisition &amp; decline</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-churn-metrics" class="rc-footer-link">3. Churn metrics</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-retention-metrics" class="rc-footer-link">4. Revenue &amp; recovery</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-review" class="rc-footer-link">5. Review &amp; resources</a>
        </div>

        <div class="rc-footer-utility">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
            <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt="Home"> Navigate Home
          </a>
          <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
        </div>

      </div>
    </div>

  </div><!-- /rc-content-wrap -->
</div><!-- /rc-guide -->
`}</HTMLBlock>

<br />
