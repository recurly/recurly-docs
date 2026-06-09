---
title: Code Test Course
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

/* ── FONT AWESOME ICON HELPERS ── */
.rc-fa-announce { color: #0D0D0B; font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark  { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: #0D0D0B; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: #0D0D0B; font-size: 1rem; }

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
.rc-guide a.rc-announce-link {
  color: #0D0D0B !important; font-weight: 800; white-space: nowrap;
  padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px;
  transition: background 0.2s; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-announce-link:hover { background: rgba(0,0,0,0.20); color: #0D0D0B !important; }

/* ── TOP NAV / BACK LINK ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* ── HERO ── */
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

/* ── NAV — sticky + collapsed (LP Overview) ── */
details.rc-sticky-nav-wrap {
  position: sticky; top: 0; z-index: 100;
  background-color: #F1EFE3;
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px 0; border-radius: 12px;
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
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: #32312D; margin: 0 0 16px; }

/* ── CALLOUTS ── */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: #32312D; }
.rc-callout-tip { background: #F1EFE3; border-left: 4px solid #0D0D0B; }
.rc-callout-tip .rc-callout-body > strong { color: #0D0D0B; }
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-callout-body a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide .rc-callout-body a:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* ── PHASE BANNERS (dark cards) ── */
.rc-phase-banner {
  background: #0D0D0B !important; border-radius: 14px;
  padding: 24px 28px; margin-bottom: 16px;
  border: 1px solid rgba(255,255,255,0.08);
}
.rc-phase-banner h3 { font-size: .98rem; font-weight: 800; margin: 0 0 6px; text-transform: uppercase; letter-spacing: .8px; }
.rc-phase-banner h3.launch-phase { color: #CCC9B8 !important; }
.rc-phase-banner h3.metrics-phase { color: #FFD706 !important; }
.rc-phase-banner > p { font-size: .87rem; color: #CCC9B8 !important; margin: 0 0 14px; line-height: 1.55; }
.rc-phase-step { display: flex; align-items: center; gap: 10px; padding: 7px 0; border-bottom: 1px solid rgba(255,255,255,0.07); font-size: .85rem; color: #CCC9B8 !important; }
.rc-phase-step:last-child { border-bottom: none; }
.rc-phase-dot { width: 24px; height: 24px; border-radius: 50%; background: #FFD706; color: #0D0D0B; font-size: 11px; font-weight: 800; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
.rc-phase-dot.orange { background: #FF8200 !important; color: #fff !important; }

/* ── SUPPORT CARDS ── */
.rc-card-grid-2col { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 20px 0 32px; }
.rc-feature-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B; margin: 0; }
.rc-feature-card p { font-size: .88rem; color: #807D73; line-height: 1.55; margin: 0; flex-grow: 1; }
.rm-Markdown.markdown-body .rc-guide a.rc-support-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-support-link {
  display: inline-flex; align-items: center; gap: 6px;
  background: #FFD706; color: #0D0D0B !important;
  padding: 9px 16px; border-radius: 8px; font-weight: 700; font-size: .82rem;
  width: fit-content; margin-top: 4px; border-bottom: 0 !important; transition: opacity .2s;
}
.rm-Markdown.markdown-body .rc-guide a.rc-support-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-support-link:hover { opacity: .88; color: #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-support-link-ghost:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-support-link-ghost {
  display: inline-flex; align-items: center; gap: 6px;
  background: transparent; color: #0D0D0B !important;
  padding: 9px 16px; border-radius: 8px; font-weight: 700; font-size: .82rem;
  width: fit-content; margin-top: 4px; border: 1px solid #CCC9B8 !important;
  border-bottom: 1px solid #CCC9B8 !important; transition: all .2s;
}
.rm-Markdown.markdown-body .rc-guide a.rc-support-link-ghost:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-support-link-ghost:hover { border-color: #0D0D0B !important; border-bottom-color: #0D0D0B !important; color: #0D0D0B !important; }

/* ── VIDEO CARD ── */
.rc-video-card { border: 1px solid #CCC9B8; border-radius: 14px; overflow: hidden; margin: 0 0 40px; }
.rc-video-header { background: #0D0D0B; padding: 16px 22px; display: flex; align-items: center; gap: 10px; }
.rc-video-header h4 { font-size: .88rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: #FFD706 !important; margin: 0; }
.rc-video-header span { font-size: .78rem; color: #CCC9B8 !important; margin-left: auto; }
.rc-video-embed { position: relative; overflow: hidden; aspect-ratio: 16/9; background: #0D0D0B; }
.rc-video-embed iframe { position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; }
.rc-video-caption { padding: 12px 22px; font-size: .83rem; color: #807D73; background: #F1EFE3; border-top: 1px solid #CCC9B8; line-height: 1.5; }

/* ── TOC CARDS ── */
.rc-toc-list { display: flex; flex-direction: column; gap: 10px; margin: 0 0 40px; }
.rc-toc-card {
  display: grid; grid-template-columns: 44px 1fr 32px;
  align-items: center; gap: 16px;
  background: #FFFDF2; border: 1px solid #CCC9B8;
  border-radius: 12px; padding: 18px 22px;
  transition: all .2s ease;
}
.rm-Markdown.markdown-body .rc-guide a.rc-toc-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-toc-card { border-bottom: 1px solid #CCC9B8 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-toc-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-toc-card:hover { border-color: #CCC9B8; border-bottom: 1px solid #CCC9B8 !important; box-shadow: 0 4px 14px rgba(204,201,184,0.30); transform: translateX(3px); }
.rc-toc-num {
  width: 36px; height: 36px; border-radius: 50%;
  background: #0D0D0B; color: #FFD706;
  display: flex; align-items: center; justify-content: center;
  font-size: .85rem; font-weight: 800; flex-shrink: 0;
}
.rc-toc-body h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B; margin: 0 0 4px; }
.rc-toc-body p { font-size: .88rem; color: #807D73; line-height: 1.5; margin: 0; }
.rc-toc-arrow { font-size: 1.1rem; color: #CCC9B8; text-align: right; transition: color .2s; }
.rc-guide a.rc-toc-card:hover .rc-toc-arrow { color: #CCC9B8; }

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
.rc-guide a.rc-resource-link {
  color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px;
  text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem;
  transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; }

/* ── FOOTER ── */
.rc-footer-nav { border-top: 1px solid #CCC9B8; padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: #32312D; background: #F1EFE3; padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link {
  color: #807D73 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem;
  transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
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
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-card-grid-2col { grid-template-columns: 1fr; }
  .rc-toc-card { grid-template-columns: 36px 1fr 24px; padding: 14px 16px; }
}
</style>

<div class="rc-guide">

  <!-- BACK LINK -->
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-back-link">← Back to Launch</a>
  </div>

  <div class="rc-content-wrap">

    <!-- ANNOUNCEMENT BAR (hidden by default — add rc-active class to show) -->
    <div class="rc-announce-bar">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Join our CSMs for a live session — bring your Launchpad questions.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
    </div>

    <!-- HERO -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png" alt="Launch"> Launch · Launchpad
      </div>
      <div class="rc-lp-hero-title"><h1>Welcome to Launchpad</h1></div>
      <p>Your step-by-step guide to optimizing Recurly, mastering your metrics, and building a thriving subscription business — starting right now.</p>
    </div>

    <!-- NAV — sticky + collapsed (LP Overview) -->
    <details class="rc-sticky-nav-wrap">
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Launchpad overview
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-production-testing" class="rc-sticky-link"><span class="rc-step-badge">1</span> Production testing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-dunning-optimization" class="rc-sticky-link"><span class="rc-step-badge">2</span> Dunning</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-account-updater" class="rc-sticky-link"><span class="rc-step-badge">3</span> Account Updater</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-branding" class="rc-sticky-link"><span class="rc-step-badge">4</span> Branding</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-gateway-failover" class="rc-sticky-link"><span class="rc-step-badge">5</span> Gateway failover</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-review" class="rc-sticky-link"><span class="rc-step-badge">6</span> Review &amp; resources</a>
      </div></div></div>
    </details>

    <!-- SECTION: What is Launchpad -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-map-location-dot rc-fa-section"></i> You're live — now let's optimize</h2>
      <p>Going live is just the beginning. Launchpad is your guided program to make sure Recurly is working as hard as possible for your business from day one.</p>

      <h3 style="font-size:1rem;font-weight:800;color:#0D0D0B;margin:0 0 12px;">What is Navigate Launchpad?</h3>
      <p>Navigate Launchpad is Recurly's self-paced optimization program for new merchants. It's designed to be completed within 90 days of going live in production — walking you through the most impactful configurations, best practices, and data insights, one step at a time.</p>
      <p>You don't need to rush. Each module builds on the last. Work through them at your own pace and come back anytime.</p>

      <!-- VIDEO — featured, above content -->
      <div class="rc-video-card">
        <div class="rc-video-header">
          <h4><i class="fa-solid fa-circle-play" style="margin-right:6px;"></i> Trail guide: welcome &amp; UI walkthrough</h4>
          <span>~5 min</span>
        </div>
        <div class="rc-video-embed">
          <iframe src="https://share.synthesia.io/embeds/videos/ee258c32-42a5-4b28-81f9-47b13ec52fe2" loading="lazy" title="Navigate Launchpad — Welcome and UI Walkthrough" allowfullscreen allow="encrypted-media; fullscreen; microphone; screen-wake-lock;"></iframe>
        </div>
        <div class="rc-video-caption">Get oriented with Recurly's UI, admin navigation, and key support resources.</div>
      </div>

    </div>

    <!-- SECTION: Two-phase journey -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-route rc-fa-section"></i> Your two-phase journey</h2>

      <div class="rc-phase-banner">
        <div style="display:flex;align-items:flex-start;gap:16px;">
          <i class="fa-solid fa-gear" style="color:#CCC9B8 !important;font-size:1.4rem;flex-shrink:0;margin-top:2px;"></i>
          <div style="flex:1;">
            <h3 class="launch-phase">Phase 1: Optimization</h3>
            <p>Lock in the configurations that protect your revenue and deliver a polished subscriber experience.</p>
            <div class="rc-phase-step"><div class="rc-phase-dot">1</div> Final production testing</div>
            <div class="rc-phase-step"><div class="rc-phase-dot">2</div> Optimize your dunning strategy</div>
            <div class="rc-phase-step"><div class="rc-phase-dot">3</div> Enable Account Updater</div>
            <div class="rc-phase-step"><div class="rc-phase-dot">4</div> Brand your emails &amp; invoices</div>
            <div class="rc-phase-step"><div class="rc-phase-dot">5</div> Set up gateway failover</div>
          </div>
        </div>
      </div>

      <div class="rc-phase-banner">
        <div style="display:flex;align-items:flex-start;gap:16px;">
          <i class="fa-solid fa-chart-line" style="color:#FFD706 !important;font-size:1.4rem;flex-shrink:0;margin-top:2px;"></i>
          <div style="flex:1;">
            <h3 class="metrics-phase">Phase 2: Mastering metrics</h3>
            <p>Understand the six core KPIs that drive subscription growth, retention, and revenue recovery.</p>
            <div class="rc-phase-step"><div class="rc-phase-dot orange">1</div> Benchmarks dashboard &amp; reporting tools</div>
            <div class="rc-phase-step"><div class="rc-phase-dot orange">2</div> Subscriber acquisition &amp; sign-up decline rate</div>
            <div class="rc-phase-step"><div class="rc-phase-dot orange">3</div> Voluntary &amp; involuntary churn</div>
            <div class="rc-phase-step"><div class="rc-phase-dot orange">4</div> Renewal invoice paid rate &amp; recovered revenue</div>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>How to use Launchpad</strong>
          <p>Each module includes a trail guide video, step-by-step setup guidance, best practices, and a completion checklist. Use the navigation menu above to move between modules — you can return to any step at any time.</p>
        </div>
      </div>
    </div>

    <!-- SECTION: Table of contents -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-list-check rc-fa-section"></i> What's inside</h2>
      <p>Launchpad is organized as a single learning path. Work through each topic in order, or jump to the one most relevant to you right now.</p>

      <div class="rc-toc-list">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-production-testing" class="rc-toc-card">
          <div class="rc-toc-num">1</div>
          <div class="rc-toc-body">
            <h4>Production testing</h4>
            <p>Confirm your integration is working end-to-end in production before your first real subscribers arrive.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-dunning-optimization" class="rc-toc-card">
          <div class="rc-toc-num">2</div>
          <div class="rc-toc-body">
            <h4>Dunning</h4>
            <p>Configure your failed payment retry logic and email cadence to maximize involuntary churn recovery.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-account-updater" class="rc-toc-card">
          <div class="rc-toc-num">3</div>
          <div class="rc-toc-body">
            <h4>Account Updater</h4>
            <p>Automatically keep card-on-file data current so payment failures caused by stale credentials don't reach your dunning queue.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-branding" class="rc-toc-card">
          <div class="rc-toc-num">4</div>
          <div class="rc-toc-body">
            <h4>Branding</h4>
            <p>Apply your brand to subscriber-facing emails and invoices for a consistent, professional experience.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-gateway-failover" class="rc-toc-card">
          <div class="rc-toc-num">5</div>
          <div class="rc-toc-body">
            <h4>Gateway failover</h4>
            <p>Set up a backup payment gateway so a single-gateway outage doesn't silently stop your revenue.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-review" class="rc-toc-card">
          <div class="rc-toc-num">6</div>
          <div class="rc-toc-body">
            <h4>Review &amp; resources</h4>
            <p>Consolidate what you've configured, check your work against the full optimization checklist, and access all path resources in one place.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
      </div>
    </div>

    <!-- SECTION: Support -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-headset rc-fa-section"></i> Get help along the way</h2>
      <p>Each module in Launchpad is designed to be self-serve, but support is available whenever you need it.</p>

      <div class="rc-card-grid-2col">
        <div class="rc-feature-card">
          <h4><i class="fa-solid fa-headset rc-fa-section" style="margin-right:6px;"></i> Your customer support team</h4>
          <p>Have questions as you work through Launchpad? Recurly Support is here to help.</p>
          <a href="mailto:support@recurly.com" class="rc-support-link"><i class="fa-regular fa-envelope"></i> support@recurly.com</a>
        </div>
        <div class="rc-feature-card">
          <h4><i class="fa-regular fa-file-lines rc-fa-section" style="margin-right:6px;"></i> Navigate resource guide</h4>
          <p>A quick-reference guide to all Recurly support links, documentation, and program resources.</p>
          <a href="https://go.recurly.com/recurly_navigate_resource_guide.html" target="_blank" rel="noopener noreferrer" class="rc-support-link-ghost"><i class="fa-solid fa-arrow-down"></i> Download resource guide</a>
        </div>
      </div>
    </div>

    <!-- PATH NAV -->
    <div class="rc-lp-nav">
      <span class="rc-btn-start">Start</span>
      <span class="rc-lp-nav-indicator">Overview</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-production-testing" class="rc-btn-path">Next: Production testing →</a>
    </div>

    <!-- RESOURCES -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly documentation</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
      </div>
    </div>

    <!-- FOOTER NAV — LP Overview pattern -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Launchpad</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one" class="rc-footer-link">Launchpad overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-production-testing" class="rc-footer-link">Production testing</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-dunning-optimization" class="rc-footer-link">Dunning</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-account-updater" class="rc-footer-link">Account Updater</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-branding" class="rc-footer-link">Branding</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-gateway-failover" class="rc-footer-link">Gateway failover</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-review" class="rc-footer-link">Review &amp; resources</a>
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
