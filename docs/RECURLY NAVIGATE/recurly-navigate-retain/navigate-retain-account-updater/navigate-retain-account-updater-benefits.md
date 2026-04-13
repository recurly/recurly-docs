---
title: 'Why use it? '
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
  .rc-guide{--yellow:#FFD706;--orange:#FF8200;--vermillion:#FF5810;--salmon:#FF9D88;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
  *{box-sizing:border-box} body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
  .rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px}
  .rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
  .rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
  .rc-hero p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 32px;color:var(--lightgray)}
  .rc-hero-stats,.rc-stat-grid{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num,.rc-stat-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}
  .rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:8px;padding:10px 14px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack);box-shadow:0 2px 10px rgba(255,215,6,.25)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-sec{margin-bottom:56px}.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)} .rc-sec-header p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-card,.rc-opt,.pricing-card,.rc-tip,.rc-stat{border-radius:14px}
  .rc-card{background:var(--offwhite);padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-stat-grid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-stat{background:var(--offblack);padding:24px 16px;text-align:center}
  .rc-stat-label{font-size:.78rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px;margin-top:4px}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:26px}
  .rc-opt{background:var(--offwhite);border:1px solid var(--lightgray);padding:18px}
  .rc-oicon{font-size:22px;margin-bottom:8px}
  .rc-opt h4{font-size:.92rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
  .rc-opt p{font-size:.82rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-tag{display:inline-block;margin-top:10px;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;background:var(--offblack);color:var(--yellow)}
  .pricing-card{padding:20px 24px;margin-bottom:16px;border:1px solid var(--lightgray);background:var(--offwhite)}
  .pricing-card.free{border-left:4px solid #2E7D32}.pricing-card.paid{border-left:4px solid var(--orange)}
  .pricing-card h4{font-size:.95rem;font-weight:700;color:var(--offblack);margin:0 0 6px}
  .pricing-card p{font-size:.86rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);padding:20px 24px;margin-bottom:24px;display:flex;gap:16px;align-items:flex-start}
  .rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
  .rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}
  .rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media (max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-2col,.rc-stat-grid{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/why-use-it"><span class="rc-snum">2</span>Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/things-to-consider"><span class="rc-snum">3</span>Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/when-not-to-use-it"><span class="rc-snum">4</span>When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/how-to-enable-it"><span class="rc-snum">5</span>How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/tracking-impact"><span class="rc-snum">6</span>Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pitch-to-leadership"><span class="rc-snum">✓</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">📈</div>
      <div><h2>Why Should You Use Account Updater?</h2><p>The business case for enabling Account Updater — including what it protects, what it recovers, and what it costs.</p></div>
    </div>

    <div class="rc-stat-grid">
      <div class="rc-stat"><div class="rc-stat-num">77x</div><div class="rc-stat-label">Average ROI across Recurly customers using AU</div></div>
      <div class="rc-stat"><div class="rc-stat-num">18%</div><div class="rc-stat-label">Of recovered revenue attributed to AU on average</div></div>
      <div class="rc-stat"><div class="rc-stat-num">96M+</div><div class="rc-stat-label">Card updates processed by Recurly in 2025</div></div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🎯 The Core Problem It Solves</h3>
      <p style="font-size:0.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Involuntary churn — customers who leave not because they wanted to, but because a payment failed — is one of the largest and most preventable sources of subscriber loss for recurring businesses. Failed payments happen every day, and a large share of them are caused not by lack of funds or genuine cancellation intent, but simply by outdated card information.</p>
      <p style="font-size:0.92rem;color:var(--darkgray);line-height:1.6;margin:0;">When a card expires or is reissued, the subscriber probably doesn't think to update it in your system — especially if they haven't interacted with your product recently. They may not even know their card changed. Account Updater catches those changes before the charge ever fails.</p>
    </div>

    <h3 class="rc-subhead">💼 Key Business Benefits</h3>
    <div class="rc-2col">
      <div class="rc-opt"><div class="rc-oicon">🛡️</div><h4>Prevent Involuntary Churn Before It Starts</h4><p>Unlike dunning, which attempts to recover revenue after a payment has already failed, Account Updater acts before the failed charge ever occurs. It's the most upstream form of revenue protection available.</p><span class="rc-tag">Proactive</span></div>
      <div class="rc-opt"><div class="rc-oicon">💸</div><h4>Reduce Failed Payment Volume</h4><p>Fewer failed payments means less dunning overhead, fewer customer service inquiries about billing, and less operational cost spent chasing recoverable revenue.</p><span class="rc-tag">Cost Reduction</span></div>
      <div class="rc-opt"><div class="rc-oicon">🤝</div><h4>Zero-Friction for Your Subscribers</h4><p>Customers never have to update their card details themselves. No email asking them to update their payment method. No risk of them clicking through to cancel instead. The experience stays seamless.</p><span class="rc-tag">CX Improvement</span></div>
      <div class="rc-opt"><div class="rc-oicon">🔁</div><h4>Works Alongside Dunning, Not Instead of It</h4><p>Account Updater and Recurly's dunning logic are complementary. AU fixes known card changes before charging; dunning handles unexpected declines after the fact. Together they form a comprehensive revenue recovery strategy.</p><span class="rc-tag">Complementary</span></div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">💰 Pricing Considerations</h3>
      <p style="font-size:0.88rem;color:var(--gray);margin:0 0 16px;">How Account Updater is priced depends on your Recurly contract. Check your contract or speak with your Account Manager to understand which applies to you.</p>
      <div class="pricing-card free"><h4>✅ Included in Your Contract</h4><p>For many Recurly customers, Account Updater is bundled into their subscription plan at no additional per-update cost. If this is your situation, there is no incremental cost to enable it — and no financial reason not to.</p></div>
      <div class="pricing-card paid"><h4>💳 Usage-Based Pricing</h4><p>For some customers, Account Updater is available as a per-successful-update service. A charge applies only when Recurly successfully retrieves updated card information — not for every lookup. Compare the cost per update against your average subscription value to assess the business case for your situation.</p></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Think About the Lifetime Value</h4><p>When a subscription renews successfully instead of failing, you're not just recovering one month of revenue — you're protecting the subscriber's entire future lifetime value. A successful card update today can be worth many months or even years of continued subscription revenue.</p></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-account-updater">← What Is It?</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/things-to-consider">Next: Things to Consider →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/docs/account-updater" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Account Updater</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/tracking-impact">📊 Tracking Impact</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">🎧 Contact Customer Success</a>
  </div>
</div>
</body>
</html>
</HTMLBlock>
`}</HTMLBlock>

<br />
