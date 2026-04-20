---
title: 'Account Updater: Tracking impact'
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
  .rc-hero-stats{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}.rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:10px;padding:10px 18px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-sec{margin-bottom:56px}.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}.rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
  .rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
  .rc-sbadge-dark{width:38px;height:38px;border-radius:10px;background:var(--darkgray);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:26px}
  .rc-opt{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:14px;padding:18px}
  .rc-oicon{font-size:22px;margin-bottom:8px}.rc-opt h4{font-size:.92rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-opt p{font-size:.82rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-tag{display:inline-block;margin-top:10px;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;background:var(--offblack);color:var(--yellow)}
  .rc-office-hours{background:linear-gradient(135deg, var(--offblack) 0%, #1a1a1a 100%);color:#fff;border-radius:16px;padding:32px;margin:32px 0;display:flex;gap:24px;align-items:center;border:1px solid var(--yellow)}
  .rc-oh-content h4{color:var(--yellow);margin:0 0 8px;font-size:1.1rem;font-weight:800;text-transform:uppercase;letter-spacing:1px}
  .rc-oh-content p{color:var(--lightgray);font-size:.95rem;line-height:1.6;margin:0 0 20px}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;margin-bottom:24px;display:flex;gap:16px;align-items:flex-start}
  .rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-sec-header{flex-direction:column}.rc-2col{grid-template-columns:1fr}.rc-nav,.rc-sec-nav{flex-direction:column}.rc-sec-nav{align-items:stretch}.rc-office-hours{flex-direction:column;text-align:center}}
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
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater">Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits"><span class="rc-snum">1</span>Why use it?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations"><span class="rc-snum">2</span>Things to consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable"><span class="rc-snum">3</span>How to enable it</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data"><span class="rc-snum">4</span>Tracking impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case"><span class="rc-snum">5</span>Pitch to leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">📊</div>
      <div>
        <h2>Tracking the impact of account updater (AU)</h2>
        <p>Quantify your retention success by isolating revenue recovered through card updates. Utilize Churn Management dashboards for strategic trends and leverage Transactions Exports for a granular audit of every card lifecycle event.</p>
      </div>
    </div>

    <h3 class="rc-subhead">📏 Key performance indicators (KPIs)</h3>
    <div class="rc-2col">
      <div class="rc-opt"><div class="rc-oicon">💰</div><h4>Recovered revenue (AU)</h4><p>The total currency value successfully processed on cards updated by Account Updater (AU) prior to the billing attempt. This is your primary ROI signal.</p></div>
      <div class="rc-opt"><div class="rc-oicon">📉</div><h4>Involuntary churn rate</h4><p>The percentage of subscribers lost due to payment failure. This metric should decrease as Account Updater (AU) proactively handles card lifecycle events.</p></div>
      <div class="rc-opt"><div class="rc-oicon">📋</div><h4>Renewal count by AU</h4><p>The raw volume of subscription invoices that renewed successfully because of a card update. Found in Renewal Invoices reporting.</p></div>
      <div class="rc-opt"><div class="rc-oicon">🔍</div><h4>Remaining "expired" declines</h4><p>Found in Renewal Declines, this identifies cards that AU could not update (subject to network participation), helping you refine your dunning strategy.</p></div>
    </div>

    <h3 class="rc-subhead">📍 Navigating your dashboards</h3>
    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge-dark">1</div>
        <div>
          <h3>Recovered revenue dashboard</h3>
          <p>Navigate to <strong>Analytics → Churn Management → Recovered Revenue</strong>. Use the <strong>Recovered Revenue by Method</strong> chart to see the contribution of card updates compared to dunning.</p>
          
          <div style="position:relative;overflow:hidden;aspect-ratio:1920/1080;border-radius:12px;margin-top:16px;border:1px solid var(--lightgray);">
            <iframe src="https://share.synthesia.io/embeds/videos/57b979ea-216b-4e3f-8215-cd6060e32107" loading="lazy" title="Trail Guide: Recovered Revenue Dashboard" allowfullscreen allow="encrypted-media; fullscreen;" style="position:absolute;width:100%;height:100%;top:0;left:0;border:none;margin:0;"></iframe>
          </div>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge-dark">2</div>
        <div>
          <h3>Renewal invoices: The "other outcomes" chart</h3>
          <p>Go to <strong>Analytics → Churn Management → Renewal Invoices</strong>. Review the <strong>Invoices with Other Outcomes</strong> chart to see the specific count of invoices saved specifically by Account Updater (AU) logic.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge-dark">3</div>
        <div>
          <h3>Renewal eclines dashboard</h3>
          <p>Navigate to <strong>Analytics → Churn Management → Renewal Declines</strong>. Filter for "Expired Card" codes to see remaining friction points.</p>
        </div>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📁 Advanced audit: The invoices summary export</h3>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin-bottom:16px;">For raw data verification, use the <strong>Invoices Summary Export</strong> under <strong>Analytics → Exports</strong>. This report provides the underlying proof of card updates at the transaction level.</p>
      <div class="rc-step" style="border:none; padding:0;">
        <div class="rc-sbadge-dark" style="width:28px; height:28px; font-size:12px;">A</div>
        <p style="margin:0; padding-top:4px;"><strong>Filter by 'recovery_reason':</strong> Choose <code>account_updater</code> transactions to isolate AU collections.</p>
      </div>
    </div>

    <div class="rc-office-hours">
      <div class="rc-oh-content">
        <h4>🗓️ Need strategic support?</h4>
        <p>Join our <strong>Customer Success Global Office Hours</strong>! Meet face-to-face with our CSMs to walk through your analytics, work through roadblocks, and get strategic advice on optimizing your revenue recovery.</p>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" style="background-color:#ffd706; color:#0d0d0b; text-decoration:none; padding:12px 24px; border-radius:10px; font-weight:700; font-size:.9rem; display:inline-flex; align-items:center; gap:10px;">Register for office hours →</a>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Expert insight: The 90-day rule</h4><p>Account Updater (AU) impact is cumulative. It takes roughly 90 days to see the full "stabilized" impact on your recovery metrics. Use this window to establish your new churn baseline.</p></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable">← Section 3: How to enable It</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case">Next: Section 5: Pitch to leadership →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/docs/recovered-revenue" target="_blank" rel="noopener noreferrer">📈 Docs: Recovered Revenue Dashboard</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/docs/renewal-invoices" target="_blank" rel="noopener noreferrer">📋 Docs: Renewal invoices report</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/docs/renewal-declines" target="_blank" rel="noopener noreferrer">📉 Docs: Renewal declines dashboard</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/docs/transaction-export" target="_blank" rel="noopener noreferrer">📂 Docs: Transactions export guide</a>
  </div>
</div>
</body>
</html>
</HTMLBlock>
`}</HTMLBlock>

<br />
