---
title: Dunningn 101
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<HTMLBlock>
<style>
.rc-guide{max-width:900px;margin:20px auto;font-family:"Inter",-apple-system,sans-serif;color:#0D0D0B;line-height:1.6;background-color:#ffffff;border-radius:16px;overflow:hidden;box-shadow:0 4px 24px rgba(0,0,0,0.08)}
.rc-hero{background-color:#0D0D0B;color:#FFFFFF;padding:56px 40px 48px;text-align:center}
.rc-badge{display:inline-block;background-color:#FFD706;color:#0D0D0B;border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;text-transform:uppercase;margin-bottom:20px;letter-spacing:.5px}
.rc-hero h1{font-size:32px;margin:0 0 12px;font-weight:700}
.rc-hero p{color:#CCC9B8;font-size:1.05rem;margin:0 auto;max-width:600px}
.rc-hero-stats{display:flex;justify-content:center;gap:48px;flex-wrap:wrap;margin-top:32px}
.rc-stat-num{font-size:28px;font-weight:800;color:#FFD706;display:block}
.rc-stat-lbl{font-size:11px;font-weight:600;color:#807D73;text-transform:uppercase;letter-spacing:.5px}
.rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:32px 0 40px;padding:0 40px}
.rc-nav a{display:inline-flex;align-items:center;gap:8px;padding:10px 16px;border-radius:12px;border:1px solid #CCC9B8;background-color:#FFFFFF;color:#32312D;text-decoration:none;font-size:.85rem;font-weight:700}
.rc-nav a:hover{border-color:#FFD706;color:#0D0D0B}
.rc-nav a.rc-active{border-color:#FFD706;background-color:#FFD706;color:#0D0D0B}
.rc-snum{display:inline-flex;align-items:center;justify-content:center;width:22px;height:22px;border-radius:50%;background-color:#0D0D0B;color:#FFD706;font-size:11px;font-weight:700}
.rc-nav a.rc-active .rc-snum{background-color:#0D0D0B;color:#FFD706}
.rc-body{padding:0 40px 40px}
.rc-body p{font-size:.92rem;color:#32312D;line-height:1.7;margin:0 0 14px}
.rc-body ul{padding-left:20px;margin:0 0 16px;color:#32312D;font-size:.92rem;line-height:1.8}
.rc-body ul li{margin-bottom:4px}
.rc-sec-header{display:flex;gap:20px;align-items:flex-start;margin-bottom:28px}
.rc-sec-icon{width:52px;height:52px;background-color:#FFD706;border-radius:14px;display:flex;align-items:center;justify-content:center;flex-shrink:0;font-size:26px}
.rc-sec-header h2{font-size:22px;font-weight:700;margin:0 0 6px}
.rc-sec-header p{margin:0;color:#807D73;font-size:.95rem}
.rc-subhead{font-size:18px;font-weight:700;margin:36px 0 14px;color:#0D0D0B}
.rc-subhead-sm{font-size:15px;font-weight:700;margin:24px 0 10px;color:#0D0D0B}
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
.rc-dark-card{background-color:#0D0D0B;border-radius:14px;padding:24px 28px;margin-bottom:14px}
.rc-dark-card h3{font-size:16px;font-weight:700;color:#FFD706;margin:0 0 8px}
.rc-dark-card p{font-size:13.5px;color:#CCC9B8;margin:0;line-height:1.65}
.rc-dark-card a{color:#FFD706;font-weight:700}
.rc-tip{border-left:4px solid #FFD706;background-color:#FFFDF2;padding:20px 24px;border-radius:0 12px 12px 0;margin:20px 0}
.rc-tip p{margin:0;font-size:.92rem;color:#32312D;line-height:1.65}
.rc-warning{border-left:4px solid #FF8200;background-color:#FFF8F0;padding:20px 24px;border-radius:0 12px 12px 0;margin:20px 0}
.rc-warning p{margin:0;font-size:.92rem;color:#32312D;line-height:1.65}
.rc-table{width:100%;border-collapse:collapse;font-size:13.5px;margin-bottom:20px;border-radius:10px;overflow:hidden;border:1px solid #CCC9B8}
.rc-table thead{background-color:#0D0D0B;color:#FFFDF2}
.rc-table thead th{padding:12px 16px;text-align:left;font-size:12px;font-weight:700;letter-spacing:.5px;text-transform:uppercase}
.rc-table tbody tr:nth-child(even){background-color:#F1EFE3}
.rc-table tbody tr:nth-child(odd){background-color:#FFFDF2}
.rc-table tbody td{padding:12px 16px;color:#32312D;border-bottom:1px solid #CCC9B8;vertical-align:top}
.rc-table tbody td strong{color:#0D0D0B}
.rc-results-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-bottom:24px}
.rc-result-card{background-color:#FFFDF2;border:1px solid #CCC9B8;border-radius:12px;padding:20px}
.rc-result-num{font-size:28px;font-weight:800;color:#0D0D0B;display:block;margin-bottom:6px}
.rc-result-tag{display:inline-block;background-color:#FFD706;color:#0D0D0B;font-size:11px;font-weight:700;padding:3px 10px;border-radius:20px;margin-bottom:10px}
.rc-result-card p{font-size:12.5px;color:#32312D;margin:0;line-height:1.6}
.rc-divider{border:none;border-top:1px solid #F1EFE3;margin:32px 0}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;margin-top:48px;padding:24px 40px;border-top:1px solid #CCC9B8;background-color:#FFFFFF}
.rc-btn-next{background-color:#FFD706;color:#0D0D0B;padding:12px 28px;border-radius:10px;font-weight:700;text-decoration:none;font-size:.9rem}
.rc-btn-prev{background-color:#FFFFFF;color:#32312D;padding:12px 28px;border-radius:10px;font-weight:700;text-decoration:none;font-size:.9rem;border:1px solid #CCC9B8}
.rc-page-label{color:#807D73;font-weight:600;font-size:.88rem}
@media(max-width:640px){.rc-hero{padding:36px 20px 32px}.rc-hero h1{font-size:24px}.rc-hero-stats{gap:24px}.rc-nav{padding:0 20px}.rc-body{padding:0 20px 28px}.rc-3col{flex-direction:column}.rc-2col{grid-template-columns:1fr}.rc-results-grid{grid-template-columns:1fr}.rc-sec-nav{padding:20px;flex-direction:column;gap:12px;align-items:stretch;text-align:center}.rc-flow{flex-direction:column}}
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">Recurly Navigate &middot; Dunning 101</div>
    <h1>Dunning 101</h1>
    <p>Recover more revenue, reduce passive churn, and build a dunning strategy that works quietly in the background.</p>
    <div class="rc-hero-stats">
      <div><span class="rc-stat-num">3&ndash;5%</span><span class="rc-stat-lbl">Avg Recovery Uplift</span></div>
      <div><span class="rc-stat-num">35%</span><span class="rc-stat-lbl">Median Recovery Rate</span></div>
      <div><span class="rc-stat-num">Up to 40%</span><span class="rc-stat-lbl">Of Churn Is Passive</span></div>
    </div>
  </div>
  <nav class="rc-nav">
    <a href="[https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101](https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101)" class="rc-active"><span class="rc-snum">1</span> Basics</a>
    <a href="[https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-configuration](https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-configuration)"><span class="rc-snum">2</span> Setup</a>
    <a href="[https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-email-strategy](https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-email-strategy)"><span class="rc-snum">3</span> Email Strategy</a>
    <a href="[https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-subscriber-engagement](https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-subscriber-engagement)"><span class="rc-snum">4</span> Engagement</a>
    <a href="[https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-advanced-configuration](https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-advanced-configuration)"><span class="rc-snum">5</span> Advanced</a>
    <a href="[https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-metrics](https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-metrics)"><span class="rc-snum">6</span> Metrics</a>
    <a href="[https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-strategy-resources](https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-strategy-resources)"><span class="rc-snum">✓</span> Resources</a>
  </nav>

  <div class="rc-body">

    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔄</div>
      <div>
        <h2>Dunning Basics</h2>
        <p>What dunning is, how it works, why it matters, and where it fits in your revenue recovery toolkit.</p>
      </div>
    </div>

    <p>Dunning is Recurly's automated system for recovering failed subscription payments. When a renewal charge doesn't go through, dunning kicks in — retrying the payment at the optimal time and reaching out to the subscriber so they can update their billing information before their subscription expires.</p>

    <div class="rc-flow">
      <div class="rc-flow-node">
        <span class="rc-flow-icon">💳</span>
        <span class="rc-flow-lbl">Payment Fails</span>
        <span class="rc-flow-sub">Invoice past_due</span>
      </div>
      <span class="rc-flow-arrow">&rarr;</span>
      <div class="rc-flow-node hl">
        <span class="rc-flow-icon">🤖</span>
        <span class="rc-flow-lbl">Retention Agent</span>
        <span class="rc-flow-sub">AI Intelligent Retries</span>
      </div>
      <span class="rc-flow-arrow">&rarr;</span>
      <div class="rc-flow-node hl">
        <span class="rc-flow-icon">📧</span>
        <span class="rc-flow-lbl">Dunning Emails</span>
        <span class="rc-flow-sub">Customer outreach</span>
      </div>
      <span class="rc-flow-arrow">&rarr;</span>
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
        <p>Powered by the Recurly Retention Agent, this ML engine analyzes transaction data to determine the optimal moment to retry a payment. It runs fully automatically within your dunning window.</p>
      </div>
      <div class="rc-wi">
        <span class="rc-wi-icon">📬</span>
        <h4>Dunning Emails</h4>
        <p>Automated email sequences sent to subscribers prompting them to update billing info. You control the day, template, and tone of every email in the sequence.</p>
      </div>
      <div class="rc-wi">
        <span class="rc-wi-icon">🪟</span>
        <h4>Dunning Window</h4>
        <p>The time period during which Recurly retries payments. Per 2026 best practices, Recurly recommends 28 days for monthly plans and 60 days for annual plans.</p>
      </div>
    </div>

    <div class="rc-tip">
      <p><strong>💡 Key distinction:</strong> Retries and emails are independent systems. An email being sent does NOT trigger a retry — they run on separate schedules to give you full flexibility in optimization.</p>
    </div>

    <div class="rc-subhead">Who enters the dunning process?</div>
    <p>Any invoice that becomes <code>past_due</code> enters dunning. What happens next depends on the decline type received from the gateway.</p>

    <table class="rc-table">
      <thead>
        <tr><th>Failure Type</th><th>Example</th><th>Retries?</th><th>Emails?</th></tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>Soft Decline</strong></td>
          <td>Insufficient funds, card limit</td>
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
          <td><strong>Auto Invoice</strong></td>
          <td>Any failed renewal payment</td>
          <td>If soft decline</td>
          <td>✅ Yes &mdash; per your campaign</td>
        </tr>
      </tbody>
    </table>

    <div class="rc-warning">
      <p><strong>⚠️ Hard declines require fast action.</strong> Since Recurly typically won't retry hard declines, email is your only automated tool. Ensure your first dunning email fires immediately on Day 0 for hard declines.</p>
    </div>

    <hr class="rc-divider" />

    <div class="rc-subhead">Why dunning matters</div>

    <p>Payment failures are a normal part of running a subscription business — industry-wide, 5–10% of subscription payments fail on first attempt. What separates high-performing businesses is what happens next.</p>

    <div class="rc-2col">
      <div class="rc-dark-card">
        <h3>3&ndash;5% uplift is the norm</h3>
        <p>Recurly customers typically see a 3–5% uplift in dunning recovery rate after following the 10 optimization tips — from changes that take a few hours to implement.</p>
      </div>
      <div class="rc-dark-card">
        <h3>Passive churn is the hidden problem</h3>
        <p>Passive churn — losing subscribers due to failed payments rather than intent — can account for up to 40% of total churn.</p>
      </div>
    </div>

    <div class="rc-subhead">Real customer results</div>

    <div class="rc-results-grid">
      <div class="rc-result-card">
        <span class="rc-result-num">+12%</span>
        <span class="rc-result-tag">Branding &amp; Window</span>
        <p>Enhanced email branding, updated dunning window length, and optimized communication frequency.</p>
      </div>
      <div class="rc-result-card">
        <span class="rc-result-num">+11%</span>
        <span class="rc-result-tag">Window Extension</span>
        <p>Extended the dunning window to 60 days (annual) and added value-driven messaging.</p>
      </div>
      <div class="rc-result-card">
        <span class="rc-result-num">+8%</span>
        <span class="rc-result-tag">Email Frequency</span>
        <p>Modified window length and adjusted communication frequency — leaving more days between each message.</p>
      </div>
    </div>

    <div class="rc-dark-card">
      <h3>+279% recovery revenue in one month</h3>
      <p>My Music Workshop implemented best practices from scratch and saw a 279% increase in dunning recovery revenue in their first month.</p>
    </div>

    <div class="rc-card" style="border: 2px solid #FFD706; margin-top: 24px; padding: 22px;">
      <h3 style="margin-top: 0; font-size: 16px;">🎧 Ready for a deeper conversation?</h3>
      <p style="font-size: 13.5px; line-height: 1.6; margin-bottom: 14px;">Join our live <strong>Customer Success Global Office Hours</strong> to walk through your specific setup and get personalized recommendations.</p>
      <a class="rc-btn-next" href="[https://navigate.recurly.com/global-office-hours/](https://navigate.recurly.com/global-office-hours/)" target="_blank" style="padding: 10px 20px; font-size: 0.85rem;">Sign up here &rarr;</a>
    </div>

    <hr class="rc-divider" />

    <div class="rc-subhead">Where dunning fits in your recovery toolkit</div>

    <table class="rc-table">
      <thead><tr><th>Tool</th><th>What It Does</th><th>Type</th></tr></thead>
      <tbody>
        <tr><td><strong>Account Updater</strong></td><td>Automatically updates expired or replaced card details before billing fails</td><td>Proactive</td></tr>
        <tr><td><strong>Expired Card Management</strong></td><td>Updates expired card info to prevent billing interruptions at renewal</td><td>Proactive</td></tr>
        <tr><td><strong>Retention Agent</strong></td><td>ML-optimized retry timing for declined payments — runs automatically within dunning</td><td>Reactive</td></tr>
        <tr><td><strong>Dunning Management</strong></td><td>Email sequences + 28-day window — the focus of this learning path</td><td>Reactive</td></tr>
        <tr><td><strong>Backup Payment Method</strong></td><td>Tries a secondary card on file if the primary payment method fails</td><td>Reactive</td></tr>
        <tr><td><strong>External Recovery</strong></td><td>Syncs successful recoveries from external systems back into Recurly</td><td>Reactive</td></tr>
      </tbody>
    </table>

  </div>

  <div class="rc-sec-nav">
    <span class="rc-page-label">&bull; Start of path</span>
    <span class="rc-page-label">Page 1 of 7</span>
    <a href="[https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-configuration](https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-configuration)" class="rc-btn-next">Setup &amp; Configuration &rarr;</a>
  </div>
</div>
</HTMLBlock>
`}</HTMLBlock>

<br />