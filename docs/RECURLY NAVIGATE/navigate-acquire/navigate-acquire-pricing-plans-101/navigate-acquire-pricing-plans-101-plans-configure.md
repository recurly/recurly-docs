---
title: 'Plans: Configuration'
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

    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Pricing & Plans 101
      </div>
      <div class="rc-lp-hero-title"><h1>Plans — How to Configure</h1></div>
      <p>A step-by-step walkthrough of every field that matters when building a plan in Recurly — including the ones that are permanent, the ones that affect existing subscribers, and the ones most people miss.</p>
    </div>

    <!-- Navigation Menu — non-sticky, open, Micro-Path, page 2 active -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-sticky-link"><span class="rc-step-badge">1</span> Plans: Overview</a>
        <!-- Active page: map pin replaces badge -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-configure" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Plans: Configure
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-strategy" class="rc-sticky-link"><span class="rc-step-badge">3</span> Plans: Strategy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- Step-by-step -->
    <div class="rc-lp-section" id="create-plan">
      <h2>⚙️ Creating a plan — step by step</h2>
      <p>Navigate to <strong>Configuration → Plans → New Plan</strong> in your Recurly Admin Console. Work through these fields in order — several of them have permanent or far-reaching consequences you need to understand before you hit Save.</p>

      <!-- Video first — watch the walkthrough, then follow the steps -->
      <div class="rc-video-card">
        <div class="rc-video-header">
          <h4>Trail guide: Creating a plan in Recurly</h4>
          <span>Video coming soon</span>
        </div>
        <div class="rc-video-placeholder">
          <span style="font-size:2rem;">▶</span>
          <span style="font-size:.85rem; color:var(--gray); font-weight:600;">Walkthrough video will be added here</span>
        </div>
        <div class="rc-video-caption">A step-by-step screencast walking through plan creation in the Recurly Admin Console, including key field decisions and common configuration mistakes.</div>
      </div>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Set your Plan Name</h4>
            <p>This is the customer-facing name that appears on your <strong>Hosted Payment Page</strong>, subscriber invoices, and email templates. Make it descriptive and benefit-led — not an internal code. Limit is 255 characters.</p>
            <p>Examples of strong plan names: <strong>"Pro Monthly"</strong>, <strong>"Starter — Billed Annually"</strong>, <strong>"Teams Plan (Up to 10 Seats)"</strong>. These communicate what the subscriber is getting, not just what the tier is called internally.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Set your Plan Code — carefully</h4>
            <p>The plan code is your permanent, API-critical identifier. It is <strong>used in every API call, webhook payload, and integration that references this plan</strong>. Once set, it cannot be changed.</p>
            <p>Use a clean, lowercase alphanumeric convention: <code>pro-monthly-v2</code>, <code>starter-annual</code>, <code>teams-monthly</code>. Avoid spaces, special characters, and internal shorthand that won't make sense in 18 months. The 25-character limit forces brevity — plan for it.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Configure your Billing Period</h4>
            <p>Set how often subscribers are billed: weekly, monthly, every 2 months, quarterly, every 6 months, or annually. This determines your billing cycle length and is the primary driver of the monthly vs. annual LTV difference.</p>
            <p>You can also set a <strong>Total Billing Cycles</strong> limit — leave blank for infinite renewal, or enter a number (e.g., 12 for a one-year fixed term that auto-expires).</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Choose your Pricing Model</h4>
            <p>Select <strong>Fixed</strong> for a flat recurring charge, or <strong>Ramp</strong> for a price that changes over time (introductory pricing or loyalty discounts). Usage-based pricing is configured at the add-on level, not the base plan.</p>
            <p>If you choose Ramp, you'll be prompted to add pricing intervals. You can configure up to 12 ramps. See the Pricing Models path for a full walkthrough.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">5</div>
          <div class="rc-step-content">
            <h4>Set your Price (and Price Segments)</h4>
            <p>Enter the base price for your default currency. If you have multi-currency enabled, you'll add additional currency prices here — each must be set manually (Recurly does not auto-convert).</p>
            <p>Use <strong>Price Segments</strong> to create multiple price points within a single plan for A/B testing or geographic pricing — without creating duplicate plans. This is covered in depth in P&amp;P 201: Pricing Segmentation.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">6</div>
          <div class="rc-step-content">
            <h4>Configure Trial Period (optional)</h4>
            <p>Set a free or discounted trial period in days or months. Choose whether to require billing information at signup or allow a cardless trial. This has significant impact on your first-renewal success rate — see the Trials path for full guidance.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">7</div>
          <div class="rc-step-content">
            <h4>Add a Setup Fee (optional)</h4>
            <p>A one-time charge processed at the time of signup — useful for onboarding, activation, or hardware costs. Setup fees are processed separately from the first recurring charge and are not included in trial periods.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">8</div>
          <div class="rc-step-content">
            <h4>Assign a Dunning Campaign</h4>
            <p>Select the dunning campaign that should apply to subscribers on this plan. This is one of the most important and most overlooked configuration steps. Assigning dunning at the plan level means your payment recovery cadence can be tailored to how that plan bills.</p>
            <p>Monthly plans need faster, tighter dunning windows. Annual plans need longer recovery windows and proactive pre-renewal communications. If you don't assign a campaign here, the site default applies to all plans equally — which is rarely optimal.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">9</div>
          <div class="rc-step-content">
            <h4>Set end-of-term behavior</h4>
            <p>Choose <strong>Auto-renew</strong> (subscription continues until canceled) or <strong>Expire at term end</strong> (subscription ends after the configured number of billing cycles). Auto-renew is the default for most subscription businesses. Fixed-term commitments should use expire + renewal term configuration.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">10</div>
          <div class="rc-step-content">
            <h4>Save and verify</h4>
            <p>Once saved, your plan is live and accessible via its unique Hosted Payment Page at <code>yoursubdomain.recurly.com/subscribe/[plan-code]</code>. Test it before sending traffic. Confirm the plan name, pricing, and trial appear correctly.</p>
          </div>
        </div>
      </div>

      <div class="rc-steps">

    <!-- Field reference -->
    <div class="rc-lp-section" id="field-reference">
      <h2>📋 Critical field reference</h2>
      <p>These are the fields that have the most downstream impact on your billing operations, integrations, and subscriber experience. Know these before you save your first plan.</p>

      <table class="rc-field-table">
        <thead>
          <tr>
            <th>Field</th>
            <th>Permanent?</th>
            <th>Customer-facing?</th>
            <th>What to know</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Plan Name</td>
            <td>No — editable</td>
            <td>Yes — invoices &amp; HPP</td>
            <td>Updating the name applies site-wide. Existing subscribers will see the new name on future invoices.</td>
          </tr>
          <tr>
            <td>Plan Code</td>
            <td><strong>Yes — permanent</strong></td>
            <td>No</td>
            <td>Cannot be changed after creation. Used in all API calls, webhooks, and integrations. Choose deliberately.</td>
          </tr>
          <tr>
            <td>Price / Billing Interval</td>
            <td>No — editable</td>
            <td>Yes — invoices</td>
            <td><strong>Versioned terms</strong> — changes only apply to new subscribers. Existing subscribers keep their original price and interval.</td>
          </tr>
          <tr>
            <td>Setup Fee</td>
            <td>No — editable</td>
            <td>Yes — first invoice</td>
            <td>Versioned — changes apply to new subscribers only. Percentage discounts never apply to setup fees.</td>
          </tr>
          <tr>
            <td>Dunning Campaign</td>
            <td>No — editable</td>
            <td>No</td>
            <td>Applies to all new subscriptions on this plan. Existing subscriptions keep their previously assigned campaign until changed individually.</td>
          </tr>
          <tr>
            <td>Accounting Code</td>
            <td>No — editable</td>
            <td>No — internal only</td>
            <td>Max 25 lowercase alphanumeric characters. Used in invoice exports for internal accounting. Configure based on your tax and compliance requirements.</td>
          </tr>
        </tbody>
      </table>
    </div>

    <!-- Warnings -->
    <div class="rc-lp-section" id="warnings">
      <h2>⚠️ Things that will surprise you if you don't know them</h2>

      <div class="rc-accent-card rc-accent-orange">
        <h4>🔒 Plan codes are permanent</h4>
        <p>Once you save a plan with a given plan code, that code is locked forever. It's referenced in every API call, webhook, integration, and export that involves this plan. If you need to "rename" a plan code, you have to create a new plan and migrate subscribers — which requires an API script (there's no bulk migration tool in the UI).</p>
        <p>Before saving any plan, confirm the code with your engineering team and follow whatever naming convention your codebase expects.</p>
      </div>

      <div class="rc-accent-card rc-accent-orange">
        <h4>📝 Plan name changes are retroactive — price changes are not</h4>
        <p>This is one of the most misunderstood aspects of Recurly plan management. If you update a plan's name, that new name appears on all future invoices for all subscribers on that plan — including existing ones. But if you update a plan's price or billing interval, those changes <strong>only apply to new subscribers</strong>. Existing subscribers retain the terms they signed up under (versioned terms).</p>
        <p>This is intentional design — it protects subscribers from surprise price changes — but it means if you want to change pricing for existing subscribers, you need to do so at the subscription level individually or via API.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>📦 Archiving a plan does NOT cancel active subscriptions</h4>
        <p>Archiving removes a plan from new signups but existing subscriptions continue to renew indefinitely on that plan until explicitly canceled or changed. Archived plans cannot be reactivated — once archived, that plan code is permanently retired.</p>
        <ul>
          <li><strong>Before archiving:</strong> Export all active subscriptions on the plan and decide whether to migrate or let them naturally expire.</li>
          <li><strong>Bulk migration:</strong> No native UI tool exists — you'll need to use the Recurly API's Update Subscription endpoint with the new <code>plan_code</code>. Choose "At Renewal" timing to avoid proration surprises.</li>
        </ul>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Duplicate a plan to save time</strong>
          <p>Need to create a similar plan with minor variations? Use the <strong>"Duplicate"</strong> option on any existing plan — hover over the plan row in your Plans dashboard to find it. All settings copy over. In the duplicate, adjust what's different, update the plan code and name, remove the "-copy" suffix, and save.</p>
        </div>
      </div>
    </div>

    <!-- Path nav -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-btn-prev">← Overview</a>
      <span class="rc-lp-nav-indicator">2 of 3 · Plans</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-strategy" class="rc-btn-path">Next: Strategy &amp; Best Practices →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Plans</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/billing-models" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Pricing Models</a>
        <a href="https://support.recurly.com/hc/en-us/articles/44223937178004" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Bulk Plan Migration Best Practice</a>
        <a href="https://support.recurly.com/hc/en-us/articles/360051667292" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Tax Configurations for Plans</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Support</a>
      </div>
    </div>

    <!-- Footer — grouped sections -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Micro-Path: Plans:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-footer-link">Plans: Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-configure" class="rc-footer-link">Plans: Configure</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-strategy" class="rc-footer-link">Plans: Strategy &amp; Best Practices</a>
        </div>
        <div class="rc-footer-section">
          <span class="rc-footer-label">Pricing &amp; Plans 101</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-footer-link">Pricing & Plans 101: Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-footer-link">Add-Ons</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-footer-link">Currency</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-footer-link">Pricing Models</a>
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
