---
title: 'Pricing & Plans 101: Review & resources'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
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
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--darkgray);
}
.rc-guide * { box-sizing: border-box; }
body { margin: 0; background: #fff; }

/* Host-theme armor */
.rc-guide a, .rc-guide a:link, .rc-guide a:visited, .rc-guide a:hover, .rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

/* Layout */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link { color: var(--gray); text-decoration: none !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Announcement bar */
.rc-announce-bar { display: none; background: var(--yellow); color: var(--offblack); align-items: center; justify-content: space-between; padding: 10px 20px; font-size: .88rem; font-weight: 600; border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4; }
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 12px; flex: 1; flex-wrap: wrap; }
.rc-announce-link { color: var(--offblack) !important; font-weight: 800; text-decoration: none !important; white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; transition: background 0.2s; }
.rc-announce-link:hover { background: rgba(0,0,0,0.20); }
.rc-announce-close { background: none; border: none; font-size: 1.4rem; line-height: 1; cursor: pointer; color: var(--offblack); padding: 0 2px; opacity: 0.45; transition: opacity 0.2s; flex-shrink: 0; }
.rc-announce-close:hover { opacity: 1; }

/* Hero */
.rc-hero { background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)), url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center; background-color: #0D0D0B; background-size: cover; color: #fff; padding: 56px 40px 48px; text-align: center; border-radius: 16px; margin-bottom: 0; }
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,215,6,0.20); border: 1px solid rgba(255,215,6,0.45); color: #FFD706; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-completion-badge { font-size: 3rem; line-height: 1; margin-bottom: 16px; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: #FFFDF2; margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: #CCC9B8; line-height: 1.6; }
.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: #FFD706; line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: #CCC9B8; line-height: 1.3; }

/* Nav — non-sticky, open */
details.rc-sticky-nav-wrap { position: relative; background-color: var(--yellow); box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px; border-radius: 12px; border: 1px solid rgba(0,0,0,0.08); overflow: hidden; }
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
.rc-sticky-link { color: var(--offblack) !important; text-decoration: none !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; }
.rc-sticky-link:hover { background: var(--offblack); color: var(--yellow) !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-sticky-link-active { background: rgba(0,0,0,0.12); font-weight: 800; }
.rc-sticky-link-active:hover { background: var(--offblack); color: var(--yellow) !important; }

/* Sections */
.rc-lp-section { margin-bottom: 52px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }
.rc-lp-section p:last-child { margin-bottom: 0; }

/* Path recap grid */
.rc-recap-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 14px; margin: 20px 0 0; }
.rc-recap-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 20px; display: flex; flex-direction: column; gap: 6px; }
.rc-recap-num { font-size: .7rem; font-weight: 800; text-transform: uppercase; letter-spacing: .9px; color: var(--yellow); background: var(--offblack); display: inline-block; padding: 3px 8px; border-radius: 5px; width: fit-content; }
.rc-recap-card h4 { font-size: .95rem; font-weight: 800; color: var(--offblack); margin: 0; line-height: 1.3; }
.rc-recap-card p { font-size: .82rem; color: var(--gray); line-height: 1.5; margin: 0; }

