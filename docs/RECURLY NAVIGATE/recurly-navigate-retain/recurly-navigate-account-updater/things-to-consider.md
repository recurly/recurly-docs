---
title: Things to consider
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<HTMLBlock>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8" />
<style>
  .rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
  *{box-sizing:border-box} body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
  .rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px}
  .rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
  .rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
  .rc-hero p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 32px;color:var(--lightgray)}
  .rc-hero-stats{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num{font-size:1.8rem;font-weight:800;color:var(--yellow)} .rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:8px;padding:10px 14px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700}
  .rc-sec{margin-bottom:56px}.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)} .rc-sec-header p{margin:0;color:var(--gray);font-size:.95rem;line-height:1.5}
  .rc-card,.rc-tip,.rc-warning,.rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-card{padding:28px}.rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-tip{border:2px solid var(--yellow);padding:20px 24px;display:flex;gap:16px;align-items:flex-start}
  .rc-tipicon{font-size:24px}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-warning{background:#FFF8E6;border:1px solid var(--orange);padding:16px 20px;display:flex;gap:14px;align-items:flex-start}
  .rc-wicon{font-size:20px}.rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
  .rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
  .rc-sbadge{width:38px;height:38px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)} .rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
  .rc-checklist{overflow:hidden}.rc-cl-header{padding:16px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:center;gap:10px;background:var(--offblack)}
  .rc-cl-header h3{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
  .rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;gap:14px}.rc-cli:last-child{border-bottom:none}
  .rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;background:#fff;display:flex;align-items:center;justify-content:center;font-size:12px;color:var(--gray)}
  .rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}.rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}
  .rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media (max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
</style>
</head>
<body>
<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">💳 Revenue Recovery</div>
    <h1>Account Updater</h1>
    <p>Protect your recurring revenue by automatically keeping card details up to date — before payments ever fail.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">77x</div><div class="rc-lbl">Average ROI</div></div>
      <div><div class="rc-num">18%</div><div class="rc-lbl">Of recovered revenue</div></div>
      <div><div class="rc-num">96M+</div><div class="rc-lbl">Card updates in 2025</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-account-updater"><span class="rc-snum">1</span>What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/why-use-it"><span class="rc-snum">2</span>Why Use It?</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/things-to-consider"><span class="rc-snum">3</span>Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/when-not-to-use-it"><span class="rc-snum">4</span>When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/how-to-enable-it"><span class="rc-snum">5</span>How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/tracking-impact"><span class="rc-snum">6</span>Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pitch-to-leadership"><span class="rc-snum">✓</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🤔</div>
      <div><h2>Things to Think About</h2><p>Before enabling Account Updater, take a few minutes to review these considerations to ensure you get the most out of the feature.</p></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Good News: Most Merchants Are Already Set Up</h4><p>For the majority of Recurly customers, there's little to no technical work required to enable Account Updater. The main steps are a configuration toggle and — if you're enabling American Express Cardrefresher — providing your Amex merchant account details.</p></div>
    </div>

    <h3 class="rc-subhead">🔍 Key Questions to Ask Before You Enable</h3>
    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>How are you collecting card information?</h3><p>Account Updater works only when Recurly has direct access to card data — meaning you're using Recurly.js or a Recurly-hosted checkout. If you're using your gateway's own checkout and passing a gateway token to Recurly, Recurly doesn't hold the card data and cannot run AU.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Are you already using Account Updater through your gateway?</h3><p>If your payment gateway is already running Account Updater, enabling it again in Recurly would result in duplicate effort. You don't need both. However, Adyen users should review Recurly's dedicated Adyen RTAU integration.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>What payment types make up your subscriber base?</h3><p>Account Updater applies to credit and debit cards only. If a significant portion of your subscribers pay via ACH, bank transfer, PayPal, Apple Pay, Google Pay, or other alternative payment methods, those accounts won't benefit from AU.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>Do you use manual invoices?</h3><p>Account Updater does not apply to one-time transactions or manual invoices. If your billing model relies primarily on manually issued invoices rather than automatic subscription charges, AU will have limited applicability.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">5</div><div><h3>Do you want to enable American Express Cardrefresher?</h3><p>This requires a direct Amex merchant account and your business must be based in the United States. You'll need your Amex Service Establishment number and Merchant Category Code to complete setup.</p></div></div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📋 A Note on Adyen Users</h3>
      <p style="font-size:0.88rem;color:var(--darkgray);line-height:1.6;margin:0;">If Adyen is your primary gateway, Recurly now supports a dedicated Adyen Real-Time Account Updater integration. Enabling both Adyen RTAU and Recurly AU in parallel can maximize coverage across card brands and regions. Check the <a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen#adyen-realtime-account-updater" target="_blank" rel="noopener noreferrer" style="color:var(--orange);">Recurly Adyen RTAU docs</a> for current details.</p>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>One-time transactions are excluded.</strong> Account Updater is only applied to subscriptions — specifically to cards stored in Recurly's vault for recurring billing. It will not run on one-time charges or manual invoices regardless of how the feature is configured.</p>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Pre-Enablement Checklist</h3></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">You are using Recurly.js or Recurly-hosted checkout to collect card data<span>If using gateway tokens, enable AU with your gateway instead</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">You are not already running Account Updater through your gateway for the same card pool<span>Check with your payment ops team</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Your subscriber base includes a meaningful volume of credit/debit card payers<span>AU does not apply to APMs</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">If enabling Amex Cardrefresher: you have a direct Amex merchant account and a US business address<span>OptBlue accounts are not supported</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">You have reviewed the pricing model that applies to your contract<span>Speak with your Account Manager if unsure</span></div></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/why-use-it">← Why Use It?</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/when-not-to-use-it">Next: When Not to Use It →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/docs/account-updater" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Account Updater</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/adyen#adyen-realtime-account-updater" target="_blank" rel="noopener noreferrer">🔗 Adyen RTAU Docs</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">🎧 Contact Customer Success</a>
  </div>
</div>
</body>
</html>
</HTMLBlock>
`}</HTMLBlock>

<br />
