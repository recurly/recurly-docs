---
title: 'Plan Price Increase: Review & resources'
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
.rc-guide h1 { border-bottom: none !important; padding-bottom: 0 !important; }
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

/* ── BACK LINK — (0,0,8,1) ── */
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

/* ── NAV — non-sticky, open (Course page) ── */
details.rc-sticky-nav-wrap {
  position: relative; z-index: 1;
  background-color: var(--yellow);
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
.rc-guide a.rc-sticky-link { color: #0D0D0B !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
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

/* ── CONGRATULATORY BLOCK ── */
.rc-congrats-block {
  background: var(--offblack); border-radius: 16px; padding: 40px 48px;
  text-align: center; margin-bottom: 48px; border: 1px solid rgba(255,255,255,0.06);
}
.rc-congrats-badge {
  display: inline-flex; align-items: center; gap: 8px;
  background: rgba(255,215,6,0.15); border: 1px solid rgba(255,215,6,0.30);
  color: #FFD706; font-size: .72rem; font-weight: 800; letter-spacing: 1px;
  text-transform: uppercase; padding: 6px 16px; border-radius: 20px; margin-bottom: 20px;
}
.rc-congrats-block h2 {
  font-size: 1.6rem; font-weight: 800; color: #FFFDF2 !important;
  margin: 0 0 16px; border-bottom: none !important; padding-bottom: 0 !important;
  display: block;
}
.rc-congrats-block h2::after { display: none; }
.rc-congrats-block p { font-size: 1rem; color: #CCC9B8 !important; line-height: 1.65; max-width: 620px; margin: 0 auto; }
.rc-congrats-icon { color: #FFD706 !important; font-size: 2.2rem; margin-bottom: 16px; display: block; }

/* ── REFLECTION CARDS ── */
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

/* ── QUIZ CARD ── */
.rc-quiz-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 14px; overflow: hidden; padding: 22px 24px; margin: 20px 0; }
.rc-quiz-label { display: inline-block; background: var(--offblack); color: var(--yellow); font-size: .72rem; font-weight: 800; text-transform: uppercase; letter-spacing: .6px; padding: 3px 8px; border-radius: 5px; margin-bottom: 10px; }
.rc-quiz-q { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 16px; line-height: 1.45; }
.rc-quiz-options { display: flex; flex-direction: column; gap: 8px; margin-bottom: 16px; }
.rc-quiz-option { display: flex; align-items: center; gap: 10px; padding: 10px 14px; border-radius: 8px; border: 1px solid var(--lightgray); background: #fff; cursor: pointer; transition: all .18s; }
.rc-quiz-option input[type="radio"] { position: absolute; opacity: 0; width: 0; height: 0; pointer-events: none; }
.rc-radio-dot { width: 16px; height: 16px; border-radius: 50%; border: 2px solid var(--lightgray); flex-shrink: 0; background: #fff; transition: all .18s; }
.rc-quiz-option:has(input[type="radio"]:checked) .rc-radio-dot { background: var(--offblack); border-color: var(--offblack); }
.rc-option-text { font-size: .9rem; color: var(--darkgray); line-height: 1.4; }
.rc-quiz-option.rc-quiz-correct:has(input[type="radio"]:checked) { background: rgba(106,177,135,0.10); border-color: #6ab187; }
.rc-quiz-option:not(.rc-quiz-correct):has(input[type="radio"]:checked) { background: rgba(255,130,0,0.08); border-color: var(--orange); }
details.rc-quiz-reveal > summary::-webkit-details-marker { display: none; }
details.rc-quiz-reveal > summary::marker { display: none; }
details.rc-quiz-reveal > summary::before { content: "▶"; font-size: .58rem; display: inline-block; transition: transform .2s; margin-right: 6px; }
details.rc-quiz-reveal[open] > summary::before { transform: rotate(90deg); }
details.rc-quiz-reveal > summary { font-size: .82rem; font-weight: 700; color: var(--gray); cursor: pointer; user-select: none; display: inline-flex; align-items: center; }
.rc-quiz-answer { margin-top: 10px; background: var(--brightgray); border-radius: 8px; padding: 12px 16px; font-size: .88rem; color: var(--darkgray); line-height: 1.55; }
.rc-quiz-answer strong { color: var(--offblack); }

/* ── CONTINUE YOUR JOURNEY ── */
.rc-next-steps { margin: 40px 0 0; }
.rc-next-steps h3 { font-size: .78rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 16px; display: flex; align-items: center; gap: 8px; }
.rc-next-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; }
.rc-next-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 20px; text-decoration: none !important; color: inherit; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-guide a.rc-next-card { border-bottom: 1px solid var(--lightgray) !important; }
.rc-guide a.rc-next-card:hover { border-color: #FFD706; border-bottom: 1px solid #FFD706 !important; box-shadow: 0 4px 16px rgba(255,215,6,0.20); transform: translateY(-2px); }
.rc-next-card-tag { font-size: .68rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: #FFD706 !important; margin-bottom: 2px; }
.rc-next-card-icon { font-size: 1.3rem; line-height: 1; color: #0D0D0B !important; }
.rc-next-card h4 { font-size: .95rem; font-weight: 800; color: #0D0D0B !important; margin: 0; line-height: 1.3; }
.rc-next-card p { font-size: .85rem; color: #807D73 !important; line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-next-card-arrow { font-size: .82rem; font-weight: 700; color: #FF8200 !important; margin-top: 4px; }

/* ── PATH NAV BUTTONS ── */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
.rc-btn-complete { background: var(--brightgray); color: var(--offblack) !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--yellow); cursor: default; user-select: none; }

/* ── RESOURCES ── */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--yellow); border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 16px; display: flex; align-items: center; gap: 8px; }
.rc-resource-group { margin-bottom: 16px; }
.rc-resource-group:last-child { margin-bottom: 0; }
.rc-resource-group-label { font-size: .72rem; font-weight: 800; text-transform: uppercase; letter-spacing: .7px; color: var(--lightgray); margin: 0 0 6px; display: block; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link { color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FFD706 !important; }

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

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-next-grid { grid-template-columns: 1fr; }
  .rc-congrats-block { padding: 28px 24px; }
}
</style>

<div class="rc-guide">

  <!-- BACK LINK -->
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-back-link">← Back to Acquire</a>
  </div>

  <div class="rc-content-wrap">

    <!-- ANNOUNCEMENT BAR — add class rc-active to show before publishing -->
    <div class="rc-announce-bar">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Bring your pricing questions to a live CSM session.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
    </div>

    <!-- HERO -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Plan price increase
      </div>
      <div class="rc-lp-hero-title">
        <h1>Plan price increase: review &amp; resources</h1>
      </div>
      <p>You've completed the course. Test your knowledge, reflect on your approach, and bookmark the references you'll need when it's time to execute.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">6</div>
          <div class="rc-hero-stat-label">Pages completed</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">3</div>
          <div class="rc-hero-stat-label">Subscriber migration methods</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">90</div>
          <div class="rc-hero-stat-label">Day monitoring window</div>
        </div>
      </div>
    </div>

    <!-- NAV — non-sticky, open (Course page, step 7 of 7 active) -->
    <!-- NOTE: Update all href values below to match the actual slugs in your ReadMe instance -->
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
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-considerations" class="rc-sticky-link">
          <span class="rc-step-badge">2</span> Things to consider
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
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-review" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Review &amp; resources
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- CONGRATULATORY BLOCK -->
    <div class="rc-congrats-block">
      <i class="fa-solid fa-circle-check rc-congrats-icon"></i>
      <div class="rc-congrats-badge"><i class="fa-solid fa-trophy" style="font-size:.8rem;"></i> Course complete</div>
      <h2>You've finished Plan price increase</h2>
      <p>You now know how to evaluate when and how much to raise prices, prepare your subscriber segments, execute the change in Recurly, communicate with your base, and track the impact over time. Use the questions and resources below to consolidate what you've learned — and as a reference when you're ready to act.</p>
    </div>

    <!-- KNOWLEDGE CHECK: MULTIPLE CHOICE -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-clipboard-question rc-fa-section"></i> Knowledge check</h2>
      <p>One question to confirm a key concept from the course.</p>

      <div class="rc-quiz-card">
        <span class="rc-quiz-label">Question 1 of 2 · Multiple choice</span>
        <p class="rc-quiz-q">You need to move 500 existing subscribers from an old plan price to the new one. Which approach does Recurly support for this at scale?</p>

        <div class="rc-quiz-options" id="quiz1">

          <label class="rc-quiz-option">
            <input type="radio" name="quiz1" value="a">
            <div class="rc-radio-dot"></div>
            <span class="rc-option-text">Edit each subscription individually in the Recurly admin dashboard</span>
          </label>

          <label class="rc-quiz-option">
            <input type="radio" name="quiz1" value="b">
            <div class="rc-radio-dot"></div>
            <span class="rc-option-text">Update the plan price — all existing subscriptions automatically reflect the new amount</span>
          </label>

          <label class="rc-quiz-option rc-quiz-correct">
            <input type="radio" name="quiz1" value="c">
            <div class="rc-radio-dot"></div>
            <span class="rc-option-text">Use a bulk CSV import or the Recurly API to update subscriptions in a single operation</span>
          </label>

          <label class="rc-quiz-option">
            <input type="radio" name="quiz1" value="d">
            <div class="rc-radio-dot"></div>
            <span class="rc-option-text">Cancel all affected subscriptions and ask subscribers to resubscribe at the new rate</span>
          </label>

        </div>

        <details class="rc-quiz-reveal">
          <summary>See answer</summary>
          <div class="rc-quiz-answer">
            <strong>Use a bulk CSV import or the Recurly API.</strong> Recurly does not automatically apply a plan price change to existing subscriptions — you need to migrate them intentionally. For large volumes, a bulk subscription update via CSV import or API is the recommended approach. Editing subscriptions individually works for small numbers but doesn't scale.
          </div>
        </details>
      </div>
    </div>

    <!-- REFLECTION -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-brain rc-fa-section"></i> Reflection</h2>
      <p>Take a moment to connect the course material to your actual subscriber base and business context.</p>

      <div class="rc-reflect-card">
        <span class="rc-reflect-label">Question 2 of 2 · Reflection</span>
        <h4>Your team has approved a price increase effective in 60 days. Looking at your own subscriber base, which segment concerns you most — and which communication strategy from this course would you apply to them first?</h4>
        <p>Think about your longest-tenured subscribers, your highest-volume plan, and which segment is most price-sensitive. Consider whether grandfathering, an extended notice window, or a personalized message would be most effective for that group.</p>
      </div>
    </div>

    <!-- CONTINUE YOUR JOURNEY -->
    <div class="rc-next-steps"style="display: none;">
      <h3><i class="fa-solid fa-compass rc-fa-section"></i> Continue your journey</h3>
      <div class="rc-next-grid">

        <!-- TODO: Replace href below with the actual next Acquire path URL when available -->
        <a href="#" class="rc-next-card">
          <div class="rc-next-card-tag">Recommended next</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-arrow-up-right-dots"></i></div>
          <h4>Subscription upgrades &amp; downgrades</h4>
          <p>Price changes often prompt subscribers to reconsider their plan tier. Learn how to configure and manage plan changes mid-cycle so you're ready for the movement that follows a price increase.</p>
          <div class="rc-next-card-arrow">Start path →</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-next-card">
          <div class="rc-next-card-tag">Explore the pillar</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-layer-group"></i></div>
          <h4>All Acquire paths</h4>
          <p>See every learning path in the Acquire pillar — covering plan setup, pricing strategy, trials, coupons, and more.</p>
          <div class="rc-next-card-arrow">View Acquire →</div>
        </a>

        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-next-card">
          <div class="rc-next-card-tag">Live session</div>
          <div class="rc-next-card-icon"><i class="fa-solid fa-microphone"></i></div>
          <h4>Global Office Hours</h4>
          <p>Bring your price increase questions — or your rollout plan — to our CSMs live. Sessions run weekly.</p>
          <div class="rc-next-card-arrow">Register →</div>
        </a>

      </div>
    </div>

    <!-- PATH NAV BUTTONS -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-impact" class="rc-btn-prev">← Track the impact</a>
      <span class="rc-lp-nav-indicator">6 of 6</span>
      <span class="rc-btn-complete"><i class="fa-solid fa-circle-check"></i> Course complete!</span>
    </div>

    <!-- RESOURCES — grouped (10+ links consolidated from all 6 course pages) -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Planning your increase</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Managing subscription plans</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/plan-changes" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Plan changes overview</a>
        </div>
      </div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Executing the change</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/subscription-updates" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Updating a subscription</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/import-subscriptions" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Bulk subscription imports via CSV</a>
          <a href="https://recurly.com/developers/api/v2021-02-25/index.html#tag/Subscriptions/operation/updateSubscription" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly API: Update subscription endpoint</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/custom-price-override" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Subscription-level price override</a>
        </div>
      </div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Communication &amp; notifications</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/email-customization" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Email template customization</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/webhooks" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Webhooks for subscription events</a>
        </div>
      </div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Tracking &amp; analytics</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/revenue-overview" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Revenue overview report</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/subscriber-report" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Subscriber analytics report</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/export-data" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Exporting subscription data</a>
        </div>
      </div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Get support</span>
        <div class="rc-resource-links">
          <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
          <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
        </div>
      </div>

    </div>

    <!-- FOOTER NAV -->
    <!-- NOTE: Update all href values to match your actual ReadMe slugs -->
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

  </div><!-- /rc-content-wrap -->
</div><!-- /rc-guide -->
`}</HTMLBlock>

<br />
