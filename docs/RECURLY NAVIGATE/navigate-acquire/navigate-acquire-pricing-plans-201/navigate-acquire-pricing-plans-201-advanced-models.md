---
title: 'Advanced Pricing Models: Overview'
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
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:hover,
.rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

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
.rc-hero { background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)), url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center; background-color: var(--offblack); background-size: cover; color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0; }
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,215,6,0.20); border: 1px solid rgba(255,215,6,0.45); color: #FFD706; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: var(--lightgray); line-height: 1.6; }
.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); line-height: 1.3; }

/* Nav */
details.rc-sticky-nav-wrap { position: static; background-color: var(--yellow); box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px 0; border-radius: 12px; border: 1px solid rgba(0,0,0,0.08); overflow: hidden; }
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
.rc-sticky-link:hover .rc-step-badge { background: var(--yellow) !important; color: var(--offblack) !important; }
.rc-sticky-link-active { background: rgba(0,0,0,0.12); font-weight: 800; }
.rc-sticky-link-active:hover { background: var(--offblack); color: var(--yellow) !important; }

/* Content sections */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* Stat strip */
.rc-stat-strip { display: grid; grid-template-columns: repeat(3, 1fr); background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 0 0 32px; }
.rc-stat-tile { padding: 24px 20px; text-align: center; }
.rc-stat-tile + .rc-stat-tile { border-left: 1px solid var(--lightgray); }
.rc-stat-tile-num { font-size: 2rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 4px; }
.rc-stat-tile-label { font-size: .7rem; font-weight: 700; letter-spacing: .8px; text-transform: uppercase; color: var(--gray); margin-bottom: 10px; }
.rc-stat-tile-context { font-size: .8rem; color: var(--darkgray); line-height: 1.5; padding-top: 10px; border-top: 1px solid var(--brightgray); }

/* Card grid */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: var(--yellow); box-shadow: 0 4px 16px rgba(255,215,6,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }
.rc-feature-tag { display: inline-block; margin-top: 4px; padding: 3px 10px; border-radius: 20px; font-size: .7rem; font-weight: 700; letter-spacing: .5px; background: var(--offblack); color: var(--yellow); width: fit-content; }

/* Three-col */
.rc-three-col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 0 0 32px; }
.rc-col-block { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; }
.rc-col-block-num { font-size: 1.6rem; font-weight: 800; color: var(--yellow); margin-bottom: 8px; line-height: 1; }
.rc-col-block h4 { font-size: .95rem; font-weight: 800; color: var(--offblack); margin: 0 0 8px; }
.rc-col-block p { font-size: .85rem; color: var(--gray); line-height: 1.55; margin: 0; }

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

/* Accent card */
.rc-accent-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 20px 0; }
.rc-accent-card.rc-accent-orange { border-left: 4px solid var(--orange); }
.rc-accent-card.rc-accent-yellow { border-left: 4px solid var(--yellow); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 12px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-accent-card ul { font-size: .9rem; color: var(--gray); line-height: 1.75; padding-left: 20px; margin: 0; }
.rc-accent-card ul li { margin-bottom: 4px; }
.rc-accent-card ul li strong { color: var(--darkgray); }

/* Comparison table */
.rc-compare-table { width: 100%; border-collapse: collapse; margin: 0 0 32px; font-size: .88rem; border-radius: 12px; overflow: hidden; border: 1px solid var(--lightgray); }
.rc-compare-table thead tr { background: var(--offblack); }
.rc-compare-table thead th { padding: 14px 18px; text-align: left; font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: var(--yellow); }
.rc-compare-table thead th:first-child { width: 22%; }
.rc-compare-table tbody tr { border-bottom: 1px solid var(--brightgray); }
.rc-compare-table tbody tr:last-child { border-bottom: none; }
.rc-compare-table tbody tr:nth-child(even) { background: var(--offwhite); }
.rc-compare-table tbody tr:nth-child(odd) { background: #fff; }
.rc-compare-table tbody td { padding: 12px 18px; color: var(--darkgray); line-height: 1.5; vertical-align: top; }
.rc-compare-table tbody td:first-child { font-weight: 700; color: var(--offblack); }

/* Path nav */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-guide a.rc-btn-prev { background: transparent; color: var(--offblack) !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--lightgray); transition: all .2s; }
.rc-guide a.rc-btn-prev { border-bottom: 2px solid var(--lightgray) !important; }
.rc-guide a.rc-btn-prev:hover { border: 2px solid var(--offblack) !important; border-bottom: 2px solid var(--offblack) !important; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); }
.rc-guide a.rc-btn-path { border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }
.rc-btn-start { background: var(--brightgray); color: var(--gray); padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid var(--lightgray); cursor: default; }

