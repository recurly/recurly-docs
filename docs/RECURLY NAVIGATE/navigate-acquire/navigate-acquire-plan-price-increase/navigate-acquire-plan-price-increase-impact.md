---
title: 'Plan Price Increase: Tracking impact'
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

/* ── NAVIGATE MASTER ARMOR — (0,0,7,1) beats global section 1.1 rule (0,0,6,2)
   All .rc-guide a.[class] overrides must be declared AFTER this block. ── */
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

/* ── LAYOUT ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Back link — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

/* ── ANNOUNCEMENT BAR ── */
.rc-announce-bar {
  display: none; background: #FFD706; color: #0D0D0B;
  align-items: center; justify-content: space-between;
  padding: 10px 20px; font-size: .88rem; font-weight: 600;
  border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4;
}
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 10px; flex: 1; flex-wrap: wrap; }
/* Announce link — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-announce-link { color: #0D0D0B !important; font-weight: 800; white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; transition: background .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-announce-link:hover { background: rgba(0,0,0,0.20); color: #0D0D0B !important; }

/* ── HERO ── */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack); background-size: cover;
  color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0;
}
.rc-lp-pillar-tag {
  display: inline-flex; align-items: center; gap: 7px;
  background: rgba(255,215,6,0.20); border: 1px solid rgba(255,215,6,0.45);
  color: #FFD706; font-size: .75rem; font-weight: 800;
  letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 14px; border-radius: 20px; margin-bottom: 20px;
}
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: var(--lightgray); line-height: 1.6; }
.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); line-height: 1.3; }

/* ── NAV — non-sticky, open on load (Course page) ── */
details.rc-sticky-nav-wrap {
  position: relative;
  z-index: 1;
  background-color: var(--yellow);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px; border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08); overflow: hidden;
}
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

/* Nav links — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link {
  color: #0D0D0B !important; font-weight: 700; font-size: .83rem; letter-spacing: .4px;
  text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s;
  white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }

.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-sticky-link:hover .rc-step-badge { background: var(--yellow); color: var(--offblack); }

/* Active item — no persistent background; map pin icon identifies current page */
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }

/* ── CONTENT SECTIONS ── */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* ── NUMBERED STEPS ── */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 0 0 24px; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0 0 8px; }
.rc-step-content p:last-child { margin-bottom: 0; }
.rc-step-content strong { color: var(--darkgray); }

/* ── CARD GRID ── */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: #FFD706; box-shadow: 0 4px 16px rgba(255,215,6,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; color: var(--offblack); }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }
/* Feature card inline links — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide .rc-feature-card a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-feature-card a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rc-feature-tag { display: inline-block; margin-top: 4px; padding: 3px 10px; border-radius: 20px; font-size: .7rem; font-weight: 700; letter-spacing: .5px; background: var(--offblack); color: var(--yellow); width: fit-content; }

/* ── CARD ── */
.rc-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 0 0 20px; }
.rc-card-title { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 14px; display: flex; align-items: center; gap: 8px; }
.rc-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-card p:last-child { margin-bottom: 0; }
.rc-card ul { font-size: .92rem; color: var(--gray); line-height: 1.75; padding-left: 20px; margin: 0; }
.rc-card ul li { margin-bottom: 6px; }
.rc-card ul li strong { color: var(--darkgray); }

