---
title: 'Payments Hub: Getting started'
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
.rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
.rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray);text-align:center}
.rc-wi-icon{font-size:28px;margin-bottom:10px}
.rc-wi h4{font-size:.88rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
.rc-wi p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
.rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
.rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
.rc-sbadge{width:38px;height:38px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
.rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
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
.rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
.rc-btn-prev,.rc-btn-disabled{border:1px solid var(--lightgray)}
.rc-btn-prev{background:#fff;color:var(--darkgray)}
.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
.rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
.rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
@media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-3col{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">
      <img src="https://drive.google.com/uc?export=view&id=19iENz4PHZRl4F4tJHSVenTOhVbVfsZgS" alt="Scale">
      Scale
    </div>
    <h1>Payments Hub</h1>
    <p>Your payment performance data, all in one place. Learn your way around every dashboard — and know what to look for from day one.</p>
  </div>

  <nav class="rc-nav">
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub">Payments Hub</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview"><span class="rc-snum">1</span>Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing"><span class="rc-snum">2</span>Payment processing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater"><span class="rc-snum">3</span>Account updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries"><span class="rc-snum">4</span>Payment retries</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention"><span class="rc-snum">5</span>Fraud prevention</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources"><span class="rc-snum">6</span>Review &amp; resources</a>
  </nav>

  <div class="rc-sec">

    <div class="rc-sec-header">
      <div class="rc-sec-icon">📊</div>
      <div>
        <h2>What is Payments Hub?</h2>
        <p>A new payment analytics dashboard inside your Recurly account — giving you a complete view of your payment performance without ever leaving the platform.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🧩 The problem it solves</h3>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Before Payments Hub, understanding your payment performance meant logging into each gateway portal separately, manually reconciling the data, and hoping it all matched what Recurly was reporting. It was time-consuming, error-prone, and incomplete.</p>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0;">Payments Hub changes that. It pulls all of your payment data — across every connected gateway, payment method, and value-add service — into one place. One view to understand what's working, what isn't, and where to focus.</p>
    </div>

    <h3 class="rc-subhead">🗺️ What's inside</h3>
    <div class="rc-3col">
      <div class="rc-wi"><div class="rc-wi-icon">🏠</div><h4>Overview</h4><p>Top-level payment health — success rates, volume by region, and payment method mix.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">💳</div><h4>Payment processing</h4><p>Acceptance rates by gateway, payment method, card BIN, and decline reason.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🔄</div><h4>Account updater</h4><p>Revenue protected through automatic card updates before payments fail.</p></div>
    </div>
    <div class="rc-3col">
      <div class="rc-wi"><div class="rc-wi-icon">🔁</div><h4>Payment retries</h4><p>Recovered revenue through intelligent retries — and which attempt captured it.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🛡️</div><h4>Fraud prevention</h4><p>Blocked transactions and risk score trends. Available for Kount-enabled merchants.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🎯</div><h4>How this path works</h4><p>Each step walks through one dashboard, what it shows, and an activity to try in your account.</p></div>
    </div>

    <div class="rc-sec-header" style="margin-top:40px;">
      <div class="rc-sec-icon">🧭</div>
      <div>
        <h2>How to find it</h2>
        <p>Payments Hub lives inside Analytics in your Recurly account. No setup required — if you have the Analytics role, it's already there.</p>
      </div>
    </div>

    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Log in to your Recurly account</h3><p>Head to <strong>app.recurly.com</strong> and sign in with your credentials.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Navigate to Analytics</h3><p>Click <strong>Analytics</strong> in the left-hand navigation.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Select Payments Hub</h3><p>Under Analytics, click <strong>Payments Hub</strong> to open the Overview dashboard — your starting point for all payment analytics.</p></div></div>
    </div>

    <!-- Replace [NAV_IMAGE_URL] with the hosted URL of your navigation screenshot -->
    <img src="[NAV_IMAGE_URL]" alt="Navigating to Payments Hub in Recurly Analytics" style="width:100%;border-radius:14px;border:1px solid var(--lightgray);margin-bottom:24px;" />

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Don't see Payments Hub?</strong> You need the <strong>Analytics user role</strong> in Recurly. If it's missing from your nav, contact your Recurly admin to confirm your permissions. <a href="https://docs.recurly.com/recurly-subscriptions/docs/user-roles-and-permissions" target="_blank" style="color:var(--orange);font-weight:700;">Learn about user roles →</a></p>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Data availability</h4><p>Payments Hub began collecting data in Q1 2026. Data prior to that date is not available in these dashboards — this is expected.</p></div>
    </div>

    <h3 class="rc-subhead">✅ Before you move on</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Getting started checklist</h3></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="gs1"><label for="gs1" class="rc-clab">Open Payments Hub in your Recurly account<span>Analytics → Payments Hub → Overview</span></label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="gs2"><label for="gs2" class="rc-clab">Confirm all 5 sections are visible in your left nav: Overview, Payment Processing, Account Updater, Payment Retry Recovery, and Fraud Prevention<span>If any are missing, check your user role or contact support</span></label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="gs3"><label for="gs3" class="rc-clab">Take note of the first number that catches your attention on the Overview dashboard<span>You'll dig into this in the next step</span></label></div>
    </div>

    <div class="rc-sec-nav">
      <span class="rc-btn-disabled">🎯 Start</span>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview">Next: Overview →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/payments-hub" target="_blank">📖 Recurly Docs: Payments Hub</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/user-roles-and-permissions" target="_blank">🔐 User roles and permissions</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
  </div>
</div>
`}</HTMLBlock>

<br />
