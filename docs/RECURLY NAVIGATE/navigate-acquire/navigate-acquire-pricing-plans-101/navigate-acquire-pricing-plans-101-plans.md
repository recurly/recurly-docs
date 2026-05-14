---
title: Plans overview
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
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: #0D0D0B; background-size: cover;
  color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0;
}
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

/* Nav — static, open by default, Acquire yellow */
details.rc-sticky-nav-wrap {
  position: static;
  background-color: var(--yellow);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px; border-radius: 12px;
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
.rc-sticky-link { color: var(--offblack) !important; text-decoration: none !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; }
.rc-sticky-link:hover { background: var(--offblack); color: var(--yellow) !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-sticky-link-active { background: rgba(0,0,0,0.12); font-weight: 800; }
.rc-sticky-link-active:hover { background: var(--offblack); color: var(--yellow) !important; }

/* Nav divider label */
.rc-nav-divider { font-size: .68rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; color: rgba(0,0,0,0.35); padding: 7px 10px; align-self: center; white-space: nowrap; }

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

/* Two-truths comparison table */
.rc-compare-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-compare-card { border-radius: 12px; padding: 24px; border: 1px solid var(--lightgray); background: var(--offwhite); }
.rc-compare-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 16px; display: flex; align-items: center; gap: 8px; }
.rc-compare-card ul { list-style: none; padding: 0; margin: 0; display: flex; flex-direction: column; gap: 10px; }
.rc-compare-card ul li { font-size: .88rem; color: var(--darkgray); line-height: 1.5; padding-left: 20px; position: relative; }
.rc-compare-card ul li::before { content: '→'; position: absolute; left: 0; color: var(--yellow); font-weight: 800; font-size: .8rem; }
.rc-compare-label { display: inline-block; font-size: .68rem; font-weight: 800; letter-spacing: .8px; text-transform: uppercase; padding: 3px 10px; border-radius: 20px; margin-bottom: 14px; }
.rc-compare-label-monthly { background: rgba(255,215,6,0.15); color: #7a6500; }
.rc-compare-label-annual { background: rgba(13,13,11,0.08); color: var(--offblack); }

/* Path nav buttons */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-btn-start { background: var(--brightgray); color: var(--gray); padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid var(--lightgray); cursor: default; display: inline-flex; align-items: center; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Resources */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--yellow); border-radius: 10px; padding: 20px 24px; margin: 48px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FFD706 !important; }

/* Footer */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 32px; margin-top: 32px; text-align: center; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-wrap: wrap; gap: 24px; justify-content: center; align-items: center; }
.rc-footer-link { color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .9rem; transition: color .2s; display: inline-flex; align-items: center; gap: 5px; }
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
  .rc-card-grid { grid-template-columns: 1fr; }
  .rc-compare-grid { grid-template-columns: 1fr; }
  .rc-stat-strip { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-back-link">← Back to Course Start</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Announcement bar -->
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
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire
      </div>
      <div class="rc-lp-hero-title"><h4><strong>COURSE:</strong> PRICING & PLANS 101</H4><h1>Plans: Overview</h1></div>
      <p>Your plan is more than a billing configuration — it's the first value message your subscriber sees. Learn what makes a plan portfolio work and why one plan is never enough.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">78%</div>
          <div class="rc-hero-stat-label">of merchants now offer both monthly &amp; annual</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">50–60%</div>
          <div class="rc-hero-stat-label">more revenue per user on annual plans</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">52%</div>
          <div class="rc-hero-stat-label">of subscribers cancel within the first year</div>
        </div>
      </div>
    </div>

    <!-- Nav — static, open, Plans Overview active -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">P&amp;P 101 · Plans <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-sticky-link">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> P&amp;P 101
            </a>
            <span class="rc-nav-divider">Plans:</span>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-sticky-link rc-sticky-link-active"><span class="rc-step-badge">1</span> Overview</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-configure" class="rc-sticky-link"><span class="rc-step-badge">2</span> Configure</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-strategy" class="rc-sticky-link"><span class="rc-step-badge">3</span> Strategy &amp; BP</a>
            <span class="rc-nav-divider">Series:</span>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-sticky-link">Add-Ons</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-sticky-link">Currency</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-sticky-link">Pricing Models</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-sticky-link">Trials</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-sticky-link">Analytics</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- What is a plan -->
    <div class="rc-lp-section" id="what-is-a-plan">
      <h2>🧱 What is a plan in Recurly?</h2>
      <p>A plan is the foundational billing object in Recurly. Every subscription you create is tied to a plan — it defines how much you charge, how often you charge it, and what happens at renewal. Think of it as the blueprint for a subscriber's entire billing lifecycle.</p>
      <p>But here's what matters most for acquisition: <strong>your plan isn't just a billing configuration — it's the offer your prospective subscriber evaluates before they buy.</strong> The name they read, the price they see, the commitment they're being asked to make — all of that is determined by how you've built your plans.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🔁</div>
          <h4>Recurring billing engine</h4>
          <p>Plans define your billing interval (weekly, monthly, quarterly, annual), total billing cycles, and what happens at term end — auto-renew or expire.</p>
          <span class="rc-feature-tag">Foundation</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">💰</div>
          <h4>Pricing model container</h4>
          <p>Each plan carries a pricing model — Fixed, Ramp, or Usage-based. The model you choose shapes how subscribers perceive value over time.</p>
          <span class="rc-feature-tag">Pricing</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🧩</div>
          <h4>Add-on anchor</h4>
          <p>Add-ons are attached at the plan level. Your plan structure determines which upsells and extras are available to each subscriber segment.</p>
          <span class="rc-feature-tag">Packaging</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🎯</div>
          <h4>Dunning campaign assignment</h4>
          <p>Each plan can be assigned its own dunning campaign. This means your payment recovery strategy can be tailored to the billing behavior of each plan type.</p>
          <span class="rc-feature-tag">Recovery</span>
        </div>
      </div>
    </div>

    <!-- Monthly vs annual framework -->
    <div class="rc-lp-section" id="monthly-vs-annual">
      <h2>⚖️ The two-truths framework: Monthly vs. Annual</h2>
      <p>The 2026 State of Subscriptions report surfaces a critical insight about plan design: monthly and annual plans are not better or worse than each other — they serve fundamentally different purposes in your subscriber lifecycle. The merchants winning at acquisition are using both, not choosing between them.</p>

      <div class="rc-stat-strip">
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">82.9%</div>
          <div class="rc-stat-tile-label">Annual Renewal Rate</div>
          <div class="rc-stat-tile-context">Annual plans renew at a lower rate than monthly — but the subscribers who do renew generate 50–60% more revenue per user over their lifetime.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">53%</div>
          <div class="rc-stat-tile-label">Monthly Recovery Rate</div>
          <div class="rc-stat-tile-context">Monthly plans are more recoverable when payments fail — more frequent billing cycles give you more chances to recover a declined charge.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">23.3%</div>
          <div class="rc-stat-tile-label">Annual Failed Renewal Recovery</div>
          <div class="rc-stat-tile-context">Only about 1 in 4 failed annual renewals are recovered — making the pre-renewal period your most important retention moment.</div>
        </div>
      </div>

      <div class="rc-compare-grid">
        <div class="rc-compare-card">
          <div class="rc-compare-label rc-compare-label-monthly">Monthly</div>
          <h4>📅 The acquisition engine</h4>
          <ul>
            <li>Lower commitment — easier for new subscribers to say yes</li>
            <li>Higher volatility — early-cycle churn is more common</li>
            <li>More recoverable when payments fail (53% recovery rate)</li>
            <li>Best used as your entry-tier to build usage and trust</li>
            <li>Migrate engaged monthly subscribers to annual for LTV gains</li>
          </ul>
        </div>
        <div class="rc-compare-card">
          <div class="rc-compare-label rc-compare-label-annual">Annual</div>
          <h4>📈 The retention anchor</h4>
          <ul>
            <li>Higher commitment — requires a subscriber who already sees value</li>
            <li>50–60% more revenue per user over the subscription lifetime</li>
            <li>Renewal moment is high-risk — pre-renewal communication is essential</li>
            <li>Lower recovery on failed renewals (23.3% vs 53% for monthly)</li>
            <li>Best offered selectively to engaged, high-LTV subscribers</li>
          </ul>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>The playbook: use monthly to acquire, annual to retain</strong>
          <p>Lead with monthly as your default acquisition tier. When a subscriber hits engagement milestones — consistent usage, feature adoption, support interactions — that's your trigger to offer an annual upgrade. You're not just saving revenue; you're locking in a subscriber who's already proven they find value.</p>
        </div>
      </div>
    </div>

    <!-- Why one plan isn't enough -->
    <div class="rc-lp-section" id="portfolio">
      <h2>🚫 Why a single plan is a growth ceiling</h2>
      <p>If your business has only one plan, every subscriber is making a binary decision: buy this, or don't. You've removed the middle ground — the lower-commitment entry points, the premium upgrade path, the different billing cadence that might work better for a different segment.</p>
      <p>The data backs this up. Across all industries, <strong>71% of merchants offer both monthly and annual plans</strong>. In Software and Education — two of the highest-LTV verticals — that number climbs to 76–80%. These merchants aren't offering multiple plans because it's more complex to manage. They're doing it because plan diversity directly drives acquisition and retention.</p>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon">⚠️</div>
        <div class="rc-callout-body">
          <strong>The 70% signal</strong>
          <p>If 70% or more of your active subscribers are on your cheapest plan, that's a value perception problem — not a pricing success. It means your higher tiers aren't communicating enough incremental value. This series will help you address that through plan design, add-ons, and analytics.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-caution">
        <div class="rc-callout-icon">🔶</div>
        <div class="rc-callout-body">
          <strong>But don't overcorrect with too many tiers</strong>
          <p>Research consistently shows that 3–4 plan tiers (Good / Better / Best / Enterprise) is the sweet spot. Beyond that, decision paralysis sets in and conversion drops. More plans isn't better — more <em>intentional</em> plans is better.</p>
        </div>
      </div>
    </div>

    <!-- Path nav -->
    <div class="rc-lp-nav">
      <span class="rc-btn-start">Start</span>
      <span class="rc-lp-nav-indicator">1 of 3 · Plans</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-configure" class="rc-btn-path">Next: How to Configure →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Plans</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/billing-models" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Pricing Models</a>
        <a href="https://recurly.com/research/saas-benchmarks-for-subscription-plans/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📊 SaaS Plan Benchmarks</a>
        <a href="https://recurly.com/blog/subscription-pricing-strategy-playbook/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📝 Pricing Strategy Playbook</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Support</a>
      </div>
    </div>

    <!-- Footer -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
          <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-footer-link">P&amp;P 101</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-footer-link">Plans: Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-configure" class="rc-footer-link">Plans: Configure</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-strategy" class="rc-footer-link">Plans: Strategy &amp; BP</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-footer-link">Add-Ons</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-footer-link">Currency</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-footer-link">Pricing Models</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-footer-link">Trials</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-footer-link">Analytics</a>
        <a href="mailto:support@recurly.com" class="rc-footer-link">support@recurly.com</a>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
