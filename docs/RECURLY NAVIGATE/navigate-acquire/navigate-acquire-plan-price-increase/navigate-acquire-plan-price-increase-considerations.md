---
title: 'Plan Price Increase: Considerations'
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

/* NAVIGATE MASTER ARMOR — (0,0,7,1) beats global section 1.1 rule (0,0,6,2) */
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

/* FONT AWESOME ICON HELPERS */
.rc-fa-announce { color: #0D0D0B; font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark  { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: #0D0D0B; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: #0D0D0B; font-size: 1rem; }

.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }

/* Back link — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Announcement bar */
.rc-announce-bar { display: none; background: #FFD706; color: #0D0D0B; align-items: center; justify-content: space-between; padding: 10px 20px; font-size: .88rem; font-weight: 600; border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4; }
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 10px; flex: 1; flex-wrap: wrap; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-announce-link { color: #0D0D0B !important; font-weight: 800; white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; transition: background .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-announce-link:hover { background: rgba(0,0,0,0.20); color: #0D0D0B !important; }

/* Hero */
.rc-hero { background: linear-gradient(rgba(13,13,11,0.82),rgba(13,13,11,0.82)), url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center; background-color: var(--offblack); background-size: cover; color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0; }
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,215,6,0.20); border: 1px solid rgba(255,215,6,0.45); color: #FFD706; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: var(--lightgray); line-height: 1.6; }
.rc-hero-stats { display: grid; grid-template-columns: repeat(3,1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: #FFD706; line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); line-height: 1.3; }

/* Nav — position: relative + open for course pages */
details.rc-sticky-nav-wrap { position: relative; z-index: 1; background-color: var(--yellow); box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px; border-radius: 12px; border: 1px solid rgba(0,0,0,0.08); overflow: hidden; }
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: .6px; text-transform: uppercase; color: var(--offblack); }
.rc-nav-chevron { font-size: .72rem; color: var(--offblack); opacity: .55; line-height: 1; transition: transform .25s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows .3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }

/* Nav links — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link { color: #0D0D0B !important; font-weight: 700; font-size: .83rem; letter-spacing: .4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-sticky-link:hover .rc-step-badge { background: var(--yellow); color: var(--offblack); }

/* Active item — no persistent background; map pin identifies current page */
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }

/* Content sections */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* Cards */
.rc-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 0 0 20px; }
.rc-card-title { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 10px; display: flex; align-items: center; gap: 8px; }
.rc-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-card p:last-child { margin-bottom: 0; }
.rc-card ul { font-size: .92rem; color: var(--gray); line-height: 1.75; padding-left: 20px; margin: 0; }
.rc-card ul li { margin-bottom: 6px; }
.rc-card ul li strong { color: var(--darkgray); }

/* Accent cards */
.rc-accent-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 20px 0; }
.rc-accent-card.rc-accent-yellow { border-left: 4px solid var(--yellow); }
.rc-accent-card.rc-accent-orange { border-left: 4px solid var(--orange); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 10px; display: flex; align-items: center; gap: 8px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-accent-card p:last-child { margin-bottom: 0; }
.rc-accent-card ul { font-size: .9rem; color: var(--gray); line-height: 1.75; padding-left: 20px; margin: 0; }
.rc-accent-card ul li { margin-bottom: 4px; }
.rc-accent-card ul li strong { color: var(--darkgray); }

/* Steps */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 0; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0; }
.rc-step-content strong { color: var(--darkgray); }

/* Callouts */
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
/* Callout inline links — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-callout-body a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide .rc-callout-body a:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* Path navigation */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }

/* rc-btn-prev — (0,0,8,1); hex borders required (KI #52) */
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }

