---
title: 'Launchpad Phase 2: Mastering Metrics'
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
  position: relative;
  z-index: 1;
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

/* CALLOUT */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: #32312D; }
.rc-callout-tip { background: #F1EFE3; border-left: 4px solid #0D0D0B; }
.rc-callout-tip .rc-callout-body > strong { color: #0D0D0B; }

/* PHASE 1 HANDOFF CARD */
.rc-handoff-card {
  background: #0D0D0B !important;
  border-radius: 14px; padding: 28px 32px; margin-bottom: 32px;
  border: 1px solid rgba(255,255,255,0.08);
}
.rc-handoff-card h3 {
  font-size: .88rem; font-weight: 800; text-transform: uppercase;
  letter-spacing: .8px; color: #FFD706 !important; margin: 0 0 10px;
  display: flex; align-items: center; gap: 8px;
}
.rc-handoff-card p { font-size: .92rem; color: #CCC9B8 !important; line-height: 1.6; margin: 0 0 18px; }
.rc-handoff-checklist { list-style: none; margin: 0; padding: 0; display: flex; flex-direction: column; gap: 8px; }
.rc-handoff-item { display: flex; align-items: center; gap: 10px; font-size: .9rem; color: #CCC9B8 !important; }
.rc-handoff-item i { color: #FFD706 !important; font-size: .9rem; flex-shrink: 0; }

/* METRIC CARDS (3-col grid) */
.rc-metric-grid { display: grid; grid-template-columns: 1fr; gap: 12px; margin: 0 0 32px; }
.rc-metric-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 12px; padding: 18px 20px; }
.rc-metric-card-icon { font-size: 1.2rem; color: #FF8200; margin-bottom: 10px; line-height: 1; }
.rc-metric-card h4 { font-size: .92rem; font-weight: 800; color: #0D0D0B; margin: 0 0 4px; }
.rc-metric-card p { font-size: .83rem; color: #807D73; line-height: 1.45; margin: 0; }
@media(max-width:768px){ .rc-metric-grid { grid-template-columns: 1fr 1fr; } }

/* SCORECARD PREVIEW CARD */
.rc-scorecard-card {
  background: #0D0D0B !important;
  border-radius: 14px; padding: 28px 32px; margin: 0 0 32px;
  border: 1px solid rgba(255,255,255,0.08);
}
.rc-scorecard-card h3 {
  font-size: 1rem; font-weight: 800; color: #FF8200 !important;
  margin: 0 0 12px; display: flex; align-items: center; gap: 8px;
}
.rc-scorecard-card p { font-size: .92rem; color: #CCC9B8 !important; line-height: 1.6; margin: 0 0 20px; }
.rc-scorecard-card strong { color: #ffffff !important; }
.rc-scorecard-preview { background: rgba(255,255,255,0.04); border: 1px solid rgba(255,255,255,0.10); border-radius: 10px; padding: 18px 20px; }
.rc-scorecard-preview-label {
  font-size: .72rem; font-weight: 800; text-transform: uppercase; letter-spacing: .8px;
  color: #FFD706 !important; margin: 0 0 10px; display: flex; align-items: center; gap: 6px;
}
.rc-scorecard-preview-img { width: 100%; border-radius: 6px; display: block; }

/* WEBINAR CLIP CARD */
.rc-clip-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 14px; padding: 22px 24px; margin: 0 0 32px; }
.rc-clip-badge { display: inline-flex; align-items: center; gap: 6px; background: #0D0D0B; color: #FF8200; border-radius: 6px; padding: 4px 10px; font-size: .73rem; font-weight: 800; text-transform: uppercase; letter-spacing: .5px; margin-bottom: 12px; }
.rc-clip-card h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B; margin: 0 0 8px; }
.rc-clip-card p { font-size: .9rem; color: #32312D; line-height: 1.6; margin: 0 0 14px; }
.rm-Markdown.markdown-body .rc-guide a.rc-clip-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-clip-link { color: #FF8200 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-clip-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-clip-link:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* CARD GRID (2-col support cards) */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-feature-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; color: #0D0D0B; }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B; margin: 0; }
.rc-feature-card p { font-size: .88rem; color: #807D73; line-height: 1.55; margin: 0; flex-grow: 1; }
.rm-Markdown.markdown-body .rc-guide .rc-feature-card a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-feature-card a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide .rc-feature-card a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide .rc-feature-card a:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }
@media(max-width:768px){ .rc-card-grid { grid-template-columns: 1fr; } }

/* TOC CARDS — orange accent for Phase 2 */
.rc-toc-list { display: flex; flex-direction: column; gap: 10px; margin: 0 0 32px; }
.rc-toc-card { display: grid; grid-template-columns: 44px 1fr 32px; align-items: center; gap: 16px; background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 12px; padding: 18px 22px; transition: all .2s ease; }
.rm-Markdown.markdown-body .rc-guide a.rc-toc-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-toc-card { color: #32312D !important; border-bottom: 1px solid #CCC9B8 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-toc-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-toc-card:hover { border-color: #FF8200; border-bottom: 1px solid #FF8200 !important; box-shadow: 0 4px 14px rgba(255,130,0,0.18); transform: translateX(3px); color: #32312D !important; }
.rc-toc-num { width: 36px; height: 36px; border-radius: 50%; background: #0D0D0B; color: #FF8200; display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; }
.rc-toc-body h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B; margin: 0 0 4px; }
.rc-toc-body p { font-size: .88rem; color: #807D73; line-height: 1.5; margin: 0; }
.rc-toc-arrow { font-size: 1.1rem; color: #CCC9B8; text-align: right; transition: color .2s; }
.rc-guide a.rc-toc-card:hover .rc-toc-arrow { color: #FF8200; }
@media(max-width:768px){ .rc-toc-card { grid-template-columns: 36px 1fr 24px; padding: 14px 16px; } }

/* PATH NAV BUTTONS — orange accent for Phase 2 */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: #CCC9B8; letter-spacing: .5px; }
/* rc-btn-prev — double-prefix + :not() → (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
/* rc-btn-path — orange for Phase 2 */
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
  .rc-metric-grid { grid-template-columns: 1fr 1fr; }
  .rc-card-grid { grid-template-columns: 1fr; }
  .rc-toc-card { grid-template-columns: 36px 1fr 24px; padding: 14px 16px; }
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
      <div class="rc-lp-hero-title"><h1>Mastering metrics</h1></div>
      <p>Phase 1 locked in the configurations that protect your revenue. Phase 2 builds your fluency with the six KPIs that show how your subscription business is performing.</p>
    </div>

    <!-- Nav (non-sticky + open — Course Overview page) -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Path overview
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-benchmarks-dashboard" class="rc-sticky-link"><span class="rc-step-badge">1</span> Benchmarks &amp; reporting</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-acquisition-metrics" class="rc-sticky-link"><span class="rc-step-badge">2</span> Acquisition &amp; decline</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-churn-metrics" class="rc-sticky-link"><span class="rc-step-badge">3</span> Churn metrics</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-retention-metrics" class="rc-sticky-link"><span class="rc-step-badge">4</span> Revenue &amp; recovery</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-review" class="rc-sticky-link"><span class="rc-step-badge">5</span> Review &amp; resources</a>

      </div></div></div>
    </details>

    <!-- Section: Picking up from Phase 1 -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-gear rc-fa-section"></i> Picking up from Phase 1</h2>
      <div class="rc-handoff-card">
        <h3><i class="fa-solid fa-circle-check" style="color:#FFD706;font-size:1rem;"></i> Phase 1 complete</h3>
        <p>You've set up the systems that protect and recover your revenue automatically. Before continuing, confirm these are in place:</p>
        <ul class="rc-handoff-checklist">
          <li class="rc-handoff-item"><i class="fa-solid fa-circle-check"></i> Dunning &amp; Intelligent Retry configured</li>
          <li class="rc-handoff-item"><i class="fa-solid fa-circle-check"></i> Account Updater enabled</li>
          <li class="rc-handoff-item"><i class="fa-solid fa-circle-check"></i> Branded emails &amp; invoices</li>
          <li class="rc-handoff-item"><i class="fa-solid fa-circle-check"></i> Gateway Failover in place</li>
        </ul>
      </div>
      <p>Phase 2 builds on that foundation. You'll measure performance through Recurly Analytics, learn to read your six core KPIs, and start using data to make informed decisions about your subscription business.</p>
    </div>



    <!-- Section: Your 6 core metrics -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-chart-line rc-fa-section"></i> Your 7 core benchmark metrics</h2>
      <p>These are the metrics that drive subscription growth. They show how well you're acquiring subscribers, how much revenue you're keeping, and how effectively your recovery systems are working.</p>

      <div class="rc-metric-grid">
        <div class="rc-metric-card">
          <div class="rc-metric-card-icon"><i class="fa-solid fa-arrow-trend-up"></i></div>
          <h4>Acquisition rate</h4>
          <p>New subscribers / active subscribers at start of period</p>
        </div>
        <div class="rc-metric-card">
          <div class="rc-metric-card-icon"><i class="fa-solid fa-bolt"></i></div>
          <h4>Sign-up decline rate</h4>
          <p>Failed sign-up attempts / total sign-up attempts</p>
        </div>
        <div class="rc-metric-card">
          <div class="rc-metric-card-icon"><i class="fa-solid fa-right-from-bracket"></i></div>
          <h4>Voluntary churn rate</h4>
          <p>Subscribers who chose to cancel</p>
        </div>
        <div class="rc-metric-card">
          <div class="rc-metric-card-icon"><i class="fa-solid fa-credit-card"></i></div>
          <h4>Involuntary churn rate</h4>
          <p>Subscribers lost to dunning expiration</p>
        </div>
        <div class="rc-metric-card">
          <div class="rc-metric-card-icon"><i class="fa-solid fa-circle-check"></i></div>
          <h4>Renewal invoice paid rate</h4>
          <p>Percentage of renewals collected successfully</p>
        </div>
        <div class="rc-metric-card">
          <div class="rc-metric-card-icon"><i class="fa-solid fa-rotate"></i></div>
          <h4>Dunning recovery rate</h4>
          <p>Invoices paid / total invoices entering dunning</p>
        </div>
        <div class="rc-metric-card">
          <div class="rc-metric-card-icon"><i class="fa-solid fa-arrow-trend-down"></i></div>
          <h4>Decline rate at renewal</h4>
          <p>Percentage of failed renewal attempts</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-file-arrow-down"></i></div>
        <div class="rc-callout-body">
          <strong>Download the Metrics Cheatsheet</strong>
          <p>Before diving in, grab the <a href="https://go.recurly.com/Recurly-Navigate-Metrics-Cheatsheet.html" target="_blank" rel="noopener noreferrer">Launchpad Metrics Cheatsheet</a>. It lists every KPI definition, calculation formula, and which direction you want each metric to move.</p>
        </div>
      </div>
    </div>

    <!-- Section: Your Monthly Metrics Scorecard -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-clipboard-list rc-fa-section"></i> Your monthly metrics scorecard</h2>
      <div class="rc-scorecard-card">
        <h3><i class="fa-solid fa-chart-bar" style="color:#FF8200;font-size:1rem;"></i> What you're working toward</h3>
        <p>After completing Launchpad, you'll begin receiving your <strong>Monthly Metrics Scorecard</strong> — a complete snapshot of your previous full fiscal month in Recurly. It shows your six core KPIs at a glance so you can track performance and compare against your own benchmarks over time.</p>
        <p>Scorecards are delivered by email on the first Tuesday of each month, starting 90 days after going live. You'll learn how to read and act on yours at the end of this course.</p>
        <div class="rc-scorecard-preview">
          <div class="rc-scorecard-preview-label"><i class="fa-solid fa-eye" style="font-size:.75rem;"></i> Sneak peek</div>
          <img class="rc-scorecard-preview-img" src="https://go.recurly.com/rs/439-LSC-903/images/Monthly%20scorecard%20sample.png" alt="Monthly metrics scorecard sample">
        </div>
      </div>
    </div>

    <!-- Section: Bonus webinar -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-circle-play rc-fa-section"></i> Get a head start: advanced reporting</h2>
      <div class="rc-clip-card">
        <div class="rc-clip-badge"><i class="fa-solid fa-circle-play"></i> Webinar on demand</div>
        <h4>Beyond the dashboard: reporting drives growth</h4>
        <p>Director of Data Matthew Cryer walks through the Trendalyzer, hourly activation monitoring, and the four layers of Recurly reporting — including how to surface non-obvious growth insights that most merchants miss.</p>
        <a href="https://navigate.recurly.com/lunch-and-learn/reporting-drives-growth/" target="_blank" rel="noopener noreferrer" class="rc-clip-link"><i class="fa-solid fa-circle-play"></i> Watch on demand →</a>
      </div>
    </div>

    <!-- Section: What's in this course -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-list-check rc-fa-section"></i> What's in this course</h2>
      <p>Each module covers one metric area from definition to action. Work through them in order for the full picture, or jump to whichever topic is most relevant right now.</p>

      <div class="rc-toc-list">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-benchmarks-dashboard" class="rc-toc-card">
          <div class="rc-toc-num">1</div>
          <div class="rc-toc-body">
            <h4>Benchmarks &amp; reporting</h4>
            <p>Get oriented with Recurly Analytics, the Benchmarks Dashboard, and the Trendalyzer so you know where to find your performance data.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-acquisition-metrics" class="rc-toc-card">
          <div class="rc-toc-num">2</div>
          <div class="rc-toc-body">
            <h4>Acquisition &amp; decline</h4>
            <p>Understand your subscriber acquisition rate and sign-up decline rate — and what to do when either moves in the wrong direction.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-churn-metrics" class="rc-toc-card">
          <div class="rc-toc-num">3</div>
          <div class="rc-toc-body">
            <h4>Churn metrics</h4>
            <p>Learn the difference between voluntary and involuntary churn, how to calculate each, and which Recurly tools address them.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-retention-metrics" class="rc-toc-card">
          <div class="rc-toc-num">4</div>
          <div class="rc-toc-body">
            <h4>Revenue &amp; recovery</h4>
            <p>Measure your renewal invoice paid rate and dunning recovery rate — the two metrics that show how well your revenue protection is working.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-review" class="rc-toc-card">
          <div class="rc-toc-num">5</div>
          <div class="rc-toc-body">
            <h4>Review &amp; resources</h4>
            <p>Check your understanding, explore your monthly scorecard, and access all resources from across the course in one place.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>How to use this Path</strong>
          <p>Each module includes definitions, calculation formulas, benchmarks, and guidance on what to do when a metric is off. Use the navigation menu to move between modules — you can return to any step at any time.</p>
        </div>
      </div>
    </div>

   <!-- Section: Support and resources -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-headset rc-fa-section"></i> Support &amp; resources</h2>
      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-headset"></i></div>
          <h4>Your customer support team</h4>
          <p>Need technical support? Recurly Support is available. Reach us at <a href="mailto:support@recurly.com">support@recurly.com</a>.</p>
        </div>
<div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-bullhorn"></i></div>
          <h4>Customer success office hours</h4>
          <p>Have questions as you work through Launchpad? Our CSMs are here to help you live. <a href="https://navigate.recurly.com/global-office-hours/">Choose a session</a> that works for you.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-file-arrow-down"></i></div>
          <h4>Download your resource guide</h4>
          <p>A quick-reference guide to all Recurly support links, documentation, and program resources. <a href="https://go.recurly.com/recurly_navigate_resource_guide.html" target="_blank" rel="noopener noreferrer">Navigate Resource Guide ↗</a></p>
        </div>
 <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-book-atlas"></i></div>
          <h4>Navigate resource library</h4>
          <p>A one-stop location for all links to Recurly support offerings, documentation, updates, events, and more. <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-resource-library" target="_blank" rel="noopener noreferrer">Go to the Resource library</a></p>
        </div>
</div>

    <!-- Path navigation -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-review" class="rc-btn-prev">← Phase 1: Review &amp; resources</a>
      <span class="rc-lp-nav-indicator">Overview</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-benchmarks-dashboard" class="rc-btn-path">Next: Benchmarks &amp; reporting →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://go.recurly.com/Recurly-Navigate-Metrics-Cheatsheet.html" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Launchpad Metrics Cheatsheet</a>
        <a href="https://navigate.recurly.com/lunch-and-learn/reporting-drives-growth/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-circle-play"></i> Beyond the dashboard — webinar on demand</a>
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
