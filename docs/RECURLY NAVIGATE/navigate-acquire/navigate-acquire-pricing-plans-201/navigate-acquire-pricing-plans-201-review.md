---
title: 'Pricing & Plans 201: Review & resources'
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
  --yellow: #FFD706;
  --orange: #FF8200;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
  color: #32312D !important;
  background: #ffffff;
}
.rc-guide * { box-sizing: border-box; }

/* FA icon helpers */
.rc-fa-section { color: var(--offblack); font-size: 1rem; }
.rc-fa-announce { color: var(--offblack); font-size: 1rem; flex-shrink: 0; }

/* Layout */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Back link */
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

/* Announcement bar */
.rc-announce-bar { display: none; background: var(--yellow); color: var(--offblack); align-items: center; justify-content: space-between; padding: 10px 20px; font-size: .88rem; font-weight: 600; border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4; }
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 10px; flex: 1; flex-wrap: wrap; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-announce-link { color: #0D0D0B !important; font-weight: 800; white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; transition: background 0.2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-announce-link:hover { background: rgba(0,0,0,0.20); color: #0D0D0B !important; }

/* Hero */
.rc-hero { background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)), url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center; background-color: var(--offblack); background-size: cover; color: #fff; padding: 52px 40px 48px; text-align: center; border-radius: 16px; margin-bottom: 0; }
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,215,6,0.20); border: 1px solid rgba(255,215,6,0.45); color: #FFD706; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: #FFFDF2; margin: 0; }
.rc-hero > p { font-size: 1rem; max-width: 640px; margin: 0 auto; color: #CCC9B8; line-height: 1.6; }

/* Nav */
details.rc-sticky-nav-wrap { position: relative; background-color: var(--yellow); box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px 0; border-radius: 12px; border: 1px solid rgba(0,0,0,0.08); overflow: hidden; }
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

/* Sections */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }
.rc-lp-section p:last-child { margin-bottom: 0; }

/* Reflection cards */
.rc-reflect-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-left: 4px solid var(--yellow); border-radius: 14px; padding: 24px 28px; margin: 20px 0; }
.rc-reflect-label { display: inline-block; background: #FFD706; color: #0D0D0B; font-size: .72rem; font-weight: 800; text-transform: uppercase; letter-spacing: .6px; padding: 3px 10px; border-radius: 5px; margin-bottom: 12px; }
.rc-reflect-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 10px; line-height: 1.4; }
.rc-reflect-card p { font-size: .9rem; color: var(--gray); line-height: 1.6; margin: 0; }

/* Quiz cards */
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
.rm-Markdown.markdown-body .rc-guide .rc-quiz-answer a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-quiz-answer a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide .rc-quiz-answer a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide .rc-quiz-answer a:hover { text-decoration: underline !important; text-decoration-color: #FF8200 !important; text-underline-offset: 2px !important; }

/* Path nav */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
.rc-btn-complete { background: var(--brightgray); color: var(--offblack) !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--yellow); cursor: default; user-select: none; }

