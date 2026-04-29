---
title: 'Payments Hub: Overview dashboard'
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
    <h1>Overview Dashboard</h1>
    <p>The Overview dashboard is your starting point — a high-level summary of your payment health, with filters to drill into exactly what you need.</p>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub">Payments Hub</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview"><span class="rc-snum">1</span>Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing"><span class="rc-snum">2</span>Payment processing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater"><span class="rc-snum">3</span>Account updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries"><span class="rc-snum">4</span>Payment retry recovery</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention"><span class="rc-snum">5</span>Fraud prevention</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources"><span class="rc-snum">6</span>Review &amp; resources</a>
  </nav>

  <div class="rc-sec">

    <div class="rc-sec-header">
      <div class="rc-sec-icon">🏠</div>
      <div>
        <h2>Overview dashboard</h2>
        <p>Your top-level payment health summary. This is the first thing you see when you open Payments Hub — a single view of how your payments are performing across all gateways and methods.</p>
      </div>
    </div>

    <!-- Replace [OVERVIEW_SCREENSHOT_URL] with your hosted screenshot -->
    <img src="https://files.readme.io/8f305076d6acfa324bd422edaf949a4a4d60d596edb29ebd0d336e8179640407-Overview_Dashboard.png" style="width:100%;border-radius:14px;border:1px solid var(--lightgray);margin-bottom:24px;" />

    <h3 class="rc-subhead">📋 What's on this dashboard</h3>
    <div class="rc-card">
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.75;margin:0;">
        <strong>Global payment volume distribution</strong> — A heat map showing where your payments are coming from by billing country. Darker shades = higher volume.<br><br>
        <strong>Payment method distribution</strong> — A pie chart showing the share of transactions by payment method type (credit card, PayPal, Apple Pay, etc.).<br><br>
        <strong>Overall success rate</strong> — Your blended payment success rate across all methods and gateways, with a comparison to the previous time period.<br><br>
        <strong>CIT success rate</strong> — Customer Initiated Transactions: payments where the customer is actively in session (sign-ups, checkout clicks, dunning re-entries).<br><br>
        <strong>MIT success rate</strong> — Merchant Initiated Transactions: automatic recurring renewals and scheduled payments.<br><br>
        <strong>Account Updater tile</strong> — Revenue authorized on automatically updated cards in the period. Data visible to Account Updater enabled merchants only. See tip below for details.<br><br>
        <strong>Payment Retry Recovery tile</strong> — Revenue recovered through intelligent retries in the period.<br><br>
        <strong>Fraud blocking tile</strong> — Count of transactions blocked by Kount. Data visible to Kount-enabled merchants only. See tip below for details.<br><br><br>
      </p>
    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>No data on Account Updater or Fraud tiles?</h4><p>If you don't have Account Updater or Kount enabled, those tiles will display a "Learn More" prompt instead of data. This is expected — the dashboard is aware of which features you have active.<br><br>
        🔰 Learn more about <strong>Kount fraud prevention <a href="https://docs.recurly.com/recurly-subscriptions/docs/kount" target="_blank" rel="noopener noreferrer">here</a></strong>.<br>
				<strong>🔄 Account Updater not enabled yet?</strong> Learn what it means and how to make it work for you <strong><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" target="_blank" rel="noopener noreferrer">here</a></strong>.
</p></div>
      </div></div>

 

    <h3 class="rc-subhead">🔍 CIT vs. MIT — what's the difference?</h3>
    <div class="rc-2col">
      <div class="rc-wi">
        <h4>CIT — Customer Initiated</h4>
        <p>The customer is present. Includes sign-up transactions, checkout pages, and dunning click-throughs where a customer re-enters their card. These typically have higher success rates because the customer is actively engaged.</p>
      </div>
      <div class="rc-wi">
        <h4>MIT — Merchant Initiated</h4>
        <p>Automatic payments. Includes all scheduled subscription renewals and recurring charges that happen without the customer in session — which is why tools like Account Updater and intelligent retries matter most here.</p>
      </div>
    </div>

    <h3 class="rc-subhead">🎛️ Using the filters</h3>
    <div class="rc-card">
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">All filters sit at the top of the dashboard and apply to the entire page. Every chart, table, and metric updates when you apply one. You can also click directly on the map or pie chart to filter by that selection.</p>
      <p style="font-size:.88rem;color:var(--darkgray);line-height:1.8;margin:0;">
        <strong>Date range</strong> — Defaults to the last 30 days. Adjust to any custom range.<br>
        <strong>Country</strong> — Filter by billing country on the transaction.<br>
        <strong>Gateway</strong> — Isolate data for one or more connected gateways.<br>
        <strong>Payment method</strong> — Focus on a specific payment type (e.g., Apple Pay, PayPal).<br>
        <strong>Initiated by</strong> — Filter to CIT only or MIT only.<br>
        <strong>Currency</strong> — Filter to a specific currency.
      </p>
    </div>

    <h3 class="rc-subhead">✅ Activity: Explore the Overview</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Overview activity</h3></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="ov1"><label for="ov1" class="rc-clab">What is your overall payment success rate? Is it trending up or down compared to the previous period?<span>Look for the red or green delta below the success rate tile</span></label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="ov2"><label for="ov2" class="rc-clab">Try filtering by country. Does your success rate change significantly for any region?<span>Click directly on the map to filter — click again to deselect</span></label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="ov3"><label for="ov3" class="rc-clab">Look at the payment method distribution. Is the split what you expected?<span>Are there payment methods with a higher share than you realized?</span></label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="ov4"><label for="ov4" class="rc-clab">Compare your CIT and MIT success rates. Which is higher, and by how much?<span>A large gap between the two may be worth exploring in the Payment Processing dashboard</span></label></div>
    </div>

    <div class="rc-office">
      <h4>🗓️ Want to talk through your numbers?</h4>
      <p>Join Global Office Hours to walk through your Overview dashboard with a Recurly Customer Success Manager. We can help you understand what your metrics mean and what to prioritize.</p>
      <a href="https://navigate.recurly.com/event-hub/">Register for office hours →</a>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub">← Payments Hub</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing">Next: Payment processing →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/payments-hub-overview" target="_blank">📖 Docs: Overview dashboard</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com"target="_blank">🎧 Contact Recurly Support</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/"target="_blank">🌐 Join Global Office Hours</a>
  </div>
</div>
`}</HTMLBlock>

<br />
