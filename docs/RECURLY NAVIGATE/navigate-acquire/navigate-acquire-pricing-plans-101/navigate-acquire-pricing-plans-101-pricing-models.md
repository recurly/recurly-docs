---
title: 'Pricing Models: Overview'
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
.rc-hero { background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)), url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center; background-color: #0D0D0B; background-size: cover; color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0; }
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,215,6,0.20); border: 1px solid rgba(255,215,6,0.45); color: #FFD706; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: #FFFDF2; margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: #CCC9B8; line-height: 1.6; }
.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: #FFD706; line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: #CCC9B8; line-height: 1.3; }

/* Nav — non-sticky, open by default, Micro-Path variant */
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
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-sticky-link:hover .rc-step-badge { background: var(--yellow); color: var(--offblack); }
.rc-sticky-link-active { background: rgba(0,0,0,0.12); font-weight: 800; }
.rc-sticky-link-active:hover { background: var(--offblack); color: var(--yellow) !important; }

/* Sections */
.rc-lp-section { margin-bottom: 52px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }
.rc-lp-section p:last-child { margin-bottom: 0; }

/* Callouts */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout + .rc-callout { margin-top: 12px; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-body a { color: var(--orange) !important; font-weight: 600; }
.rc-guide .rc-callout-body a:hover { text-decoration: underline !important; }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body > strong { color: var(--offblack); }
.rc-callout-warning { background: rgba(255,215,6,0.12); border-left: 4px solid var(--yellow); }
.rc-callout-warning .rc-callout-body > strong { color: var(--darkgray); }
.rc-callout-caution { background: rgba(255,130,0,0.08); border-left: 4px solid var(--orange); }
.rc-callout-caution .rc-callout-body > strong { color: var(--darkgray); }

/* Card grid — 2-col */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: var(--yellow); box-shadow: 0 4px 16px rgba(255,215,6,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }
.rc-feature-tag { display: inline-block; margin-top: 4px; padding: 3px 10px; border-radius: 20px; font-size: .7rem; font-weight: 700; letter-spacing: .5px; background: var(--offblack); color: var(--yellow); width: fit-content; }

/* Stat strip */
.rc-stat-strip { display: grid; grid-template-columns: repeat(3, 1fr); background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 0 0 32px; }
.rc-stat-tile { padding: 24px 20px; text-align: center; }
.rc-stat-tile + .rc-stat-tile { border-left: 1px solid var(--lightgray); }
.rc-stat-tile-num { font-size: 2rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 4px; }
.rc-stat-tile-label { font-size: .7rem; font-weight: 700; letter-spacing: .8px; text-transform: uppercase; color: var(--gray); margin-bottom: 10px; }
.rc-stat-tile-context { font-size: .8rem; color: var(--darkgray); line-height: 1.5; padding-top: 10px; border-top: 1px solid var(--brightgray); }

/* Compare grid */
.rc-compare-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-compare-card { border-radius: 12px; padding: 24px; border: 1px solid var(--lightgray); background: var(--offwhite); }
.rc-compare-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 16px; }
.rc-compare-card ul { list-style: none; padding: 0; margin: 0; display: flex; flex-direction: column; gap: 10px; }
.rc-compare-card ul li { font-size: .88rem; color: var(--darkgray); line-height: 1.5; padding-left: 20px; position: relative; }
.rc-compare-card ul li::before { content: '→'; position: absolute; left: 0; color: var(--yellow); font-weight: 800; font-size: .8rem; }
.rc-compare-label { display: inline-block; font-size: .68rem; font-weight: 800; letter-spacing: .8px; text-transform: uppercase; padding: 3px 10px; border-radius: 20px; margin-bottom: 14px; }
.rc-compare-label-fixed { background: rgba(255,215,6,0.15); color: #7a6500; }
.rc-compare-label-ramp { background: rgba(13,13,11,0.08); color: var(--offblack); }

/* Path nav */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-btn-start { background: var(--brightgray); color: var(--gray); padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid var(--lightgray); cursor: default; display: inline-flex; align-items: center; }
.rc-guide a.rc-btn-prev { background: transparent; color: var(--offblack) !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--lightgray); transition: all .2s; }
.rc-guide a.rc-btn-prev { border-bottom: 2px solid var(--lightgray) !important; }
.rc-guide a.rc-btn-prev:hover { border: 2px solid var(--offblack) !important; border-bottom: 2px solid var(--offblack) !important; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Resources */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--yellow); border-radius: 10px; padding: 20px 24px; margin: 48px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FFD706 !important; }

