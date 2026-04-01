---
title: 'Section 5: Gateway Failover'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<HTMLBlock>{\`
<style>
  .rc-guide{--yellow:#FFD706;--orange:#FF8200;--vermillion:#FF5810;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
  .rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px;margin-bottom:0}
  .rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
  .rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
  .rc-hero>p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 32px;color:var(--lightgray)}
  .rc-hero-stats{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}
  .rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:8px;padding:10px 14px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s,background .2s,color .2s}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack);text-decoration:none}
  .rc-nav a.rc-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-sec{margin-bottom:56px}
  .rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
  .rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-opt{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:14px;padding:18px}
  .rc-oicon{font-size:22px;margin-bottom:8px}
  .rc-opt h4{font-size:.92rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
  .rc-opt p{font-size:.82rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-tag{display:inline-block;margin-top:10px;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;background:var(--offblack);color:var(--yellow)}
  .rc-tag-green{background:#2E7D32;color:#fff}
  .rc-tag-orange{background:var(--orange);color:#fff}
  .rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
  .rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
  .rc-sbadge{width:38px;height:38px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
  .rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;margin-bottom:24px;display:flex;gap:16px;align-items:flex-start}
  .rc-tipicon{font-size:24px;flex-shrink:0}
  .rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
  .rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;margin-bottom:24px;display:flex;gap:14px;align-items:flex-start}
  .rc-wicon{font-size:20px;flex-shrink:0}
  .rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:28px}
  .rc-cl-header{padding:16px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:center;gap:10px;background:var(--offblack)}
  .rc-cl-header h3{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
  .rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:flex-start;gap:14px}
  .rc-cli:last-child{border-bottom:none}
  .rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;margin-top:1px;background:#fff;display:flex;align-items:center;justify-content:center;font-size:12px;color:var(--gray)}
  .rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}
  .rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
  .rc-phase-tag{display:inline-flex;align-items:center;gap:6px;background:var(--offblack);color:var(--yellow);border-radius:20px;padding:4px 14px;font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;margin-bottom:20px}
  .rc-complete-banner{background:var(--offblack);border-radius:16px;padding:32px;text-align:center;margin-bottom:24px}
  .rc-complete-banner h3{font-size:1.3rem;font-weight:800;color:var(--yellow);margin:10px 0 8px}
  .rc-complete-banner p{font-size:.9rem;color:var(--lightgray);margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none;border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}
  .rc-btn-next{background:var(--yellow);color:var(--offblack);border-color:var(--yellow)}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  .rc-link-sec:hover{background:var(--brightgray)}
  @media(max-width:640px){
    .rc-hero h1{font-size:1.7rem}
    .rc-2col{grid-template-columns:1fr}
    .rc-hero{padding:36px 20px 32px}
    .rc-hero-stats{gap:20px}
    .rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}
    .rc-sec-nav{align-items:stretch}
  }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">⚙️ Phase 1: Optimization</div>
    <h1>Navigate Launchpad</h1>
    <p>Your 90-day program to optimize, grow, and master your Recurly subscription business.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Week 5</div><div class="rc-lbl">Gateway Failover</div></div>
      <div><div class="rc-num">Phase 1</div><div class="rc-lbl">Optimization</div></div>
      <div><div class="rc-num">~15</div><div class="rc-lbl">Min to Complete</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-welcome"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-production-testing"><span class="rc-snum">1</span>Production Testing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-dunning"><span class="rc-snum">2</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-account-updater"><span class="rc-snum">3</span>Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-branding"><span class="rc-snum">4</span>Branding</a>
    <a class="rc-active" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-metrics"><span class="rc-snum">6</span>Metrics & Growth</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-phase-tag">⚙️ Phase 1 · Week 5 of 6</div>

    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔒</div>
      <div>
        <h2>Gateway Failover</h2>
        <p>Outages are rare. But when your primary payment gateway goes down, having a backup in place is the difference between zero lost revenue and a very bad day.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🤔 What Is Gateway Failover?</h3>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Gateway Failover is Recurly's ability to automatically route transactions to a secondary payment gateway when your primary gateway is unavailable or experiencing errors. When it works, customers don't know anything happened — their purchase goes through, your subscription starts, and revenue is protected.</p>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0;">Without failover, a gateway outage means failed transactions, lost sign-ups, and disrupted renewals — even if the outage lasts only minutes. For a subscription business, that's direct revenue loss and potential subscriber frustration.</p>
    </div>

    <h3 class="rc-subhead">⚡ What Can Trigger a Gateway Failure?</h3>
    <div class="rc-2col">
      <div class="rc-opt"><div class="rc-oicon">🔌</div><h4>System Outages</h4><p>Gateway infrastructure goes down for scheduled or unplanned maintenance. Even major providers experience occasional outages that can last minutes to hours.</p><span class="rc-tag rc-tag-orange">Unpredictable</span></div>
      <div class="rc-opt"><div class="rc-oicon">🚨</div><h4>Fraud or Chargeback Thresholds</h4><p>A sudden spike in chargebacks or fraud flags can cause your gateway to temporarily suspend processing for your account — sometimes with little warning.</p><span class="rc-tag rc-tag-orange">Risk-Based</span></div>
      <div class="rc-opt"><div class="rc-oicon">⚙️</div><h4>Configuration Errors</h4><p>A misconfiguration, API key expiry, or credential change can break your gateway connection silently — you might not notice until transactions start failing.</p><span class="rc-tag rc-tag-orange">Avoidable</span></div>
      <div class="rc-opt"><div class="rc-oicon">🛡️</div><h4>With Failover Enabled</h4><p>All of the above become a non-event. Recurly detects the primary gateway failure and reroutes automatically. Payments continue. Customers notice nothing.</p><span class="rc-tag rc-tag-green">Protected</span></div>
    </div>

    <h3 class="rc-subhead">⚙️ How to Enable Gateway Failover</h3>
    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Set up a secondary gateway account</h3><p>To use Gateway Failover, you need a second payment gateway connected to Recurly. This can be a different gateway provider entirely, or a second account with the same provider. The secondary gateway should be fully verified and capable of processing real transactions.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Connect the secondary gateway in Recurly</h3><p>In your Recurly admin, go to <strong>Settings → Payment Gateways</strong>. Add your secondary gateway using the same process you used for your primary — entering credentials and verifying the connection.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Configure failover routing rules</h3><p>Once both gateways are connected, configure which gateway is primary and which is the failover. You can set Recurly to automatically route to the secondary when the primary fails a specified number of consecutive transactions.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>Review gateway selection logic</h3><p>Recurly's gateway selection logic uses factors including transaction type, card brand, and geography to route transactions optimally. Review the documentation to understand how routing decisions are made for your specific setup.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">5</div><div><h3>Test your failover configuration</h3><p>Before relying on it, simulate a failover scenario in a test environment to confirm transactions route correctly to the secondary gateway. Don't wait for a real outage to discover your failover isn't configured properly.</p></div></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Pro Tip · Keep Both Gateways Active</h4>
        <p>A common mistake is to set up a secondary gateway and never process any real transactions through it. Gateways can develop issues like credential expiry or account inactivity flags that you won't discover until you need the failover. Consider routing a small percentage of transactions to your secondary gateway regularly to keep it active and verified.</p>
      </div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Not all gateways support failover.</strong> Review Recurly's Gateway Failover documentation to confirm your specific gateway combination is supported. Some gateway features and transaction types have limitations in failover configurations. Check the docs before assuming full coverage.</p>
    </div>

    <div class="rc-complete-banner">
      <div style="font-size:36px;">🎉</div>
      <h3>You've Completed Phase 1!</h3>
      <p>With Production Testing, Dunning, Account Updater, Branding, and Gateway Failover complete — your Recurly setup is optimized and protected. Next up: Phase 2, where you'll master the metrics that drive subscription growth.</p>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Week 5 Checklist: Gateway Failover</h3></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Identified a secondary gateway for failover<span>Verified the gateway is supported by Recurly's failover feature</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Secondary gateway connected and credentials verified in Recurly<span>Settings → Payment Gateways</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Failover routing rules configured<span>Primary/secondary hierarchy and failure thresholds set</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Failover tested in test environment<span>Confirmed transactions route correctly to secondary</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Plan in place to keep secondary gateway active<span>Consider routing a small % of transactions regularly</span></div></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-branding">← Branding</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-metrics">Next: Metrics & Growth →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/docs/gateway-failover" target="_blank" rel="noopener noreferrer">📖 Gateway Failover Docs</a>
    <a class="rc-link-btn rc-link-sec" href="https://share.synthesia.io/12149951-6016-4a63-86fb-bab20b93da0b" target="_blank" rel="noopener noreferrer">▶ Trail Guide Video</a>
    <a class="rc-link-btn rc-link-sec" href="https://support.recurly.com" target="_blank" rel="noopener noreferrer">🎧 Recurly Support</a>
  </div>
</div>
\`}</HTMLBlock>
`}</HTMLBlock>

<br />
