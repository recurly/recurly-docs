---
title: 'Pricing Models: Configuration'
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

/* Nav — non-sticky, open, Micro-Path */
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

/* Numbered steps */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 20px 0 0; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0; }
.rc-step-content p + p { margin-top: 8px; }
.rc-step-content strong { color: var(--darkgray); }
.rc-step-content a { color: var(--orange); font-weight: 600; text-decoration: none !important; }
.rc-guide .rc-step-content a:hover { text-decoration: underline !important; }
.rc-step-content code { background: var(--brightgray); color: var(--offblack); padding: 2px 7px; border-radius: 4px; font-size: .82rem; font-family: monospace; }

/* Accent cards */
.rc-accent-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 20px 0; }
.rc-accent-card.rc-accent-orange { border-left: 4px solid var(--orange); }
.rc-accent-card.rc-accent-yellow { border-left: 4px solid var(--yellow); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 12px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-accent-card p:last-child { margin-bottom: 0; }
.rc-accent-card ul { font-size: .9rem; color: var(--gray); line-height: 1.75; padding-left: 20px; margin: 0; }
.rc-accent-card ul li { margin-bottom: 4px; }
.rc-accent-card ul li strong { color: var(--darkgray); }

/* Field reference table */
.rc-field-table { width: 100%; border-collapse: collapse; margin: 20px 0 32px; font-size: .88rem; }
.rc-field-table th { background: var(--offblack); color: var(--yellow); font-size: .72rem; font-weight: 800; letter-spacing: .8px; text-transform: uppercase; padding: 10px 14px; text-align: left; }
.rc-field-table td { padding: 12px 14px; border-bottom: 1px solid var(--brightgray); color: var(--darkgray); vertical-align: top; line-height: 1.5; }
.rc-field-table tr:last-child td { border-bottom: none; }
.rc-field-table tr:nth-child(even) td { background: var(--offwhite); }
.rc-field-table td:first-child { font-weight: 700; color: var(--offblack); white-space: nowrap; }
.rc-field-table td code { background: var(--brightgray); color: var(--offblack); padding: 1px 6px; border-radius: 4px; font-size: .8rem; font-family: monospace; }

/* Video card */
.rc-video-card { border: 1px solid var(--lightgray); border-radius: 14px; overflow: hidden; margin: 0 0 32px; }
.rc-video-header { background: var(--offblack); padding: 16px 22px; display: flex; align-items: center; gap: 10px; }
.rc-video-header h4 { font-size: .88rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: var(--yellow); margin: 0; }
.rc-video-header span { font-size: .78rem; color: var(--lightgray); margin-left: auto; }
.rc-video-placeholder { aspect-ratio: 16/9; background: var(--brightgray); display: flex; align-items: center; justify-content: center; flex-direction: column; gap: 12px; }
.rc-video-placeholder span { font-size: .85rem; color: var(--gray); font-weight: 600; }
.rc-video-caption { padding: 12px 22px; font-size: .83rem; color: var(--gray); background: var(--brightgray); border-top: 1px solid var(--lightgray); line-height: 1.5; }

/* Path nav */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-guide a.rc-btn-prev { background: transparent; color: var(--offblack) !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--lightgray); border-bottom: 2px solid var(--lightgray) !important; transition: all .2s; }
.rc-guide a.rc-btn-prev:hover { border: 2px solid var(--offblack) !important; border-bottom: 2px solid var(--offblack) !important; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Resources */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--yellow); border-radius: 10px; padding: 20px 24px; margin: 48px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FFD706 !important; }

