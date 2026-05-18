---
title: Navigate Code Test - Gemini
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
  --retain:    #FF9D88;
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--darkgray);
}
.rc-guide * { box-sizing: border-box; }

/* ── HOST-THEME ARMOR ── */
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:hover,
.rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

/* ── ANNOUNCEMENT BAR ── */
.rc-announce-bar {
  display: none; background: var(--yellow); color: var(--offblack);
  align-items: center; justify-content: space-between;
  padding: 10px 20px; font-size: .88rem; font-weight: 600;
  border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4;
}
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 12px; flex: 1; flex-wrap: wrap; }
.rc-announce-link { color: var(--offblack) !important; font-weight: 800; text-decoration: none !important; white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; transition: background 0.2s; }
.rc-announce-link:hover { background: rgba(0,0,0,0.20); }
.rc-announce-close { background: none; border: none; font-size: 1.4rem; line-height: 1; cursor: pointer; color: var(--offblack); padding: 0 2px; opacity: 0.45; transition: opacity 0.2s; flex-shrink: 0; }
.rc-announce-close:hover { opacity: 1; }

/* ── TOP BACK LINK ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link { color: var(--gray); text-decoration: none !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }

/* ── CONTENT WRAPPER ── */
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* ── HERO ── */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack); background-size: cover;
  color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0;
}
.rc-lp-pillar-tag {
  display: inline-flex; align-items: center; gap: 7px;
  background: rgba(255,157,136,0.20); border: 1px solid rgba(255,157,136,0.45);
  color: #FF9D88; font-size: .75rem; font-weight: 800;
  letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 14px; border-radius: 20px; margin-bottom: 20px;
}
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: var(--lightgray); line-height: 1.6; }
.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); line-height: 1.3; }

/* ── NAVIGATION MENU (NON-STICKY) ── */
details.rc-sticky-nav-wrap {
  position: relative; z-index: 1;
  background-color: var(--retain);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px 0; border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08); overflow: hidden;
}
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
.rc-sticky-link {
  color: var(--offblack) !important; text-decoration: none !important;
  font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase;
  padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap;
  display: inline-flex; align-items: center; gap: 6px;
}
.rc-sticky-link:hover { background: var(--offblack); color: var(--yellow) !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-sticky-link:hover .rc-step-badge { background: var(--yellow); color: var(--offblack); }
.rc-sticky-link-active { background: rgba(0,0,0,0.12); font-weight: 800; }
.rc-sticky-link-active:hover { background: var(--offblack); color: var(--yellow) !important; }

/* ── CONTENT SECTIONS ── */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* ── CUSTOM SPLIT CARD (RESTORED) ── */
.rc-split-card { display: grid; grid-template-columns: 1fr 1fr; gap: 0; border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 8px 0 28px; }
.rc-split-panel { padding: 24px 28px; display: flex; flex-direction: column; gap: 10px; }
.rc-split-panel:first-child { background: var(--brightgray); border-right: 1px solid var(--lightgray); }
.rc-split-panel:last-child { background: rgba(255,157,136,0.10); }
.rc-split-label { font-size: .7rem; font-weight: 700; letter-spacing: 1px; text-transform: uppercase; }
.rc-split-panel:first-child .rc-split-label { color: var(--gray); }
.rc-split-panel:last-child .rc-split-label { color: var(--retain); }
.rc-split-icon { font-size: 1.4rem; line-height: 1; }
.rc-split-panel h4 { font-size: 1rem; font-weight: 800; margin: 0; line-height: 1.3; color: var(--offblack); }
.rc-split-panel p { font-size: .9rem; line-height: 1.6; margin: 0; }
.rc-split-panel:first-child p { color: var(--gray); }
.rc-split-panel:last-child p { color: var(--darkgray); }

/* ── TYPE SUBLABEL & CARD GRIDS ── */
.rc-type-sublabel { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--darkgray); margin: 0 0 12px; }
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-card-grid-3col { grid-template-columns: 1fr 1fr 1fr; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: var(--retain); box-shadow: 0 4px 16px rgba(255,157,136,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }

/* ── NUMBERED STEPS ── */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 20px 0 0; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0; }

/* ── CALLOUTS ── */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout + .rc-callout { margin-top: 12px; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body > strong { color: var(--offblack); }
.rc-callout-warning { background: rgba(255,215,6,0.12); border-left: 4px solid var(--yellow); }
.rc-callout-warning .rc-callout-body > strong { color: var(--darkgray); }

/* ── PATH NAV BUTTONS ── */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-btn-start { background: var(--brightgray); color: var(--gray); padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid var(--lightgray); cursor: default; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* ── RESOURCES ── */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--retain); border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FF9D88 !important; }

