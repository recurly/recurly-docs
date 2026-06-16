---
title: 'Account Hierarchy: Configuration'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
/* HOST-THEME BACKGROUND OVERRIDE */
body { background: #ffffff !important; }

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
  background: #ffffff;
}
.rc-guide * { box-sizing: border-box; }

/* Host-theme armor */
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:hover,
.rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

/* FA6 icon helpers */
.rc-fa-announce { color: var(--offblack); font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: var(--offblack); font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: var(--offblack); font-size: 1rem; }

/* Layout */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link { color: var(--gray); text-decoration: none !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Announcement bar */
.rc-announce-bar { display: none; background: var(--yellow); color: var(--offblack); align-items: center; justify-content: space-between; padding: 10px 20px; font-size: .88rem; font-weight: 600; border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4; }
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 10px; flex: 1; flex-wrap: wrap; }
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

/* Nav — non-sticky, open */
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
.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: var(--offblack) !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-sticky-link:hover .rc-step-badge { background: var(--yellow); color: var(--offblack); }
.rc-sticky-link-active { font-weight: 800; }
.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: var(--offblack) !important; }

/* Sections */
.rc-lp-section { margin-bottom: 48px; }
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

/* Steps */
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
.rc-step-content code { background: var(--brightgray); color: var(--offblack); padding: 2px 7px; border-radius: 4px; font-size: .82rem; font-family: monospace; }

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

