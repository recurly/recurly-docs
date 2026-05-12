---
title: Navigate Code Testing Learning Path
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Account Updater — Recurly Navigate</title>
<style>
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
  --retain: #FF9D88;
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--darkgray);
}
.rc-guide * { box-sizing: border-box; }
body { margin: 0; background: #fff; }

/* ── ANNOUNCEMENT BAR (hidden — remove display:none to activate) ── */
.rc-announce-bar {
  display: none;
  background: var(--yellow);
  color: var(--offblack);
  align-items: center;
  justify-content: space-between;
  padding: 10px 20px;
  font-size: .88rem;
  font-weight: 600;
  border-radius: 10px;
  margin-bottom: 16px;
  gap: 12px;
  line-height: 1.4;
}
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 12px; flex: 1; flex-wrap: wrap; }
.rc-announce-link {
  color: var(--offblack) !important; font-weight: 800; text-decoration: none !important;
  white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; transition: background 0.2s;
}
.rc-announce-link:hover { background: rgba(0,0,0,0.20); }
.rc-announce-close {
  background: none; border: none; font-size: 1.4rem; line-height: 1; cursor: pointer;
  color: var(--offblack); padding: 0 2px; opacity: 0.45; transition: opacity 0.2s; flex-shrink: 0;
}
.rc-announce-close:hover { opacity: 1; }

/* ── TOP BACK LINK ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link { color: var(--gray); text-decoration: none !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }

/* ── CONTENT WRAPPER ── */
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* ── LEARNING PATH HERO ── */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack);
  background-size: cover;
  color: #fff;
  padding: 48px 40px 44px;
  text-align: center;
  border-radius: 16px;
  margin-bottom: 0;
}
.rc-brand-header { display: flex; align-items: center; justify-content: center; margin-bottom: 28px; }
.rc-logo-image { height: 36px; width: auto; }

.rc-lp-hero-title {
  text-align: center;
  margin: 0 0 14px;
}
.rc-lp-pillar-badge {
  display: inline-block;
  vertical-align: middle;
  width: 26px;
  height: 26px;
  object-fit: contain;
  opacity: 0.9;
  margin-right: 10px;
  margin-bottom: 4px;
}
.rc-lp-hero-title h1 {
  display: inline;
  font-size: 2.2rem;
  font-weight: 800;
  line-height: 1.15;
  color: var(--offwhite);
  margin: 0;
  vertical-align: middle;
}
.rc-hero > p {
  font-size: 1rem;
  opacity: .85;
  max-width: 640px;
  margin: 0 auto 32px;
  color: var(--lightgray);
  line-height: 1.6;
}

/* Hero stats (learning paths only) */
.rc-hero-stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 0;
  border-top: 1px solid rgba(255,255,255,0.12);
  padding-top: 24px;
  margin-top: 4px;
}
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); line-height: 1.3; }

/* ── NAVIGATE QUICK LINKS NAV — Retain accent ── */
details.rc-sticky-nav-wrap {
  position: sticky;
  top: 0;
  z-index: 100;
  background-color: var(--retain);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px 0;
  border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08);
  overflow: hidden;
}
details.rc-sticky-nav-wrap > summary {
  list-style: none;
  display: flex;
  align-items: center;
  padding: 15px 24px;
  cursor: pointer;
  user-select: none;
}
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label {
  display: inline-flex; align-items: center; gap: 8px;
  font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: var(--offblack);
}
.rc-nav-chevron { font-size: .72rem; color: var(--offblack); opacity: 0.55; line-height: 1; transition: transform 0.25s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
.rc-sticky-link {
  color: var(--offblack) !important; text-decoration: none !important;
  font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase;
  padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap;
  display: inline-flex; align-items: center; gap: 6px;
}
.rc-sticky-link:hover { background: var(--offblack); color: var(--yellow) !important; text-decoration: none !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
/* Step number circles in nav */
.rc-step-badge {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: var(--offblack);
  color: var(--yellow);
  font-size: .65rem;
  font-weight: 800;
  flex-shrink: 0;
  line-height: 1;
}
  background: rgba(0,0,0,0.12);
  font-weight: 800;
}
.rc-sticky-link-active:hover { background: var(--offblack); color: var(--yellow) !important; }

/* ── CONTENT SECTIONS ── */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 {
  font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack);
  display: flex; align-items: center; gap: 12px;
}
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section h3 { font-size: 1.1rem; font-weight: 700; margin: 24px 0 10px; color: var(--offblack); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* ── AU TYPE CARDS (3-col grid) ── */
.rc-type-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0 28px; }
.rc-type-card {
  background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px;
  padding: 20px; display: flex; flex-direction: column; gap: 8px;
}
.rc-type-card-icon { font-size: 1.4rem; line-height: 1; }
.rc-type-card h4 { font-size: .95rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-type-card p { font-size: .88rem; color: var(--gray); line-height: 1.5; margin: 0; }

/* ── NUMBERED STEPS ── */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 20px 0 28px; }
.rc-step {
  display: grid;
  grid-template-columns: 40px 1fr;
  gap: 16px;
  align-items: flex-start;
  padding: 16px 0;
  border-bottom: 1px solid var(--brightgray);
}
.rc-step:last-child { border-bottom: none; }
.rc-step-num {
  width: 36px; height: 36px; border-radius: 50%;
  background: var(--offblack); color: var(--yellow);
  display: flex; align-items: center; justify-content: center;
  font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px;
}
.rc-step-content h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.55; margin: 0; }

