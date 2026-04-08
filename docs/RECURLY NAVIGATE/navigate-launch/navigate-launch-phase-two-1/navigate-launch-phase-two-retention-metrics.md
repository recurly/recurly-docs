---
title: 'Section 4: Revenue Recovery'
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
.rc-nav a.rc-active{background:var(--orange);border-color:var(--orange);color:#fff}
.rc-snum{display:inline-flex;align-items:center;justify-content:center;width:22px;height:22px;border-radius:50%;background:var(--offblack);color:var(--orange);font-size:11px;font-weight:800;flex-shrink:0}
.rc-nav a.rc-active .rc-snum{background:rgba(255,255,255,.2);color:#fff}
.rc-sec{margin-bottom:48px}
.rc-sec-header{display:flex;align-items:flex-start;gap:18px;margin-bottom:28px}
.rc-sec-icon{width:52px;height:52px;border-radius:14px;background:var(--orange);display:flex;align-items:center;justify-content:center;font-size:24px;flex-shrink:0}
.rc-sec-header h2{font-size:1.45rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
.rc-sec-header p{font-size:.9rem;color:var(--gray);margin:0;line-height:1.6}
.rc-card{background:#fff;border:1px solid var(--lightgray);border-radius:14px;padding:20px 22px;margin-bottom:16px;box-shadow:0 2px 6px rgba(13,13,11,.04)}
.rc-subhead{font-size:.98rem;font-weight:800;color:var(--offblack);margin:0 0 10px}
.rc-metric{background:#fff;border:1px solid var(--lightgray);border-radius:14px;padding:20px 22px;margin-bottom:14px}
.rc-metric-head{display:flex;align-items:center;gap:12px;margin-bottom:10px}
.rc-metric-icon{width:40px;height:40px;border-radius:10px;background:var(--offblack);color:var(--orange);font-size:18px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-metric h3{font-size:.96rem;font-weight:800;margin:0;color:var(--offblack)}
.rc-metric p{font-size:.85rem;color:var(--gray);margin:0 0 10px;line-height:1.6}
.rc-formula{background:var(--brightgray);border-radius:8px;padding:10px 14px;font-size:.83rem;font-family:monospace;color:var(--darkgray);margin-bottom:10px}
.rc-pills{display:flex;gap:8px;flex-wrap:wrap}
.rc-pill{padding:4px 12px;border-radius:20px;font-size:.75rem;font-weight:700;background:var(--offwhite);border:1px solid var(--lightgray);color:var(--darkgray)}
.rc-pill.up{background:rgba(22,163,74,.1);color:#15803d;border-color:#86efac}
.rc-pill.down{background:rgba(220,38,38,.1);color:#dc2626;border-color:#fca5a5}
.rc-tip{background:#fff6ee;border:1px solid #ffcb99;border-radius:12px;padding:15px 17px;margin-bottom:16px;font-size:.87rem;color:var(--darkgray);line-height:1.6}
.rc-tip strong{color:var(--offblack)}
.rc-video-wrap{position:relative;width:100%;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:10px;margin-bottom:8px;background:var(--offblack)}
.rc-video-wrap iframe{position:absolute;top:0;left:0;width:100%;height:100%;border:0;overflow:hidden}
.rc-video-cap{font-size:.8rem;color:var(--gray);text-align:center;margin-bottom:4px;font-style:italic}
.rc-clip{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:14px;padding:16px 18px;margin-bottom:16px}
.rc-clip-label{display:inline-flex;align-items:center;gap:5px;background:var(--offblack);color:var(--orange);border-radius:6px;padding:3px 10px;font-size:.73rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;margin-bottom:10px}
.rc-clip p{font-size:.87rem;color:var(--gray);margin:0 0 10px;line-height:1.5}
.rc-clip-title{font-size:.93rem;font-weight:700;color:var(--offblack);margin:0 0 6px}
.rc-webinar-link{display:inline-flex;align-items:center;gap:6px;font-size:.83rem;font-weight:700;color:var(--orange);text-decoration:none}
.rc-webinar-link:hover{text-decoration:underline}
.rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:16px}
.rc-phase1-tie{background:var(--offblack);border-radius:13px;padding:18px 20px;margin-bottom:16px}
.rc-phase1-tie h4{font-size:.9rem;font-weight:800;color:var(--yellow);margin:0 0 10px}
.rc-phase1-row{display:flex;align-items:flex-start;gap:10px;padding:7px 0;border-bottom:1px solid rgba(255,255,255,.07);font-size:.84rem;color:#CCC9B8}
.rc-phase1-row:last-child{border-bottom:none}
.rc-phase1-dot{width:22px;height:22px;border-radius:50%;background:var(--yellow);color:var(--offblack);font-size:10px;display:flex;align-items:center;justify-content:center;flex-shrink:0;margin-top:1px}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.87rem;text-decoration:none;border:1px solid var(--lightgray)}
.rc-btn-prev{background:#fff;color:var(--darkgray)}
.rc-btn-prev:hover{background:var(--brightgray);text-decoration:none}
.rc-btn-next{background:var(--orange);color:#fff;border-color:var(--orange)}
.rc-btn-next:hover{opacity:.92;text-decoration:none}
.rc-link-btn{background:var(--orange);color:#fff;border-color:var(--orange);margin:0 8px 8px 0}
.rc-link-btn:hover{opacity:.9;text-decoration:none}
.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
.rc-link-sec:hover{background:var(--brightgray);text-decoration:none}
.rc-resources{margin-top:32px}
.rc-resources h3{font-size:.84rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--gray);margin:0 0 12px}
@media(max-width:640px){.rc-hero{padding:30px 16px 26px}.rc-hero h1{font-size:1.65rem}.rc-2col{grid-template-columns:1fr}.rc-hero-stats{gap:14px}.rc-sec-header{flex-direction:column}.rc-sec-nav{flex-direction:column;align-items:stretch}}
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">📊 Navigate · Launchpad Phase 2</div>
    <h1>Revenue Recovery Metrics</h1>
    <p>These three metrics measure how much of your earned revenue you actually collect — and how hard your dunning, retry, and card update systems are working on your behalf.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Step 4</div><div class="rc-lbl">Phase 2</div></div>
      <div><div class="rc-num">3</div><div class="rc-lbl">Recovery KPIs</div></div>
      <div><div class="rc-num">↑</div><div class="rc-lbl">All 3 Should Climb</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two"><span class="rc-snum">🏠</span>Phase 2 Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-benchmarks-dashboard"><span class="rc-snum">1</span>Benchmarks &amp; Reporting</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-acquisition-metrics"><span class="rc-snum">2</span>Acquisition &amp; Decline</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-churn-metrics"><span class="rc-snum">3</span>Churn Metrics</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-retention-metrics" class="rc-active"><span class="rc-snum">4</span>Revenue &amp; Recovery</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-review"><span class="rc-snum">✓</span>Full Course Review</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">💰</div>
      <div>
        <h2>How Much Revenue Are You Actually Collecting?</h2>
        <p>Revenue recovery metrics close the loop on everything you built in Phase 1. These three KPIs give you the answer to your business growth at every stage of the billing cycle.</p>
      </div>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">▶ Trail Guide: Renewal Invoice Paid Rate &amp; Revenue Recovery</p>
      <div class="rc-video-wrap">
        <iframe src="https://share.synthesia.io/embeds/videos/9cfddf79-92e3-4c0a-ae46-315581008566" loading="lazy" title="Navigate Launchpad — Renewal Invoice Paid Rate" allow="encrypted-media; fullscreen;" allowfullscreen></iframe>
      </div>
      <p class="rc-video-cap">A walkthrough of Renewal Invoice Paid Rate and Decline Rate at Renewal — where to find each in the Benchmarks Dashboard and how to interpret them together.</p>
    </div>

    <div class="rc-metric">
      <div class="rc-metric-head">
        <div class="rc-metric-icon">✅</div>
        <h3>Renewal Invoice Paid Rate</h3>
      </div>
      <p>The percentage of renewal invoices successfully paid either on first attempt or through recovery. This is your primary health metric for revenue collection. A declining rate signals a growing problem with payment failures or dunning effectiveness.</p>
      <div class="rc-formula">% collected successfully at renewal = Renewal Invoice Paid Rate %</div>
      <div class="rc-pills">
        <span class="rc-pill up">↑ Higher is better</span>
        <span class="rc-pill">Check monthly</span>
        <span class="rc-pill">Analytics → Dashboards → Benchmarks</span>
      </div>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">▶ Trail Guide: Dunning Recovery Rate Deep Dive</p>
      <div class="rc-video-wrap">
        <iframe src="https://share.synthesia.io/embeds/videos/94ebc34a-579b-4129-9a0f-ee926d42a34a" loading="lazy" title="Navigate Launchpad — Dunning Recovery Rate" allow="encrypted-media; fullscreen;" allowfullscreen></iframe>
      </div>
      <p class="rc-video-cap">How to read your Dunning Recovery Rate and how to troubleshoot if your rate is below the industry median for your vertical.</p>
    </div>

    <div class="rc-metric">
      <div class="rc-metric-head">
        <div class="rc-metric-icon">💰</div>
        <h3>Dunning Recovery Rate</h3>
      </div>
      <p>Of all renewal invoices that enter dunning, what percentage are ultimately recovered? This measures the combined effectiveness of your dunning window, Intelligent Retry logic, and email sequences.</p>
      <div class="rc-formula">Invoices paid ÷ Total invoices entering dunning = Dunning Recovery Rate %</div>
      <div class="rc-pills">
        <span class="rc-pill up">↑ Higher is better</span>
        <span class="rc-pill">Industry median: ~27%</span>
        <span class="rc-pill">Analytics → Dashboards → Benchmarks</span>
      </div>
    </div>

    <div class="rc-metric">
      <div class="rc-metric-head">
        <div class="rc-metric-icon">⚡</div>
        <h3>Decline Rate at Renewal</h3>
      </div>
      <p>The percentage of renewal invoices declined on first attempt. Unlike sign-ups, renewal declines are almost entirely involuntary (expired cards, insufficient funds). This metric is a direct reflection of Account Updater effectiveness.</p>
      <div class="rc-formula">First-attempt declined renewals ÷ Total renewal invoices = Decline Rate at Renewal %</div>
      <div class="rc-pills">
        <span class="rc-pill down">↓ Lower is better</span>
        <span class="rc-pill">Check monthly</span>
        <span class="rc-pill">Analytics → Dashboards → Benchmarks</span>
      </div>
    </div>

    <div class="rc-clip">
      <div class="rc-clip-label">🎬 Where in the Webinar?</div>
      <p class="rc-clip-title">Deep Dive: Reading the Renewal Funnel</p>
      <p>Fast-forward to the <strong>Renewal and Dunning Benchmarks</strong> segment of this session. Strategic CSM Dan Shipley breaks down the "declined → entered dunning → recovered" flow and explains how to benchmark your recovery rate against your vertical's top quartile to spot optimization gaps.</p>
      <a class="rc-webinar-link" href="https://navigate.recurly.com/lunch-and-learn/stack-up-benchmarks/" target="_blank" rel="noopener noreferrer">▶ Watch "Stack Up Against the Competition" On-Demand →</a>
    </div>

    <div class="rc-phase1-tie">
      <h4>⚙️ How Phase 1 Configurations Drive These Metrics</h4>
      <div class="rc-phase1-row"><div class="rc-phase1-dot">AU</div>Account Updater reduces Decline Rate at Renewal by refreshing card details before billing attempts</div>
      <div class="rc-phase1-row"><div class="rc-phase1-dot">D</div>Dunning Optimization and Intelligent Retry directly improve your Dunning Recovery Rate</div>
      <div class="rc-phase1-row"><div class="rc-phase1-dot">GF</div>Gateway Failover prevents outage-driven declines from entering dunning at all</div>
      <div class="rc-phase1-row"><div class="rc-phase1-dot">B</div>Branded dunning emails improve subscriber response rates — increasing self-serve card updates</div>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">🎯 Reading the Recovery Funnel Together</p>
      <div class="rc-2col">
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">High decline rate, high recovery rate</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Many invoices fail on first attempt, but most are recovered. Dunning is working — but consider expanding Account Updater to reduce the initial failure rate.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Low decline rate, high paid rate</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">This is the target state. Account Updater is keeping cards current, and the few failures are recovered efficiently. Focus on maintaining this as you scale.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">High decline rate, low recovery rate</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Invoices are failing and staying unpaid. Revisit your dunning window, enable Intelligent Retry, and check Account Updater coverage.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Sudden drop in paid rate</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">An unexpected drop usually signals a gateway issue or a card-type-specific problem. Investigate immediately with your CSM or support team.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Benchmark relative to your vertical:</strong> High-ticket annual subscriptions often have lower recovery rates than monthly B2C plans. Always benchmark within your vertical before drawing conclusions.
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-churn-metrics">← Churn Metrics</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-review">Full Course Review →</a>
    </div>

    <div class="rc-resources">
      <h3>Additional Resources</h3>
      <a class="rc-link-btn" href="https://docs.recurly.com/docs/renewal-benchmarks" target="_blank" rel="noopener noreferrer">📖 Renewal Benchmarks Guide</a>
      <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">🎧 Webinars On-Demand</a>
      <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">✉ Contact Customer Support</a>
    </div>
  </div>

</div>
`}</HTMLBlock>

<br />
