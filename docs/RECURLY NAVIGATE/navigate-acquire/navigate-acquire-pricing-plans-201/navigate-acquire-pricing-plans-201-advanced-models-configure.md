---
title: 'Advanced Pricing Models: Configuration'
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

/* Section headings */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* Model dividers */
.rc-model-header { background: var(--offblack); border-radius: 10px 10px 0 0; padding: 14px 22px; display: flex; align-items: center; gap: 12px; margin-top: 32px; }
.rc-model-header-icon { font-size: 1.2rem; line-height: 1; }
.rc-model-header h3 { font-size: .88rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: var(--yellow); margin: 0; }
.rc-model-body { border: 1px solid var(--lightgray); border-top: none; border-radius: 0 0 10px 10px; padding: 0; margin-bottom: 40px; }

/* Numbered steps */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 0; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 22px; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0 0 8px; }
.rc-step-content p:last-child { margin-bottom: 0; }
.rc-step-content strong { color: var(--darkgray); }
.rc-step-content a { color: var(--orange); font-weight: 600; text-decoration: none !important; }
.rc-guide .rc-step-content a:hover { text-decoration: underline !important; }
.rc-step-content code { background: var(--brightgray); color: var(--offblack); padding: 2px 7px; border-radius: 4px; font-size: .82rem; font-family: monospace; }

/* Video card */
.rc-video-card { border: 1px solid var(--lightgray); border-radius: 14px; overflow: hidden; margin: 0 0 40px; }
.rc-video-header { background: var(--offblack); padding: 16px 22px; display: flex; align-items: center; gap: 10px; }
.rc-video-header h4 { font-size: .88rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: var(--yellow); margin: 0; }
.rc-video-header span { font-size: .78rem; color: var(--lightgray); margin-left: auto; }
.rc-video-embed { position: relative; overflow: hidden; aspect-ratio: 16/9; background: var(--offblack); }
.rc-video-embed iframe { position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; }
.rc-video-caption { padding: 12px 22px; font-size: .83rem; color: var(--gray); background: var(--brightgray); border-top: 1px solid var(--lightgray); line-height: 1.5; }

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

