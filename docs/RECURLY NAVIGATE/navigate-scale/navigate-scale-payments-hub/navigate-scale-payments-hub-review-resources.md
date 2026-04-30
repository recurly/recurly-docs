---
title: 'Payments Hub: Review & resources'
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
.rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
.rc-tipicon{font-size:24px;flex-shrink:0}
.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
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

/* Complete banner */
.rc-complete{background:var(--offblack);border:2px solid var(--yellow);border-radius:16px;padding:36px 32px;text-align:center;margin-bottom:36px}
.rc-complete h2{font-size:1.5rem;font-weight:800;color:var(--offwhite);margin:12px 0 10px}
.rc-complete p{color:var(--lightgray);font-size:.95rem;line-height:1.6;max-width:600px;margin:0 auto 20px}
.rc-complete a{display:inline-flex;align-items:center;gap:8px;background:var(--yellow);color:var(--offblack);text-decoration:none;padding:12px 24px;border-radius:10px;font-weight:700;font-size:.9rem;margin:4px}
.rc-complete a.rc-sec-btn{background:transparent;border:1px solid var(--lightgray);color:var(--lightgray)}

/* Dashboard summary cards */
.rc-dash-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:28px}
.rc-dash-card{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray)}
.rc-dash-card-head{display:flex;align-items:center;gap:10px;margin-bottom:10px}
.rc-dash-card-icon{font-size:22px;flex-shrink:0}
.rc-dash-card h4{font-size:.92rem;font-weight:700;color:var(--offblack);margin:0}
.rc-dash-card p{font-size:.82rem;color:var(--gray);line-height:1.55;margin:0}
.rc-dash-card strong{color:var(--darkgray)}

/* Key metrics callout row */
.rc-metrics{display:grid;grid-template-columns:1fr 1fr 1fr;gap:12px;margin-bottom:28px}
.rc-metric{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:14px;padding:18px;text-align:center}
.rc-metric-icon{font-size:26px;margin-bottom:8px}
.rc-metric h5{font-size:.82rem;font-weight:700;color:var(--offblack);margin:0 0 4px;text-transform:uppercase;letter-spacing:.5px}
.rc-metric p{font-size:.78rem;color:var(--gray);line-height:1.45;margin:0}

