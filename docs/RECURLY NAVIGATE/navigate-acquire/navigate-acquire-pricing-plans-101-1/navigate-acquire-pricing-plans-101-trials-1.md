---
title: 'Trials: Overview'
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

/* Nav — non-sticky, open, Micro-Path */
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
.rc-callout-caution { background: rgba(255,130,0,0.08); border-left: 4px solid var(--orange); }
.rc-callout-caution .rc-callout-body > strong { color: var(--darkgray); }

/* Numbered steps */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 20px 0 0; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0; }
.rc-step-content p + p { margin-top: 8px; }
.rc-step-content strong { color: var(--darkgray); }
.rc-step-content a { color: var(--orange); font-weight: 600; text-decoration: none !important; }
.rc-guide .rc-step-content a:hover { text-decoration: underline !important; }

/* Comparison table */
.rc-compare-table { width: 100%; border-collapse: collapse; margin: 20px 0 32px; font-size: .88rem; }
.rc-compare-table th { background: var(--offblack); color: var(--yellow); font-size: .72rem; font-weight: 800; letter-spacing: .8px; text-transform: uppercase; padding: 10px 14px; text-align: left; }
.rc-compare-table td { padding: 13px 14px; border-bottom: 1px solid var(--brightgray); color: var(--darkgray); vertical-align: top; line-height: 1.5; }
.rc-compare-table tr:last-child td { border-bottom: none; }
.rc-compare-table tr:nth-child(even) td { background: var(--offwhite); }
.rc-compare-table td:first-child { font-weight: 700; color: var(--offblack); }
.rc-compare-table .rc-tag-yes { display: inline-flex; align-items: center; gap: 4px; font-size: .75rem; font-weight: 700; color: var(--offblack); background: rgba(255,215,6,0.25); border: 1px solid rgba(255,215,6,0.5); padding: 2px 9px; border-radius: 10px; white-space: nowrap; }
.rc-compare-table .rc-tag-no { display: inline-flex; align-items: center; gap: 4px; font-size: .75rem; font-weight: 700; color: var(--gray); background: var(--brightgray); border: 1px solid var(--lightgray); padding: 2px 9px; border-radius: 10px; white-space: nowrap; }

/* Accent cards */
.rc-accent-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 20px 0; }
.rc-accent-card.rc-accent-orange { border-left: 4px solid var(--orange); }
.rc-accent-card.rc-accent-yellow { border-left: 4px solid var(--yellow); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 12px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-accent-card p:last-child { margin-bottom: 0; }
.rc-accent-card ul { font-size: .9rem; color: var(--gray); line-height: 1.75; padding-left: 20px; margin: 0; }
.rc-accent-card ul li { margin-bottom: 4px; }
.rc-accent-card ul li strong { color: var(--darkgray); }

/* Path nav */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }.rc-guide a.rc-btn-prev { background: transparent; color: var(--offblack) !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--lightgray); transition: all .2s; }
.rc-guide a.rc-btn-prev { border-bottom: 2px solid var(--lightgray) !important; }
.rc-guide a.rc-btn-prev:hover { border: 2px solid var(--offblack) !important; border-bottom: 2px solid var(--offblack) !important; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }
.rc-btn-start-label { font-size: .8rem; font-weight: 600; color: var(--lightgray); }

/* Resources */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--yellow); border-radius: 10px; padding: 20px 24px; margin: 48px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FFD706 !important; }

