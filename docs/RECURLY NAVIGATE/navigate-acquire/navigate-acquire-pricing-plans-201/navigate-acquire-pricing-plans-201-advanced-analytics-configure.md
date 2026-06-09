---
title: 'Advanced Analtyics: Configuration'
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

/* Video card */
.rc-video-card { border: 1px solid var(--lightgray); border-radius: 14px; overflow: hidden; margin: 0 0 40px; }
.rc-video-header { background: var(--offblack); padding: 16px 22px; display: flex; align-items: center; gap: 10px; }
.rc-video-header h4 { font-size: .88rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: var(--yellow); margin: 0; }
.rc-video-header span { font-size: .78rem; color: var(--lightgray); margin-left: auto; }
.rc-video-embed { position: relative; overflow: hidden; aspect-ratio: 16/9; background: var(--offblack); }
.rc-video-embed iframe { position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; }
.rc-video-caption { padding: 12px 22px; font-size: .83rem; color: var(--gray); background: var(--brightgray); border-top: 1px solid var(--lightgray); line-height: 1.5; }

/* Steps */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 20px 0 0; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0 0 8px; }
.rc-step-content p:last-child { margin-bottom: 0; }
.rc-step-content strong { color: var(--darkgray); }
.rc-step-content a { color: var(--orange); font-weight: 600; text-decoration: none !important; }
.rc-guide .rc-step-content a:hover { text-decoration: underline !important; }
.rc-step-content code { background: var(--brightgray); color: var(--offblack); padding: 2px 7px; border-radius: 4px; font-size: .82rem; font-family: monospace; }

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

