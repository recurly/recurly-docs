---
title: Metrics to Track
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
  .rc-hero p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 0;color:var(--lightgray)}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:8px;padding:10px 14px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700}
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700}
  .rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
  .rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-wi{background:var(--offwhite);border-radius:14px;padding:24px;border:1px solid var(--lightgray);text-align:center}
  .rc-wi-icon{font-size:30px;margin-bottom:10px}
  .rc-wi h4{font-size:.95rem;font-weight:700;margin:0 0 8px;color:var(--offblack)}
  .rc-wi p{font-size:.84rem;color:var(--gray);line-height:1.55;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}
  .rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
  .rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev{border:1px solid var(--lightgray);background:#fff;color:var(--darkgray)}
  .rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  @media (max-width:640px){
    .rc-hero h1{font-size:1.7rem}
    .rc-3col{grid-template-columns:1fr}
    .rc-hero{padding:36px 20px 32px}
    .rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}
    .rc-sec-nav{align-items:stretch}
  }
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">📊 Measurement</div>
    <h1>Metrics to Track</h1>
    <p>Tracking the right metrics helps you understand whether pause is improving retention or simply delaying churn.</p>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/update/docs/pause-subscriptions-1"><span class="rc-snum">1</span>What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/why-offer-it"><span class="rc-snum">2</span>Why Offer It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/best-practices-1"><span class="rc-snum">3</span>Best Practices</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/metrics-to-track"><span class="rc-snum">4</span>Metrics to Track</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/building-the-case"><span class="rc-snum">5</span>Building the Case</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/how-to-implement"><span class="rc-snum">6</span>How to Implement</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/resources"><span class="rc-snum">✓</span>Resources</a>
  </nav>

  <div class="rc-sec-header">
    <div class="rc-sec-icon">📈</div>
    <div>
      <h2>Start with these 3 core pause metrics</h2>
      <p>These are the three measurement areas highlighted in your transcript and deck.</p>
    </div>
  </div>

  <div class="rc-3col">
    <div class="rc-wi"><div class="rc-wi-icon">🔄</div><h4>Unpause Rate</h4><p>Tracks how many paused subscribers return. This helps show whether pause is actually retaining customers.</p></div>
    <div class="rc-wi"><div class="rc-wi-icon">⏱️</div><h4>Pause Duration</h4><p>Shows how long subscribers step away. This can support forecasting and help time re-engagement efforts.</p></div>
    <div class="rc-wi"><div class="rc-wi-icon">📉</div><h4>Voluntary Churn</h4><p>Helps you evaluate whether offering pause is reducing cancellations over time.</p></div>
  </div>

  <div class="rc-tip">
    <span class="rc-tipicon">💡</span>
    <div><h4>How to use these metrics</h4><p>Track them together. A pause program with strong unpause rates and lower voluntary churn signals that pause is functioning as a real retention tool.</p></div>
  </div>

  <div class="rc-sec-nav">
    <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/best-practices-1">← Back: Best Practices</a>
    <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/building-the-case">Next: Building the Case →</a>
  </div>

</div>
</body>
</html>
</HTMLBlock>
`}</HTMLBlock>

<br />
