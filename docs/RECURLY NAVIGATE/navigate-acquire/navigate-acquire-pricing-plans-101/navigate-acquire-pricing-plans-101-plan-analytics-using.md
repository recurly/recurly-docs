---
title: 'Analytics: Reading your data'
excerpt: 'Need to check slug for this page since the title changed. '
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
.rc-lp-section p:last-child { margin-bottom: 0; }

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

/* Numbered steps */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 20px 0 0; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0; }
.rc-step-content p + p { margin-top: 8px; }
.rc-step-content strong { color: var(--darkgray); }
.rc-step-content code { background: var(--brightgray); color: var(--offblack); padding: 2px 7px; border-radius: 4px; font-size: .82rem; font-family: monospace; }

/* Report reference table */
.rc-field-table { width: 100%; border-collapse: collapse; margin: 20px 0 32px; font-size: .88rem; }
.rc-field-table th { background: var(--offblack); color: var(--yellow); font-size: .72rem; font-weight: 800; letter-spacing: .8px; text-transform: uppercase; padding: 10px 14px; text-align: left; }
.rc-field-table td { padding: 12px 14px; border-bottom: 1px solid var(--brightgray); color: var(--darkgray); vertical-align: top; line-height: 1.5; }
.rc-field-table tr:last-child td { border-bottom: none; }
.rc-field-table tr:nth-child(even) td { background: var(--offwhite); }
.rc-field-table td:first-child { font-weight: 700; color: var(--offblack); }

