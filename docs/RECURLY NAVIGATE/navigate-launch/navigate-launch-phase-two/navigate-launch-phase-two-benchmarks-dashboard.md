---
title: 'Section 1: Reporting Tools'
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
.rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:16px}
.rc-tip{background:#fff6ee;border:1px solid #ffcb99;border-radius:12px;padding:15px 17px;margin-bottom:16px;font-size:.87rem;color:var(--darkgray);line-height:1.6}
.rc-tip strong{color:var(--offblack)}
.rc-video-wrap{position:relative;width:100%;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:10px;margin-bottom:8px;background:var(--offblack)}
.rc-video-wrap iframe{position:absolute;top:0;left:0;width:100%;height:100%;border:0}
.rc-video-cap{font-size:.8rem;color:var(--gray);text-align:center;margin-bottom:4px;font-style:italic}
.rc-clip{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:14px;padding:16px 18px;margin-bottom:16px}
.rc-clip-label{display:inline-flex;align-items:center;gap:5px;background:var(--offblack);color:var(--orange);border-radius:6px;padding:3px 10px;font-size:.73rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;margin-bottom:10px}
.rc-clip p{font-size:.87rem;color:var(--gray);margin:0 0 10px;line-height:1.5}
.rc-clip-title{font-size:.93rem;font-weight:700;color:var(--offblack);margin:0 0 6px}
.rc-webinar-link{display:inline-flex;align-items:center;gap:6px;font-size:.83rem;font-weight:700;color:var(--orange);text-decoration:none}
.rc-webinar-link:hover{text-decoration:underline}
.rc-tool-card{background:#fff;border:1px solid var(--lightgray);border-radius:12px;padding:17px 19px}
.rc-tool-icon{font-size:22px;margin-bottom:8px}
.rc-tool-card h4{font-size:.92rem;font-weight:800;color:var(--offblack);margin:0 0 5px}
.rc-tool-card p{font-size:.83rem;color:var(--gray);line-height:1.5;margin:0 0 8px}
.rc-tool-tag{display:inline-block;background:var(--brightgray);color:var(--darkgray);border-radius:5px;padding:2px 8px;font-size:.72rem;font-weight:700}
.rc-tool-tag.recommended{background:rgba(255,130,0,.12);color:var(--orange)}
.rc-steps{display:flex;flex-direction:column;gap:11px;margin-bottom:16px}
.rc-step{background:#fff;border:1px solid var(--lightgray);border-radius:12px;padding:15px 17px;display:flex;gap:13px;align-items:flex-start}
.rc-sbadge{width:34px;height:34px;border-radius:9px;background:var(--offblack);color:var(--orange);font-weight:800;font-size:14px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-step h3{font-size:.93rem;font-weight:700;margin:0 0 4px;color:var(--offblack)}
.rc-step p{font-size:.84rem;color:var(--gray);line-height:1.6;margin:0}
.rc-checklist{background:var(--offwhite);border-radius:14px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:18px}
.rc-cl-header{padding:13px 19px;border-bottom:1px solid var(--lightgray);display:flex;align-items:center;gap:9px;background:var(--offblack)}
.rc-cl-header h3{font-size:.82rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--orange);margin:0}
.rc-cli{padding:11px 19px;border-bottom:1px solid var(--brightgray);display:flex;gap:11px;align-items:flex-start}
.rc-cli:last-child{border-bottom:none}
.rc-cb{width:19px;height:19px;border-radius:5px;border:2px solid var(--lightgray);flex-shrink:0;margin-top:1px;background:#fff}
.rc-clab{font-size:.85rem;color:var(--darkgray);line-height:1.4}
.rc-clab span{display:block;font-size:.75rem;color:var(--gray);margin-top:2px}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.87rem;text-decoration:none;border:1px solid var(--lightgray)}
.rc-btn-prev{background:#fff;color:var(--darkgray)}
.rc-btn-prev:hover{background:var(--brightgray);text-decoration:none}
.rc-btn-next{background:var(--orange);color:#fff;border-color:var(--orange)}
.rc-btn-next:hover{opacity:.92;text-decoration:none}
.rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default;pointer-events:none}
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
    <h1>Benchmarks Dashboard &amp; Reporting Tools</h1>
    <p>Before you can act on your metrics, you need to know where to find them — and which tool is right for which question. This module maps Recurly's four reporting layers and walks you through the Benchmarks Dashboard.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Step 1</div><div class="rc-lbl">Phase 2</div></div>
      <div><div class="rc-num">4</div><div class="rc-lbl">Reporting Tools</div></div>
      <div><div class="rc-num">9</div><div class="rc-lbl">Benchmark KPIs</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two"><span class="rc-snum">🏠</span>Phase 2 Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-benchmarks-dashboard" class="rc-active"><span class="rc-snum">1</span>Benchmarks &amp; Reporting</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-acquisition-metrics"><span class="rc-snum">2</span>Acquisition &amp; Decline</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-churn-metrics"><span class="rc-snum">3</span>Churn Metrics</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-retention-metrics"><span class="rc-snum">4</span>Revenue &amp; Recovery</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-review"><span class="rc-snum">✓</span>Full Course Review</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🗺️</div>
      <div>
        <h2>Recurly's 4 Reporting Layers</h2>
        <p>Recurly gives you multiple ways to access your data — from one-click dashboards to custom BI tooling. Understanding which layer to use for which question makes analysis faster and more actionable.</p>
      </div>
    </div>

    <div class="rc-2col">
      <div class="rc-tool-card">
        <div class="rc-tool-icon">📊</div>
        <h4>In-App Dashboards</h4>
        <p>Pre-built dashboards inside the Recurly UI. The fastest way to see KPIs, trends, and Benchmark comparisons without building anything.</p>
        <span class="rc-tool-tag recommended">Start Here</span>
      </div>
      <div class="rc-tool-card">
        <div class="rc-tool-icon">⬇</div>
        <h4>Exports &amp; CSVs</h4>
        <p>Manually download or schedule data exports from Recurly. Best for deep dives in Excel or syncing raw data to your own data warehouse.</p>
        <span class="rc-tool-tag">Versatile</span>
      </div>
      <div class="rc-tool-card">
        <div class="rc-tool-icon">🔍</div>
        <h4>Analytics Dashboards</h4>
        <p>Recurly's Looker-powered self-service tool. Access advanced, interactive reports and custom filtering to drill into specific subscriber segments.</p>
        <span class="rc-tool-tag">Advanced</span>
      </div>
      <div class="rc-tool-card">
        <div class="rc-tool-icon">🤖</div>
        <h4>Recurly AI Assistant</h4>
        <p>Ask plain-language questions to the AI to uncover data insights and trends instantly. A powerful shortcut for fast answers without manual builds.</p>
        <span class="rc-tool-tag recommended">Try It</span>
      </div>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">▶ Trail Guide: Exploring Your Benchmarks Dashboard</p>
      <div class="rc-video-wrap">
        <iframe src="https://drive.google.com/file/d/[BENCHMARKS-DASHBOARD-VIDEO-ID]/preview" allow="autoplay" allowfullscreen></iframe>
      </div>
      <p class="rc-video-cap">A guided tour of the Benchmarks Dashboard — how to read your KPIs, apply filters, and compare your performance against industry peers.</p>
    </div>

    <div class="rc-clip">
      <div class="rc-clip-label">🎬 Bonus Learning: Webinar</div>
      <p class="rc-clip-title">Stack Up Against the Competition: Mastering Benchmarks</p>
      <p>Get a headstart on your metrics with Senior CSM Dan Shipley. Watch him define the <strong>9 core Benchmarks</strong>, demonstrate how to interpret industry quartiles, and share high-impact strategies—like prepaid card blocking and gateway failover—to optimize your performance against your peers.</p>
      <a class="rc-webinar-link" href="https://navigate.recurly.com/lunch-and-learn/stack-up-benchmarks/" target="_blank" rel="noopener noreferrer">▶ Watch "Stack Up Against the Competition" On-Demand →</a>
    </div>

    <p class="rc-subhead" style="margin-bottom:12px">🪜 Step-by-Step: Navigate Your Benchmarks Dashboard</p>
    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Open the Benchmarks Dashboard</h3>
          <p>In your Recurly admin, navigate to <strong>Analytics → Dashboards → Benchmarks</strong>. You'll see an overview of your KPIs compared to industry peers.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Select your industry vertical</h3>
          <p>Use the industry filter to select your vertical (e.g., SaaS, Media). Your benchmarks will adjust to show how you stack up against relevant peers.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Read each metric card</h3>
          <p>Each card shows your current rate, the benchmark range (represented by quartiles), and your trend line. Note which of the 9 KPIs need attention.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div>
          <h3>Apply date range filters</h3>
          <p>Compare metrics month-over-month to spot trends. Improving direction often matters more than your current level when evaluating new optimizations.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div>
          <h3>Try the AI Assistant</h3>
          <p>Navigate to <strong>Analytics → Analytics Dashboards</strong> and locate the AI Assistant. Ask it plain-language questions about your growth or subscriber trends.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Benchmark context matters:</strong> Always evaluate your 9 KPIs against your industry vertical for the most accurate health check. A sign-up decline rate that looks high in isolation might actually be typical for your pricing model.
    </div>

    <p class="rc-subhead" style="margin-bottom:12px">✅ Benchmarks &amp; Reporting Checklist</p>
    <div class="rc-checklist">
      <div class="rc-cl-header"><h3>Complete Before Moving to Acquisition Metrics</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Located Benchmarks in Analytics → Dashboards → Benchmarks</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Selected your industry vertical in the dashboard filter</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Reviewed all 9 core KPI cards for your current performance</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Applied a date range filter to compare at least two time periods</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Tried the Recurly AI Assistant with at least one question</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Downloaded the Metrics Cheatsheet for definition reference</div></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two">← Phase 2 Overview</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-acquisition-metrics">Step 2: Acquisition &amp; Decline →</a>
    </div>

    <div class="rc-resources">
      <h3>Additional Resources</h3>
      <a class="rc-link-btn" href="https://docs.recurly.com/docs/built-in-benchmarks" target="_blank" rel="noopener noreferrer">📖 Benchmarks Guide</a>
      <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/docs/analytics-dashboards" target="_blank" rel="noopener noreferrer">🔍 Analytics Dashboards Docs</a>
      <a class="rc-link-btn rc-link-sec" href="https://recurly.com/events/" target="_blank" rel="noopener noreferrer">🎧 Webinars On-Demand</a>
      <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">✉ Contact Customer Success</a>
    </div>
  </div>

</div>
`}</HTMLBlock>

<br />
