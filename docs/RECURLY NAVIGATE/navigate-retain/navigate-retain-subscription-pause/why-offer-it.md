---
title: Why offer it?
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
  .rc-card,.rc-wi,.rc-tip,.rc-warning{margin-bottom:24px}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray)}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray);text-align:center}
  .rc-wi-icon{font-size:30px;margin-bottom:10px}
  .rc-wi h4{font-size:.88rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
  .rc-wi p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start}
  .rc-tipicon{font-size:24px;flex-shrink:0}
  .rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
  .rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start}
  .rc-wicon{font-size:20px;flex-shrink:0}
  .rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev{border:1px solid var(--lightgray);background:#fff;color:var(--darkgray)}
  .rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
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
    <div class="rc-badge">📈 Retention Impact</div>
    <h1>Why Offer Pause?</h1>
    <p>Pause gives subscribers a flexible alternative to cancellation and helps merchants preserve relationships that might otherwise be lost.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">38%</div><div class="rc-lbl">Prefer pause over cancel</div></div>
      <div><div class="rc-num">337%</div><div class="rc-lbl">Pause usage increase</div></div>
      <div><div class="rc-num">3 in 4</div><div class="rc-lbl">Paused subscribers return</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/update/docs/pause-subscriptions-1"><span class="rc-snum">1</span>What Is It?</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/why-offer-it"><span class="rc-snum">2</span>Why Offer It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/best-practices-1"><span class="rc-snum">3</span>Best Practices</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/metrics-to-track"><span class="rc-snum">4</span>Metrics to Track</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/building-the-case"><span class="rc-snum">5</span>Building the Case</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/how-to-implement"><span class="rc-snum">6</span>How to Implement</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/resources"><span class="rc-snum">✓</span>Resources</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🎯</div>
      <div>
        <h2>Pause helps retain subscribers who are not ready to leave for good</h2>
        <p>Many subscribers cancel for temporary reasons. Pause gives them a way to step away without ending the relationship permanently.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📌 Why it matters</h3>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">
        According to Recurly’s 2026 State of Subscriptions report, 38% of consumers prefer pausing over canceling. The same report found that brands offering “pause before cancel” saw pause usage increase by 337%, and 3 out of 4 of those paused subscribers returned within months.
      </p>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0;">
        For merchants, that means pause can help reduce voluntary churn while preserving future revenue opportunities.
      </p>
    </div>

    <div class="rc-3col">
      <div class="rc-wi"><div class="rc-wi-icon">💸</div><h4>Budget Changes</h4><p>Some subscribers need a temporary break because of changing financial priorities.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">✈️</div><h4>Travel or Seasonality</h4><p>Usage can fluctuate during travel periods or seasonal slowdowns.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">📦</div><h4>Excess Inventory</h4><p>Pause can be especially useful when customers have more product than they can use.</p></div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Good to know:</strong> Pause is most valuable when the customer’s reason for leaving is temporary. It helps you offer flexibility without defaulting straight to cancellation.</p>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>The Bottom Line</h4><p>Pause is a practical retention strategy because it gives subscribers control while keeping them connected to your brand.</p></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/update/docs/pause-subscriptions-1">← Back: What Is It?</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/best-practices-1">Next: Best Practices →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://recurly.com/blog/why-pausing-a-subscription-can-be-a-powerful-retention-tactic/" target="_blank" rel="noopener noreferrer">📝 Blog: Why Pause Is Powerful</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/metrics-to-track">📊 Metrics to Track</a>
  </div>

</div>
</body>
</html>
</HTMLBlock>
`}</HTMLBlock>

<br />
