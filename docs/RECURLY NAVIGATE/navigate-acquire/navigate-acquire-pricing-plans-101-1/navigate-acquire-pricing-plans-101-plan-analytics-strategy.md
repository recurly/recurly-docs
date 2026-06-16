---
title: 'Plan Analytics: Strategy & best practices'
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

/* Numbered + Q steps */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 20px 0 0; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-num-q { width: 36px; height: 36px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0; }
.rc-step-content p + p { margin-top: 8px; }
.rc-step-content strong { color: var(--darkgray); }

/* Checklist */
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
.rc-checklist-item:has(input[type="checkbox"]:checked) { background: rgba(255,215,6,0.06); }
.rc-checklist-text { flex: 1; }
.rc-checklist-text strong { font-size: .9rem; font-weight: 700; color: var(--offblack); display: block; margin-bottom: 2px; transition: color .18s; }
.rc-checklist-text span { font-size: .8rem; color: var(--gray); line-height: 1.4; display: block; }
.rc-checklist-footer { padding: 10px 22px; background: var(--brightgray); border-top: 1px solid var(--lightgray); font-size: .78rem; color: var(--gray); font-weight: 600; }

/* Pitch card */
.rc-pitch-card { background: #0D0D0B !important; border-radius: 14px; padding: 36px 40px; text-align: center; margin: 0 0 40px; border: 1px solid rgba(255,255,255,0.08); }
.rc-pitch-emoji { font-size: 2.4rem; margin-bottom: 12px; }
.rc-pitch-card h3 { font-size: 1.1rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; color: #FFD706 !important; margin: 0 0 16px; }
.rc-pitch-quote { font-size: 1.05rem; color: #FFFDF2 !important; line-height: 1.7; max-width: 680px; margin: 0 auto; font-style: italic; }
.rc-pitch-quote strong { color: #ffffff !important; font-style: normal; }

/* OH CTA */
.rc-oh-cta { background: var(--offblack); border: 2px solid var(--yellow); border-radius: 14px; padding: 32px 36px; margin: 32px 0; }
.rc-oh-cta h4 { color: #FFD706; font-size: 1.05rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px; }
.rc-oh-cta p { color: #CCC9B8; font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
.rc-oh-cta p strong { color: #FFFDF2; }
.rc-guide a.rc-oh-btn { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-oh-btn:hover { background: transparent !important; color: var(--yellow) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Continue your journey */
.rc-next-steps { margin: 40px 0 0; }
.rc-next-steps h3 { font-size: .78rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 16px; }
.rc-next-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; }
.rc-next-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 20px; text-decoration: none !important; color: inherit; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-guide a.rc-next-card { border-bottom: 1px solid var(--lightgray) !important; }
.rc-guide a.rc-next-card:hover { border-color: #FFD706; border-bottom: 1px solid #FFD706 !important; box-shadow: 0 4px 16px rgba(255,215,6,0.15); transform: translateY(-2px); }
.rc-next-card-tag { font-size: .68rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: var(--yellow); margin-bottom: 2px; }
.rc-next-card-icon { font-size: 1.3rem; line-height: 1; }
.rc-next-card h4 { font-size: .95rem; font-weight: 800; color: var(--offblack); margin: 0; line-height: 1.3; }
.rc-next-card p { font-size: .85rem; color: var(--gray); line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-next-card-arrow { font-size: .82rem; font-weight: 700; color: var(--orange); margin-top: 4px; }

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
  .rc-next-grid { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-oh-cta { padding: 24px 20px; }
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
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Pricing &amp; Plans 101
      </div>
      <div class="rc-lp-hero-title"><h1>Plan analytics — Strategy & best practices</h1></div>
      <p>Having the data is the easy part. Connecting it to the right decisions — which plans to invest in, which pricing changes to test, which trials to redesign — is where analytics creates real business value. This page closes the Pricing &amp; Plans 101 series with the framework for turning your Recurly data into a continuous improvement cycle.</p>
      
    </div>

    <!-- Navigation Menu — page 3 active -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-sticky-link"><span class="rc-step-badge">1</span> Analytics: Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics-using" class="rc-sticky-link"><span class="rc-step-badge">2</span> Analytics: Reading Your Data</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics-strategy" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Analytics: Strategy
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- Analytics-to-action framework -->
    <div class="rc-lp-section" id="analytics-to-action">
      <h2>🔄 Closing the loop: from data to decision</h2>
      <p>The goal of plan analytics isn't a better dashboard — it's a faster, more confident decision cycle. Every pricing or packaging change you make should start with a specific data question and end with a measurable outcome you track. Without that loop, analytics becomes reporting theater: numbers reviewed in a meeting, no action taken, repeated next month.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Use ARPU movement as the primary signal for pricing model effectiveness</h4>
            <p>When you add an add-on, change a pricing model, or introduce a new plan tier, ARPU should move — upward if the change increases revenue per subscriber, or downward if it introduces a cheaper option that cannibalized an existing one. If ARPU doesn't move after a pricing change that was intended to increase revenue, the change either isn't being adopted (low attach or upgrade rates) or it's replacing equivalent-value subscriptions at a net-zero impact. ARPU is the most sensitive and fastest-moving indicator of pricing model health.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Run cohort retention analysis after every significant pricing change</h4>
            <p>Cohort analysis answers the question that ARPU can't: did the subscribers acquired under the new pricing retain better or worse over time? Group subscriptions by their acquisition month, then track what percentage of each cohort is still active at 3, 6, and 12 months. Compare cohorts created before vs. after your pricing change. <strong>A pricing change that improves ARPU but degrades cohort retention is a short-term win and a long-term problem</strong> — you're charging more per subscriber but losing them faster, which produces worse LTV even with better ARPU.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Monitor plan mix monthly and flag when it drifts from intention</h4>
            <p>Your plan mix — the distribution of subscribers and MRR across plans — should reflect your intended value architecture. If you've designed a three-tier product (starter / professional / enterprise) and 80% of subscribers are on starter with 5% on enterprise, your tiers aren't working as intended. Review plan mix monthly and set thresholds: if the starter plan exceeds X% of total subscribers, that's a trigger to review upgrade friction. If the enterprise plan drops below Y% of MRR, that's a trigger to review whether it's differentiated enough.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Separate voluntary from involuntary churn before deciding what to fix</h4>
            <p>Voluntary churn (subscriber chose to cancel) and involuntary churn (payment failure) have completely different root causes and interventions. Recurly's dunning and recovery reporting lets you see both. If a large share of your churn is involuntary, the highest-leverage improvement isn't your pricing or your product — it's your payment recovery stack. Recurly's Account Updater and retry logic can recover a meaningful percentage of involuntary churn before it becomes permanent. Fix payment recovery before adding features or changing prices to address a churn number that's primarily driven by failed payments.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Q&A -->
    <div class="rc-lp-section" id="qa">
      <h2>❓ Common analytics strategy questions</h2>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Our MRR is growing but our churn rate is also increasing. What do we do first?"</h4>
            <p>Separate the churn into voluntary and involuntary before deciding. If the churn rate increase is mostly involuntary (payment failures), improving your dunning configuration and enabling Account Updater will have the fastest and largest impact — and doesn't require any product or pricing changes. If the churn is voluntary, segment it by plan and look at which plans are churning fastest relative to their acquisition rate. <strong>The plan where the gap between new subscriber rate and cancellation rate is narrowing fastest is your most urgent retention problem.</strong> Start with exit survey data for that plan to understand why subscribers are leaving before making changes.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"We changed our pricing six months ago. How do we know if it worked?"</h4>
            <p>Three data points give you a reliable answer. First, compare ARPU before and after the change — if ARPU increased by more than the price increase alone would explain, you're seeing positive adoption of higher-value configurations. Second, run cohort retention analysis: do subscribers acquired after the pricing change retain better at 3 and 6 months than the cohort acquired just before? Third, check plan mix: are subscribers distributing across your plans as intended, or is there heavy concentration in a tier that suggests the pricing isn't creating the right incentive to upgrade? All three together give you a confident answer. One alone can mislead.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Our add-on attach rates are low. Is that an analytics problem or a pricing problem?"</h4>
            <p>Low add-on attach rates are almost never an analytics problem — they're a visibility, positioning, or pricing problem. Analytics tells you the rate is low; it doesn't tell you why. To diagnose, check: where in the subscriber journey is the add-on presented? Is it available in the checkout flow, the in-app upgrade prompt, and the Hosted Account Page, or just in one place? Is the add-on's value described in terms of subscriber benefit or in terms of features? Is the price positioned against a clear alternative cost (e.g. "add multi-currency for $X/month vs. building and maintaining your own currency logic")? Low attach rates with high visibility usually indicate a pricing or value-framing problem, not a positioning problem.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Analytics audit checklist -->
    <div class="rc-lp-section" id="audit">
      <h2>🔍 Analytics readiness check</h2>
      <p>Run this before your next pricing or packaging review. The goal isn't a perfect analytics setup — it's having enough baseline data to make decisions with evidence rather than instinct.</p>

      <div class="rc-checklist">
        <div class="rc-checklist-header">
          <span style="font-size:1rem;">📋</span>
          <h4>P&amp;P analytics readiness audit</h4>
        </div>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>MRR, churn rate, and ARPU are tracked monthly with documented baselines</strong>
            <span>If not: pull the last 6 months from Recurly Reports → Metrics and record it in a shared doc. You need at least 3 months of data before a pricing change to establish a meaningful baseline.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Voluntary and involuntary churn are tracked separately</strong>
            <span>If not: go to Reports → Churn and filter by churn reason to see the split. If involuntary churn is &gt;30% of total churn, payment recovery is a higher priority than pricing changes.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Trial conversion rate is tracked per plan and has a documented baseline</strong>
            <span>If not: export subscription data filtered by plan, calculate conversions from trialing to active for the last 90 days, and record the rate. No trial strategy improvement is measurable without this number.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Plan mix (subscriber and MRR distribution by plan) is reviewed quarterly</strong>
            <span>If not: export active subscriptions and calculate the percentage of subscribers and MRR on each plan. Compare to your intended distribution. Any plan holding &gt;70% of subscribers with &lt;40% of MRR is a signal that upgrade friction is too high or plan differentiation is too low.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Plan codes follow a consistent naming convention</strong>
            <span>If not: establish a convention now for any new plans (e.g. product_tier_billing-frequency_currency). Inconsistent codes make every filter, export, and API query harder — and the problem compounds with every new plan you create.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>A cohort retention export has been run at least once in the last year</strong>
            <span>If not: export subscriptions with created_at dates, group by acquisition month, and track 3-month and 6-month survival rates. This single analysis often reveals more about pricing effectiveness than any dashboard metric.</span>
          </div>
        </label>
        <div class="rc-checklist-footer">✓ Mark each item complete as you address it — any unchecked item is a specific, actionable opportunity</div>
      </div>
    </div>

    <!-- AI era -->
    <div class="rc-lp-section" id="ai-analytics">
      <h2>🤖 Analytics in the AI era</h2>
      <p>AI tools are changing the speed and accessibility of subscription analytics — not the underlying logic of what the data means, but how quickly you can move from raw data to insight. Two capabilities are particularly relevant for P&amp;P analytics right now.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Can I use AI to analyze my Recurly export data?"</h4>
            <p>Yes — and it dramatically accelerates analyses that would otherwise take hours. Export your subscription data as CSV from Recurly, then upload it to an AI tool with a specific question: <strong>"What is the 6-month retention rate by acquisition cohort for each plan?"</strong> or <strong>"Which plans have the highest revenue churn relative to subscriber churn, and what does that suggest about which subscribers are leaving?"</strong> The AI handles the data manipulation; you focus on interpreting the output and deciding what to do with it. The cleaner your Recurly data (consistent plan codes, complete subscription records), the more reliable the AI's analysis will be.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"What analytics questions should I be asking about how AI is affecting my subscription business?"</h4>
            <p>The most important question right now is whether AI-assisted subscriber behavior is changing your churn and upgrade patterns in ways you haven't yet noticed. Specifically: are subscribers on your starter plans churning faster or slower since AI tools became widely available? If AI tools are helping subscribers self-serve things they used to need your product for, churn on feature-limited plans may accelerate. Conversely, if AI tools are driving subscribers to discover and use more of your product, add-on attach rates and upgrade rates should be improving. Pull cohort retention for the last 18 months and look for inflection points that don't correlate with pricing changes.</p>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Data quality compounds — in both directions</strong>
          <p>Every inconsistency in your plan codes, every missing add-on record, and every subscription that wasn't properly closed makes your analytics less reliable — and AI-assisted analysis amplifies both the benefits of clean data and the costs of dirty data. An AI analyzing a clean export produces sharp insights in minutes. An AI analyzing a messy export produces confident-sounding nonsense. If you're going to use AI for subscription analytics, investing time now in data hygiene will pay back many times over.</p>
        </div>
      </div>
    </div>

    <!-- Pitch card -->
    <div class="rc-pitch-card">
      <div class="rc-pitch-emoji">📈</div>
      <h3>Data tells you what happened. Strategy tells you what to do next.</h3>
      <p class="rc-pitch-quote">"The subscription businesses that grow most reliably are the ones that treat every pricing decision as an <strong>experiment with a measurable outcome</strong> — not a permanent bet made once and never reviewed."</p>
    </div>

    <!-- Thought-provoking question -->
    <div class="rc-lp-section">
      <h2>💭 Something to consider</h2>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num-q">?</div>
          <div class="rc-step-content">
            <h4>Look at everything you've built and configured in this series: plans, add-ons, currency, pricing models, trials. What's the one metric that would tell you, six months from now, whether those decisions were the right ones?</h4>
            <p>It's worth naming that metric explicitly and writing it down before you finish this path. Not because one number captures everything, but because the discipline of identifying the single most important leading indicator of success for your current configuration is how you avoid reviewing 15 metrics every month and drawing no conclusions. For most subscription businesses at an early-to-mid growth stage, that metric is either ARPU (am I getting more revenue per subscriber as I grow?) or cohort retention at 6 months (are the subscribers I'm acquiring staying?). The answer shapes every analytical priority for the next quarter.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- OH CTA -->
    <div class="rc-oh-cta">
      <h4>🗓️ Questions about measuring your P&amp;P configuration?</h4>
      <p>Our Customer Success team runs weekly <strong>Global Office Hours</strong> sessions where you can bring specific analytics questions — how to pull trial conversion by plan, how to set up cohort analysis in Recurly exports, how to interpret MRR movement, or how to connect your Recurly data to a BI tool.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <!-- Path nav — completion, links to Review & Resources -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics-using" class="rc-btn-prev">← Reading Your Data</a>
      <span class="rc-lp-nav-indicator">3 of 3 · Analytics</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-review" class="rc-btn-path">Review &amp; Resources →</a>
    </div>
    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/analytics-overview" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Analytics Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/mrr" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: MRR</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/churn" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Churn</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/subscription-reports" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Subscription Reports</a>
        <a href="https://recurly.com/resources/subscription-benchmarks/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📝 Recurly Subscription Benchmarks</a>
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
          <span class="rc-footer-label">Pricing &amp; Packaging 101:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-footer-link">P&amp;P 101 Overview</a>
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