/* ── CALLOUT BOXES ── */
.rc-callout {
  border-radius: 10px; padding: 16px 20px; margin: 20px 0;
  display: flex; gap: 14px; align-items: flex-start;
}
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }

.rc-callout-warning { background: rgba(255,215,6,0.12); border-left: 4px solid var(--yellow); }
.rc-callout-warning .rc-callout-body strong { color: var(--darkgray); }

.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body strong { color: var(--offblack); }

/* ── PATH NAVIGATION BUTTONS ── */
.rc-lp-nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  margin: 40px 0 16px;
}
/* Static "you are here" indicator — not a link */
.rc-btn-current {
  background: var(--brightgray);
  color: var(--gray) !important;
  padding: 13px 24px; border-radius: 10px;
  font-weight: 700; font-size: .9rem;
  display: inline-flex; align-items: center; gap: 8px;
  border: 2px solid var(--lightgray);
  cursor: default;
  user-select: none;
}
/* Active "next" link */
.rc-btn-path {
  background: var(--yellow); color: var(--offblack) !important;
  text-decoration: none !important; padding: 13px 28px; border-radius: 10px;
  font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px;
  transition: all .2s; border: 2px solid var(--yellow);
}
.rc-btn-path:hover { background: transparent; color: var(--offblack) !important; }

/* ── RESOURCES — callout style, tied to page content ── */
.rc-resources {
  background: var(--brightgray);
  border-left: 4px solid var(--retain);
  border-radius: 10px;
  padding: 20px 24px;
  margin: 32px 0 0;
}
.rc-resources h3 {
  font-size: .75rem; font-weight: 700; text-transform: uppercase;
  letter-spacing: .9px; color: var(--gray); margin: 0 0 12px;
}
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link {
  color: var(--darkgray) !important;
  text-decoration: underline !important;
  text-underline-offset: 3px;
  text-decoration-color: var(--lightgray) !important;
  font-weight: 500;
  font-size: .88rem;
  transition: all .18s;
  display: inline-flex; align-items: center; gap: 6px;
}
.rc-resource-link:hover {
  color: var(--offblack) !important;
  text-decoration-color: var(--retain) !important;
}