/* rc-btn-path — (0,0,8,1); hex borders required (KI #44) */
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path { background: var(--yellow); color: #0D0D0B !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: #0D0D0B !important; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }

/* Resources */
.rc-resources { background: var(--brightgray); border-left: 4px solid #FFD706; border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
/* Resource links — (0,0,8,1); hex colors (KI #41) */
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link { color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration-color: #FFD706 !important; }

/* Footer */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
/* Footer links — (0,0,8,1); hex colors */
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link { color: #807D73 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-footer-link:hover { color: #FF8200 !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: .5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

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
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Plan price increase
      </div>
      <div class="rc-lp-hero-title"><h1>Things to consider</h1></div>
      <p>Before you touch the plan UI, work through timing, subscriber segments, contracts, and grandfathering logic.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">30–90</div><div class="rc-hero-stat-label">Days of notice recommended before change takes effect</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">3</div><div class="rc-hero-stat-label">Subscriber segments to plan for separately</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">100%</div><div class="rc-hero-stat-label">Of contract subscribers must be reviewed before migration</div></div>
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
				<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-why" class="rc-sticky-link rc-stick-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Things to consider
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
      <h2><i class="fa-solid fa-clock rc-fa-section"></i> Timing your increase</h2>
      <p>The single most common mistake in a price increase rollout is moving too fast. Rushing the timeline leads to subscriber surprise, support spikes, and avoidable churn. Here's how to think about pacing.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Choose your effective date strategically</h4>
            <p>Avoid major holidays, Q4 renewal peaks for B2B subscribers, or any period when your support team is understaffed. The best window is a quieter mid-quarter period with predictable renewal volume.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Monthly plans: 30 days minimum notice</h4>
            <p>Monthly subscribers feel the change quickly — they'll see the new price at their very next renewal. Give them at least 30 days to decide whether to stay, and make sure your notification goes out before that window opens.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Annual plans: 60–90 days minimum notice</h4>
            <p>Annual subscribers have a longer relationship with your product and a larger financial commitment. They deserve more lead time — and if they're approaching renewal, they may prefer to lock in at the current rate for one more cycle.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Stagger communication waves, not the change itself</h4>
            <p>Send notices in batches if your subscriber base is large — this prevents a single day of support volume from overwhelming your team. The actual plan price update can happen on one date; the notifications can roll out over a week.</p>
          </div>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-users rc-fa-section"></i> Subscriber segments to plan for</h2>
      <p>Not all of your subscribers should be treated identically. Think through each cohort before you migrate anyone.</p>

      <div class="rc-accent-card rc-accent-yellow">
        <h4><i class="fa-solid fa-user-plus rc-fa-section"></i> New subscribers</h4>
        <p>Once you update the plan's unit amount in Recurly, all new subscriptions automatically get the new price. No additional action needed. This group is the simplest — and it's a good reason to update the plan price before you communicate the change to existing subscribers.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4><i class="fa-solid fa-arrows-rotate rc-fa-section"></i> Active subscribers on the current plan</h4>
        <p>These subscribers need to be explicitly migrated. You have three options: migrate at their next renewal (least disruptive), migrate immediately mid-cycle (unusual — only for significant repositioning), or grandfather them indefinitely (for high-value or high-risk accounts). Migration mechanics are covered in step 3.</p>
      </div>

      <div class="rc-accent-card rc-accent-orange">
        <h4><i class="fa-solid fa-file-contract rc-fa-section"></i> Subscribers under contract</h4>
        <p>Review your contracts carefully before migrating anyone in this cohort. If a subscriber's contract specifies a fixed price or locks in renewal terms, you may not be able to apply the increase until their contract period ends. Migrating a contracted subscriber at a higher price without reviewing obligations is a legal and relationship risk. When in doubt, check with your legal or finance team first.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4><i class="fa-solid fa-crown rc-fa-section"></i> High-value or long-tenure subscribers</h4>
        <p>Your highest-value subscribers — by revenue, by tenure, or by strategic relationship — warrant individual consideration. Some may benefit from a personal outreach instead of (or before) the standard notification. Others may be candidates for grandfathering as a retention gesture.</p>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-lock rc-fa-section"></i> Grandfathering strategy</h2>
      <p>Grandfathering means locking a subscriber at their current price — indefinitely, or for a defined period — while the rest of your base moves to the new rate. It's a powerful retention tool when used deliberately; it erodes your pricing integrity when used as a default.</p>

      <div class="rc-card">
        <div class="rc-card-title"><i class="fa-solid fa-ruler rc-fa-section"></i> When to grandfather</div>
        <ul>
          <li><strong>High-risk churn accounts:</strong> A subscriber who has already submitted a cancellation request or complained about pricing recently is a candidate for a retention conversation — not a migration notice.</li>
          <li><strong>Long-tenure advocates:</strong> Subscribers who have been with you for 3+ years and actively refer others deserve special treatment. A grandfathered price is a low-cost loyalty signal.</li>
          <li><strong>Strategic accounts:</strong> Subscribers whose logos, referrals, or case studies have commercial value beyond their subscription revenue.</li>
          <li><strong>Promotional commitments:</strong> Anyone who was explicitly promised a locked-in rate as part of a campaign or sales conversation.</li>
        </ul>
      </div>

      <div class="rc-callout rc-callout-caution">
        <div class="rc-callout-icon"><i class="fa-solid fa-triangle-exclamation"></i></div>
        <div class="rc-callout-body">
          <strong>Don't grandfather by default</strong>
          <p>If grandfathering becomes your standard response to any pushback, you undermine the price increase entirely. Use it for specific accounts with specific reasons, not as a pressure valve for every complaint.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>How Recurly handles grandfathering</strong>
          <p>In Recurly, a grandfathered price is a subscription-level unit amount override. You update the plan price for everyone, then apply a <strong>custom unit amount</strong> override on specific subscriptions to lock them at their old rate. This keeps your plan clean while protecting specific accounts. Detailed steps are in step 3.</p>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-folder-open rc-fa-section"></i> What to do with legacy plans</h2>
      <p>If you've been running the same plan for years, you may have subscribers on several different price points — some from promotional periods, some from old pricing tiers, some from manual overrides. Before a price increase, it's worth cleaning up this landscape.</p>

      <div class="rc-card">
        <div class="rc-card-title"><i class="fa-solid fa-list-check rc-fa-section"></i> Pre-increase plan audit</div>
        <ul>
          <li><strong>Export your active subscriptions</strong> before making any changes — this is your baseline. You'll need it for migration and for post-change comparison.</li>
          <li><strong>Identify plans with overlapping pricing:</strong> If you have three plans all priced within $5 of each other, consolidate before increasing. A confused plan structure makes migration logic harder.</li>
          <li><strong>Retire plans you no longer sell:</strong> Recurly allows you to mark plans as inactive so they no longer appear in your checkout, while existing subscribers on those plans continue uninterrupted. Do this before the price change so your catalog is clean.</li>
          <li><strong>Note any plans with add-ons or coupons:</strong> Price increases interact with add-on pricing and coupon discounts. Confirm whether your increase should affect the base price only or net pricing as well.</li>
        </ul>
      </div>
    </div>

    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-why" class="rc-btn-prev">← Why increase prices?</a>
      <span class="rc-lp-nav-indicator">2 of 5</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-how" class="rc-btn-path">Next: How to enable it →</a>
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
