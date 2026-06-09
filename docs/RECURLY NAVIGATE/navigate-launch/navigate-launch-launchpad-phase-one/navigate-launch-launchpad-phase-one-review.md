---
title: 'Section 6: Phase 1 Review'
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

/* ── NAV ── */
details.rc-sticky-nav-wrap {
  position: relative; z-index: 1;
  background-color: var(--brightgray);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px 0; border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08); overflow: hidden;
}
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: var(--offblack); }
.rc-nav-chevron { font-size: .72rem; color: var(--offblack); opacity: 0.55; line-height: 1; transition: transform 0.25s ease; }
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
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }

/* ── CONTENT SECTIONS ── */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* ── RECAP CARDS ── */
.rc-recap-row { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; margin-bottom: 24px; }
.rc-recap-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 13px; padding: 20px 22px; display: flex; flex-direction: column; gap: 8px; }
.rc-recap-card h4 { font-size: .95rem; font-weight: 800; margin: 0; color: var(--offblack); display: flex; align-items: center; gap: 8px; }
.rc-recap-card p { font-size: .88rem; color: var(--gray); margin: 0; line-height: 1.55; flex-grow: 1; }
.rm-Markdown.markdown-body .rc-guide a.rc-recap-res:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-recap-res { color: #FF8200 !important; font-size: .82rem; font-weight: 700; border-bottom: 0 !important; display: inline-flex; align-items: center; gap: 4px; margin-top: 4px; }
.rm-Markdown.markdown-body .rc-guide a.rc-recap-res:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-recap-res:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* ── CALLOUT ── */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body > strong { color: var(--offblack); }

/* ── CONTINUE YOUR JOURNEY (next steps) ── */
.rc-next-steps { margin: 40px 0 0; }
.rc-next-steps h3 { font-size: .78rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 16px; display: flex; align-items: center; gap: 8px; }
.rc-next-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; }
.rm-Markdown.markdown-body .rc-guide a.rc-next-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-next-card { background: var(--offwhite); border: 1px solid #CCC9B8; border-radius: 12px; padding: 20px; text-decoration: none !important; color: inherit; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; border-bottom: 1px solid #CCC9B8 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-next-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-next-card:hover { border-color: #CCC9B8; border-bottom: 1px solid #CCC9B8 !important; box-shadow: 0 4px 16px rgba(204,201,184,0.30); transform: translateY(-2px); }
.rc-next-card-tag { font-size: .68rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: #CCC9B8 !important; margin-bottom: 2px; }
.rc-next-card-icon { font-size: 1.3rem; line-height: 1; color: #0D0D0B !important; }
.rc-next-card h4 { font-size: .95rem; font-weight: 800; color: #0D0D0B !important; margin: 0; line-height: 1.3; }
.rc-next-card p { font-size: .85rem; color: #807D73 !important; line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-next-card-arrow { font-size: .82rem; font-weight: 700; color: #FF8200 !important; margin-top: 4px; }

/* ── PATH NAV ── */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
.rc-btn-complete { background: var(--brightgray); color: var(--offblack) !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--yellow); cursor: default; user-select: none; }

/* ── RESOURCES ── */
.rc-resources { background: var(--brightgray); border-left: 4px solid #CCC9B8; border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
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
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link {
  color: #807D73 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem;
  transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-footer-link:hover { color: #FF8200 !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* ── REFLECT CARD ── */
.rc-reflect-card {
  background: var(--offwhite); border: 1px solid var(--lightgray);
  border-left: 4px solid var(--yellow); border-radius: 14px;
  padding: 24px 28px; margin: 20px 0;
}
.rc-reflect-label {
  display: inline-block; background: #FFD706; color: #0D0D0B;
  font-size: .72rem; font-weight: 800; text-transform: uppercase; letter-spacing: .6px;
  padding: 3px 10px; border-radius: 5px; margin-bottom: 12px;
}
.rc-reflect-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 10px; line-height: 1.4; }
.rc-reflect-card p { font-size: .9rem; color: var(--gray); line-height: 1.6; margin: 0; }

/* ── OFFICE HOURS CTA ── */
.rc-oh-cta { background: var(--offblack); border: 2px solid var(--yellow); border-radius: 14px; padding: 32px 36px; margin: 32px 0; }
.rc-oh-cta h4 { color: var(--yellow); font-size: 1.05rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px; }
.rc-oh-cta p { color: var(--lightgray); font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
.rc-oh-cta p strong { color: var(--offwhite); }
.rm-Markdown.markdown-body .rc-guide a.rc-oh-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-oh-btn { background: var(--yellow); color: #0D0D0B !important; text-decoration: none !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-oh-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-oh-btn:hover { background: transparent !important; color: var(--yellow) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* ── PHASE 2 CTA ── */
.rc-phase2-cta { background: var(--offwhite); border: 2px solid var(--orange); border-radius: 14px; padding: 32px 36px; margin: 28px 0 0; }
.rc-phase2-cta h3 { font-size: 1.1rem; font-weight: 800; color: var(--offblack); margin: 0 0 10px; }
.rc-phase2-cta p { font-size: .95rem; color: var(--darkgray); line-height: 1.6; margin: 0 0 20px; }
.rc-phase2-cta:hover { box-shadow: 0 4px 16px rgba(255,130,0,0.15); }
.rm-Markdown.markdown-body .rc-guide a.rc-phase2-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-phase2-btn { background: #FF8200; color: #ffffff !important; text-decoration: none !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid #FF8200 !important; border-bottom: 2px solid #FF8200 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-phase2-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-phase2-btn:hover { background: transparent !important; color: #FF8200 !important; border: 2px solid #FF8200 !important; border-bottom: 2px solid #FF8200 !important; }

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-oh-cta { padding: 24px 20px; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-recap-row { grid-template-columns: 1fr; }
  .rc-next-grid { grid-template-columns: 1fr; }
}
</style>

<div class="rc-guide">

  <!-- ANNOUNCEMENT BAR — add rc-active class to show before publishing -->
  <div class="rc-announce-bar">
    <div class="rc-announce-inner">
      <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
      <strong>Upcoming:</strong> Join our CSMs for a live Q&amp;A session.
      <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
    </div>
  </div>

  <!-- BACK LINK -->
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one" class="rc-back-link">← Back to Path Start</a>
  </div>

  <div class="rc-content-wrap">

    <!-- HERO -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/b6c93b0c856b23bcb18d1c1f5106eb9c83d23d9b505dc37e5ce9ea0d8dcfe89b-Launch-icon-white.png" alt="Launch"> Launch · Launchpad Phase 1
      </div>
      <div class="rc-lp-hero-title"><h1>Phase 1 complete — rewind &amp; review</h1></div>
      <p>You've set the foundation for a resilient, optimized Recurly setup. Here's everything you accomplished — and everything you need to carry it forward.</p>
    </div>

    <!-- Nav (sticky + collapsed — LP Overview) -->
    <details class="rc-sticky-nav-wrap"open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one" class="rc-sticky-link">Launchpad overview
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-production-testing" class="rc-sticky-link"><span class="rc-step-badge">1</span> Production testing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-dunning"  class="rc-sticky-link"><span class="rc-step-badge">2</span> Dunning</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-account-updater" class="rc-sticky-link"><span class="rc-step-badge">3</span> Account Updater</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-branding" class="rc-sticky-link"><span class="rc-step-badge">4</span> Branding</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-gateway-failover" class="rc-sticky-link"><span class="rc-step-badge">5</span> Gateway failover</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-review" class="rc-sticky-link rc-sticky-link-active">  <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt="">Review &amp; resources</a>
      </div></div></div>
    </details>

    <!-- SECTION: WHAT YOU BUILT -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-trophy rc-fa-section"></i> What you built in Phase 1</h2>
      <p>Each step in Phase 1 addresses a specific revenue risk. Together, they form a complete optimization layer around your Recurly setup — working automatically, around the clock, without manual intervention.</p>

      <div class="rc-recap-row">
        <div class="rc-recap-card">
          <h4><i class="fa-solid fa-flask rc-fa-section"></i> Final production testing</h4>
          <p>You validated the full subscriber checkout experience, confirmed payment processing, and checked PSD2 compliance — catching issues before real subscribers ever saw them.</p>
          <a class="rc-recap-res" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-production-testing">← Review this step</a>
        </div>
        <div class="rc-recap-card">
          <h4><i class="fa-solid fa-rotate rc-fa-section"></i> Dunning optimization</h4>
          <p>You configured your dunning campaign — window length, email sequence, and expiration behavior. Recurly's built-in Intelligent Retry logic runs automatically to maximize every recovery opportunity.</p>
          <a class="rc-recap-res" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-dunning" >← Review this step</a>
        </div>
        <div class="rc-recap-card">
          <h4><i class="fa-solid fa-credit-card rc-fa-section"></i> Account Updater</h4>
          <p>You enabled proactive card update checks so expired or replaced cards are refreshed before renewal — preventing payment failures from occurring in the first place.</p>
          <a class="rc-recap-res" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-account-updater">← Review this step</a>
        </div>
        <div class="rc-recap-card">
          <h4><i class="fa-solid fa-palette rc-fa-section"></i> Branding</h4>
          <p>Every email and invoice your subscribers receive is now on-brand — building trust, reducing support confusion, and making your Recurly communications feel native to your product.</p>
          <a class="rc-recap-res" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-branding">← Review this step</a>
        </div>
        <div class="rc-recap-card">
          <h4><i class="fa-solid fa-shield-halved rc-fa-section"></i> Gateway Failover</h4>
          <p>You've eliminated the single point of payment failure. If your primary gateway goes down, transactions automatically route to your backup — your revenue stream stays uninterrupted.</p>
          <a class="rc-recap-res" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-gateway-failover">← Review this step</a>
        </div>
      </div>

 <!-- SECTION: Callout tip -->
      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>Keep it going</strong>
          <p>These optimizations don't stop working when you close this page. Dunning runs every billing cycle. Account Updater refreshes cards before every renewal. Gateway Failover monitors every transaction. You've built a system — now let it run.</p>
        </div>
      </div>

 <!-- SECTION: REFLECTION -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-thought-bubble rc-fa-section"></i> Reflect before you move on</h2>

      <div class="rc-reflect-card">
        <span class="rc-reflect-label">Question 1 of 3 · Reflection</span>
        <h4>Which Phase 1 step felt like the biggest gap in your current setup — and have you confirmed it's now fully configured?</h4>
        <p>Think through each of the five steps. If any feel incomplete or uncertain, return to that page and work through the checklist before moving to Phase 2.</p>
      </div>

      <div class="rc-reflect-card">
        <span class="rc-reflect-label">Question 2 of 3 · Reflection</span>
        <h4>Is your dunning window aligned with your billing cycle length — and do you know how to find out if it isn't?</h4>
        <p>A common misconfiguration is setting the dunning window too long or too short for the plan type. Navigate to <strong>Configuration → Dunning Management</strong> and verify the window against your shortest billing cycle.</p>
      </div>

      <div class="rc-reflect-card">
        <span class="rc-reflect-label">Question 3 of 3 · Reflection</span>
        <h4>When did you last test your checkout flow end-to-end in production — and what would it take to make that a regular practice?</h4>
        <p>Most issues surface between releases, not during them. A brief monthly test with Recurly's test card values takes under 10 minutes and catches regressions early.</p>
      </div>
      </div>

 <!-- SECTION: PHASE TWO CTA -->

      <div class="rc-phase2-cta">
        <h3><i class="fa-solid fa-chart-line rc-fa-light"></i> Ready for Phase 2?</h3>
        <p>Now that your setup is optimized, it's time to understand the data. Phase 2 teaches you the six core benchmark metrics every subscription business should track — and how to use them to grow smarter.</p>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two" class="rc-phase2-btn">Start Phase 2: Mastering metrics →</a>
      </div>
    </div>

   

    <!-- SECTION: RESOURCES -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-book-open rc-fa-section"></i> Phase 1 reference resources</h2>
      <p>Everything referenced across Phase 1, in one place.</p>

      <div class="rc-resources">
        <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
        <div class="rc-resource-links">
          <a href="https://go.recurly.com/Navigate-Launchpad-Cheatsheet.html" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Launchpad Phase 1 cheatsheet</a>
          <a href="https://go.recurly.com/Navigate-Resource-Guide.html" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Navigate Resource Guide</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/account-updater" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Account Updater</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-management" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Dunning Management</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/gateway-failover" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Gateway Failover</a>
          <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
          <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
        </div>
      </div>
    </div>

    <!-- CONTINUE YOUR JOURNEY — LP R&R page only -->
    <div class="rc-next-steps"style="display: none;">
      <h3><i class="fa-solid fa-compass rc-fa-section"></i> Continue your journey</h3>
      <div class="rc-next-grid">

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two" class="rc-next-card">
          <div class="rc-next-card-tag">Recommended next</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-chart-line"></i></div>
          <h4>Launchpad Phase 2: Mastering metrics</h4>
          <p>Phase 1 built your setup. Phase 2 teaches you to read the data — six core benchmark metrics every subscription business should track.</p>
          <div class="rc-next-card-arrow">Start Phase 2 →</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-next-card">
          <div class="rc-next-card-tag">Explore the pillar</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-rocket"></i></div>
          <h4>All Launch paths</h4>
          <p>See every learning path in the Launch pillar — from initial setup through advanced configuration and growth metrics.</p>
          <div class="rc-next-card-arrow">View Launch →</div>
        </a>

        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-next-card">
          <div class="rc-next-card-tag">Live session</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-microphone"></i></div>
          <h4>Global Office Hours</h4>
          <p>Bring your Phase 1 questions to our CSMs live. Sessions run weekly and are open to all Navigate participants.</p>
          <div class="rc-next-card-arrow">Register →</div>
        </a>

      </div>
    </div>

    <!-- PATH NAV — LP R&R: prev = last Micro-Path; rc-btn-complete; indicator = Overview -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-gateway-failover" class="rc-btn-prev">← Gateway Failover</a>
      <span class="rc-lp-nav-indicator">Overview</span>
      <span class="rc-btn-complete"><i class="fa-solid fa-circle-check"></i> Path complete!</span>
    </div>

    <!-- FOOTER NAV — LP R&R pattern: one section row + utility -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">

        <div class="rc-footer-section">
          <span class="rc-footer-label">Launchpad Phase 1</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one" class="rc-footer-link">Launchpad Phase 1 overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-production-testing" class="rc-footer-link">Production testing</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-dunning"  class="rc-footer-link">Dunning</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-account-updater" class="rc-footer-link">Account Updater</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-branding" class="rc-footer-link">Branding</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-gateway-failover" class="rc-footer-link">Gateway Failover</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-review" class="rc-footer-link">Review &amp; resources</a>
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
