---
title: 'Payments Hub: Review & resources'
excerpt: >-
  Recap your progress through the Payments Hub learning path with a summary of
  all five dashboards and key metrics to watch. Access on-demand walkthroughs,
  register for live office hours, and explore deep-dive documentation to
  optimize your payment strategy.
deprecated: false
hidden: false
metadata:
  keywords:
    - Payment analytics
    - recurring revenue metrics
    - Recurly support
    - payment health monitoring
    - revenue recovery
    - Payments Hub.
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
/* FA6 FONT RESTORE — (0,0,2,0) beats wildcard (0,0,1,0); must follow wildcard */
.rc-guide [class^="fa-"],
.rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide .fa-brands,
.rc-guide [class*="fa-brands"] { font-family: "Font Awesome 6 Brands" !important; }

/* ── NAVIGATE MASTER ARMOR — (0,0,7,1) beats global section 1.1 rule (0,0,6,2) ── */
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
  font-family: "Polar", "Helvetica Neue", Helvetica, arial, sans-serif !important;
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
.rc-announce-bar { display: none; background: #FFD706; color: #0D0D0B; align-items: center; justify-content: space-between; padding: 10px 20px; font-size: .88rem; font-weight: 600; border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4; }
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 10px; flex: 1; flex-wrap: wrap; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-announce-link { color: #0D0D0B !important; font-weight: 800; white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; transition: background 0.2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-announce-link:hover { background: rgba(0,0,0,0.20); color: #0D0D0B !important; }

/* ── HERO ── */
.rc-hero { background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)), url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center; background-color: #0D0D0B; background-size: cover; color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0; }
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,88,16,0.20); border: 1px solid rgba(255,88,16,0.45); color: #FF5810; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: #FFFDF2; margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: #CCC9B8; line-height: 1.6; }

