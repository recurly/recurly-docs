---
title: 'Benchmarks 101: Dunning'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8" />
<style>
  .rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
  *{box-sizing:border-box}body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
  .rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px}
  .rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
  .rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
  .rc-hero p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 32px;color:var(--lightgray)}
  .rc-hero-stats{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}.rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:10px;padding:10px 18px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack);box-shadow:0 2px 10px rgba(255,215,6,.25)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-nav a.is-active .rc-snum{background:var(--offblack);color:var(--yellow)}
  .rc-sec{margin-bottom:56px}.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}.rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray);text-align:center}
  .rc-wi-icon{font-size:30px;margin-bottom:10px}.rc-wi h4{font-size:.88rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-wi p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
  .rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
  .rc-sbadge{width:38px;height:38px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start;margin-bottom:24px}
  .rc-wicon{font-size:20px;flex-shrink:0}.rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-def-box{background:var(--brightgray);border-radius:12px;padding:20px 24px;margin-bottom:16px;border-left:4px solid var(--yellow)}
  .rc-def-title{font-size:.95rem;font-weight:800;color:var(--offblack);margin:0 0 6px}
  .rc-def-formula{font-family:monospace;font-size:.82rem;background:var(--offwhite);border:1px solid var(--lightgray);border-radius:6px;padding:7px 12px;color:var(--darkgray);font-weight:700;margin-bottom:10px;display:block}
  .rc-def-box p{font-size:.85rem;color:var(--gray);line-height:1.6;margin:0}
  .rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:28px}
  .rc-cl-header{padding:16px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:center;gap:10px;background:var(--offblack)}
  .rc-cl-header h3{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
  .rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:flex-start;gap:14px}.rc-cli:last-child{border-bottom:none}
  .rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;background:#fff}
  .rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}.rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
  .rc-bench-table{width:100%;border-collapse:collapse;margin-bottom:24px;font-size:.88rem}
  .rc-bench-table th{background:var(--offblack);color:var(--offwhite);font-weight:700;padding:10px 16px;text-align:left;font-size:.8rem;letter-spacing:.04em}
  .rc-bench-table td{padding:10px 16px;border-bottom:1px solid var(--lightgray);color:var(--darkgray)}
  .rc-bench-table tr:nth-child(even) td{background:var(--brightgray)}
  .rc-img-placeholder{background:var(--brightgray);border:2px dashed var(--lightgray);border-radius:12px;padding:32px 24px;text-align:center;margin-bottom:24px}
  .rc-img-icon{font-size:32px;margin-bottom:8px}.rc-img-label{font-size:.85rem;font-weight:700;color:var(--darkgray);margin-bottom:4px}.rc-img-sub{font-size:.78rem;color:var(--gray)}
  .rc-video-placeholder{background:var(--brightgray);border:2px dashed var(--lightgray);border-radius:12px;padding:40px 24px;text-align:center;margin-bottom:24px}
  .rc-video-icon{font-size:40px;margin-bottom:10px}.rc-video-label{font-size:.9rem;font-weight:700;color:var(--darkgray);margin-bottom:4px}.rc-video-sub{font-size:.8rem;color:var(--gray)}
  .rc-recovery-card{background:var(--offwhite);border-radius:14px;padding:18px 16px;border:1px solid var(--lightgray);border-bottom:3px solid var(--yellow);text-align:center}
  .rc-recovery-icon{font-size:24px;margin-bottom:8px}
  .rc-recovery-title{font-size:.88rem;font-weight:800;color:var(--offblack);margin-bottom:5px}
  .rc-recovery-desc{font-size:.78rem;color:var(--gray);line-height:1.5}
  .rc-office-hours{background:linear-gradient(135deg,var(--offblack) 0%,#1a1a1a 100%);color:#fff;border-radius:16px;padding:32px;margin:32px 0;display:flex;gap:24px;align-items:center;border:1px solid var(--yellow)}
  .rc-oh-content h4{color:var(--yellow);margin:0 0 8px;font-size:1.1rem;font-weight:800;text-transform:uppercase;letter-spacing:1px}
  .rc-oh-content p{color:var(--lightgray);font-size:.95rem;line-height:1.6;margin:0 0 20px}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev,.rc-btn-disabled{border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-3col,.rc-2col{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}.rc-office-hours{flex-direction:column}}
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">📊 Reporting</div>
    <h1>Benchmarks</h1>
    <p>See how you stack up against thousands of subscription businesses — and know exactly where to focus to improve.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">2,200+</div><div class="rc-lbl">Merchants in the benchmark</div></div>
      <div><div class="rc-num">76M</div><div class="rc-lbl">Unique subscribers analyzed</div></div>
      <div><div class="rc-num">10</div><div class="rc-lbl">KPIs benchmarked</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101">Benchmarks</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-subscriber"><span class="rc-snum">1</span>Subscriber</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-churn"><span class="rc-snum">2</span>Churn</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-renewal"><span class="rc-snum">3</span>Renewal</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-dunning"><span class="rc-snum">4</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-best-practices"><span class="rc-snum">5</span>Best Practices</a>
  </nav>


  <div class="rc-sec">

    <div class="rc-sec-header">
      <div class="rc-sec-icon">💰</div>
      <div>
        <h2>Dunning Benchmarks</h2>
        <p>Dunning Recovery Rate — understand how effectively you recover failed payments compared to your industry peers, and where you're leaving revenue on the table.</p>
      </div>
    </div>

    <!-- WHAT IT IS -->
    <div class="rc-card">
      <h3 class="rc-subhead">🧩 What is the Dunning Benchmarks dashboard?</h3>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Dunning is the automated process of retrying failed invoice payments. The Dunning Benchmarks dashboard shows your <strong>dunning recovery rate</strong> — the percentage of invoices that enter dunning and are ultimately paid — compared against businesses in your industry.</p>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0;">Think of dunning recovery as "found money." Out of every 100 renewal attempts, roughly 9 will decline and enter dunning. How many of those 9 you recover is what this benchmark measures — and what it helps you optimize.</p>
    </div>

    <!-- VIDEO -->
    <div class="rc-card">
      <h3 class="rc-subhead">📹 Walkthrough: Dunning Benchmarks</h3>
      <div class="rc-video-placeholder">
        <div class="rc-video-icon">▶️</div>
        <div class="rc-video-label">VIDEO PLACEHOLDER</div>
        <div class="rc-video-sub">Insert clip from "Stack Up Against the Competition" webinar — Dunning Benchmarks walkthrough segment (~3–4 min)</div>
      </div>
    </div>

    <!-- KPI DEFINITION -->
    <h3 class="rc-subhead">📐 KPI: Dunning Recovery Rate</h3>

    <div class="rc-def-box">
      <div class="rc-def-title">💰 Dunning Recovery Rate</div>
      <span class="rc-def-formula">Invoices Recovered During Dunning Window ÷ Total Invoices That Entered Dunning</span>
      <p>Measures the percentage of invoices that fail on first attempt and are subsequently recovered during the dunning window — through retry attempts, Account Updater, Expiration Date Changes, Backup Payment Methods, or Customer Updates. A higher rate means more revenue saved from what would have been lost to involuntary churn.</p>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Example — what "recovery" looks like</h4>
        <p>A subscriber's renewal invoice is scheduled for <strong>June 1st</strong> and fails due to a decline. Recurly puts the invoice into dunning. If the invoice is recovered at any point during your dunning window — whether via an intelligent retry, an Account Updater card refresh, or the subscriber updating their payment details — it counts as <strong>recovered</strong> in this metric.</p>
      </div>
    </div>

    <!-- SIX MECHANISMS -->
    <h3 class="rc-subhead">🔧 The six recovery mechanisms — how Recurly recovers revenue</h3>
    <p style="font-size:.88rem;color:var(--gray);margin:0 0 16px;">Recurly's recovery suite uses multiple channels to recover failed invoices. Understanding each helps you know which levers to activate — and why your recovery rate may be higher or lower than a peer with fewer tools enabled.</p>

    <div class="rc-3col">
      <div class="rc-recovery-card">
        <div class="rc-recovery-icon">📅</div>
        <div class="rc-recovery-title">Expiration Date Changes</div>
        <div class="rc-recovery-desc">Automatically updates card expiration dates for continuous billing without a card network request</div>
      </div>
      <div class="rc-recovery-card">
        <div class="rc-recovery-icon">🔄</div>
        <div class="rc-recovery-title">Account Updater</div>
        <div class="rc-recovery-desc">Refreshes stored payment details when cards are replaced or reissued by the bank</div>
      </div>
      <div class="rc-recovery-card">
        <div class="rc-recovery-icon">🤖</div>
        <div class="rc-recovery-title">Intelligent Retries</div>
        <div class="rc-recovery-desc">AI-powered retry scheduling — attempts at the statistically optimal moment for each subscriber</div>
      </div>
      <div class="rc-recovery-card">
        <div class="rc-recovery-icon">💳</div>
        <div class="rc-recovery-title">Backup Payment Method</div>
        <div class="rc-recovery-desc">Automatically retries failed payments using a subscriber's backup card on file</div>
      </div>
      <div class="rc-recovery-card">
        <div class="rc-recovery-icon">👤</div>
        <div class="rc-recovery-title">Customer Updates</div>
        <div class="rc-recovery-desc">Prompts subscribers via email to update their payment method to resolve a failed invoice</div>
      </div>
      <div class="rc-recovery-card">
        <div class="rc-recovery-icon">🏢</div>
        <div class="rc-recovery-title">Forced Recovery</div>
        <div class="rc-recovery-desc">Manual collection initiation by your team on a specific past-due invoice</div>
      </div>
    </div>

    <!-- INDUSTRY TABLE -->
    <h3 class="rc-subhead">🏭 2025 revenue recovered through dunning by industry</h3>
    <p style="font-size:.88rem;color:var(--gray);margin:0 0 14px;">From Recurly's 2026 State of Subscriptions Report — the scale of what's recoverable when dunning is optimized:</p>

    <table class="rc-bench-table">
      <thead>
        <tr>
          <th>Industry</th>
          <th>Revenue Recovered (2025)</th>
          <th>Context</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>Software</td><td><strong>$155 million</strong></td><td>Highest recovery volume — automated dunning at scale</td></tr>
        <tr><td>Digital Media &amp; Entertainment</td><td><strong>$100 million</strong></td><td>High volume of monthly billing recoveries</td></tr>
        <tr><td>Consumer Goods &amp; Retail</td><td><strong>$34 million</strong></td><td>Recovering despite higher churn volatility</td></tr>
        <tr><td>Business &amp; Professional Services</td><td><strong>$19 million</strong></td><td>Smaller base, but high-value recovery per account</td></tr>
        <tr><td>Publishing</td><td><strong>$15 million</strong></td><td>Consistent recovery across mid-term subscribers</td></tr>
        <tr><td>Education</td><td><strong>$8 million</strong></td><td>Seasonal billing patterns affect recovery windows</td></tr>
      </tbody>
    </table>

    <div class="rc-img-placeholder">
      <div class="rc-img-icon">🖥️</div>
      <div class="rc-img-label">SCREENSHOT PLACEHOLDER</div>
      <div class="rc-img-sub">Insert screenshot: Dunning Recovery Rate dashboard — your rate vs. industry benchmark, with breakdown by recovery mechanism</div>
    </div>

    <!-- HOW TO IMPROVE -->
    <h3 class="rc-subhead">📈 How to improve your recovery rate — step by step</h3>
    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Enable Account Updater</h3>
          <p>If you haven't enabled Account Updater, this is the single highest-impact step. It automatically updates card details when issuers reissue cards — silently recovering payments before they even fail. Go to <strong>Configuration → Payment Settings</strong> to enable.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Review your dunning window length</h3>
          <p>Longer dunning windows give more opportunity for recovery — especially for soft declines like insufficient funds, which often clear within a few days. Review your cadence and window in Dunning Settings.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Enable Intelligent Retries</h3>
          <p>Recurly's machine learning models determine the optimal retry timing for each subscriber based on historical patterns — significantly improving recovery vs. fixed-cadence retries.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div>
          <h3>Set up Backup Payment Methods</h3>
          <p>Enable backup payment method collection at signup so Recurly has a fallback option if the primary payment fails at renewal.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div>
          <h3>Design billing-frequency-specific dunning</h3>
          <p>Monthly, quarterly, and annual invoices should have different dunning cadences. An annual subscriber's failed invoice has a much higher urgency and value — customize your approach accordingly.</p>
        </div>
      </div>
    </div>

    <!-- BEST PRACTICES CHECKLIST -->
    <h3 class="rc-subhead">✅ Best practices — getting the most from dunning benchmarks</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Dunning Benchmarks action checklist</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Use dunning recovery rate as a leading retention indicator<span>An improving recovery rate directly reduces involuntary churn — track it alongside your churn metrics</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">If your rate is below benchmark, audit which recovery mechanisms are enabled<span>A peer with all 6 mechanisms active will almost always outperform one using only 2</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Track recovery by mechanism<span>If Intelligent Retries is your top recovery driver, ensure settings are optimized. If Customer Updates underperforms, review your dunning email messaging and timing</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Benchmark improvement over time using the 18-month view<span>After each dunning optimization, confirm your recovery rate improved in subsequent months</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Consider the "silent save" value<span>Most recovered invoices happen without the subscriber ever knowing. A strong recovery rate is invisible to your customers — frictionless retention at its best</span></div></div>
    </div>

    <!-- OFFICE HOURS CTA -->
    <div class="rc-office-hours">
      <div class="rc-oh-content">
        <h4>🗓️ Need strategic support on your recovery setup?</h4>
        <p>Join our <strong>Customer Success Global Office Hours</strong>! Meet face-to-face with our CSMs to walk through your dunning analytics, review your recovery mechanism setup, and get strategic advice on closing the gap to benchmark.</p>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" style="background-color:#FFD706;color:#0D0D0B;text-decoration:none;padding:12px 24px;border-radius:10px;font-weight:700;font-size:.9rem;display:inline-flex;align-items:center;gap:10px;">Register for Office Hours →</a>
      </div>
    </div>

    <!-- THOUGHT LEADERSHIP -->
    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Thought leadership — AI is raising the bar on recovery</h4>
        <p>Nearly 40% of subscription companies now leverage AI operationally for revenue recovery. Recurly's Intelligent Retries uses machine learning to make real-time retry decisions — not fixed schedules. The businesses with the best recovery rates have moved beyond "retry on day 3" to letting data determine the optimal moment for each individual subscriber. Your dunning benchmark tells you how close you are to that standard.</p>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-benchmarks-renewal">← Section 3: Renewal Benchmarks</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-benchmarks-bestpractices">Next: Best Practices →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-benchmarks" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Dunning Benchmarks</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/built-in-benchmarks" target="_blank" rel="noopener noreferrer">📖 Built-In Benchmarks Overview</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" target="_blank" rel="noopener noreferrer">💳 Navigate: Account Updater Learning Path</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>

  </div>
</div>
</body>
</html>
`}</HTMLBlock>

<br />