/* Resources — grouped */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--yellow); border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 16px; display: flex; align-items: center; gap: 8px; }
.rc-resource-group { margin-bottom: 16px; }
.rc-resource-group:last-child { margin-bottom: 0; }
.rc-resource-group-label { font-size: .72rem; font-weight: 800; text-transform: uppercase; letter-spacing: .7px; color: var(--lightgray); margin: 0 0 6px; display: block; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link { color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration-color: #FFD706 !important; }

/* Footer */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link { color: #807D73 !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-footer-link:hover { color: #FF8200 !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* Responsive */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-back-link">← Back to Acquire</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Announcement bar (hidden) -->
    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Join our CSMs for a live pricing Q&amp;A — bring your advanced billing questions.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
    </div>

    <!-- Hero -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Pricing &amp; Plans 201
      </div>
      <div class="rc-lp-hero-title">
        <h1>Review &amp; resources</h1>
      </div>
      <p>Three questions to reinforce the key decision points from this course, and every resource referenced along the way — organized by topic for easy reference.</p>
    </div>

    <!-- Nav — Page 7 (R&R) active -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-sticky-link">Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-segmentation" class="rc-sticky-link"><span class="rc-step-badge">1</span> Price segmentation</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-sticky-link"><span class="rc-step-badge">2</span> Account hierarchy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-sticky-link"><span class="rc-step-badge">3</span> Usage billing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models" class="rc-sticky-link"><span class="rc-step-badge">4</span> Advanced pricing models</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency" class="rc-sticky-link"><span class="rc-step-badge">5</span> Advanced currency</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics" class="rc-sticky-link"><span class="rc-step-badge">6</span> Advanced analytics</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-review" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Review &amp; resources
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- Questions -->
    <div class="rc-lp-section" id="questions">
      <h2><i class="fa-solid fa-circle-question rc-fa-section"></i> Check your understanding</h2>

      <!-- Q1 — Multiple choice -->
      <div class="rc-quiz-card">
        <span class="rc-quiz-label">Question 1 of 3 · Multiple choice</span>
        <p class="rc-quiz-q">A merchant wants to charge $12/month in the US and €9.99/month in Germany without creating a second plan. They also want to run an A/B price test next quarter. Which Recurly feature handles both use cases — and what must they set up externally before activating it?</p>
        <div class="rc-quiz-options" id="quiz1">
          <label class="rc-quiz-option">
            <input type="radio" name="quiz1" value="a">
            <div class="rc-radio-dot"></div>
            <span class="rc-option-text">Coupons — no external setup needed, Recurly tracks coupon performance natively</span>
          </label>
          <label class="rc-quiz-option rc-quiz-correct">
            <input type="radio" name="quiz1" value="b">
            <div class="rc-radio-dot"></div>
            <span class="rc-option-text">Price segments — and they must set up external analytics to track segment performance before activating</span>
          </label>
          <label class="rc-quiz-option">
            <input type="radio" name="quiz1" value="c">
            <div class="rc-radio-dot"></div>
            <span class="rc-option-text">Separate plans per market — no external setup needed</span>
          </label>
          <label class="rc-quiz-option">
            <input type="radio" name="quiz1" value="d">
            <div class="rc-radio-dot"></div>
            <span class="rc-option-text">Price segments — Recurly's built-in dashboards track segment performance automatically</span>
          </label>
        </div>
        <details class="rc-quiz-reveal">
          <summary>See answer</summary>
          <div class="rc-quiz-answer">
            <strong>Price segments, with external analytics set up first.</strong> Segments let a single plan carry multiple price points — per currency, per cohort, per acquisition channel — eliminating the need for duplicate plans. But Recurly's built-in analytics do not filter by segment code. Before running a price test or geographic rollout, the merchant must capture <code>price_segment_code</code> in an external tool or data warehouse. A test you can't measure isn't a test.
          </div>
        </details>
      </div>

      <!-- Q2 — Multiple choice -->
      <div class="rc-quiz-card">
        <span class="rc-quiz-label">Question 2 of 3 · Multiple choice</span>
        <p class="rc-quiz-q">An enterprise customer has three subsidiaries in different countries. They want one consolidated invoice going to headquarters. Which of the following is a genuine risk to evaluate before activating Invoice Rollup across all three?</p>
        <div class="rc-quiz-options" id="quiz2">
          <label class="rc-quiz-option">
            <input type="radio" name="quiz2" value="a">
            <div class="rc-radio-dot"></div>
            <span class="rc-option-text">Invoice Rollup will cancel existing subscriptions on child accounts</span>
          </label>
          <label class="rc-quiz-option">
            <input type="radio" name="quiz2" value="b">
            <div class="rc-radio-dot"></div>
            <span class="rc-option-text">Invoice Rollup is not available on any Recurly plan</span>
          </label>
          <label class="rc-quiz-option rc-quiz-correct">
            <input type="radio" name="quiz2" value="c">
            <div class="rc-radio-dot"></div>
            <span class="rc-option-text">When children have different shipping addresses, Recurly taxes each line item by shipping destination — which may create multi-jurisdiction tax complexity</span>
          </label>
          <label class="rc-quiz-option">
            <input type="radio" name="quiz2" value="d">
            <div class="rc-radio-dot"></div>
            <span class="rc-option-text">Invoice Rollup requires the merchant to rebuild all subscription plans</span>
          </label>
        </div>
        <details class="rc-quiz-reveal">
          <summary>See answer</summary>
          <div class="rc-quiz-answer">
            <strong>Multi-jurisdiction tax complexity.</strong> When Invoice Rollup is active and child accounts have different shipping addresses, Recurly taxes each line item based on its shipping destination. For subsidiaries in different countries, this means each subsidiary's charges are taxed at their local rate — which may create compliance complexity that the customer's tax team needs to review before activation. Invoice Rollup also requires the Elite plan and support team activation, so plan lead time into the enterprise onboarding timeline.
          </div>
        </details>
      </div>

      <!-- Q3 — Reflection -->
      <div class="rc-reflect-card">
        <span class="rc-reflect-label">Question 3 of 3 · Reflection</span>
        <h4>Look at your current billing setup. Which of the six capabilities covered in this course — segmentation, hierarchy, usage billing, hybrid pricing, advanced currency, or advanced analytics — is most likely to unlock meaningful value for your business in the next 12 months?</h4>
        <p>For each one you're considering: what is the specific problem it solves, what is the engineering or operational dependency that would need to be in place first, and who else in your organization would need to be aligned before you could activate it? Bringing concrete answers to these questions to a Global Office Hours session is a good use of 30 minutes with a CSM.</p>
      </div>
    </div>

    <!-- Path nav — complete state -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics" class="rc-btn-prev">← Advanced analytics</a>
      <span class="rc-lp-nav-indicator">7 of 7</span>
      <span class="rc-btn-complete"><i class="fa-solid fa-circle-check"></i> Course complete!</span>
    </div>

    <!-- Resources — grouped (8+ links) -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> All course resources</h3>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Price segmentation</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Plans (price segments)</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/subscriptions-exports" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Subscriptions export</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/change-subscription" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Change subscription</a>
          <a href="https://recurly.com/blog/product-announcement-segmented-pricing-one-plan-for-multiple-price/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Recurly Blog: Segmented pricing</a>
        </div>
      </div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Account hierarchy</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/account-hierarchy-1" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Account hierarchy</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/ah-invoice-rollup" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Invoice Rollup</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/calendar-billing" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Calendar billing</a>
          <a href="https://recurly.com/blog/account-hierarchy-enables-parent-child-billing-for-increased-efficiency/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Recurly Blog: Account hierarchy &amp; parent-child billing</a>
        </div>
      </div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Usage billing</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/usage-based-billing" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Usage-based billing</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/usage-based-pricing-guide" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Usage-based pricing guide (API)</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/add-ons" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Add-ons</a>
        </div>
      </div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Advanced pricing models</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/hybrid-pricing" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Hybrid pricing</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/prepaid-account-balance" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Prepaid account balance</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/billing-models" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Pricing models overview</a>
        </div>
      </div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Advanced currency</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/currencies" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Currencies</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/custom-gateway-routing-configuration" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Custom gateway routing</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/3d-secure-20-integration-guide" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: 3DS2 integration guide</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-configuration-for-3ds-2-declines" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Dunning for 3DS2 declines</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/gateway-failover" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Gateway failover</a>
          <a href="https://docs.recurly.com/docs/revised-payment-services-directive-psd2" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: PSD2 compliance</a>
        </div>
      </div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Advanced analytics</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-analytics-overview" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Analytics overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-builder" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Explore overview (Elite)</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/export-overview" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Data exports overview</a>
        </div>
      </div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Get support</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Pricing &amp; Plans 101</a>
          <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Global Office Hours</a>
          <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
        </div>
      </div>

    </div>

    <!-- Footer -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Pricing &amp; Plans 201</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-footer-link">Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-segmentation" class="rc-footer-link">1. Price segmentation</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-footer-link">2. Account hierarchy</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-footer-link">3. Usage billing</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models" class="rc-footer-link">4. Advanced pricing models</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency" class="rc-footer-link">5. Advanced currency</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics" class="rc-footer-link">6. Advanced analytics</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-review" class="rc-footer-link">7. Review &amp; resources</a>
        </div>
        <div class="rc-footer-utility">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
            <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
          </a>
          <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
        </div>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