/* Field table */
.rc-field-table { width: 100%; border-collapse: collapse; margin: 20px 0 32px; font-size: .88rem; }
.rc-field-table th { background: var(--offblack); color: var(--yellow); font-size: .72rem; font-weight: 800; letter-spacing: .8px; text-transform: uppercase; padding: 10px 14px; text-align: left; }
.rc-field-table td { padding: 12px 14px; border-bottom: 1px solid var(--brightgray); color: var(--darkgray); vertical-align: top; line-height: 1.5; }
.rc-field-table tr:last-child td { border-bottom: none; }
.rc-field-table tr:nth-child(even) td { background: var(--offwhite); }
.rc-field-table td:first-child { font-weight: 700; color: var(--offblack); white-space: nowrap; }
.rc-field-table td code { background: var(--brightgray); color: var(--offblack); padding: 1px 6px; border-radius: 4px; font-size: .8rem; font-family: monospace; }

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
.rc-guide a.rc-btn-prev { background: transparent; color: var(--offblack) !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--lightgray); transition: all .2s; }
.rc-guide a.rc-btn-prev:hover { border: 2px solid var(--offblack) !important; border-bottom: 2px solid var(--offblack) !important; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); }
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Resources */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--yellow); border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
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
  .rc-oh-cta { padding: 24px 20px; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-back-link">← Back to Path Start</a>
  </div>

  <div class="rc-content-wrap">

    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Join our CSMs for a live Pricing &amp; Packaging Q&amp;A.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- Hero -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Pricing &amp; Plans 201
      </div>
      <div class="rc-lp-hero-title"><h1>Account hierarchy — How to configure</h1></div>
      <p>A step-by-step walkthrough of creating parent and child accounts, setting billing responsibility, enabling Invoice Rollup, and verifying your hierarchy before going live with an enterprise customer.</p>
      
    </div>

    <!-- Navigation Menu — page 2 active -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt="Home"> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-sticky-link"><span class="rc-step-badge">1</span> Hierarchy: Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy-configure" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Hierarchy: Configure
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy-strategy" class="rc-sticky-link"><span class="rc-step-badge">3</span> Hierarchy: Strategy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- Building the hierarchy -->
    <div class="rc-lp-section" id="build-hierarchy">
      <h2><i class="fa-solid fa-diagram-project rc-fa-section"></i> Building a parent-child hierarchy in Recurly</h2>
      <p>Account Hierarchy is built from the child account — you link a child to a parent, not the other way around. The parent account is a standard Recurly account; no special configuration is needed on it before linking children. Start by identifying or creating both accounts in your Recurly admin.</p>

      <div class="rc-video-card">
        <div class="rc-video-header">
          <h4>Trail guide: Creating an account hierarchy in Recurly</h4>
          <span>Video coming soon</span>
        </div>
        <div class="rc-video-placeholder">
          <i class="fa-solid fa-circle-play" style="font-size: 2.5rem; color: var(--gray);"></i>
          <span>Walkthrough video will be added here</span>
        </div>
        <div class="rc-video-caption">A screencast showing how to link a child account to a parent, configure billing responsibility, view the hierarchy dashboard, and verify invoice ownership from both the parent and child account views.</div>
      </div>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Create or locate the parent account</h4>
            <p>The parent account is a standard Recurly account representing the top-level entity. Navigate to <strong>Accounts → New Account</strong> and create it as you would any other account — with a unique account code, name, email, and billing details. If the parent account already exists, locate it via <strong>Accounts → Search</strong>.</p>
            <p>The parent account's billing address will be used for tax calculations on any invoices billed to the parent. Make sure it reflects the correct billing entity before linking children.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Create or locate the child account</h4>
            <p>Create the child account the same way — <strong>Accounts → New Account</strong>. Give it a unique account code that reflects the entity it represents (a location code, department identifier, or subsidiary name). The child account holds its own subscriptions and service history, regardless of which account receives the invoices.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Link the child to the parent</h4>
            <p>From the child account's detail page, navigate to <strong>Account Information → Edit</strong>. In the Parent Account field, search for and select the parent account. Save the change — the relationship is now established.</p>
            <p>After saving, both accounts will reflect the hierarchy. The child account page shows a "Child" tag and a link to the parent. The parent account page shows a "Parent" tag, a count of associated child accounts, and a link to the full Account Hierarchy overview.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Set billing responsibility for the child</h4>
            <p>This is the most commercially significant configuration step. On the child account, find the <strong>Bill All Charges To</strong> setting and choose either <strong>Parent Account</strong> or <strong>This Account</strong>.</p>
            <p>Choosing <strong>Parent Account</strong>: all invoices, charges, credits, and payment information belong to the parent. The child has no payment method on file. Choosing <strong>This Account</strong>: the child manages its own billing independently — it just has a visible parent association for organizational context.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">5</div>
          <div class="rc-step-content">
            <h4>Add subscriptions to the child account</h4>
            <p>Subscriptions are created on child accounts — not on the parent. Navigate to the child account and create subscriptions via <strong>New Subscription</strong> in the admin UI, or via the Recurly Purchase or New Subscription API endpoints. If the child is configured to bill to the parent, all resulting invoices will appear on the parent account.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">6</div>
          <div class="rc-step-content">
            <h4>Repeat for each child account</h4>
            <p>Link each subsidiary, location, or entity as a separate child account. Each child is linked individually — there is no bulk import for hierarchy relationships. For large hierarchies, use the Recurly API's <code>PUT /accounts/{account_code}</code> endpoint and pass the <code>parent_account_code</code> field to establish the link programmatically.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">7</div>
          <div class="rc-step-content">
            <h4>Verify from the hierarchy dashboard</h4>
            <p>From the parent account, click <strong>View Account Hierarchy</strong>. This dashboard shows all child accounts, their associated subscriptions, and their invoices — filterable by whether charges are billed to the child or the parent. Verify that each child's billing responsibility is set correctly and that test subscriptions are generating invoices on the expected account.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Enabling Invoice Rollup -->
    <div class="rc-lp-section" id="invoice-rollup">
      <h2><i class="fa-solid fa-layer-group rc-fa-section"></i> Enabling Invoice Rollup</h2>
      <p>Invoice Rollup consolidates charges from all billed-to-parent children into a single parent invoice. It requires two things: Calendar Billing must be active on your site, and Invoice Rollup itself must be activated by the Recurly Support team. Neither is self-serve.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Contact Recurly Support to activate Invoice Rollup</h4>
            <p>Reach out to <a href="mailto:support@recurly.com">support@recurly.com</a> to request activation of Account Hierarchy — Invoice Rollup on your site. Include your site name and confirm that you understand the Calendar Billing dependency. Support will activate the feature and confirm when it's ready.</p>
            <p>Plan this step into your implementation timeline. For enterprise onboarding situations where a customer is expecting consolidated invoicing from day one, contact Support before the customer's subscription start date.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Align child billing dates with Calendar Billing</h4>
            <p>Invoice Rollup is powered by Calendar Billing — Recurly's feature that aligns all child account billing dates to match the parent account's billing date. When Invoice Rollup is activated, Calendar Billing automatically aligns billing dates across the hierarchy. Any one-time charges on parent or child accounts are included in the consolidated invoice at the next billing cycle.</p>
            <p>For child accounts with existing subscriptions at different billing dates, expect a proration adjustment at the point of alignment. Review your billing cycle timing with the customer before activating to avoid surprise charges.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Confirm consolidated invoices in sandbox</h4>
            <p>Before activating for a live enterprise customer, test the full Invoice Rollup flow in your Recurly sandbox. Create a parent account with two or more child accounts, each with a subscription billed to the parent. Advance the billing date and verify that a single consolidated invoice appears on the parent account with line items from each child — and that each line item clearly identifies the originating child account.</p>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon"><i class="fa-solid fa-circle-info"></i></div>
        <div class="rc-callout-body">
          <strong>Invoice Rollup changes how credits and coupons behave</strong>
          <p>When Invoice Rollup is active, credits and coupons applied to the parent account flow across all billed-to-parent children on the consolidated invoice. A credit issued for a service disruption affecting one child location will reduce the invoice for all children billed to that parent in the same cycle. Communicate this to your finance team and to the customer's procurement contact before activating.</p>
        </div>
      </div>
    </div>

    <!-- API table -->
    <div class="rc-lp-section" id="api">
      <h2><i class="fa-solid fa-code rc-fa-section"></i> Managing hierarchy via the API</h2>
      <p>For large hierarchies or automated onboarding flows, the admin UI becomes impractical. The Recurly API handles all hierarchy operations and is the right path for any implementation involving more than a handful of accounts.</p>

      <table class="rc-field-table">
        <thead>
          <tr>
            <th>Operation</th>
            <th>API endpoint</th>
            <th>Key parameter</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Link child to parent</td>
            <td><code>PUT /accounts/{account_code}</code></td>
            <td><code>parent_account_code</code> — the account code of the parent</td>
          </tr>
          <tr>
            <td>Set billing responsibility</td>
            <td><code>PUT /accounts/{account_code}</code></td>
            <td><code>bill_to</code> — set to <code>parent</code> or <code>self</code></td>
          </tr>
          <tr>
            <td>Remove parent relationship</td>
            <td><code>PUT /accounts/{account_code}</code></td>
            <td>Set <code>parent_account_code</code> to null or empty</td>
          </tr>
          <tr>
            <td>List child accounts</td>
            <td><code>GET /accounts/{account_code}/accounts</code></td>
            <td>Returns all child accounts linked to the given parent</td>
          </tr>
          <tr>
            <td>View hierarchy invoices</td>
            <td><code>GET /accounts/{account_code}/invoices</code></td>
            <td>Filter by <code>type</code> and check <code>account</code> vs. <code>billing_account</code> fields per line item</td>
          </tr>
        </tbody>
      </table>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>Both API v2 and v3 support hierarchy data</strong>
          <p>If your integration uses Recurly API v2, hierarchy data is available — you don't need to upgrade to v3 to use Account Hierarchy or Invoice Rollup. Invoice line items in both API versions include fields identifying the originating account and the billing account, so you can reconcile parent and child charges regardless of which API version your system uses.</p>
        </div>
      </div>
    </div>

    <!-- Gotchas -->
    <div class="rc-lp-section" id="gotchas">
      <h2><i class="fa-solid fa-triangle-exclamation rc-fa-section"></i> What to know before you go live</h2>

      <div class="rc-accent-card rc-accent-orange">
        <h4>Billing responsibility change affects new invoices only</h4>
        <p>If you change a child account's billing responsibility from "self" to "parent" (or vice versa), the change applies to invoices generated <em>after</em> the change. Existing open invoices on the child account are not reassigned. If you're migrating an existing customer to a consolidated billing model, align the change with a billing cycle boundary and communicate the transition to the customer's finance team in advance.</p>
      </div>

      <div class="rc-accent-card rc-accent-orange">
        <h4>Multi-jurisdiction tax warning for billed-to-parent accounts</h4>
        <p>When a child bills to the parent, Recurly calculates tax based on the <em>parent's</em> billing address — not the child's. If your enterprise customer has subsidiaries in different tax jurisdictions from the parent entity, you may be applying the wrong tax treatment to child charges. Review this with your customer's tax team before activating parent billing across a multi-jurisdiction hierarchy.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Invoice Rollup requires Calendar Billing alignment at first use</h4>
        <p>When Invoice Rollup is first activated on a site with existing subscriptions, Calendar Billing will align billing dates across the hierarchy. For children with mid-cycle subscriptions, this triggers a proration adjustment. Test this in your sandbox with representative subscription configurations before activating for a live enterprise customer — and discuss the billing cycle impact with the customer before their first consolidated invoice.</p>
      </div>
    </div>

    <!-- Path nav -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-btn-prev">← Overview</a>
      <span class="rc-lp-nav-indicator">2 of 3 · Account Hierarchy</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy-strategy" class="rc-btn-path">Next: Strategy &amp; best practices →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/docs/account-hierarchy-1" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Account Hierarchy</a>
        <a href="https://docs.recurly.com/docs/ah-invoice-rollup" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Invoice Rollup</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/accounts" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Accounts API</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
      </div>
    </div>

    <!-- Footer -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Micro-Path: Account Hierarchy:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-footer-link">Hierarchy: Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy-configure" class="rc-footer-link">Hierarchy: Configure</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy-strategy" class="rc-footer-link">Hierarchy: Strategy &amp; best practices</a>
        </div>
        <div class="rc-footer-section">
          <span class="rc-footer-label">Pricing &amp; Packaging 201:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-footer-link">P&amp;P 201 Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-segmentation" class="rc-footer-link">Segmentation</a>
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
