---
title: Building the Case
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
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:20px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start;margin-bottom:16px}
  .rc-sbadge{width:38px;height:38px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
  .rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
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
    .rc-hero{padding:36px 20px 32px}
    .rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}
    .rc-sec-nav{align-items:stretch}
  }
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">🧱 Business Case</div>
    <h1>Building the Case</h1>
    <p>Use pause as a retention conversation, not just a feature conversation.</p>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/update/docs/pause-subscriptions-1"><span class="rc-snum">1</span>What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/why-offer-it"><span class="rc-snum">2</span>Why Offer It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/best-practices-1"><span class="rc-snum">3</span>Best Practices</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/metrics-to-track"><span class="rc-snum">4</span>Metrics to Track</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/building-the-case"><span class="rc-snum">5</span>Building the Case</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/how-to-implement"><span class="rc-snum">6</span>How to Implement</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/resources"><span class="rc-snum">✓</span>Resources</a>
  </nav>

  <div class="rc-sec-header">
    <div class="rc-sec-icon">💼</div>
    <div>
      <h2>How to explain the value of pause internally</h2>
      <p>If you need buy-in, frame pause around retention, flexibility, and long-term customer value.</p>
    </div>
  </div>

  <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Pause supports retention</h3><p>It gives subscribers a temporary alternative to cancellation, which can help reduce voluntary churn.</p></div></div>
  <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Pause supports customer choice</h3><p>The 2026 State of Subscriptions report found that 38% of consumers prefer pausing over canceling.</p></div></div>
  <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Pause preserves future value</h3><p>When subscribers pause instead of cancel, merchants keep the relationship intact and create a clearer path to return.</p></div></div>
  <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>Pause aligns with the Retain stage of the flywheel</h3><p>It helps merchants hold onto existing relationships during budget shifts, seasonality, usage gaps, or other temporary disruptions.</p></div></div>

  <div class="rc-card">
    <h3 class="rc-subhead">🎬 Example from the market</h3>
    <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0;">
      Cinemark used Recurly’s pause functionality during pandemic closures to suspend billing without forcing cancellations. According to your source materials, this contributed to a 90% customer retention rate over a 14-month closure period.
    </p>
  </div>

  <div class="rc-tip">
    <span class="rc-tipicon">💡</span>
    <div><h4>Leadership framing</h4><p>Pause is easiest to justify when positioned as a low-friction way to protect relationships that would otherwise be lost to temporary churn.</p></div>
  </div>

  <div class="rc-sec-nav">
    <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/metrics-to-track">← Back: Metrics to Track</a>
    <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/how-to-implement">Next: How to Implement →</a>
  </div>

</div>
</body>
</html>
</HTMLBlock>
`}</HTMLBlock>

<br />
