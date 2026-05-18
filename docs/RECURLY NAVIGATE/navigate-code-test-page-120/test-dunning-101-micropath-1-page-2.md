---
title: 'TEST: Dunning 101, Micropath 1, Page 2'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
/* Base CSS omitted for brevity - exactly the same as Page 1 */
html { scroll-behavior: smooth; scroll-padding-top: 80px; }
.rc-guide { --yellow:#FFD706; --orange:#FF8200; --offblack:#0D0D0B; --darkgray:#32312D; --gray:#807D73; --lightgray:#CCC9B8; --brightgray:#F1EFE3; --offwhite:#FFFDF2; --retain:#FF9D88; font-family:'Segoe UI',system-ui,sans-serif; color:var(--darkgray); }
.rc-guide * { box-sizing: border-box; }
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link { color: var(--gray); text-decoration: none !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }
.rc-guide a, .rc-guide a:link, .rc-guide a:visited, .rc-guide a:hover, .rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

/* Hero */
.rc-hero { background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)), url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center; background-color: var(--offblack); background-size: cover; color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0; }
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,157,136,0.20); border: 1px solid rgba(255,157,136,0.45); color: #FF9D88; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: var(--lightgray); line-height: 1.6; }

/* Non-Sticky Expanded Nav */
details.rc-sticky-nav-wrap { position: relative; z-index: 1; background-color: var(--retain); box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px 0; border-radius: 12px; border: 1px solid rgba(0,0,0,0.08); overflow: hidden; }
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
details.rc-sticky-nav-wrap > summary::-webkit-details-marker, details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: var(--offblack); }
.rc-nav-chevron { font-size: .72rem; color: var(--offblack); opacity: 0.55; line-height: 1; transition: transform 0.25s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
.rc-sticky-link { color: var(--offblack) !important; text-decoration: none !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; }
.rc-sticky-link:hover { background: var(--offblack); color: var(--yellow) !important; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-sticky-link:hover .rc-step-badge { background: var(--yellow); color: var(--offblack); }
.rc-sticky-link-active { background: rgba(0,0,0,0.12); font-weight: 800; }
.rc-sticky-link-active:hover { background: var(--offblack); color: var(--yellow) !important; }

/* Content Elements */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h3 { font-size: 1.2rem; font-weight: 800; margin: 32px 0 16px; color: var(--offblack); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* Card Grids */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 24px 0; }
.rc-card-grid-3col { grid-template-columns: repeat(3, 1fr); }
.rc-feature-card { background: var(--offblack); border: 1px solid var(--darkgray); border-radius: 12px; padding: 24px; display: flex; flex-direction: column; gap: 8px; }
.rc-feature-card h4 { font-size: 1.05rem; font-weight: 800; color: var(--yellow); margin: 0; }
.rc-feature-card p { font-size: .9rem; color: var(--lightgray); line-height: 1.55; margin: 0; }

/* Result Cards */
.rc-result-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; display: flex; flex-direction: column; }
.rc-result-card .rc-stat { font-size: 1.8rem; font-weight: 800; color: var(--offblack); display: block; margin-bottom: 8px; line-height: 1; }
.rc-result-card .rc-tag { align-self: flex-start; background: var(--yellow); color: var(--offblack); font-size: .75rem; font-weight: 800; text-transform: uppercase; letter-spacing: 0.5px; padding: 4px 12px; border-radius: 20px; margin-bottom: 12px; }
.rc-result-card p { font-size: .88rem; color: var(--darkgray); margin: 0; line-height: 1.55; }

/* Accent Card */
.rc-accent-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 20px 0; }
.rc-accent-card.rc-accent-retain { border-left: 4px solid var(--retain); }
.rc-accent-card h4 { font-size: 1.1rem; font-weight: 800; color: var(--offblack); margin: 0 0 8px; }
.rc-accent-card p { font-size: .95rem; color: var(--darkgray); line-height: 1.65; margin: 0; }

