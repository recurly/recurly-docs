---
title: 'Advanced Analytics: Best practices & strategy'
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
.rc-accent-card.rc-accent-yellow { border-left: 4px solid var(--yellow); }
.rc-accent-card.rc-accent-orange { border-left: 4px solid var(--orange); }
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
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0 0 8px; }
.rc-step-content p:last-child { margin-bottom: 0; }
.rc-step-content strong { color: var(--darkgray); }

/* Thought question */
.rc-thought-q { background: var(--offblack); border-radius: 14px; padding: 36px 40px; margin: 40px 0; text-align: center; border: 1px solid rgba(255,255,255,0.08); }
.rc-thought-q-label { font-size: .72rem; font-weight: 700; letter-spacing: 1px; text-transform: uppercase; color: #FFD706; margin-bottom: 16px; display: block; }
.rc-thought-q h3 { font-size: 1.25rem; font-weight: 800; color: #FFFDF2 !important; line-height: 1.5; margin: 0 0 12px; max-width: 680px; margin-left: auto; margin-right: auto; }
.rc-thought-q p { font-size: .9rem; color: rgba(255,253,242,0.65) !important; line-height: 1.6; max-width: 580px; margin: 0 auto; }

/* Pitch card — capstone */
.rc-pitch-card { background: #0D0D0B !important; border-radius: 14px; padding: 36px 40px; text-align: center; margin: 0 0 40px; border: 1px solid rgba(255,255,255,0.08); }
.rc-pitch-emoji { font-size: 2.4rem; margin-bottom: 12px; }
.rc-pitch-card h3 { font-size: 1.1rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; color: #FFD706 !important; margin: 0 0 16px; }
.rc-pitch-quote { font-size: 1.05rem; color: #FFFDF2 !important; line-height: 1.7; max-width: 680px; margin: 0 auto; font-style: italic; }
.rc-pitch-quote strong { color: #ffffff !important; font-style: normal; }

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
  .rc-pitch-card { padding: 28px 24px; }
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
      <div class="rc-lp-hero-title"><h1>Advanced analytics — Strategy &amp; best practices</h1></div>
      <p>Build a measurement framework that closes the loop on everything you've configured — from plan design to pricing models, markets, and the metrics that signal when to iterate.</p>
      
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
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics-configure" class="rc-sticky-link">
              <span class="rc-step-badge">2</span> Where to Find It
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics-strategy" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Strategy &amp; Best Practices
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-sticky-link">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- Section 1: Building a Measurement Framework -->
    <div class="rc-lp-section">
      <h2>🏗️ Building a Measurement Framework for Your Portfolio</h2>
      <p>The hardest part of analytics isn't finding the data — it's knowing which questions to ask first. A P&P portfolio generates dozens of metrics. Most of them are interesting. A handful are actually useful for making decisions. The discipline is focusing on the latter.</p>
      <p>A practical framework for P&P analytics organizes metrics into three layers: <strong>financial health</strong> (is the portfolio generating the revenue it was designed to?), <strong>acquisition efficiency</strong> (is the pricing lowering the barrier to sign-up and converting trials to paid?), and <strong>retention signals</strong> (are customers staying, growing, or churning — and why?). Each layer has one or two lead indicators that, if healthy, typically mean the rest is working.</p>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Layer 1: Financial health — the one number that matters</h4>
        <p>Net MRR growth. Not gross MRR, not subscriber count, not expansion MRR in isolation — net. Net MRR = new + expansion + reactivation − contraction − churn. If this number is positive and growing, the portfolio is working. If it's positive but slowing, you have a growth problem. If it's negative, you have a retention problem, a pricing problem, or both. Everything else is context for understanding which one it is.</p>
        <p>Find this in <strong>Analytics → MRR Dashboard</strong>. Set a monthly review cadence and track the composition — not just the total. A portfolio with high expansion but also high churn is structurally fragile even if net MRR is positive today.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Layer 2: Acquisition efficiency — the funnel metric</h4>
        <p>Trial-to-paid conversion rate. This is the single clearest signal of whether your pricing's entry point is calibrated correctly. If your free tier or trial is converting at expected rates, your acquisition pricing is working. If it's declining, something in the entry experience — price, friction, perceived value, or trial length — needs attention. Track this in <strong>Analytics → Trials</strong> and watch it per plan, not just in aggregate, once you have enough volume per plan.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Layer 3: Retention signals — the early warning system</h4>
        <p>Voluntary churn rate by plan cohort. This is the hardest to get right analytically, because Recurly's native churn analytics are aggregate — they don't filter by plan or pricing model without export analysis. But it's the most important retention signal for P&P operators. A plan with 3% monthly voluntary churn has a fundamentally different problem than one with 0.8% — and no amount of acquisition optimization compensates for a high-churn pricing tier. Build the plan-level churn view in your external analytics tool using the Subscriptions export.</p>
      </div>
    </div>

    <!-- Section 2: The Minimum Viable Analytics Stack -->
    <div class="rc-lp-section">
      <h2>🛠️ The Minimum Viable Analytics Stack</h2>
      <p>You don't need a data warehouse and a dedicated analytics team to get meaningful visibility into a P&P portfolio. A minimum viable stack that covers the gaps in Recurly's native analytics can be surprisingly lean — the key is connecting the right data sources to the right questions.</p>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">📋</div>
        <div class="rc-callout-body">
          <strong>Start with a structured spreadsheet before building a BI dashboard</strong>
          <p>Before investing in a BI tool integration, run a manual monthly analysis for 2–3 months using the Subscriptions and Usage Records exports in a structured spreadsheet. This process forces you to define exactly which questions matter to your business and what the data structure looks like — both of which dramatically speed up any subsequent BI tool setup. Premature infrastructure is the enemy of insight.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">🔗</div>
        <div class="rc-callout-body">
          <strong>The three exports that power most P&P analytics</strong>
          <p>If you set up only three automated exports, make them these: <strong>Subscriptions</strong> (plan distribution, currency, segment codes, subscription status, trial dates), <strong>Subscriptions — Usage Records</strong> (usage data per account — essential for usage billing analytics), and <strong>Invoices</strong> (actual revenue per currency, add-on revenue attribution, ramp-period billing). These three, combined with your own customer data, answer the majority of P&P questions that Recurly's native dashboards don't.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">📊</div>
        <div class="rc-callout-body">
          <strong>Use Recurly's native MRR dashboard for the financial summary, external tools for the breakdown</strong>
          <p>There's no need to replicate what Recurly already does well. The MRR dashboard, Subscriber Retention cohort view, and Trial Performance dashboards are solid — use them as your financial summary layer. External tools should be built to answer the questions those dashboards can't: segment performance, usage patterns, ramp lifecycle, per-currency market health. Don't build a parallel MRR calculator; extend what exists.</p>
        </div>
      </div>
    </div>

    <!-- Section 3: Q&A -->
    <div class="rc-lp-section">
      <h2>❓ Common Questions from Merchants</h2>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"How do we know if our ramp pricing is causing subscribers to churn at the escalation point?"</h4>
            <p>This requires the <strong>Subscriptions — Ramp Pricing export</strong> combined with the <strong>Subscriptions export</strong>. Join them on subscription UUID, and filter for subscriptions that churned within 1–2 billing periods of reaching each ramp interval. If churn spikes consistently at the same ramp interval, that interval's price point is too high for your customer's willingness to pay at that stage of the relationship. The fix is usually either lowering that specific interval's price or adding a loyalty incentive that lands just before the escalation. This analysis is straightforward in a spreadsheet once you have the two exports.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"We have price segments for A/B testing. How do we measure which segment converts and retains better?"</h4>
            <p>The Subscriptions export includes the segment code on each subscription. Pull this export and group subscriptions by <code>plan_code</code> and <code>segment_code</code>. Then calculate trial conversion rate (using trial start and conversion date fields), voluntary churn rate (subscriptions that cancelled within defined periods), and average MRR per subscription for each segment group. This is your A/B analysis. The key discipline is holding the test long enough — 3–6 months minimum — before drawing conclusions about retention differences, since early churn patterns can be misleading.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Our usage billing revenue is higher than expected some months — how do we figure out which accounts are driving that?"</h4>
            <p>Pull the <strong>Usage Records export</strong> and group by subscription UUID and billing period. Sum the quantity logged per subscription per period and sort descending. The top accounts by usage volume are your revenue drivers — and, importantly, your best expansion candidates. Cross-reference these account UUIDs with your CRM or customer data to identify company size, industry, and CSM relationship status. High-usage accounts that aren't in any proactive CS motion are almost certainly under-leveraged. This is one of the most valuable queries in the entire P&P analytics stack.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Section 4: AI Strategy — Capstone -->
    <div class="rc-lp-section">
      <h2>🤖 AI Strategy — The Full P&P 201 Picture</h2>
      <p>Across this series, we've covered AI applications specific to each topic. Here's the synthesis: what does an AI-informed P&P operation look like end-to-end, and what's realistic to build at different stages of your analytics maturity?</p>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">🧠</div>
        <div class="rc-callout-body">
          <strong>Stage 1 (Months 1–6): Pattern recognition in export data</strong>
          <p>Before AI models, you need clean data. The first stage is establishing reliable export pipelines and running structured analysis — segment conversion comparisons, usage trend identification, ramp churn correlation. AI at this stage is most useful as a coding assistant: "write me a Python script to join these two exports and calculate churn rate by plan" is a genuinely useful prompt that accelerates analysis without requiring a data team.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">🎯</div>
        <div class="rc-callout-body">
          <strong>Stage 2 (6–18 months): Scoring and triggering</strong>
          <p>Once you have 6+ months of cohort data, you can build simple scoring models: usage-based churn risk scores (accounts whose usage is declining), expansion propensity scores (accounts approaching tier thresholds), ramp escalation risk flags (subscriptions approaching an interval that historically has high churn). These scores don't require complex ML — a scored spreadsheet updated weekly often performs comparably to a sophisticated model for a portfolio under a few thousand subscriptions. The key is connecting the score to a human action: a CSM outreach, an in-app message, a proactive pricing conversation.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">🔄</div>
        <div class="rc-callout-body">
          <strong>Stage 3 (18+ months): Closing the pricing feedback loop</strong>
          <p>At maturity, AI can drive the pricing iteration cycle itself. Trained on your full cohort history, a model can recommend: which plan prices to test next, which markets are underperforming relative to expected conversion curves, whether your ramp escalation schedule should be adjusted based on historical churn patterns, and which customer segments are candidates for new plan variants. This is the full feedback loop that P&P 201 was designed to make possible — not just configuring a pricing portfolio, but continuously improving it based on real customer behavior data.</p>
        </div>
      </div>
    </div>

    <!-- Pitch card — Capstone -->
    <div class="rc-pitch-card">
      <div class="rc-pitch-emoji">🎓</div>
      <h3>P&P 201 Complete</h3>
      <p class="rc-pitch-quote">"The merchants who grow fastest aren't the ones who set the right price once — they're the ones who <strong>built the system to know when the price is wrong</strong> and change it."</p>
    </div>

    <!-- Thought Question -->
    <div class="rc-thought-q">
      <span class="rc-thought-q-label">💭 Capstone Question</span>
      <h3>If you had to defend every pricing decision in your portfolio to a new CFO tomorrow, which ones could you back with data — and which ones are still running on intuition?</h3>
      <p>P&P 201 gave you the tools to build a sophisticated portfolio. Analytics is what earns you the right to keep operating it. The gap between what you can configure and what you can measure is the gap between a pricing strategy and a pricing experiment you haven't evaluated yet.</p>
    </div>

    <!-- OH CTA -->
    <div class="rc-oh-cta">
      <h4>🗓️ Close Out the Series with a Strategy Session</h4>
      <p>You've completed P&P 201. Bring your portfolio to a <strong>Customer Success Global Office Hours</strong> session — walk through what you've built, what you're measuring, and what you'd like to test next. Our CSMs have seen hundreds of pricing configurations and can help you prioritize what to optimize first.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <!-- Path nav -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics-configure" class="rc-btn-prev">← Where to Find It</a>
      <span class="rc-lp-nav-indicator">3 of 3</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-review" class="rc-btn-path">Continue to Review & Resources →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-analytics-overview" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Analytics Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/mmr-by-plan" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: MRR by Plan</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/data-imports-and-exports" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Data Exports</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/usages-records-export" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Usage Records Export</a>
        <a href="https://docs.recurly.com/docs/subscription-ramp-pricing-export" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Ramp Pricing Export</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-analytics-overview" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Analytics Settings</a>
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
