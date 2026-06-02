---
title: Benchmarks 101
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
  .rc-kpi-table{width:100%;border-collapse:collapse;margin-bottom:24px;font-size:.88rem}
  .rc-kpi-table th{background:var(--offblack);color:var(--offwhite);font-weight:700;padding:10px 16px;text-align:left;font-size:.8rem;letter-spacing:.04em}
  .rc-kpi-table td{padding:10px 16px;border-bottom:1px solid var(--lightgray);color:var(--darkgray);line-height:1.5}
  .rc-kpi-table tr:nth-child(even) td{background:var(--brightgray)}
  .rc-img-placeholder{background:var(--brightgray);border:2px dashed var(--lightgray);border-radius:12px;padding:32px 24px;text-align:center;margin-bottom:24px}
  .rc-img-icon{font-size:32px;margin-bottom:8px}.rc-img-label{font-size:.85rem;font-weight:700;color:var(--darkgray);margin-bottom:4px}.rc-img-sub{font-size:.78rem;color:var(--gray)}
  .rc-video-placeholder{background:var(--brightgray);border:2px dashed var(--lightgray);border-radius:12px;padding:40px 24px;text-align:center;margin-bottom:24px}
  .rc-video-icon{font-size:40px;margin-bottom:10px}.rc-video-label{font-size:.9rem;font-weight:700;color:var(--darkgray);margin-bottom:4px}.rc-video-sub{font-size:.8rem;color:var(--gray)}
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

  <!-- HERO -->
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

  <!-- TAB NAV -->
  <nav class="rc-nav">
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101">Benchmarks</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-subscriber"><span class="rc-snum">1</span>Subscriber</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-churn"><span class="rc-snum">2</span>Churn</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-renewal"><span class="rc-snum">3</span>Renewal</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-dunning"><span class="rc-snum">4</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-best-practices"><span class="rc-snum">5</span>Best Practices</a>
  </nav>


  <!-- SECTION -->
  <div class="rc-sec">

    <div class="rc-sec-header">
      <div class="rc-sec-icon">📊</div>
      <div>
        <h2>What are Recurly's Built-In Benchmarks?</h2>
        <p>Real-time comparisons against thousands of subscription businesses — built directly into your Recurly analytics, no exports or spreadsheets required.</p>
      </div>
    </div>

    <!-- INTRO CARD -->
    <div class="rc-card">
      <h3 class="rc-subhead">🧩 The simple version</h3>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Most subscription businesses track their metrics in isolation. Is a 3% monthly churn rate good or bad? Is your sign-up decline rate a red flag — or totally normal for your industry? Without context, numbers are just numbers.</p>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0;"><strong>Recurly's built-in benchmarks solve this.</strong> By anonymously aggregating data from over 2,200 subscription merchants and 76 million unique subscribers, Recurly surfaces industry comparisons directly inside your analytics dashboard. Your data, in context, in real time — without leaving the platform.</p>
    </div>

    <!-- STATS -->
    <div class="rc-stat-grid">
      <div class="rc-stat"><div class="rc-stat-num">2,200+</div><div class="rc-stat-label">Subscription merchants powering the benchmarks</div></div>
      <div class="rc-stat"><div class="rc-stat-num">76M</div><div class="rc-stat-label">Unique subscribers analyzed annually</div></div>
      <div class="rc-stat"><div class="rc-stat-num">10</div><div class="rc-stat-label">KPIs benchmarked across your subscription lifecycle</div></div>
    </div>

    <!-- VIDEO -->
    <div class="rc-card">
      <h3 class="rc-subhead">📹 Introduction: Benchmarks overview</h3>
      <div class="rc-video-placeholder">
        <div class="rc-video-icon">▶️</div>
        <div class="rc-video-label">VIDEO PLACEHOLDER</div>
        <div class="rc-video-sub">Insert intro clip from "Stack Up Against the Competition" webinar — ~2–3 min overview of the benchmarks concept and dashboard walkthrough</div>
      </div>
    </div>

    <!-- THE 10 KPIs -->
    <h3 class="rc-subhead">🗺️ The 10 benchmark KPIs — what gets measured</h3>
    <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 16px;">Across four dashboard areas, Recurly tracks 10 core KPIs that map to every stage of the subscriber lifecycle — from first payment to final recovery.</p>

    <table class="rc-kpi-table">
      <thead>
        <tr>
          <th>Dashboard</th>
          <th>KPI</th>
          <th>What it measures</th>
        </tr>
      </thead>
      <tbody>
        <tr><td><strong>Subscriber</strong></td><td>Acquisition Rate</td><td>New paying subscribers acquired per month as a % of your base</td></tr>
        <tr><td><strong>Subscriber</strong></td><td>Sign-Up Decline Rate</td><td>% of first payment attempts that fail at signup</td></tr>
        <tr><td><strong>Churn</strong></td><td>Voluntary Churn Rate</td><td>% of subscribers who choose to cancel</td></tr>
        <tr><td><strong>Churn</strong></td><td>Involuntary Churn Rate</td><td>% of subscribers lost to payment failure</td></tr>
        <tr><td><strong>Churn</strong></td><td>Total Churn Rate</td><td>Combined voluntary + involuntary churn</td></tr>
        <tr><td><strong>Renewal</strong></td><td>Renewal Invoice Paid Rate</td><td>% of renewal invoices successfully paid (including dunning recovery)</td></tr>
        <tr><td><strong>Renewal</strong></td><td>Decline Rate at Renewal</td><td>% of renewals declined on first attempt</td></tr>
        <tr><td><strong>Dunning</strong></td><td>Dunning Recovery Rate</td><td>% of dunned invoices ultimately recovered</td></tr>
      </tbody>
    </table>

    <!-- HOW TO ACCESS -->
    <h3 class="rc-subhead">🔧 How to access benchmarks in Recurly</h3>
    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Log in to your Recurly Admin</h3>
          <p>Navigate to your account dashboard at app.recurly.com</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Go to Analytics</h3>
          <p>Select <strong>Analytics</strong> from the left sidebar navigation</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Select a Benchmark Dashboard</h3>
          <p>Choose from Subscriber Benchmarks, Churn, Renewal, or Dunning within the Analytics sections</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div>
          <h3>Set your industry in Analytics Settings</h3>
          <p>Go to Analytics Settings to confirm your industry classification — this determines your peer group. Industry changes can take up to 24 hours to update.</p>
        </div>
      </div>
    </div>

    <div class="rc-img-placeholder">
      <div class="rc-img-icon">🖥️</div>
      <div class="rc-img-label">SCREENSHOT PLACEHOLDER</div>
      <div class="rc-img-sub">Insert screenshot: Recurly Analytics left nav with Benchmarks section highlighted</div>
    </div>

    <!-- WHAT'S IN THIS PATH -->
    <div class="rc-card">
      <h3 class="rc-subhead">📋 What's in this learning path</h3>
      <p style="font-size:.87rem;color:var(--gray);line-height:1.6;margin:0 0 16px;">This path walks you through each benchmark area — what it measures, why it matters, how to read it, and the best practices to act on what you find.</p>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step"><div class="rc-sbadge" style="background:var(--yellow);color:var(--offblack);">1</div><div><h3>Subscriber Benchmarks</h3><p>Acquisition rate, sign-up decline rate, and cohort retention</p></div></div>
        <div class="rc-step"><div class="rc-sbadge" style="background:var(--yellow);color:var(--offblack);">2</div><div><h3>Churn Benchmarks</h3><p>Voluntary, involuntary, and combined churn by industry</p></div></div>
        <div class="rc-step"><div class="rc-sbadge" style="background:var(--yellow);color:var(--offblack);">3</div><div><h3>Renewal Benchmarks</h3><p>Renewal invoice paid rate and first-attempt decline rate</p></div></div>
        <div class="rc-step"><div class="rc-sbadge" style="background:var(--yellow);color:var(--offblack);">4</div><div><h3>Dunning Benchmarks</h3><p>Recovery rate vs. peers after invoices enter dunning</p></div></div>
        <div class="rc-step"><div class="rc-sbadge" style="background:var(--yellow);color:var(--offblack);">5</div><div><h3>Best Practices</h3><p>Actionable playbooks for improving every benchmark area</p></div></div>
      </div>
    </div>

    <!-- WHY IT MATTERS -->
    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Why benchmarks matter</h4>
        <p>According to Recurly's 2026 State of Subscriptions Report, subscription growth slowed from 15.4% to 12.6% in 2025 — and 52% of consumers canceled at least one subscription. The businesses that win are those using data to act, not just observe. Benchmarks give you that context.</p>
      </div>
    </div>

    <!-- 2026 CONTEXT -->
    <div class="rc-card">
      <h3 class="rc-subhead">📈 2026 market context — what the data tells us</h3>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 12px;">Recurly's 2026 State of Subscriptions Report reveals the macro trends shaping every benchmark comparison you'll see in this learning path:</p>
      <div class="rc-3col">
        <div class="rc-wi">
          <div class="rc-wi-icon">📉</div>
          <h4>Growth slowdown</h4>
          <p>Subscriber growth slowed to ~3% on average in 2025. Healthcare led at +137.3%; Consumer Goods contracted at -11.0%</p>
        </div>
        <div class="rc-wi">
          <div class="rc-wi-icon">🚪</div>
          <h4>Cancel surge</h4>
          <p>52% of consumers canceled at least one subscription in the past 12 months — most often because they weren't using it enough</p>
        </div>
        <div class="rc-wi">
          <div class="rc-wi-icon">💰</div>
          <h4>Recovery opportunity</h4>
          <p>Subscription companies recovered hundreds of millions in would-be lost revenue through dunning — benchmarks show you where you stand</p>
        </div>
      </div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Before you benchmark:</strong> Make sure your industry is correctly set in Analytics Settings. An incorrect industry classification will skew every comparison in this path. Changes take up to 24 hours to reflect. Go to <strong>Analytics → Settings → Industry</strong> to confirm.</p>
    </div>

    <!-- NAV BUTTONS -->
    <div class="rc-sec-nav">
      <span class="rc-btn-disabled">🎯 Start</span>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-benchmarks-subscriber">Next: Subscriber Benchmarks →</a>
    </div>

    <!-- ADDITIONAL RESOURCES -->
    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/built-in-benchmarks" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Built-In Benchmarks</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/analytics-settings" target="_blank" rel="noopener noreferrer">⚙️ Analytics Settings</a>
    <a class="rc-link-btn rc-link-sec" href="https://recurly.com/research/" target="_blank" rel="noopener noreferrer">📊 Recurly Research Hub</a>
    <a class="rc-link-btn rc-link-sec" href="https://recurly.com/blog/built-in-subscription-benchmarks/" target="_blank" rel="noopener noreferrer">📰 Introducing Built-In Benchmarks — Blog</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>

  </div>
</div>
</body>
</html>
`}</HTMLBlock>

<br />