/* ── CALLOUT ── */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout + .rc-callout { margin-top: 12px; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body > strong { color: var(--offblack); }
/* Callout inline links — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-callout-body a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }

/* ── THOUGHT-PROVOKING QUESTION ── */
.rc-tpq { background: #0D0D0B !important; border: 2px solid #FFD706; border-radius: 14px; padding: 36px 40px; text-align: center; margin: 40px 0 32px; }
.rc-tpq-label { font-size: .72rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; color: #FFD706 !important; margin-bottom: 16px; display: flex; align-items: center; justify-content: center; gap: 8px; }
.rc-tpq h3 { font-size: 1.25rem; font-weight: 800; color: #FFFDF2 !important; line-height: 1.45; margin: 0 0 12px; font-style: italic; }
.rc-tpq p { font-size: .88rem; color: #CCC9B8 !important; line-height: 1.6; margin: 0; }

/* ── OFFICE HOURS CTA ── */
.rc-oh-cta { background: #0D0D0B !important; border: 2px solid #FFD706; border-radius: 14px; padding: 32px 36px; margin: 32px 0; }
.rc-oh-cta h4 { color: #FFD706 !important; font-size: 1.05rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px; }
.rc-oh-cta p { color: #CCC9B8 !important; font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
.rc-oh-cta p strong { color: #FFFDF2 !important; }
/* OH button — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-oh-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-oh-btn { background: #FFD706; color: #0D0D0B !important; text-decoration: none !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-oh-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-oh-btn:hover { background: transparent !important; color: #FFD706 !important; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }

/* ── PATH NAV BUTTONS ── */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
/* rc-btn-prev — (0,0,8,1); hex border values required */
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
.rc-btn-complete { background: var(--brightgray); color: var(--offblack) !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--yellow); cursor: default; user-select: none; }

/* ── CONTINUE YOUR JOURNEY ── */
.rc-next-steps { margin: 40px 0 0; }
.rc-next-steps h3 { font-size: .78rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 16px; display: flex; align-items: center; gap: 8px; }
.rc-next-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; }
/* rc-next-card — (0,0,8,1) with explicit border-bottom */
.rm-Markdown.markdown-body .rc-guide a.rc-next-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-next-card { background: var(--offwhite); border: 1px solid #CCC9B8 !important; border-bottom: 1px solid #CCC9B8 !important; border-radius: 12px; padding: 20px; color: #32312D !important; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rm-Markdown.markdown-body .rc-guide a.rc-next-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-next-card:hover { border: 1px solid #FFD706 !important; border-bottom: 1px solid #FFD706 !important; box-shadow: 0 4px 16px rgba(255,215,6,0.15); transform: translateY(-2px); }
.rc-next-card-tag { font-size: .68rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: var(--yellow); margin-bottom: 2px; }
.rc-next-card-icon { font-size: 1.3rem; line-height: 1; color: var(--offblack); }
.rc-next-card h4 { font-size: .95rem; font-weight: 800; color: #0D0D0B; margin: 0; line-height: 1.3; }
.rc-next-card p { font-size: .85rem; color: #807D73; line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-next-card-arrow { font-size: .82rem; font-weight: 700; color: var(--orange); margin-top: 4px; }

/* ── RESOURCES ── */
.rc-resources { background: var(--brightgray); border-left: 4px solid #FFD706; border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
/* Resource links — (0,0,8,1); base color is gray (#807D73) not darkgray */
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link { color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FFD706 !important; }

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
  .rc-oh-cta { padding: 24px 20px; }
  .rc-tpq { padding: 28px 24px; }
  .rc-card-grid { grid-template-columns: 1fr; }
  .rc-next-grid { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-back-link">← Back to Acquire</a>
  </div>

  <div class="rc-content-wrap">

    <!-- ANNOUNCEMENT BAR — add rc-active class to show before publishing -->
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
      <div class="rc-lp-hero-title"><h1>Track the impact</h1></div>
      <p>Which Recurly reports to watch, what KPIs to monitor, and how to build the baseline you'll need for a real 30/60/90-day comparison.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">30/60/90</div><div class="rc-hero-stat-label">Day checkpoints for post-change analysis</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">4</div><div class="rc-hero-stat-label">Core Recurly reports to monitor after a price change</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">Wk 1–4</div><div class="rc-hero-stat-label">The highest-signal churn window after a price change</div></div>
      </div>
    </div>

    <!-- NAV — non-sticky, open on load (Course page) -->
 

<details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">

/* ── NAVIGATE HOME ── */       
 <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>

/* ── OVERVIEW PAGE ── */           
	 <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase" class="rc-sticky-link">
          Overview
        </a>
       
/* ── WHY INCREASE PRICES── */     
	<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-why" class="rc-sticky-link">
          <span class="rc-step-badge">1</span> Why increase prices?
        </a>

/* ── THINGS TO CONSIDER── */     	
	<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-considerations" class="rc-sticky-link">
          <span class="rc-step-badge">2</span> Things to consider
        </a>

/* ── HOW TO EXECUTE IT── */     
 <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-how" class="rc-sticky-link">
          <span class="rc-step-badge">3</span> How to execute it
        </a>

/* ── HOW TO COMMUNICATE IT── */   
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-communicate" class="rc-sticky-link">
	<span class="rc-step-badge">4</span> How to communicate it
        </a>


/* ── TRACKING IMPACT── */             
	<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-impact" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> 
          Tracking impact
        </a>

/* ── REVIEW & RESOURCES ── */            
	<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-review" class="rc-sticky-link">
          <span class="rc-step-badge">6</span> Review &amp; resources
        </a>
        
/* ── BACK TO PATH START── */     
	<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      
	</div></div></div>
    </details>

    <!-- SECTION 1 -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-file-export rc-fa-section"></i> Step zero — build your baseline first</h2>
      <p>Before any change takes effect, export your current subscriber data. This is your control group. Without it, you have no way to calculate actual uplift or isolate what changed. If you haven't done this yet, do it now — before the migration runs.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Export active subscriptions</h4>
            <p>Go to <strong>Subscriptions → Export</strong> and download a CSV of all active subscriptions on the plan(s) being updated. Include unit amount, billing period, and account UUID. This file is your pre-change MRR baseline.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Note your current MRR and subscriber count</h4>
            <p>Pull the Revenue Summary report in Recurly for the current month and record total MRR and active subscriber count for the affected plan(s). You'll compare against these numbers at each 30-day checkpoint.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Record your current churn rate</h4>
            <p>Pull the Subscriber Churn report for the last 3 months and note the average monthly churn rate. Any spike above this baseline in the 4 weeks post-change is attributable to the price increase.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- SECTION 2 -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-chart-bar rc-fa-section"></i> Recurly reports to watch</h2>
      <p>These four reports give you the clearest signal on how your price change is performing. Pull them at 30, 60, and 90 days post-change.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-dollar-sign"></i></div>
          <h4>Revenue Summary</h4>
          <p>Your primary MRR indicator. Compare month-over-month MRR before and after the migration to calculate net revenue uplift. Found under <strong>Reports → Revenue Summary</strong>.</p>
          <span class="rc-feature-tag">Primary metric</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-arrow-trend-down"></i></div>
          <h4>Subscriber Churn</h4>
          <p>Monitor weekly and monthly churn rates against your pre-change baseline. Weeks 1–4 post-change carry the strongest signal — churn typically peaks in week 2. Found under <strong>Reports → Subscriber Churn</strong>.</p>
          <span class="rc-feature-tag">Retention signal</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-rotate"></i></div>
          <h4>MRR Movement</h4>
          <p>Shows MRR change broken down by new, expansion, contraction, and churn. After a price increase, expansion MRR should rise from migrations; watch for contraction or churn MRR driven by cancellations. Found under <strong>Reports → MRR Movement</strong>.</p>
          <span class="rc-feature-tag">Cohort breakdown</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-regular fa-rectangle-list"></i></div>
          <h4>Subscription Activity</h4>
          <p>Track new subscriptions, cancellations, and renewals for the affected plan by date range. Use this to identify if cancellation volume spiked immediately after notification or after the effective date. Found under <strong>Reports → Subscription Activity</strong>.</p>
          <span class="rc-feature-tag">Activity log</span>
        </div>
      </div>
    </div>

    <!-- SECTION 3 -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-bullseye rc-fa-section"></i> KPIs to track at each checkpoint</h2>
      <p>These are the specific numbers to pull and compare at 30, 60, and 90 days post-change. Put them in a simple spreadsheet alongside your baseline values.</p>

      <div class="rc-card">
        <div class="rc-card-title"><i class="fa-solid fa-table-columns rc-fa-section"></i> Your post-change KPI dashboard</div>
        <ul>
          <li><strong>MRR (affected plan):</strong> Compare to pre-change baseline. Target: net positive after accounting for any churn MRR loss.</li>
          <li><strong>Monthly churn rate:</strong> Compare to your 3-month pre-change average. An increase above 1–2 percentage points signals communication or value issues.</li>
          <li><strong>Cancellations per week (weeks 1–4):</strong> Track weekly cancel volume. A spike in week 2 is common — watch for it returning to baseline by week 4.</li>
          <li><strong>Renewal success rate at new price:</strong> What % of subscriptions that came up for renewal at the new price successfully renewed? A drop below your historical renewal rate indicates friction.</li>
          <li><strong>Support ticket volume:</strong> Track pricing-related support tickets as a proxy for subscriber sentiment. A spike that doesn't normalize by week 3 suggests the communication missed.</li>
          <li><strong>Net revenue impact:</strong> (New MRR from migrations + retained MRR at new price) − (MRR lost to churn). This is your bottom-line result.</li>
        </ul>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>Separate churn timing from churn cause</strong>
          <p>Not all churn in the 30 days after a price change is caused by the price change. Compare against your seasonal baseline — if churn typically rises in Q1, you need to account for that before attributing the uplift to the price increase.</p>
        </div>
      </div>
    </div>

    <!-- SECTION 4 -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-circle-check rc-fa-section"></i> What good looks like</h2>
      <p>Here's what a successful price increase outcome looks like in the Recurly reports at the 90-day mark.</p>

      <div class="rc-card">
        <ul>
          <li><strong>MRR uplift of 3–8%</strong> on the affected plan(s), net of any churn-driven MRR loss.</li>
          <li><strong>Churn rate returned to baseline</strong> by week 4–6. A brief spike in weeks 1–3 is normal and expected.</li>
          <li><strong>Renewal rate stable</strong> — within 2–3 percentage points of pre-change renewal rate at 60 days.</li>
          <li><strong>Support volume normalized</strong> by week 3 — pricing-related tickets trending back to baseline after the initial notification wave.</li>
          <li><strong>Grandfathered accounts intact</strong> — confirm no grandfathered subscriptions were accidentally migrated by checking unit amounts against your grandfather list.</li>
        </ul>
      </div>
    </div>

    <!-- THOUGHT-PROVOKING QUESTION -->
    <div class="rc-tpq">
      <div class="rc-tpq-label"><i class="fa-solid fa-circle-question"></i> Something to think about</div>
      <h3>"If you already knew your subscribers' exact churn threshold, how would that change the way you designed this price increase — the magnitude, the timing, or the communication?"</h3>
      <p>Most merchants set a price increase based on what they think is reasonable. The data you're collecting now could tell you what's actually defensible — and inform how boldly you price the next one.</p>
    </div>

    <!-- OFFICE HOURS CTA -->
    <div class="rc-oh-cta">
      <h4><i class="fa-solid fa-headset rc-fa-dark"></i>Bring your numbers to Office Hours</h4>
      <p>If you're staring at your post-change data and not sure what story it's telling, bring it to a <strong>Customer Success Global Office Hours</strong> session. Our CSMs can help you interpret the MRR Movement report, diagnose a churn spike, and figure out whether your price increase is performing as expected — or if there's something to course-correct.</p>
      <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <!-- PATH NAV BUTTONS -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-communicate" class="rc-btn-prev">← Communicate it</a>
      <span class="rc-lp-nav-indicator">5 of 5</span>
      <span class="rc-btn-complete"><i class="fa-solid fa-circle-check"></i> Path complete!</span>
    </div>

    <!-- CONTINUE YOUR JOURNEY (appropriate on Course last/R&R page) -->
    <div class="rc-next-steps">
      <h3><i class="fa-solid fa-compass rc-fa-section"></i> Continue your journey</h3>
      <div class="rc-next-grid">

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-packaging-201" class="rc-next-card">
          <div class="rc-next-card-tag">Recommended next</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-chart-line"></i></div>
          <h4>Pricing &amp; Packaging 201</h4>
          <p>Go deeper on advanced pricing structures — segmentation, account hierarchy, usage billing, and the models that turn a single price point into a growth lever.</p>
          <div class="rc-next-card-arrow">Start path →</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-next-card">
          <div class="rc-next-card-tag">Explore the pillar</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-bullseye"></i></div>
          <h4>All Acquire paths</h4>
          <p>See every learning path in the Acquire pillar — checkout optimization, payment methods, pricing strategy, and more.</p>
          <div class="rc-next-card-arrow">View Acquire →</div>
        </a>

        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-next-card">
          <div class="rc-next-card-tag">Live session</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-microphone"></i></div>
          <h4>Global Office Hours</h4>
          <p>Bring your pricing questions to our CSMs live. Sessions run weekly and cover real merchant scenarios.</p>
          <div class="rc-next-card-arrow">Register →</div>
        </a>

      </div>
    </div>

    <!-- RESOURCES -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/docs/plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Plans</a>
        <a href="https://docs.recurly.com/docs/subscriptions" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Subscriptions</a>
        <a href="https://developers.recurly.com/api/v2021-02-25/index.html#operation/update_subscription" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-code"></i> API: Update Subscription</a>
        <a href="https://docs.recurly.com/docs/email-templates" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Email Templates</a>
        <a href="https://docs.recurly.com/docs/webhooks" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Webhooks</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
      </div>
    </div>

    <!-- FOOTER NAV — grouped rc-footer-section structure -->
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
