---
title: 'Payments Hub: Payment retry recovery dashboard'
excerpt: >-
  Track how much initially failed revenue is successfully captured through
  Recurly’s intelligent retry logic. Analyze your recovery rate and
  success-by-attempt distribution to determine if your dunning timeline is
  effectively salvaging revenue at risk.
deprecated: false
hidden: false
metadata:
  keywords:
    - Payment retry recovery
    - revenue at risk
    - dunning recovery rate
    - intelligent retry logic
    - success by attempt
    - failed payment collection.
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
    <h1>Payment Retry Recovery Dashboard</h1>
    <p>The Payment Retry Recovery dashboard shows how much initially failed revenue was recovered on subsequent payment attempts — and at which attempt it was captured.</p>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub">Payments Hub</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview"><span class="rc-snum">1</span>Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing"><span class="rc-snum">2</span>Payment processing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater"><span class="rc-snum">3</span>Account updater</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries"><span class="rc-snum">4</span>Payment retry recovery</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention"><span class="rc-snum">5</span>Fraud prevention</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources"><span class="rc-snum">6</span>Review &amp; resources</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔁</div>
      <div>
        <h2>Payment retries</h2>
        <p>When a payment fails on the first attempt, Recurly's intelligent retry logic works to recover it. This dashboard shows you how much revenue that recovery effort is capturing — and the story behind each retry attempt.</p>
      </div>
    </div>

   <img src="https://files.readme.io/dd846483711337200d1b60b8f6e3d4cfc3b778110e986a4b7380e492093a5dc3-Payment_Retry_Recovery.png" style="width:100%;border-radius:14px;border:1px solid var(--lightgray);margin-bottom:24px;" />

    <h3 class="rc-subhead">📋 What's on this dashboard</h3>
    <div class="rc-card">
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.75;margin:0;">
        <strong>Recovered transactions</strong> — Total count of payments successfully recovered through retries in the period.<br><br>
        <strong>Payment recovery over time</strong> — A trend line showing recovered transaction volume by day.<br><br>
        <strong>Retry attempts</strong> — Total number of retry attempts made in the period (a single transaction may be retried multiple times).<br><br>
        <strong>Revenue at risk</strong> — The total value of invoices attached to a dunning campaign whose first payment attempt failed. This is the pool of revenue eligible for recovery on subsequent attempts.<br><br>
        <strong>Payment retry recovered revenue</strong> — The dollar value successfully collected on the second or later payment attempt.<br><br>
        <strong>Recovery rate</strong> — The percentage of revenue at risk that was successfully recovered.<br><br>
        <strong>Success by retry attempt number</strong> — A chart showing which retry attempt (1st, 2nd, 3rd...) actually captured the payment. Most payments are recovered within the first several attempts.
      </p>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <div>
        <h4>Important: retries vs. dunning</h4>
        <p>This dashboard counts <strong>all successful payments on attempt 2+ as recovered</strong>, regardless of mechanism. The main Analytics dunning dashboards break recovery into named buckets (retry, Account Updater, backup payment, customer card updates, etc.) and may apply different filters. For example, some exclude manual dunning campaigns or include first-attempt successes in their totals. The numbers will not always match.<br><br> <strong>This dashboard is the simplest view of 'how much failed revenue did we eventually collect.</strong></p>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>What the retry attempt chart tells you</h4><p>The "Success by Retry Attempt Number" chart is one of the most useful views in Payments Hub. It shows the distribution of which retry number is capturing the payment. For most merchants, the bulk of recoveries happen within the first 10 attempts, which validates that your dunning timeline is appropriate, and that recovery is working as expected.</p></div>
    </div>

    <h3 class="rc-subhead">✅ Activity: Explore Payment Retry Recovery</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Payment retries activity</h3></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="rt1"><label for="rt1" class="rc-clab">What is your current recovery rate?<span><strong>Remember</strong>: this number may differ from the recovery figure in your main Analytics dunning dashboards because they apply different definitions of recovered revenue.</span></label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="rt2"><label for="rt2" class="rc-clab">Compare your recovered revenue to your revenue at risk. What percentage is being saved?<span>Revenue at risk = all initial payment failures. Recovered revenue = what retries captured from that pool.</span></label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="rt3"><label for="rt3" class="rc-clab">Look at the Success by Retry Attempt chart. At which attempt number do most of your recoveries happen?<span>If most payments are capturing very late (attempt 15+), your dunning timeline may benefit from adjustment</span></label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="rt4"><label for="rt4" class="rc-clab">Open your main Analytics dunning dashboard and note the overall recovery number. How does it compare to the number here?<span>The two won't always match. The Analytics dashboards apply different definitions of recovered revenue, including some that count first-attempt successes.</span></label></div>
    </div>

    <div class="rc-office">
      <h4>🗓️ Want to optimize your retry strategy?</h4>
      <p>Join Global Office Hours to talk through your retry recovery data with a CSM. We can help you understand what your numbers mean in context and identify opportunities to improve.</p>
      <a href="https://navigate.recurly.com/event-hub/"target="_blank">Register for office hours →</a>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater">← Account Updater</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention">Next: Fraud prevention →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/payments-hub-payment-retry-recovery" target="_blank">📖 Docs: Payment retry recovery</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/retry-logic" target="_blank">🔁 Docs: Intelligent retries</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/" target="_blank">🌐 Join Global Office Hours</a>
  </div>
</div>
`}</HTMLBlock>

<br />