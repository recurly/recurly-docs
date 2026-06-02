---
title: 'Payment Banners: Review & resources'
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
.rc-fa-section { color: var(--offblack); font-size: 1rem; }

/* ── LAYOUT ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Back link */
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

/* ── ANNOUNCEMENT BAR (hidden) ── */
.rc-announce-bar { display: none; }

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
  position: relative; z-index: 1; background-color: var(--retain);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px; border-radius: 12px;
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
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:hover,
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; }

/* ── CONTENT SECTIONS ── */
.rc-lp-section { margin-bottom: 52px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section > p { font-size: .97rem; line-height: 1.7; color: var(--darkgray); margin: 0 0 24px; }

/* ── MULTIPLE CHOICE QUIZ — pure CSS, no JS ── */
.rc-quiz { display: flex; flex-direction: column; gap: 28px; margin: 20px 0 0; }
.rc-quiz-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 14px; overflow: hidden; }
.rc-quiz-header { padding: 18px 24px 14px; border-bottom: 1px solid var(--brightgray); }
.rc-quiz-label { font-size: .68rem; font-weight: 800; text-transform: uppercase; letter-spacing: .9px; color: var(--yellow); background: var(--offblack); display: inline-block; padding: 3px 8px; border-radius: 5px; margin-bottom: 10px; }
.rc-quiz-q { font-size: 1rem; font-weight: 800; color: var(--offblack); line-height: 1.4; margin: 0; }
.rc-quiz-options { padding: 14px 24px 10px; display: flex; flex-direction: column; gap: 7px; }
.rc-quiz-option { display: flex; align-items: flex-start; gap: 10px; padding: 10px 14px; border-radius: 8px; border: 1px solid var(--lightgray); background: #fff; cursor: pointer; transition: all .15s; }
.rc-quiz-option:hover { background: var(--brightgray); }
.rc-quiz-option input[type="radio"] { position: absolute; opacity: 0; width: 0; height: 0; pointer-events: none; }
.rc-radio-dot { width: 18px; height: 18px; border-radius: 50%; border: 2px solid var(--lightgray); flex-shrink: 0; margin-top: 1px; transition: all .15s; background: #fff; }
/* Selected — any option */
.rc-quiz-option:has(input[type="radio"]:checked) .rc-radio-dot { background: var(--offblack); border-color: var(--offblack); box-shadow: inset 0 0 0 4px #fff; }
.rc-quiz-option:has(input[type="radio"]:checked) { background: rgba(13,13,11,0.04); border-color: var(--darkgray); }
/* Correct answer when selected */
.rc-quiz-option.rc-correct:has(input[type="radio"]:checked) { background: rgba(255,157,136,0.09); border-color: var(--retain); }
.rc-quiz-option.rc-correct:has(input[type="radio"]:checked) .rc-radio-dot { background: var(--retain); border-color: var(--retain); box-shadow: inset 0 0 0 4px #fff; }
/* Wrong answer when selected */
.rc-quiz-option:not(.rc-correct):has(input[type="radio"]:checked) { background: rgba(255,130,0,0.06); border-color: var(--orange); }
.rc-quiz-option:not(.rc-correct):has(input[type="radio"]:checked) .rc-radio-dot { background: var(--orange); border-color: var(--orange); box-shadow: inset 0 0 0 4px #fff; }
.rc-option-text { font-size: .88rem; color: var(--darkgray); line-height: 1.4; flex: 1; }
/* Answer reveal */
details.rc-quiz-reveal { margin: 4px 24px 20px; }
details.rc-quiz-reveal > summary { font-size: .8rem; font-weight: 700; color: var(--gray); cursor: pointer; user-select: none; padding: 8px 0 4px; list-style: none; display: inline-flex; align-items: center; gap: 6px; }
details.rc-quiz-reveal > summary::-webkit-details-marker { display: none; }
details.rc-quiz-reveal > summary::marker { display: none; }
details.rc-quiz-reveal > summary::before { content: "▶"; font-size: .58rem; transition: transform .2s; display: inline-block; }
details.rc-quiz-reveal[open] > summary::before { transform: rotate(90deg); }
details.rc-quiz-reveal[open] > summary { color: var(--offblack); }
.rc-quiz-answer { background: var(--brightgray); border-left: 4px solid var(--offblack); border-radius: 0 8px 8px 0; padding: 14px 18px; margin-top: 6px; }
.rc-quiz-answer p { font-size: .88rem; color: var(--darkgray); line-height: 1.6; margin: 0; }
.rc-quiz-answer strong { color: var(--offblack); }

/* ── REFLECTION CARD ── */
.rc-reflect-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-left: 4px solid var(--yellow); border-radius: 14px; padding: 24px 28px; margin-top: 28px; }
.rc-reflect-label { font-size: .68rem; font-weight: 800; text-transform: uppercase; letter-spacing: .9px; color: var(--offblack); background: var(--yellow); display: inline-block; padding: 3px 8px; border-radius: 5px; margin-bottom: 12px; }
.rc-reflect-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 10px; line-height: 1.4; }
.rc-reflect-card p { font-size: .9rem; color: var(--gray); line-height: 1.6; margin: 0 0 8px; }
.rc-reflect-card p:last-child { margin-bottom: 0; }
.rc-reflect-card strong { color: var(--darkgray); }

/* ── ACCENT CARDS ── */
.rc-accent-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 20px 0; }
.rc-accent-card.rc-accent-retain { border-left: 4px solid var(--retain); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 12px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.7; margin: 0 0 8px; }
.rc-accent-card ul { font-size: .9rem; color: var(--gray); line-height: 1.8; padding-left: 20px; margin: 8px 0 0; }
.rc-accent-card ul li { margin-bottom: 4px; }
.rc-accent-card ul li strong { color: var(--darkgray); }

/* ── PATH NAV BUTTONS ── */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 44px 0 0; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; text-align: center; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev {
  background: transparent; color: #0D0D0B !important; text-decoration: none !important;
  padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem;
  display: inline-flex; align-items: center; gap: 8px;
  border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s;
}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
/* Completion indicator — inert span, no click target, per Component 16 */
.rc-btn-complete { background: var(--brightgray); color: var(--offblack) !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--yellow); cursor: default; user-select: none; }

/* ── CONTINUE YOUR JOURNEY — rc-next-card ── */
.rc-next-steps { margin: 40px 0 0; }
.rc-next-steps h3 { font-size: .78rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 16px; display: flex; align-items: center; gap: 8px; }
.rc-next-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; }
/* Card is the <a> — border-bottom needs double-prefix to beat armor */
.rm-Markdown.markdown-body .rc-guide a.rc-next-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-next-card {
  background: var(--offwhite); border: 1px solid #CCC9B8; border-bottom: 1px solid #CCC9B8 !important;
  border-radius: 12px; padding: 20px; color: inherit;
  display: flex; flex-direction: column; gap: 8px; transition: all .2s ease;
}
.rm-Markdown.markdown-body .rc-guide a.rc-next-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-next-card:hover {
  border-color: #FF9D88 !important; border-bottom: 1px solid #FF9D88 !important;
  box-shadow: 0 4px 16px rgba(255,157,136,0.15); transform: translateY(-2px);
}
.rc-next-card-tag { font-size: .68rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: #FF9D88 !important; margin-bottom: 2px; }
.rc-next-card-icon { font-size: 1.3rem; line-height: 1; color: #0D0D0B !important; }
.rc-next-card h4 { font-size: .95rem; font-weight: 800; color: #0D0D0B !important; margin: 0; line-height: 1.3; }
.rc-next-card p { font-size: .85rem; color: #807D73 !important; line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-next-card-arrow { font-size: .82rem; font-weight: 700; color: #FF8200 !important; margin-top: 4px; }

/* ── RESOURCES ── */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--retain); border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 14px; display: flex; align-items: center; gap: 8px; }
.rc-resource-group { margin-bottom: 16px; }
.rc-resource-group:last-child { margin-bottom: 0; }
.rc-resource-group-label { font-size: .72rem; font-weight: 800; text-transform: uppercase; letter-spacing: .7px; color: var(--lightgray); margin: 0 0 6px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link {
  color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px;
  text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem;
  transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration-color: #FF9D88 !important; }

/* ── FOOTER NAV ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link { color: #807D73 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:hover,
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
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; }
  .rc-next-grid { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">

  <div class="rc-announce-bar"></div>

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
        <h1>Review &amp; resources</h1>
      </div>
      <p>Two questions to close the course — then everything you need to put payment banners to work.</p>
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

    <!-- Nav: non-sticky, open. Active: page 7 (R&R) -->
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
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-strategy" class="rc-sticky-link"><span class="rc-step-badge">5</span> Strategy &amp; best practices</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-tracking" class="rc-sticky-link"><span class="rc-step-badge">6</span> Tracking your impact</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-review" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Review &amp; resources
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- Section: Check your understanding -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-circle-question rc-fa-section"></i> Check your understanding</h2>

      <div class="rc-quiz">

        <!-- Q1: Multiple choice — strategic/action-oriented -->
        <div class="rc-quiz-card">
          <div class="rc-quiz-header">
            <div class="rc-quiz-label">Question 1 of 2 · Multiple choice</div>
            <p class="rc-quiz-q">Your Recurly Analytics shows 40% of subscriber losses last quarter were involuntary — matching the industry average. You already have dunning emails configured. A colleague argues that matching the benchmark means your recovery setup is performing as expected. What's the most important thing missing from that assessment?</p>
          </div>
          <div class="rc-quiz-options">
            <label class="rc-quiz-option">
              <input type="radio" name="q1">
              <div class="rc-radio-dot"></div>
              <span class="rc-option-text">A. Dunning email open rates — if subscribers aren't opening the emails, the benchmark comparison is misleading</span>
            </label>
            <label class="rc-quiz-option">
              <input type="radio" name="q1">
              <div class="rc-radio-dot"></div>
              <span class="rc-option-text">B. Whether the 40% is trending up month over month, which would invalidate the benchmark as a baseline</span>
            </label>
            <label class="rc-quiz-option rc-correct">
              <input type="radio" name="q1">
              <div class="rc-radio-dot"></div>
              <span class="rc-option-text">C. In-session recovery coverage — the 40% benchmark represents what most businesses achieve without payment banners. Reaching it signals an opportunity, not a ceiling.</span>
            </label>
            <label class="rc-quiz-option">
              <input type="radio" name="q1">
              <div class="rc-radio-dot"></div>
              <span class="rc-option-text">D. Competitor pricing data — involuntary churn at the benchmark level may indicate price sensitivity masking as payment failure</span>
            </label>
          </div>
          <details class="rc-quiz-reveal">
            <summary>Reveal answer</summary>
            <div class="rc-quiz-answer">
              <p><strong>C is correct.</strong> The 40% stat describes what merchants typically achieve with dunning emails and Account Updater but without in-session payment banners — it's the industry baseline, not the ceiling. Merchants who add payment banners to their stack reach subscribers in the moment dunning emails can't: when they're actively inside the product. "Matching the average" is the signal to act, not to stop. Option A is a useful diagnostic but doesn't identify the structural gap in the recovery stack. Option B matters for trend analysis, but even a stable 40% represents significant recoverable revenue. Option D misidentifies the cause — involuntary churn is definitionally a payment processing failure, not a pricing issue.</p>
            </div>
          </details>
        </div>

      </div>

      <!-- Q2: Reflection card -->
      <div class="rc-reflect-card">
        <div class="rc-reflect-label">Question 2 of 2 · Reflection</div>
        <h4>Look at your dunning email open rate. The gap between that number and 100% is your payment banner opportunity — those are subscribers your recovery emails are missing in the moment. Given what you've learned in this course, which scenario would you deploy first, and what would your first banner say?</h4>
        <p>Start with the trigger that has the most subscribers — whether that's an expiring card pool, an active failed-payment cohort, or an upcoming annual renewal. Then ask: do your subscribers primarily live inside your own app, or in a Recurly-hosted subscriber portal? <strong>That single question determines whether webhooks or Recurly Engage is the faster path to live.</strong> From there, write one sentence of banner copy — specific enough to name the card, the date, or the amount — and you'll have your starting point.</p>
      </div>
    </div>

    <!-- Path navigation -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-tracking" class="rc-btn-prev">← Tracking your impact</a>
      <span class="rc-lp-nav-indicator">7 of 7 · Payment banners</span>
      <span class="rc-btn-complete"><i class="fa-solid fa-circle-check"></i> Course complete!</span>
    </div>

    <!-- Continue your journey -->
    <div class="rc-next-steps">
      <h3><i class="fa-solid fa-compass rc-fa-section"></i> Continue your journey</h3>
      <div class="rc-next-grid">

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" class="rc-next-card">
          <div class="rc-next-card-tag">Recommended next</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-rotate"></i></div>
          <h4>Account Updater</h4>
          <p>Payment banners handle active subscribers. Account Updater handles everyone else — silently recovering card details before a payment ever fails. The two features together give you full coverage.</p>
          <div class="rc-next-card-arrow">Start course →</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101" class="rc-next-card">
          <div class="rc-next-card-tag">Deepen your retention stack</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-envelope-open-text"></i></div>
          <h4>Dunning 101</h4>
          <p>Payment banners and dunning work best together. If you haven't yet built out your dunning sequence — or want to optimize what you have — this is the natural next step.</p>
          <div class="rc-next-card-arrow">Start course →</div>
        </a>

        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-next-card">
          <div class="rc-next-card-tag">Live session</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-microphone"></i></div>
          <h4>Global Office Hours</h4>
          <p>Bring your implementation questions, strategy decisions, and measurement questions to our CSMs live. Sessions run weekly and are free for all Recurly customers.</p>
          <div class="rc-next-card-arrow">Register →</div>
        </a>

      </div>
    </div>

    <!-- All course resources — grouped -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> All course resources</h3>

      <div class="rc-resource-group">
        <div class="rc-resource-group-label">Recurly Engage</div>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-engage/docs/failed-rebill" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Payment Failure Guide</a>
          <a href="https://support.recurly.com/hc/en-us/articles/41994057703316-How-do-I-set-up-a-Payment-Failure-Guide-in-Recurly-Engage" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> How to set up a Payment Failure Guide</a>
          <a href="https://docs.recurly.com/recurly-engage/docs/in-prompt-billing" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> In-Prompt Billing</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-engage-integration" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Engage integration guide</a>
          <a href="https://support.recurly.com/hc/en-us/articles/41993539482516" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Cancellation Save Guide</a>
          <a href="https://docs.recurly.com/recurly-engage/docs/popular-uses" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Popular Recurly Engage use cases</a>
          <a href="https://support.recurly.com/hc/en-us/articles/41994337356180-How-Can-I-A-B-Test-Different-Prompt-Experiences-in-Recurly-Engage" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> A/B testing prompt experiences</a>
          <a href="https://docs.recurly.com/recurly-engage/docs/overlays" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Overlay prompt types</a>
          <a href="https://docs.recurly.com/recurly-engage/docs/inlines" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Inline prompt types</a>
        </div>
      </div>

      <div class="rc-resource-group">
        <div class="rc-resource-group-label">Webhooks</div>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/push-notifications" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Webhooks overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/webhook-notifications" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Webhook event reference</a>
        </div>
      </div>

      <div class="rc-resource-group">
        <div class="rc-resource-group-label">Strategy &amp; benchmarks</div>
        <div class="rc-resource-links">
          <a href="https://recurly.com/research/subscriber-retention-benchmarks/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Subscriber retention benchmarks</a>
          <a href="https://recurly.com/blog/dunning" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> All about dunning</a>
          <a href="https://support.recurly.com/hc/en-us/articles/44224955931924-What-Are-the-Best-Practices-for-Initial-and-Recurring-Payment-Failure-Recovery" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Best practices for payment failure recovery</a>
          <a href="https://recurly.com/blog/cancellation-flow-examples-to-improve-subscriber-retention/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Cancellation flow examples</a>
          <a href="https://recurly.com/resources/guide/10-plays-to-drive-subscriber-upsells-and-reduce-churn-recurly-engage/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> 10 plays to reduce churn with Recurly Engage</a>
          <a href="https://recurly.com/resources/webinar/revenue-recovery-on-demand-video/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-play-circle"></i> Revenue recovery webinar (on-demand)</a>
        </div>
      </div>

      <div class="rc-resource-group" style="margin-bottom:0;">
        <div class="rc-resource-group-label">Get support</div>
        <div class="rc-resource-links">
          <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
          <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
        </div>
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