/* Resources */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--yellow); border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--yellow) !important; }

/* Footer */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 32px; margin-top: 32px; text-align: center; }
.rc-footer-section { margin-bottom: 14px; display: flex; flex-wrap: wrap; gap: 6px 20px; justify-content: center; align-items: center; }
.rc-footer-section-label { font-size: .72rem; font-weight: 700; text-transform: uppercase; letter-spacing: .6px; color: var(--gray); opacity: 0.65; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 8px 24px; justify-content: center; padding-top: 16px; border-top: 1px solid var(--brightgray); margin-top: 8px; }
.rc-footer-link { color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s; display: inline-flex; align-items: center; gap: 5px; }
.rc-footer-link:hover { color: var(--offblack); }
.rc-footer-link img { width: 13px; height: 13px; object-fit: contain; opacity: 0.55; }

/* Responsive */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-card-grid, .rc-three-col { grid-template-columns: 1fr; }
  .rc-stat-strip { grid-template-columns: 1fr; }
  .rc-compare-table { font-size: .8rem; }
  .rc-compare-table thead th, .rc-compare-table tbody td { padding: 10px 12px; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-back-link">← Back to Path Start</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Announcement bar (hidden) -->
    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>Upcoming:</strong> Join our CSMs for a live P&P strategy session.
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- Hero -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Pricing &amp; Plans 201
      </div>
      <div class="rc-lp-hero-title"><h1>Advanced pricing models — Overview</h1></div>
      <p>Go beyond flat-rate billing with Ramp, Hybrid, and Prepaid models — three architectures that lower deal-close barriers, capture expansion revenue, and improve cash flow.</p>
      
    </div>

    <!-- Nav -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Overview
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models-configure" class="rc-sticky-link">
              <span class="rc-step-badge">2</span> Configure
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models-strategy" class="rc-sticky-link">
              <span class="rc-step-badge">3</span> Strategy &amp; Best Practices
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-sticky-link">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- Section 1: What Are Advanced Pricing Models -->
    <div class="rc-lp-section">
      <h2>📐 What Are Advanced Pricing Models?</h2>
      <p>Most subscription businesses start with flat-rate pricing — one price, billed on a recurring schedule. It's simple to configure, easy to communicate, and works well when your customer base is relatively homogenous. But as your product matures and your customer segments diverge, flat-rate pricing starts to constrain you. Some customers find the full-price commitment too high to sign up. Others grow far beyond what their plan price captures. Some want to prepay at a discount rather than commit to monthly charges.</p>
      <p>Advanced pricing models are Recurly's tools for handling these situations without creating plan sprawl or requiring custom billing logic. Three stand out as the highest-leverage models to master after flat-rate: <strong>Ramp Pricing</strong>, which schedules automatic price changes over a subscription term; <strong>Hybrid Pricing</strong>, which combines a fixed base charge with variable usage billing in a single subscription; and <strong>Prepaid Account Balance</strong>, which lets customers pay upfront and draw against a credit balance for future purchases.</p>
      <p>Each model solves a specific problem in your acquisition or retention motion. Choosing the right one starts with understanding what that problem actually is.</p>
    </div>

    <!-- Section 2: The Business Case -->
    <div class="rc-lp-section">
      <h2>💡 The Business Problem Each Model Solves</h2>

      <div class="rc-stat-strip">
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">12</div>
          <div class="rc-stat-tile-label">Ramp intervals per plan</div>
          <div class="rc-stat-tile-context">A single Recurly plan can hold up to 12 scheduled price changes — enough to model multi-year enterprise contracts, loyalty escalations, or graduated onboarding discounts without creating separate plans for each stage.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">$0</div>
          <div class="rc-stat-tile-label">Intro period entry cost</div>
          <div class="rc-stat-tile-context">A ramp plan can open with a $0 first period — functionally a free trial that transitions to full price on schedule, without requiring a separate trial plan or manual upgrade. The price change happens automatically at the configured interval.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">100%</div>
          <div class="rc-stat-tile-label">Prepaid revenue collected upfront</div>
          <div class="rc-stat-tile-context">Prepaid Account Balance collects the full credit amount at purchase, before any services are consumed. For annual deals, this eliminates the dunning risk of monthly renewals and improves cash flow for your Finance team.</div>
        </div>
      </div>

      <div class="rc-three-col">
        <div class="rc-col-block">
          <div class="rc-col-block-num">🪜</div>
          <h4>Ramp Pricing</h4>
          <p><strong>Problem it solves:</strong> Sticker shock at the full contract price prevents deals from closing, especially with new customers who haven't yet experienced the product's value. Ramp pricing lets you start low and escalate on a schedule — making the first period cost-effective while capturing full value once the customer is invested.</p>
        </div>
        <div class="rc-col-block">
          <div class="rc-col-block-num">🔀</div>
          <h4>Hybrid Pricing</h4>
          <p><strong>Problem it solves:</strong> Flat-rate pricing leaves expansion revenue on the table when power users consume far more than casual ones. Hybrid pricing captures that upside automatically — a base subscription covers platform access, and usage add-ons bill for the variable components that grow with customer activity.</p>
        </div>
        <div class="rc-col-block">
          <div class="rc-col-block-num">💰</div>
          <h4>Prepaid Account Balance</h4>
          <p><strong>Problem it solves:</strong> Monthly billing creates recurring collection friction and invoice anxiety for customers managing tight budgets. Prepaid balance lets customers buy credits upfront at a volume discount — they pay once, then draw against the balance for purchases. You collect cash immediately; they get predictability.</p>
        </div>
      </div>
    </div>

    <!-- Section 3: Comparison -->
    <div class="rc-lp-section">
      <h2>⚖️ Model Comparison at a Glance</h2>
      <p>All three models are available in Recurly, but they serve fundamentally different purposes and suit different segments. Use this to orient your choice before diving into configuration.</p>

      <table class="rc-compare-table">
        <thead>
          <tr>
            <th>Model</th>
            <th>Best for</th>
            <th>Revenue timing</th>
            <th>Customer experience</th>
            <th>Key constraint</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Ramp Pricing</td>
            <td>Enterprise deals, new customer acquisition, loyalty programs</td>
            <td>Varies by period; escalates on schedule</td>
            <td>Price increases are transparent and agreed upfront — no surprise renewals</td>
            <td>Requires "Only Bill What Changed" feature enabled; may need plan upgrade</td>
          </tr>
          <tr>
            <td>Hybrid Pricing</td>
            <td>Products with both platform access and variable consumption</td>
            <td>Predictable base + variable overage at cycle end</td>
            <td>Customers understand the base charge; variable portion requires usage transparency</td>
            <td>Usage component is API-logged — same integration requirement as usage billing</td>
          </tr>
          <tr>
            <td>Prepaid Balance</td>
            <td>Annual contracts, high-volume platforms, credit bundle sales</td>
            <td>100% upfront at purchase, drawn down over time</td>
            <td>Customers see a balance and track consumption — low ongoing billing friction</td>
            <td>ACH and manual payments don't fund balance until transaction is confirmed</td>
          </tr>
        </tbody>
      </table>
    </div>

    <!-- Section 4: When to Use Which -->
    <div class="rc-lp-section">
      <h2>🗺️ Choosing the Right Model for Your Situation</h2>
      <p>These models aren't mutually exclusive — you can layer them. But starting with the right primary model for your use case matters. Here's a framework for the most common scenarios.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🤝</div>
          <h4>Closing enterprise or annual deals</h4>
          <p>Lead with <strong>Ramp Pricing</strong>. The most common blocker in enterprise deals is year-one cost — especially for customers replacing an existing vendor or investing in an unproven category. A ramp structure that starts lower and escalates to full rate in year two or three addresses the CFO's objection without permanently discounting your product.</p>
          <span class="rc-feature-tag">Use: Ramp Pricing</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">📈</div>
          <h4>Capturing growth from active users</h4>
          <p>Lead with <strong>Hybrid Pricing</strong>. If your most active customers generate significantly more value from your product than casual ones — API calls, transactions processed, seats used — a hybrid model ensures your revenue scales with their usage. The base subscription locks in predictable income; add-ons capture the expansion automatically.</p>
          <span class="rc-feature-tag">Use: Hybrid Pricing</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">💳</div>
          <h4>Selling credit bundles or volume discounts</h4>
          <p>Lead with <strong>Prepaid Account Balance</strong>. If customers want to commit to a volume of usage at a discount — and you want that revenue in the bank immediately — prepaid balance is the mechanism. Common patterns: annual credit packs for usage-based products, platform access bundles, or enterprise commitment deals where procurement prefers a single annual purchase order.</p>
          <span class="rc-feature-tag">Use: Prepaid Balance</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🔄</div>
          <h4>Reducing monthly collection friction</h4>
          <p>Combine <strong>Prepaid Balance + Ramp</strong>. Customers who find monthly billing administratively burdensome — small teams managing tight budgets, or enterprise accounts where every invoice requires PO approval — benefit from prepaid balance. Pair it with a ramp structure for annual contract renewals to maintain predictable pricing expectations over the contract term.</p>
          <span class="rc-feature-tag">Use: Both</span>
        </div>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon">⚠️</div>
        <div class="rc-callout-body">
          <strong>Ramp Pricing requires feature enablement — check before configuring</strong>
          <p>Ramp pricing requires the "Only Bill What Changed" feature to be active on your Recurly account. Accounts created before May 2018 also need "Credit Invoices" enabled. Additionally, ramp pricing may not be available on Starter or Pro plan tiers — contact Recurly Sales or Support to confirm your account eligibility before building ramp plans.</p>
        </div>
      </div>
    </div>

    <!-- Path navigation -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-btn-prev">← Usage Billing</a>
      <span class="rc-lp-nav-indicator">1 of 3</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models-configure" class="rc-btn-path">Next: Configure →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/docs/billing-models" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Pricing Models</a>
        <a href="https://docs.recurly.com/docs/ramp-pricing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Ramp Pricing</a>
        <a href="https://docs.recurly.com/docs/hybrid-pricing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Hybrid Pricing</a>
        <a href="https://docs.recurly.com/docs/prepaid-account-balance" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Prepaid Account Balance</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Join Global Office Hours</a>
      </div>
    </div>

    <!-- Footer -->
    <div class="rc-footer-nav">
      <div class="rc-footer-section">
        <span class="rc-footer-section-label">Advanced Models:</span>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models" class="rc-footer-link">Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models-configure" class="rc-footer-link">Configure</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models-strategy" class="rc-footer-link">Strategy &amp; Best Practices</a>
      </div>
      <div class="rc-footer-section">
        <span class="rc-footer-section-label">P&amp;P 201:</span>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-footer-link">P&amp;P 201 Hub</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-segmentation" class="rc-footer-link">Segmentation</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-footer-link">Account Hierarchy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-footer-link">Usage Billing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models" class="rc-footer-link">Advanced Models</a>
      </div>
      <div class="rc-footer-utility">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Navigate Home
        </a>
        <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
      </div>
    </div>

  </div><!-- /.rc-content-wrap -->
</div><!-- /.rc-guide -->
`}</HTMLBlock>

<br />
