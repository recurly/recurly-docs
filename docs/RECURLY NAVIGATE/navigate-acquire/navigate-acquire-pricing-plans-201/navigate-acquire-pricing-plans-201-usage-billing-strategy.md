---
title: 'Usage Billing: Best practices & strategy'
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

/* Card grid */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: var(--yellow); box-shadow: 0 4px 16px rgba(255,215,6,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }
.rc-feature-tag { display: inline-block; margin-top: 4px; padding: 3px 10px; border-radius: 20px; font-size: .7rem; font-weight: 700; letter-spacing: .5px; background: var(--offblack); color: var(--yellow); width: fit-content; }

/* Q&A steps */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 20px 0 0; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num-q { width: 36px; height: 36px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0; }
.rc-step-content strong { color: var(--darkgray); }

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
.rc-accent-card.rc-accent-orange { border-left: 4px solid var(--orange); }
.rc-accent-card.rc-accent-yellow { border-left: 4px solid var(--yellow); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 12px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-accent-card ul { font-size: .9rem; color: var(--gray); line-height: 1.75; padding-left: 20px; margin: 0; }
.rc-accent-card ul li { margin-bottom: 4px; }
.rc-accent-card ul li strong { color: var(--darkgray); }

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
.rc-btn-complete { background: var(--brightgray); color: var(--offblack) !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--yellow); cursor: default; user-select: none; }

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
  .rc-card-grid { grid-template-columns: 1fr; }
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
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire
      </div>
      <div class="rc-lp-hero-title"><h1>Usage Billing: Strategy &amp; Best Practices</h1></div>
      <p>Build a usage model that lowers acquisition barriers, captures expansion revenue automatically, and stays measurable — even without native analytics in Recurly.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">61%</div>
          <div class="rc-hero-stat-label">of SaaS companies now offer usage-based pricing</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">3x</div>
          <div class="rc-hero-stat-label">higher net revenue expansion for usage-based businesses</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">100%</div>
          <div class="rc-hero-stat-label">of usage logging is API-driven — no manual entries</div>
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
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-sticky-link">
              <span class="rc-step-badge">1</span> Overview
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing-configure" class="rc-sticky-link">
              <span class="rc-step-badge">2</span> Configure
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing-strategy" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Strategy &amp; Best Practices
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-sticky-link">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- Section 1: Design Your Model -->
    <div class="rc-lp-section">
      <h2>🎯 Design Your Usage Model Before You Build It</h2>
      <p>The most common mistake with usage billing is jumping straight into configuration before making the foundational decisions that shape every downstream choice — your pricing structure, your free tier, your communication to customers, and your analytics setup. Spend time here first. Changing a pricing structure after customers are live is significantly harder than getting it right upfront.</p>
      <p>A well-designed usage model answers three questions clearly: What exactly are you measuring? How does consumption map to price? And what happens when a customer's usage is low — is there a floor, a free tier, or a base subscription below the usage component?</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon">📏</div>
          <h4>Choose a metric that customers understand</h4>
          <p>Your measured unit should be something your customers can see, control, and predict. If customers can't easily estimate their bill before they receive it, usage billing creates anxiety rather than alignment. "API calls" and "GB stored" are easy to grasp. "Processing units" or "credits" require more explanation — make sure your invoices and pricing pages do that work clearly.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">⚖️</div>
          <h4>Align your metric to customer value</h4>
          <p>The best usage metrics grow in proportion to the value the customer receives. If your product helps customers process payments, billing on payment volume makes intuitive sense — as they earn more, you earn more. If your metric grows without corresponding value (e.g., page loads that don't drive outcomes), customers will resent the charges and churn. The ideal metric is one where a customer's usage increase feels like a good problem to have.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🔮</div>
          <h4>Make billing predictable at scale</h4>
          <p>Pure pay-as-you-go creates bill anxiety for enterprise customers who need predictable costs for budget approval. Consider pairing usage billing with a base subscription (hybrid model) so customers have a predictable floor, then adding usage for overages. Alternatively, offer pre-purchase credit bundles at a discount — customers buy volume upfront, and usage draws from that balance.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🗺️</div>
          <h4>Document the model before you configure it</h4>
          <p>Write out exactly how a customer would be billed for three representative scenarios — low usage, average usage, and power usage. Share these examples with your CS, Sales, and Finance teams before configuration begins. If any of those conversations surfaces confusion or surprise, that's a signal to revisit the model. Invoice clarity is part of the product experience.</p>
        </div>
      </div>
    </div>

    <!-- Section 2: Free Tier Strategy -->
    <div class="rc-lp-section">
      <h2>🆓 Free Tier Strategy</h2>
      <p>A free usage tier is one of the most effective acquisition tools available for usage-based products, and it's built directly into Recurly's tiered pricing model. The mechanic is simple: the first tier of your add-on is priced at <strong>$0 per unit</strong> up to your chosen threshold. Customers pay nothing for usage below that level, then a per-unit rate kicks in above it.</p>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Free tiers reduce the activation barrier, not your revenue ceiling</strong>
          <p>A free tier doesn't reduce revenue for customers who generate meaningful value — those customers almost always exceed the threshold. What it does is remove the reason for hesitation at sign-up. A prospect who isn't sure if they'll get their money's worth will try a free-tier product and never try a paid-only one. Most of your revenue expansion still comes from the usage above the free threshold.</p>
        </div>
      </div>

      <p><strong>Setting the right free threshold:</strong> The free tier should cover enough usage for a customer to experience the core value of your product — a meaningful trial of real functionality, not just a token amount. Too low and it doesn't reduce conversion friction. Too high and you're giving away margin on customers who would have paid anyway. A useful benchmark: look at usage patterns for your lowest tier of paying customers today and set the free threshold slightly below that median.</p>

      <p><strong>What to track:</strong> Free tier effectiveness lives outside Recurly — you need to track activation-to-paid conversion rate by cohort, average time from first usage to first charged cycle, and whether customers who hit the free threshold convert or churn. None of these metrics come from Recurly natively. Set up this tracking in your external analytics before you launch a free tier.</p>
    </div>

    <!-- Section 3: Pricing Structures -->
    <div class="rc-lp-section">
      <h2>📐 Choosing Your Pricing Structure</h2>
      <p>Recurly supports four pricing structures for usage add-ons. Each has a different revenue and customer experience profile. Pick based on your business model and customer expectations, not on which is easiest to configure.</p>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Per Unit — Simple, Transparent, Easy to Explain</h4>
        <p>A fixed price per unit, every time. No complexity for the customer — they know exactly what each unit costs. Works well for low-volume, high-value transactions where customers can calculate their bill themselves. Combine with tiered pricing (lower rate at higher volume) to reward growth without requiring separate plans.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Tiered — Reward Volume, Enable Free Entry Points</h4>
        <p>Different price per unit depending on which tier the usage falls into. The first tier can be $0 (free threshold). Each unit is priced according to the tier it falls within. This is the right choice when you want to reduce entry friction with a free tier while still capturing revenue at higher consumption levels. Best for API-call and transaction-based models.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Volume — Bulk Discounts Based on Total Usage</h4>
        <p>The rate applied to all units is determined by the total quantity consumed in the period. If a customer uses 5,000 units and your volume break is at 1,000 units, all 5,000 units are charged at the 5,000-unit rate — not the lower tiers. This rewards high-volume customers with more aggressive discounts and is a common model for infrastructure and platform services where heavy users are your best customers.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Percentage — Align Revenue with Customer Success</h4>
        <p>A percentage of the dollar amount logged as usage. Ideal for payments platforms, marketplaces, and any business where your product enables financial transactions. As the merchant grows their volume, your revenue grows proportionally. This is the most compelling model for enterprise sales — "we only win when you win" — and the most straightforward to justify in renewal conversations.</p>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon">⚠️</div>
        <div class="rc-callout-body">
          <strong>Stairstep pricing: use with care</strong>
          <p>Stairstep pricing bills the entire period's usage at the rate corresponding to the highest tier reached — meaning a customer who just crosses a tier threshold sees a significant bill increase for that single extra unit. This can create jarring invoices and customer confusion. If you use stairstep pricing, communicate the tier breaks prominently in your pricing pages and pre-invoice notifications.</p>
        </div>
      </div>
    </div>

    <!-- Section 4: Q&A -->
    <div class="rc-lp-section">
      <h2>❓ Common Questions from Merchants</h2>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Can I offer a usage-only plan with no base fee — just pay for what you use?"</h4>
            <p>Yes. You can create a plan with a base price of $0 and a usage add-on for the consumption component. The subscriber activates the plan, your system logs usage throughout the period, and at cycle close Recurly invoices only for what was logged. There's no minimum charge. This is the cleanest implementation of true pay-as-you-go, and it's particularly effective for developer-facing products where customer acquisition is volume-driven. The tradeoff: without a base fee, you have no guaranteed revenue floor — usage analytics become critical for forecasting.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"What happens if our integration goes down and we miss logging some usage?"</h4>
            <p>That usage is permanently lost if the billing period closes before it's logged. Recurly does not allow backdating records into closed periods. This makes your logging pipeline's reliability a revenue integrity issue, not just a technical concern. Build retry logic, dead-letter queues, and alerting into your integration from day one. Consider logging usage to a durable store in your own system first, then posting to Recurly asynchronously — so that even if the Recurly API is temporarily unavailable, your usage data is preserved and can be replayed once connectivity is restored.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Can we charge a base subscription plus usage on the same plan?"</h4>
            <p>Absolutely — and this is often the best of both worlds. Set a recurring base price on the plan (for platform access, included features, or a seat count) and attach one or more usage add-ons for the variable components. The customer sees a predictable base charge on every invoice, with variable usage charges listed as separate line items below it. This hybrid model is the most common pattern in B2B SaaS because it gives Finance teams a predictable floor while capturing expansion from heavy users. Make sure your pricing page communicates both components clearly so customers aren't surprised at invoice time.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Section 5: External Analytics — Key Emphasis -->
    <div class="rc-lp-section">
      <h2>📊 Building Your Analytics Pipeline — Non-Negotiable</h2>
      <p>This is the most important operational step in any usage billing deployment, and the one most often treated as an afterthought. Recurly does not provide native dashboards for usage analytics. There are no charts showing usage trends, no per-account consumption views, and no alerts when usage approaches a tier threshold. The <strong>Subscriptions Usage Records export</strong> is your only data source from Recurly, and it's a flat file — not a live dashboard.</p>

      <div class="rc-callout rc-callout-caution">
        <div class="rc-callout-icon">🚨</div>
        <div class="rc-callout-body">
          <strong>Set up external tracking before you go live — not after</strong>
          <p>Every meaningful usage metric — activation rates, usage-to-paid conversion, at-risk accounts, expansion opportunities, pricing tier distribution — requires building outside Recurly. If you launch usage billing without this pipeline in place, you'll be flying blind. By the time you realize you need the data, you'll have months of history you can't retroactively analyze in a structured way.</p>
        </div>
      </div>

      <p><strong>Minimum viable analytics for usage billing:</strong></p>

      <div class="rc-accent-card rc-accent-orange">
        <h4>Track These Before Anything Else</h4>
        <ul>
          <li><strong>Usage by account, by period:</strong> Know which accounts are your heaviest consumers. These are your expansion opportunities and your highest-value customers — they should be on your CSM radar.</li>
          <li><strong>Free-to-paid conversion rate:</strong> What percentage of accounts on a free tier convert to paying? Track this by cohort (month of activation). If it drops, your free tier threshold may be set too high, or your product isn't delivering enough value at the free level.</li>
          <li><strong>Usage trend over time per account:</strong> Accounts whose usage is trending up month-over-month are candidates for plan upgrades or tier renegotiation. Accounts whose usage is declining are churn risks.</li>
          <li><strong>Tier distribution:</strong> What percentage of accounts sit in each pricing tier? If nearly everyone is in the free tier and rarely converts, you have a pricing problem. If no one ever exceeds the first paid tier, your tiers may be too broad.</li>
          <li><strong>Usage logging failures:</strong> Monitor your integration for failed API calls to Recurly. Any failure means lost revenue and gaps in your data. Alert on this in your observability stack.</li>
        </ul>
      </div>
    </div>

    <!-- Section 6: AI Strategy -->
    <div class="rc-lp-section">
      <h2>🤖 AI Strategy for Usage Billing</h2>
      <p>Usage billing generates richer behavioral data than any fixed-price model — and that data is exactly what makes AI-driven strategies tractable. Here's where intelligent automation has the most leverage.</p>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">🧠</div>
        <div class="rc-callout-body">
          <strong>Predict the right moment to upgrade a customer</strong>
          <p>The ideal upgrade trigger is when a customer is consistently hitting a tier threshold — using 80–95% of their included volume for two or more consecutive periods. An AI model trained on usage patterns can identify this cohort automatically and trigger a proactive outreach from your CS or Sales team before the customer manually requests a change. This converts an inbound ticket into an outbound expansion conversation.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">🔔</div>
        <div class="rc-callout-body">
          <strong>Flag at-risk accounts before they churn</strong>
          <p>A sustained drop in usage — especially one that crosses a tier boundary downward — is a leading churn indicator. An AI anomaly detector watching account-level usage can surface these accounts for human review before the customer decides to cancel. This is especially high-value for accounts where there's no CSM assigned, since the usage data becomes a proxy for engagement health.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💰</div>
        <div class="rc-callout-body">
          <strong>Use usage patterns to inform pricing optimization</strong>
          <p>With enough data, you can model what pricing structure would maximize revenue given your actual customer usage distribution. If most accounts cluster just below a tier threshold, that threshold may be set slightly too high — a small adjustment could move a significant portion of accounts into a paid tier. AI-assisted pricing analysis turns your usage export into a strategic lever, not just a billing record.</p>
        </div>
      </div>
    </div>

    <!-- Thought-Provoking Question -->
    <div class="rc-thought-q">
      <span class="rc-thought-q-label">💭 Something to Consider</span>
      <h3>If your billing perfectly reflected the value customers received, what would change about how you price — and who you'd target first with a usage model?</h3>
      <p>Usage billing is as much a product strategy as a technical configuration. The customers you choose to put on usage plans, and what you measure, signals something about what you believe drives value in your product.</p>
    </div>

    <!-- Office Hours CTA -->
    <div class="rc-oh-cta">
      <h4>🗓️ Bring Your Usage Model to Office Hours</h4>
      <p>Not sure whether your pricing structure is right, or whether to lead with a free tier? Join a <strong>Customer Success Global Office Hours</strong> session and walk through your model with a Recurly CSM. We can help you validate your approach against what's working for similar merchants — before you build it.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <!-- Path navigation -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing-configure" class="rc-btn-prev">← Configure</a>
      <span class="rc-lp-nav-indicator">3 of 3</span>
      <span class="rc-btn-complete">🎉 Path complete!</span>
    </div>

    <!-- Continue Your Journey -->
    <div class="rc-next-steps">
      <h3>🧭 Continue your journey</h3>
      <div class="rc-next-grid">

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models" class="rc-next-card">
          <div class="rc-next-card-tag">Recommended next</div>
          <div class="rc-next-card-icon">🧩</div>
          <h4>P&amp;P 201: Advanced Pricing Models</h4>
          <p>Usage billing pairs naturally with hybrid, ramp, and prepaid models. Explore how to layer these approaches for more sophisticated plan portfolios that serve a wider range of customer segments.</p>
          <div class="rc-next-card-arrow">Start path →</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-next-card">
          <div class="rc-next-card-tag">Explore the pillar</div>
          <div class="rc-next-card-icon">🎯</div>
          <h4>All Acquire paths</h4>
          <p>See every learning path in the Acquire pillar — from checkout optimization to pricing strategy, conversion tactics, and payment method expansion.</p>
          <div class="rc-next-card-arrow">View Acquire →</div>
        </a>

        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-next-card">
          <div class="rc-next-card-tag">Live session</div>
          <div class="rc-next-card-icon">🎙️</div>
          <h4>Global Office Hours</h4>
          <p>Bring your usage billing questions, free tier design, or pricing model decisions to our CSMs live. Sessions run weekly and are open to all merchants.</p>
          <div class="rc-next-card-arrow">Register →</div>
        </a>

      </div>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/usage-based-billing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Usage-Based Billing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/usage-based-pricing-guide" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Usage-Based Pricing Guide</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/billing-models" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Pricing Models</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/add-ons" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Add-Ons</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/usages-records-export" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Usage Records Export</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Join Global Office Hours</a>
      </div>
    </div>

    <!-- Footer -->
    <div class="rc-footer-nav">
      <div class="rc-footer-section">
        <span class="rc-footer-section-label">Usage Billing:</span>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-footer-link">Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing-configure" class="rc-footer-link">Configure</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing-strategy" class="rc-footer-link">Strategy &amp; Best Practices</a>
      </div>
      <div class="rc-footer-section">
        <span class="rc-footer-section-label">P&amp;P 201:</span>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-footer-link">P&amp;P 201 Hub</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-segmentation" class="rc-footer-link">Segmentation</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-footer-link">Account Hierarchy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-footer-link">Usage Billing</a>
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