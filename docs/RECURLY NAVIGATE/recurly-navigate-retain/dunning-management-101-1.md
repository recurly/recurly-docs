---
title: Dunning - API TEST
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<HTMLBlock>{\`
<style>
  .rc-guide{--yellow:#FFD706;--orange:#FF8200;--vermillion:#FF5810;--salmon:#FF9D88;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif;}
  *{box-sizing:border-box}
  .rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px}
  .rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
  .rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
  .rc-hero p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 32px;color:var(--lightgray)}
  .rc-hero-stats{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}
  .rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:8px;padding:10px 14px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s,background .2s,color .2s}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack);box-shadow:0 2px 10px rgba(255,215,6,.25)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-sec{margin-bottom:56px}
  .rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
  .rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-card,.rc-wi,.rc-checklist,.rc-tip,.rc-warning{margin-bottom:24px}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray)}
  .rc-subhead{font-size:1.1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray);text-align:center}
  .rc-wi-icon{font-size:30px;margin-bottom:10px}
  .rc-wi h4{font-size:.88rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
  .rc-wi p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start}
  .rc-tipicon{font-size:24px;flex-shrink:0}
  .rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
  .rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start}
  .rc-wicon{font-size:20px;flex-shrink:0}
  .rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev,.rc-btn-disabled{border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}
  .rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  .rc-table{width:100%;border-collapse:collapse;font-size:13px;margin:20px 0;border:1px solid var(--lightgray);border-radius:12px;overflow:hidden}
  .rc-table th{background:var(--offblack);color:#fff;padding:12px;text-align:left;text-transform:uppercase;font-size:11px;letter-spacing:.5px}
  .rc-table td{padding:12px;border-bottom:1px solid var(--lightgray);background:#fff}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
  @media (max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-3col{grid-template-columns:1fr}.rc-2col{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
</style>
<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">Revenue Recovery</div>
    <h1>Dunning 101</h1>
    <p>Recover more revenue, reduce passive churn, and build a dunning strategy that works quietly in the background.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">3-5%</div><div class="rc-lbl">Avg Recovery Uplift</div></div>
      <div><div class="rc-num">35%</div><div class="rc-lbl">Median Recovery Rate</div></div>
      <div><div class="rc-num">Up to 40%</div><div class="rc-lbl">Of Churn Is Passive</div></div>
    </div>
  </div>
  <nav class="rc-nav">
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101"><span class="rc-snum">1</span>Basics</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-configuration"><span class="rc-snum">2</span>Setup</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-email-strategy"><span class="rc-snum">3</span>Email Strategy</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-subscriber-engagement"><span class="rc-snum">4</span>Engagement</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-advanced-configuration"><span class="rc-snum">5</span>Advanced</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-metrics"><span class="rc-snum">6</span>Metrics</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-strategy-resources"><span class="rc-snum">v</span>Resources</a>
  </nav>
  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔄</div>
      <div>
        <h2>Dunning Basics</h2>
        <p>What dunning is, how it works, and why it is the foundation of your recovery toolkit.</p>
      </div>
    </div>
    <div class="rc-card">
      <h3 class="rc-subhead">The Simple Version</h3>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Dunning is Recurly's automated system for recovering failed subscription payments. When a renewal charge doesn't go through, dunning kicks in - retrying the payment at the optimal time and reaching out to the subscriber so they can update billing info before their subscription expires.</p>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0;">How it works: Dunning uses a combination of AI-driven retry logic (powered by the Retention Agent) and strategic email sequences. The goal is to maximize the chance of success without manual intervention.</p>
    </div>
    <div class="rc-3col">
      <div class="rc-wi"><div class="rc-wi-icon">🤖</div><h4>Retention Agent</h4><p>ML-powered engine that analyzes transaction data to determine the optimal moment to retry a payment.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">📬</div><h4>Dunning Emails</h4><p>Automated sequences prompting subscribers to update billing info. You control the timing and tone.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🪟</div><h4>Dunning Window</h4><p>The time period for recovery. Recurly recommends 28 days for monthly and 60 days for annual plans.</p></div>
    </div>
    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Key Distinction</h4><p>Retries and emails are independent systems. An email being sent does NOT trigger a retry - they run on separate schedules to give you full flexibility.</p></div>
    </div>
    <div class="rc-card">
      <h3 class="rc-subhead">Who enters dunning?</h3>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Any invoice that becomes past-due enters dunning. What happens depends on the decline type received.</p>
      <table class="rc-table">
        <thead>
          <tr><th>Failure Type</th><th>Example</th><th>Retries?</th><th>Emails?</th></tr>
        </thead>
        <tbody>
          <tr><td>Soft Decline</td><td>Insufficient funds</td><td>Yes - ML Optimized</td><td>Yes</td></tr>
          <tr><td>Hard Decline</td><td>Invalid card number</td><td>No</td><td>Yes (Day 0)</td></tr>
          <tr><td>Auto Invoice</td><td>Failed renewal</td><td>If soft decline</td><td>Yes</td></tr>
        </tbody>
      </table>
    </div>
    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p>Hard declines require fast action. Since Recurly typically won't retry hard declines, email is your only automated tool. Ensure your first email fires on Day 0.</p>
    </div>
    <h3 class="rc-subhead">Why Dunning Matters</h3>
    <div class="rc-2col">
      <div class="rc-card" style="background:var(--offblack);color:#fff;">
        <h4 style="color:var(--yellow);margin:0 0 8px 0;">3-5% Uplift</h4>
        <p style="color:var(--lightgray);font-size:0.85rem;margin:0;">Standard recovery uplift seen by merchants after following the 10 dunning best practices.</p>
      </div>
      <div class="rc-card" style="background:var(--offblack);color:#fff;">
        <h4 style="color:var(--yellow);margin:0 0 8px 0;">Passive Churn</h4>
        <p style="color:var(--lightgray);font-size:0.85rem;margin:0;">Involuntary churn can account for up to 40% of total churn. Dunning targets customers who want to stay.</p>
      </div>
    </div>
    <div class="rc-card" style="border:2px solid var(--yellow);">
      <h3 class="rc-subhead">Ready for a deeper conversation?</h3>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Join our live Customer Success Global Office Hours to walk through your specific setup and get recommendations.</p>
      <a class="rc-link-btn" href="https://navigate.recurly.com/global-office-hours/" target="_blank">Sign up here</a>
    </div>
    <div class="rc-sec-nav">
      <span class="rc-btn-disabled">Back</span>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-configuration">Next: Setup & Configuration</a>
    </div>
  </div>
</div>
\`}</HTMLBlock>
`}</HTMLBlock>

<br />
