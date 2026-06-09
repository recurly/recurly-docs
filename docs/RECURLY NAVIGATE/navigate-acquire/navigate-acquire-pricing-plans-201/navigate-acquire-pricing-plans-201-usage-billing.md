---
title: 'Usage Billing: Overview'
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

/* Accent cards */
.rc-accent-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 20px 0; }
.rc-accent-card.rc-accent-orange { border-left: 4px solid var(--orange); }
.rc-accent-card.rc-accent-yellow { border-left: 4px solid var(--yellow); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 12px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-accent-card ul { font-size: .9rem; color: var(--gray); line-height: 1.75; padding-left: 20px; margin: 0; }
.rc-accent-card ul li { margin-bottom: 4px; }
.rc-accent-card ul li strong { color: var(--darkgray); }

/* Three-column structure block */
.rc-three-col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 0 0 32px; }
.rc-col-block { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; }
.rc-col-block-num { font-size: 1.6rem; font-weight: 800; color: var(--yellow); margin-bottom: 8px; line-height: 1; }
.rc-col-block h4 { font-size: .95rem; font-weight: 800; color: var(--offblack); margin: 0 0 8px; }
.rc-col-block p { font-size: .85rem; color: var(--gray); line-height: 1.55; margin: 0; }

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
.rc-btn-complete { background: var(--brightgray); color: var(--offblack) !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--yellow); cursor: default; user-select: none; }

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
  .rc-oh-cta { padding: 24px 20px; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-card-grid, .rc-three-col { grid-template-columns: 1fr; }
  .rc-stat-strip { grid-template-columns: 1fr; }
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
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire
      </div>
      <div class="rc-lp-hero-title"><h1>Usage Billing</h1></div>
      <p>Charge customers based on what they actually consume — and unlock new pathways to acquisition, expansion, and compounding revenue growth.</p>
      
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
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Overview
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing-configure" class="rc-sticky-link">
              <span class="rc-step-badge">2</span> Configure
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing-strategy" class="rc-sticky-link">
              <span class="rc-step-badge">3</span> Strategy &amp; Best Practices
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-sticky-link">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- Section 1: What Is Usage Billing -->
    <div class="rc-lp-section">
      <h2>📊 What Is Usage Billing?</h2>
      <p>Usage billing lets you charge customers based on how much they consume, rather than a fixed amount per billing period. Instead of every customer paying the same price each month, their bill reflects their actual activity — API calls made, gigabytes stored, transactions processed, or any measurable unit your product generates.</p>
      <p>In Recurly, usage billing is implemented through <strong>usage-based add-ons</strong> attached to subscription plans. Each add-on tracks a specific <strong>measured unit</strong> — the thing you're counting — and the usage is logged programmatically via the API throughout the billing period. At cycle end, Recurly tallies up everything logged and generates an invoice for the total.</p>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Billed in arrears by design</strong>
          <p>Usage is always billed at the end of the billing cycle, not upfront. Recurly collects usage records throughout the period and invoices for the total when the cycle closes. This means your customers pay for what they used, not what they might use.</p>
        </div>
      </div>
    </div>

    <!-- Section 2: The Business Case -->
    <div class="rc-lp-section">
      <h2>💡 Why Usage Billing Changes Your Revenue Model</h2>
      <p>Fixed pricing is simple to understand and easy to communicate. But it leaves revenue on the table when power users consume far more than casual ones — and it creates conversion friction for prospects who aren't sure if they'll get their money's worth. Usage billing solves both problems.</p>

      <div class="rc-stat-strip">
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">61%</div>
          <div class="rc-stat-tile-label">SaaS companies with usage pricing</div>
          <div class="rc-stat-tile-context">More than six in ten B2B SaaS companies now include usage-based components in their pricing — making it one of the fastest-growing billing models in software.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">3x</div>
          <div class="rc-stat-tile-label">Higher expansion revenue</div>
          <div class="rc-stat-tile-context">Businesses with usage-based models report roughly three times higher net revenue expansion compared to those on flat-rate plans alone — because billing scales with the customer's growth.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">$0</div>
          <div class="rc-stat-tile-label">Possible entry price with a free tier</div>
          <div class="rc-stat-tile-context">A free usage tier sets your entry price to zero and removes the biggest barrier to sign-up. Customers start, see value, and convert — without any upfront financial commitment required.</div>
        </div>
      </div>

      <p>The compounding effect matters here. When a customer grows their business, they use more of your product — and your revenue grows with them automatically, without a sales conversation or a manual upgrade. That's the real promise of a well-designed usage model.</p>
    </div>

    <!-- Section 3: How Recurly Structures It -->
    <div class="rc-lp-section">
      <h2>🔧 How Recurly Structures Usage Billing</h2>
      <p>Recurly breaks usage billing into three interconnected pieces. Understanding all three before you configure anything will save you significant rework later.</p>

      <div class="rc-three-col">
        <div class="rc-col-block">
          <div class="rc-col-block-num">01</div>
          <h4>Measured Units</h4>
          <p>A measured unit defines what you're counting — "API calls," "GB stored," "transactions processed." You create these under <strong>Configuration → Measured Units</strong> in the Admin Console, and they're reusable across multiple add-ons and plans. Think of them as the label on your usage meter.</p>
        </div>
        <div class="rc-col-block">
          <div class="rc-col-block-num">02</div>
          <h4>Usage Add-Ons</h4>
          <p>A usage add-on is attached to a plan and references a measured unit. It defines the pricing logic — per unit, tiered, volume, stairstep, or percentage. This is where you decide how usage translates to revenue. A single plan can carry multiple usage add-ons if you track several resources.</p>
        </div>
        <div class="rc-col-block">
          <div class="rc-col-block-num">03</div>
          <h4>Usage Records</h4>
          <p>Usage records are the actual data you log. They're written to Recurly via the API — one record per metering event, or batched — and tied to a specific subscription and add-on. Recurly sums all records within the billing period (or uses the most recent, depending on your calculation method) to produce the invoice line item.</p>
        </div>
      </div>
    </div>

    <!-- Section 4: Use Cases -->
    <div class="rc-lp-section">
      <h2>🃏 Common Use Cases</h2>
      <p>Usage billing applies to any product where consumption varies meaningfully between customers. Here are the most common patterns and how they map to Recurly's model.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon">⚡</div>
          <h4>API Calls &amp; Transactions</h4>
          <p>Charge per API call, webhook event, or transaction processed. A free tier of 10,000 calls/month lets prospects get started; they pay per call beyond that threshold. Works well with tiered pricing where early volume is free and higher tiers carry a per-unit rate.</p>
          <span class="rc-feature-tag">Per unit / Tiered</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🗄️</div>
          <h4>Storage &amp; Bandwidth</h4>
          <p>Bill by gigabytes stored, data transferred, or compute minutes used. Infrastructure and developer tooling products often combine a base subscription (for platform access) with a usage add-on (for resources consumed). Volume pricing rewards heavy users with lower per-GB rates.</p>
          <span class="rc-feature-tag">Volume / Tiered</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">👥</div>
          <h4>Seat Overages</h4>
          <p>Keep a base seat count in your plan price, and use a usage add-on to bill for seats beyond the included threshold. Log the peak active seat count each billing period. This hybrid model preserves predictable base revenue while capturing expansion from growing teams.</p>
          <span class="rc-feature-tag">Hybrid / Per unit</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">💳</div>
          <h4>Percentage of Volume</h4>
          <p>Take a percentage of total payment volume, revenue processed, or GMV flowing through your platform. Recurly supports percentage-based usage add-ons natively — no custom math required. This model aligns your revenue directly with your customers' success, which is a compelling pitch.</p>
          <span class="rc-feature-tag">Percentage</span>
        </div>
      </div>
    </div>

    <!-- Section 5: Limitations -->
    <div class="rc-lp-section">
      <h2>⚠️ Limitations to Know Before You Begin</h2>
      <p>Usage billing in Recurly is powerful, but it comes with important constraints that should shape your architecture decisions before you write a single line of configuration. Go into this with eyes open.</p>

      <div class="rc-accent-card rc-accent-orange">
        <h4>Four Constraints That Matter</h4>
        <ul>
          <li><strong>API-only logging:</strong> There is no way to enter usage records through the Recurly Admin Console UI. Every usage record must be written via the API. If your platform doesn't yet have an integration that logs usage programmatically, that work needs to happen before you go live with usage billing.</li>
          <li><strong>No backdating into closed periods:</strong> Once a billing cycle closes and an invoice is generated, you cannot add or modify usage records for that period. Usage must be logged during the active billing period — before the cycle closes. Plan your logging cadence accordingly.</li>
          <li><strong>No native analytics by usage:</strong> Recurly does not provide built-in dashboards showing usage trends, by-account consumption, or usage growth over time. The Usage Records export gives you raw data, but any meaningful analysis requires an external tool. Build your tracking setup before you activate usage billing.</li>
          <li><strong>Decimal logging is a feature flag:</strong> Whole-number quantities are the default. If you need decimal precision (e.g., billing for 1.75 GB rather than rounding to 2), the decimal usage logging feature must be enabled for your site. Contact Recurly Support before designing a model that requires decimal quantities.</li>
        </ul>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon">📊</div>
        <div class="rc-callout-body">
          <strong>Set up external tracking before you go live</strong>
          <p>Because Recurly provides no native analytics for usage data, you should have your external tracking pipeline ready — whether that's a data warehouse, a BI tool, or even a well-structured spreadsheet export from the Usage Records export — before you activate usage billing for real customers.</p>
        </div>
      </div>
    </div>

    <!-- Path navigation -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-btn-prev">← Account Hierarchy</a>
      <span class="rc-lp-nav-indicator">1 of 3</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing-configure" class="rc-btn-path">Next: Configure Usage Billing →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/usage-based-billing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Usage-Based Billing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/billing-models" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Pricing Models</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/add-ons" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Add-Ons</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Join Global Office Hours</a>
      </div>
    </div>

    <!-- Footer -->
    <div class="rc-footer-nav">
      <div class="rc-footer-section">
        <span class="rc-footer-section-label">Usage Billing:</span>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-footer-link">Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing-configure" class="rc-footer-link">Configure</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing-strategy" class="rc-footer-link">Strategy &amp; Best Practices</a>
      </div>
      <div class="rc-footer-section">
        <span class="rc-footer-section-label">P&amp;P 201:</span>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-footer-link">P&amp;P 201 Hub</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-segmentation" class="rc-footer-link">Segmentation</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-footer-link">Account Hierarchy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-footer-link">Usage Billing</a>
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