/* Accent cards */
.rc-accent-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 20px 0; }
.rc-accent-card.rc-accent-yellow { border-left: 4px solid var(--yellow); }
.rc-accent-card.rc-accent-orange { border-left: 4px solid var(--orange); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 12px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-accent-card p:last-child { margin-bottom: 0; }

/* Video card */
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

/* Footer */
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
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Pricing & Plans 101
      </div>
      <div class="rc-lp-hero-title"><h1>Plan Analytics — Reading Your Data</h1></div>
      <p>A practical walkthrough of where to find the key metrics in Recurly's admin UI — how to navigate to each report, what you're looking at when you get there, and what to export when you need to go deeper than the dashboard.</p>

    </div>

    <!-- Navigation Menu — page 2 active -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-sticky-link"><span class="rc-step-badge">1</span> Analytics: Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics-using" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Analytics: Reading Your Data
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics-strategy" class="rc-sticky-link"><span class="rc-step-badge">3</span> Analytics: Strategy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- Metrics dashboard -->
    <div class="rc-lp-section" id="metrics-dashboard">
      <h2>📊 The Metrics dashboard: your starting point</h2>
      <p>Navigate to <strong>Reports → Metrics</strong> in the Recurly admin. This is the highest-level view of your subscription health — MRR, active subscriber count, new subscriptions, churn, and MRR movement for your selected date range. Start here every time before drilling into specific reports.</p>

      <div class="rc-video-card">
        <div class="rc-video-header">
          <h4>Trail guide: Navigating Recurly's key analytics reports</h4>
          <span>Video coming soon</span>
        </div>
        <div class="rc-video-placeholder">
          <span style="font-size:2rem;">▶</span>
          <span>Walkthrough video will be added here</span>
        </div>
        <div class="rc-video-caption">A screencast tour of Recurly's Metrics dashboard, Subscription Activity report, Churn report, and plan-level filtering — showing where to find each number and what to look for when reading it.</div>
      </div>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Read MRR and MRR movement together</h4>
            <p>The Metrics dashboard shows your current MRR and the components driving its change: <strong>new MRR</strong> (from new subscriptions), <strong>expansion MRR</strong> (from upgrades or add-ons), <strong>contraction MRR</strong> (from downgrades), and <strong>churn MRR</strong> (from cancellations). Read all four alongside the total figure — a growing MRR total with high churn MRR means you're working very hard to stay in place. Healthy subscription businesses have new + expansion MRR significantly exceeding contraction + churn MRR.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Set the date range to a full month, then compare periods</h4>
            <p>The default view may show a partial or rolling window. Set the date range to a complete calendar month so you're comparing like-for-like periods. Then use the period comparison feature to view the same metrics against the prior month or prior year. Month-over-month comparisons reveal trends; year-over-year comparisons reveal whether seasonal patterns are repeating.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Bookmark this view for your monthly review</h4>
            <p>The Metrics dashboard is most useful as a consistent monthly checkpoint, not a daily monitor. Set a recurring reminder to review it on the same day each month — first of the month or last business day of the month. Consistent timing makes trends visible that would otherwise be missed in day-to-day noise.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Where to find each report -->
    <div class="rc-lp-section" id="report-map">
      <h2>🗺️ Report map: where to find what you need</h2>
      <p>Recurly organizes its reporting under <strong>Reports</strong> in the main navigation. Here's a reference for each report relevant to plan analytics and where to find it.</p>

      <table class="rc-field-table">
        <thead>
          <tr>
            <th>Metric / Question</th>
            <th>Report name</th>
            <th>Where to find it</th>
            <th>Key filter</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>MRR, ARR, ARPU</td>
            <td>Metrics</td>
            <td>Reports → Metrics</td>
            <td>Date range; compare periods</td>
          </tr>
          <tr>
            <td>New subscriptions, cancellations, status changes</td>
            <td>Subscription Activity</td>
            <td>Reports → Subscriptions</td>
            <td>Plan; date range; subscription state</td>
          </tr>
          <tr>
            <td>Voluntary vs. involuntary churn</td>
            <td>Churn</td>
            <td>Reports → Churn</td>
            <td>Plan; churn reason</td>
          </tr>
          <tr>
            <td>Trial conversion rate</td>
            <td>Subscription Activity</td>
            <td>Reports → Subscriptions, filter by state = trialing or filter transitions</td>
            <td>Plan; trial end date range</td>
          </tr>
          <tr>
            <td>Revenue by plan</td>
            <td>Revenue Summary</td>
            <td>Reports → Revenue</td>
            <td>Plan; date range</td>
          </tr>
          <tr>
            <td>Failed payments and recovery</td>
            <td>Dunning</td>
            <td>Reports → Dunning</td>
            <td>Date range; recovery outcome</td>
          </tr>
          <tr>
            <td>Add-on attach rates, per-subscription line items</td>
            <td>Subscription Export (CSV)</td>
            <td>Reports → Export → Subscriptions</td>
            <td>Export and analyze in spreadsheet or BI tool</td>
          </tr>
        </tbody>
      </table>
    </div>

    <!-- Filtering by plan -->
    <div class="rc-lp-section" id="plan-filter">
      <h2>🔎 Filtering reports by plan</h2>
      <p>Most Recurly reports can be filtered by plan using a dropdown or plan code selector in the report filter bar. Plan-level filtering is the most important analytical capability for P&amp;P decision-making — without it, you're making plan changes based on aggregate data that may be masking very different performance across your plan portfolio.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Filter the Subscription Activity report by plan</h4>
            <p>In <strong>Reports → Subscriptions</strong>, use the Plan filter to select a specific plan. The report will show new subscriptions, cancellations, and active counts for that plan only. Run this for each plan in your portfolio and compare — the plan with the lowest cancellation rate relative to new subscriptions is your stickiest offer, which is the right place to invest in acquisition.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Compare churn rate by plan</h4>
            <p>In <strong>Reports → Churn</strong>, filter by plan to see churn rate per plan. Export each plan's churn data and compare side by side. If your lower-priced plans are churning significantly faster than your higher-priced plans, that's useful pricing signal — it may indicate that subscribers on the lower plan aren't getting enough value to justify renewal, which is an argument for reducing the feature gap between tiers or raising the lower plan's price.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Export subscription data for add-on attach rate analysis</h4>
            <p>Recurly's built-in reports don't surface add-on attach rate directly. To see what percentage of subscribers on a given plan have also purchased each add-on, export your subscription data from <strong>Reports → Export</strong> and analyze it in a spreadsheet. Filter by plan code, then count the rows with each add-on code present. This is a key metric for understanding whether optional add-ons are being discovered and purchased — or whether they need better placement in your checkout flow.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Track trial conversion per plan using the API or export</h4>
            <p>To calculate trial conversion rate by plan: export subscriptions filtered by plan and creation date range, then count subscriptions that transitioned from trialing to active vs. those that expired or were canceled during the trial period. The Recurly API also supports querying subscription state transitions directly — <code>GET /subscriptions?state=active&plan_codes[]=your_plan</code> combined with trial data gives you a precise conversion figure for any plan and date range.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- What to export and when -->
    <div class="rc-lp-section" id="exports">
      <h2>📥 What to export and when</h2>
      <p>Recurly's dashboard answers most routine questions. These are the scenarios where exporting to CSV or using the API produces insight that the built-in reports can't.</p>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>📊 Export for: add-on attach rate and revenue contribution</h4>
        <p>Export subscriptions with line items from <strong>Reports → Export → Subscriptions</strong>. For each plan, calculate what percentage of subscribers have each add-on, and what the average add-on revenue per subscriber is. If optional add-ons have low attach rates (&lt;15%), the add-on may be poorly placed in checkout or not discoverable in the account management portal — not necessarily unwanted.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>📊 Export for: cohort retention analysis</h4>
        <p>Export subscriptions with their <code>created_at</code> date and current state. Group by acquisition month (cohort) and calculate what percentage of each cohort is still active after 3, 6, and 12 months. Cohort retention analysis shows whether subscribers acquired in different periods (e.g. before vs. after a pricing change) retain differently — the single most reliable way to measure whether a plan or pricing change improved long-term retention.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>📊 Export for: quantity distribution on add-on pricing models</h4>
        <p>For Tiered, Volume, or Stairstep add-ons, export active subscriptions with add-on quantities. Plot the distribution of quantities across your subscriber base. Spikes just below a pricing band boundary are a signal of band-gaming behavior (as discussed in Pricing Models). A heavy concentration at the lowest band may mean your higher bands aren't reachable for most subscribers — which is an argument for narrowing the first band or adjusting the threshold.</p>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Clean plan codes make analytics dramatically easier</strong>
          <p>Every filter, export, and API query for plan-level analytics depends on your plan codes being consistent and descriptive. A plan code like <code>pro_monthly_usd</code> is filterable and self-documenting. A plan code like <code>plan_3_v2_new</code> requires knowing the history to interpret. If your plan code naming is inconsistent, now is the right time to establish a convention for new plans — you can't rename existing plan codes without migrating subscriptions, but you can prevent future confusion.</p>
        </div>
      </div>
    </div>

    <!-- Path nav -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-btn-prev">← Overview</a>
      <span class="rc-lp-nav-indicator">2 of 3 · Analytics</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics-strategy" class="rc-btn-path">Next: Strategy →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/analytics-overview" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Analytics Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/mrr" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: MRR</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/churn" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Churn</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/subscription-reports" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Subscription Reports</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Support</a>
      </div>
    </div>

    <!-- Footer -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Micro-Path: Analytics:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-footer-link">Analytics: Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics-using" class="rc-footer-link">Analytics: Reading Your Data</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics-strategy" class="rc-footer-link">Analytics: Strategy</a>
        </div>
        <div class="rc-footer-section">
          <span class="rc-footer-label">Pricing &amp; Plans 101</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-footer-link">Pricing & Plans 101: Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-footer-link">Plans</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-footer-link">Add-Ons</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-footer-link">Currency</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-footer-link">Pricing Models</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-footer-link">Trials</a>
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
