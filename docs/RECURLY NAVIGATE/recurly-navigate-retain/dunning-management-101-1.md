---
title: Dunning - API TEST
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<HTMLBlock>{\`
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
    <span class="rc-flow-sub">Invoice becomes past_due</span>
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
  <p><strong>💡 Key distinction:</strong> Retries and emails are independent systems. An email being sent does NOT trigger a retry — they run on separate schedules. This gives you full flexibility to optimize payment recovery timing and communication cadence independently.</p>
</div>

<div class="rc-subhead">Who enters the dunning process?</div>
<p>Any invoice that becomes <code>past_due</code> enters dunning. What happens next depends on the type of decline received from the payment gateway.</p>

<table class="rc-table">
  <thead>
    <tr><th>Failure Type</th><th>Common Example</th><th>Retries?</th><th>Emails?</th></tr>
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
      <td><strong>Any Automatic Invoice</strong></td>
      <td>Any failed renewal payment</td>
      <td>If soft decline</td>
      <td>✅ Yes &mdash; per your campaign</td>
    </tr>
  </tbody>
</table>

<div class="rc-warning">
  <p><strong>⚠️ Hard declines require fast action.</strong> Since Recurly typically won't retry hard declines, email is your only automated recovery tool. Make sure your first dunning email fires immediately on Day 0 for hard decline events — not delayed to later in the cycle.</p>
</div>

<hr class="rc-divider" />

<div class="rc-subhead">Why dunning matters</div>

<p>Payment failures are a normal part of running a subscription business — industry-wide, 5–10% of subscription payments fail on first attempt. What separates high-performing businesses from struggling ones is what happens next.</p>

<div class="rc-2col">
  <div class="rc-dark-card">
    <h3>3&ndash;5% uplift is the norm</h3>
    <p>Recurly customers typically see a 3–5% uplift in dunning recovery rate after following the optimization tips found in this learning path.</p>
  </div>
  <div class="rc-dark-card">
    <h3>Passive churn is the hidden problem</h3>
    <p>Passive churn — losing subscribers due to failed payments rather than intent — can account for up to 40% of total churn. These are customers who want to stay subscribed.</p>
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
    <p>Extended the dunning window for annual plans to 60 days and added value-reinforcement emails.</p>
  </div>
  <div class="rc-result-card">
    <span class="rc-result-num">+8%</span>
    <span class="rc-result-tag">Email Frequency</span>
    <p>Modified window length and adjusted communication frequency — leaving more days between each message.</p>
  </div>
</div>

<div class="rc-dark-card">
  <h3>🎧 +279% recovery revenue in one month</h3>
  <p>My Music Workshop implemented dunning best practices from scratch and saw a 279% increase in dunning recovery revenue in their first month.</p>
</div>

<div class="rc-card" style="border:2px solid var(--yellow); margin-top:24px;">
  <h3 class="rc-subhead" style="margin-top:0;">🎧 Ready for a deeper conversation?</h3>
  <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Join our live <strong>Customer Success Global Office Hours</strong> to walk through your specific setup and get personalized recommendations.</p>
  <a class="rc-btn-next" href="[https://navigate.recurly.com/global-office-hours/](https://navigate.recurly.com/global-office-hours/)" target="_blank">Sign up here &rarr;</a>
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
\`}</HTMLBlock>
`}</HTMLBlock>

<br />
