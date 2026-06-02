---
title: 'Benchmarks 101: Renewal'
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
  .rc-img-placeholder{background:var(--brightgray);border:2px dashed var(--lightgray);border-radius:12px;padding:32px 24px;text-align:center;margin-bottom:24px}
  .rc-img-icon{font-size:32px;margin-bottom:8px}.rc-img-label{font-size:.85rem;font-weight:700;color:var(--darkgray);margin-bottom:4px}.rc-img-sub{font-size:.78rem;color:var(--gray)}
  .rc-video-placeholder{background:var(--brightgray);border:2px dashed var(--lightgray);border-radius:12px;padding:40px 24px;text-align:center;margin-bottom:24px}
  .rc-video-icon{font-size:40px;margin-bottom:10px}.rc-video-label{font-size:.9rem;font-weight:700;color:var(--darkgray);margin-bottom:4px}.rc-video-sub{font-size:.8rem;color:var(--gray)}
  .rc-filter-pill{display:inline-flex;align-items:center;gap:6px;background:var(--brightgray);border:1px solid var(--lightgray);border-radius:20px;padding:5px 14px;font-size:.78rem;font-weight:600;color:var(--darkgray);margin:0 6px 8px 0}
  .rc-tag{display:inline-block;margin-top:10px;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;background:var(--offblack);color:var(--yellow)}
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
      <div class="rc-sec-icon">🔄</div>
      <div>
        <h2>Renewal Benchmarks</h2>
        <p>Invoice Paid Rate and Renewal Decline Rate — understand how your invoices are performing at renewal and exactly why failures happen, compared to your industry peers.</p>
      </div>
    </div>

    <!-- WHAT IT IS -->
    <div class="rc-card">
      <h3 class="rc-subhead">🧩 What is the Renewal Benchmarks dashboard?</h3>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Renewal Benchmarks give you visibility into the health of your ongoing subscription billing. Every renewal is a moment of truth — the Renewal dashboard tracks what percentage of those moments result in a successful payment, and what percentage fail on their first attempt.</p>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0;">It pairs your performance against industry peers, and lets you filter by gateway, payment type, and decline reason to isolate root causes and make targeted improvements.</p>
    </div>

    <!-- VIDEO -->
    <div class="rc-card">
      <h3 class="rc-subhead">📹 Walkthrough: Renewal Benchmarks</h3>
      <div class="rc-video-placeholder">
        <div class="rc-video-icon">▶️</div>
        <div class="rc-video-label">VIDEO PLACEHOLDER</div>
        <div class="rc-video-sub">Insert clip from "Stack Up Against the Competition" webinar — Renewal Invoice Paid Rate &amp; Renewal Decline walkthrough (~3–4 min)</div>
      </div>
    </div>

    <!-- KPI DEFINITIONS -->
    <h3 class="rc-subhead">📐 Two KPIs — two different lenses on renewal health</h3>

    <div class="rc-def-box">
      <div class="rc-def-title">✅ Renewal Invoice Paid Rate</div>
      <span class="rc-def-formula">Renewal Invoices Paid (by month-end) ÷ Total Renewal Invoices</span>
      <p>The percentage of all renewal invoices that end in a paid state by month-end — including those recovered during dunning after an initial failure. This is your most comprehensive payment health metric: it accounts for first-attempt success, dunning recovery, Account Updater, and retry results combined.</p>
    </div>

    <div class="rc-def-box">
      <div class="rc-def-title">🚫 Renewal Invoice Decline Rate</div>
      <span class="rc-def-formula">Renewal Invoices Declined on First Attempt ÷ Total Renewal Invoices</span>
      <p>The percentage of renewal invoices that are declined on their <em>first</em> transaction attempt. This metric isolates your payment authorization quality — it does not reflect what happens in dunning afterward. An invoice recovered in dunning still counts as declined here.</p>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Key distinction — paid rate vs. decline rate</h4>
        <p>The <strong>Renewal Invoice Paid Rate</strong> is your overall success rate — it captures the final outcome after all recovery efforts. The <strong>Renewal Decline Rate</strong> measures only first-attempt failures. Use both together: a high decline rate with a high paid rate means your dunning and recovery tools are working hard. A low paid rate regardless of decline rate means recovery is the problem to solve.</p>
      </div>
    </div>

    <!-- FILTERS -->
    <h3 class="rc-subhead">🔧 Dashboard filters — get precise with your data</h3>
    <div class="rc-card">
      <h3 class="rc-subhead">Filter the Renewal Decline dashboard by:</h3>
      <div style="margin-bottom:8px;">
        <span class="rc-filter-pill">📅 Invoice Creation Date (up to 18 months)</span>
        <span class="rc-filter-pill">🏭 Industry</span>
        <span class="rc-filter-pill">🏦 Gateway</span>
        <span class="rc-filter-pill">⚠️ Failure / Decline Type (top 5 by default)</span>
        <span class="rc-filter-pill">💳 Payment Type / Method</span>
      </div>
      <p style="font-size:.87rem;color:var(--gray);line-height:1.55;margin:0;">Use the <strong>Gateway filter</strong> to compare decline rates between processors. If one gateway shows significantly higher declines, explore a different provider or routing logic. Use the <strong>Industry filter</strong> to compare against a different vertical — useful if you're expanding into a new market segment.</p>
    </div>

    <div class="rc-img-placeholder">
      <div class="rc-img-icon">🖥️</div>
      <div class="rc-img-label">SCREENSHOT PLACEHOLDER</div>
      <div class="rc-img-sub">Insert screenshot: Renewal Decline dashboard with filter panel open, showing gateway and failure type filters applied</div>
    </div>

    <!-- REGIONAL DYNAMICS -->
    <div class="rc-card" style="border-left:4px solid var(--orange);">
      <h3 class="rc-subhead">🌍 Regional payment friction — why geography changes your renewal strategy</h3>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Recurly's 2026 State of Subscriptions data reveals a critical regional pattern — payment friction at signup vs. renewal differs dramatically by geography and payment method.</p>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step">
          <div class="rc-sbadge">US</div>
          <div>
            <h3>U.S. subscribers</h3>
            <p>Credit and debit card users are twice as likely to experience <em>sign-up</em> declines, but have lower renewal decline rates. The risk is front-loaded at checkout.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-sbadge">EU</div>
          <div>
            <h3>EMEA subscribers</h3>
            <p>Wallet-based APMs (PayPal, Apple Pay) sign up easily but are <em>twice as likely</em> to encounter renewal declines — wallet tokens expire or fall out of sync over time.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-sbadge">→</div>
          <div>
            <h3>Implication</h3>
            <p>If you have significant EMEA volume, your Renewal Decline benchmark should be interpreted against EMEA-specific baselines, and your dunning strategy should account for APM-specific recovery mechanics.</p>
          </div>
        </div>
      </div>
    </div>

    <div class="rc-img-placeholder">
      <div class="rc-img-icon">🖥️</div>
      <div class="rc-img-label">SCREENSHOT PLACEHOLDER</div>
      <div class="rc-img-sub">Insert screenshot: Renewal Decline Rate trended over 18 months with industry benchmark overlay</div>
    </div>

    <!-- WHY IT MATTERS -->
    <h3 class="rc-subhead">💼 Why renewal benchmarks matter for your business</h3>
    <div class="rc-2col">
      <div class="rc-wi">
        <div class="rc-wi-icon">🏦</div>
        <h4>Gateway strategy</h4>
        <p>Isolate decline performance by gateway to find which processors are underperforming on renewals — not just signups. A routing change can have an outsized impact on paid rate.</p>
        <span class="rc-tag">Optimization</span>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">💳</div>
        <h4>Payment method mix</h4>
        <p>Identify which payment types are driving your decline rate. If debit cards decline significantly more at renewal, consider promoting alternatives at checkout.</p>
        <span class="rc-tag">Checkout Mix</span>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">🔬</div>
        <h4>Decline reason analysis</h4>
        <p>The top 5 decline reasons are shown by default. Soft declines (insufficient funds) and hard declines (invalid card) require different recovery strategies.</p>
        <span class="rc-tag">Root Cause</span>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">📅</div>
        <h4>Seasonal patterns</h4>
        <p>Track renewal declines over 18 months to identify seasonal trends. Holiday periods often see higher decline rates — plan your dunning cadence accordingly.</p>
        <span class="rc-tag">Planning</span>
      </div>
    </div>

    <!-- BEST PRACTICES -->
    <h3 class="rc-subhead">✅ Best practices — optimizing your renewal performance</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Renewal Benchmarks action checklist</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Use the Renewal Invoice Paid Rate as your primary KPI<span>It reflects the total outcome of all your recovery efforts, not just first-attempt authorization quality</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Benchmark the Decline Rate by gateway separately<span>If one gateway's decline rate consistently exceeds benchmark, explore alternative routing or a new payment partner</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Design separate dunning cadences for monthly, quarterly, and annual plans<span>The timing and urgency of recovery should match the subscriber's billing frequency and the invoice value</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Build pre-renewal playbooks for annual subscribers<span>Annual renewals have an 82.9% success rate — meaning nearly 1 in 5 will fail. Send pre-renewal nudges 2–4 weeks out</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Monitor decline reason trends over time<span>If "Do Not Honor" spikes, it may signal fraud. If "Insufficient Funds" rises, it may reflect a broader economic signal in your subscriber base</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Use the 18-month date range to measure the impact of changes<span>Track whether a new gateway, payment method, or pricing change improved or worsened your renewal performance</span></div></div>
    </div>

    <!-- THOUGHT LEADERSHIP -->
    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Thought leadership — renewals as "found money"</h4>
        <p>Out of every 100 renewal attempts, roughly 9 will decline and move into dunning. Businesses with the strongest recovery rates treat these as "found money" — not lost customers. Software companies alone recovered over $155 million in would-be lost revenue through dunning in 2025. Your Renewal Decline benchmark tells you how much opportunity is waiting to be recovered.</p>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-benchmarks-churn">← Section 2: Churn Benchmarks</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-benchmarks-dunning">Next: Dunning Benchmarks →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/renewal-benchmarks" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Renewal Benchmarks</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/built-in-benchmarks" target="_blank" rel="noopener noreferrer">📖 Built-In Benchmarks Overview</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/analytics-settings" target="_blank" rel="noopener noreferrer">⚙️ Analytics Settings</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>

  </div>
</div>
</body>
</html>
`}</HTMLBlock>

<br />