/* Footer — grouped sections */
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
  .rc-compare-table { font-size: .8rem; }
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
      <div class="rc-lp-hero-title"><h1>Trials — Overview</h1></div>
      <p>Trials reduce the risk of signing up. But how you structure a trial — whether you require a card, how long you run it, and what happens at the end — shapes both who starts and who converts. This page explains how trials work in Recurly and the key decisions before you configure one.</p>
      
    </div>

    <!-- Navigation Menu — page 1 active -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <!-- Active page: map pin replaces badge -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Trials: Overview
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials-configure" class="rc-sticky-link"><span class="rc-step-badge">2</span> Trials: Configure</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials-strategy" class="rc-sticky-link"><span class="rc-step-badge">3</span> Trials: Strategy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- What trials do in Recurly -->
    <div class="rc-lp-section" id="what-trials-do">
      <h2>🧪 What trials do in Recurly</h2>
      <p>A trial in Recurly is a period at the start of a subscription during which the subscriber is not billed. The trial is configured at the plan level — you set a trial length (in days) and decide whether billing information is required to start the trial. When a subscription is created with that plan, Recurly creates it in a <strong>trialing</strong> status and schedules the first invoice for after the trial period ends.</p>
      <p>At the end of the trial, Recurly automatically transitions the subscription to <strong>active</strong> and generates the first invoice. If a payment method is on file, Recurly attempts to collect immediately. If no payment method was collected during signup (cardless trial), Recurly transitions the subscription to <strong>past due</strong> and triggers your dunning workflow.</p>
      <p>Trials are not refunds, free accounts, or feature-limited plans. A trialing subscription has full access to the plan's features — it just hasn't been charged yet. This matters for how you communicate the end of the trial to the subscriber.</p>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Trial vs. freemium: different tools for different goals</strong>
          <p>A trial gives a subscriber time-limited access to a paid plan without charge. Freemium gives indefinite access to a limited version of the product at no cost. Recurly handles trials natively — freemium models typically use a free plan priced at $0, which is a different configuration. Don't use a trial to approximate freemium if you need ongoing free access.</p>
        </div>
      </div>
    </div>

    <!-- Trial approaches comparison -->
    <div class="rc-lp-section" id="trial-approaches">
      <h2>🔀 Three approaches to trials in Recurly</h2>
      <p>Recurly supports three ways to create a trial-like experience. Each has different tradeoffs for conversion, tracking, and operational complexity.</p>

      <table class="rc-compare-table">
        <thead>
          <tr>
            <th>Approach</th>
            <th>How it works</th>
            <th>Card required?</th>
            <th>Auto-converts?</th>
            <th>Best for</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Plan-level free trial</td>
            <td>Trial length set on the plan. New subscriptions enter <em>trialing</em> status and auto-convert at trial end.</td>
            <td><span class="rc-tag-yes">Configurable</span></td>
            <td><span class="rc-tag-yes">Yes — automatic</span></td>
            <td>Most subscription products. Clean, native, requires no workarounds.</td>
          </tr>
          <tr>
            <td>Coupon-based trial (100% off first period)</td>
            <td>A 100% discount coupon applied at checkout gives a $0 first invoice. Subscriber is billed at full price next cycle.</td>
            <td><span class="rc-tag-yes">Always required</span></td>
            <td><span class="rc-tag-yes">Yes — automatic</span></td>
            <td>When you want trial tracking separate from plan config, or targeted trial offers by cohort.</td>
          </tr>
          <tr>
            <td>Manual trial extension via API</td>
            <td>Override a specific subscription's trial end date via the API or admin UI. Used to extend existing trials case by case.</td>
            <td><span class="rc-tag-no">Depends on plan</span></td>
            <td><span class="rc-tag-yes">Yes — at extended end date</span></td>
            <td>CSM-led or sales-assisted trial management. Not a substitute for plan-level trial setup.</td>
          </tr>
        </tbody>
      </table>

      <div class="rc-callout rc-callout-caution">
        <div class="rc-callout-icon">⚠️</div>
        <div class="rc-callout-body">
          <strong>Coupon-based trials add operational overhead</strong>
          <p>While 100% coupon trials give you more flexibility in targeting and tracking, they require managing coupon codes and redemption limits separately from the plan. For most products, the native plan-level trial is simpler and less error-prone. Reserve the coupon approach for cases where you genuinely need per-cohort or per-campaign trial differentiation.</p>
        </div>
      </div>
    </div>

    <!-- The key decisions -->
    <div class="rc-lp-section" id="key-decisions">
      <h2>🎯 The key decisions before you configure</h2>
      <p>These four decisions determine the shape of your trial and should be resolved before you touch a plan configuration. Changing a plan's trial settings after subscribers are on it doesn't retroactively affect existing subscriptions — new subscribers only.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>How long should the trial be?</h4>
            <p>Trial length should match the time it takes a new subscriber to reach a moment where the product has delivered clear value — not the time it takes to explore every feature. Common trial lengths are 7, 14, and 30 days. A 30-day trial is rarely better than a 14-day trial unless your product has a genuinely long time-to-value. Longer trials often delay the purchase decision without improving conversion.</p>
            <p>Set the length in days, not months — Recurly supports both, but days gives you precise control and makes it easier to communicate clearly in onboarding emails ("Your trial ends on [date]").</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Do you require billing information at trial signup?</h4>
            <p>This is the most consequential decision in trial configuration. <strong>Requiring a card</strong> gives you a higher-quality funnel, automatic conversion at trial end, and no payment collection risk — but reduces trial start rate because many users won't enter card details for something they're not yet convinced about. <strong>Waiving the card requirement</strong> increases trial starts but produces a weaker conversion signal and requires active payment collection before or at trial end.</p>
            <p>Neither is universally correct. The right answer depends on your product's trust environment, your sales motion (product-led vs. sales-assisted), and how much of your funnel you're optimising for at the top vs. the bottom.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>What happens to subscribers who don't convert at trial end?</h4>
            <p>For card-required trials: Recurly bills at trial end. If the charge fails, the subscription enters your dunning workflow. For cardless trials: Recurly transitions the subscription to past due and your dunning workflow begins — but you have no guarantee of a payment method on file to bill against. You need an active re-engagement flow (email, in-app, CSM outreach) to collect payment from cardless trial subscribers before they expire.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Will you offer trial extensions?</h4>
            <p>Decide in advance whether trial extensions are a customer success tool (yes, we extend for high-intent users who need more time) or an exception (no, standard trial length is non-negotiable). Ad hoc extensions are possible via the admin UI and API — but if your support team or CSMs are extending trials without a clear policy, you lose conversion signal and extend your revenue recognition timeline unpredictably.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- What trials are not -->
    <div class="rc-lp-section" id="what-trials-are-not">
      <h2>⛔ What trials don't solve</h2>
      <p>Trials are a trust-building mechanism, not a product or pricing fix. If you're adding a trial to compensate for a problem elsewhere in the funnel, understand what problem you're actually solving before you configure one.</p>

      <div class="rc-accent-card rc-accent-orange">
        <h4>🔒 Trials don't fix churn caused by weak product value</h4>
        <p>A trial that delays the first payment doesn't change what the subscriber experiences after they convert. If subscribers are churning after their first paid period, a longer trial will shift when the churn happens — it won't reduce the rate. Audit post-trial churn before extending trial length as a retention strategy.</p>
      </div>

      <div class="rc-accent-card rc-accent-orange">
        <h4>📊 Trials don't fix pricing that's misaligned with perceived value</h4>
        <p>If a subscriber goes through a 30-day trial, sees the value, but still doesn't convert because the price feels too high relative to what they're getting, the problem is pricing or packaging — not trial length. Adding Ramp pricing or extending the trial further doesn't fix a value-perception gap. It pushes the decision further out.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>⚠️ Cardless trials are not demand — they are intent signals</h4>
        <p>A subscriber who starts a trial without a payment method has expressed curiosity, not commitment. Cardless trial starts can look impressive as a funnel metric while producing almost no paid conversions. Track <strong>trial-to-paid conversion rate</strong> — not trial starts — as the primary measure of trial effectiveness. A card-required trial with half the starts but three times the conversion rate is a better trial.</p>
      </div>
    </div>

    <!-- Path nav — start -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models-configure" class="rc-btn-prev">← Start of Micro-Path</a>
      <span class="rc-lp-nav-indicator">1 of 3 · Trials</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials-configure" class="rc-btn-path">Next: How to Configure →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/trials" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Trials</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Plans</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/coupons" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Coupons</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Support</a>
      </div>
    </div>

    <!-- Footer — grouped sections -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Micro-Path: Trials:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-footer-link">Trials: Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials-configure" class="rc-footer-link">Trials: Configure</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials-strategy" class="rc-footer-link">Trials: Strategy &amp; Best Practices</a>
        </div>
        <div class="rc-footer-section">
          <span class="rc-footer-label">Pricing &amp; Plans 101</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-footer-link">Pricing & Plans 101: Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-footer-link">Plans</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-footer-link">Add-Ons</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-footer-link">Currency</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-footer-link">Pricing Models</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-footer-link">Analytics</a>
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