/* Path Navigation */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); }
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-btn-prev { background: transparent; color: var(--offblack) !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--lightgray); transition: all .2s; }
.rc-guide a.rc-btn-prev:hover { border: 2px solid var(--offblack) !important; border-bottom: 2px solid var(--offblack) !important; }

/* Footer Nav */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rc-footer-link { color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; }
.rc-footer-link:hover { color: var(--orange); }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-card-grid, .rc-card-grid-3col { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">
  <div class="rc-top-nav">
    <a href="/docs/dunning-101-overview" class="rc-back-link">← Back to Path Start</a>
  </div>

  <div class="rc-content-wrap">
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt="Retain"> RETAIN
      </div>
      <div class="rc-lp-hero-title">
        <h1>Understanding Dunning</h1>
      </div>
      <p>How the automated recovery process works behind the scenes.</p>
    </div>

    <details class="rc-sticky-nav-wrap" open>
      <summary><span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span></summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="/docs/understanding-dunning-1" class="rc-sticky-link"><span class="rc-step-badge">1</span> How it Works</a>
            <a href="/docs/understanding-dunning-2" class="rc-sticky-link rc-sticky-link-active"><img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt="Current Page"> Why it Matters</a>
            <a href="/docs/understanding-dunning-3" class="rc-sticky-link"><span class="rc-step-badge">3</span> Your Revenue Toolkit</a>
          </div>
        </div>
      </div>
    </details>

    <div class="rc-lp-section">
      <h2>📈 Why it Matters</h2>
      <p>Payment failures are a normal part of running a subscription business — industry-wide, 5–10% of subscription payments fail on first attempt. What separates high-performing businesses is what happens next.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <h4>3–5% uplift is the norm</h4>
          <p>Recurly customers typically see a 3–5% uplift in dunning recovery rate after following the 10 optimization tips — from changes that take a few hours to implement.</p>
        </div>
        <div class="rc-feature-card">
          <h4>Passive churn is the hidden problem</h4>
          <p>Passive churn — losing subscribers due to failed payments rather than intent — can account for up to 40% of total churn. These are customers who want to stay subscribed.</p>
        </div>
      </div>

      <h3>Real Customer Results</h3>
      <div class="rc-card-grid rc-card-grid-3col">
        <div class="rc-result-card">
          <span class="rc-stat">+12%</span>
          <span class="rc-tag">Branding & Window</span>
          <p>Enhanced email branding, updated dunning window length, and optimized communication frequency.</p>
        </div>
        <div class="rc-result-card">
          <span class="rc-stat">+11%</span>
          <span class="rc-tag">Window Extension</span>
          <p>Extended the dunning window by 13 days and added emails reminding customers of the value they would lose.</p>
        </div>
        <div class="rc-result-card">
          <span class="rc-stat">+8%</span>
          <span class="rc-tag">Email Frequency</span>
          <p>Modified window length and adjusted frequency — leaving more days between each message.</p>
        </div>
      </div>

      <div class="rc-accent-card rc-accent-retain">
        <h4>+279% recovery revenue in one month</h4>
        <p>My Music Workshop implemented all 10 dunning best practices from scratch and saw a 279% increase in dunning recovery revenue in their first month.</p>
      </div>
    </div>

    <div class="rc-lp-nav">
      <a href="/docs/understanding-dunning-1" class="rc-btn-prev">← How it Works</a>
      <span class="rc-lp-nav-indicator">2 of 3</span>
      <a href="/docs/understanding-dunning-3" class="rc-btn-path">Next: Your Revenue Toolkit →</a>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Micro-Path: Understanding Dunning:</span>
          <a href="/docs/understanding-dunning-1" class="rc-footer-link">How it Works</a>
          <a href="/docs/understanding-dunning-2" class="rc-footer-link">Why it Matters</a>
          <a href="/docs/understanding-dunning-3" class="rc-footer-link">Your Revenue Toolkit</a>
        </div>
        <div class="rc-footer-utility">
          <a href="/docs/navigate-home" class="rc-footer-link"><img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt="Home"> Navigate Home</a>
          <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
        </div>
      </div>
    </div>
  </div>
</div>
`}</HTMLBlock>

<br />
