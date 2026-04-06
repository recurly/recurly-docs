---
title: 'Launchpad Phase 2: Mastering Metrics'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
.rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif;max-width:960px;margin:0 auto;padding:0 20px 60px}
.rc-hero{background:var(--offblack);border-radius:16px;padding:52px 40px 44px;text-align:center;margin-bottom:0}
.rc-badge{display:inline-block;background:var(--orange);color:#fff;border-radius:20px;padding:6px 20px;font-size:12px;font-weight:800;letter-spacing:1px;text-transform:uppercase;margin-bottom:18px}
.rc-hero h1{font-size:2.3rem;font-weight:800;line-height:1.15;margin:0 0 12px;color:#fff}
.rc-hero>p{font-size:1rem;max-width:680px;margin:0 auto 28px;color:#CCC9B8;line-height:1.6}
.rc-hero-stats{display:flex;justify-content:center;gap:36px;flex-wrap:wrap}
.rc-num{font-size:1.7rem;font-weight:800;color:var(--orange)}
.rc-lbl{font-size:.76rem;color:#CCC9B8;text-transform:uppercase;letter-spacing:.5px}
.rc-nav{display:flex;flex-wrap:wrap;gap:8px;margin:22px 0 32px;padding:16px;background:var(--offwhite);border-radius:14px;border:1px solid var(--lightgray)}
.rc-nav a{display:inline-flex;align-items:center;gap:7px;padding:9px 13px;border-radius:10px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.83rem;font-weight:700;transition:all .2s}
.rc-nav a:hover{border-color:var(--orange);box-shadow:0 2px 8px rgba(255,130,0,.2);color:var(--offblack);text-decoration:none}
.rc-nav a.rc-active{background:var(--orange);border-color:var(--orange);color:#fff;box-shadow:0 2px 10px rgba(255,130,0,.3)}
.rc-snum{display:inline-flex;align-items:center;justify-content:center;width:22px;height:22px;border-radius:50%;background:var(--offblack);color:var(--orange);font-size:11px;font-weight:800;flex-shrink:0}
.rc-nav a.rc-active .rc-snum{background:rgba(255,255,255,.2);color:#fff}
.rc-sec{margin-bottom:48px}
.rc-sec-header{display:flex;align-items:flex-start;gap:18px;margin-bottom:28px}
.rc-sec-icon{width:52px;height:52px;border-radius:14px;background:var(--orange);display:flex;align-items:center;justify-content:center;font-size:24px;flex-shrink:0}
.rc-sec-header h2{font-size:1.45rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
.rc-sec-header p{font-size:.9rem;color:var(--gray);margin:0;line-height:1.6}
.rc-card{background:#fff;border:1px solid var(--lightgray);border-radius:14px;padding:20px 22px;margin-bottom:16px;box-shadow:0 2px 6px rgba(13,13,11,.04)}
.rc-subhead{font-size:.98rem;font-weight:800;color:var(--offblack);margin:0 0 10px}
.rc-handoff-from{background:linear-gradient(135deg,var(--offblack),#1a1200);border-radius:14px;padding:22px 24px;margin-bottom:18px;display:flex;align-items:flex-start;gap:16px}
.rc-handoff-from h3{font-size:.98rem;font-weight:800;color:var(--yellow);margin:0 0 6px}
.rc-handoff-from p{font-size:.87rem;color:#CCC9B8;margin:0;line-height:1.5}
.rc-check-row{display:flex;align-items:center;gap:10px;padding:6px 0;font-size:.85rem;color:#CCC9B8}
.rc-check-dot{width:20px;height:20px;border-radius:50%;background:var(--yellow);color:var(--offblack);font-size:11px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-metric-row{display:grid;grid-template-columns:1fr 1fr 1fr;gap:12px;margin-bottom:16px}
.rc-metric-card{background:#fff;border:1px solid var(--lightgray);border-radius:12px;padding:16px 18px;text-align:center}
.rc-metric-num{font-size:1.6rem;font-weight:800;color:var(--orange);margin-bottom:4px}
.rc-metric-name{font-size:.82rem;font-weight:700;color:var(--offblack);margin-bottom:4px}
.rc-metric-desc{font-size:.78rem;color:var(--gray);line-height:1.4}
.rc-scorecard{background:var(--offblack);border-radius:14px;padding:22px 24px;margin-bottom:16px}
.rc-scorecard h3{font-size:.96rem;font-weight:800;color:var(--orange);margin:0 0 14px}
.rc-scorecard p{font-size:.87rem;color:#CCC9B8;line-height:1.6;margin-bottom:18px}
.rc-sneak-peek{margin-top:24px;background:rgba(255,255,255,0.03);border-radius:10px;padding:15px;border:1px solid rgba(255,255,255,0.1)}
.rc-crop-container{width:100%;height:180px;overflow:hidden;border-radius:6px;margin-top:12px;border:1px solid rgba(255,215,6,0.25);position:relative}
.rc-crop-container img{position:absolute;width:150%;left:-5%;top:-10%;filter:contrast(1.05)}
.rc-sneak-label{font-size:0.75rem;font-weight:800;color:var(--yellow);text-transform:uppercase;letter-spacing:0.5px;display:block;margin-bottom:6px}

.rc-tip{background:#fff6ee;border:1px solid #ffcb99;border-radius:12px;padding:15px 17px;margin-bottom:16px;font-size:.87rem;color:var(--darkgray);line-height:1.6}
.rc-tip strong{color:var(--offblack)}
.rc-clip{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:14px;padding:16px 18px;margin-bottom:16px}
.rc-clip-label{display:inline-flex;align-items:center;gap:5px;background:var(--offblack);color:var(--orange);border-radius:6px;padding:3px 10px;font-size:.73rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;margin-bottom:10px}
.rc-clip p{font-size:.87rem;color:var(--gray);margin:0 0 10px;line-height:1.5}
.rc-clip-title{font-size:.93rem;font-weight:700;color:var(--offblack);margin:0 0 6px}
.rc-webinar-link{display:inline-flex;align-items:center;gap:6px;font-size:.83rem;font-weight:700;color:var(--orange);text-decoration:none}
.rc-webinar-link:hover{text-decoration:underline}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.87rem;text-decoration:none;border:1px solid var(--lightgray)}
.rc-btn-prev{background:#fff;color:var(--darkgray)}
.rc-btn-prev:hover{background:var(--brightgray);text-decoration:none}
.rc-btn-next{background:var(--orange);color:#fff;border-color:var(--orange)}
.rc-btn-next:hover{opacity:.92;text-decoration:none}
.rc-resources{margin-top:32px}
.rc-resources h3{font-size:.84rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--gray);margin:0 0 12px}
@media(max-width:640px){.rc-hero{padding:30px 16px 26px}.rc-hero h1{font-size:1.65rem}.rc-metric-row{grid-template-columns:1fr 1fr}.rc-hero-stats{gap:14px}.rc-sec-header{flex-direction:column}.rc-sec-nav{flex-direction:column;align-items:stretch}.rc-handoff-from{flex-direction:column}}
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">📊 Navigate · Launchpad Phase 2</div>
    <h1>Mastering Metrics</h1>
    <p>Phase 1 locked in your optimization setup. Now it's time to understand the data behind your subscription business — and use it to grow smarter.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">6</div><div class="rc-lbl">Core KPIs</div></div>
      <div><div class="rc-num">Phase 2</div><div class="rc-lbl">Mastering Metrics</div></div>
      <div><div class="rc-num">Monthly</div><div class="rc-lbl">Scorecard Cadence</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two" class="rc-active"><span class="rc-snum">🏠</span>Phase 2 Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-benchmarks-dashboard"><span class="rc-snum">1</span>Benchmarks &amp; Reporting</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-acquisition-metrics"><span class="rc-snum">2</span>Acquisition &amp; Decline</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-churn-metrics"><span class="rc-snum">3</span>Churn Metrics</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-retention-metrics"><span class="rc-snum">4</span>Revenue &amp; Recovery</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-review"><span class="rc-snum">✓</span>Full Course Review</a>
  </nav>

  <div class="rc-sec">

    <div class="rc-handoff-from">
      <div style="font-size:26px;flex-shrink:0;margin-top:2px">⚙️</div>
      <div>
        <h3>Picking Up From Phase 1</h3>
        <p style="margin-bottom:10px">In Phase 1, you set up the systems that protect and recover your revenue automatically. By now you should have:</p>
        <div class="rc-check-row"><div class="rc-check-dot">✓</div>Dunning &amp; Intelligent Retry configured</div>
        <div class="rc-check-row"><div class="rc-check-dot">✓</div>Account Updater enabled</div>
        <div class="rc-check-row"><div class="rc-check-dot">✓</div>Branded emails &amp; invoices</div>
        <div class="rc-check-row"><div class="rc-check-dot">✓</div>Gateway Failover in place</div>
        <p style="margin-top:10px">Phase 2 builds on that foundation — now you'll measure performance via <strong>Recurly Analytics</strong> and spot growth opportunities.</p>
      </div>
    </div>

    <div class="rc-sec-header">
      <div class="rc-sec-icon">📊</div>
      <div>
        <h2>Your 6 Core Benchmark Metrics</h2>
        <p>These metrics reveal your business health — from how well you're acquiring subscribers to how effectively you're recovering revenue.</p>
      </div>
    </div>

    <div class="rc-metric-row">
      <div class="rc-metric-card">
        <div class="rc-metric-num">📈</div>
        <div class="rc-metric-name">Acquisition Rate</div>
        <div class="rc-metric-desc">New subs / Active subs (start of period)</div>
      </div>
      <div class="rc-metric-card">
        <div class="rc-metric-num">⚡</div>
        <div class="rc-metric-name">Sign-Up Decline Rate</div>
        <div class="rc-metric-desc">Failed attempts / Total sign-up attempts</div>
      </div>
      <div class="rc-metric-card">
        <div class="rc-metric-num">👋</div>
        <div class="rc-metric-name">Voluntary Churn Rate</div>
        <div class="rc-metric-desc">Subscribers who chose to cancel</div>
      </div>
      <div class="rc-metric-card">
        <div class="rc-metric-num">💳</div>
        <div class="rc-metric-name">Involuntary Churn Rate</div>
        <div class="rc-metric-desc">Subscribers lost to dunning expiration</div>
      </div>
      <div class="rc-metric-card">
        <div class="rc-metric-num">✅</div>
        <div class="rc-metric-name">Renewal Paid Rate</div>
        <div class="rc-metric-desc">% collected successfully at renewal</div>
      </div>
      <div class="rc-metric-card">
        <div class="rc-metric-num">💰</div>
        <div class="rc-metric-name">Dunning Recovery Rate</div>
        <div class="rc-metric-desc">Invoices paid / total entering dunning</div>
      </div>
    </div>

    <div class="rc-scorecard">
      <h3>📋 Your Monthly Metrics Scorecard</h3>
      <p class="rc-scorecard-summary">The scorecard provides a complete snapshot of your last full fiscal month in Recurly so you can see your performance at a glance. You will begin receiving yours via email on the first Tuesday of each month, starting 90 days after going live.</p>
      
      <div class="rc-sneak-peek">
        <span class="rc-sneak-label">✨ Sneak Peek</span>
        <p style="font-size:0.83rem; color:#CCC9B8; margin:0;">See how you stack up against yourself and your peers. You'll learn more about using this at the end of this learning path!</p>
        <div class="rc-crop-container">
          <img src="Monthly Merchant Score Card Sample.png" alt="Scorecard Preview">
        </div>
      </div>
    </div>

    <div class="rc-clip">
      <div class="rc-clip-label">🎬 Bonus Learning: Webinar</div>
      <p class="rc-clip-title">Get a Headstart: Advanced Reporting Secrets</p>
      <p>Watch Director of Data Matthew Cryer demonstrate how to master the <strong>Trendalyzer</strong>, monitor <strong>hourly activations</strong>, and navigate the four layers of Recurly reporting to unlock non-obvious growth insights.</p>
      <a class="rc-webinar-link" href="https://recurly.com/events/" target="_blank">▶ Watch "Beyond the Dashboard" On-Demand →</a>
    </div>

    <div class="rc-tip">
      <strong>💡 Download the Metrics Cheatsheet:</strong> Before diving into the individual metrics, grab the Launchpad Metrics Cheatsheet. It lists every KPI definition, calculation formula, and what direction you want each metric to move.
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-one-review">← Phase 1 Review</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-benchmarks-dashboard">Step 1: Benchmarks &amp; Reporting →</a>
    </div>

    <div class="rc-resources">
      <h3>Additional Resources</h3>
      <a class="rc-link-btn" href="https://go.recurly.com/Navigate-Metrics-Cheatsheet.html" target="_blank" rel="noopener noreferrer">⬇ Metrics Cheatsheet</a>
      <a class="rc-link-btn rc-link-sec" href="https://recurly.com/events/" target="_blank" rel="noopener noreferrer">🎧 Webinars On-Demand</a>
      <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">✉ Contact Customer Success</a>
    </div>
  </div>

</div>
`}</HTMLBlock>

<br />