/* Footer — grouped sections */
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
  .rc-field-table { font-size: .8rem; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
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

    <!-- Hero -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Pricing & Plans 101
      </div>
      <div class="rc-lp-hero-title"><h1>Pricing models — How to configure</h1></div>
      <p>A complete walkthrough of configuring Fixed and Ramp pricing on plans, and Tiered, Volume, and Stairstep pricing on add-ons — including the fields that matter most and the decisions you can't undo.</p>
   
    </div>

    <!-- Navigation Menu — page 2 active -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-sticky-link"><span class="rc-step-badge">1</span> Pricing Models: Overview</a>
        <!-- Active page: map pin replaces badge -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models-configure" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Pricing Models: Configure
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models-strategy" class="rc-sticky-link"><span class="rc-step-badge">3</span> Pricing Models: Strategy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- Configuring plan pricing -->
    <div class="rc-lp-section" id="plan-pricing">
      <h2>⚙️ Configuring pricing on plans: Fixed and Ramp</h2>
      <p>Plan pricing is set in the Pricing section of the plan form. Navigate to <strong>Configuration → Plans → New Plan</strong> (or open an existing plan and click <strong>Edit</strong>). The steps below cover both Fixed and Ramp — choose the path that matches your model.</p>

      <!-- Video first — watch the walkthrough, then follow the steps -->
      <div class="rc-video-card">
        <div class="rc-video-header">
          <h4>Trail guide: Configuring Fixed and Ramp pricing on a plan</h4>
          <span>Video coming soon</span>
        </div>
        <div class="rc-video-placeholder">
          <span style="font-size:2rem;">▶</span>
          <span>Walkthrough video will be added here</span>
        </div>
        <div class="rc-video-caption">A screencast walking through setting Fixed pricing on a new plan, then configuring a Ramp plan with three intervals — including the cycle numbering logic and how the final interval behaves.</div>
      </div>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Set up Fixed pricing</h4>
            <p>In the Pricing section, the default model is Fixed. Enter your base price in the <strong>Price</strong> field. If you have multi-currency enabled, add a price for each additional currency — Recurly does not auto-convert, so each currency price must be entered manually.</p>
            <p>That's it for Fixed. The subscriber pays this amount every billing period until the subscription is canceled or the price is updated. If you update the price later, the change only applies to <strong>new subscribers</strong> — existing subscribers keep their original price (versioned terms).</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Switch to Ramp pricing</h4>
            <p>Select <strong>Ramp</strong> as the pricing type. The form will expand to show a pricing intervals table. You'll add one row per interval — each row defines a billing cycle range and the price for that range.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Configure your Ramp intervals</h4>
            <p>Click <strong>Add Interval</strong> to add each stage of your ramp. For each interval, set the <strong>Starting Billing Cycle</strong> (the cycle number when this price takes effect) and the <strong>Price</strong> for that stage. Recurly bills at each interval's price from its starting cycle until the next interval begins.</p>
            <p>The <strong>final interval has no end</strong> — once the last stage begins, that price continues indefinitely. You can add up to 12 intervals. A two-stage introductory ramp (cycles 1–3 at $19/mo, cycle 4+ at $49/mo) only needs two intervals: starting cycle 1 at $19, starting cycle 4 at $49.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Add currency prices for each interval</h4>
            <p>If you have multi-currency enabled, you must add a price for each currency at each ramp interval — not just for the default currency. Expand each interval row to add the additional currency prices. A ramp interval without a currency price won't display to subscribers checking out in that currency.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">5</div>
          <div class="rc-step-content">
            <h4>Save and verify the ramp schedule</h4>
            <p>After saving, review the plan's pricing summary to confirm the interval schedule reads as expected. Create a test subscription in your Recurly sandbox and advance the billing date to confirm the correct price is charged at each stage before activating for production subscribers.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Ramp field reference -->
    <div class="rc-lp-section" id="ramp-reference">
      <h2>📋 Ramp interval field reference</h2>
      <p>These are the fields that control how your ramp schedule works. Getting the starting cycle numbers wrong is the most common configuration mistake — the numbering starts at 1, not 0.</p>

      <table class="rc-field-table">
        <thead>
          <tr>
            <th>Field</th>
            <th>What it does</th>
            <th>What to know</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Starting Billing Cycle</td>
            <td>The billing cycle number when this interval's price takes effect</td>
            <td>Cycle 1 = the first billing period. For a 3-cycle introductory price that steps up on cycle 4, set two intervals: one starting at cycle 1, one starting at cycle 4.</td>
          </tr>
          <tr>
            <td>Price</td>
            <td>The charge per billing period for this interval</td>
            <td>Versioned — if you update this price on the plan, the change only applies to new subscriptions created after the update. Existing subscribers keep the price they were charged at each stage.</td>
          </tr>
          <tr>
            <td>Final interval</td>
            <td>The last interval in the table — has no end cycle</td>
            <td>This price continues indefinitely once it begins. There is no "ramp end" — once a subscriber reaches the final stage, they stay at that price until the subscription is changed or canceled.</td>
          </tr>
          <tr>
            <td>Maximum intervals</td>
            <td>Up to 12 intervals per plan</td>
            <td>Most ramp pricing structures use 2–4 intervals. Beyond that, the complexity is difficult to communicate to subscribers and rarely produces better conversion than a simpler pricing message.</td>
          </tr>
        </tbody>
      </table>
    </div>

    <!-- Configuring add-on pricing models -->
    <div class="rc-lp-section" id="addon-pricing">
      <h2>⚙️ Configuring Tiered, Volume, and Stairstep on add-ons</h2>
      <p>These models are configured when creating a new add-on, either directly on a plan or through the Item Catalog. Navigate to <strong>Configuration → Plans → [your plan] → Add-ons → New Add-on</strong>. The pricing model you choose here cannot be changed after the add-on is saved — choose deliberately.</p>

      <!-- Video first -->
      <div class="rc-video-card">
        <div class="rc-video-header">
          <h4>Trail guide: Configuring quantity-based add-on pricing models</h4>
          <span>Video coming soon</span>
        </div>
        <div class="rc-video-placeholder">
          <span style="font-size:2rem;">▶</span>
          <span>Walkthrough video will be added here</span>
        </div>
        <div class="rc-video-caption">A screencast showing how to configure Tiered, Volume, and Stairstep add-ons side by side — including how quantity band rows are added, the difference in price fields between models, and how to preview the calculated charge at a given quantity.</div>
      </div>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Set Add-on Type to Fixed and select your Pricing Model</h4>
            <p>Set the Add-on Type to <strong>Fixed</strong> (not Usage). In the Pricing Model dropdown, select <strong>Tiered</strong>, <strong>Volume</strong>, or <strong>Stairstep</strong>. The form will expand to show a quantity bands table. The choice you make here cannot be changed after saving.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Define your quantity bands</h4>
            <p>Click <strong>Add Tier</strong> (or Add Band) to add each quantity range. For each band, set the <strong>From</strong> quantity (the minimum of the range, starting at 1 for the first band) and the <strong>To</strong> quantity (the maximum, or leave blank on the final band for unlimited). Bands must be contiguous — there should be no gaps between them.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Set the price for each band</h4>
            <p>For <strong>Tiered and Volume</strong>: enter a per-unit price for each band. The difference between the models is in how the charge is calculated — not in how the bands are entered. For <strong>Stairstep</strong>: enter a flat fee for each band — this is the total charge when a subscriber's quantity falls within that range, regardless of exactly how many units they have.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Add currency prices for each band</h4>
            <p>If multi-currency is enabled, expand each band row to add prices for additional currencies. As with plans, Recurly does not auto-convert — every currency price at every band must be entered manually.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">5</div>
          <div class="rc-step-content">
            <h4>Set quantity behavior and limits</h4>
            <p>Configure whether the add-on is <strong>Optional</strong> or <strong>Required</strong>, and whether subscribers can adjust their own quantity. For optional quantity-based add-ons, you can enable <strong>Editable Quantity</strong> and set minimum and maximum quantity limits — subscribers self-serve within those bounds on their Hosted Account Page.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">6</div>
          <div class="rc-step-content">
            <h4>Save and test the billing calculation</h4>
            <p>After saving, create a test subscription in your Recurly sandbox and add the add-on at different quantities to confirm the calculated charge matches your expectation. For Tiered vs. Volume, confirm you understand the calculation difference — the same quantity will produce different charges on each model, and subscribers or your finance team will notice if the invoice doesn't match expectations.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Add-on band field reference -->
    <div class="rc-lp-section" id="addon-reference">
      <h2>📋 Quantity band field reference</h2>

      <table class="rc-field-table">
        <thead>
          <tr>
            <th>Field</th>
            <th>Applies to</th>
            <th>What to know</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>From (quantity)</td>
            <td>All models</td>
            <td>The minimum quantity for this band. The first band always starts at 1. Must be one more than the previous band's "To" value — no gaps allowed.</td>
          </tr>
          <tr>
            <td>To (quantity)</td>
            <td>All models</td>
            <td>The maximum quantity for this band. Leave blank on the final band to make it unlimited. A subscriber whose quantity exceeds all defined bands will produce a billing error if there is no open-ended final band.</td>
          </tr>
          <tr>
            <td>Per-unit price</td>
            <td>Tiered, Volume</td>
            <td>The price charged per unit within this band. For Tiered, each unit in the band pays this rate. For Volume, all units in the subscription pay this rate if the total quantity lands in this band.</td>
          </tr>
          <tr>
            <td>Flat fee</td>
            <td>Stairstep</td>
            <td>The total charge for any quantity within this band — not a per-unit price. A subscriber with 7 units in a 6–10 band pays the same flat fee as one with 10 units in that band.</td>
          </tr>
          <tr>
            <td>Pricing model</td>
            <td>All models</td>
            <td><strong>Permanent after save.</strong> You cannot change an add-on from Tiered to Volume or any other model without creating a new add-on entirely. This is the most consequential field in the form.</td>
          </tr>
        </tbody>
      </table>
    </div>

    <!-- Warnings -->
    <div class="rc-lp-section" id="warnings">
      <h2>⚠️ What to know before you save</h2>

      <div class="rc-accent-card rc-accent-orange">
        <h4>🔒 Add-on pricing model is permanent</h4>
        <p>Once an add-on is saved with a pricing model, that model is locked. Changing from Tiered to Volume (or any other combination) requires creating a new add-on with the correct model, updating every affected subscription via API to reference the new add-on code, and retiring the original. This is a significant migration — plan your model selection carefully and validate it in your Recurly sandbox before production use.</p>
      </div>

      <div class="rc-accent-card rc-accent-orange">
        <h4>📝 Ramp pricing only activates for new subscriptions</h4>
        <p>If you add or modify Ramp intervals on a plan that already has active subscribers, <strong>those existing subscribers are not affected</strong>. Their billing continues at whatever price they were originally subscribed at. Ramp intervals only take effect for subscriptions created after the plan is saved with those intervals configured. To apply new pricing to existing subscribers, you must update each subscription individually or via API.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>⚠️ A missing final open-ended band will cause billing errors</h4>
        <p>For Tiered, Volume, and Stairstep add-ons, if a subscriber's quantity exceeds all defined bands, Recurly cannot calculate the charge — and the subscription will error at renewal. Always ensure your final quantity band has no "To" limit (leave it blank) so any quantity is covered.</p>
        <ul>
          <li><strong>Before activating for subscribers:</strong> Test at quantities above your highest defined band to confirm the calculation succeeds.</li>
          <li><strong>In production:</strong> If you expand your pricing to higher volumes, update the final band's upper limit (or remove it entirely) before subscribers reach that threshold.</li>
        </ul>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Validate the calculation in sandbox before going live</strong>
          <p>Create a test subscription for each pricing model you configure, add the add-on at quantities that span multiple bands, and verify the invoice total matches your expected calculation. For Volume especially, verify that crossing a band boundary produces the expected all-units price drop — it's easy to confuse with Tiered behavior until you see both on an invoice side by side.</p>
        </div>
      </div>
    </div>

    <!-- Path nav -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-btn-prev">← Overview</a>
      <span class="rc-lp-nav-indicator">2 of 3 · Pricing Models</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models-strategy" class="rc-btn-path">Next: Strategy &amp; Best Practices →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/billing-models" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Pricing Models</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/-tiered-stairstep-and-volume-pricing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Tiered, Stairstep &amp; Volume Pricing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/add-ons" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Add-Ons</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Plans</a>
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
          <span class="rc-footer-label">Pricing &amp; Plans 101</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-footer-link">Pricing & Plans 101: Overview</a>
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
