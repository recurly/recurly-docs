---
title: 'Add-ons: Configuration'
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

/* Nav */
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

/* Video placeholder */
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
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · P&amp;P 101
      </div>
      <div class="rc-lp-hero-title"><h1>Add-Ons — How to Configure</h1></div>
      <p>A complete walkthrough of creating add-ons both directly on a plan and through the Item Catalog — including key field decisions, usage setup, and the warnings most merchants learn the hard way.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">Plan level</div>
          <div class="rc-hero-stat-label">or Item Catalog — two paths to the same outcome</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">Permanent</div>
          <div class="rc-hero-stat-label">add-on codes — cannot be changed after creation</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">API required</div>
          <div class="rc-hero-stat-label">to log usage records for metered add-ons</div>
        </div>
      </div>
    </div>

    <!-- Navigation Menu — page 2 active -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-sticky-link"><span class="rc-step-badge">1</span> Add-Ons: Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons-configure" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Add-Ons: Configure
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons-strategy" class="rc-sticky-link"><span class="rc-step-badge">3</span> Add-Ons: Strategy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- Path A: Plan-level add-on -->
    <div class="rc-lp-section" id="plan-addon">
      <h2>⚙️ Path A — Creating a plan-level add-on</h2>
      <p>Use this path when the add-on is unique to a single plan. Navigate to <strong>Configuration → Plans → [your plan] → Add-ons → New Add-on</strong>.</p>

      <!-- Video placeholder — above steps per skill rule -->
      <div class="rc-video-card">
        <div class="rc-video-header">
          <h4>Trail guide: Creating a plan-level add-on</h4>
          <span>Video coming soon</span>
        </div>
        <div class="rc-video-placeholder">
          <span style="font-size:2rem;">▶</span>
          <span>Walkthrough video will be added here</span>
        </div>
        <div class="rc-video-caption">A screencast showing how to create a fixed and a tiered add-on directly on a plan, including add-on code setup and editable quantity configuration.</div>
      </div>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Set the Add-on Name</h4>
            <p>The customer-facing name that appears on invoices and the Hosted Account Page. Make it descriptive and outcome-led — <strong>"Priority Support"</strong> not <strong>"Support Tier 2"</strong>. Subscribers see this name when deciding whether to add or keep it.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Set the Add-on Code — carefully</h4>
            <p>Like plan codes, add-on codes are <strong>permanent once saved</strong>. They appear in every API call, webhook, and export that references this add-on. Use a clean, lowercase alphanumeric convention: <code>priority-support</code>, <code>extra-seats</code>, <code>storage-50gb</code>.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Choose the Add-on Type</h4>
            <p>Select <strong>Fixed</strong> for a flat recurring charge, or <strong>Usage</strong> for a metered add-on billed in arrears based on logged usage records. If you select Usage, you'll also set the unit name (e.g., "API calls", "messages", "GB") used when logging records.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Choose the Pricing Model (for Fixed type)</h4>
            <p>Select <strong>Fixed</strong>, <strong>Tiered</strong>, <strong>Volume</strong>, or <strong>Stairstep</strong>. For Tiered, Volume, and Stairstep, you'll define the quantity ranges and per-unit or flat prices for each band. These display as a pricing table in the Recurly UI.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">5</div>
          <div class="rc-step-content">
            <h4>Set the Price</h4>
            <p>Enter the price for your default currency. For multi-currency plans, add additional currency prices here — Recurly does not auto-convert. For Tiered/Volume/Stairstep, enter the per-unit or flat rate for each defined quantity band.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">6</div>
          <div class="rc-step-content">
            <h4>Configure Optional vs. Required</h4>
            <p>Set whether the add-on is <strong>optional</strong> (subscriber can self-serve add/remove on their Hosted Account Page) or <strong>required</strong> (cannot be removed — always billed). For optional add-ons, you can also enable <strong>Editable Quantity</strong> to let subscribers adjust their own quantity within limits you define.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">7</div>
          <div class="rc-step-content">
            <h4>Set Accounting Code (optional)</h4>
            <p>Max 20 alphanumeric characters. Used in invoice exports and rev rec integrations. If you're using a rev rec or ERP system, confirm the expected code format with your finance team before saving — changing this later won't retroactively update past invoices.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">8</div>
          <div class="rc-step-content">
            <h4>Save and associate</h4>
            <p>The add-on is now available on this plan. To make it appear on a subscriber's checkout or Hosted Account Page, include the add-on code when creating or updating subscriptions via API, or configure it to display in your Hosted Payment Page settings.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Path B: Item Catalog -->
    <div class="rc-lp-section" id="catalog-addon">
      <h2>⚙️ Path B — Creating an Item Catalog add-on</h2>
      <p>Use this path when the add-on will be sold on multiple plans, needs consistent tax treatment, or you're building a scalable product catalog. Navigate to <strong>Configuration → Item Catalog → New Item</strong>.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Create the Item</h4>
            <p>Set the Item Name, Item Code (permanent — choose carefully), and External SKU (optional, for ERP/billing system reference). The item code is distinct from the add-on code you'll set when associating it with a plan.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Configure Tax and Rev Rec</h4>
            <p>Set the item's <strong>tax code</strong> (used to determine taxability in supported regions) and <strong>revenue recognition settings</strong> if you're integrated with a rev rec system. These settings apply consistently every time this item is used, regardless of which plan it's attached to — this is the primary advantage of the Item Catalog approach.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Associate with a plan</h4>
            <p>Navigate to your plan (<strong>Configuration → Plans → [your plan] → Add-ons → Add Item Catalog Add-on</strong>), select the item, and configure the plan-specific settings: add-on code for this plan, pricing, optional/required, and editable quantity. The same item can have different prices and codes on different plans.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Repeat association for each plan</h4>
            <p>Associate the same catalog item with as many plans as needed. Each association can have different pricing and configuration — the shared item maintains consistent tax and accounting settings while the plan-level association handles the billing specifics.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Usage add-ons -->
    <div class="rc-lp-section" id="usage-addons">
      <h2>📊 Configuring usage-based add-ons</h2>
      <p>Usage add-ons require an additional step beyond the UI: you must log usage records via the Recurly API during each billing period. Recurly aggregates these records and bills in arrears at the end of the period.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Create the add-on with type = Usage</h4>
            <p>Follow Path A above, selecting <strong>Usage</strong> as the add-on type. Set the measured unit name — this is the label that appears on invoices (e.g., "API calls", "messages sent", "GB stored"). Choose your usage pricing model: percentage of base plan price, or unit amount (a fixed rate per unit consumed).</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Log usage records via API</h4>
            <p>During each billing period, your system must call the Recurly API to record usage. Each usage record includes the subscription UUID, add-on code, quantity consumed, and a timestamp. Recurly aggregates all records logged in the billing period and bills the total at period end.</p>
            <p>Endpoint: <code>POST /subscriptions/{uuid}/add_ons/{add_on_code}/usage</code></p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Verify in the Recurly UI</h4>
            <p>Navigate to the subscriber's account and view their subscription to confirm usage records are appearing correctly before the billing period closes. You can view logged usage under the subscription's add-on details.</p>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-caution">
        <div class="rc-callout-icon">🔶</div>
        <div class="rc-callout-body">
          <strong>Usage records cannot be back-dated beyond the billing period</strong>
          <p>If usage records are not logged before the billing period closes, they will not appear on the invoice for that period. Build reliable usage logging into your system before activating usage add-ons for subscribers — a missed billing period means lost revenue with no recovery path.</p>
        </div>
      </div>
    </div>

    <!-- Critical warnings -->
    <div class="rc-lp-section" id="warnings">
      <h2>⚠️ What to know before you save</h2>

      <div class="rc-accent-card rc-accent-orange">
        <h4>🔒 Add-on codes are permanent</h4>
        <p>Once an add-on is saved with a given code, that code is locked. It appears in every API call, webhook, and subscription export that references this add-on. If you need to change an add-on code, you must create a new add-on and migrate existing subscriptions via API.</p>
        <p>Agree on your naming convention with your engineering team before creating any add-ons that will be referenced in your codebase.</p>
      </div>

      <div class="rc-accent-card rc-accent-orange">
        <h4>💰 Changing an add-on price does not update existing subscriptions</h4>
        <p>Like plan pricing, add-on price changes are versioned — they only apply to new subscriptions created after the change. Existing subscribers keep the add-on price they were originally charged. To update pricing for existing subscribers, you must update each subscription individually or via API.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>🗑️ Removing an add-on from a plan does not cancel it on active subscriptions</h4>
        <p>If you remove an add-on from a plan's available add-ons, existing subscriptions that already have that add-on will continue to be billed for it. The add-on must be explicitly removed from each affected subscription.</p>
        <ul>
          <li><strong>Before removing:</strong> Export subscriptions with that add-on and communicate the change to affected subscribers.</li>
          <li><strong>Bulk removal:</strong> Use the Recurly API's Update Subscription endpoint to remove the add-on from each subscription individually.</li>
        </ul>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Test with a trial subscription first</strong>
          <p>Before activating a new add-on for production subscribers, create a test subscription in your Recurly sandbox, add the add-on, and verify it appears correctly on the invoice preview. For usage add-ons, log a few test records and confirm the billing calculation matches your expectation before going live.</p>
        </div>
      </div>
    </div>

    <!-- Path nav -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-btn-prev">← Overview</a>
      <span class="rc-lp-nav-indicator">2 of 3 · Add-Ons</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons-strategy" class="rc-btn-path">Next: Strategy &amp; Best Practices →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/add-ons" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Add-Ons</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/item-catalog" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Item Catalog</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/usage-based-pricing-guide" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Usage-Based Billing Guide</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/-tiered-stairstep-and-volume-pricing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Tiered, Stairstep &amp; Volume Pricing</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Support</a>
      </div>
    </div>

    <!-- Footer -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Micro-Path: Add-Ons:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-footer-link">Add-Ons: Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons-configure" class="rc-footer-link">Add-Ons: Configure</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons-strategy" class="rc-footer-link">Add-Ons: Strategy &amp; Best Practices</a>
        </div>
        <div class="rc-footer-section">
          <span class="rc-footer-label">Pricing &amp; Packaging 101:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-footer-link">P&amp;P 101 Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-footer-link">Plans</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-footer-link">Currency</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-footer-link">Pricing Models</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-footer-link">Trials</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-footer-link">Analytics</a>
        </div>
        <div class="rc-footer-utility">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
            <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Navigate Home
          </a>
          <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
        </div>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
