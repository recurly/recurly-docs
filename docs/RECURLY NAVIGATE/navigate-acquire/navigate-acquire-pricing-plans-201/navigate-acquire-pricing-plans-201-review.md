---
title: 'Pricing & Plans 201: Review & resources'
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

/* Nav — non-sticky, open */
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
.rc-sticky-link-active { background: rgba(0,0,0,0.12); font-weight: 800; }
.rc-sticky-link-active:hover { background: var(--offblack); color: var(--yellow) !important; }

/* Sections */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* Congratulatory banner */
.rc-congrats { background: var(--offblack); border-radius: 16px; padding: 44px 48px; text-align: center; margin-bottom: 48px; border: 2px solid rgba(255,215,6,0.3); }
.rc-congrats-emoji { font-size: 3rem; margin-bottom: 16px; line-height: 1; }
.rc-congrats h2 { font-size: 1.6rem; font-weight: 800; color: #FFD706 !important; margin: 0 0 14px; letter-spacing: .5px; }
.rc-congrats p { font-size: 1rem; color: #FFFDF2 !important; line-height: 1.7; max-width: 660px; margin: 0 auto 24px; opacity: .9; }
.rc-congrats-pills { display: flex; flex-wrap: wrap; gap: 8px; justify-content: center; margin-top: 4px; }
.rc-congrats-pill { background: rgba(255,215,6,0.15); border: 1px solid rgba(255,215,6,0.3); color: #FFD706 !important; font-size: .72rem; font-weight: 700; letter-spacing: .8px; text-transform: uppercase; padding: 5px 14px; border-radius: 20px; }

/* Question cards */
.rc-question-set { display: flex; flex-direction: column; gap: 20px; margin: 0 0 16px; }

/* MCQ card */
.rc-question-card { border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; }
.rc-question-header { background: var(--offblack); padding: 14px 20px; display: flex; align-items: center; gap: 14px; }
.rc-question-badge { width: 32px; height: 32px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-size: .8rem; font-weight: 800; flex-shrink: 0; }
.rc-question-meta { flex: 1; }
.rc-question-type-label { font-size: .65rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--lightgray); display: block; margin-bottom: 2px; }
.rc-question-topic { font-size: .78rem; font-weight: 600; color: var(--yellow); }
.rc-question-body { padding: 20px 24px; background: var(--offwhite); }
.rc-question-text { font-size: .95rem; font-weight: 600; color: var(--offblack); line-height: 1.55; margin: 0 0 16px; }
.rc-question-options { list-style: none; padding: 0; margin: 0 0 16px; display: flex; flex-direction: column; gap: 8px; }
.rc-question-options li { font-size: .9rem; color: var(--darkgray); line-height: 1.5; padding: 10px 14px; background: #fff; border: 1px solid var(--lightgray); border-radius: 7px; }
.rc-question-options li strong { color: var(--offblack); }

/* Answer reveal (details/summary — JS-free) */
details.rc-answer-reveal { border-top: 1px solid var(--lightgray); margin: 0 -24px -20px; }
details.rc-answer-reveal > summary { list-style: none; padding: 11px 24px; cursor: pointer; font-size: .82rem; font-weight: 700; color: var(--gray); display: flex; align-items: center; gap: 8px; user-select: none; transition: color .2s; }
details.rc-answer-reveal > summary::-webkit-details-marker { display: none; }
details.rc-answer-reveal > summary::marker { display: none; }
details.rc-answer-reveal > summary::before { content: '▶'; font-size: .6rem; color: var(--yellow); transition: transform .2s; }
details.rc-answer-reveal[open] > summary::before { transform: rotate(90deg); }
details.rc-answer-reveal > summary:hover { color: var(--offblack); }
.rc-answer-body { padding: 16px 24px 20px; background: rgba(255,215,6,0.07); border-top: 1px solid rgba(255,215,6,0.2); }
.rc-answer-correct { display: inline-flex; align-items: center; gap: 6px; font-size: .82rem; font-weight: 800; text-transform: uppercase; letter-spacing: .6px; color: var(--offblack); background: var(--yellow); padding: 4px 12px; border-radius: 20px; margin-bottom: 10px; }
.rc-answer-body p { font-size: .9rem; color: var(--darkgray); line-height: 1.6; margin: 0; }
.rc-answer-body p strong { color: var(--offblack); }

/* Open-ended question card */
.rc-question-card-open { border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; }
.rc-question-card-open .rc-question-header { background: var(--offblack); }
.rc-question-open-body { padding: 20px 24px; background: var(--brightgray); }
.rc-question-open-body .rc-question-text { margin: 0 0 14px; }
.rc-question-guidance { font-size: .88rem; color: var(--gray); line-height: 1.6; margin: 0; font-style: italic; border-top: 1px solid var(--lightgray); padding-top: 12px; }
.rc-question-guidance strong { color: var(--darkgray); font-style: normal; }

/* Callouts */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body > strong { color: var(--offblack); }

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

/* Resources — grouped by topic */
.rc-resources-block { background: var(--brightgray); border-left: 4px solid var(--yellow); border-radius: 10px; padding: 24px 28px; margin: 32px 0 0; }
.rc-resources-block h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 20px; }
.rc-resource-group { margin-bottom: 20px; }
.rc-resource-group:last-child { margin-bottom: 0; }
.rc-resource-group-label { font-size: .72rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: var(--offblack); margin-bottom: 8px; display: block; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 3px 20px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--yellow) !important; }
.rc-resource-divider { height: 1px; background: var(--lightgray); margin: 16px 0; opacity: 0.5; }

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
  .rc-next-grid { grid-template-columns: 1fr; }
  .rc-congrats { padding: 32px 24px; }
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
      <div class="rc-lp-hero-title"><h1>Pricing &amp; Plans 201 — Review &amp; resources</h1></div>
      <p>Six micro-paths. Eighteen pages. One complete advanced pricing and plans portfolio — built, tested, and ready to measure.</p>
      
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
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-review" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Review &amp; Resources
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-sticky-link">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- Congratulations -->
    <div class="rc-congrats">
      <div class="rc-congrats-emoji">🎓</div>
      <h2>You've Completed P&amp;P 201</h2>
      <p>You've moved well beyond flat-rate billing. You can segment customers by price point, structure account hierarchies, charge for what's actually consumed, build pricing that adapts over time, reach global markets in local currencies, and measure all of it with the right data sources. That's a sophisticated pricing and packaging capability — and one most subscription businesses take years to assemble.</p>
      <div class="rc-congrats-pills">
        <span class="rc-congrats-pill">✓ Segmentation</span>
        <span class="rc-congrats-pill">✓ Account Hierarchy</span>
        <span class="rc-congrats-pill">✓ Usage Billing</span>
        <span class="rc-congrats-pill">✓ Advanced Models</span>
        <span class="rc-congrats-pill">✓ Advanced Currency</span>
        <span class="rc-congrats-pill">✓ Advanced Analytics</span>
      </div>
    </div>

    <!-- Questions -->
    <div class="rc-lp-section">
      <h2>🧠 Check Your Understanding</h2>
      <p>Six questions — four multiple choice, two open-ended. Use them to confirm you've got the key concepts locked in before putting any of this into production.</p>

      <div class="rc-question-set">

        <!-- Q1: Usage Billing — backdating -->
        <div class="rc-question-card">
          <div class="rc-question-header">
            <div class="rc-question-badge">1</div>
            <div class="rc-question-meta">
              <span class="rc-question-type-label">Multiple Choice</span>
              <span class="rc-question-topic">MP9 — Usage Billing</span>
            </div>
          </div>
          <div class="rc-question-body">
            <p class="rc-question-text">Your usage logging system experienced a 4-hour outage on the last day of a customer's billing cycle. 12,000 API calls were not logged during that window. The billing cycle closed and an invoice was generated. What is the correct outcome?</p>
            <ul class="rc-question-options">
              <li><strong>A.</strong> Recurly automatically detects the gap and adjusts the invoice to account for estimated usage</li>
              <li><strong>B.</strong> You can submit the missing records up to 7 days after the cycle closes and Recurly will issue a revised invoice</li>
              <li><strong>C.</strong> The missing usage is permanently lost — it cannot be added to that closed billing period's invoice</li>
              <li><strong>D.</strong> The subscription enters a grace period and billing is paused until all records are reconciled</li>
            </ul>
            <details class="rc-answer-reveal">
              <summary>Reveal answer</summary>
              <div class="rc-answer-body">
                <span class="rc-answer-correct">✓ C is correct</span>
                <p>Recurly does not support backdating usage records into closed billing periods. Once a billing cycle closes and an invoice is generated, that period is sealed. Usage that wasn't logged before cycle close is permanently unrecoverable on that invoice. This makes your logging pipeline's reliability a revenue integrity issue — build retry logic and alerting into your integration from day one.</p>
              </div>
            </details>
          </div>
        </div>

        <!-- Q2: Ramp pricing — prerequisite -->
        <div class="rc-question-card">
          <div class="rc-question-header">
            <div class="rc-question-badge">2</div>
            <div class="rc-question-meta">
              <span class="rc-question-type-label">Multiple Choice</span>
              <span class="rc-question-topic">MP10 — Advanced Models</span>
            </div>
          </div>
          <div class="rc-question-body">
            <p class="rc-question-text">A merchant wants to configure ramp pricing on their Recurly account. Before opening the plan configuration, which Recurly feature must be confirmed as enabled — and may require contacting Support to activate?</p>
            <ul class="rc-question-options">
              <li><strong>A.</strong> Revenue Recognition Advanced</li>
              <li><strong>B.</strong> Only Bill What Changed (also known as Bill Only for Changes)</li>
              <li><strong>C.</strong> Account Hierarchy with Invoice Rollup</li>
              <li><strong>D.</strong> Multi-Currency Support</li>
            </ul>
            <details class="rc-answer-reveal">
              <summary>Reveal answer</summary>
              <div class="rc-answer-body">
                <span class="rc-answer-correct">✓ B is correct</span>
                <p><strong>Only Bill What Changed</strong> must be enabled on the Recurly account for ramp pricing to function. Accounts created before May 2018 also require <strong>Credit Invoices</strong> to be active. Additionally, ramp pricing may not be available on Starter or Pro tiers — contact Recurly Sales or Support to confirm eligibility before designing ramp-based plans.</p>
              </div>
            </details>
          </div>
        </div>

        <!-- Q3: Multi-currency — no auto conversion -->
        <div class="rc-question-card">
          <div class="rc-question-header">
            <div class="rc-question-badge">3</div>
            <div class="rc-question-meta">
              <span class="rc-question-type-label">Multiple Choice</span>
              <span class="rc-question-topic">MP11 — Advanced Currency</span>
            </div>
          </div>
          <div class="rc-question-body">
            <p class="rc-question-text">A merchant activates EUR as a currency in Recurly and confirms their gateway supports it. They have 15 active plans, all priced only in USD. A European customer attempts to subscribe to one of those plans in EUR. What happens?</p>
            <ul class="rc-question-options">
              <li><strong>A.</strong> Recurly automatically converts the USD price at the current exchange rate and charges the customer in EUR</li>
              <li><strong>B.</strong> The customer is charged in USD regardless of location, with currency conversion handled by their bank</li>
              <li><strong>C.</strong> The subscription cannot be created — the plan has no EUR price configured, so it is unavailable in that currency</li>
              <li><strong>D.</strong> The customer sees an estimated EUR price that updates daily based on live FX rates</li>
            </ul>
            <details class="rc-answer-reveal">
              <summary>Reveal answer</summary>
              <div class="rc-answer-body">
                <span class="rc-answer-correct">✓ C is correct</span>
                <p>Recurly does <strong>not</strong> automatically convert prices between currencies. Every currency price is set manually by the merchant on each plan. A plan without an explicit EUR price cannot be purchased in EUR — the transaction will fail. After activating a new currency, you must update every plan in your catalog with a price in that currency before customers in that market can subscribe.</p>
              </div>
            </details>
          </div>
        </div>

        <!-- Q4: Analytics — native vs. external -->
        <div class="rc-question-card">
          <div class="rc-question-header">
            <div class="rc-question-badge">4</div>
            <div class="rc-question-meta">
              <span class="rc-question-type-label">Multiple Choice</span>
              <span class="rc-question-topic">MP12 — Advanced Analytics</span>
            </div>
          </div>
          <div class="rc-question-body">
            <p class="rc-question-text">Which of the following analytics questions can be answered using Recurly's <em>native</em> Analytics dashboards — without any export analysis or external tooling?</p>
            <ul class="rc-question-options">
              <li><strong>A.</strong> Trial-to-paid conversion rate broken down by price segment code</li>
              <li><strong>B.</strong> Total MRR contributed by a specific plan, including expansion and contraction components</li>
              <li><strong>C.</strong> Usage consumption trends per account over the past 6 months</li>
              <li><strong>D.</strong> Monthly recurring revenue broken out by subscriber currency as a percentage of total ARR</li>
            </ul>
            <details class="rc-answer-reveal">
              <summary>Reveal answer</summary>
              <div class="rc-answer-body">
                <span class="rc-answer-correct">✓ B is correct</span>
                <p>The <strong>MRR by Plan</strong> dashboard in Recurly Analytics shows total MRR per plan with a full growth decomposition — new subscriptions, expansions, contractions, and churn — and supports drill-down to account-level specifics. The other three options all require external analysis: segment performance (A) requires joining segment codes from the Subscriptions export; usage trends (C) require the Usage Records export; per-currency MRR (D) requires combining the Invoices and Subscriptions exports in an external tool.</p>
              </div>
            </details>
          </div>
        </div>

        <!-- Q5: Thought-provoking — Segmentation + Analytics -->
        <div class="rc-question-card-open">
          <div class="rc-question-header">
            <div class="rc-question-badge" style="background: var(--brightgray); color: var(--offblack);">5</div>
            <div class="rc-question-meta">
              <span class="rc-question-type-label">Reflect &amp; Apply</span>
              <span class="rc-question-topic">MP7 + MP12 — Segmentation &amp; Analytics</span>
            </div>
          </div>
          <div class="rc-question-open-body">
            <p class="rc-question-text">You've run a 90-day A/B price test using two segments on your core plan: Segment A at $79/month and Segment B at $59/month. Trial-to-paid conversion rates are nearly identical for both. Your CEO asks which price to standardize on. What additional metric would determine the right answer — and exactly where in Recurly would you find the data to calculate it?</p>
            <p class="rc-question-guidance"><strong>Consider:</strong> Conversion rate alone doesn't tell you which segment is more valuable over time. The critical metric is <strong>voluntary churn rate over the 90-day cohort</strong> — which price point retains customers better? Pull the Subscriptions export, filter by segment code, and calculate churn rate per segment cohort. Also worth modeling: <strong>lifetime value</strong> per segment (average MRR × inverse churn rate). A segment that converts at the same rate but retains 3 months longer is worth meaningfully more than its headline price suggests. If $79 retains better, standardize there. If both retain identically, the lower price is only advantageous if it opens a meaningfully larger market.</p>
          </div>
        </div>

        <!-- Q6: Thought-provoking — Full synthesis -->
        <div class="rc-question-card-open">
          <div class="rc-question-header">
            <div class="rc-question-badge" style="background: var(--brightgray); color: var(--offblack);">6</div>
            <div class="rc-question-meta">
              <span class="rc-question-type-label">Synthesis</span>
              <span class="rc-question-topic">Full P&amp;P 201 Series</span>
            </div>
          </div>
          <div class="rc-question-open-body">
            <p class="rc-question-text">A B2B SaaS company currently has one flat-rate plan at $49/month. They want to accomplish three things: expand into European and LATAM markets, capture more revenue from their most active power users, and reduce churn from customers who cancel because monthly bills feel unpredictable. Drawing on P&P 201, propose a pricing architecture using at least three features from the series. Describe the role each feature plays and name one metric you'd track to know if it's working.</p>
            <p class="rc-question-guidance"><strong>One possible architecture:</strong> <strong>Hybrid Pricing (MP10)</strong> — a $49 base plan covering platform access + a usage add-on for API calls beyond an included free tier. This captures power-user revenue automatically without surprising casual users; track <em>expansion MRR from usage overages</em>. <strong>Ramp Pricing (MP10)</strong> — an introductory period at $29 for the first 3 months reducing "unpredictable bill" anxiety at acquisition; track <em>churn rate at ramp escalation</em> to confirm the price increase doesn't cause exits. <strong>Multi-Currency (MP11)</strong> — explicit EUR and BRL pricing reflecting local purchasing power (not spot FX rates); track <em>trial-to-paid conversion by currency</em> to confirm each market entry point is calibrated correctly. <strong>Advanced Analytics (MP12)</strong> — Subscriptions + Usage Records exports feeding a BI tool to see plan distribution, segment performance, and per-market churn; the baseline analytics required to know if the above decisions are working.</p>
          </div>
        </div>

      </div><!-- /.rc-question-set -->

      <div class="rc-callout rc-callout-tip" style="margin-top: 32px;">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>These questions make great discussion starters at Office Hours</strong>
          <p>Especially Q5 and Q6 — if you're unsure how your specific business would answer either of them, bring them to a Global Office Hours session. Recurly CSMs regularly help merchants think through these exact trade-offs with real plan catalog data.</p>
        </div>
      </div>
    </div>

    <!-- Path nav -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics-strategy" class="rc-btn-prev">← Advanced Analytics</a>
      <span class="rc-lp-nav-indicator">Series complete</span>
      <span class="rc-btn-complete">🎉 P&amp;P 201 complete!</span>
    </div>

    <!-- Continue Your Journey -->
    <div class="rc-next-steps">
      <h3>🧭 Continue your journey</h3>
      <div class="rc-next-grid">

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-next-card">
          <div class="rc-next-card-tag">Recommended next</div>
          <div class="rc-next-card-icon">🛡️</div>
          <h4>Navigate: Retain</h4>
          <p>Your analytics will surface customers at risk of churning. The Retain pillar teaches you exactly what to do about it — dunning strategy, pause flows, cancel saves, and Account Updater — to protect the subscriber base your pricing built.</p>
          <div class="rc-next-card-arrow">Explore Retain →</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-next-card">
          <div class="rc-next-card-tag">Explore the pillar</div>
          <div class="rc-next-card-icon">🎯</div>
          <h4>All Acquire paths</h4>
          <p>See every learning path in the Acquire pillar — from checkout optimization to conversion tactics and payment method expansion beyond what you've covered here.</p>
          <div class="rc-next-card-arrow">View Acquire →</div>
        </a>

        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-next-card">
          <div class="rc-next-card-tag">Live session</div>
          <div class="rc-next-card-icon">🎙️</div>
          <h4>Global Office Hours</h4>
          <p>Bring your completed P&P 201 portfolio to our CSMs live. Let's review what you've built and map out what to prioritize for your next pricing iteration.</p>
          <div class="rc-next-card-arrow">Register →</div>
        </a>

      </div>
    </div>

    <!-- Resources — all P&P 201 sources -->
    <div class="rc-resources-block">
      <h3>📚 All P&amp;P 201 Resources</h3>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Segmentation (MP7)</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Plans &amp; Price Segments</a>
          <a href="https://docs.recurly.com/docs/billing-models" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Pricing Models</a>
        </div>
      </div>

      <div class="rc-resource-divider"></div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Account Hierarchy (MP8)</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/account-hierarchy-1" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Account Hierarchy</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/ah-invoice-rollup" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Invoice Rollup</a>
        </div>
      </div>

      <div class="rc-resource-divider"></div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Usage Billing (MP9)</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/usage-based-billing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Usage-Based Billing</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/usage-based-pricing-guide" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Usage-Based Pricing Guide</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/add-ons" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Add-Ons</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/usages-records-export" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Usage Records Export</a>
        </div>
      </div>

      <div class="rc-resource-divider"></div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Advanced Models (MP10)</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/docs/ramp-pricing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Ramp Pricing</a>
          <a href="https://docs.recurly.com/docs/hybrid-pricing" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Hybrid Pricing</a>
          <a href="https://docs.recurly.com/docs/prepaid-account-balance" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Prepaid Account Balance</a>
          <a href="https://docs.recurly.com/docs/subscription-ramp-pricing-export" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Ramp Pricing Export</a>
        </div>
      </div>

      <div class="rc-resource-divider"></div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Advanced Currency (MP11)</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/docs/currencies" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Currencies</a>
          <a href="https://docs.recurly.com/docs/currency-support-by-gateway" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Currency Support by Gateway</a>
          <a href="https://docs.recurly.com/docs/gateway-configuration" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Multiple Gateway Configuration</a>
        </div>
      </div>

      <div class="rc-resource-divider"></div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Advanced Analytics (MP12)</span>
        <div class="rc-resource-links">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-analytics-overview" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Analytics Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/mmr-by-plan" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: MRR by Plan</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/data-imports-and-exports" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Data Exports</a>
        </div>
      </div>

      <div class="rc-resource-divider"></div>

      <div class="rc-resource-group">
        <span class="rc-resource-group-label">Support &amp; Live Learning</span>
        <div class="rc-resource-links">
          <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
          <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Join Global Office Hours</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-resource-link">🗺️ P&amp;P 201 Hub — full series overview</a>
        </div>
      </div>

    </div>

    <!-- Footer -->
    <div class="rc-footer-nav">
      <div class="rc-footer-section">
        <span class="rc-footer-section-label">P&amp;P 201:</span>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-footer-link">P&amp;P 201 Hub</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-segmentation" class="rc-footer-link">Segmentation</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-footer-link">Account Hierarchy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-footer-link">Usage Billing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models" class="rc-footer-link">Advanced Models</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency" class="rc-footer-link">Advanced Currency</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics" class="rc-footer-link">Advanced Analytics</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-review" class="rc-footer-link">Review &amp; Resources</a>
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