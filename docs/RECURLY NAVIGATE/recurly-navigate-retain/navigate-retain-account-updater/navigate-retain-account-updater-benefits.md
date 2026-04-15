---
title: 'Section 1: Why use it? '
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
  *{box-sizing:border-box}body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
  .rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px}
  .rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
  .rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
  .rc-hero p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 32px;color:var(--lightgray)}
  .rc-hero-stats,.rc-stat-grid{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num,.rc-stat-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}.rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:8px;padding:10px 14px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-sec{margin-bottom:56px}.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}.rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-stat-grid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-stat{background:var(--offblack);border-radius:14px;padding:24px 16px;text-align:center}
  .rc-stat-label{font-size:.78rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px;margin-top:4px}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:26px}
  .rc-opt{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:14px;padding:18px}
  .rc-oicon{font-size:22px;margin-bottom:8px}.rc-opt h4{font-size:.92rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-opt p{font-size:.82rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-tag{display:inline-block;margin-top:10px;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;background:var(--offblack);color:var(--yellow)}
  .pricing-card{border-radius:14px;padding:20px 24px;margin-bottom:16px;border:1px solid var(--lightgray);background:var(--offwhite)}
  .pricing-card.free{border-left:4px solid #2E7D32}.pricing-card.paid{border-left:4px solid var(--orange)}
  .pricing-card h4{font-size:.95rem;font-weight:700;color:var(--offblack);margin:0 0 6px}.pricing-card p{font-size:.86rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;margin-bottom:24px;display:flex;gap:16px;align-items:flex-start}
  .rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-2col,.rc-stat-grid{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater"><span class="rc-snum">1</span>What Is It?</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits"><span class="rc-snum">2</span>Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations"><span class="rc-snum">3</span>Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable"><span class="rc-snum">4</span>How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data"><span class="rc-snum">5</span>Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case"><span class="rc-snum">✓</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">📈</div>
      <div><h2>Why Should You Use Account Updater?</h2><p>Maximize your recovery ROI by stopping involuntary churn at the source. Account Updater (AU) secures future Lifetime Value (LTV) by bypassing the friction of dunning and avoiding unnecessary gateway transaction fees.</p></div>
    </div>

    <div class="rc-stat-grid">
      <div class="rc-stat"><div class="rc-stat-num">77x</div><div class="rc-stat-label">Average ROI across Recurly customers using AU</div></div>
      <div class="rc-stat"><div class="rc-stat-num">18%</div><div class="rc-stat-label">Of recovered revenue attributed to AU on average</div></div>
      <div class="rc-stat"><div class="rc-stat-num">96M+</div><div class="rc-stat-label">Card updates processed by Recurly in 2025</div></div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🎯 The Core Problem It Solves</h3>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Involuntary churn — customers who leave not because they wanted to, but because a payment failed — is one of the largest and most preventable sources of subscriber loss for recurring businesses. Beyond simple expirations, Account Updater (AU) also flags <strong>Account Closed</strong> statuses, allowing you to stop charging invalid cards immediately.</p>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0;">When a card is reissued, the subscriber rarely thinks to update it until their service is cut off. Account Updater (AU) catches those changes before the charge ever fails, preserving both the revenue and the customer relationship.</p>
    </div>

    <h3 class="rc-subhead">💼 Key Business Benefits</h3>
    <div class="rc-2col">
      <div class="rc-opt"><div class="rc-oicon">🛡️</div><h4>Prevent Involuntary Churn Upstream</h4><p>Unlike dunning, which reacts after a failure, Account Updater (AU) acts before the charge occurs. It is your first line of defense in protecting the customer lifecycle.</p><span class="rc-tag">Proactive Recovery</span></div>
      <div class="rc-opt"><div class="rc-oicon">💸</div><h4>Significant Cost Avoidance</h4><p>By identifying "Closed" or "Invalid" accounts before a transaction attempt, Account Updater (AU) helps you avoid gateway transaction fees for charges that were guaranteed to fail.</p><span class="rc-tag">Lower OpEx</span></div>
      <div class="rc-opt"><div class="rc-oicon">🤝</div><h4>Seamless Subscriber Experience</h4><p>No intrusive "Update your payment" emails or service interruptions. The transition to a new card happens silently in the vault, maintaining total friction-less billing.</p><span class="rc-tag">CX Improvement</span></div>
      <div class="rc-opt"><div class="rc-oicon">🔁</div><h4>Accelerate Active Dunning</h4><p>If a card is updated while an invoice is in dunning, Recurly uses the new info for the next automatic retry. This drastically increases the success rate of dunning cycles.</p><span class="rc-tag">Integrated Logic</span></div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">💰 Pricing Considerations</h3>
      <p style="font-size:.88rem;color:var(--gray);margin:0 0 16px;">How Account Updater (AU) is priced depends on your Recurly contract and the specific update method (Batch vs. Real-Time Account Updater (RTAU)).</p>
      <div class="pricing-card free"><h4>✅ Included in Your Contract</h4><p>Many plans bundle standard Batch Account Updater (AU) at no additional per-update cost. In these cases, it is a high-value feature that costs nothing extra to activate.</p></div>
      <div class="pricing-card paid"><h4>💳 Usage-Based Updates</h4><p>Some configurations apply fees for successful card updates. Because Account Updater (AU) recovers an average of 18% of revenue, the cost per update is typically a fraction of the recovered Lifetime Value (LTV).</p></div>
      <p style="font-size:.88rem;color:var(--gray);margin-top:16px;text-align:center;"><strong>Not sure which pricing model applies to you?</strong> <a href="mailto:support@recurly.com" style="color:var(--orange);font-weight:700;text-decoration:none;">Contact Recurly Support</a> to discuss your specific contract and the differences between Standard and Real-Time Account Updater (RTAU).</p>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Think About the Lifetime Value</h4><p>When a card updates successfully, you aren't just saving one invoice; you are securing the entire future stream of revenue for that subscriber. A single update today can protect hundreds or thousands of dollars in future Lifetime Value (LTV).</p></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater">← What Is It?</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations">Next: Things to Consider →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/account-updater" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Account Updater</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Customer Support</a>
<a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
  </div>
</div>
</body>
</html>
</HTMLBlock>
`}</HTMLBlock>

<br />