/* Path nav */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-guide a.rc-btn-prev { background: transparent; color: var(--offblack) !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--lightgray); transition: all .2s; }
.rc-guide a.rc-btn-prev { border-bottom: 2px solid var(--lightgray) !important; }
.rc-guide a.rc-btn-prev:hover { border: 2px solid var(--offblack) !important; border-bottom: 2px solid var(--offblack) !important; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); }
.rc-guide a.rc-btn-path { border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

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
      <div class="rc-lp-hero-title"><h1>Configure Advanced Pricing Models</h1></div>
      <p>Exact UI paths and configuration steps for Ramp Pricing, Hybrid Pricing, and Prepaid Account Balance — from plan setup to first subscription.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">12</div>
          <div class="rc-hero-stat-label">Maximum ramp intervals on a single Recurly plan</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">$0</div>
          <div class="rc-hero-stat-label">Possible first-period cost with an intro ramp structure</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">100%</div>
          <div class="rc-hero-stat-label">Of prepaid revenue collected before service delivery</div>
        </div>
      </div>
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
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models" class="rc-sticky-link">
              <span class="rc-step-badge">1</span> Overview
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models-configure" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Configure
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

    <!-- Intro -->
    <div class="rc-lp-section">
      <h2>📹 Trail Guide Walkthrough</h2>
      <div class="rc-video-card">
        <div class="rc-video-header">
          <h4>Configuring Advanced Pricing Models in Recurly</h4>
          <span>~6 min</span>
        </div>
        <div class="rc-video-embed">
          <iframe src="about:blank" loading="lazy" title="Configure Advanced Pricing Models Walkthrough" allowfullscreen allow="encrypted-media; fullscreen; microphone; screen-wake-lock;"></iframe>
        </div>
        <div class="rc-video-caption">This walkthrough covers creating a ramp-priced plan, building a hybrid plan with a usage add-on, and adding a prepaid credit balance to a customer account.</div>
      </div>
    </div>

    <!-- Model A: Ramp Pricing -->
    <div class="rc-lp-section">
      <h2>🪜 Part A: Configure Ramp Pricing</h2>
      <p>Ramp pricing is configured entirely at the plan level. Once the plan is set, any subscription to that plan will follow the defined price schedule automatically — no manual updates required at each period change.</p>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon">⚠️</div>
        <div class="rc-callout-body">
          <strong>Confirm feature eligibility first</strong>
          <p>Ramp pricing requires the <strong>Only Bill What Changed</strong> feature enabled on your Recurly account. Accounts created before May 2018 also require <strong>Credit Invoices</strong> to be active. This feature may not be available on Starter or Pro plan tiers — contact Recurly Support or Sales to verify before configuring.</p>
        </div>
      </div>

      <div class="rc-model-header">
        <div class="rc-model-header-icon">🪜</div>
        <h3>Ramp Pricing — Step by Step</h3>
      </div>
      <div class="rc-model-body">
        <div class="rc-steps">
          <div class="rc-step">
            <div class="rc-step-num">1</div>
            <div class="rc-step-content">
              <h4>Navigate to Plans and create or edit a plan</h4>
              <p>Go to <strong>Configuration → Plans</strong> in the Admin Console. Click <strong>New Plan</strong> to create a ramp plan from scratch, or open an existing plan to add ramp pricing. Note that adding ramp pricing to a plan that already has active subscribers will only affect new subscriptions — existing subscribers keep their current terms.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-step-num">2</div>
            <div class="rc-step-content">
              <h4>Select "Ramp" as the pricing model</h4>
              <p>In the <strong>Pricing Model</strong> section of the plan form, choose <strong>Ramp</strong> from the dropdown. The form will expand to show ramp interval configuration. Fill in all other required plan fields — name, code, billing interval, trial settings — as you would for a standard plan.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-step-num">3</div>
            <div class="rc-step-content">
              <h4>Set the price for your first ramp interval</h4>
              <p>Enter the price you want to charge in the first billing period (or group of periods). This can be any amount — including <code>$0.00</code> for a free introductory period. Set the number of billing periods this price applies to before the next ramp kicks in. For example, a monthly plan might have a first ramp of 3 periods at $49/month before escalating.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-step-num">4</div>
            <div class="rc-step-content">
              <h4>Add additional ramp intervals</h4>
              <p>Click <strong>Add another ramp</strong> to define the next price point. Enter the new price and the number of periods it applies to. You can add up to 12 ramps on a single plan. The final ramp interval repeats indefinitely — so if a subscriber reaches the last ramp and renews, they continue at that final price until they cancel or you change the plan.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-step-num">5</div>
            <div class="rc-step-content">
              <h4>Save the plan and verify the ramp schedule</h4>
              <p>Save your plan and open it to review the ramp schedule. Verify the period counts and prices match your intent. Then test in sandbox mode by creating a subscription to this plan — you should see the first ramp price on the initial invoice. Use the <strong>Subscriptions — Ramp Pricing export</strong> under Reports → Exports to track subscriber progress through the ramp schedule once live.</p>
            </div>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Ramp pricing and auto-renew terms</strong>
          <p>The end-of-term behavior you configure (auto-renew or expire) does not alter the ramp schedule during the subscription's active term. The price changes at each ramp interval regardless of whether the subscription is set to auto-renew. This makes ramp pricing safe to combine with both term-based and evergreen subscription models.</p>
        </div>
      </div>
    </div>

    <!-- Model B: Hybrid Pricing -->
    <div class="rc-lp-section">
      <h2>🔀 Part B: Configure Hybrid Pricing</h2>
      <p>Hybrid pricing in Recurly isn't a separate plan type — it's the result of combining a fixed recurring plan price with one or more usage-based add-ons on the same plan. If you've completed the Usage Billing micro-path, you already know the add-on piece. This section focuses on the combination and what's specific to the hybrid architecture.</p>

      <div class="rc-model-header">
        <div class="rc-model-header-icon">🔀</div>
        <h3>Hybrid Pricing — Step by Step</h3>
      </div>
      <div class="rc-model-body">
        <div class="rc-steps">
          <div class="rc-step">
            <div class="rc-step-num">1</div>
            <div class="rc-step-content">
              <h4>Create or edit a plan with a fixed base price</h4>
              <p>Go to <strong>Configuration → Plans</strong> and create a new plan. Set the <strong>Pricing Model</strong> to <strong>Fixed</strong> and enter your base recurring price — this is what customers pay every billing cycle for platform access, regardless of usage. This base charge appears as its own line item on every invoice.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-step-num">2</div>
            <div class="rc-step-content">
              <h4>Add a usage-based add-on to the plan</h4>
              <p>Navigate to the plan's <strong>Add-Ons</strong> section and click <strong>Create Add-On</strong>. Set the type to <strong>Usage</strong>, assign or create a Measured Unit, and configure your usage pricing structure (per unit, tiered, volume, percentage). This add-on represents the variable component of the hybrid model — it only generates an invoice line item in periods where usage is logged.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-step-num">3</div>
            <div class="rc-step-content">
              <h4>Set the overage threshold (if applicable)</h4>
              <p>If you want to offer included usage within the base price before variable charges kick in, configure this as a <strong>free tier within the tiered pricing model</strong> on the usage add-on. For example: first 1,000 API calls at $0, then $0.001 per call beyond that. The base plan price covers access; the free usage tier covers a reasonable included allotment; the paid tiers capture the overage. This three-layer structure is the core of most SaaS hybrid models.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-step-num">4</div>
            <div class="rc-step-content">
              <h4>Test the hybrid invoice flow in sandbox</h4>
              <p>Create a test subscription to this plan in sandbox mode. Log some usage records via the API — both below and above your included tier threshold — then advance the billing cycle to see how Recurly generates the invoice. Confirm the base charge and usage line item both appear correctly. Pay attention to how the invoice communicates the usage breakdown to the customer; this is what they'll receive in production.</p>
            </div>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Multiple usage add-ons on one plan</strong>
          <p>A single plan can carry multiple usage add-ons, each with its own measured unit and pricing structure. This is how you bill for several independent resource types — for example, a plan that charges for both API calls and GB stored. Each add-on produces a separate line item on the invoice, giving customers clear visibility into what drove their variable charges.</p>
        </div>
      </div>
    </div>

    <!-- Model C: Prepaid Account Balance -->
    <div class="rc-lp-section">
      <h2>💰 Part C: Configure Prepaid Account Balance</h2>
      <p>Prepaid Account Balance works differently from the other two models — it's not configured on a plan, but on an individual customer account. The customer purchases a credit balance, Recurly collects the payment immediately, and future charges draw from that balance rather than triggering new transactions. There are no transaction fees when a purchase is funded from an account balance.</p>

      <div class="rc-model-header">
        <div class="rc-model-header-icon">💰</div>
        <h3>Prepaid Account Balance — Step by Step</h3>
      </div>
      <div class="rc-model-body">
        <div class="rc-steps">
          <div class="rc-step">
            <div class="rc-step-num">1</div>
            <div class="rc-step-content">
              <h4>Navigate to the customer's account</h4>
              <p>In the Admin Console, go to <strong>Customers → Accounts</strong> and open the account for the customer you want to add a prepaid balance to. The customer must have a valid payment method on file — the prepaid purchase is a real transaction that charges their card or payment instrument.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-step-num">2</div>
            <div class="rc-step-content">
              <h4>Create a Prepaid Account Balance charge</h4>
              <p>Within the account, click <strong>Add Charge</strong> (or the equivalent action in the Account Actions menu). Set the <strong>Charge Type</strong> to <strong>Prepaid Account Balance</strong>. Enter the credit amount you are loading — this is the dollar value the customer is prepaying. Preview the charge before confirming to make sure the amount and payment method are correct.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-step-num">3</div>
            <div class="rc-step-content">
              <h4>Process the prepayment</h4>
              <p>Confirm and submit the charge. If the transaction succeeds, the credit amount is immediately added to the account balance and appears in the account's <strong>Account Balance</strong> field. For <strong>ACH and direct debit</strong> payment methods, note that the balance is not funded until Recurly receives a successful transaction notification — which can take several business days. Card payments fund the balance immediately upon authorization.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-step-num">4</div>
            <div class="rc-step-content">
              <h4>Verify balance draws on future invoices</h4>
              <p>When this account's next invoice is generated — for a subscription renewal, a one-time charge, or any other purchase — Recurly will automatically apply the available account balance before charging the payment method. The invoice will show the balance credit as a line item. Any invoice amount beyond the available balance will be charged to the payment method on file. You can also apply a balance to a past-due invoice manually from the invoice view in the Admin Console.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-step-num">5</div>
            <div class="rc-step-content">
              <h4>For programmatic prepaid top-ups — use the API</h4>
              <p>If your platform needs to load prepaid balances automatically — for example, when a customer purchases a credit bundle through your own checkout — use the Recurly v3 API. Create a Purchase request with a line item where <code>origin</code> is set to <code>"prepayment"</code>. For v2 API, use a charge adjustment with <code>origin: "prepayment"</code>. This approach is preferred for high-volume or self-serve credit bundle purchasing flows.</p>
            </div>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-caution">
        <div class="rc-callout-icon">🚫</div>
        <div class="rc-callout-body">
          <strong>Prepaid balances cannot be refunded once consumed</strong>
          <p>Refunds are only possible for the unused portion of a prepaid balance. Once credit has been applied to an invoice, it cannot be reversed through a standard refund workflow. Communicate this clearly in your terms of service and prepaid purchase confirmation flow so customers understand the commitment they're making.</p>
        </div>
      </div>
    </div>

    <!-- Path navigation -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models" class="rc-btn-prev">← Overview</a>
      <span class="rc-lp-nav-indicator">2 of 3</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models-strategy" class="rc-btn-path">Next: Strategy &amp; Best Practices →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/docs/ramp-pricing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Ramp Pricing</a>
        <a href="https://docs.recurly.com/docs/hybrid-pricing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Hybrid Pricing</a>
        <a href="https://docs.recurly.com/docs/prepaid-account-balance" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Prepaid Account Balance</a>
        <a href="https://docs.recurly.com/docs/subscription-ramp-pricing-export" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Ramp Pricing Export</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/usage-based-billing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Usage-Based Billing</a>
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
