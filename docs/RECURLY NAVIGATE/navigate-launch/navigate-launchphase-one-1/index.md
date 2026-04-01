---
title: 'Launchpad Phase 1: Optimize'
deprecated: false
hidden: true
metadata:
  robots: index
next:
  description: |
    Click "Section 1: Final Production Testing" to continue the course. 
  pages:
    - slug: final-production-testing
      title: 'Section 1: Final Production Testing'
      type: basic
---
<HTMLBlock>{`
<style>
  .rc-guide {
    --yellow: #FFD706;
    --orange: #FF8200;
    --vermillion: #FF5810;
    --offblack: #0D0D0B;
    --darkgray: #32312D;
    --gray: #807D73;
    --lightgray: #CCC9B8;
    --brightgray: #F1EFE3;
    --offwhite: #FFFDF2;
    font-family: 'Segoe UI', system-ui, sans-serif;
  }

  .rc-hero {
    background: var(--offblack);
    color: #fff;
    padding: 56px 40px 48px;
    text-align: center;
    border-radius: 16px;
    margin-bottom: 0;
  }

  .rc-badge {
    display: inline-block;
    background: var(--yellow);
    color: var(--offblack);
    border-radius: 20px;
    padding: 6px 18px;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-bottom: 20px;
  }

  .rc-hero h1 {
    font-size: 2.4rem;
    font-weight: 800;
    line-height: 1.15;
    margin: 0 0 14px;
    color: var(--offwhite);
  }

  .rc-hero > p {
    font-size: 1.05rem;
    opacity: 0.8;
    max-width: 700px;
    margin: 0 auto 32px;
    color: var(--lightgray);
  }

  .rc-hero-stats {
    display: flex;
    justify-content: center;
    gap: 40px;
    flex-wrap: wrap;
  }

  .rc-num {
    font-size: 1.8rem;
    font-weight: 800;
    color: var(--yellow);
  }

  .rc-lbl {
    font-size: 0.8rem;
    color: var(--lightgray);
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  .rc-nav {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin: 24px 0 28px;
  }

  .rc-nav a {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 14px;
    border-radius: 12px;
    border: 1px solid var(--lightgray);
    background: #fff;
    color: var(--darkgray);
    text-decoration: none;
    font-size: 0.88rem;
    font-weight: 700;
    transition: border-color 0.2s, box-shadow 0.2s, background 0.2s, color 0.2s;
  }

  .rc-nav a:hover {
    border-color: var(--yellow);
    box-shadow: 0 2px 8px rgba(255, 215, 6, 0.2);
    color: var(--offblack);
    text-decoration: none;
  }

  .rc-nav a.rc-active {
    background: var(--yellow);
    border-color: var(--yellow);
    color: var(--offblack);
    box-shadow: 0 2px 10px rgba(255, 215, 6, 0.25);
  }

  .rc-snum {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 24px;
    height: 24px;
    border-radius: 50%;
    background: var(--offblack);
    color: var(--yellow);
    font-size: 12px;
    font-weight: 700;
    flex-shrink: 0;
  }

  .rc-sec {
    margin-bottom: 56px;
  }

  .rc-sec-header {
    display: flex;
    align-items: flex-start;
    gap: 20px;
    margin-bottom: 32px;
  }

  .rc-sec-icon {
    width: 56px;
    height: 56px;
    border-radius: 16px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 26px;
    flex-shrink: 0;
    background: var(--yellow);
  }

  .rc-sec-header h2 {
    font-size: 1.7rem;
    font-weight: 800;
    margin: 0 0 6px;
    color: var(--offblack);
  }

  .rc-sec-header > div > p {
    color: var(--gray);
    font-size: 0.95rem;
    line-height: 1.5;
    margin: 0;
  }

  .rc-card {
    background: var(--offwhite);
    border-radius: 16px;
    padding: 28px;
    border: 1px solid var(--lightgray);
    margin-bottom: 24px;
  }

  .rc-subhead {
    font-size: 1rem;
    font-weight: 700;
    margin: 0 0 16px;
    color: var(--offblack);
  }

  .rc-3col {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 14px;
    margin-bottom: 24px;
  }

  .rc-wi {
    background: var(--offwhite);
    border-radius: 14px;
    padding: 20px;
    border: 1px solid var(--lightgray);
    text-align: center;
  }

  .rc-wi-icon {
    font-size: 30px;
    margin-bottom: 10px;
  }

  .rc-wi h4 {
    font-size: 0.88rem;
    font-weight: 700;
    margin: 0 0 5px;
    color: var(--offblack);
  }

  .rc-wi p {
    font-size: 0.8rem;
    color: var(--gray);
    line-height: 1.5;
    margin: 0;
  }

  .rc-phase-banner {
    border-radius: 16px;
    padding: 28px 32px;
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 20px;
  }

  .rc-phase-banner.phase1 {
    background: var(--offblack);
    border: 2px solid var(--yellow);
  }

  .rc-phase-banner.phase2 {
    background: var(--darkgray);
    border: 2px solid var(--orange);
  }

  .rc-phase-icon {
    font-size: 36px;
    flex-shrink: 0;
  }

  .rc-phase-banner h3 {
    font-size: 1.05rem;
    font-weight: 800;
    color: var(--yellow);
    margin: 0 0 4px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  .rc-phase-banner.phase2 h3 {
    color: var(--orange);
  }

  .rc-phase-banner p {
    font-size: 0.88rem;
    color: var(--lightgray);
    margin: 0;
    line-height: 1.5;
  }

  .rc-phase-weeks {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    margin-top: 10px;
  }

  .rc-week-chip {
    display: inline-flex;
    align-items: center;
    padding: 4px 12px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: 700;
    background: rgba(255, 215, 6, 0.15);
    color: var(--yellow);
    border: 1px solid rgba(255, 215, 6, 0.3);
  }

  .rc-phase-banner.phase2 .rc-week-chip {
    background: rgba(255, 130, 0, 0.15);
    color: var(--orange);
    border-color: rgba(255, 130, 0, 0.3);
  }

  .rc-journey {
    display: flex;
    overflow-x: auto;
    padding-bottom: 8px;
    gap: 0;
  }

  .rc-jstep {
    flex: 1;
    min-width: 90px;
    text-align: center;
    position: relative;
  }

  .rc-jstep::after {
    content: '→';
    position: absolute;
    right: -12px;
    top: 10px;
    font-size: 18px;
    color: var(--lightgray);
  }

  .rc-jstep:last-child::after {
    display: none;
  }

  .rc-jdot {
    width: 38px;
    height: 38px;
    border-radius: 50%;
    background: var(--offblack);
    color: var(--yellow);
    font-size: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 6px;
  }

  .rc-jlbl {
    font-size: 0.7rem;
    font-weight: 700;
    color: var(--darkgray);
    line-height: 1.3;
  }

  .rc-tip {
    background: var(--offwhite);
    border: 2px solid var(--yellow);
    border-radius: 14px;
    padding: 20px 24px;
    margin-bottom: 24px;
    display: flex;
    gap: 16px;
    align-items: flex-start;
  }

  .rc-tipicon {
    font-size: 24px;
    flex-shrink: 0;
  }

  .rc-tip h4 {
    font-size: 0.82rem;
    font-weight: 700;
    color: var(--offblack);
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin: 0 0 4px;
  }

  .rc-tip p {
    font-size: 0.87rem;
    color: var(--darkgray);
    line-height: 1.55;
    margin: 0;
  }

  .rc-warning {
    background: #FFF8E6;
    border: 1px solid var(--orange);
    border-radius: 14px;
    padding: 16px 20px;
    margin-bottom: 24px;
    display: flex;
    gap: 14px;
    align-items: flex-start;
  }

  .rc-wicon {
    font-size: 20px;
    flex-shrink: 0;
  }

  .rc-warning p {
    font-size: 0.87rem;
    color: var(--darkgray);
    line-height: 1.55;
    margin: 0;
  }

  .rc-sec-nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
    margin-top: 24px;
    flex-wrap: wrap;
  }

  .rc-btn-prev,
  .rc-btn-next,
  .rc-btn-disabled,
  .rc-link-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 11px 18px;
    border-radius: 10px;
    font-weight: 700;
    font-size: 0.88rem;
    text-decoration: none;
    border: 1px solid var(--lightgray);
  }

  .rc-btn-prev {
    background: #fff;
    color: var(--darkgray);
  }

  .rc-btn-next {
    background: var(--yellow);
    color: var(--offblack);
    border-color: var(--yellow);
  }

  .rc-btn-disabled {
    background: var(--brightgray);
    color: var(--gray);
    cursor: default;
  }

  .rc-link-btn {
    gap: 8px;
    background: var(--yellow);
    color: var(--offblack);
    margin: 0 8px 8px 0;
  }

  .rc-link-sec {
    background: var(--offwhite);
    color: var(--darkgray);
    border: 1px solid var(--lightgray);
  }

  .rc-link-sec:hover {
    background: var(--brightgray);
  }

  @media (max-width: 640px) {
    .rc-hero h1 {
      font-size: 1.7rem;
    }

    .rc-3col {
      grid-template-columns: 1fr;
    }

    .rc-hero {
      padding: 36px 20px 32px;
    }

    .rc-hero-stats {
      gap: 20px;
    }

    .rc-nav,
    .rc-sec-nav,
    .rc-sec-header {
      flex-direction: column;
    }

    .rc-sec-nav {
      align-items: stretch;
    }

    .rc-phase-banner {
      flex-direction: column;
      gap: 12px;
    }
  }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">🚀 Navigate Launchpad</div>
    <h1>Welcome to Recurly Navigate Launchpad</h1>
    <p>Your 90-day success program to optimize your Recurly setup, master your metrics, and build a thriving subscription business from day one.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">90</div><div class="rc-lbl">Days to Success</div></div>
      <div><div class="rc-num">2</div><div class="rc-lbl">Phases</div></div>
      <div><div class="rc-num">12</div><div class="rc-lbl">Weekly Modules</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a class="rc-active" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-welcome"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-production-testing"><span class="rc-snum">1</span>Production Testing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-dunning"><span class="rc-snum">2</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-account-updater"><span class="rc-snum">3</span>Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-branding"><span class="rc-snum">4</span>Branding</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-metrics"><span class="rc-snum">6</span>Metrics & Growth</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🎉</div>
      <div>
        <h2>Congratulations on Going Live!</h2>
        <p>You've crossed a major milestone. Now it's time to make sure your Recurly setup is fully optimized — and that you have the tools and knowledge to grow a successful subscription business.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🧭 What is Navigate Launchpad?</h3>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Navigate Launchpad is your 90-day guided success program, built specifically for merchants who just went live in Recurly. It combines structured weekly learning with practical best practices — giving you everything you need to launch confidently, recover revenue automatically, and understand your data.</p>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0;">Think of it as your personal roadmap — broken into two focused phases that build on each other, week by week.</p>
    </div>

    <h3 class="rc-subhead">📅 Your Two-Phase Journey</h3>

    <div class="rc-phase-banner phase1">
      <div class="rc-phase-icon">⚙️</div>
      <div>
        <h3>Phase 1: Optimization — Weeks 1–6</h3>
        <p>Lock in your most impactful Recurly configurations. From your first production test to gateway failover, each week adds a layer of revenue protection and operational efficiency.</p>
        <div class="rc-phase-weeks">
          <span class="rc-week-chip">Week 1: Production Testing</span>
          <span class="rc-week-chip">Week 2: Dunning</span>
          <span class="rc-week-chip">Week 3: Account Updater</span>
          <span class="rc-week-chip">Week 4: Branding</span>
          <span class="rc-week-chip">Week 5: Gateway Failover</span>
          <span class="rc-week-chip">Week 6: Phase Review</span>
        </div>
      </div>
    </div>

    <div class="rc-phase-banner phase2">
      <div class="rc-phase-icon">📊</div>
      <div>
        <h3>Phase 2: Mastering Metrics — Weeks 7–12</h3>
        <p>Transform your Recurly data into business intelligence. Learn the six metrics that power subscription growth, how to benchmark your performance, and how to turn insights into strategy.</p>
        <div class="rc-phase-weeks">
          <span class="rc-week-chip">Week 7: Core Metrics Intro</span>
          <span class="rc-week-chip">Week 8: Acquisition & Decline</span>
          <span class="rc-week-chip">Week 9: Churn</span>
          <span class="rc-week-chip">Week 10: Recovery Rate</span>
          <span class="rc-week-chip">Week 11: Renewal Invoice Rate</span>
          <span class="rc-week-chip">Week 12: Recovered Revenue</span>
        </div>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🗺️ Your Launchpad Journey at a Glance</h3>
      <div class="rc-journey">
        <div class="rc-jstep"><div class="rc-jdot">🧪</div><div class="rc-jlbl">Test Your Flow</div></div>
        <div class="rc-jstep"><div class="rc-jdot">📬</div><div class="rc-jlbl">Optimize Dunning</div></div>
        <div class="rc-jstep"><div class="rc-jdot">💳</div><div class="rc-jlbl">Enable AU</div></div>
        <div class="rc-jstep"><div class="rc-jdot">🎨</div><div class="rc-jlbl">Brand It</div></div>
        <div class="rc-jstep"><div class="rc-jdot">🔒</div><div class="rc-jlbl">Protect Revenue</div></div>
        <div class="rc-jstep"><div class="rc-jdot">📈</div><div class="rc-jlbl">Master Metrics</div></div>
      </div>
    </div>

    <h3 class="rc-subhead">✨ What You'll Accomplish in 90 Days</h3>
    <div class="rc-3col">
      <div class="rc-wi"><div class="rc-wi-icon">🛡️</div><h4>Protect Your Revenue</h4><p>Automated tools working 24/7 to catch failed payments before they cause churn.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">📊</div><h4>Understand Your Data</h4><p>Know your six most important subscription metrics and how to act on them.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🚀</div><h4>Build for Scale</h4><p>The right configurations in place to grow your subscriber base with confidence.</p></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>How to Use This Program</h4>
        <p>Each module in Launchpad is self-contained and takes about 10–15 minutes to complete. Work through them in order — each week builds on the last. If you've already configured something, use the module as a best-practice audit to make sure it's set up optimally.</p>
      </div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Before you begin:</strong> Make sure you've completed your basic Recurly account setup and have successfully gone live in production. If you're still in testing, complete your setup first — then come back here to start Launchpad.</p>
    </div>

    <div class="rc-sec-nav">
      <span class="rc-btn-disabled">← Start of Program</span>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-production-testing">Next: Production Testing →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com" target="_blank" rel="noopener noreferrer">📖 Recurly Docs</a>
    <a class="rc-link-btn rc-link-sec" href="https://support.recurly.com" target="_blank" rel="noopener noreferrer">🎧 Recurly Support</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">✉️ Customer Success Team</a>
  </div>
</div>
`}</HTMLBlock>