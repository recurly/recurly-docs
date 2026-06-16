---
title: 'Advanced Pricing Models: Strategy & best practices'
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

/* Content sections */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

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

/* Accent cards */
.rc-accent-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 20px 0; }
.rc-accent-card.rc-accent-orange { border-left: 4px solid var(--orange); }
.rc-accent-card.rc-accent-yellow { border-left: 4px solid var(--yellow); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 12px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-accent-card ul { font-size: .9rem; color: var(--gray); line-height: 1.75; padding-left: 20px; margin: 0; }
.rc-accent-card ul li { margin-bottom: 4px; }
.rc-accent-card ul li strong { color: var(--darkgray); }

/* Q&A steps */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 20px 0 0; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num-q { width: 36px; height: 36px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0; }
.rc-step-content strong { color: var(--darkgray); }

/* Thought question */
.rc-thought-q { background: var(--offblack); border-radius: 14px; padding: 36px 40px; margin: 40px 0; text-align: center; border: 1px solid rgba(255,255,255,0.08); }
.rc-thought-q-label { font-size: .72rem; font-weight: 700; letter-spacing: 1px; text-transform: uppercase; color: #FFD706; margin-bottom: 16px; display: block; }
.rc-thought-q h3 { font-size: 1.25rem; font-weight: 800; color: #FFFDF2 !important; line-height: 1.5; margin: 0 0 12px; max-width: 680px; margin-left: auto; margin-right: auto; }
.rc-thought-q p { font-size: .9rem; color: rgba(255,253,242,0.65) !important; line-height: 1.6; max-width: 580px; margin: 0 auto; }

/* OH CTA */
.rc-oh-cta { background: var(--offblack); border: 2px solid var(--yellow); border-radius: 14px; padding: 32px 36px; margin: 32px 0; }
.rc-oh-cta h4 { color: var(--yellow); font-size: 1.05rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px; }
.rc-oh-cta p { color: var(--lightgray); font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
.rc-oh-cta p strong { color: var(--offwhite); }
@media(max-width:768px){ .rc-oh-cta { padding: 24px 20px; } }
.rc-guide a.rc-oh-btn { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); }
.rc-guide a.rc-oh-btn { border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-oh-btn:hover { background: transparent !important; color: var(--yellow) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Path nav */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-guide a.rc-btn-prev { background: transparent; color: var(--offblack) !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--lightgray); transition: all .2s; }
.rc-guide a.rc-btn-prev { border-bottom: 2px solid var(--lightgray) !important; }
.rc-guide a.rc-btn-prev:hover { border: 2px solid var(--offblack) !important; border-bottom: 2px solid var(--offblack) !important; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Continue Your Journey */
.rc-next-steps { margin: 40px 0 0; }
.rc-next-steps h3 { font-size: .78rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 16px; }
.rc-next-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; }
.rc-next-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 20px; text-decoration: none !important; color: inherit; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-guide a.rc-next-card { border-bottom: 1px solid var(--lightgray) !important; }
.rc-guide a.rc-next-card:hover { border-color: var(--yellow); border-bottom: 1px solid var(--yellow) !important; box-shadow: 0 4px 16px rgba(255,215,6,0.15); transform: translateY(-2px); }
.rc-next-card-tag { font-size: .68rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: var(--yellow); margin-bottom: 2px; }
.rc-next-card-icon { font-size: 1.3rem; line-height: 1; }
.rc-next-card h4 { font-size: .95rem; font-weight: 800; color: var(--offblack); margin: 0; line-height: 1.3; }
.rc-next-card p { font-size: .85rem; color: var(--gray); line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-next-card-arrow { font-size: .82rem; font-weight: 700; color: var(--orange); margin-top: 4px; }

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
  .rc-oh-cta { padding: 24px 20px; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-next-grid { grid-template-columns: 1fr; }
  .rc-thought-q { padding: 28px 24px; }
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
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Pricing &amp; Plans 201
      </div>
      <div class="rc-lp-hero-title"><h1>Advanced models — Strategy &amp; best practices</h1></div>
      <p>When to use each model, how to structure them for your segment, and what to watch for once customers are live on ramp, hybrid, and prepaid plans.</p>
      
 
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
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models-configure" class="rc-sticky-link">
              <span class="rc-step-badge">2</span> Configure
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models-strategy" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Strategy &amp; Best Practices
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-sticky-link">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- Section 1: Ramp Strategy -->
    <div class="rc-lp-section">
      <h2>🪜 Ramp Pricing Strategy</h2>
      <p>Ramp pricing is most valuable when the barrier to a deal isn't product quality or fit — it's year-one cost. Buyers are more willing to commit to a three-year contract at $1,500/month in year one escalating to $2,000 in year two and $2,500 in year three than they are to sign at $2,000 flat from the start, even if the total contract value is similar. The ramp structure lets you compete more aggressively on year-one cost without permanently lowering your rate.</p>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Anchor the conversation to total contract value, not the first period</strong>
          <p>When presenting a ramp structure, always show the customer the full schedule upfront — period 1 price, when it escalates, and what it reaches. Transparency about the ramp builds trust and prevents the price increase from feeling like a surprise when it arrives. Frame the lower year-one cost as an onboarding discount rather than "your real price starts later."</p>
        </div>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Three ramp structures worth knowing</h4>
        <ul>
          <li><strong>Introductory pricing:</strong> A lower first-period price that escalates to the standard rate after 1–3 billing periods. Best for reducing new customer acquisition friction without discounting the core product permanently. Works well for monthly plans with a 3-month intro rate.</li>
          <li><strong>Graduated annual escalation:</strong> Small percentage price increases scheduled annually — typically 3–8%. Commonly used in multi-year enterprise contracts to account for cost-of-living increases and lock in a renewal relationship. Set the escalation on a 12-period ramp interval for monthly plans.</li>
          <li><strong>Loyalty rewards (ramp down):</strong> Start higher and decrease price as a subscriber ages on the plan. This is less common but works well for retention-driven industries — the longer they stay, the better the rate. Can also be used as a trial-to-paid conversion model where the trial is free and each subsequent period adds cost until reaching the steady-state price.</li>
        </ul>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon">⚠️</div>
        <div class="rc-callout-body">
          <strong>Plan changes do not retroactively apply ramps to existing subscribers</strong>
          <p>If you modify a ramp plan after customers are already subscribed to it, existing subscribers keep the terms they signed up on. New subscribers get the updated ramp schedule. If you need to update pricing for an existing subscriber, you'll need to handle it through a subscription change or a separate plan update workflow.</p>
        </div>
      </div>
    </div>

    <!-- Section 2: Hybrid Strategy -->
    <div class="rc-lp-section">
      <h2>🔀 Hybrid Pricing Strategy</h2>
      <p>Hybrid pricing earns its keep in products where usage varies significantly between customers — or where usage grows over time for individual customers. The base subscription gives you predictable revenue and a defined relationship with the customer; the usage component captures the upside as they scale.</p>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Getting the base/variable split right</h4>
        <p>The base price should cover the minimum viable access to your product — the core features a customer needs to get started. The usage component should bill for the resources or activities that scale with the customer's business. A common mistake is setting the base price too low (making the product feel "usage-heavy" and unpredictable) or too high (eliminating the value of usage-based scaling for customers who are growing).</p>
        <p>A useful benchmark: look at your median monthly revenue per customer today. If you're transitioning from flat-rate, a base price around 60–70% of that median, with usage add-ons capturing the rest, tends to feel balanced to customers while preserving upside for power users.</p>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Make the usage portion feel like expansion, not surcharge</strong>
          <p>How you frame the variable component matters as much as how you price it. "Included: 10,000 API calls. Additional calls: $0.0005 each" positions usage as a generous starting allotment with modest overage. "Base plan: $99/month, plus API usage fees" sounds like a gotcha. The framing on your pricing page, invoice, and onboarding communications shapes how customers experience the variable bill when it arrives.</p>
        </div>
      </div>
    </div>

    <!-- Section 3: Prepaid Strategy -->
    <div class="rc-lp-section">
      <h2>💰 Prepaid Account Balance Strategy</h2>
      <p>Prepaid balance is most strategically valuable in two scenarios: when customers want to pay annually and avoid monthly billing friction, and when you're selling to high-volume customers who can secure a volume discount by committing upfront. In both cases, you collect cash immediately and reduce churn risk by increasing switching cost — a customer with unused prepaid balance is far less likely to leave than one billing month-to-month.</p>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Credit bundle design principles</h4>
        <ul>
          <li><strong>Make the discount meaningful:</strong> If the incentive to prepay is less than 10%, most customers won't bother. A 15–20% discount for a 12-month prepay is a common sweet spot that motivates the commitment without cannibalizing margin.</li>
          <li><strong>Set expiry expectations clearly:</strong> Recurly's prepaid balance doesn't automatically expire, but your business policy might impose one. If you expire credits after 12 or 18 months, communicate this prominently — surprise expiry is one of the fastest paths to a churn-driven complaint.</li>
          <li><strong>Consider credit "tiers":</strong> Offer two or three bundle sizes with increasing discounts (e.g., $500 for a 10% discount, $1,000 for 15%, $2,500 for 20%). This gives customers a clear reason to commit more upfront while giving your Finance team more predictable cash flow planning at each level.</li>
          <li><strong>Reload reminders are a retention opportunity:</strong> When a customer's balance is running low, send a proactive reload offer. This is a natural expansion conversation — "you're about to run out of credits, here's the bundle deal for topping up" is much easier than a cold upsell.</li>
        </ul>
      </div>
    </div>

    <!-- Section 4: Q&A -->
    <div class="rc-lp-section">
      <h2>❓ Common Questions from Merchants</h2>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Can we combine ramp pricing with usage add-ons on the same plan?"</h4>
            <p>Yes. A ramp plan sets the recurring base price at each interval, and usage add-ons on that plan are charged separately based on logged consumption each period. The two components operate independently — the base price ramps on schedule, while usage charges are calculated from the add-on's pricing structure regardless of which ramp interval the subscription is in. This combination is a powerful model for enterprise contracts: a known, escalating base price gives Finance predictability, while usage overages capture activity-driven expansion.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Can a customer's prepaid balance fund a ramp-priced subscription?"</h4>
            <p>Yes. When a subscription invoice generates — whether at the first ramp price or any subsequent interval — Recurly will draw from the available account balance first before charging the payment method on file. This combination is ideal for enterprise customers who want to prepay a year's worth of credits upfront and then have those credits automatically applied to their monthly invoices as the subscription progresses through its ramp schedule. Just ensure the prepaid amount is sufficient to cover the escalating charges across the full term.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"What happens to the ramp schedule if a subscriber upgrades or downgrades their plan?"</h4>
            <p>A plan change resets the subscriber to the new plan's terms — they don't carry their position in the old plan's ramp schedule forward. If you're using ramp pricing for long-term contract management, this means plan changes require careful handling. Best practice: if a customer needs a mid-contract adjustment, work through a subscription change that explicitly addresses the remaining ramp terms rather than switching them to an entirely new plan. Consider whether a price segment change (for customers on the same plan) would serve the need without disrupting the ramp lifecycle.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Section 5: AI Strategy -->
    <div class="rc-lp-section">
      <h2>🤖 AI Strategy for Advanced Pricing Models</h2>
      <p>Advanced pricing models generate more data about customer intent and lifecycle stage than flat-rate plans, and that data is exactly what makes AI-assisted decisions tractable. Here's where it has the most leverage.</p>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">🧠</div>
        <div class="rc-callout-body">
          <strong>Identify which customers should be offered a ramp — before they ask to leave</strong>
          <p>Price sensitivity is often a leading indicator of churn, not a post-cancellation confession. An AI model trained on support ticket sentiment, pricing objection patterns in sales calls, and subscription age can flag accounts where a proactive ramp offer might prevent cancellation. This turns a retention save into a revenue-positive conversation — the customer gets a lower near-term cost; you keep the relationship and the long-term contract value.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💳</div>
        <div class="rc-callout-body">
          <strong>Predict which accounts are most likely to prepay</strong>
          <p>Not every customer is a good prepaid balance candidate. Customers who regularly ask about invoicing, request payment terms, or have annual procurement cycles are strong signals. An AI model looking at account metadata — company size, billing history, support ticket topics — can score accounts for prepaid propensity before your CS or Sales team reaches out, making outreach more targeted and conversion rates higher.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">📈</div>
        <div class="rc-callout-body">
          <strong>Use ramp export data to model optimal escalation rates</strong>
          <p>The Subscriptions Ramp Pricing export gives you detailed data on how subscribers behave at each ramp interval — who stays, who downgrades, who churns after a price increase. Feed this into a predictive model to find the price escalation rate that maximizes net revenue across your cohort. You may find that 8% annual escalation retains 95% of customers, while 12% retains only 82% — a net revenue difference worth knowing before you set your next contract template.</p>
        </div>
      </div>
    </div>

    <!-- Thought Question -->
    <div class="rc-thought-q">
      <span class="rc-thought-q-label">💭 Something to Consider</span>
      <h3>If your pricing model fully reflected your customers' ability and willingness to pay at different stages of their relationship with you, how different would it look from what you offer today?</h3>
      <p>Ramp, hybrid, and prepaid are tools for meeting customers where they are financially — not just where your plan catalog happens to sit. The question is whether you've mapped that alignment intentionally.</p>
    </div>

    <!-- Office Hours CTA -->
    <div class="rc-oh-cta">
      <h4>🗓️ Bring Your Pricing Architecture to Office Hours</h4>
      <p>Deciding between ramp, hybrid, and prepaid — or trying to layer them — involves tradeoffs that depend heavily on your specific customer mix and sales motion. Join a <strong>Customer Success Global Office Hours</strong> session to walk through your situation with a Recurly CSM who can help you think it through.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <!-- Path navigation -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models-configure" class="rc-btn-prev">← Configure</a>
      <span class="rc-lp-nav-indicator">3 of 3</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency" class="rc-btn-path">Continue to Advanced Currency →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/docs/ramp-pricing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Ramp Pricing</a>
        <a href="https://docs.recurly.com/docs/hybrid-pricing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Hybrid Pricing</a>
        <a href="https://docs.recurly.com/docs/prepaid-account-balance" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Prepaid Account Balance</a>
        <a href="https://docs.recurly.com/docs/billing-models" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Pricing Models</a>
        <a href="https://docs.recurly.com/docs/subscription-ramp-pricing-export" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Ramp Pricing Export</a>
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