/* Footer — grouped section structure */
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
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-card-grid { grid-template-columns: 1fr; }
  .rc-compare-grid { grid-template-columns: 1fr; }
  .rc-stat-strip { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-back-link">← Back to Path Start</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Announcement bar (hidden — add rc-active to show) -->
    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>Upcoming:</strong> Join our CSMs for a live Pricing &amp; Packaging Q&amp;A.
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- Hero -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · P&amp;P 101
      </div>
      <div class="rc-lp-hero-title"><h1>Pricing Models</h1></div>
      <p>The pricing model you choose determines how Recurly calculates what a subscriber owes each billing period — and how they perceive the value of what they're paying for. Here's what each model does and when each one belongs in your setup.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">5</div><div class="rc-hero-stat-label">pricing models available across plans and add-ons</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">Fixed</div><div class="rc-hero-stat-label">the right model for most base plans — simple, predictable, subscriber-friendly</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">3</div><div class="rc-hero-stat-label">add-on-only models — Tiered, Volume, and Stairstep — for quantity-based billing</div></div>
      </div>
    </div>

    <!-- Navigation Menu — non-sticky, open, Micro-Path, page 1 active -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <!-- Active page: map pin replaces badge entirely -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Pricing Models: Overview
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models-configure" class="rc-sticky-link"><span class="rc-step-badge">2</span> Pricing Models: Configure</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models-strategy" class="rc-sticky-link"><span class="rc-step-badge">3</span> Pricing Models: Strategy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- What pricing models do -->
    <div class="rc-lp-section" id="what-pricing-models-do">
      <h2>🧱 What pricing models do in Recurly</h2>
      <p>A pricing model is the rule Recurly uses to calculate the charge on a subscription or add-on for each billing period. It determines whether a subscriber pays the same flat amount every cycle, whether their price changes over time, or whether the charge scales with how many seats or units they're using.</p>
      <p>Pricing models live in two places, and the placement matters. <strong>Fixed and Ramp are configured at the plan level</strong> — they define how the base subscription charge works. <strong>Tiered, Volume, and Stairstep are add-on-only models</strong> — they're used when you need quantity-based billing, and they layer on top of whatever the base plan charges. Fixed is available on both.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon">💵</div>
          <h4>Fixed</h4>
          <p>A flat charge per billing period, regardless of usage or quantity. Subscribers always know exactly what they'll pay. The most common and most transparent model — available on both plans and add-ons.</p>
          <span class="rc-feature-tag">Plan + Add-on</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">📈</div>
          <h4>Ramp</h4>
          <p>The base plan price changes at defined billing cycle milestones — typically starting lower and stepping up to the full price. Used for introductory periods and step-up commitments. Plan-level only.</p>
          <span class="rc-feature-tag">Plan only</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🪜</div>
          <h4>Tiered</h4>
          <p>Per-unit price changes as quantity moves through defined bands. Each unit is billed at the rate for its own tier. Creates volume incentives while preserving per-unit transparency. Add-on only.</p>
          <span class="rc-feature-tag">Add-on only</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">📦</div>
          <h4>Volume &amp; Stairstep</h4>
          <p>Both apply a single rate based on the quantity band the total falls into. Volume charges per-unit at that band's rate; Stairstep charges a flat fee for the whole band. Both are add-on only.</p>
          <span class="rc-feature-tag">Add-on only</span>
        </div>
      </div>
    </div>

    <!-- Fixed and Ramp -->
    <div class="rc-lp-section" id="fixed-and-ramp">
      <h2>⚖️ Fixed and Ramp — the plan-level models</h2>
      <p>Most subscriptions use Fixed pricing and never need anything else. Ramp pricing solves a specific problem: the gap between what a subscriber is willing to commit to at signup and the full price your product is worth once they've experienced value. If you don't have that gap, Fixed is the right choice.</p>

      <div class="rc-compare-grid">
        <div class="rc-compare-card">
          <div class="rc-compare-label rc-compare-label-fixed">Fixed</div>
          <h4>💵 Same charge every period</h4>
          <ul>
            <li>Identical charge every billing cycle — no surprises for subscribers</li>
            <li>Easiest to communicate at checkout ("$49/month, always")</li>
            <li>Easiest for subscribers to budget for and reconcile on invoices</li>
            <li>Available on both plans and Fixed-type add-ons</li>
            <li>The right default for 80%+ of base subscription pricing</li>
          </ul>
        </div>
        <div class="rc-compare-card">
          <div class="rc-compare-label rc-compare-label-ramp">Ramp</div>
          <h4>📈 Price changes at defined milestones</h4>
          <ul>
            <li>Price steps up (or down) at pre-defined billing cycle intervals</li>
            <li>Supports up to 12 pricing intervals per plan</li>
            <li>Solves the commitment gap: lower entry price, full price after proven value</li>
            <li>Used for introductory periods, loyalty pricing, and multi-year step-ups</li>
            <li>Plan-level only — cannot be applied to add-ons</li>
          </ul>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>The two scenarios where Ramp earns its complexity</strong>
          <p>Ramp pricing fits well in two situations: <strong>introductory pricing</strong>, where a lower rate in the first 1–3 billing cycles steps up to full price after the subscriber has experienced the product; and <strong>step-up commitments</strong>, like a multi-year contract where the annual price increases to reflect growing product value. Outside those scenarios, Fixed is simpler, clearer, and almost always the better choice.</p>
        </div>
      </div>
    </div>

    <!-- Tiered, Volume, Stairstep -->
    <div class="rc-lp-section" id="quantity-models">
      <h2>📊 Tiered, Volume, and Stairstep — quantity-based add-on models</h2>
      <p>These three models all apply to add-ons where the charge varies by quantity. They're frequently confused because they all use quantity bands — but <strong>how they calculate the charge from those bands is meaningfully different</strong>. The distinction matters most when you're deciding what incentive structure your pricing should create for subscribers.</p>
      <p>The clearest way to see the difference is with the same example across all three. Pricing bands: <strong>1–10 units at $10/unit, 11–20 units at $8/unit, 21–30 units at $6/unit</strong>. A subscriber with 25 units:</p>

      <div class="rc-stat-strip">
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">$210</div>
          <div class="rc-stat-tile-label">Tiered — 25 units</div>
          <div class="rc-stat-tile-context">(10 × $10) + (10 × $8) + (5 × $6) = $210. Each unit is billed at the rate for its own tier — the most granular, per-unit-fair model.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">$150</div>
          <div class="rc-stat-tile-label">Volume — 25 units</div>
          <div class="rc-stat-tile-context">All 25 units at $6 (the rate for the band where 25 lands). Every unit gets the same rate — the one that matches the total quantity.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">$120</div>
          <div class="rc-stat-tile-label">Stairstep — 25 units</div>
          <div class="rc-stat-tile-context">Flat fee for the 21–30 band, regardless of exact quantity. No per-unit math at all — just one band price for that range.</div>
        </div>
      </div>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🪜</div>
          <h4>Tiered — per-unit fairness at volume</h4>
          <p>Each unit is charged at its tier's rate. Subscribers who cross a tier boundary pay less per unit for the additional units — but the units in cheaper tiers stay at their original rate. Best for seat-based models where per-unit billing feels fair and the invoice breakdown is transparent.</p>
          <span class="rc-feature-tag">Per-unit by tier</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🎚️</div>
          <h4>Volume — all-or-nothing rate drop</h4>
          <p>All units are charged at the rate for the band the total falls into — including units that would have been cheaper in lower tiers. Crossing a volume threshold creates a meaningful price drop across the entire usage. Best for commodity billing where you want clean, single-rate invoices.</p>
          <span class="rc-feature-tag">Single rate per band</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">📦</div>
          <h4>Stairstep — flat fee per band</h4>
          <p>A single flat fee for a quantity range — not per-unit at all. Moving to the next range bumps the charge to that band's flat fee, regardless of how many units are in the range. Best when you want to sell seats in bundles (1–5, 6–10, 11–25) with simple, predictable band pricing.</p>
          <span class="rc-feature-tag">Flat fee per band</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">📊</div>
          <h4>Usage (metered)</h4>
          <p>Usage is logged via API and billed in arrears based on what the subscriber actually consumed. Not a quantity band model — charges scale with real consumption. Available as a flat amount per unit or a percentage of the base plan price. Covered in depth in the Add-Ons Micro-Path.</p>
          <span class="rc-feature-tag">API-logged consumption</span>
        </div>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon">⚠️</div>
        <div class="rc-callout-body">
          <strong>Pricing model choice is permanent on add-ons — plan before you save</strong>
          <p>Once an add-on is saved with a pricing model (Tiered, Volume, Stairstep, or Fixed), <strong>you cannot change the model</strong> without creating an entirely new add-on. If you later decide Stairstep doesn't serve your pricing structure and want to switch to Tiered, you'll need to build a new add-on, update each affected subscription via API, and retire the original. Agree on the right model for each add-on with your billing operations team before going to production.</p>
        </div>
      </div>
    </div>

    <!-- Path nav -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency-configure" class="rc-btn-prev">← Currency</a>
      <span class="rc-lp-nav-indicator">1 of 3 · Pricing Models</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models-configure" class="rc-btn-path">Next: How to Configure →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/billing-models" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Pricing Models</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/-tiered-stairstep-and-volume-pricing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Tiered, Stairstep &amp; Volume Pricing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/add-ons" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Add-Ons</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Support</a>
      </div>
    </div>

    <!-- Footer — grouped sections -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Micro-Path: Pricing Models:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-footer-link">Pricing Models: Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models-configure" class="rc-footer-link">Pricing Models: Configure</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models-strategy" class="rc-footer-link">Pricing Models: Strategy &amp; Best Practices</a>
        </div>
        <div class="rc-footer-section">
          <span class="rc-footer-label">Pricing &amp; Packaging 101:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-footer-link">P&amp;P 101 Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-footer-link">Plans</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-footer-link">Add-Ons</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-footer-link">Currency</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-footer-link">Trials</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-footer-link">Analytics</a>
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
