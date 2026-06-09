---
title: 'Advanced Analytics: Overview'
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

/* Sections */
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
.rc-card-grid-3col { grid-template-columns: 1fr 1fr 1fr; }
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

/* Accent card */
.rc-accent-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 20px 0; }
.rc-accent-card.rc-accent-yellow { border-left: 4px solid var(--yellow); }
.rc-accent-card.rc-accent-orange { border-left: 4px solid var(--orange); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 12px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-accent-card ul { font-size: .9rem; color: var(--gray); line-height: 1.75; padding-left: 20px; margin: 0; }
.rc-accent-card ul li { margin-bottom: 4px; }
.rc-accent-card ul li strong { color: var(--darkgray); }

/* Compare table */
.rc-compare-table { width: 100%; border-collapse: collapse; margin: 0 0 32px; font-size: .88rem; border-radius: 12px; overflow: hidden; border: 1px solid var(--lightgray); }
.rc-compare-table thead tr { background: var(--offblack); }
.rc-compare-table thead th { padding: 14px 18px; text-align: left; font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: var(--yellow); }
.rc-compare-table thead th:first-child { width: 30%; }
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
  .rc-card-grid, .rc-card-grid.rc-card-grid-3col { grid-template-columns: 1fr; }
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

    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>Upcoming:</strong> Join our CSMs for a live P&amp;P strategy session.
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- Hero -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Pricing &amp; Plans 201
      </div>
      <div class="rc-lp-hero-title"><h1>Advanced analytics</h1></div>
      <p>You've built a sophisticated pricing and packaging portfolio. Now learn how to measure whether it's working — what Recurly shows you natively, and where the gaps require external tooling.</p>
     
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
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Overview
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics-configure" class="rc-sticky-link">
              <span class="rc-step-badge">2</span> Where to Find It
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics-strategy" class="rc-sticky-link">
              <span class="rc-step-badge">3</span> Strategy &amp; Best Practices
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-sticky-link">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- Section 1: What Analytics Means for P&P -->
    <div class="rc-lp-section">
      <h2>📊 Analytics as a Pricing Feedback Loop</h2>
      <p>A pricing and packaging strategy isn't something you set once. It's something you test, observe, and adjust. The advanced pricing portfolio you've built through P&P 201 — segmented plans, usage-based add-ons, ramp pricing, multi-currency markets — only improves if you have visibility into how each component is performing. Analytics is what closes the loop.</p>
      <p>The right question isn't "how do I access Recurly's analytics?" — it's "what do I need to know to make better pricing decisions, and where does that data live?" Some of it lives natively in Recurly. Some of it requires piping Recurly exports into external tools. Knowing which is which before you start building dashboards will save you significant rework.</p>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Analytics permission required</strong>
          <p>Access to Recurly Analytics dashboards requires the <strong>Analytics</strong> user role. If you or your team members can't see the Analytics section in the Admin Console, a site administrator will need to grant this permission under <strong>Users</strong> in your site settings.</p>
        </div>
      </div>
    </div>

    <!-- Section 2: What Recurly Provides Natively -->
    <div class="rc-lp-section">
      <h2>🔧 What Recurly Analytics Provides Natively</h2>
      <p>Recurly Analytics covers the financial and subscription lifecycle metrics that matter most for a general subscription business. For a P&P-focused operator, these are the dashboards you'll use most regularly.</p>

      <div class="rc-stat-strip">
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">10+</div>
          <div class="rc-stat-tile-label">Native dashboards</div>
          <div class="rc-stat-tile-context">Recurly Analytics includes dashboards for MRR, billings, subscriber retention, churn, trials, dunning effectiveness, recovered revenue, LTV, and more — all included with any Recurly subscription plan.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">Plan-level</div>
          <div class="rc-stat-tile-label">MRR visibility</div>
          <div class="rc-stat-tile-context">The MRR by Plan dashboard shows which plans generate the most MRR, the net impact of new subscriptions, expansions, and churn per plan, and lets you drill down to account-level specifics. This is the P&P operator's primary financial dashboard.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">Cohort</div>
          <div class="rc-stat-tile-label">Retention analysis</div>
          <div class="rc-stat-tile-context">The Subscriber Retention dashboard uses cohort analysis to show paid subscriber retention rates over time — how long customers stay subscribed based on when they signed up. Essential for comparing retention across plans and pricing models.</div>
        </div>
      </div>

      <div class="rc-card-grid rc-card-grid-3col">
        <div class="rc-feature-card">
          <div class="rc-feature-icon">💹</div>
          <h4>MRR &amp; ARR Dashboards</h4>
          <p>Total MRR with full growth decomposition: new business, expansion, contraction, churn, and reactivation. Drill down by plan with the MRR by Plan view. Toggle between discount and failed invoice settings for accurate reporting.</p>
          <span class="rc-feature-tag">Core financial</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">👥</div>
          <h4>Subscriber Retention</h4>
          <p>Cohort-based retention analysis showing how long subscribers stay on each cohort and whether activation month affects long-term retention. The closest native equivalent to a plan-level churn comparison.</p>
          <span class="rc-feature-tag">Retention</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🧪</div>
          <h4>Trial Performance</h4>
          <p>Trial conversion rates, trial durations, and conversion trends over time. Critical for evaluating whether your trial design is working — and whether free-tier usage billing is converting as expected.</p>
          <span class="rc-feature-tag">Acquisition</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">📉</div>
          <h4>Churn Analytics</h4>
          <p>Breakdown of churn by reason — voluntary, involuntary (payment failure), and by subscription status. Helps distinguish pricing-driven churn from payment-failure churn, which have very different remediation strategies.</p>
          <span class="rc-feature-tag">Retention</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🔄</div>
          <h4>Dunning Effectiveness</h4>
          <p>Tracks how well your dunning workflow is recovering failed payments — recovery rates, timing, and revenue recovered. Connects to MRR "in dunning" to show at-risk revenue currently in the recovery cycle.</p>
          <span class="rc-feature-tag">Recovery</span>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">📐</div>
          <h4>Benchmarking</h4>
          <p>Compare your performance metrics against industry standards for your sector. Enable benchmarking in Analytics Settings to see how your churn rate, LTV, and MRR growth compare to peers. Percentile data loads within one business day after enabling.</p>
          <span class="rc-feature-tag">Context</span>
        </div>
      </div>
    </div>

    <!-- Section 3: What Recurly Doesn't Provide -->
    <div class="rc-lp-section">
      <h2>⚠️ Where Recurly's Native Analytics Fall Short</h2>
      <p>For a P&P 201 operator running a sophisticated portfolio, several critical analytics questions can't be answered in Recurly's native dashboards. These gaps aren't bugs — they're deliberate scope decisions. But you need to know about them before you design your analytics stack.</p>

      <table class="rc-compare-table">
        <thead>
          <tr>
            <th>P&P 201 topic</th>
            <th>What Recurly shows natively</th>
            <th>What requires external tooling</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Segmentation (MP7)</td>
            <td>Plan-level MRR and subscriber counts</td>
            <td>Per-segment performance, conversion rates by segment code, price segment A/B test results — requires joining segment codes from your subscription API data with your own analytics store</td>
          </tr>
          <tr>
            <td>Account Hierarchy (MP8)</td>
            <td>Individual account metrics</td>
            <td>Rolled-up MRR across parent/child account groups, hierarchy-level churn, consolidated billing analytics — not available in native dashboards</td>
          </tr>
          <tr>
            <td>Usage Billing (MP9)</td>
            <td>Invoice totals (which include usage charges)</td>
            <td>Usage trends per account, usage-to-paid conversion, tier distribution, consumption patterns — the Usage Records export is your only Recurly data source; analysis happens externally</td>
          </tr>
          <tr>
            <td>Advanced Models (MP10)</td>
            <td>MRR by plan (includes ramp and hybrid plans)</td>
            <td>Ramp lifecycle position (which subscribers are at which interval), churn rates at ramp escalation points, prepaid balance draw-down rates — requires the Ramp Pricing export and external analysis</td>
          </tr>
          <tr>
            <td>Advanced Currency (MP11)</td>
            <td>Total MRR across all currencies (in your base currency)</td>
            <td>Per-currency conversion rates, subscriber counts by currency, churn rates by market, MRR broken out by currency — requires external analysis of subscription export data</td>
          </tr>
        </tbody>
      </table>

      <div class="rc-callout rc-callout-caution">
        <div class="rc-callout-icon">🚨</div>
        <div class="rc-callout-body">
          <strong>Build your external analytics pipeline before these gaps become blind spots</strong>
          <p>The P&P features you've configured throughout this series generate data that Recurly stores but doesn't natively surface in dashboards. If you haven't set up an external analytics pipeline — even a simple one — you're operating your pricing portfolio without the visibility needed to optimize it. The Configure page shows exactly which exports to pull and what questions each one answers.</p>
        </div>
      </div>
    </div>

    <!-- Path nav -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency" class="rc-btn-prev">← Advanced Currency</a>
      <span class="rc-lp-nav-indicator">1 of 3</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics-configure" class="rc-btn-path">Next: Where to Find It →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-analytics-overview" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Analytics Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/mmr-by-plan" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: MRR by Plan</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/data-imports-and-exports" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Data Exports</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Join Global Office Hours</a>
      </div>
    </div>

    <!-- Footer -->
    <div class="rc-footer-nav">
      <div class="rc-footer-section">
        <span class="rc-footer-section-label">Advanced Analytics:</span>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics" class="rc-footer-link">Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics-configure" class="rc-footer-link">Where to Find It</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics-strategy" class="rc-footer-link">Strategy &amp; Best Practices</a>
      </div>
      <div class="rc-footer-section">
        <span class="rc-footer-section-label">P&amp;P 201:</span>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-footer-link">P&amp;P 201 Hub</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-segmentation" class="rc-footer-link">Segmentation</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-footer-link">Account Hierarchy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-footer-link">Usage Billing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models" class="rc-footer-link">Advanced Models</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency" class="rc-footer-link">Advanced Currency</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics" class="rc-footer-link">Advanced Analytics</a>
      </div>
      <div class="rc-footer-utility">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Navigate Home
        </a>
        <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