/* ── NAVIGATION MENU — Non-sticky, open (Course page) — Scale pillar ── */
details.rc-sticky-nav-wrap { position: relative; z-index: 1; background-color: #FF5810; box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px 0; border-radius: 12px; border: 1px solid rgba(0,0,0,0.08); overflow: hidden; }
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: #ffffff; }
/* Scale pillar: chevron must be white */
.rc-nav-chevron { font-size: .72rem; color: #ffffff; opacity: 0.55; line-height: 1; transition: transform 0.25s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
/* Scale nav: links must be white */
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link { color: #ffffff !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.20); color: #ffffff !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: #0D0D0B; color: #FFD706; font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-guide a.rc-sticky-link:hover .rc-step-badge { background: #FFD706; color: #0D0D0B; }
/* Active item — no persistent background (Known Issue #27) */
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #ffffff !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.20); color: #ffffff !important; }

/* ── SECTION HEADINGS ── */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: #0D0D0B; display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: #CCC9B8; }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: #32312D; margin: 0 0 16px; }

/* ── COMPLETION BANNER ── */
.rc-completion { background: #0D0D0B !important; border: 2px solid #FFD706 !important; border-radius: 16px; padding: 40px 36px; text-align: center; margin-bottom: 48px; }
.rc-completion-icon { font-size: 2.5rem; color: #FFD706 !important; margin-bottom: 16px; display: block; }
.rc-completion h2 { font-size: 1.5rem; font-weight: 800; color: #FFFDF2 !important; margin: 0 0 12px; }
.rc-completion p { color: #CCC9B8 !important; font-size: .95rem; line-height: 1.6; max-width: 580px; margin: 0 auto 24px; }
.rc-completion-actions { display: flex; flex-wrap: wrap; gap: 10px; justify-content: center; }
.rm-Markdown.markdown-body .rc-guide a.rc-completion-btn-primary:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-completion-btn-primary { background: #FFD706 !important; color: #0D0D0B !important; text-decoration: none !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; transition: all .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-completion-btn-primary:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-completion-btn-primary:hover { background: transparent !important; color: #FFD706 !important; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-completion-btn-secondary:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-completion-btn-secondary { background: transparent !important; color: #CCC9B8 !important; text-decoration: none !important; padding: 12px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid rgba(204,201,184,0.35) !important; border-bottom: 2px solid rgba(204,201,184,0.35) !important; transition: all .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-completion-btn-secondary:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-completion-btn-secondary:hover { border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; color: #FFFDF2 !important; }

/* ── CARD GRIDS ── */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-card-grid-3col { grid-template-columns: 1fr 1fr 1fr; }
.rc-feature-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: #FF5810; box-shadow: 0 4px 16px rgba(255,88,16,0.15); transform: translateY(-2px); }
.rc-feature-card-head { display: flex; align-items: center; gap: 10px; }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; color: #0D0D0B; }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B; margin: 0; }
.rc-feature-card h5 { font-size: .8rem; font-weight: 800; color: #0D0D0B; margin: 0; text-transform: uppercase; letter-spacing: .6px; }
.rc-feature-card p { font-size: .88rem; color: #807D73; line-height: 1.55; margin: 0; flex-grow: 1; }
.rc-feature-card p strong { color: #32312D; }
.rc-kount-note { font-size: .75rem; font-weight: 400; color: #807D73; margin-left: 6px; }

/* Full-width card */
.rc-card { background: #FFFDF2; border-radius: 16px; padding: 28px; border: 1px solid #CCC9B8; margin-bottom: 24px; transition: all .2s ease; }
.rc-card:hover { border-color: #FF5810; box-shadow: 0 4px 16px rgba(255,88,16,0.15); }
.rc-card p { font-size: .88rem; color: #807D73; line-height: 1.55; margin: 0; }
.rc-card p strong { color: #32312D; }

/* ── CALLOUTS ── */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: #32312D; }
.rc-callout-tip { background: #F1EFE3; border-left: 4px solid #0D0D0B; }
.rc-callout-tip .rc-callout-body > strong { color: #0D0D0B; }
/* Callout inline links */
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-callout-body a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide .rc-callout-body a:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* ── OFFICE HOURS CTA ── */
.rc-oh-cta { background: #0D0D0B !important; border: 2px solid #FFD706 !important; border-radius: 14px; padding: 32px 36px; margin: 32px 0; }
/* h4 must be display: block (default) so .rc-fa-dark renders above text — never display: flex */
.rc-oh-cta h4 { font-size: 1.05rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px; color: #FFD706 !important; }
.rc-oh-cta p { color: #CCC9B8 !important; font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
.rc-oh-cta p strong { color: #FFFDF2 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-oh-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-oh-btn { background: #FFD706 !important; color: #0D0D0B !important; text-decoration: none !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-oh-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-oh-btn:hover { background: transparent !important; color: #FFD706 !important; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }

/* ── PATH NAV ── */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: #CCC9B8; letter-spacing: .5px; }
/* rc-btn-prev — double-prefix + :not() → (0,0,8,1); hex borders (Known Issue #52) */
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
.rc-btn-complete { background: #F1EFE3; color: #0D0D0B !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #FFD706; cursor: default; user-select: none; }

/* ── CONTINUE YOUR JOURNEY ── */
.rc-next-steps { margin: 40px 0 0; }
.rc-next-steps h3 { font-size: .78rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: #807D73; margin: 0 0 16px; display: flex; align-items: center; gap: 8px; }
.rc-next-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; }
/* rc-next-card — (0,0,8,1) with explicit border-bottom (Known Issue #12) */
.rm-Markdown.markdown-body .rc-guide a.rc-next-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-next-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-bottom: 1px solid #CCC9B8 !important; border-radius: 12px; padding: 20px; color: #32312D !important; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rm-Markdown.markdown-body .rc-guide a.rc-next-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-next-card:hover { border-color: #FF5810; border-bottom: 1px solid #FF5810 !important; box-shadow: 0 4px 16px rgba(255,88,16,0.15); transform: translateY(-2px); }
.rc-next-card-tag { font-size: .68rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: #FF5810; margin-bottom: 2px; }
.rc-next-card-icon { font-size: 1.3rem; line-height: 1; color: #0D0D0B; }
.rc-next-card h4 { font-size: .95rem; font-weight: 800; color: #0D0D0B !important; margin: 0; line-height: 1.3; }
.rc-next-card p { font-size: .85rem; color: #807D73 !important; line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-next-card-arrow { font-size: .82rem; font-weight: 700; color: #FF8200; margin-top: 4px; }

/* ── RESOURCES ── */
.rc-resources { background: #F1EFE3; border-left: 4px solid #FF5810; border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: #807D73; margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
/* Resource link base color is #807D73 (gray) — NOT #32312D (Known Issue #16 / #41) */
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link { color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FF5810 !important; }

/* ── FOOTER NAV ── */
.rc-footer-nav { border-top: 1px solid #CCC9B8; padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: #32312D; background: #F1EFE3; padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
/* Footer links */
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link { color: #807D73 !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-footer-link:hover { color: #FF8200 !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-guide a.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid #F1EFE3; }

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-oh-cta { padding: 24px 20px; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-completion { padding: 28px 20px; }
  .rc-completion-actions { flex-direction: column; align-items: center; }
  .rc-card-grid, .rc-card-grid.rc-card-grid-3col { grid-template-columns: 1fr; }
  .rc-next-grid { grid-template-columns: 1fr; }
}
</style>

<div class="rc-guide">
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale" class="rc-back-link">← Back to Scale</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Announcement bar — hidden by default; add rc-active class before publishing -->
    <div class="rc-announce-bar">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Join our CSMs for a live Payments Hub walkthrough.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
    </div>

    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Scale">
        Scale
      </div>
      <div class="rc-lp-hero-title"><h1>Payments Hub review &amp; resources</h1></div>
      <p>You've made it through all five dashboards. Here's a quick recap of what you've covered, the key metrics to keep watching, and everything you need to go deeper.</p>
    </div>

    <!-- Navigation Menu — non-sticky + open (Course page) -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/83faba29b18efa915aa8aad0182d79d0f8328da2a9d7ea16504d8ee8a3cf3677-White_Home_Icon_1.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview" class="rc-sticky-link"><span class="rc-step-badge">1</span> Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing" class="rc-sticky-link"><span class="rc-step-badge">2</span> Payment processing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater" class="rc-sticky-link"><span class="rc-step-badge">3</span> Account updater</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries" class="rc-sticky-link"><span class="rc-step-badge">4</span> Payment retry recovery</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention" class="rc-sticky-link"><span class="rc-step-badge">5</span> Fraud prevention</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/c8c36df1d0552052603885aa5936c2474ddd7b3ece261aa70bac9fee6fd16017-White_Navigate_Home_Pin.png" alt=""> Review &amp; resources
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- Completion banner -->
    <div class="rc-completion">
      <i class="fa-solid fa-circle-check rc-completion-icon"></i>
      <h2>You've explored all 5 Payments Hub dashboards!</h2>
      <p>You now know what each dashboard shows, what to look for, and how to take action. Ready to go deeper? Watch the on-demand Payments Hub walkthrough or bring your questions to a live Global Office Hours session.</p>
      <div class="rc-completion-actions">
        <a href="https://navigate.recurly.com/lunch-and-learn/new-payment-hub/" target="_blank" rel="noopener noreferrer" class="rc-completion-btn-primary"><i class="fa-solid fa-circle-play"></i> Watch: Payments Hub walkthrough</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-completion-btn-secondary"><i class="fa-regular fa-calendar-days"></i> Join Office Hours</a>
      </div>
    </div>

    <!-- What you've covered -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-map rc-fa-section"></i> What you've covered</h2>
      <p>A quick summary of each dashboard and its primary purpose — use this as a reference when you return to Payments Hub.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-card-head">
            <div class="rc-feature-icon"><i class="fa-solid fa-house"></i></div>
            <h4>Overview</h4>
          </div>
          <p>Your top-level payment health snapshot. Shows <strong>overall, CIT, and MIT success rates</strong>, payment method distribution, geographic volume, and summary tiles for Account Updater, Retry Recovery, and Fraud blocking.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-card-head">
            <div class="rc-feature-icon"><i class="fa-solid fa-credit-card"></i></div>
            <h4>Payment processing</h4>
          </div>
          <p>The most actionable dashboard. Shows <strong>success rates by gateway, payment method, and card BIN</strong> — plus a ranked table of your top decline reasons, categorized as hard or soft.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-card-head">
            <div class="rc-feature-icon"><i class="fa-solid fa-rotate"></i></div>
            <h4>Account updater</h4>
          </div>
          <p>Tracks <strong>revenue protected through automatic card updates</strong> before payments fail. Shows update counts, revenue authorized on updated cards, update type breakdown, and activity by card network.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-card-head">
            <div class="rc-feature-icon"><i class="fa-solid fa-arrow-rotate-left"></i></div>
            <h4>Payment retry recovery</h4>
          </div>
          <p>Shows how much <strong>initially failed revenue was recovered through intelligent retries</strong> — including total recovered, recovery rate, revenue at risk, and which retry attempt captured the payment.</p>
        </div>
      </div>

      <div class="rc-card">
        <div class="rc-feature-card-head" style="margin-bottom:10px;">
          <div class="rc-feature-icon"><i class="fa-solid fa-shield-halved"></i></div>
          <h4 style="font-size:.98rem;font-weight:800;color:#0D0D0B;margin:0;">Fraud prevention <span class="rc-kount-note">Kount-enabled merchants only</span></h4>
        </div>
        <p>Consolidates your fraud blocking activity into one view. Shows <strong>blocked transactions, average risk score trends, fraud by payment method, and blocked volume by gateway.</strong> The risk score trend is your early warning system — a falling average often precedes a spike in blocks.</p>
      </div>
    </div>

    <!-- Metrics to watch -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-chart-line rc-fa-section"></i> Metrics to watch regularly</h2>
      <p>These are the numbers worth checking on a recurring basis — whether that's weekly, monthly, or when something looks off.</p>

      <div class="rc-card-grid rc-card-grid-3col">
        <div class="rc-feature-card" style="text-align:center; padding: 20px;">
          <div class="rc-feature-icon" style="margin-bottom:8px; font-size: 1.4rem;"><i class="fa-solid fa-chart-line"></i></div>
          <h5>Payment success rate</h5>
          <p>Your blended rate across all gateways and methods. Watch the trend over time — a downward drift often signals something worth investigating in Payment Processing.</p>
        </div>
        <div class="rc-feature-card" style="text-align:center; padding: 20px;">
          <div class="rc-feature-icon" style="margin-bottom:8px; font-size: 1.4rem;"><i class="fa-solid fa-arrow-rotate-left"></i></div>
          <h5>Retry recovery rate</h5>
          <p>What percentage of initially failed revenue is being recovered. Compare this to your overall dunning recovery for a complete picture.</p>
        </div>
        <div class="rc-feature-card" style="text-align:center; padding: 20px;">
          <div class="rc-feature-icon" style="margin-bottom:8px; font-size: 1.4rem;"><i class="fa-solid fa-rotate"></i></div>
          <h5>Revenue protected (AU)</h5>
          <p>The dollar value authorized on automatically updated cards. This is revenue that would likely have failed without Account Updater running.</p>
        </div>
        <div class="rc-feature-card" style="text-align:center; padding: 20px;">
          <div class="rc-feature-icon" style="margin-bottom:8px; font-size: 1.4rem;"><i class="fa-solid fa-triangle-exclamation"></i></div>
          <h5>Top decline reason</h5>
          <p>Your single most common reason for failed payments. Know whether it's a hard or soft decline — the response strategy is very different.</p>
        </div>
        <div class="rc-feature-card" style="text-align:center; padding: 20px;">
          <div class="rc-feature-icon" style="margin-bottom:8px; font-size: 1.4rem;"><i class="fa-solid fa-shield-halved"></i></div>
          <h5>Average risk score</h5>
          <p>For Kount users: monitor this as a leading indicator. A falling score often precedes a spike in blocked transactions — act early.</p>
        </div>
        <div class="rc-feature-card" style="text-align:center; padding: 20px;">
          <div class="rc-feature-icon" style="margin-bottom:8px; font-size: 1.4rem;"><i class="fa-solid fa-globe"></i></div>
          <h5>Success rate by region</h5>
          <p>Filter the Overview by country to check for geographic drop-offs. Regional differences may point to gateway routing or payment method gaps.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>Keep in mind</strong>
          <p>Payments Hub data begins from Q1 2026. Numbers in these dashboards reflect payment-level data — more granular than your standard Recurly billing analytics. Some figures may differ slightly from other dashboards in your account; both are accurate, measuring different things.</p>
        </div>
      </div>
    </div>

    <!-- Office Hours CTA -->
    <div class="rc-oh-cta">
      <h4><i class="fa-solid fa-headset rc-fa-dark"></i>Go deeper with a CSM</h4>
      <p><strong>Global Office Hours</strong> are the best place to walk through your own data with a Recurly Customer Success Manager. Bring your numbers, ask your questions, and leave with a clear next step. Sessions are free, open to all customers, and run regularly.</p>
      <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <!-- Path nav — completion state -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention" class="rc-btn-prev">← Fraud prevention</a>
      <span class="rc-lp-nav-indicator">6 of 6</span>
      <span class="rc-btn-complete"><i class="fa-solid fa-circle-check"></i> Path complete!</span>
    </div>

    <!-- Continue your journey -->
    <div class="rc-next-steps" style="display: none;>
      <h3><i class="fa-solid fa-compass rc-fa-section"></i> Continue your journey</h3>
      <div class="rc-next-grid">

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale" class="rc-next-card">
          <div class="rc-next-card-tag">Explore the pillar</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-bolt"></i></div>
          <h4>All Scale paths</h4>
          <p>See every learning path in the Scale pillar and find your next topic.</p>
          <div class="rc-next-card-arrow">View Scale →</div>
        </a>

        <a href="https://navigate.recurly.com/lunch-and-learn/new-payment-hub/" target="_blank" rel="noopener noreferrer" class="rc-next-card">
          <div class="rc-next-card-tag">On demand</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-circle-play"></i></div>
          <h4>Payments Hub walkthrough</h4>
          <p>Watch the full product walkthrough — all five dashboards in one session with a Recurly expert.</p>
          <div class="rc-next-card-arrow">Watch now →</div>
        </a>

        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-next-card">
          <div class="rc-next-card-tag">Live session</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-microphone"></i></div>
          <h4>Global Office Hours</h4>
          <p>Bring your questions to our CSMs live. Sessions run weekly and are free for all Recurly customers.</p>
          <div class="rc-next-card-arrow">Register →</div>
        </a>

      </div>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources &amp; documentation</h3>
      <div class="rc-resource-links">
        <a href="https://navigate.recurly.com/lunch-and-learn/new-payment-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-circle-play"></i> Payments Hub walkthrough (on demand)</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/payments-hub" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Payments Hub</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/api-transaction-errors" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Decline messages reference</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/retry-logic" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Intelligent retries documentation</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Account Updater learning path</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/kount" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Kount fraud prevention docs</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/user-roles-and-permissions" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> User roles &amp; permissions</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
      </div>
    </div>

    <!-- Footer nav -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <!-- Course footer: bare path name + descriptor; no "Course:" prefix; numbered links use "N. title" not "Step N:" -->
        <div class="rc-footer-section">
          <span class="rc-footer-label">Payments Hub: Getting started</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub" class="rc-footer-link">Path overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview" class="rc-footer-link">1. Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing" class="rc-footer-link">2. Payment processing</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater" class="rc-footer-link">3. Account updater</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries" class="rc-footer-link">4. Payment retry recovery</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention" class="rc-footer-link">5. Fraud prevention</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources" class="rc-footer-link">6. Review &amp; resources</a>
        </div>
        <div class="rc-footer-utility">
          <!-- Light footer → black home icon -->
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
