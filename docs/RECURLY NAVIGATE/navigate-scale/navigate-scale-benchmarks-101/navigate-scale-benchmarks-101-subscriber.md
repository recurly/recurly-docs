---
title: 'Benchmarks 101: Subscriber'
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
  .rc-stat-grid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-stat{background:var(--offblack);border-radius:14px;padding:24px 16px;text-align:center}
  .rc-stat-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}.rc-stat-label{font-size:.78rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px;margin-top:4px}
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
  .rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;background:#fff;display:flex;align-items:center;justify-content:center;font-size:12px;color:var(--gray)}
  .rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}.rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
  .rc-img-placeholder{background:var(--brightgray);border:2px dashed var(--lightgray);border-radius:12px;padding:32px 24px;text-align:center;margin-bottom:24px}
  .rc-img-icon{font-size:32px;margin-bottom:8px}.rc-img-label{font-size:.85rem;font-weight:700;color:var(--darkgray);margin-bottom:4px}.rc-img-sub{font-size:.78rem;color:var(--gray)}
  .rc-video-placeholder{background:var(--brightgray);border:2px dashed var(--lightgray);border-radius:12px;padding:40px 24px;text-align:center;margin-bottom:24px}
  .rc-video-icon{font-size:40px;margin-bottom:10px}.rc-video-label{font-size:.9rem;font-weight:700;color:var(--darkgray);margin-bottom:4px}.rc-video-sub{font-size:.8rem;color:var(--gray)}
  .rc-tag{display:inline-block;margin-top:10px;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;background:var(--offblack);color:var(--yellow)}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev,.rc-btn-disabled{border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-3col,.rc-2col,.rc-stat-grid{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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

  </nav>

  <div class="rc-sec">

    <div class="rc-sec-header">
      <div class="rc-sec-icon">👥</div>
      <div>
        <h2>Subscriber Benchmarks</h2>
        <p>Acquisition Rate and Sign-Up Decline Rate — understand how effectively you're growing and converting new paying subscribers compared to your industry peers.</p>
      </div>
    </div>

    <!-- WHAT IT IS -->
    <div class="rc-card">
      <h3 class="rc-subhead">🧩 What is the Subscriber Benchmarks dashboard?</h3>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">The Subscriber Benchmarks dashboard is your first window into subscription health. It reveals how effectively you're acquiring and converting new paying subscribers — relative to thousands of businesses in your industry.</p>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0;">It covers two core KPIs: <strong>Acquisition Rate</strong> (how fast you're growing) and <strong>Sign-Up Decline Rate</strong> (how often first payments fail at signup). Together, they define the top of your subscription funnel.</p>
    </div>

    <!-- VIDEO -->
    <div class="rc-card">
      <h3 class="rc-subhead">📹 Walkthrough: Subscriber Benchmarks</h3>
      <div class="rc-video-placeholder">
        <div class="rc-video-icon">▶️</div>
        <div class="rc-video-label">VIDEO PLACEHOLDER</div>
        <div class="rc-video-sub">Insert clip from "Stack Up Against the Competition" webinar — Acquisition Rate &amp; Sign-Up Decline walkthrough (~2–4 min)</div>
      </div>
    </div>

    <!-- ACQUISITION RATE -->
    <h3 class="rc-subhead">📈 KPI: Acquisition Rate</h3>

    <div class="rc-def-box">
      <div class="rc-def-title">Acquisition Rate</div>
      <span class="rc-def-formula">Monthly New Paying Subscribers ÷ Total Paying Subscribers</span>
      <p>Measures the percentage of your subscriber base that is newly acquired each month. Recurly counts a subscriber as "acquired" when they have at least one non-expired subscription at month-end, after having no active subscription at month-start.</p>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🔑 Eligibility rules — what counts as an acquisition</h3>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step">
          <div class="rc-sbadge">✓</div>
          <div>
            <h3>Paying subscribers only</h3>
            <p>Trial users are excluded. Only subscribers who have made at least one successful payment are counted in this metric.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-sbadge">✓</div>
          <div>
            <h3>No "ghost acquisitions"</h3>
            <p>A subscriber who churns and re-subscribes within the same month (while still active on Day 1) is <strong>not</strong> counted as a new acquisition. Recurly filters these out for accuracy.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-sbadge">✓</div>
          <div>
            <h3>Industry-adjusted comparison</h3>
            <p>Your acquisition rate is compared against peers in your selected industry — set in Analytics Settings. Healthcare saw +137.3% growth in 2025; Consumer Goods &amp; Retail contracted at -11.0%.</p>
          </div>
        </div>
      </div>
    </div>

    <div class="rc-img-placeholder">
      <div class="rc-img-icon">🖥️</div>
      <div class="rc-img-label">SCREENSHOT PLACEHOLDER</div>
      <div class="rc-img-sub">Insert screenshot: Acquisition Rate benchmark chart — your rate vs. industry average with trend line</div>
    </div>

    <!-- SIGN UP DECLINE -->
    <h3 class="rc-subhead">🚫 KPI: Sign-Up Decline Rate</h3>

    <div class="rc-def-box">
      <div class="rc-def-title">Sign-Up Decline Rate</div>
      <span class="rc-def-formula">Declined Initial Payment Attempts ÷ Total Sign-Up Payment Attempts</span>
      <p>Tracks the percentage of <em>first</em> payment attempts during signup that are declined. This is the very first transaction Recurly sends to your gateway. A high rate signals checkout friction — whether from payment method issues, gateway configuration, or fraud patterns.</p>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Current month data note:</strong> The current month's sign-up data will always appear lower than previous months because new signups continue to accumulate throughout the month. This is expected behavior — don't interpret it as a decline trend.</p>
    </div>

    <div class="rc-img-placeholder">
      <div class="rc-img-icon">🖥️</div>
      <div class="rc-img-label">SCREENSHOT PLACEHOLDER</div>
      <div class="rc-img-sub">Insert screenshot: Sign-Up Decline Rate trend chart showing year-over-year comparison view</div>
    </div>

    <!-- WHY IT MATTERS -->
    <h3 class="rc-subhead">💼 Why these metrics matter</h3>
    <div class="rc-2col">
      <div class="rc-wi">
        <div class="rc-wi-icon">🔍</div>
        <h4>Fraud detection</h4>
        <p>A sudden spike in sign-up declines may signal card testing or fraud on your checkout. One merchant saw a 500% spike in fraud responses — the benchmark dashboard caught it first.</p>
        <span class="rc-tag">Early Warning</span>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">🏦</div>
        <h4>Gateway comparison</h4>
        <p>Filter sign-up declines by gateway to compare approval rates across processors — especially useful if you use multiple gateways.</p>
        <span class="rc-tag">Optimization</span>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">💳</div>
        <h4>Payment method insights</h4>
        <p>Identify which card types or payment methods are driving higher decline rates so you can optimize your checkout mix.</p>
        <span class="rc-tag">Checkout Health</span>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">📊</div>
        <h4>Industry context</h4>
        <p>Compare your acquisition rate against peers in your segment — know whether your growth is ahead, in line, or lagging your industry.</p>
        <span class="rc-tag">Benchmarking</span>
      </div>
    </div>

    <!-- COHORT RETENTION -->
    <h3 class="rc-subhead">📉 Subscriber Cohort Descent</h3>
    <div class="rc-card">
      <h3 class="rc-subhead">Understanding cohort retention over time</h3>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Within the Subscriber Benchmarks dashboard, you'll also find a <strong>Subscriber Cohort Descent</strong> chart — a powerful view that shows how well subscribers acquired in a given month are retained over time.</p>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0;">Each line in the chart represents a cohort of subscribers who made their first payment in that calendar month. The chart tracks what percentage of them remain active in subsequent months. A sharp drop in Month 2 signals onboarding or value delivery issues. A slow steady descent is healthy and expected.</p>
    </div>

    <div class="rc-card" style="border-left:4px solid var(--orange);">
      <h3 class="rc-subhead">📋 How cohorts are defined</h3>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step">
          <div class="rc-sbadge">→</div>
          <div><h3>Sign-up month</h3><p>The month a subscriber makes their first payment over $0. Trial users or those whose first paid invoice is still overdue are excluded.</p></div>
        </div>
        <div class="rc-step">
          <div class="rc-sbadge">→</div>
          <div><h3>Retained</h3><p>Has at least one active subscription. A subscription on hold is <em>not</em> counted as churned.</p></div>
        </div>
        <div class="rc-step">
          <div class="rc-sbadge">→</div>
          <div><h3>Excluded from cohorts</h3><p>$0 invoices, trial subscriptions, gift card subscriptions, and subsequent subscriptions by existing subscribers.</p></div>
        </div>
      </div>
    </div>

    <div class="rc-img-placeholder">
      <div class="rc-img-icon">📉</div>
      <div class="rc-img-label">SCREENSHOT PLACEHOLDER</div>
      <div class="rc-img-sub">Insert screenshot: Subscriber Cohort Descent line chart showing monthly retention curves by cohort</div>
    </div>

    <!-- BEST PRACTICES CHECKLIST -->
    <h3 class="rc-subhead">✅ Best practices — what to do with what you find</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Subscriber Benchmarks action checklist</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Monitor sign-up declines weekly, not just monthly<span>Fraud and card testing events can spike and resolve quickly — monthly reviews will miss them</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Use year-over-year comparison for Sign-Up Decline Rate<span>Identifies seasonal patterns vs. emerging issues in your checkout</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Filter sign-up declines by gateway<span>A simple gateway swap or retry logic change can recover significant volume if one processor underperforms</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Cross-reference sign-up declines by payment type<span>U.S. subscribers on credit and debit cards typically see higher initial decline rates than wallet-based methods</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Use cohort data to identify early churn patterns<span>If Month 2 retention drops sharply, investigate onboarding and value delivery in the first 30–60 days</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Confirm your industry is set correctly in Analytics Settings<span>A software company benchmarked against consumer retail will see misleading acquisition comparisons</span></div></div>
    </div>

    <!-- THOUGHT LEADERSHIP -->
    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Thought leadership — the acquisition shift</h4>
        <p>Traditional free trial conversion is trending down (47% in 2021 → 34% in 2025). Short-term micro-subscriptions — day passes, weekend passes — are emerging as high-intent acquisition alternatives that convert 13% of buyers into recurring subscribers. If your acquisition rate is lagging benchmark, consider testing these lower-commitment entry points alongside your standard trial flow.</p>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-benchmarks-overview">← Benchmarks Overview</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-benchmarks-churn">Next: Churn Benchmarks →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/subscriber-benchmarks" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Subscriber Benchmarks</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/analytics-settings" target="_blank" rel="noopener noreferrer">⚙️ Analytics Settings</a>
    <a class="rc-link-btn rc-link-sec" href="https://recurly.com/research/" target="_blank" rel="noopener noreferrer">📊 Recurly Research Hub</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>

  </div>
</div>
</body>
</html>
`}</HTMLBlock>

<br />
