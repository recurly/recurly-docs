---
title: 'Payments Hub: Fraud prevention'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
.rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
*{box-sizing:border-box}body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
.rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px}
.rc-badge{display:inline-flex;align-items:center;gap:8px;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
.rc-badge img{width:16px;height:16px;display:block;object-fit:contain}
.rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
.rc-hero p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 0;color:var(--lightgray)}
.rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
.rc-nav a{display:inline-flex;align-items:center;gap:10px;padding:10px 18px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s}
.rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
.rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack);box-shadow:0 2px 10px rgba(255,215,6,.25)}
.rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
.rc-sec{margin-bottom:56px}
.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
.rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
.rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
.rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
.rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
.rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
.rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
.rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray)}
.rc-wi h4{font-size:.9rem;font-weight:700;margin:0 0 6px;color:var(--offblack)}
.rc-wi p{font-size:.82rem;color:var(--gray);line-height:1.5;margin:0}
.rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
.rc-tipicon{font-size:24px;flex-shrink:0}
.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
.rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start;margin-bottom:24px}
.rc-wicon{font-size:20px;flex-shrink:0}
.rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
.rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:28px}
.rc-cl-header{padding:16px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:center;gap:10px;background:var(--offblack)}
.rc-cl-header h3{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
.rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:flex-start;gap:14px}
.rc-cli:last-child{border-bottom:none}
.rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;background:#fff}
.rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}
.rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
.rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}
.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
.rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
.rc-office{background:var(--offblack);color:#fff;border-radius:16px;padding:28px 32px;margin:28px 0;border:1px solid var(--yellow)}
.rc-office h4{color:var(--yellow);margin:0 0 10px;font-size:1rem;font-weight:800;text-transform:uppercase;letter-spacing:1px}
.rc-office p{color:var(--lightgray);font-size:.92rem;line-height:1.6;margin:0 0 18px}
.rc-office a{background:var(--yellow);color:var(--offblack);text-decoration:none;padding:10px 22px;border-radius:10px;font-weight:700;font-size:.88rem;display:inline-flex;align-items:center;gap:8px}
@media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-2col{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">
      <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Scale">
      Scale
    </div>
    <h1>Fraud Prevention Dashboard</h1>
    <p>The Fraud Prevention dashboard gives Kount-enabled merchants a real-time view of blocked transactions and risk score trends — so you can spot and respond to fraud pressure early.</p>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub">Payments Hub</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview"><span class="rc-snum">1</span>Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing"><span class="rc-snum">2</span>Payment processing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater"><span class="rc-snum">3</span>Account updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries"><span class="rc-snum">4</span>Payment retries</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention"><span class="rc-snum">5</span>Fraud prevention</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources"><span class="rc-snum">6</span>Review &amp; resources</a>
  </nav>


  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🛡️</div>
      <div>
        <h2>Fraud prevention</h2>
        <p>For merchants using Kount, this dashboard consolidates your fraud blocking activity and risk score data into a single view — making it easy to monitor trends and act before fraud pressure escalates.</p>
      </div>
    </div>

    <img src="https://files.readme.io/44645be7caeb3412eb2d65f1627ede0c4115b23b8a52d57250bf66992fe46933-Fraud_Prevention_Dashboard.png" style="width:100%;border-radius:14px;border:1px solid var(--lightgray);margin-bottom:24px;" />

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Kount required:</strong> The Fraud Prevention dashboard only shows data if Kount is enabled on your Recurly site. If you see a blank dashboard or "Learn More" prompt, Kount is not yet active for your account. <a href="https://docs.recurly.com/recurly-subscriptions/docs/kount" target="_blank" style="color:var(--orange);font-weight:700;">Learn about Kount →</a></p>
    </div>

    <h3 class="rc-subhead">📋 What's on this dashboard</h3>
    <div class="rc-card">
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.75;margin:0;">
        <strong>Transactions blocked (fraud)</strong> — Total count of transactions Kount flagged and blocked in the period, with comparison to the previous period.<br><br>
        <strong>Blocked transactions over time</strong> — A line chart tracking daily blocked transaction count. Sudden spikes are an early signal of an active fraud attack.<br><br>
        <strong>Average risk score</strong> — The mean Kount risk score assigned to transactions in the period. Higher scores indicate higher risk. A rising average score often precedes an increase in blocked transactions — giving you a window to act proactively.<br><br>
        <strong>Average risk score over time</strong> — Tracks your daily average risk score. Use this as an early warning system — a trend upward here usually comes before a spike in blocks.<br><br>
        <strong>Fraud by payment method</strong> — A breakdown of blocked transactions by payment method. Helps you understand where fraud attempts are concentrating.<br><br>
        <strong>Blocked transactions by gateway</strong> — A bar chart showing fraud-blocked volume per gateway.
      </p>
    </div>

    <h3 class="rc-subhead">🔍 Understanding the risk score</h3>
    <div class="rc-card">
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 12px;">Kount assigns every transaction a risk score between 0 and 100. <strong>Higher scores indicate higher risk.</strong> A score near 100 means Kount has flagged the transaction as very likely fraudulent. Scores near 0 indicate low risk.</p>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0;">Your Kount rules determine the thresholds — a score above a certain level triggers a block, while scores in a middle range may require additional authentication. The exact thresholds depend on how your Kount rules are configured. Contact your Kount representative if you have questions about where your thresholds are set.</p>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Use the risk score trend as an early warning</h4><p>Don't wait for blocked transactions to spike before investigating. The Average Risk Score Over Time chart is your leading indicator. If you see the average score rising over several days — even if blocked transactions haven't spiked yet — it's worth reviewing your Kount rules and reaching out to your Kount representative.</p></div>
    </div>

    <h3 class="rc-subhead">✅ Activity: Explore Fraud Prevention</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Fraud prevention activity</h3></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="fp1"><label for="fp1" class="rc-clab">What is your current average risk score? Is it trending up, down, or stable over the period?<span>A rising trend is your early warning signal — act before blocked transactions spike</span></label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="fp2"><label for="fp2" class="rc-clab">Look at Fraud by Payment Method. Which payment method has the highest concentration of blocked transactions?<span>This tells you where fraud attempts are focusing — and may inform where to add friction or tighten rules</span></label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="fp3"><label for="fp3" class="rc-clab">Check Blocked Transactions by Gateway. Is fraud pressure concentrated on a specific gateway?<span>If one gateway shows significantly more blocks, it may indicate a routing or rule configuration worth reviewing</span></label></div>
    </div>

    <div class="rc-office">
      <h4>🗓️ Questions about Kount or fraud settings?</h4>
      <p>Join Global Office Hours to talk through your Fraud Prevention dashboard with a Recurly CSM. Whether you're new to Kount or looking to optimize your rules, we're here to help.</p>
      <a href="https://navigate.recurly.com/event-hub/">Register for office hours →</a>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-payments-hub-retries">← Payment retries</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources">📚 Review & resources</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/payments-hub-fraud-prevention" target="_blank">📖 Docs: Fraud prevention dashboard</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/kount" target="_blank">🔐 Docs: Kount integration</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/lunch-and-learn/new-payment-hub/" target="_blank">🎤 Register: May 7 Payments Hub walkthrough</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
  </div>
</div>
`}</HTMLBlock>

<br />
