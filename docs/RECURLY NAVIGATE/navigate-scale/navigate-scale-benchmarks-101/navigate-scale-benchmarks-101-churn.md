---
title: 'Benchmarks 101: Churn'
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
  .rc-tag{display:inline-block;margin-top:10px;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;background:var(--offblack);color:var(--yellow)}
  .rc-churn-type{border-radius:14px;padding:20px;border:1px solid var(--lightgray);text-align:center;background:var(--offwhite)}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev,.rc-btn-disabled{border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-3col,.rc-2col{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
      <div class="rc-sec-icon">📉</div>
      <div>
        <h2>Churn Benchmarks</h2>
        <p>Voluntary, involuntary, and combined churn — understand whether your subscriber losses are a competitive problem or an industry norm, and which type to tackle first.</p>
      </div>
    </div>

    <!-- WHAT IT IS -->
    <div class="rc-card">
      <h3 class="rc-subhead">🧩 What is the Subscriber Churn Analysis dashboard?</h3>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">The Subscriber Churn Analysis dashboard monitors subscription losses over a specified timeframe, breaking them down by <strong>voluntary</strong> (subscriber-initiated) and <strong>involuntary</strong> (payment failure) reasons.</p>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0;">Paired with industry benchmarks, it transforms your churn number from a raw metric into a competitive signal — telling you not just how much you're losing, but <em>why</em>, and whether it's normal for businesses like yours.</p>
    </div>

    <!-- THREE TYPES -->
    <h3 class="rc-subhead">🔎 The three churn types — know the difference</h3>
    <div class="rc-3col">
      <div class="rc-churn-type" style="border-top:4px solid var(--orange);">
        <div style="font-size:28px;margin-bottom:10px;">🖐️</div>
        <h4 style="font-size:.9rem;font-weight:800;margin:0 0 6px;color:var(--offblack);">Voluntary Churn</h4>
        <p style="font-size:.8rem;color:var(--gray);line-height:1.5;margin:0;">Subscribers who choose to cancel. Driven by perceived value, pricing, or lifestyle changes. Requires a retention and engagement fix.</p>
        <span class="rc-tag">Subscriber Intent</span>
      </div>
      <div class="rc-churn-type" style="border-top:4px solid #c0392b;">
        <div style="font-size:28px;margin-bottom:10px;">💳</div>
        <h4 style="font-size:.9rem;font-weight:800;margin:0 0 6px;color:var(--offblack);">Involuntary Churn</h4>
        <p style="font-size:.8rem;color:var(--gray);line-height:1.5;margin:0;">Subscribers lost to payment failure. Expired cards, insufficient funds, gateway issues. Requires a payment recovery fix.</p>
        <span class="rc-tag">Payment Failure</span>
      </div>
      <div class="rc-churn-type" style="border-top:4px solid var(--offblack);">
        <div style="font-size:28px;margin-bottom:10px;">📊</div>
        <h4 style="font-size:.9rem;font-weight:800;margin:0 0 6px;color:var(--offblack);">Total Churn</h4>
        <p style="font-size:.8rem;color:var(--gray);line-height:1.5;margin:0;">The combined rate. Your headline retention metric — benchmark this against your industry to understand your competitive position.</p>
        <span class="rc-tag">Overall Health</span>
      </div>
    </div>

    <!-- VIDEO -->
    <div class="rc-card">
      <h3 class="rc-subhead">📹 Walkthrough: Churn Benchmarks</h3>
      <div class="rc-video-placeholder">
        <div class="rc-video-icon">▶️</div>
        <div class="rc-video-label">VIDEO PLACEHOLDER</div>
        <div class="rc-video-sub">Insert clip from "Stack Up Against the Competition" webinar — Churn Benchmarking walkthrough segment (~3–5 min)</div>
      </div>
    </div>

    <!-- KPI DEFINITIONS -->
    <h3 class="rc-subhead">📐 KPI definitions — how each type is calculated</h3>

    <div class="rc-def-box">
      <div class="rc-def-title">🖐️ Voluntary Churn Rate</div>
      <span class="rc-def-formula">Voluntary Cancellations ÷ Total Paid Subscribers (start of period)</span>
      <p>Subscribers who actively cancel their subscription. Reflects value perception — if voluntary churn rises, subscribers don't see enough reason to stay. The most common reasons: not using it enough (51%), price too high (45%), lost interest (32%).</p>
    </div>

    <div class="rc-def-box">
      <div class="rc-def-title">💳 Involuntary Churn Rate</div>
      <span class="rc-def-formula">Payment-Failure Cancellations ÷ Total Paid Subscribers (start of period)</span>
      <p>Subscribers lost because their payment failed and was not recovered. This is largely a recoverable problem — better dunning, Account Updater, and retry logic can significantly reduce it. Many merchants cut involuntary churn substantially after enabling Recurly's recovery tools.</p>
    </div>

    <div class="rc-def-box">
      <div class="rc-def-title">📊 Total Churn Rate</div>
      <span class="rc-def-formula">Total Churned Subscribers ÷ Total Paid Subscribers (start of period)</span>
      <p>The sum of voluntary and involuntary churn. This is your headline retention metric — benchmark it against your industry to understand your competitive position.</p>
    </div>

    <!-- INDUSTRY TABLE -->
    <h3 class="rc-subhead">🏭 2025 average monthly churn by industry</h3>
    <p style="font-size:.88rem;color:var(--gray);margin:0 0 14px;">From Recurly's 2026 State of Subscriptions Report — average monthly total churn rates across industries:</p>

    <table class="rc-bench-table">
      <thead>
        <tr>
          <th>Industry</th>
          <th>Avg Monthly Churn 2024</th>
          <th>Avg Monthly Churn 2025</th>
          <th>Trend</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>Healthcare</td><td>2.7%</td><td><strong>3.0%</strong></td><td>↑ Rising</td></tr>
        <tr><td>Business &amp; Professional Services</td><td>3.7%</td><td>3.7%</td><td>→ Stable</td></tr>
        <tr><td>Education</td><td>6.1%</td><td><strong>5.7%</strong></td><td>↓ Improving</td></tr>
        <tr><td>Software</td><td>3.0%</td><td><strong>2.9%</strong></td><td>↓ Improving</td></tr>
        <tr><td>Publishing</td><td>3.3%</td><td>3.3%</td><td>→ Stable</td></tr>
        <tr><td>Digital Media &amp; Entertainment</td><td>5.6%</td><td><strong>5.5%</strong></td><td>↓ Improving</td></tr>
        <tr><td>Consumer Goods &amp; Retail</td><td>3.9%</td><td>3.9%</td><td>→ Stable</td></tr>
      </tbody>
    </table>

    <div class="rc-img-placeholder">
      <div class="rc-img-icon">🖥️</div>
      <div class="rc-img-label">SCREENSHOT PLACEHOLDER</div>
      <div class="rc-img-sub">Insert screenshot: Churn Analysis dashboard showing voluntary vs. involuntary split with industry benchmark overlay</div>
    </div>

    <!-- PLAN TYPE DYNAMICS -->
    <div class="rc-card">
      <h3 class="rc-subhead">📋 Monthly vs. annual plan churn dynamics</h3>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 16px;">Understanding how your plan mix affects your churn benchmark is critical. Monthly and annual plans have very different churn profiles — your benchmark comparison should reflect that.</p>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step">
          <div class="rc-sbadge">M</div>
          <div>
            <h3>Monthly plans</h3>
            <p>Higher early-cycle churn, but 53% recovery rate when invoices fail. More volatile month-to-month, but flexible and easier to recover from payment failures.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-sbadge">A</div>
          <div>
            <h3>Annual plans</h3>
            <p>82.9% renewal rate at the annual moment — but only 23.3% of failed annual renewals are recovered. Annual subscribers generate 50–60% more revenue over their lifetime, but the renewal moment is high-risk.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-sbadge">→</div>
          <div>
            <h3>Strategy</h3>
            <p>Offer annual plans selectively to high-LTV, engaged subscribers. Build pre-renewal playbooks for annual renewals — they are high-stakes moments that deserve dedicated attention.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- WHY IT MATTERS -->
    <h3 class="rc-subhead">💼 Why separating churn types matters</h3>
    <div class="rc-2col">
      <div class="rc-wi">
        <div class="rc-wi-icon">🔍</div>
        <h4>Diagnose the right problem</h4>
        <p>High voluntary churn needs a retention fix. High involuntary churn needs a payment recovery fix. They require completely different solutions.</p>
        <span class="rc-tag">Root Cause</span>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">📈</div>
        <h4>Track strategy impact</h4>
        <p>After enabling Account Updater or adjusting your dunning cadence, use churn benchmarks to confirm improvement in involuntary churn over subsequent months.</p>
        <span class="rc-tag">Measurement</span>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">🚨</div>
        <h4>Spot underlying issues</h4>
        <p>A spike in voluntary churn in a specific cohort may indicate a product or billing change that affected perceived value — catch it before it compounds.</p>
        <span class="rc-tag">Early Warning</span>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">🏆</div>
        <h4>Competitive positioning</h4>
        <p>If your churn rate is below your industry benchmark, you have a defensible retention advantage — a signal to lean into retention-led growth strategies.</p>
        <span class="rc-tag">Benchmarking</span>
      </div>
    </div>

    <!-- BEST PRACTICES -->
    <h3 class="rc-subhead">✅ Best practices — turning churn benchmarks into action</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Churn Benchmarks action checklist</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Separate voluntary and involuntary churn in your reporting<span>Treating them as one metric hides where to focus — the solutions are completely different</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">If involuntary churn is above benchmark, activate Account Updater and review your dunning cadence<span>Enable Intelligent Retries and Backup Payment Method collection — one merchant saw major improvements with Account Updater alone</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">If voluntary churn is above benchmark, investigate cancel reasons<span>Are subscribers not using the product? Consider pause options or downgrade paths before they reach cancel</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Implement a "pause before cancel" option<span>Brands offering this saw 337% more pauses — and 3 out of 4 paused subscribers returned within months</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Monitor churn monthly by cohort<span>If new subscriber cohorts are churning faster than older ones, it's an early warning sign of product-market fit issues</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Treat former subscribers as a win-back segment<span>Nearly 1 in 4 new subscriptions in 2025 came from a previously canceled customer — target them with personalized win-back campaigns</span></div></div>
    </div>

    <!-- THOUGHT LEADERSHIP -->
    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Thought leadership — what churn is really telling you</h4>
        <p>52% of consumers canceled at least one subscription in the past 12 months — most often because they weren't using it enough (51%). Churn is not primarily a pricing or payment problem. It's an engagement and perceived value problem. Benchmarks help you separate the two and allocate resources accordingly. The businesses that win are those who build retention systems before churn spikes — not after.</p>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-benchmarks-subscriber">← Section 1: Subscriber Benchmarks</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-benchmarks-renewal">Next: Renewal Benchmarks →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/subscriber-churn-benchmarks" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Churn Benchmarks</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/built-in-benchmarks" target="_blank" rel="noopener noreferrer">📖 Built-In Benchmarks Overview</a>
    <a class="rc-link-btn rc-link-sec" href="https://recurly.com/research/" target="_blank" rel="noopener noreferrer">📊 Recurly Research Hub</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>

  </div>
</div>
</body>
</html>
`}</HTMLBlock>

<br />
