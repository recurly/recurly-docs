---
title: When not to use it
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
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700}
  .rc-sec{margin-bottom:56px}.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;background:var(--yellow);flex-shrink:0}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)} .rc-sec-header p{margin:0;color:var(--gray);font-size:.95rem;line-height:1.5}
  .rc-callout,.rc-tip,.rc-card,.rc-opt,.rc-step{background:var(--offwhite);border-radius:14px}
  .rc-callout{border:1px solid #4A90D9;padding:16px 20px;margin-bottom:24px;display:flex;gap:14px}.rc-callout-icon{font-size:20px}.rc-callout p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
  .rc-step{padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
  .rc-sbadge-orange{width:38px;height:38px;border-radius:10px;background:var(--orange);color:#fff;font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)} .rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
  .rc-tip{border:2px solid var(--yellow);padding:20px 24px;margin-bottom:24px;display:flex;gap:16px}.rc-tipicon{font-size:24px}
  .rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-card{padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}.rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px}
  .rc-opt{border:1px solid var(--lightgray);padding:18px}.rc-oicon{font-size:22px;margin-bottom:8px}
  .rc-opt h4{font-size:.92rem;font-weight:700;margin:0 0 5px;color:var(--offblack)} .rc-opt p{font-size:.82rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-tag{display:inline-block;margin-top:10px;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700}
  .rc-tag-green{background:#2E7D32;color:#fff}.rc-tag-orange{background:var(--orange);color:#fff}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}
  .rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media (max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-2col{grid-template-columns:1fr}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/things-to-consider"><span class="rc-snum">3</span>Things to Consider</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/when-not-to-use-it"><span class="rc-snum">4</span>When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/how-to-enable-it"><span class="rc-snum">5</span>How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/tracking-impact"><span class="rc-snum">6</span>Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pitch-to-leadership"><span class="rc-snum">✓</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🚫</div>
      <div><h2>When You Might Not Want to Use It</h2><p>Account Updater is the right tool for most Recurly customers — but there are specific situations where enabling it in Recurly either doesn't apply or would create redundancy.</p></div>
    </div>

    <div class="rc-callout">
      <span class="rc-callout-icon">ℹ️</span>
      <p>None of these situations are permanent disqualifiers. They are simply configurations worth understanding before you toggle AU on. If any apply to you, review them with your technical team or Recurly Account Manager.</p>
    </div>

    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge-orange">1</div><div><h3>You're already running AU through your gateway</h3><p>If your gateway is already subscribed to an Account Updater service and is updating the card data in its own vault, running AU in Recurly as well would be redundant. In most cases, you should pick one place to run it.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge-orange">2</div><div><h3>You're using your gateway's hosted checkout and passing gateway tokens</h3><p>If your checkout is powered by a gateway-native solution and you're sending a gateway token to Recurly rather than the raw card data, Recurly does not hold the actual card details. In this setup, you should enable AU with your gateway, not Recurly.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge-orange">3</div><div><h3>Your billing model relies primarily on manual invoices</h3><p>Account Updater is designed for subscription-based, automatic recurring billing where a card is stored on file. If your primary billing workflow is manually issuing invoices, AU will have limited or no applicability to your billing flow.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge-orange">4</div><div><h3>You exclusively use Alternative Payment Methods</h3><p>If your entire subscriber base pays via APMs — Apple Pay, Google Pay, SEPA, ACH, PayPal, etc. — Account Updater will not apply to any of your transactions. AU is a card-specific service.</p></div></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Most Merchants Don't Fall Into These Categories</h4><p>If you're using Recurly.js for checkout, billing credit or debit card subscribers on auto-renew, and not running AU elsewhere — you're a strong candidate to enable Account Updater today.</p></div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🔁 Not Sure? A Quick Diagnostic</h3>
      <div class="rc-2col">
        <div class="rc-opt"><div class="rc-oicon">✅</div><h4>You should enable AU in Recurly if…</h4><p>You use Recurly.js or Recurly-hosted checkout, have auto-renewing card subscribers, and are not running AU through your gateway for the same cards.</p><span class="rc-tag rc-tag-green">Go for it</span></div>
        <div class="rc-opt"><div class="rc-oicon">🔀</div><h4>Enable AU with your gateway instead if…</h4><p>You use gateway-hosted checkout and pass gateway tokens to Recurly. In this case, the gateway holds the card data and should run the update service.</p><span class="rc-tag rc-tag-orange">Gateway side</span></div>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/things-to-consider">← Things to Consider</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/how-to-enable-it">Next: How to Enable It →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/docs/account-updater" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Account Updater</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/things-to-consider">🤔 Things to Consider</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">🎧 Contact Customer Success</a>
  </div>
</div>
</body>
</html>
</HTMLBlock>
`}</HTMLBlock>

<br />
