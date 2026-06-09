---
title: 'Pricing & Packaging 201: Advanced'
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

/* Back link */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link { color: var(--gray); text-decoration: none !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }

/* Content wrap */
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Announcement bar */
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

/* Hero */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack); background-size: cover;
  color: #fff; padding: 52px 40px 48px; text-align: center; border-radius: 16px; margin-bottom: 0;
}
.rc-lp-pillar-tag {
  display: inline-flex; align-items: center; gap: 7px;
  background: rgba(255,215,6,0.20); border: 1px solid rgba(255,215,6,0.45);
  color: var(--yellow); font-size: .75rem; font-weight: 800;
  letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 14px; border-radius: 20px; margin-bottom: 20px;
}
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.6rem; font-weight: 800; line-height: 1.1; color: #FFFDF2; margin: 0; }
.rc-hero > p { font-size: 1.05rem; opacity: .85; max-width: 660px; margin: 0 auto 32px; color: #CCC9B8; line-height: 1.65; }
.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 28px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 2rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: #CCC9B8; line-height: 1.3; }

/* Nav — sticky, collapsed, Acquire yellow, LP Overview variant */
details.rc-sticky-nav-wrap {
  position: sticky; top: 0; z-index: 100;
  background-color: var(--yellow);
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

/* Section headings */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* Stat strip (content) */
.rc-stat-strip { display: grid; grid-template-columns: repeat(3, 1fr); background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 0 0 32px; }
.rc-stat-tile { padding: 24px 20px; text-align: center; }
.rc-stat-tile + .rc-stat-tile { border-left: 1px solid var(--lightgray); }
.rc-stat-tile-num { font-size: 2rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 4px; }
.rc-stat-tile-label { font-size: .7rem; font-weight: 700; letter-spacing: .8px; text-transform: uppercase; color: var(--gray); margin-bottom: 10px; }
.rc-stat-tile-context { font-size: .8rem; color: var(--darkgray); line-height: 1.5; padding-top: 10px; border-top: 1px solid var(--brightgray); }

/* Callouts */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body > strong { color: var(--offblack); }

/* Table of contents cards — full-width, one per Micro-Path */
.rc-toc-list { display: flex; flex-direction: column; gap: 10px; margin: 0 0 40px; }
.rc-toc-card {
  display: grid; grid-template-columns: 44px 1fr 32px;
  align-items: center; gap: 16px;
  background: var(--offwhite); border: 1px solid var(--lightgray);
  border-radius: 12px; padding: 18px 22px;
  transition: all .2s ease;
}
.rc-guide a.rc-toc-card { border-bottom: 1px solid var(--lightgray) !important; }
.rc-guide a.rc-toc-card:hover { border-color: var(--yellow); border-bottom: 1px solid var(--yellow) !important; box-shadow: 0 4px 14px rgba(255,215,6,0.12); transform: translateX(3px); }
.rc-toc-num {
  width: 36px; height: 36px; border-radius: 50%;
  background: var(--offblack); color: var(--yellow);
  display: flex; align-items: center; justify-content: center;
  font-size: .85rem; font-weight: 800; flex-shrink: 0;
}
.rc-toc-body h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0 0 4px; }
.rc-toc-body p { font-size: .88rem; color: var(--gray); line-height: 1.5; margin: 0; }
.rc-toc-arrow { font-size: 1.1rem; color: var(--lightgray); text-align: right; transition: color .2s; }
.rc-guide a.rc-toc-card:hover .rc-toc-arrow { color: var(--yellow); }

/* Path navigation buttons */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-btn-start { background: var(--brightgray); color: var(--gray); padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid var(--lightgray); cursor: default; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Resources */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--yellow); border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FFD706 !important; }

