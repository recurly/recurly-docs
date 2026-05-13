---
title: Navigate Code Testing Learning Path Payments Hub Overview Dashboard
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

/* Layout */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link { color: var(--gray); text-decoration: none !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Host-theme armor — neutralises ReadMe's global link border-bottom/underline styles.
   Button hover rules use .rc-guide prefix to outrank this rule's specificity. */
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:hover,
.rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

@media(max-width:768px){ .rc-content-wrap { padding: 0 20px; } .rc-top-nav { padding: 16px 20px; } }

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
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,88,16,0.20); border: 1px solid rgba(255,88,16,0.45); color: #FF5810; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: var(--lightgray); line-height: 1.6; }

/* Sticky nav — Scale pillar: #FF5810 bg, white text/chevron */
details.rc-sticky-nav-wrap { position: sticky; top: 0; z-index: 100; background-color: #FF5810; box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px 0; border-radius: 12px; border: 1px solid rgba(0,0,0,0.08); overflow: hidden; }
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: #fff; }
.rc-nav-chevron { font-size: .72rem; color: #fff; opacity: 0.55; line-height: 1; transition: transform 0.25s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
.rc-sticky-link { color: #fff !important; text-decoration: none !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; }
.rc-sticky-link:hover { background: var(--offblack); color: var(--yellow) !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-sticky-link-active { background: rgba(0,0,0,0.12); font-weight: 800; }
.rc-sticky-link-active:hover { background: var(--offblack); color: var(--yellow) !important; }

/* Section headings */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* Inline step video */
.rc-step-video { border-radius: 10px; margin-top: 16px; border: 1px solid var(--lightgray); overflow: hidden; background: var(--offblack); }
.rc-step-video-label { background: var(--offblack); padding: 9px 14px; display: flex; align-items: center; gap: 8px; }
.rc-step-video-label::before { content: '▶'; font-size: .6rem; color: #FF5810; flex-shrink: 0; }
.rc-step-video-label span { font-size: .72rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: var(--lightgray); }
.rc-step-video-frame { position: relative; overflow: hidden; aspect-ratio: 16/9; }
.rc-step-video-frame iframe { position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; }
.rc-step-video-caption { font-size: .8rem; color: var(--gray); padding: 8px 14px 10px; background: var(--brightgray); border-top: 1px solid var(--lightgray); line-height: 1.5; }

/* Screenshot */
.rc-screenshot { width: 100%; border-radius: 14px; border: 1px solid var(--lightgray); margin-bottom: 24px; display: block; }

/* Card */
.rc-card { background: var(--offwhite); border-radius: 16px; padding: 28px; border: 1px solid var(--lightgray); margin-bottom: 24px; }
.rc-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.75; margin: 0; }

/* Card grid — 2-col */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: #FF5810; box-shadow: 0 4px 16px rgba(255,88,16,0.15); transform: translateY(-2px); }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }
@media(max-width:768px){ .rc-card-grid { grid-template-columns: 1fr; } }

/* Callouts */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout + .rc-callout { margin-top: 12px; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-body a { color: var(--orange) !important; font-weight: 600; }
.rc-guide .rc-callout-body a:hover { text-decoration: underline !important; }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body strong { color: var(--offblack); }
.rc-callout-warning { background: rgba(255,215,6,0.12); border-left: 4px solid var(--yellow); }
.rc-callout-warning .rc-callout-body strong { color: var(--darkgray); }
.rc-callout-caution { background: rgba(255,130,0,0.08); border-left: 4px solid var(--orange); }
.rc-callout-caution .rc-callout-body strong { color: var(--darkgray); }

/* Checklist — pure CSS, no JS */
.rc-checklist { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 20px 0 32px; }
.rc-checklist-header { padding: 14px 22px; background: var(--offblack); display: flex; align-items: center; gap: 10px; }
.rc-checklist-header h4 { font-size: .82rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: var(--yellow); margin: 0; }
.rc-checklist-item { padding: 14px 22px; border-bottom: 1px solid var(--brightgray); display: flex; align-items: flex-start; gap: 14px; transition: background .15s; cursor: pointer; }
.rc-checklist-item:last-child { border-bottom: none; }
.rc-checklist-item:hover { background: var(--brightgray); }
.rc-checklist-item input[type="checkbox"] { position: absolute; opacity: 0; width: 0; height: 0; pointer-events: none; }
.rc-checkbox-box { width: 22px; height: 22px; border-radius: 6px; border: 2px solid var(--lightgray); flex-shrink: 0; background: #fff; display: flex; align-items: center; justify-content: center; transition: all .18s; margin-top: 1px; }
.rc-checklist-item input[type="checkbox"]:checked + .rc-checkbox-box { background: var(--offblack); border-color: var(--offblack); }
.rc-checklist-item input[type="checkbox"]:checked + .rc-checkbox-box::after { content: '✓'; color: var(--yellow); font-size: .75rem; font-weight: 800; line-height: 1; }
.rc-checklist-item input[type="checkbox"]:checked ~ .rc-checklist-text strong { text-decoration: line-through; color: var(--gray); }
.rc-checklist-item:has(input[type="checkbox"]:checked) { background: rgba(255,88,16,0.06); }
.rc-checklist-text { flex: 1; }
.rc-checklist-text strong { font-size: .9rem; font-weight: 700; color: var(--offblack); display: block; margin-bottom: 2px; transition: color .18s; }
.rc-checklist-text span { font-size: .8rem; color: var(--gray); line-height: 1.4; display: block; }
.rc-checklist-footer { padding: 10px 22px; background: var(--brightgray); border-top: 1px solid var(--lightgray); font-size: .78rem; color: var(--gray); font-weight: 600; }

/* Office Hours CTA — dark card, !important on all color properties per ReadMe constraint */
.rc-oh-cta { background: #0D0D0B !important; border: 2px solid #FFD706; border-radius: 14px; padding: 32px 36px; margin: 32px 0; }
.rc-oh-cta h4 { color: #FFD706 !important; font-size: 1.05rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px; }
.rc-oh-cta p { color: #CCC9B8 !important; font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
.rc-oh-cta p strong { color: #FFFDF2 !important; }
.rc-oh-btn { background: #FFD706 !important; color: #0D0D0B !important; text-decoration: none !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid #FFD706 !important; }
.rc-guide a.rc-oh-btn { border-bottom: 2px solid #FFD706 !important; }
.rc-guide .rc-oh-btn:hover { background: transparent !important; color: #FFD706 !important; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }

/* Path nav — .rc-guide prefix on hover rules to beat armor specificity */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-btn-prev { background: transparent; color: var(--offblack) !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--lightgray); transition: all .2s; }
.rc-guide a.rc-btn-prev { border-bottom: 2px solid var(--lightgray) !important; }
.rc-guide .rc-btn-prev:hover { border: 2px solid var(--offblack) !important; border-bottom: 2px solid var(--offblack) !important; }
.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); }
.rc-guide a.rc-btn-path { border-bottom: 2px solid var(--yellow) !important; }
.rc-guide .rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }
@media(max-width:768px){ .rc-lp-nav { flex-wrap: wrap; justify-content: center; } .rc-lp-nav-indicator { width: 100%; text-align: center; } }

/* Resources — var(--gray) link color, .rc-guide prefix on hover */
.rc-resources { background: var(--brightgray); border-left: 4px solid #FF5810; border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FF5810 !important; }

/* Footer nav */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 32px; margin-top: 32px; text-align: center; }
.rc-footer-links { display: flex; flex-wrap: wrap; gap: 24px; justify-content: center; align-items: center; }
.rc-footer-link { color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .9rem; transition: color .2s; display: inline-flex; align-items: center; gap: 5px; }
.rc-footer-link:hover { color: var(--offblack); }
.rc-footer-link img { width: 13px; height: 13px; object-fit: contain; opacity: 0.55; }

/* Responsive */
@media(max-width:768px){
  .rc-hero { padding: 36px 20px 32px; }
  .rc-lp-hero-title h1 { font-size: 1.7rem; }
}
</style>

<div class="rc-guide">
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub" class="rc-back-link">← Back to Payments Hub</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Announcement bar (hidden — add rc-active to show) -->
    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>Upcoming:</strong> Join our CSMs for a live Payments Hub walkthrough.
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- Hero — step pages use pillar pill only, no stats strip -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Scale">
        Scale
      </div>
      <div class="rc-lp-hero-title"><h1>Overview dashboard</h1></div>
      <p>The Overview dashboard is your starting point — a high-level summary of your payment health, with filters to drill into exactly what you need.</p>
    </div>

    <!-- Sticky nav — Step 1 active -->
    <details class="rc-sticky-nav-wrap">
      <summary><span class="rc-nav-toggle-label">Navigate Quick Links <span class="rc-nav-chevron">▲</span></span></summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Payments Hub
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview" class="rc-sticky-link rc-sticky-link-active"><span class="rc-step-badge">1</span> Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing" class="rc-sticky-link"><span class="rc-step-badge">2</span> Payment processing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater" class="rc-sticky-link"><span class="rc-step-badge">3</span> Account updater</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries" class="rc-sticky-link"><span class="rc-step-badge">4</span> Payment retry recovery</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention" class="rc-sticky-link"><span class="rc-step-badge">5</span> Fraud prevention</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources" class="rc-sticky-link"><span class="rc-step-badge">6</span> Review &amp; resources</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
        </a>
      </div></div></div>
    </details>

    <!-- Section 1: Dashboard intro + screenshot + video -->
    <div class="rc-lp-section">
      <h2>🏠 Overview dashboard</h2>
      <p>Your top-level payment health summary. This is the first thing you see when you open Payments Hub — a single view of how your payments are performing across all gateways and methods.</p>

      <img class="rc-screenshot" src="https://files.readme.io/ea22de0f101e14451f795623abc56a40f45d4f4a6fb18edbaf367c0b7c5650d1-Overview_Dashboard.png" alt="Payments Hub Overview dashboard" />

      <h2>🎬 Overview Dashboard Walkthrough</h2>

      <!-- ⚠️ Replace src with the public Goldcast embed URL for this clip -->
      <!-- Grab the embed URL from the clip's Share panel in Goldcast admin -->
      <div class="rc-step-video">
        <div class="rc-step-video-label"><span>Dashboard demo</span></div>
        <div class="rc-step-video-frame">
          <iframe src="about:blank" loading="lazy" title="Payments Hub: Overview dashboard demo" allowfullscreen allow="encrypted-media; fullscreen; microphone; screen-wake-lock;"></iframe>
        </div>
        <div class="rc-step-video-caption">A quick walkthrough of the Overview dashboard — what each tile shows and how to use the filters.</div>
      </div>
    </div>

    <!-- Section 2: What's on this dashboard -->
    <div class="rc-lp-section">
      <h2>📋 What's on this dashboard</h2>

      <div class="rc-card">
        <p>
          <strong>Global payment volume distribution</strong> — A heat map showing where your payments are coming from by billing country. Darker shades = higher volume.<br><br>
          <strong>Payment method distribution</strong> — A pie chart showing the share of transactions by payment method type (credit card, PayPal, Apple Pay, etc.).<br><br>
          <strong>Overall success rate</strong> — Your blended payment success rate across all methods and gateways, with a comparison to the previous time period.<br><br>
          <strong>CIT success rate</strong> — Customer Initiated Transactions: payments where the customer is actively in session (sign-ups, checkout clicks, dunning re-entries).<br><br>
          <strong>MIT success rate</strong> — Merchant Initiated Transactions: automatic recurring renewals and scheduled payments.<br><br>
          <strong>Account Updater tile</strong> — Revenue authorized on automatically updated cards in the period. Visible to Account Updater enabled merchants only.<br><br>
          <strong>Payment Retry Recovery tile</strong> — Revenue recovered on failed invoices in the time period. Includes all success reasons: retries, account updater, backup gateway, new payment method from dunning, etc.<br><br>
          <strong>Fraud blocking tile</strong> — Count of transactions blocked by Kount. Visible to Kount-enabled merchants only.
        </p>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>No data on Account Updater or Fraud tiles?</strong>
          <p>If you don't have Account Updater or Kount enabled, those tiles will display a "Learn More" prompt instead of data. This is expected — the dashboard is aware of which features you have active.<br><br>
          🔰 Learn more about <a href="https://docs.recurly.com/recurly-subscriptions/docs/kount" target="_blank" rel="noopener noreferrer">Kount fraud prevention →</a><br>
          🔄 Account Updater not enabled yet? Learn what it means and how to make it work for you via the <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater">Account Updater learning path →</a></p>
        </div>
      </div>
    </div>

    <!-- Section 3: CIT vs MIT -->
    <div class="rc-lp-section">
      <h2>🔍 CIT vs. MIT — what's the difference?</h2>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <h4>CIT — Customer Initiated</h4>
          <p>The customer is present. Includes sign-up transactions, checkout pages, and dunning click-throughs where a customer re-enters their card. These typically have higher success rates because the customer is actively engaged.</p>
        </div>
        <div class="rc-feature-card">
          <h4>MIT — Merchant Initiated</h4>
          <p>Automatic payments. Includes all scheduled subscription renewals and recurring charges that happen without the customer in session — which is why tools like Account Updater and intelligent retries matter most here.</p>
        </div>
      </div>
    </div>

    <!-- Section 4: Using the filters -->
    <div class="rc-lp-section">
      <h2>🎛️ Using the filters</h2>
      <p>All filters sit at the top of the dashboard and apply to the entire page. Every chart, table, and metric updates when you apply one. You can also click directly on the map or pie chart to filter by that selection.</p>

      <div class="rc-card">
        <p>
          <strong>Date range</strong> — Defaults to the last 30 days. Adjust to any custom range.<br>
          <strong>Country</strong> — Filter by billing country on the transaction.<br>
          <strong>Gateway</strong> — Isolate data for one or more connected gateways.<br>
          <strong>Payment method</strong> — Focus on a specific payment type (e.g., Apple Pay, PayPal).<br>
          <strong>Initiated by</strong> — Filter to CIT only or MIT only.<br>
          <strong>Currency</strong> — Filter to a specific currency.
        </p>
      </div>
    </div>

    <!-- Section 5: Activity checklist -->
    <div class="rc-lp-section">
      <h2>✅ Activity: Explore the Overview</h2>

      <div class="rc-checklist">
        <div class="rc-checklist-header"><span style="font-size:1rem;">✅</span><h4>Overview activity</h4></div>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text"><strong>What is your overall payment success rate? Is it trending up or down compared to the previous period?</strong><span>Look for the red or green delta below the success rate tile</span></div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text"><strong>Try filtering by country. Does your success rate change significantly for any region?</strong><span>Click directly on the map to filter — click again to deselect</span></div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text"><strong>Look at the payment method distribution. Is the split what you expected?</strong><span>Are there payment methods with a higher share than you realized?</span></div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text"><strong>Compare your CIT and MIT success rates. Which is higher, and by how much?</strong><span>A large gap between the two may be worth exploring in the Payment Processing dashboard</span></div>
        </label>
        <div class="rc-checklist-footer">✓ Tap each item to mark it complete</div>
      </div>
    </div>

    <!-- Office Hours CTA -->
    <div class="rc-oh-cta">
      <h4>🗓️ Want to talk through your numbers?</h4>
      <p>Join <strong>Global Office Hours</strong> to walk through your Overview dashboard with a Recurly Customer Success Manager. We can help you understand what your metrics mean and what to prioritize.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <!-- Path nav -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub" class="rc-btn-prev">← Payments Hub</a>
      <span class="rc-lp-nav-indicator">1 of 6</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing" class="rc-btn-path">Next: Payment processing →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/payments-hub-overview" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Overview dashboard</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Join Global Office Hours</a>
      </div>
    </div>

    <!-- Footer nav -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link"><img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub" class="rc-footer-link">Path Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview" class="rc-footer-link">Step 1: Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing" class="rc-footer-link">Step 2: Payment processing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater" class="rc-footer-link">Step 3: Account updater</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries" class="rc-footer-link">Step 4: Payment retry recovery</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention" class="rc-footer-link">Step 5: Fraud prevention</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources" class="rc-footer-link">Step 6: Review &amp; resources</a>
        <a href="mailto:support@recurly.com" class="rc-footer-link">support@recurly.com</a>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
