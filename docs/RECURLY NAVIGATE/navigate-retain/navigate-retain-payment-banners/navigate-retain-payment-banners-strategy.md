---
title: 'Payment Banners: Strategy & best practices'
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
.rc-guide h1 { border-bottom: none !important; padding-bottom: 0 !important; }
.rc-guide, .rc-guide * { font-family: "Polar", "Helvetica Neue", Helvetica, arial, sans-serif !important; }
.rc-guide [class^="fa-"],
.rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide .fa-brands,
.rc-guide [class*="fa-brands"] { font-family: "Font Awesome 6 Brands" !important; }

/* ── NAVIGATE MASTER ARMOR — (0,0,7,1) ── */
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

/* ── DESIGN TOKENS ── */
.rc-guide {
  --yellow: #FFD706;
  --orange: #FF8200;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
  --retain: #FF9D88;
  color: #32312D !important;
  background: #ffffff;
}

/* ── FONT AWESOME ICON HELPERS ── */
.rc-fa-announce { color: var(--offblack); font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: var(--offblack); font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: var(--offblack); font-size: 1rem; }

/* ── LAYOUT ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Back link — (0,0,8,1) */
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

/* ── ANNOUNCEMENT BAR (hidden by default) ── */
.rc-announce-bar { display: none; background: var(--offblack); padding: 10px 40px; align-items: center; justify-content: center; gap: 12px; flex-wrap: wrap; }
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-bar p { color: var(--lightgray); font-size: .85rem; margin: 0; line-height: 1.5; }
.rc-announce-bar p strong { color: var(--yellow); }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-announce-link { color: #0D0D0B !important; background: var(--yellow); padding: 5px 14px; border-radius: 6px; font-size: .82rem; font-weight: 700; border-bottom: 0 !important; transition: opacity .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-announce-link:hover { opacity: .85; }

/* ── HERO ── */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack); background-size: cover;
  color: #fff; padding: 56px 40px 48px; text-align: center; border-radius: 16px;
}
.rc-lp-pillar-tag {
  display: inline-flex; align-items: center; gap: 7px;
  background: rgba(255,157,136,0.20); border: 1px solid rgba(255,157,136,0.45);
  color: #FF9D88; font-size: .75rem; font-weight: 800; letter-spacing: 1px;
  text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px;
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

/* ── NAV — non-sticky, open ── */
details.rc-sticky-nav-wrap {
  position: relative; z-index: 1;
  background-color: var(--retain);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px; border-radius: 12px;
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
.rc-lp-section { margin-bottom: 52px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section > p { font-size: .97rem; line-height: 1.7; color: var(--darkgray); margin: 0 0 24px; }

/* ── FEATURE CARD GRIDS ── */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 28px; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: #FF9D88; box-shadow: 0 4px 16px rgba(255,157,136,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; color: var(--offblack); }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }
.rc-feature-tag { display: inline-block; margin-top: 4px; padding: 3px 10px; border-radius: 20px; font-size: .7rem; font-weight: 700; letter-spacing: .5px; background: var(--offblack); color: var(--yellow); width: fit-content; }

/* ── ACCENT CARDS ── */
.rc-accent-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 20px 0; }
.rc-accent-card.rc-accent-retain { border-left: 4px solid var(--retain); }
.rc-accent-card.rc-accent-orange { border-left: 4px solid var(--orange); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.7; margin: 0 0 8px; }
.rc-accent-card p:last-child { margin-bottom: 0; }
.rc-accent-card ul { font-size: .9rem; color: var(--gray); line-height: 1.8; padding-left: 20px; margin: 0; }
.rc-accent-card ul li { margin-bottom: 4px; }
.rc-card-grid .rc-accent-card { margin: 0; }

/* ── INTERACTIVE CHECKLIST — Pure CSS (no JS) ── */
.rc-checklist { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 0; }
.rc-checklist-header { padding: 14px 22px; background: var(--offblack); display: flex; align-items: center; gap: 10px; }
.rc-checklist-header h4 { font-size: .82rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: var(--yellow); margin: 0; }
.rc-checklist-item { padding: 14px 22px; border-bottom: 1px solid var(--brightgray); display: flex; align-items: flex-start; gap: 14px; transition: background .15s; cursor: pointer; }
.rc-checklist-item:last-child { border-bottom: none; }
.rc-checklist-item:hover { background: var(--brightgray); }
.rc-checklist-item input[type="checkbox"] { position: absolute; opacity: 0; width: 0; height: 0; pointer-events: none; }
.rc-checkbox-box { width: 22px; height: 22px; border-radius: 6px; border: 2px solid var(--lightgray); flex-shrink: 0; background: #fff; display: flex; align-items: center; justify-content: center; transition: all .18s; margin-top: 1px; }
.rc-checklist-item input[type="checkbox"]:checked + .rc-checkbox-box { background: var(--offblack); border-color: var(--offblack); }
.rc-checklist-item input[type="checkbox"]:checked + .rc-checkbox-box::after { content: '✓'; color: var(--yellow); font-size: .75rem; font-weight: 800; line-height: 1; }
.rc-checklist-item input[type="checkbox"]:checked ~ .rc-checklist-text strong { text-decoration: line-through; color: var(--gray); }
.rc-checklist-item:has(input[type="checkbox"]:checked) { background: rgba(255,157,136,0.06); }
.rc-checklist-text { flex: 1; }
.rc-checklist-text strong { font-size: .9rem; font-weight: 700; color: var(--offblack); display: block; margin-bottom: 2px; transition: color .18s; }
.rc-checklist-text span { font-size: .8rem; color: var(--gray); line-height: 1.4; display: block; }
.rc-checklist-footer { padding: 10px 22px; background: var(--brightgray); border-top: 1px solid var(--lightgray); font-size: .78rem; color: var(--gray); font-weight: 600; }

/* ── CALLOUTS ── */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout + .rc-callout { margin-top: 12px; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body > strong { color: var(--offblack); }

/* ── OFFICE HOURS CTA — all hex + !important on dark card ── */
.rc-oh-cta { background: #0D0D0B !important; border: 2px solid #FFD706; border-radius: 14px; padding: 32px 36px; margin: 32px 0; }
/* h4 must be display: block (default) — never flex — so rc-fa-dark icon stacks above text */
.rc-oh-cta h4 { color: #FFD706 !important; font-size: 1.05rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px; }
.rc-oh-cta p { color: #CCC9B8 !important; font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
.rc-oh-cta p strong { color: #FFFDF2 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-oh-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-oh-btn {
  background: #FFD706 !important; color: #0D0D0B !important; text-decoration: none !important;
  padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem;
  display: inline-flex; align-items: center; gap: 8px; transition: all .2s;
  border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-oh-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-oh-btn:hover {
  background: transparent !important; color: #FFD706 !important;
  border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important;
}

/* ── PATH NAV BUTTONS ── */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 44px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; text-align: center; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev {
  background: transparent; color: #0D0D0B !important; text-decoration: none !important;
  padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem;
  display: inline-flex; align-items: center; gap: 8px;
  border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s;
}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path {
  background: #FFD706; color: #0D0D0B !important; text-decoration: none !important;
  padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem;
  display: inline-flex; align-items: center; gap: 8px; transition: all .2s;
  border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-path:hover {
  background: transparent !important; color: #0D0D0B !important;
  border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important;
}

/* ── RESOURCES ── */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--retain); border-radius: 10px; padding: 20px 24px; margin: 40px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link {
  color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px;
  text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem;
  transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-decoration-color: #FF9D88 !important; }

/* ── FOOTER NAV ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link { color: #807D73 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-footer-link:hover { color: #FF8200 !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* ── CONSOLIDATED RESPONSIVE BLOCK ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-card-grid { grid-template-columns: 1fr; }
  .rc-oh-cta { padding: 24px 20px; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">

  <!-- Announcement bar (hidden) -->
  <div class="rc-announce-bar">
    <p><strong>New:</strong> Office Hours sessions run weekly for all Recurly customers.</p>
    <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
  </div>

  <!-- Back link -->
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-back-link">← Back to Retain</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Hero -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt="Retain">
        Retain · Payment banners
      </div>
      <div class="rc-lp-hero-title">
        <h1>Strategy &amp; best practices</h1>
      </div>
      <p>Banners succeed or fail on three things: timing, messaging, and frequency. Get all three right and you'll see measurable retention gains. Get them wrong and subscribers learn to ignore them.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">Up to 80%</div>
          <div class="rc-hero-stat-label">Recovery on failing invoices when in-app banners are added to dunning</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">40%</div>
          <div class="rc-hero-stat-label">Of all subscriber losses are involuntary — customers who didn't mean to leave</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">40%</div>
          <div class="rc-hero-stat-label">Of subscribers attempting to cancel can be saved by a well-timed in-app prompt</div>
        </div>
      </div>
    </div>

    <!-- Nav: non-sticky, open. Active: page 5 -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners" class="rc-sticky-link">Payment banners</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-why" class="rc-sticky-link"><span class="rc-step-badge">1</span> Why it matters</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-use-cases" class="rc-sticky-link"><span class="rc-step-badge">2</span> Use cases</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-webhooks" class="rc-sticky-link"><span class="rc-step-badge">3</span> Webhooks setup</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage" class="rc-sticky-link"><span class="rc-step-badge">4</span> Recurly Engage setup</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-strategy" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Strategy &amp; best practices
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-tracking" class="rc-sticky-link"><span class="rc-step-badge">6</span> Tracking your impact</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-review" class="rc-sticky-link"><span class="rc-step-badge">7</span> Review &amp; resources</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- Section 1: Timing -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-clock rc-fa-section"></i> Timing — when to fire</h2>

      <p>The single biggest factor in banner performance isn't the design or the copy — it's whether the banner fires at the right moment. Fire too early and it's noise. Fire too late and the damage is done. Each scenario has a different optimal window.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-calendar-days"></i></div>
          <h4>Expiring card: 30 days out</h4>
          <p>Deploy the first banner 30 days before card expiry. This gives the subscriber plenty of time to update without urgency. If not updated, send a second banner at 14 days. Dismissible on both — the subscriber hasn't failed yet, so keep the tone helpful rather than alarming.</p>
          <span class="rc-feature-tag">Proactive</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-bolt"></i></div>
          <h4>Failed payment: next login</h4>
          <p>Show the banner immediately on the subscriber's very next session after a payment decline. Every day of inaction raises the chance they disengage permanently. For this scenario, suppress dismiss until resolved — the issue is active and needs attention.</p>
          <span class="rc-feature-tag">Urgent</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-calendar-check"></i></div>
          <h4>Annual pre-renewal: 30 days prior</h4>
          <p>Surface for all annual subscribers 30 days before their renewal date. Annual renewals have significantly lower recovery rates once they fail — prevention is worth far more than any recovery effort after the fact. Frame it as a courtesy check-in, not a warning.</p>
          <span class="rc-feature-tag">High value</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-rotate"></i></div>
          <h4>Active dunning: every login</h4>
          <p>Show the banner on every login during an active dunning cycle until the issue is resolved. The subscriber is already receiving your dunning emails — the banner reinforces the same message in-session, through the channel where they're actually engaged. Don't reduce frequency here; the window is short and the urgency is real.</p>
          <span class="rc-feature-tag">Reinforce dunning</span>
        </div>
      </div>
    </div>

    <!-- Section 2: Messaging -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-pen-to-square rc-fa-section"></i> Messaging — what to say</h2>

      <p>The most effective payment banners are specific, calm, and direct. Specificity builds trust — mentioning the actual card or renewal date signals that this is a real alert, not a generic notification. Calm framing keeps the subscriber in a problem-solving mindset rather than triggering defensiveness. A single clear CTA removes all ambiguity about what to do next.</p>

      <div class="rc-card-grid">
        <div class="rc-accent-card rc-accent-retain">
          <h4><i class="fa-solid fa-circle-check" style="color:#4caf7d;"></i> Do</h4>
          <ul>
            <li>Be specific — mention the card last four digits or the renewal date</li>
            <li>State the consequence calmly: "to keep your subscription active"</li>
            <li>Use a direct, single CTA: "Update payment method" or "Review billing info"</li>
            <li>Keep the copy to two sentences or fewer</li>
            <li>Match your product's existing tone of voice</li>
            <li>Clear the banner automatically once the issue is resolved</li>
            <li>Exclude the billing info page so subscribers updating aren't shown the banner</li>
          </ul>
        </div>
        <div class="rc-accent-card rc-accent-orange">
          <h4><i class="fa-solid fa-circle-xmark" style="color:var(--orange);"></i> Don't</h4>
          <ul>
            <li>Use alarming language: "URGENT", "WARNING!", "Your account will be suspended"</li>
            <li>Send the same generic message regardless of the trigger</li>
            <li>Use vague CTAs: "Click here", "Learn more", "Take action"</li>
            <li>Show the banner when the subscriber is already on the billing update page</li>
            <li>Leave a resolved banner visible — it erodes trust and creates confusion</li>
            <li>Skip frequency capping — subscribers learn to ignore banners that appear constantly</li>
          </ul>
        </div>
      </div>

      <div class="rc-accent-card rc-accent-retain" style="margin-top:28px;">
        <h4><i class="fa-regular fa-comment-dots" style="margin-right:6px;color:var(--retain);"></i> Example copy by scenario</h4>
        <p><strong>Expiring card:</strong> "Your card ending in 4242 expires in 28 days. Update your payment method to keep your subscription active." → <em>Update now</em></p>
        <p><strong>Failed payment:</strong> "We couldn't process your last payment. Update your billing info to restore full access to your account." → <em>Update billing info</em></p>
        <p><strong>Annual pre-renewal:</strong> "Your annual plan renews on March 15. Confirm your payment method is up to date to avoid any interruption." → <em>Review payment method</em></p>
        <p><strong>During dunning:</strong> "We still haven't been able to process your payment. Update your billing info now to keep your access." → <em>Resolve now</em></p>
        <p><strong>Cancel save (Engage):</strong> "Before you go — would you like to pause your subscription instead?" → <em>Explore my options</em></p>
      </div>
    </div>

    <!-- Section 3: Frequency -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-clock-rotate-left rc-fa-section"></i> Frequency — preventing banner fatigue</h2>

      <p>Showing the same banner every session is one of the fastest ways to train subscribers to ignore it. Frequency capping keeps banners meaningful — they remain something the subscriber notices and acts on, rather than background noise they've learned to dismiss without reading.</p>

      <div class="rc-accent-card rc-accent-retain">
        <h4>Recommended frequency caps by scenario</h4>
        <p><strong>Expiring card:</strong> Once per 5 sessions, or once per week. Urgency is low — the subscriber has time, and repetition before they're ready will frustrate more than motivate.</p>
        <p><strong>Failed payment / active dunning:</strong> Every session for the first 3 days — the window is short and the stakes are high. After 3 days, every 3 sessions until resolved. Remove the cap only if you're also providing a clear dismiss option.</p>
        <p><strong>Annual pre-renewal:</strong> Once per week in the 30-day pre-renewal window. The subscriber needs to act before a specific date, so weekly reminders are sufficient without feeling persistent.</p>
        <p><strong>Cancel save prompt (Engage):</strong> Once per active cancel session only. Never surface cancel save banners on regular product sessions — they should only appear when the subscriber has explicitly navigated toward cancellation.</p>
      </div>
    </div>

    <!-- Optimization checklist -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-list-check rc-fa-section"></i> Optimization checklist</h2>

      <p>Use this as your ongoing reference — both when you first deploy banners and when you revisit them after 90 days to improve performance.</p>

      <div class="rc-checklist">
        <div class="rc-checklist-header">
          <i class="fa-solid fa-list-check" style="color: var(--yellow); font-size: 1rem;"></i>
          <h4>Make your banners as effective as possible</h4>
        </div>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Separate campaigns configured per trigger type</strong>
            <span>Expiring card, failed payment, and annual renewal each have tailored messaging — not a single banner for all scenarios.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Frequency cap set on all campaigns</strong>
            <span>Every banner has a cap to prevent subscriber fatigue and keep prompts feeling relevant.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>CTA is specific and action-oriented</strong>
            <span>"Update payment method" outperforms generic CTAs every time — make it clear and direct.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Billing info page is excluded from banner display rules</strong>
            <span>Subscribers who are already updating their card should never see the payment banner.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Banner dismisses automatically once the issue is resolved</strong>
            <span>A resolved banner that keeps showing erodes trust and creates confusion — clear it on the confirmation event.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Account Updater is enabled alongside your banners</strong>
            <span>AU handles the silent fixes; banners handle everything that requires subscriber action. Both running together gives you full coverage.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Banner experience tested on mobile viewports</strong>
            <span>Many subscribers access your product on mobile — verify the banner renders correctly and the CTA is tappable on small screens.</span>
          </div>
        </label>
        <div class="rc-checklist-footer">Tap each item to mark it complete</div>
      </div>

      <div class="rc-callout rc-callout-tip" style="margin-top:28px;">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>The 90-day rule</strong>
          <p>Give your payment banners 90 days before drawing firm conclusions about their impact. Card expiry cycles, billing periods, and subscriber behavior all take time to fully surface in your data. Use the first 30 days to confirm the banner is firing correctly, the second 30 to watch CTR and completion rates, and the third 30 to measure the involuntary churn delta. The next page covers exactly which metrics to track and where to find them.</p>
        </div>
      </div>
    </div>

    <!-- Office Hours CTA -->
    <div class="rc-oh-cta">
      <h4><i class="fa-solid fa-headset rc-fa-dark"></i>Want help applying this to your business?</h4>
      <p>Strategy questions are the hardest to answer alone — what frequency cap works for your subscriber mix, whether your dunning setup and banner timing are complementary, how to prioritize which scenarios to deploy first. Join a <strong>Customer Success Global Office Hours</strong> session and our CSMs will work through your specific situation with you. Sessions run weekly and are free for all Recurly customers.</p>
      <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <!-- Path navigation -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage" class="rc-btn-prev">← Recurly Engage setup</a>
      <span class="rc-lp-nav-indicator">5 of 7</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-tracking" class="rc-btn-path">Next: Tracking your impact →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://recurly.com/blog/dunning" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> All about dunning — Recurly blog</a>
        <a href="https://support.recurly.com/hc/en-us/articles/44224955931924-What-Are-the-Best-Practices-for-Initial-and-Recurring-Payment-Failure-Recovery" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Best practices for payment failure recovery</a>
        <a href="https://support.recurly.com/hc/en-us/articles/41994337356180-How-Can-I-A-B-Test-Different-Prompt-Experiences-in-Recurly-Engage" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> A/B testing prompt experiences in Engage</a>
        <a href="https://recurly.com/resources/guide/10-plays-to-drive-subscriber-upsells-and-reduce-churn-recurly-engage/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> 10 plays to reduce churn with Recurly Engage</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
      </div>
    </div>

    <!-- Footer nav -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Payment banners</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners" class="rc-footer-link">Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-why" class="rc-footer-link">1. Why it matters</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-use-cases" class="rc-footer-link">2. Use cases</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-webhooks" class="rc-footer-link">3. Webhooks setup</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage" class="rc-footer-link">4. Recurly Engage setup</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-strategy" class="rc-footer-link">5. Strategy &amp; best practices</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-tracking" class="rc-footer-link">6. Tracking your impact</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-review" class="rc-footer-link">7. Review &amp; resources</a>
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
