---
title: 'Launchpad phase two: Review & resources'
excerpt: >-
  Review your subscription optimization progress and access essential growth
  resources. Recap core subscription metrics, utilize your KPI quick reference
  guide, and prepare for your Monthly Metrics Scorecard to track long-term
  revenue recovery and business health.
deprecated: false
hidden: true
metadata:
  description: >-
    Review your subscription optimization progress and access essential growth
    resources. Recap core subscription metrics, utilize your KPI quick reference
    guide, and prepare for your Monthly Metrics Scorecard to track long-term
    revenue recovery and business health.
  keywords:
    - Recurly Launchpad review
    - subscription KPI quick reference
    - subscription billing optimization
    - revenue recovery summary
    - subscription churn metrics recap
    - Monthly Metrics Scorecard
    - subscription growth resources
    - subscriber retention checklist
    - Recurly Compass AI
    - subscription lifecycle metrics
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

/* NAV — non-sticky + open (Course R&R page) */
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

/* CELEBRATION CARD */
.rc-celebration-card {
  background: linear-gradient(135deg, #0D0D0B 0%, #1a0f00 100%);
  border-radius: 16px; padding: 44px 36px; text-align: center;
  margin-bottom: 32px; border: 2px solid rgba(255,130,0,0.30);
}
.rc-celebration-icon { color: #FF8200 !important; font-size: 2.8rem; display: block; margin-bottom: 16px; }
.rc-celebration-card h2 { font-size: 1.8rem; font-weight: 800; color: #ffffff !important; margin: 0 0 12px; }
.rc-celebration-card p { font-size: .96rem; color: #CCC9B8 !important; margin: 0 auto; max-width: 560px; line-height: 1.7; }

/* TWO-PHASE RECAP CARDS */
.rc-two-phase { display: grid; grid-template-columns: 1fr 1fr; gap: 18px; margin-bottom: 32px; }
.rc-phase-recap { border-radius: 14px; padding: 22px; background: #0D0D0B !important; }
.rc-phase-recap-p1 { border: 2px solid #FFD706; }
.rc-phase-recap-p2 { border: 2px solid #FF8200; }
.rc-phase-recap h3 { font-size: .88rem; font-weight: 800; text-transform: uppercase; letter-spacing: .7px; margin: 0 0 16px; display: flex; align-items: center; gap: 8px; }
.rc-phase-recap-p1 h3 { color: #FFD706 !important; }
.rc-phase-recap-p2 h3 { color: #FF8200 !important; }
.rc-recap-list { list-style: none; margin: 0; padding: 0; }
.rc-recap-item { display: flex; align-items: flex-start; gap: 10px; padding: 8px 0; border-bottom: 1px solid rgba(255,255,255,0.07); font-size: .84rem; color: #CCC9B8 !important; line-height: 1.5; }
.rc-recap-item:last-child { border-bottom: none; }
.rc-recap-dot { width: 22px; height: 22px; border-radius: 50%; font-size: .68rem; font-weight: 800; display: flex; align-items: center; justify-content: center; flex-shrink: 0; margin-top: 1px; }
.rc-recap-dot-y { background: #FFD706; color: #0D0D0B; }
.rc-recap-dot-o { background: #FF8200; color: #ffffff; }
@media(max-width:768px){ .rc-two-phase { grid-template-columns: 1fr; } }

/* KPI TABLE */
.rc-kpi-table { width: 100%; border-collapse: collapse; margin-bottom: 32px; font-size: .88rem; border-radius: 10px; overflow: hidden; border: 1px solid #CCC9B8; }
.rc-kpi-table th { background: #0D0D0B !important; color: #ffffff !important; font-size: .75rem; font-weight: 800; text-transform: uppercase; letter-spacing: .5px; padding: 12px 14px; text-align: left; }
.rc-kpi-table td { padding: 11px 14px; border-bottom: 1px solid #F1EFE3; color: #32312D; vertical-align: top; background: #FFFDF2 !important; }
.rc-kpi-table tr:last-child td { border-bottom: none; }
.rc-kpi-table td:first-child { font-weight: 700; color: #0D0D0B; }
.rc-kpi-table td:last-child { font-weight: 700; white-space: nowrap; }

/* SAFE SENDER CARD */
.rc-safe-sender { background: #0D0D0B !important; border: 1px solid #FFD706; border-radius: 12px; padding: 18px 22px; margin-bottom: 24px; display: flex; align-items: flex-start; gap: 16px; }
.rc-safe-sender-icon { color: #FFD706 !important; font-size: 1.3rem; flex-shrink: 0; margin-top: 2px; }
.rc-safe-sender p { font-size: .88rem; color: #CCC9B8 !important; margin: 0; line-height: 1.6; }
.rc-safe-sender strong { color: #FFD706 !important; }

/* WHAT'S NEXT CARDS */
.rc-next-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; margin-bottom: 32px; }
.rc-next-item { background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 12px; padding: 20px 22px; display: flex; flex-direction: column; gap: 8px; }
.rc-next-item-icon { font-size: 1.3rem; color: #0D0D0B; line-height: 1; }
.rc-next-item h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B; margin: 0; }
.rc-next-item p { font-size: .88rem; color: #807D73; line-height: 1.55; margin: 0; flex-grow: 1; }
.rm-Markdown.markdown-body .rc-guide a.rc-next-cta:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-next-cta { display: inline-flex; align-items: center; gap: 6px; margin-top: 8px; background: #0D0D0B; color: #FFD706 !important; font-size: .82rem; font-weight: 800; padding: 8px 14px; border-radius: 8px; transition: all .18s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-next-cta:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-next-cta:hover { background: #32312D !important; color: #FFD706 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-next-cta-ghost:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-next-cta-ghost { display: inline-flex; align-items: center; gap: 6px; margin-top: 8px; background: transparent; color: #0D0D0B !important; font-size: .82rem; font-weight: 800; padding: 8px 14px; border-radius: 8px; border: 1px solid #CCC9B8 !important; border-bottom: 1px solid #CCC9B8 !important; transition: all .18s; }
.rm-Markdown.markdown-body .rc-guide a.rc-next-cta-ghost:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-next-cta-ghost:hover { border-color: #0D0D0B !important; border-bottom: 1px solid #0D0D0B !important; color: #0D0D0B !important; }
@media(max-width:768px){ .rc-next-grid { grid-template-columns: 1fr; } }

/* VIDEO CARD */
.rc-video-card { border: 1px solid #CCC9B8; border-radius: 14px; overflow: hidden; margin: 0 0 32px; }
.rc-video-header { background: #0D0D0B; padding: 16px 22px; display: flex; align-items: center; gap: 10px; }
.rc-video-header h4 { font-size: .88rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: #FFD706; margin: 0; }
.rc-video-header span { font-size: .78rem; color: #CCC9B8; margin-left: auto; }
.rc-video-embed { position: relative; overflow: hidden; aspect-ratio: 16/9; background: #0D0D0B; }
.rc-video-embed iframe { position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; }
.rc-video-caption { padding: 12px 22px; font-size: .83rem; color: #807D73; background: #F1EFE3; border-top: 1px solid #CCC9B8; line-height: 1.5; }

/* CALLOUT */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: #32312D; }
.rc-callout-tip { background: #F1EFE3; border-left: 4px solid #0D0D0B; }
.rc-callout-tip .rc-callout-body > strong { color: #0D0D0B; }

/* CONTINUE YOUR JOURNEY */
.rc-next-steps { margin: 40px 0 0; }
.rc-next-steps h3 { font-size: .78rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: #807D73; margin: 0 0 16px; display: flex; align-items: center; gap: 8px; }
.rc-next-grid-journey { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; }
.rm-Markdown.markdown-body .rc-guide a.rc-next-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-next-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 12px; padding: 20px; text-decoration: none !important; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; border-bottom: 1px solid #CCC9B8 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-next-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-next-card:hover { border-color: #CCC9B8; border-bottom: 1px solid #CCC9B8 !important; box-shadow: 0 4px 16px rgba(204,201,184,0.35); transform: translateY(-2px); }
.rc-next-card-tag { font-size: .68rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: #CCC9B8 !important; margin-bottom: 2px; }
.rc-next-card-icon { font-size: 1.3rem; line-height: 1; color: #0D0D0B !important; }
.rc-next-card h4 { font-size: .95rem; font-weight: 800; color: #0D0D0B !important; margin: 0; line-height: 1.3; }
.rc-next-card p { font-size: .85rem; color: #807D73 !important; line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-next-card-arrow { font-size: .82rem; font-weight: 700; color: #FF8200 !important; margin-top: 4px; }
@media(max-width:768px){ .rc-next-grid-journey { grid-template-columns: 1fr; } }

/* PATH NAV BUTTONS */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: #CCC9B8; letter-spacing: .5px; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
.rc-btn-complete { background: #F1EFE3; color: #0D0D0B !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #FFD706; cursor: default; user-select: none; }

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
  .rc-next-grid-journey { grid-template-columns: 1fr; }
  .rc-next-grid { grid-template-columns: 1fr; }
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
        <img src="https://files.readme.io/b6c93b0c856b23bcb18d1c1f5106eb9c83d23d9b505dc37e5ce9ea0d8dcfe89b-Launch-icon-white.png" alt="Launch"> Launch · Launchpad Phase Two
      </div>
      <div class="rc-lp-hero-title"><h1>Review &amp; resources</h1></div>
      <p>You've completed both phases of Launchpad. Here's a recap of everything you've built — and what comes next to keep the momentum going.</p>
    </div>

    <!-- Nav (non-sticky + open — Course R&R page 5 of 5) -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two" class="rc-sticky-link">Path Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-benchmarks-dashboard" class="rc-sticky-link"><span class="rc-step-badge">1</span> Benchmarks &amp; reporting</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-acquisition-metrics" class="rc-sticky-link"><span class="rc-step-badge">2</span> Acquisition &amp; decline</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-churn-metrics" class="rc-sticky-link"><span class="rc-step-badge">3</span> Churn metrics</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-retention-metrics" class="rc-sticky-link"><span class="rc-step-badge">4</span> Revenue &amp; recovery</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-review" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Review &amp; resources
        </a>
        
      </div></div></div>
    </details>

    <!-- Celebration card -->
    <div class="rc-celebration-card">
      <i class="fa-solid fa-trophy rc-celebration-icon"></i>
      <h2>You've completed Launchpad!</h2>
      <p>From production testing and dunning configuration to benchmarking your KPIs and understanding your revenue recovery funnel — you've done the work that sets high-performing subscription businesses apart.</p>
    </div>

    <!-- Section: Everything you've accomplished -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-list-check rc-fa-section"></i> Everything you've accomplished</h2>

      <div class="rc-two-phase">
        <div class="rc-phase-recap rc-phase-recap-p1">
          <h3><i class="fa-solid fa-gears" style="color:#FFD706;font-size:.9rem;"></i> Phase 1 · Optimization</h3>
          <ul class="rc-recap-list">
            <li class="rc-recap-item"><div class="rc-recap-dot rc-recap-dot-y">1</div>Final production testing — validated your checkout end-to-end</li>
            <li class="rc-recap-item"><div class="rc-recap-dot rc-recap-dot-y">2</div>Dunning optimization — Intelligent Retry, recovery emails, expiration rules</li>
            <li class="rc-recap-item"><div class="rc-recap-dot rc-recap-dot-y">3</div>Account Updater — proactive card refresh before renewals fail</li>
            <li class="rc-recap-item"><div class="rc-recap-dot rc-recap-dot-y">4</div>Branding — on-brand emails, invoices, and dunning communications</li>
            <li class="rc-recap-item"><div class="rc-recap-dot rc-recap-dot-y">5</div>Gateway failover — automatic rerouting when primary gateway is down</li>
          </ul>
        </div>
        <div class="rc-phase-recap rc-phase-recap-p2">
          <h3><i class="fa-solid fa-chart-line" style="color:#FF8200;font-size:.9rem;"></i> Phase 2 · Mastering metrics</h3>
          <ul class="rc-recap-list">
            <li class="rc-recap-item"><div class="rc-recap-dot rc-recap-dot-o">1</div>Benchmarks Dashboard — found KPIs in Analytics → Dashboards → Benchmarks</li>
            <li class="rc-recap-item"><div class="rc-recap-dot rc-recap-dot-o">2</div>Acquisition &amp; sign-up decline rate — growth metrics and checkout friction</li>
            <li class="rc-recap-item"><div class="rc-recap-dot rc-recap-dot-o">3</div>Voluntary &amp; involuntary churn — why subscribers leave and how to act on it</li>
            <li class="rc-recap-item"><div class="rc-recap-dot rc-recap-dot-o">4</div>Renewal &amp; recovery — paid rate, dunning recovery, and renewal decline</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- Section: KPI quick reference -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-table rc-fa-section"></i> Your KPI quick reference</h2>

      <table class="rc-kpi-table">
        <thead>
          <tr>
            <th>Metric</th>
            <th>What it measures</th>
            <th>Direction</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Acquisition rate</td>
            <td>New paid subscribers / active subscribers (start of period)</td>
            <td>Higher</td>
          </tr>
          <tr>
            <td>Sign-up decline rate</td>
            <td>Failed unique transaction attempts / total attempts</td>
            <td>Lower</td>
          </tr>
          <tr>
            <td>Voluntary churn rate</td>
            <td>Subscribers who canceled / active subscribers (start of period)</td>
            <td>Lower</td>
          </tr>
          <tr>
            <td>Involuntary churn rate</td>
            <td>Subscribers lost to dunning expiration / active subscribers (start of period)</td>
            <td>Lower</td>
          </tr>
          <tr>
            <td>Renewal invoice paid rate</td>
            <td>Successfully paid renewals / all renewals issued</td>
            <td>Higher</td>
          </tr>
          <tr>
            <td>Dunning recovery rate</td>
            <td>Invoices recovered / invoices entering dunning</td>
            <td>Higher</td>
          </tr>
        </tbody>
      </table>
    </div>

    <!-- Section: What comes next -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-rocket rc-fa-section"></i> What comes next</h2>
      <p>Your optimization journey doesn't end here. Stay connected with the Recurly community and watch for tailored learning to support your specific growth goals.</p>

      <div class="rc-safe-sender">
        <i class="fa-solid fa-envelope rc-safe-sender-icon"></i>
        <p><strong>Never miss an update:</strong> Add <strong>RecurlyNavigate@Recurly.com</strong> to your contact list. This ensures you always receive Navigate updates, exclusive invites, and your curated learning paths.</p>
      </div>

      <div class="rc-next-grid">
        <div class="rc-next-item">
          <div class="rc-next-item-icon"><i class="fa-solid fa-headset"></i></div>
          <h4>Your Customer Success team</h4>
          <p>Join a live <strong>Weekly Global Office Hours</strong> session to ask strategy questions, share learnings, and stay current with new features.</p>
          <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-next-cta"><i class="fa-solid fa-calendar-days"></i> Book Global Office Hours →</a>
        </div>
        <div class="rc-next-item">
          <div class="rc-next-item-icon"><i class="fa-solid fa-circle-play"></i></div>
          <h4>Spotlight &amp; on-demand webinars</h4>
          <p>Watch the <strong>Customer Spotlight Series</strong> for peer-led workshops, or browse Navigate On-Demand Events for topics you need.</p>
          <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-next-cta-ghost"><i class="fa-solid fa-arrow-up-right-from-square"></i> Visit events →</a>
        </div>
        <div class="rc-next-item">
          <div class="rc-next-item-icon"><i class="fa-solid fa-robot"></i></div>
          <h4>Compass AI</h4>
          <p>Recurly's AI assistant inside the admin. Ask it questions about your account, interpret metrics, or get configuration recommendations — available 24/7.</p>
          <a href="https://docs.recurly.com" target="_blank" rel="noopener noreferrer" class="rc-next-cta-ghost"><i class="fa-solid fa-arrow-up-right-from-square"></i> Explore Compass AI →</a>
        </div>
        <div class="rc-next-item">
          <div class="rc-next-item-icon"><i class="fa-solid fa-graduation-cap"></i></div>
          <h4>Proactive learning paths</h4>
          <p>Watch your inbox — we'll send <strong>Navigate Learning Paths</strong> curated to your individual progress and performance in Recurly.</p>
          <a href="mailto:RecurlyNavigate@Recurly.com?subject=Whitelist%20Recurly%20Navigate" class="rc-next-cta-ghost"><i class="fa-solid fa-envelope"></i> Whitelist our email →</a>
        </div>
      </div>
    </div>

    <!-- Section: Monthly scorecard video -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-clipboard-list rc-fa-section"></i> Prepare for your monthly metrics scorecard</h2>
      <p>Watch this trail guide as it walks you through your Monthly Metrics Scorecard. You'll begin receiving your personalized snapshot via email on the <strong>second Tuesday of the month</strong> after you've been in production for <strong>90 days</strong>.</p>

      <div class="rc-video-card">
        <div class="rc-video-header">
          <h4>Understanding your monthly metrics scorecard</h4>
          <span>~5 min</span>
        </div>
        <div class="rc-video-embed">
          <iframe src="https://share.synthesia.io/embeds/videos/a9ab0aa1-ef60-4b08-aaa8-95c0275e245f" loading="lazy" title="Understanding Your Monthly Metrics Scorecard" allow="encrypted-media; fullscreen; microphone; screen-wake-lock;" allowfullscreen></iframe>
        </div>
        <div class="rc-video-caption">A guided walkthrough on how to read and act on your monthly performance data.</div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>Keep the cadence going</strong>
          <p>Treat your Benchmarks Dashboard like a monthly scorecard — review it at the start of each month, compare to the prior period, and flag any metric that moved more than expected.</p>
        </div>
      </div>
    </div>

    <!-- Continue your journey -->
    <div class="rc-next-steps"style="display: none;">
      <h3><i class="fa-solid fa-compass rc-fa-section"></i> Continue your journey</h3>
      <div class="rc-next-grid-journey">

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-next-card">
          <div class="rc-next-card-tag">Recommended next</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-bullseye"></i></div>
          <h4>Acquire</h4>
          <p>Now that your systems are optimized and you understand your metrics, explore the Acquire pillar to grow your subscriber base with confidence.</p>
          <div class="rc-next-card-arrow">Explore Acquire →</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-next-card">
          <div class="rc-next-card-tag">Explore the pillar</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-rocket"></i></div>
          <h4>All Launch paths</h4>
          <p>See every learning path in the Launch pillar.</p>
          <div class="rc-next-card-arrow">View Launch →</div>
        </a>

        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-next-card">
          <div class="rc-next-card-tag">Live session</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-microphone"></i></div>
          <h4>Global Office Hours</h4>
          <p>Bring your questions to our CSMs live. Sessions run weekly.</p>
          <div class="rc-next-card-arrow">Register →</div>
        </a>

      </div>
    </div>

    <!-- Path navigation -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-retention-metrics" class="rc-btn-prev">← Revenue &amp; recovery</a>
      <span class="rc-lp-nav-indicator">5 of 5</span>
      <span class="rc-btn-complete"><i class="fa-solid fa-circle-check"></i> Path complete!</span>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> All your Launchpad resources</h3>
      <div class="rc-resource-links">
        <a href="https://go.recurly.com/Recurly_Navigate-Launchpad-Complete-Cheatsheet.html" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Full Launchpad Cheatsheet</a>
        <a href="https://go.recurly.com/Recurly-Navigate-Metrics-Cheatsheet.html" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Launchpad Metrics Cheatsheet</a>
        <a href="https://go.recurly.com/recurly_navigate_resource_guide.html" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Navigate Resource Guide</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Support</a>
      </div>
    </div>

    <!-- Footer nav — Course pattern -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">

        <div class="rc-footer-section">
          <span class="rc-footer-label">Launchpad Phase Two</span>
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