@media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-dash-grid,.rc-metrics{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">
      &#10022;
      Scale
    </div>
    <h1>Payments Hub Review & Resources</h1>
    <p>You've made it through all five dashboards. Here's a quick recap of what you've covered, the key metrics to keep watching, and everything you need to go deeper.</p>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub">Payments Hub</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview"><span class="rc-snum">1</span>Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing"><span class="rc-snum">2</span>Payment processing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater"><span class="rc-snum">3</span>Account updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries"><span class="rc-snum">4</span>Payment retry recovery</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention"><span class="rc-snum">5</span>Fraud prevention</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources"><span class="rc-snum">6</span>Review &amp; resources</a>
  </nav>

  <div class="rc-sec">

    <!-- Completion banner -->
    <div class="rc-complete">
      <div style="font-size:48px;">🎉</div>
      <h2>You've explored all 5 Payments Hub dashboards!</h2>
      <p>You now know what each dashboard shows, what to look for, and how to take action. Ready to go deeper? Watch the on-demand Payments Hub walkthrough or bring your questions to a live Global Office Hours session.</p>
      <a href="https://navigate.recurly.com/lunch-and-learn/new-payment-hub/" target="_blank">▶ Watch: Payments Hub Walkthrough</a>
      <a class="rc-sec-btn" href="https://navigate.recurly.com/event-hub/" target="_blank">🗓️ Need help now? Join Office Hours</a>
    </div>

    <!-- Dashboard recap -->
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🗺️</div>
      <div>
        <h2>What you've covered</h2>
        <p>A quick summary of each dashboard and its primary purpose — use this as a reference when you return to Payments Hub.</p>
      </div>
    </div>

    <div class="rc-dash-grid">
      <div class="rc-dash-card">
        <div class="rc-dash-card-head">
          <span class="rc-dash-card-icon">🏠</span>
          <h4>Overview</h4>
        </div>
        <p>Your top-level payment health snapshot. Shows <strong>overall, CIT, and MIT success rates</strong>, payment method distribution, geographic volume, and summary tiles for Account Updater, Retry Recovery, and Fraud blocking.</p>
      </div>
      <div class="rc-dash-card">
        <div class="rc-dash-card-head">
          <span class="rc-dash-card-icon">💳</span>
          <h4>Payment Processing</h4>
        </div>
        <p>The most actionable dashboard. Shows <strong>success rates by gateway, payment method, and card BIN</strong> — plus a ranked table of your top decline reasons, categorized as hard or soft.</p>
      </div>
      <div class="rc-dash-card">
        <div class="rc-dash-card-head">
          <span class="rc-dash-card-icon">🔄</span>
          <h4>Account Updater</h4>
        </div>
        <p>Tracks <strong>revenue protected through automatic card updates</strong> before payments fail. Shows update counts, revenue authorized on updated cards, update type breakdown, and activity by card network.</p>
      </div>
      <div class="rc-dash-card">
        <div class="rc-dash-card-head">
          <span class="rc-dash-card-icon">🔁</span>
          <h4>Payment Retry Recovery</h4>
        </div>
        <p>Shows how much <strong>initially failed revenue was recovered through intelligent retries</strong> — including total recovered, recovery rate, revenue at risk, and which retry attempt captured the payment.</p>
      </div>
    </div>

    <div class="rc-dash-grid" style="grid-template-columns:1fr;">
      <div class="rc-dash-card">
        <div class="rc-dash-card-head">
          <span class="rc-dash-card-icon">🛡️</span>
          <h4>Fraud Prevention <span style="font-size:.78rem;font-weight:400;color:var(--gray);margin-left:6px;">Kount-enabled merchants only</span></h4>
        </div>
        <p>Consolidates your fraud blocking activity into one view. Shows <strong>blocked transactions, average risk score trends, fraud by payment method, and blocked volume by gateway</strong>. The risk score trend is your early warning system — a rising average often precedes a spike in blocks.</p>
      </div>
    </div>

    <!-- Key metrics to watch -->
    <div class="rc-sec-header" style="margin-top:16px;">
      <div class="rc-sec-icon">📊</div>
      <div>
        <h2>Metrics to watch regularly</h2>
        <p>These are the numbers worth checking on a recurring basis — whether that's weekly, monthly, or when something looks off.</p>
      </div>
    </div>

    <div class="rc-metrics">
      <div class="rc-metric">
        <div class="rc-metric-icon">📈</div>
        <h5>Payment success rate</h5>
        <p>Your blended rate across all gateways and methods. Watch the trend over time — a downward drift often signals something worth investigating in Payment Processing.</p>
      </div>
      <div class="rc-metric">
        <div class="rc-metric-icon">🔁</div>
        <h5>Retry recovery rate</h5>
        <p>What percentage of initially failed revenue is being recovered through intelligent retries. Compare this to your overall dunning recovery for a complete picture.</p>
      </div>
      <div class="rc-metric">
        <div class="rc-metric-icon">🔄</div>
        <h5>Revenue protected (AU)</h5>
        <p>The dollar value authorized on automatically updated cards. This is revenue that would likely have failed without Account Updater running.</p>
      </div>
      <div class="rc-metric">
        <div class="rc-metric-icon">⚠️</div>
        <h5>Top decline reason</h5>
        <p>Your single most common reason for failed payments. Know whether it's a hard or soft decline — the response strategy is very different.</p>
      </div>
      <div class="rc-metric">
        <div class="rc-metric-icon">🛡️</div>
        <h5>Average risk score</h5>
        <p>For Kount users: monitor this as a leading indicator. A rising trend often precedes a spike in blocked transactions — act early.</p>
      </div>
      <div class="rc-metric">
        <div class="rc-metric-icon">🌍</div>
        <h5>Success rate by region</h5>
        <p>Filter the Overview by country to check for geographic drop-offs. Regional differences in success rates may point to gateway routing or payment method gaps.</p>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Keep in mind</h4><p>Payments Hub data begins from Q1 2026. Numbers in these dashboards reflect payment-level data — more granular than your standard Recurly billing analytics. Some figures may differ slightly from other dashboards in your account; both are accurate, measuring different things.</p></div>
    </div>

    <!-- CTA: Office Hours + Walkthrough -->
    <div class="rc-office">
      <h4>🗓️ Go deeper with a CSM</h4>
      <p>Global Office Hours are the best place to walk through your own data with a Recurly Customer Success Manager. Bring your numbers, ask your questions, and leave with a clear next step. Sessions are free, open to all customers, and run regularly.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank">Register for Office Hours →</a>
    </div>

    <!-- Resources -->
    <h3 class="rc-subhead">📚 Resources & documentation</h3>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/lunch-and-learn/new-payment-hub/" target="_blank">▶ Payments Hub Walkthrough (on-demand)</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/" target="_blank">🌐 Join Global Office Hours</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/payments-hub" target="_blank">📖 Recurly Docs: Payments Hub</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/api-transaction-errors" target="_blank">📝 Decline messages reference</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/retry-logic" target="_blank">🔁 Intelligent retries documentation</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" target="_blank">🔄 Account Updater learning</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/kount" target="_blank">🔐 Kount fraud prevention docs</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/user-roles-and-permissions" target="_blank">👤 User roles & permissions</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention">← Fraud prevention</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub">↩ Back to Payments Hub start</a>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
