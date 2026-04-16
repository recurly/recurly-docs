---
title: Dunning - API TEST
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>

.rc-guide{max-width:900px;margin:20px auto;font-family:"Inter",-apple-system,sans-serif;color:#0D0D0B;line-height:1.6;background-color:#ffffff;border-radius:16px;overflow:hidden;box-shadow:0 4px 24px rgba(0,0,0,0.08)}
.rc-hero{background-color:#0D0D0B;color:#FFFFFF;padding:56px 40px 48px;text-align:center;position:relative;overflow:hidden}
.rc-badge{display:inline-block;background-color:#FFD706;color:#0D0D0B;border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;text-transform:uppercase;margin-bottom:20px;letter-spacing:.5px}
.rc-hero h1{font-size:32px;margin:0 0 12px;font-weight:700}
.rc-hero p{color:#CCC9B8;font-size:1.05rem;margin:0 auto;max-width:600px}
.rc-hero-stats{display:flex;justify-content:center;gap:48px;flex-wrap:wrap;margin-top:32px}
.rc-stat-num{font-size:28px;font-weight:800;color:#FFD706;display:block}
.rc-stat-lbl{font-size:11px;font-weight:600;color:#807D73;text-transform:uppercase;letter-spacing:.5px}
.rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:32px 0 40px;padding:0 40px}
.rc-nav a{display:inline-flex;align-items:center;gap:10px;padding:10px 16px;border-radius:12px;border:1px solid #CCC9B8;background-color:#FFFFFF;color:#32312D;text-decoration:none;font-size:.85rem;font-weight:700}
.rc-nav a:hover{border-color:#FFD706;color:#0D0D0B}
.rc-nav a.rc-active{border-color:#FFD706;background-color:#FFD706;color:#0D0D0B}
.rc-snum{display:inline-flex;align-items:center;justify-content:center;width:22px;height:22px;border-radius:50%;background-color:#0D0D0B;color:#FFD706;font-size:11px;font-weight:700}
.rc-nav a.rc-active .rc-snum{background-color:#0D0D0B;color:#FFD706}
.rc-body{padding:0 40px 40px}
.rc-sec-header{display:flex;gap:20px;align-items:flex-start;margin-bottom:28px}
.rc-sec-icon{width:52px;height:52px;background-color:#FFD706;border-radius:14px;display:flex;align-items:center;justify-content:center;flex-shrink:0;font-size:26px}
.rc-sec-header h2{font-size:22px;font-weight:700;margin:0 0 6px}
.rc-sec-header p{margin:0;color:#807D73;font-size:.95rem}
.rc-flow{background-color:#0D0D0B;border-radius:14px;padding:28px 20px;display:flex;align-items:center;gap:8px;flex-wrap:wrap;margin-bottom:24px;justify-content:center}
.rc-flow-node{background-color:rgba(255,253,242,.07);border:1px solid rgba(255,253,242,.14);border-radius:10px;padding:14px 16px;text-align:center;min-width:110px}
.rc-flow-node.hl{background-color:rgba(255,215,6,.14);border-color:rgba(255,215,6,.38)}
.rc-flow-icon{font-size:20px;display:block;margin-bottom:6px}
.rc-flow-lbl{font-size:12px;font-weight:700;color:#FFFDF2;display:block}
.rc-flow-sub{font-size:10px;color:rgba(255,253,242,.48);display:block;margin-top:2px}
.rc-flow-arrow{color:rgba(255,253,242,.3);font-size:20px}
.rc-3col{display:flex;gap:14px;margin-bottom:24px}
.rc-wi{flex:1;background-color:#FFFDF2;border-radius:12px;padding:22px;border:1px solid #CCC9B8}
.rc-wi-icon{font-size:26px;margin-bottom:10px;display:block}
.rc-wi h4{font-size:14px;font-weight:700;margin:0 0 7px;color:#0D0D0B}
.rc-wi p{font-size:12.5px;color:#32312D;margin:0;line-height:1.6}
.rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
.rc-card{background-color:#FFFDF2;border-radius:12px;padding:22px;border:1px solid #CCC9B8}
.rc-card h4{font-size:14px;font-weight:700;margin:0 0 8px;color:#0D0D0B}
.rc-card p{font-size:12.5px;color:#32312D;margin:0;line-height:1.6}
.rc-dark-card{background-color:#0D0D0B;border-radius:14px;padding:28px;margin-bottom:16px}
.rc-dark-card h3{font-size:16px;font-weight:700;color:#FFD706;margin:0 0 8px}
.rc-dark-card p{font-size:13.5px;color:#CCC9B8;margin:0;line-height:1.65}
.rc-tip{border-left:4px solid #FFD706;background-color:#FFFDF2;padding:20px 24px;border-radius:0 12px 12px 0;margin:20px 0}
.rc-tip p{margin:0;font-size:.92rem;color:#32312D;line-height:1.65}
.rc-warning{border-left:4px solid #FF8200;background-color:#FFF8F0;padding:20px 24px;border-radius:0 12px 12px 0;margin:20px 0}
.rc-warning p{margin:0;font-size:.92rem;color:#32312D;line-height:1.65}
.rc-subhead{font-size:18px;font-weight:700;margin:36px 0 16px;color:#0D0D0B}
.rc-subhead-sm{font-size:15px;font-weight:700;margin:24px 0 10px;color:#0D0D0B}
.rc-body p{font-size:.92rem;color:#32312D;line-height:1.7;margin:0 0 14px}
.rc-table{width:100%;border-collapse:collapse;font-size:13.5px;margin-bottom:20px;border-radius:10px;overflow:hidden;border:1px solid #CCC9B8}
.rc-table thead{background-color:#0D0D0B;color:#FFFDF2}
.rc-table thead th{padding:12px 16px;text-align:left;font-size:12px;font-weight:700;letter-spacing:.5px;text-transform:uppercase}
.rc-table tbody tr:nth-child(even){background-color:#F1EFE3}
.rc-table tbody tr:nth-child(odd){background-color:#FFFDF2}
.rc-table tbody td{padding:12px 16px;color:#32312D;border-bottom:1px solid #CCC9B8;vertical-align:top}
.rc-table tbody td strong{color:#0D0D0B}
.rc-steps{display:flex;flex-direction:column;gap:0;margin-bottom:24px}
.rc-step{display:flex;gap:20px;padding-bottom:24px;position:relative}
.rc-step:last-child{padding-bottom:0}
.rc-step-left{display:flex;flex-direction:column;align-items:center;flex-shrink:0}
.rc-step-dot{width:34px;height:34px;background-color:#0D0D0B;border-radius:50%;display:flex;align-items:center;justify-content:center;color:#FFD706;font-size:13px;font-weight:800;flex-shrink:0}
.rc-step-line{flex:1;width:2px;background-color:#F1EFE3;margin:6px 0;min-height:20px}
.rc-step:last-child .rc-step-line{display:none}
.rc-step-body{padding-top:5px}
.rc-step-body h4{font-size:14px;font-weight:700;color:#0D0D0B;margin:0 0 6px}
.rc-step-body p{font-size:13px;color:#32312D;line-height:1.65;margin:0}
.rc-tip-badge{display:flex;align-items:stretch;border-radius:12px;overflow:hidden;margin-bottom:24px;border:1px solid #CCC9B8}
.rc-tip-num{background-color:#FFD706;color:#0D0D0B;font-size:13px;font-weight:800;display:flex;align-items:center;justify-content:center;padding:0 18px;min-width:60px;text-align:center;line-height:1.3}
.rc-tip-title{background-color:#F1EFE3;padding:16px 20px;font-size:15px;font-weight:700;color:#0D0D0B;display:flex;align-items:center}
.rc-checklist{list-style:none;padding:0;margin:0 0 20px}
.rc-checklist li{display:flex;align-items:flex-start;gap:12px;font-size:.9rem;color:#32312D;line-height:1.6;padding:8px 0;border-bottom:1px solid #F1EFE3}
.rc-checklist li:last-child{border-bottom:none}
.rc-check{width:20px;height:20px;border:2px solid #CCC9B8;border-radius:5px;flex-shrink:0;margin-top:2px;display:flex;align-items:center;justify-content:center;font-size:10px;color:#807D73}
.rc-results-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-bottom:24px}
.rc-result-card{background-color:#FFFDF2;border:1px solid #CCC9B8;border-radius:12px;padding:20px}
.rc-result-num{font-size:28px;font-weight:800;color:#0D0D0B;display:block;margin-bottom:6px}
.rc-result-tag{display:inline-block;background-color:#FFD706;color:#0D0D0B;font-size:11px;font-weight:700;padding:3px 10px;border-radius:20px;margin-bottom:10px}
.rc-result-card p{font-size:12.5px;color:#32312D;margin:0;line-height:1.6}
.rc-resource-links{display:flex;flex-wrap:wrap;gap:10px;margin-bottom:24px}
.rc-resource-link{display:inline-flex;align-items:center;gap:7px;background-color:#F1EFE3;border:1px solid #CCC9B8;color:#0D0D0B;font-size:13px;font-weight:600;padding:9px 16px;border-radius:100px;text-decoration:none}
.rc-resource-link:hover{background-color:#FFD706;border-color:#FFD706}
.rc-divider{border:none;border-top:1px solid #F1EFE3;margin:32px 0}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;margin-top:48px;padding:24px 40px;border-top:1px solid #CCC9B8;background-color:#FFFFFF}
.rc-btn-next{background-color:#FFD706;color:#0D0D0B;padding:12px 28px;border-radius:10px;font-weight:700;text-decoration:none;font-size:.9rem}
.rc-btn-prev{background-color:#FFFFFF;color:#32312D;padding:12px 28px;border-radius:10px;font-weight:700;text-decoration:none;font-size:.9rem;border:1px solid #CCC9B8}
.rc-page-label{color:#807D73;font-weight:600;font-size:.88rem}
@media(max-width:640px){.rc-hero{padding:36px 20px 32px}.rc-hero h1{font-size:24px}.rc-hero-stats{gap:24px}.rc-nav{padding:0 20px}.rc-body{padding:0 20px 28px}.rc-3col,.rc-2col,.rc-results-grid{flex-direction:column;grid-template-columns:1fr}.rc-sec-nav{padding:20px}.rc-flow{flex-direction:column}}

</style>

<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">Recurly Navigate &middot; Dunning 101</div>
    <h1>Dunning 101</h1>
    <p>Recover more revenue, reduce passive churn, and build a dunning strategy that works quietly in the background.</p>
    <div class="rc-hero-stats">
      <div><span class="rc-stat-num">3&ndash;5%</span><span class="rc-stat-lbl">Avg Recovery Uplift</span></div>
      <div><span class="rc-stat-num">10</span><span class="rc-stat-lbl">Optimization Tips</span></div>
      <div><span class="rc-stat-num">27%</span><span class="rc-stat-lbl">Avg Recovery Rate</span></div>
    </div>
  </div>
  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-overview" class="rc-active"><span class="rc-snum">1</span> Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-why-it-matters"><span class="rc-snum">2</span> Why It Matters</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-how-to-access"><span class="rc-snum">3</span> How to Access</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-tip-1-branding"><span class="rc-snum">4</span> Tip 1: Branding</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-tip-2-spacing"><span class="rc-snum">5</span> Tip 2: Spacing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-tip-3-email-tones"><span class="rc-snum">6</span> Tip 3: Email Tones</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-tip-4-countdown"><span class="rc-snum">7</span> Tip 4: Countdown</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-tip-5-value"><span class="rc-snum">8</span> Tip 5: Value</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-tip-6-alternative-ctas"><span class="rc-snum">9</span> Tip 6: Alt CTAs</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-tip-7-urgency"><span class="rc-snum">10</span> Tip 7: Urgency</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-tip-8-campaigns"><span class="rc-snum">11</span> Tip 8: Campaigns</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-tip-9-delivery"><span class="rc-snum">12</span> Tip 9: Delivery</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-tip-10-in-app-banner"><span class="rc-snum">13</span> Tip 10: In-App</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-metrics"><span class="rc-snum">14</span> Metrics</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-think-and-lead"><span class="rc-snum">15</span> Think &amp; Lead</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-resources"><span class="rc-snum">&#10003;</span> Resources</a>
  </nav>

  <div class="rc-body">

    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔄</div>
      <div>
        <h2>What Is Dunning?</h2>
        <p>Understand how Recurly's dunning system works and the two engines driving payment recovery.</p>
      </div>
    </div>

    <div class="rc-flow">
      <div class="rc-flow-node">
        <span class="rc-flow-icon">💳</span>
        <span class="rc-flow-lbl">Payment Fails</span>
        <span class="rc-flow-sub">Invoice becomes past_due</span>
      </div>
      <span class="rc-flow-arrow">→</span>
      <div class="rc-flow-node hl">
        <span class="rc-flow-icon">🤖</span>
        <span class="rc-flow-lbl">Intelligent Retries</span>
        <span class="rc-flow-sub">ML-powered timing</span>
      </div>
      <span class="rc-flow-arrow">→</span>
      <div class="rc-flow-node hl">
        <span class="rc-flow-icon">📧</span>
        <span class="rc-flow-lbl">Dunning Emails</span>
        <span class="rc-flow-sub">Customer outreach</span>
      </div>
      <span class="rc-flow-arrow">→</span>
      <div class="rc-flow-node">
        <span class="rc-flow-icon">✅</span>
        <span class="rc-flow-lbl">Recovery or Expiry</span>
        <span class="rc-flow-sub">Invoice resolved</span>
      </div>
    </div>

    <div class="rc-3col">
      <div class="rc-wi">
        <span class="rc-wi-icon">🤖</span>
        <h4>Intelligent Retries</h4>
        <p>Recurly's ML engine analyzes transaction data to determine the optimal moment to retry a declined payment. It runs fully automatically in the background — no setup required. Retries are independent from your email schedule.</p>
      </div>
      <div class="rc-wi">
        <span class="rc-wi-icon">📬</span>
        <h4>Dunning Emails</h4>
        <p>Automated email sequences sent to subscribers prompting them to update their billing info. You control the day, template, and tone of every email in the sequence. Emails are critical for hard declines that retries can't recover.</p>
      </div>
      <div class="rc-wi">
        <span class="rc-wi-icon">🪟</span>
        <h4>Dunning Window</h4>
        <p>The time period during which Recurly retries payments and sends emails. Window length determines how long you have to recover a payment before the subscription expires. Recurly recommends 27 days for monthly plans, 60 days for annual.</p>
      </div>
    </div>

    <div class="rc-tip">
      <p><strong>💡 Key distinction:</strong> Retries and emails are independent systems. An email being sent does NOT trigger a retry — they run on separate schedules. This gives you full flexibility to optimize payment recovery timing and subscriber communication cadence independently.</p>
    </div>

    <hr class="rc-divider" />

    <div class="rc-subhead">Who enters the dunning process?</div>
    <p>Any invoice that becomes <code>past_due</code> enters dunning. What happens next depends on the type of decline received from the payment gateway.</p>

    <table class="rc-table">
      <thead>
        <tr><th>Failure Type</th><th>Common Example</th><th>Retries?</th><th>Emails?</th></tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>Soft Decline</strong></td>
          <td>Insufficient funds, card limit reached</td>
          <td>✅ Yes &mdash; ML-optimized</td>
          <td>✅ Yes &mdash; per your schedule</td>
        </tr>
        <tr>
          <td><strong>Hard Decline</strong></td>
          <td>Invalid card number, fraud block</td>
          <td>❌ Typically no</td>
          <td>✅ Yes &mdash; send on Day 0</td>
        </tr>
        <tr>
          <td><strong>Any past_due Invoice</strong></td>
          <td>Any failed renewal payment</td>
          <td>If soft decline</td>
          <td>✅ Yes &mdash; per your campaign</td>
        </tr>
      </tbody>
    </table>

    <div class="rc-warning">
      <p><strong>⚠️ Hard declines require fast action.</strong> Since Recurly typically won't retry hard declines, email is your only automated recovery tool for these subscribers. Make sure your first dunning email fires immediately on Day 0 for hard decline events &mdash; not delayed to Day 3 like soft declines.</p>
    </div>

    <div class="rc-tip">
      <p><strong>🔗 Worried about giving away free access?</strong> You can decouple dunning status from login and entitlement status using Recurly Webhooks. This lets you maintain a long recovery window while restricting product access after a short grace period. See the Resources tab for the Dunning Webhooks guide.</p>
    </div>

  </div>

  <div class="rc-sec-nav">
    <span class="rc-page-label">&bull; Start of path</span>
    <span class="rc-page-label">Page 1 of 16</span>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-why-it-matters" class="rc-btn-next">Why It Matters &rarr;</a>
  </div>

</div>
`}</HTMLBlock>

<br />