/* Knowledge check */
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
.rc-quiz-option input[type="radio"]:checked ~ .rc-radio-dot { background: var(--offblack); border-color: var(--offblack); box-shadow: inset 0 0 0 4px #fff; }
.rc-quiz-option:has(input[type="radio"]:checked) { background: rgba(13,13,11,0.04); border-color: var(--darkgray); }
.rc-quiz-option-text { font-size: .88rem; color: var(--darkgray); line-height: 1.4; flex: 1; }

/* Answer reveal — uses <details> native toggle, no JS */
details.rc-quiz-reveal { margin: 4px 24px 20px; }
details.rc-quiz-reveal > summary { font-size: .8rem; font-weight: 700; color: var(--gray); cursor: pointer; user-select: none; padding: 8px 0 4px; list-style: none; display: inline-flex; align-items: center; gap: 6px; }
details.rc-quiz-reveal > summary::-webkit-details-marker { display: none; }
details.rc-quiz-reveal > summary::marker { display: none; }
details.rc-quiz-reveal > summary::before { content: "▶"; font-size: .58rem; transition: transform .2s; display: inline-block; }
details.rc-quiz-reveal[open] > summary::before { transform: rotate(90deg); }
.rc-quiz-answer { background: var(--brightgray); border-left: 4px solid var(--offblack); border-radius: 0 8px 8px 0; padding: 14px 18px; margin-top: 6px; }
.rc-quiz-answer p { font-size: .88rem; color: var(--darkgray); line-height: 1.6; margin: 0; }
.rc-quiz-answer strong { color: var(--offblack); }

/* Reflection card */
.rc-reflect-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-left: 4px solid var(--yellow); border-radius: 14px; padding: 24px 28px; }
.rc-reflect-label { font-size: .68rem; font-weight: 800; text-transform: uppercase; letter-spacing: .9px; color: var(--offblack); background: var(--yellow); display: inline-block; padding: 3px 8px; border-radius: 5px; margin-bottom: 12px; }
.rc-reflect-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 10px; line-height: 1.4; }
.rc-reflect-card p { font-size: .9rem; color: var(--gray); line-height: 1.6; margin: 0; }
  .rc-reflect-card strong { color: var(--darkgray); }
  