/* Footer — grouped section structure */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rc-footer-link { color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; }
.rc-footer-link:hover { color: var(--orange); }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* Consolidated responsive block */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.9rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; margin-top: 24px; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-stat-strip { grid-template-columns: 1fr; }
  .rc-toc-card { grid-template-columns: 36px 1fr 24px; padding: 14px 16px; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-back-link">← Back to Acquire</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Announcement bar (hidden — add rc-active to show) -->
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
        <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Acquire"> Acquire
      </div>
      <div class="rc-lp-hero-title">
        <h1>Pricing &amp; Packaging 201</h1>
      </div>
      <p>You've built the foundation. This series goes deeper — into the pricing architectures that mature subscription businesses use to segment markets, serve enterprise customers, bill for real-world usage, and measure what's actually driving revenue growth.</p>
    </div>

    <!-- Navigation Menu — sticky, collapsed, LP Overview variant -->
    <details class="rc-sticky-nav-wrap">
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt="Home"> Navigate Home
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> P&amp;P 201 Overview
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-segmentation" class="rc-sticky-link">Segmentation</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-sticky-link">Account Hierarchy</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-sticky-link">Usage Billing</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models" class="rc-sticky-link">Advanced Models</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency" class="rc-sticky-link">Advanced Currency</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics" class="rc-sticky-link">Advanced Analytics</a>
          </div>
        </div>
      </div>
    </details>

    <!-- About this path -->
    <div class="rc-lp-section">
      <h2>📖 About this path</h2>
      <p>Pricing &amp; Packaging 101 covered the core Recurly configuration — plans, add-ons, currencies, pricing models, trials, and analytics. This series assumes you have that foundation in place and asks: how do you use it at scale?</p>
      <p>Each Micro-Path in 201 tackles a specific challenge that arises as a subscription business matures: serving multiple customer segments without plan sprawl, structuring billing for enterprise accounts, aligning cost with usage, and making your analytics data work as hard as your product does.</p>

      <div class="rc-stat-strip">
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">Plan sprawl</div>
          <div class="rc-stat-tile-label">The 201 problem to solve</div>
          <div class="rc-stat-tile-context">As businesses grow, uncontrolled plan creation produces hundreds of plans that are expensive to maintain and impossible to analyze. Price segmentation is the fix.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">API required</div>
          <div class="rc-stat-tile-label">Usage billing dependency</div>
          <div class="rc-stat-tile-context">Usage-based billing requires your system to log consumption records via the Recurly API. Unlike plan configuration, this is a technical integration — plan before you activate.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">Cohort first</div>
          <div class="rc-stat-tile-label">Advanced analytics approach</div>
          <div class="rc-stat-tile-context">Advanced analytics moves beyond dashboard metrics into cohort retention analysis, segment performance, and the data exports that feed AI-assisted decision-making.</div>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Prerequisites: P&amp;P 101</strong>
          <p>This series builds directly on the concepts in Pricing &amp; Packaging 101. If you haven't worked through plans, add-ons, pricing models, and trials yet, start there first — the 201 configurations assume those foundations are already in place. <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101">Return to P&amp;P 101 →</a></p>
        </div>
      </div>
    </div>

    <!-- What's in this path — table of contents -->
    <div class="rc-lp-section">
      <h2>📚 What's in this path</h2>
      <p>Six Micro-Paths, each focused on an advanced pricing or packaging challenge. These build on each other — Segmentation and Hierarchy lay the foundation for how your plan architecture scales, Usage Billing and Advanced Models address how you charge, and Advanced Currency and Analytics cover global operations and measurement.</p>

      <div class="rc-toc-list">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-segmentation" class="rc-toc-card">
          <div class="rc-toc-num">1</div>
          <div class="rc-toc-body">
            <h4>Price Segmentation</h4>
            <p>Charge different prices to different subscriber segments — by geography, cohort, or acquisition channel — using a single plan and price segments instead of duplicate plan configurations.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-toc-card">
          <div class="rc-toc-num">2</div>
          <div class="rc-toc-body">
            <h4>Account Hierarchy</h4>
            <p>Structure parent and child accounts for B2B and enterprise customers — with consolidated invoicing, seat management across an org, and Invoice Rollup for unified billing.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-toc-card">
          <div class="rc-toc-num">3</div>
          <div class="rc-toc-body">
            <h4>Usage Billing</h4>
            <p>Configure metered billing that charges subscribers for what they actually consume — API calls, messages, GB stored — logged via the Recurly API and billed in arrears each period.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models" class="rc-toc-card">
          <div class="rc-toc-num">4</div>
          <div class="rc-toc-body">
            <h4>Advanced Pricing Models</h4>
            <p>Build hybrid pricing architectures — base subscription plus usage add-ons — and explore prepaid account balance billing for customers who prefer to pay upfront rather than on a recurring schedule.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency" class="rc-toc-card">
          <div class="rc-toc-num">5</div>
          <div class="rc-toc-body">
            <h4>Advanced Currency</h4>
            <p>Go beyond basic multi-currency setup — configure per-currency gateway routing, handle 3DS/SCA compliance for European markets, and build region-aware dunning logic for different payment failure patterns.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics" class="rc-toc-card">
          <div class="rc-toc-num">6</div>
          <div class="rc-toc-body">
            <h4>Advanced Analytics</h4>
            <p>Move beyond built-in dashboards into exports, Analytics Explore, and external BI integrations — and learn how to use your Recurly data as the raw material for AI-assisted pricing decisions.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
      </div>

      <p style="color: var(--gray); font-size: .92rem;">Work through in order for the most complete picture, or jump to the topic most relevant to your current challenge.</p>
    </div>

    <!-- Path navigation — Start state -->
    <div class="rc-lp-nav">
      <span class="rc-btn-start">Start</span>
      <span class="rc-lp-nav-indicator">Overview</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-segmentation" class="rc-btn-path">Begin: Segmentation →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/billing-models" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Pricing Models</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/usage-based-pricing-guide" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Usage-Based Billing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/account-hierarchy" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Account Hierarchy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/analytics-overview" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Analytics Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-resource-link">📗 Pricing &amp; Packaging 101: The Basics</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Join Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
      </div>
    </div>

    <!-- Footer -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Pricing &amp; Packaging 201:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-segmentation" class="rc-footer-link">Segmentation</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-footer-link">Account Hierarchy</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-footer-link">Usage Billing</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models" class="rc-footer-link">Advanced Models</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency" class="rc-footer-link">Advanced Currency</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics" class="rc-footer-link">Advanced Analytics</a>
        </div>
        <div class="rc-footer-utility">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
            <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
          </a>
          <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
        </div>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
