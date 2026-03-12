---
title: Pause Subscriptions
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
  .rc-guide{
    --yellow:#FFD706;--orange:#FF8200;--vermillion:#FF5810;--salmon:#FF9D88;
    --offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;
    --brightgray:#F1EFE3;--offwhite:#FFFDF2;
    font-family:'Segoe UI',system-ui,sans-serif;
  }
  *{box-sizing:border-box}
  body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
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
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray);text-align:center}
  .rc-wi-icon{font-size:30px;margin-bottom:10px}
  .rc-wi h4{font-size:.88rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
  .rc-wi p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
  .rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
  .rc-sbadge{width:38px;height:38px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
  .rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
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
  @media (max-width:640px){
    .rc-hero h1{font-size:1.7rem}
    .rc-3col{grid-template-columns:1fr}
    .rc-hero{padding:36px 20px 32px}
    .rc-hero-stats{gap:20px}
    .rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}
    .rc-sec-nav{align-items:stretch}
  }
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">⏸️ Retention Strategy</div>
    <h1>Pause, Not Cancel</h1>
    <p>Give subscribers a flexible alternative to cancellation by temporarily pausing service instead of ending the relationship.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">38%</div><div class="rc-lbl">Prefer pause to cancel</div></div>
      <div><div class="rc-num">337%</div><div class="rc-lbl">Increase in pause usage</div></div>
      <div><div class="rc-num">3 in 4</div><div class="rc-lbl">Paused subscribers return</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/pause-not-cancel"><span class="rc-snum">1</span>What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/why-offer-pause"><span class="rc-snum">2</span>Why Offer It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-best-practices"><span class="rc-snum">3</span>Best Practices</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-metrics"><span class="rc-snum">4</span>Metrics to Track</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/building-the-case-for-pause"><span class="rc-snum">5</span>Building the Case</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/implementing-pause"><span class="rc-snum">6</span>How to Implement</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-resources"><span class="rc-snum">✓</span>Resources</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">⏸️</div>
      <div>
        <h2>What is Pause?</h2>
        <p>A plain-language explanation of how subscription pause works and why it is one of the most effective alternatives to voluntary churn.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🧩 The Simple Version</h3>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Sometimes a subscriber wants a break, not a breakup. They may be traveling, managing a tighter budget, working through extra inventory, or simply not using the service as often for a period of time. In those moments, canceling is a permanent action that ends the relationship entirely — even when the reason for leaving is temporary.</p>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0;"><strong>Pause gives you a smarter option.</strong> Instead of canceling, a subscriber can temporarily stop billing and service delivery while keeping their subscription, account history, and often even their pricing intact. That gives customers the flexibility they want while helping you preserve future revenue and reduce voluntary churn.</p>
    </div>

    <div class="rc-3col">
      <div class="rc-wi"><div class="rc-wi-icon">💳</div><h4>Billing Temporarily Stops</h4><p>Pause lets you suspend recurring charges for a defined period instead of ending the subscription outright.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🔒</div><h4>The Relationship Stays Intact</h4><p>The subscriber keeps their account, history, and connection to your brand rather than leaving your lifecycle completely.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🔄</div><h4>Reactivation Becomes Easier</h4><p>Because the subscription was paused rather than canceled, returning is often much simpler than reacquiring a churned customer.</p></div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🗺️ How Pause Works — Step by Step</h3>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>A subscriber signals cancellation intent</h3><p>This often happens because of temporary circumstances like budget changes, travel, seasonality, or product backlog — not because they are done with your brand forever.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>You offer pause as an alternative</h3><p>Instead of forcing an all-or-nothing decision, you give the subscriber a lower-friction option that acknowledges their current needs.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Billing and fulfillment are suspended</h3><p>During the pause period, invoices and service delivery stop temporarily, helping the subscriber step away without canceling.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>The subscription remains active in principle</h3><p>The customer relationship, account data, and future opportunity to resume are preserved, which keeps the subscriber in your retention pipeline.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">5</div><div><h3>The subscriber resumes later</h3><p>When circumstances improve, the customer can unpause and continue their subscription journey — often without the friction of signing up all over again.</p></div></div>
      </div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Important to know:</strong> Pause is most effective when it is treated as a retention strategy, not just a billing setting. The goal is not to delay churn blindly — it is to give the right subscribers a flexible path back into active engagement.</p>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>The Bottom Line</h4><p>Pause helps you retain subscribers who would otherwise cancel for temporary reasons. It preserves the customer relationship, reduces voluntary churn, and creates a smoother path to reactivation than starting over after a cancellation.</p></div>
    </div>

    <div class="rc-sec-nav">
      <span class="rc-btn-disabled">← Back</span>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/why-offer-pause">Next: Why Offer It? →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Pause Subscription</a>
    <a class="rc-link-btn" href="https://recurly.com/blog/why-pausing-a-subscription-can-be-a-powerful-retention-tactic/" target="_blank" rel="noopener noreferrer">📝 Blog: Why Pause Is Powerful</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/why-offer-pause">📈 Next: Why Offer It?</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">🎧 Contact Customer Success</a>
  </div>

</div>
</body>
</html>
</HTMLBlock>
`}</HTMLBlock>

<br />