/* Continue your journey */
.rc-next-steps { margin: 40px 0 0; }
.rc-next-steps h3 { font-size: .78rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 16px; }
.rc-next-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; }
.rc-next-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 20px; text-decoration: none !important; color: inherit; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-guide a.rc-next-card { border-bottom: 1px solid var(--lightgray) !important; }
.rc-guide a.rc-next-card:hover { border-color: #FFD706; border-bottom: 1px solid #FFD706 !important; box-shadow: 0 4px 16px rgba(255,215,6,0.15); transform: translateY(-2px); }
.rc-next-card-tag { font-size: .68rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: var(--yellow); margin-bottom: 2px; }
.rc-next-card-icon { font-size: 1.3rem; line-height: 1; }
.rc-next-card h4 { font-size: .95rem; font-weight: 800; color: var(--offblack); margin: 0; line-height: 1.3; }
.rc-next-card p { font-size: .85rem; color: var(--gray); line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-next-card-arrow { font-size: .82rem; font-weight: 700; color: var(--orange); margin-top: 4px; }



/* Resource library */
.rc-resource-library { display: flex; flex-direction: column; gap: 22px; margin: 20px 0 0; }
.rc-resource-group-label { font-size: .72rem; font-weight: 800; text-transform: uppercase; letter-spacing: .9px; color: var(--darkgray); background: var(--brightgray); padding: 5px 12px; border-radius: 6px; display: inline-block; margin-bottom: 10px; }
.rc-resource-group-links { display: flex; flex-wrap: wrap; gap: 6px 24px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FFD706 !important; }

/* OH CTA */
.rc-oh-cta { background: var(--offblack); border: 2px solid var(--yellow); border-radius: 14px; padding: 32px 36px; margin: 48px 0 0; }
.rc-oh-cta h4 { color: #FFD706; font-size: 1.05rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px; }
.rc-oh-cta p { color: #CCC9B8; font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
.rc-oh-cta p strong { color: #FFFDF2; }
.rc-guide a.rc-oh-btn { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-oh-btn:hover { background: transparent !important; color: var(--yellow) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Footer */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rc-footer-link { color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; }
.rc-footer-link:hover { color: var(--orange); }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* Responsive */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 40px 20px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-recap-grid { grid-template-columns: 1fr 1fr; }
  .rc-oh-cta { padding: 24px 20px; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-back-link">← Back to Path Start</a>
  </div>

  <div class="rc-content-wrap">

    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>Upcoming:</strong> Join our CSMs for a live Pricing &amp; Packaging Q&amp;A.
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- Hero — completion -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Pricing &amp; Plans 101
      </div>
     
      <div class="rc-lp-hero-title"><h1>Pricing &amp; Plans 101 — Review &amp; resources</h1></div>
      <p>You've completed Pricing &amp; Plans 101 — six Micro-Paths covering the full foundation of how Recurly's plan and pricing tools work and how to use them well. Use this page to test what you've learned and find every resource from across the series in one place.</p>
      
    </div>

    <!-- Nav — R&R active, all 6 micro-paths linked -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-sticky-link">Plans</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-sticky-link">Add-Ons</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-sticky-link">Currency</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-sticky-link">Pricing Models</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-sticky-link">Trials</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-sticky-link">Analytics</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-review" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Review &amp; Resources
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- What you covered -->
    <div class="rc-lp-section" id="recap">
      <h2>🗺️ What you covered</h2>
      <p>Six Micro-Paths, each building a distinct piece of the Pricing &amp; Plans foundation. Here's the one-line summary of what each one established.</p>
      <div class="rc-recap-grid">
        <div class="rc-recap-card">
          <div class="rc-recap-num">MP 1</div>
          <h4>Plans</h4>
          <p>The foundational subscription unit — billing interval, pricing, trial, and the decisions that shape every subscription created on it.</p>
        </div>
        <div class="rc-recap-card">
          <div class="rc-recap-num">MP 2</div>
          <h4>Add-Ons</h4>
          <p>Modular revenue layers on top of plans — how to configure them, fixed vs. usage types, and how add-ons drive ARPU growth.</p>
        </div>
        <div class="rc-recap-card">
          <div class="rc-recap-num">MP 3</div>
          <h4>Currency</h4>
          <p>How multi-currency works in Recurly, what must be configured per-currency, and why currency strategy is also a pricing strategy.</p>
        </div>
        <div class="rc-recap-card">
          <div class="rc-recap-num">MP 4</div>
          <h4>Pricing Models</h4>
          <p>Fixed, Ramp, Tiered, Volume, Stairstep — what each model does, when to use it, and the decisions that can't be changed after saving.</p>
        </div>
        <div class="rc-recap-card">
          <div class="rc-recap-num">MP 5</div>
          <h4>Trials</h4>
          <p>How trials work in Recurly, the card-required decision, how to measure trial conversion, and what trials cannot fix.</p>
        </div>
        <div class="rc-recap-card">
          <div class="rc-recap-num">MP 6</div>
          <h4>Analytics</h4>
          <p>The six metrics that matter for P&amp;P decisions, where to find them in Recurly, and how to connect data to pricing action.</p>
        </div>
      </div>
    </div>

    <!-- Knowledge check -->
    <div class="rc-lp-section" id="knowledge-check">
      <h2>🧠 Knowledge check</h2>
      <p>Five questions — three multiple choice and two for reflection. Select your answer on the MCQs, then use the reveal to check your thinking.</p>

      <div class="rc-quiz">

        <!-- Q1 — Pricing Models -->
        <div class="rc-quiz-card">
          <div class="rc-quiz-header">
            <div class="rc-quiz-label">Question 1 · Pricing Models</div>
            <p class="rc-quiz-q">Which pricing model applies a single per-unit rate to <em>all</em> units once the subscriber's total quantity crosses into a new band?</p>
          </div>
          <div class="rc-quiz-options">
            <label class="rc-quiz-option">
              <input type="radio" name="q1">
              <div class="rc-radio-dot"></div>
              <span class="rc-quiz-option-text">A) Tiered — each unit is charged at the rate of the band it individually falls into</span>
            </label>
            <label class="rc-quiz-option">
              <input type="radio" name="q1">
              <div class="rc-radio-dot"></div>
              <span class="rc-quiz-option-text">B) Volume — the total quantity determines a single rate applied to every unit</span>
            </label>
            <label class="rc-quiz-option">
              <input type="radio" name="q1">
              <div class="rc-radio-dot"></div>
              <span class="rc-quiz-option-text">C) Stairstep — a flat fee is charged based on which band the total quantity falls into</span>
            </label>
            <label class="rc-quiz-option">
              <input type="radio" name="q1">
              <div class="rc-radio-dot"></div>
              <span class="rc-quiz-option-text">D) Ramp — the price changes at defined billing cycle intervals over time</span>
            </label>
          </div>
          <details class="rc-quiz-reveal">
            <summary>Reveal answer</summary>
            <div class="rc-quiz-answer">
              <p><strong>B — Volume.</strong> In Volume pricing, the subscriber's total quantity determines which band's per-unit rate applies — and that rate is applied to every unit, not just the ones that fall within the band. A subscriber with 25 seats in a "21–50 = $8/unit" band pays $8 × 25 = $200. Tiered is the key contrast: Tiered charges each unit at the rate of its own band, so units 1–10 pay one rate and units 11–25 pay another, producing a blended total.</p>
            </div>
          </details>
        </div>

        <!-- Q2 — Trials -->
        <div class="rc-quiz-card">
          <div class="rc-quiz-header">
            <div class="rc-quiz-label">Question 2 · Trials</div>
            <p class="rc-quiz-q">You update a plan's trial length from 14 days to 7 days. Which subscriptions does this affect?</p>
          </div>
          <div class="rc-quiz-options">
            <label class="rc-quiz-option">
              <input type="radio" name="q2">
              <div class="rc-radio-dot"></div>
              <span class="rc-quiz-option-text">A) All subscriptions on the plan, including those currently trialing</span>
            </label>
            <label class="rc-quiz-option">
              <input type="radio" name="q2">
              <div class="rc-radio-dot"></div>
              <span class="rc-quiz-option-text">B) Only subscriptions currently in trialing status — their trial is shortened immediately</span>
            </label>
            <label class="rc-quiz-option">
              <input type="radio" name="q2">
              <div class="rc-radio-dot"></div>
              <span class="rc-quiz-option-text">C) Only new subscriptions created after the plan is updated</span>
            </label>
            <label class="rc-quiz-option">
              <input type="radio" name="q2">
              <div class="rc-radio-dot"></div>
              <span class="rc-quiz-option-text">D) No subscriptions — trial settings are locked after a plan goes live</span>
            </label>
          </div>
          <details class="rc-quiz-reveal">
            <summary>Reveal answer</summary>
            <div class="rc-quiz-answer">
              <p><strong>C — Only new subscriptions created after the update.</strong> Trial settings in Recurly are versioned at the plan level. Subscriptions already in trialing status when the plan is updated continue on their original schedule — their trial end date is unaffected. This applies to all plan-level changes: price, trial length, and billing configuration only take effect for subscriptions created after the change is saved.</p>
            </div>
          </details>
        </div>

        <!-- Q3 — Analytics -->
        <div class="rc-quiz-card">
          <div class="rc-quiz-header">
            <div class="rc-quiz-label">Question 3 · Analytics</div>
            <p class="rc-quiz-q">Your churn rate increased last quarter. What should you determine first before deciding on an intervention?</p>
          </div>
          <div class="rc-quiz-options">
            <label class="rc-quiz-option">
              <input type="radio" name="q3">
              <div class="rc-radio-dot"></div>
              <span class="rc-quiz-option-text">A) Whether your pricing is misaligned with competitor benchmarks</span>
            </label>
            <label class="rc-quiz-option">
              <input type="radio" name="q3">
              <div class="rc-radio-dot"></div>
              <span class="rc-quiz-option-text">B) Whether the increase is driven by voluntary churn or involuntary churn from payment failures</span>
            </label>
            <label class="rc-quiz-option">
              <input type="radio" name="q3">
              <div class="rc-radio-dot"></div>
              <span class="rc-quiz-option-text">C) Whether your trial length is too short to establish product value before conversion</span>
            </label>
            <label class="rc-quiz-option">
              <input type="radio" name="q3">
              <div class="rc-radio-dot"></div>
              <span class="rc-quiz-option-text">D) Whether MRR is still growing despite the higher churn rate</span>
            </label>
          </div>
          <details class="rc-quiz-reveal">
            <summary>Reveal answer</summary>
            <div class="rc-quiz-answer">
              <p><strong>B — The voluntary vs. involuntary split.</strong> Voluntary churn (subscriber chose to cancel) and involuntary churn (payment failure) have completely different root causes and interventions. If the increase is mostly involuntary, improving dunning configuration and enabling Recurly's Account Updater will have the fastest impact — and requires no product or pricing changes. Acting on the aggregate churn number without making this split first is a common and costly mistake. Recurly's Churn report lets you filter by churn reason to see the breakdown.</p>
            </div>
          </details>
        </div>

        <!-- Q4 — Reflection: Pricing Models + Analytics -->
        <div class="rc-reflect-card">
          <div class="rc-reflect-label">Reflection · Pricing Models + Analytics</div>
          <h4>You introduced Ramp pricing on your core plan to improve trial-to-paid conversion. After three months, conversion improved — but churn at month 4, when the full price kicks in, also increased. What does this pattern suggest, and what would you investigate first?</h4>
          <p>The conversion improvement indicates the introductory Ramp price removed a real signup barrier. But rising churn at the full-price stage suggests the gap between the two stages may be too large, or that <strong>subscribers aren't reaching a clear product value moment strong enough to justify the full price</strong> before it arrives. The first investigation: cohort retention analysis segmented by whether subscribers completed your product's primary activation event during the ramp period. If non-activated subscribers are churning at month 4 and activated ones aren't, the problem is onboarding speed — not the Ramp schedule or the price level.</p>
        </div>

        <!-- Q5 — Reflection: Add-Ons + Analytics -->
        <div class="rc-reflect-card">
          <div class="rc-reflect-label">Reflection · Add-Ons + Analytics</div>
          <h4>Your optional add-on has a 6% attach rate — well below the 20% you expected. Before changing the price or features, what are the three most likely causes, and how would you determine which one is the problem?</h4>
          <p>The three most likely causes: <strong>(1) Visibility</strong> — the add-on isn't surfaced at the right moment in checkout or in the subscriber's account management experience; <strong>(2) Value framing</strong> — the description explains what the add-on is, but not what it does for the subscriber's business in concrete terms; <strong>(3) Price-to-value mismatch</strong> — the price isn't anchored against a clear alternative cost, so subscribers can't evaluate whether it's worth it. To diagnose: first check where and how the add-on is presented and measure the gap between subscribers who see it and those who purchase. A 6% attach rate with low discovery is a placement problem. A 6% attach rate with high visibility and a clear description is more likely a price or value-framing issue.</p>
        </div>

      </div>
    </div>
    
 <!-- Continue your journey -->
    <div class="rc-next-steps">
      <h3>🧭 Continue your journey</h3>
      <div class="rc-next-grid">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-review" class="rc-next-card">
          <div class="rc-next-card-tag">Up next</div>
          <div class="rc-next-card-icon">🏁</div>
          <h4>Review &amp; Resources</h4>
          <p>You've completed all six Micro-Paths. Head to the Review &amp; Resources page to test your knowledge and access every resource from across the full Pricing &amp; Plans 101 series in one place.</p>
          <div class="rc-next-card-arrow">Go to Review →</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-next-card">
          <div class="rc-next-card-tag">Series hub</div>
          <div class="rc-next-card-icon">🎯</div>
          <h4>P&amp;P 101 Overview</h4>
          <p>Return to the full series overview to revisit any Micro-Path or share the program with a colleague who's new to Recurly's pricing and packaging tools.</p>
          <div class="rc-next-card-arrow">View all paths →</div>
        </a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-next-card">
          <div class="rc-next-card-tag">Live session</div>
          <div class="rc-next-card-icon">🎙️</div>
          <h4>Global Office Hours</h4>
          <p>Bring any outstanding questions from the full Pricing &amp; Plans 101 series to our CSMs live. Sessions run weekly — no question is too specific.</p>
          <div class="rc-next-card-arrow">Register →</div>
        </a>
      </div>
    </div>
    <br>
    <br>




    <!-- Full resource library -->
    <div class="rc-lp-section" id="all-resources">
      <h2>📚 Full resource library</h2>
      <p>Every resource referenced across all six Micro-Paths, organized by topic. Bookmark this page as your consolidated Pricing &amp; Plans 101 reference.</p>

      <div class="rc-resource-library">

        <div>
          <div class="rc-resource-group-label">Plans</div>
          <div class="rc-resource-group-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Plans</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/plan-intervals" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Plan Intervals</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/hosted-payment-pages" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Hosted Payment Pages</a>
          </div>
        </div>

        <div>
          <div class="rc-resource-group-label">Add-Ons</div>
          <div class="rc-resource-group-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/add-ons" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Add-Ons</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/item-catalog" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Item Catalog</a>
          </div>
        </div>

        <div>
          <div class="rc-resource-group-label">Currency</div>
          <div class="rc-resource-group-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/multi-currency" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Multi-Currency</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/gateways" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Payment Gateways</a>
          </div>
        </div>

        <div>
          <div class="rc-resource-group-label">Pricing Models</div>
          <div class="rc-resource-group-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/billing-models" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Pricing Models</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/-tiered-stairstep-and-volume-pricing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Tiered, Stairstep &amp; Volume Pricing</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/ramp-plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Ramp Plans</a>
            <a href="https://recurly.com/blog/subscription-pricing-strategy-playbook/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📝 Subscription Pricing Strategy Playbook</a>
          </div>
        </div>

        <div>
          <div class="rc-resource-group-label">Trials</div>
          <div class="rc-resource-group-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/trials" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Trials</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/coupons" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Coupons</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Dunning</a>
            <a href="https://recurly.com/blog/free-trial-conversion-rate/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📝 Recurly Blog: Free Trial Conversion</a>
          </div>
        </div>

        <div>
          <div class="rc-resource-group-label">Analytics</div>
          <div class="rc-resource-group-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/analytics-overview" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Analytics Overview</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/mrr" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: MRR</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/churn" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Churn</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/subscription-reports" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Subscription Reports</a>
            <a href="https://recurly.com/resources/subscription-benchmarks/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📝 Recurly Subscription Benchmarks</a>
          </div>
        </div>

        <div>
          <div class="rc-resource-group-label">Live &amp; Support</div>
          <div class="rc-resource-group-links">
            <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Global Office Hours — weekly live sessions with Recurly CSMs</a>
            <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Support</a>
          </div>
        </div>

      </div>
    </div>

    <!-- OH CTA -->
    <div class="rc-oh-cta">
      <h4>🗓️ Bring your Pricing &amp; Plans questions to Office Hours</h4>
      <p>You've covered the full foundation. The next step is applying it to your specific configuration — and our Customer Success team runs weekly <strong>Global Office Hours</strong> sessions where you can do exactly that. Bring plan architecture questions, pricing model tradeoffs, trial strategy decisions, or analytics interpretation challenges. No question is too specific.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <!-- Footer -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Pricing &amp; Plans 101:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-footer-link">Pricing &amp; Plans 101 Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-footer-link">Plans</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-footer-link">Add-Ons</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-footer-link">Currency</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-footer-link">Pricing Models</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-footer-link">Trials</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-footer-link">Analytics</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-review" class="rc-footer-link">Review &amp; Resources</a>
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