/* ── FOOTER NAV ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rc-footer-link { color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; }
.rc-footer-link:hover { color: var(--orange); }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* ── RESPONSIVE ── */
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
  .rc-card-grid, .rc-card-grid.rc-card-grid-3col { grid-template-columns: 1fr; }
  .rc-stat-strip { grid-template-columns: 1fr; }
  .rc-next-grid { grid-template-columns: 1fr; }
  
  /* Split card specific responsive rule */
  .rc-split-card { grid-template-columns: 1fr; } 
  .rc-split-panel:first-child { border-right: none; border-bottom: 1px solid var(--lightgray); }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="/docs/navigate-retain" class="rc-back-link">← Back to Retain</a>
  </div>

  <div class="rc-content-wrap">

    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>Upcoming:</strong> Join our CSMs for a live session on this topic.
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt="Retain"> Retain
      </div>
      <div class="rc-lp-hero-title">
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

    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
            </a>
            <a href="/docs/navigate-retain-account-updater" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Account Updater
            </a>
            <a href="/docs/navigate-retain-account-updater-benefits" class="rc-sticky-link"><span class="rc-step-badge">1</span> Why use it?</a>
            <a href="/docs/navigate-retain-account-updater-considerations" class="rc-sticky-link"><span class="rc-step-badge">2</span> Things to consider</a>
            <a href="/docs/navigate-retain-account-updater-enable" class="rc-sticky-link"><span class="rc-step-badge">3</span> How to enable it</a>
            <a href="/docs/navigate-retain-account-updater-data" class="rc-sticky-link"><span class="rc-step-badge">4</span> Tracking impact</a>
            <a href="/docs/navigate-retain-account-updater-use-case" class="rc-sticky-link"><span class="rc-step-badge">5</span> Pitch to leadership</a>
          </div>
        </div>
      </div>
    </details>

    <div class="rc-lp-section">
      <h2>💳 What is it?</h2>
      <p>A proactive tool that resolves card lifecycle events before they trigger a decline — reducing involuntary churn and eliminating gateway fees on invalid accounts.</p>

      <div class="rc-split-card">
        <div class="rc-split-panel">
          <div class="rc-split-label">The Problem</div>
          <div class="rc-split-icon">💳</div>
          <h4>Cards change. Charges fail.</h4>
          <p>When a customer's card expires, gets lost or stolen, or is reissued by their bank, the card number or expiration date changes. If you're charging that card on a recurring basis, that charge will simply fail — even though the customer never cancelled.</p>
        </div>
        <div class="rc-split-panel">
          <div class="rc-split-label">The Fix</div>
          <div class="rc-split-icon">✅</div>
          <h4>Account Updater handles it automatically.</h4>
          <p>Visa, Mastercard, AMEX, and Discover push updated card details directly to Recurly. Recurly stores the fresh information so your next billing attempt uses the correct data — no action needed from your customer.</p>
        </div>
      </div>

      <p class="rc-type-sublabel">Three ways it's delivered</p>
      
      <div class="rc-card-grid rc-card-grid-3col">
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🔄</div>
          <h4>Standard Account Updater</h4>
          <p>Supported for Visa, Mastercard, AMEX, and Discover. Updates are fetched via secure batch files before renewal attempts.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">⚡</div>
          <h4>Real-Time Account Updater (RTAU)</h4>
          <p>Supported for Visa, Mastercard, and AMEX globally, with Discover available via specific gateways.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🏦</div>
          <h4>Cardrefresher</h4>
          <p>AMEX's specialized AU service. Provides a robust fallback for legacy integrations while many updates now happen via RTAU.</p>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2>🗺️ How it works</h2>
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

    <div class="rc-lp-nav">
      <span class="rc-btn-start">Start</span>
      <span class="rc-lp-nav-indicator">1 of 6</span>
      <a href="/docs/navigate-retain-account-updater-benefits" class="rc-btn-path">Next: Why use it? →</a>
    </div>

    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/account-updater" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Account Updater</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Join Global Office Hours</a>
      </div>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Course: Account Updater:</span>
          <a href="/docs/navigate-retain-account-updater" class="rc-footer-link">Overview</a>
          <a href="/docs/navigate-retain-account-updater-benefits" class="rc-footer-link">1. Why use it?</a>
          <a href="/docs/navigate-retain-account-updater-considerations" class="rc-footer-link">2. Things to consider</a>
          <a href="/docs/navigate-retain-account-updater-enable" class="rc-footer-link">3. How to enable it</a>
          <a href="/docs/navigate-retain-account-updater-data" class="rc-footer-link">4. Tracking impact</a>
          <a href="/docs/navigate-retain-account-updater-use-case" class="rc-footer-link">5. Pitch to leadership</a>
        </div>
        <div class="rc-footer-utility">
          <a href="/docs/navigate-home" class="rc-footer-link">
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