/* Export reference table */
.rc-export-table { width: 100%; border-collapse: collapse; margin: 20px 0 32px; font-size: .88rem; border-radius: 12px; overflow: hidden; border: 1px solid var(--lightgray); }
.rc-export-table thead tr { background: var(--offblack); }
.rc-export-table thead th { padding: 13px 16px; text-align: left; font-size: .73rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: var(--yellow); }
.rc-export-table thead th:first-child { width: 28%; }
.rc-export-table tbody tr { border-bottom: 1px solid var(--brightgray); }
.rc-export-table tbody tr:last-child { border-bottom: none; }
.rc-export-table tbody tr:nth-child(even) { background: var(--offwhite); }
.rc-export-table tbody tr:nth-child(odd) { background: #fff; }
.rc-export-table tbody td { padding: 11px 16px; color: var(--darkgray); line-height: 1.5; vertical-align: top; font-size: .86rem; }
.rc-export-table tbody td:first-child { font-weight: 700; color: var(--offblack); }

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
  .rc-export-table { font-size: .8rem; }
  .rc-export-table thead th, .rc-export-table tbody td { padding: 9px 10px; }
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
      <div class="rc-lp-hero-title"><h1>Analytics: Where to find it</h1></div>
      <p>Where each analytics question lives — native Recurly dashboards, the exports library, and what to pull for each P&P 201 topic you've configured.</p>
     
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
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics" class="rc-sticky-link">
              <span class="rc-step-badge">1</span> Overview
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics-configure" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Where to Find It
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

    <!-- Video -->
    <div class="rc-lp-section">
      <h2>📹 Trail Guide Walkthrough</h2>
      <div class="rc-video-card">
        <div class="rc-video-header">
          <h4>Navigating Recurly Analytics for P&amp;P Operators</h4>
          <span>~6 min</span>
        </div>
        <div class="rc-video-embed">
          <iframe src="about:blank" loading="lazy" title="Recurly Analytics for P&P Operators Walkthrough" allowfullscreen allow="encrypted-media; fullscreen; microphone; screen-wake-lock;"></iframe>
        </div>
        <div class="rc-video-caption">This walkthrough covers the MRR by Plan dashboard, Subscriber Retention cohort analysis, the exports library, and how to set up an automated export for ongoing analytics.</div>
      </div>
    </div>

    <!-- Section: Native Dashboards -->
    <div class="rc-lp-section">
      <h2>📈 Navigating the Analytics Dashboard</h2>
      <p>Recurly Analytics is accessible from the left navigation in your Admin Console under <strong>Analytics</strong>. The section requires the Analytics user role — confirm this permission is active for anyone on your team who needs access. Here's a tour of the dashboards most relevant to P&P decision-making.</p>

      <div class="rc-steps">

        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>MRR &amp; ARR — your top-line financial pulse</h4>
            <p>Navigate to <strong>Analytics → Monthly Recurring Revenue</strong>. The dashboard shows total MRR with a growth decomposition: new subscriptions, expansions (upgrades and add-on additions), contractions (downgrades), churn, and reactivations. Each component is clickable — drill into any category to see the individual accounts and subscriptions driving that movement. The <strong>MRR by Plan</strong> sub-view is the most useful tool for P&P operators: it shows exactly which plans are generating revenue and how net MRR is shifting across your catalog.</p>
          </div>
        </div>

        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Subscriber Retention — cohort-level retention and churn</h4>
            <p>Navigate to <strong>Analytics → Subscriber Retention</strong>. This cohort analysis shows, for each month of subscriber activation, what percentage of that cohort was still subscribed at 1 month, 3 months, 6 months, and so on. This is the closest native view to a plan-by-plan churn comparison — you can identify whether newer cohorts are retaining better than older ones, and whether seasonal patterns exist in your churn. It doesn't filter by plan natively, but you can combine this view with the MRR by Plan data to triangulate retention differences across plan types.</p>
          </div>
        </div>

        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Trial Performance — acquisition top of funnel</h4>
            <p>Navigate to <strong>Analytics → Trials</strong>. This dashboard tracks trial activation counts, trial-to-paid conversion rates, and conversion trends over time. For P&P operators running free-tier usage plans or time-limited trials, this is the primary indicator of whether your acquisition pricing is converting. Watch for changes in conversion rate when you adjust plan prices, trial lengths, or usage tier thresholds — those correlations are your pricing signal.</p>
          </div>
        </div>

        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Churn Analytics — understanding what's driving exits</h4>
            <p>Navigate to <strong>Analytics → Churn</strong>. This dashboard breaks churn down by reason: voluntary cancellation, involuntary (payment failure), and by subscription status at the time of churn. For P&P operators, the key distinction is between voluntary churn (a pricing or product problem) and involuntary churn (a payment collection problem). If involuntary churn is high, that's a dunning and payment retry problem, not a pricing problem — and the remediation is completely different.</p>
          </div>
        </div>

        <div class="rc-step">
          <div class="rc-step-num">5</div>
          <div class="rc-step-content">
            <h4>Analytics Settings — configure benchmarking and MRR calculation</h4>
            <p>Navigate to <strong>Analytics → Settings</strong> (or via the gear icon in the analytics section). Two key settings matter here. First, <strong>Industry Benchmarking</strong>: enable this and select your industry category to unlock comparison metrics against peer companies. Benchmark percentiles activate within one business day. Second, <strong>Failed Charges in MRR</strong>: you can choose whether to include or exclude revenue from failed recurring charges in your MRR calculation — excluding them gives a more conservative view of actual collected revenue.</p>
          </div>
        </div>

      </div>
    </div>

    <!-- Section: The Exports Library -->
    <div class="rc-lp-section">
      <h2>📦 The Exports Library — Your P&P Data Source</h2>
      <p>Exports are available under <strong>Reports → Exports</strong> in the Admin Console. You can run exports on demand or configure automated scheduled exports. Each export is a CSV file covering a specific data category. For P&P analytics that can't be answered in native dashboards, exports are your data source.</p>

      <table class="rc-export-table">
        <thead>
          <tr>
            <th>Export name</th>
            <th>What it contains</th>
            <th>Key P&P 201 use case</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Subscriptions</td>
            <td>Every subscription with plan code, status, price, currency, start date, trial dates, segment code, account code</td>
            <td>Plan distribution, segment performance analysis, currency breakdown, trial cohort analysis, ramp plan identification</td>
          </tr>
          <tr>
            <td>Subscriptions — Ramp Pricing</td>
            <td>Ramp interval-level data for every subscription on a ramp plan — current interval, price, and period counts</td>
            <td>Tracking which subscribers are at which ramp stage, churn analysis at escalation points, ramp completion rates</td>
          </tr>
          <tr>
            <td>Subscriptions — Usage Records</td>
            <td>Every usage record logged across all usage-based add-ons, with subscription UUID, add-on code, quantity, and timestamp</td>
            <td>Usage trend analysis per account, tier distribution, usage-to-revenue reconciliation, at-risk account identification</td>
          </tr>
          <tr>
            <td>Accounts</td>
            <td>All account records with account code, parent account code, acquisition data, billing addresses</td>
            <td>Account hierarchy structure for rollup analysis, segment code attribution, multi-currency subscriber counts by country</td>
          </tr>
          <tr>
            <td>Invoices</td>
            <td>All invoices with line items, currency, subtotals, tax, discounts, status</td>
            <td>Revenue by currency, add-on revenue attribution, ramp-period revenue tracking, hybrid billing breakdown</td>
          </tr>
          <tr>
            <td>Adjustments</td>
            <td>Every charge and credit adjustment, including add-on charges and coupon credits</td>
            <td>Add-on adoption rates, coupon effectiveness, usage overage revenue breakdown</td>
          </tr>
          <tr>
            <td>Transactions</td>
            <td>All payment transactions with gateway, currency, amount, status, and failure reason</td>
            <td>Multi-currency payment performance, gateway success rates by currency, involuntary churn root cause analysis</td>
          </tr>
        </tbody>
      </table>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">⏱️</div>
        <div class="rc-callout-body">
          <strong>Set up scheduled exports before you need them</strong>
          <p>You can configure exports to run automatically on a recurring schedule — daily, weekly, or monthly — and deliver the file to a specified destination. The most valuable habit is setting up daily Subscriptions and Usage Records exports to feed into your external analytics pipeline. Retroactive analysis is possible, but gaps in export cadence create gaps in trend data. Start the schedule before you go live in production.</p>
        </div>
      </div>
    </div>

    <!-- Section: P&P Analytics Map -->
    <div class="rc-lp-section">
      <h2>🗺️ The P&P 201 Analytics Map</h2>
      <p>A quick reference for where to find the data for each P&P 201 topic — native dashboard, export, or external tooling.</p>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Segmentation (MP7) — Price segments and A/B testing</h4>
        <ul>
          <li><strong>Native:</strong> MRR by Plan shows plan-level revenue — but not segment-level breakdowns within a plan.</li>
          <li><strong>Export:</strong> Subscriptions export includes <code>plan_code</code> and segment data — join to your own system to compare segment conversion, churn, and LTV.</li>
          <li><strong>External required for:</strong> Per-segment trial conversion, churn comparison between segment cohorts, A/B pricing test analysis.</li>
        </ul>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Account Hierarchy (MP8) — Parent and child account analytics</h4>
        <ul>
          <li><strong>Native:</strong> No hierarchy-level rollup in native dashboards — individual account metrics only.</li>
          <li><strong>Export:</strong> Accounts export includes parent account codes. Join with Subscriptions export to calculate hierarchy-level MRR, subscriber counts, and churn.</li>
          <li><strong>External required for:</strong> Rolled-up revenue by parent account, enterprise account health scoring, hierarchy-level churn analysis.</li>
        </ul>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Usage Billing (MP9) — Consumption and usage patterns</h4>
        <ul>
          <li><strong>Native:</strong> Usage charges appear in invoice totals and the Adjustments export. No trend charts or per-account usage views.</li>
          <li><strong>Export:</strong> Subscriptions — Usage Records export is the primary data source. Contains every logged usage record with quantity, timestamp, add-on code, and subscription UUID.</li>
          <li><strong>External required for:</strong> Usage trends per account, at-risk account flagging, tier distribution analysis, free-tier conversion tracking.</li>
        </ul>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Advanced Models (MP10) — Ramp lifecycle and prepaid balance</h4>
        <ul>
          <li><strong>Native:</strong> Ramp plan subscriptions appear in MRR by Plan. No ramp-interval breakdown in native dashboards.</li>
          <li><strong>Export:</strong> Subscriptions — Ramp Pricing export shows current ramp interval, price, and period counts per subscription. Invoices export shows prepaid balance applications.</li>
          <li><strong>External required for:</strong> Churn rates at ramp escalation points, ramp completion percentages, prepaid balance utilization rates, renewal behavior after ramp completion.</li>
        </ul>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Advanced Currency (MP11) — Multi-currency market performance</h4>
        <ul>
          <li><strong>Native:</strong> MRR is reported in your base currency (all currencies converted). No native per-currency MRR breakdown.</li>
          <li><strong>Export:</strong> Subscriptions export includes currency code. Invoices export includes the invoiced currency and amounts. Join both for per-currency subscriber counts and revenue.</li>
          <li><strong>External required for:</strong> Conversion rates by currency/market, churn rates per market, MRR by currency for FX-adjusted revenue reporting.</li>
        </ul>
      </div>
    </div>

    <!-- Path nav -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics" class="rc-btn-prev">← Overview</a>
      <span class="rc-lp-nav-indicator">2 of 3</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics-strategy" class="rc-btn-path">Next: Strategy &amp; Best Practices →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-analytics-overview" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Analytics Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/mmr-by-plan" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: MRR by Plan</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/data-imports-and-exports" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Data Exports</a>
        <a href="https://docs.recurly.com/docs/subscription-ramp-pricing-export" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Ramp Pricing Export</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/usages-records-export" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Usage Records Export</a>
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