/* ── FOOTER NAV ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 32px; margin-top: 32px; text-align: center; }
.rc-footer-links { display: flex; flex-wrap: wrap; gap: 24px; justify-content: center; align-items: center; }
.rc-footer-link {
  color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .9rem;
  transition: color .2s; display: inline-flex; align-items: center; gap: 5px;
}
.rc-footer-link:hover { color: var(--offblack); }
.rc-footer-link img { width: 13px; height: 13px; object-fit: contain; opacity: 0.55; }

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; }
  .rc-type-grid { grid-template-columns: 1fr; }
  .rc-lp-nav { justify-content: center; }
}
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-back-link">← Back to Retain</a>
  </div>

  <div class="rc-content-wrap">

    <!-- ── ANNOUNCEMENT BAR (hidden — add class "rc-active" to show) ── -->
    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>Upcoming:</strong> Join our CSMs for a live session on this topic.
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- ── HERO ── -->
    <div class="rc-hero">
      <div class="rc-brand-header">
        <img src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly" class="rc-logo-image">
      </div>
      <div class="rc-lp-hero-title">
        <img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt="Retain" class="rc-lp-pillar-badge">
        <h1>Account Updater</h1>
      </div>
      <p>Protect your recurring revenue by automatically keeping card details up to date — before payments ever fail.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">77x</div>
          <div class="rc-hero-stat-label">Average ROI</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">18%</div>
          <div class="rc-hero-stat-label">Of recovered revenue</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">96M+</div>
          <div class="rc-hero-stat-label">Card updates in 2025</div>
        </div>
      </div>
    </div>

    <!-- ── NAVIGATE QUICK LINKS NAV ── -->
    <details class="rc-sticky-nav-wrap">
      <summary>
        <span class="rc-nav-toggle-label">
          Navigate Quick Links
          <span class="rc-nav-chevron">▲</span>
        </span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Account Updater
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits" class="rc-sticky-link"><span class="rc-step-badge">1</span> Why use it?</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations" class="rc-sticky-link"><span class="rc-step-badge">2</span> Things to consider</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable" class="rc-sticky-link"><span class="rc-step-badge">3</span> How to enable it</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data" class="rc-sticky-link"><span class="rc-step-badge">4</span> Tracking impact</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case" class="rc-sticky-link"><span class="rc-step-badge">5</span> Pitch to leadership</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- ── WHAT IS ACCOUNT UPDATER ── -->
    <div class="rc-lp-section">
      <h2>💳 What is Account Updater?</h2>
      <p>A proactive assistant designed to resolve card lifecycle events before they trigger a decline. Reduce involuntary churn and eliminate gateway fees on invalid accounts.</p>

      <h3>🧩 The simple version</h3>
      <p>When a customer's credit or debit card expires, gets lost or stolen, or is reissued by their bank, the card number or expiration date changes. If you're charging that card on a recurring basis — like a subscription renewal — that charge will simply fail. The customer hasn't cancelled; their card just changed.</p>
      <p><strong>Account Updater (AU) is the solution.</strong> It's a service run by the major card networks — Visa, Mastercard, American Express (AMEX), and Discover — that automatically pushes updated card details to Recurly. Recurly stores that fresh information so that your next billing attempt uses the correct data, without the customer needing to do anything.</p>

      <div class="rc-type-grid">
        <div class="rc-type-card">
          <div class="rc-type-card-icon">🔄</div>
          <h4>Standard Account Updater</h4>
          <p>Supported for Visa, Mastercard, AMEX, and Discover. Updates are fetched via secure batch files before renewal attempts.</p>
        </div>
        <div class="rc-type-card">
          <div class="rc-type-card-icon">⚡</div>
          <h4>Real-Time Account Updater (RTAU)</h4>
          <p>Supported for Visa, Mastercard, and AMEX globally, with Discover available via specific gateways.</p>
        </div>
        <div class="rc-type-card">
          <div class="rc-type-card-icon">🏦</div>
          <h4>Cardrefresher</h4>
          <p>AMEX's specialized AU service. Provides a robust fallback for legacy integrations while many updates now happen via RTAU.</p>
        </div>
      </div>
    </div>

    <!-- ── HOW IT WORKS ── -->
    <div class="rc-lp-section">
      <h2>🗺️ How it works — step by step</h2>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>A cardholder's bank issues a card change</h4>
            <p>This could be a new card number or updated expiration date. Common events: annual renewals, fraud replacements, or bank migrations.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>The card network is notified</h4>
            <p>Visa, Mastercard, American Express (AMEX), or Discover updates their internal records with the new card details.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Recurly is alerted</h4>
            <p>For standard AU, Recurly checks for updates on a scheduled basis. For RTAU, Recurly requests the update at the exact moment a transaction is attempted.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Recurly updates the stored payment method</h4>
            <p>For all participating banks and eligible card types, new card details replace the old ones in the vault — silently, automatically, and without action required from your customer.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">5</div>
          <div class="rc-step-content">
            <h4>The next renewal charges successfully</h4>
            <p>Because the billing info is already up to date, the subscription renews without interruption. No failed payment. No dunning. No involuntary churn.</p>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon">⚠️</div>
        <div class="rc-callout-body">
          <strong>Note on digital wallets</strong>
          <p>Account Updater works with cards stored in Recurly's vault. Apple Pay and Google Pay handle card lifecycle updates natively within their own ecosystem.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>The Bottom Line</strong>
          <p>Account Updater fixes outdated card details behind the scenes. It's one of the few revenue recovery tools that is entirely proactive rather than reactive.</p>
        </div>
      </div>
    </div>

    <!-- ── PATH NAVIGATION ── -->
    <div class="rc-lp-nav">
      <span class="rc-btn-current">🎯 Start</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits" class="rc-btn-path">
        Next: Why use it? →
      </a>
    </div>

    <!-- ── RESOURCES ── -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/account-updater" target="_blank" class="rc-resource-link">📖 Recurly Docs: Account Updater</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" class="rc-resource-link">🌐 Join Global Office Hours</a>
      </div>
    </div>

    <!-- ── FOOTER NAV ── -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" class="rc-footer-link">Account Updater</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits" class="rc-footer-link">1. Why use it?</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations" class="rc-footer-link">2. Things to consider</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable" class="rc-footer-link">3. How to enable it</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data" class="rc-footer-link">4. Tracking impact</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case" class="rc-footer-link">5. Pitch to leadership</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
          <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
        </a>
        <a href="mailto:support@recurly.com" class="rc-footer-link">support@recurly.com</a>
      </div>
    </div>

  </div>
</div>
</body>
</html>
`}</HTMLBlock>

<br />
