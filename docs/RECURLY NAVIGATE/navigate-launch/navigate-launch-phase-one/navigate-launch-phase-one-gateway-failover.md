---
title: 'Section 5: Gateway Failover'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
.rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif;max-width:960px;margin:0 auto;padding:0 20px 60px}
.rc-hero{background:var(--offblack);border-radius:16px;padding:52px 40px 44px;text-align:center;margin-bottom:0}
.rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 20px;font-size:12px;font-weight:800;letter-spacing:1px;text-transform:uppercase;margin-bottom:18px}
.rc-hero h1{font-size:2.3rem;font-weight:800;line-height:1.15;margin:0 0 12px;color:#fff}
.rc-hero>p{font-size:1rem;max-width:680px;margin:0 auto 28px;color:#CCC9B8;line-height:1.6}
.rc-hero-stats{display:flex;justify-content:center;gap:36px;flex-wrap:wrap}
.rc-num{font-size:1.7rem;font-weight:800;color:var(--yellow)}
.rc-lbl{font-size:.76rem;color:#CCC9B8;text-transform:uppercase;letter-spacing:.5px}
.rc-nav{display:flex;flex-wrap:wrap;gap:8px;margin:22px 0 32px;padding:16px;background:var(--offwhite);border-radius:14px;border:1px solid var(--lightgray)}
.rc-nav a{display:inline-flex;align-items:center;gap:7px;padding:9px 13px;border-radius:10px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.83rem;font-weight:700;transition:all .2s}
.rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.25);color:var(--offblack);text-decoration:none}
.rc-nav a.rc-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack)}
.rc-snum{display:inline-flex;align-items:center;justify-content:center;width:22px;height:22px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:11px;font-weight:800;flex-shrink:0}
.rc-nav a.rc-active .rc-snum{background:rgba(13,13,11,.15);color:var(--offblack)}
.rc-sec{margin-bottom:48px}
.rc-sec-header{display:flex;align-items:flex-start;gap:18px;margin-bottom:28px}
.rc-sec-icon{width:52px;height:52px;border-radius:14px;background:var(--yellow);display:flex;align-items:center;justify-content:center;font-size:24px;flex-shrink:0}
.rc-sec-header h2{font-size:1.45rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
.rc-sec-header p{font-size:.9rem;color:var(--gray);margin:0;line-height:1.6}
.rc-card{background:#fff;border:1px solid var(--lightgray);border-radius:14px;padding:20px 22px;margin-bottom:16px;box-shadow:0 2px 6px rgba(13,13,11,.04)}
.rc-subhead{font-size:.98rem;font-weight:800;color:var(--offblack);margin:0 0 10px}
.rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:16px}
.rc-steps{display:flex;flex-direction:column;gap:11px;margin-bottom:16px}
.rc-step{background:#fff;border:1px solid var(--lightgray);border-radius:12px;padding:15px 17px;display:flex;gap:13px;align-items:flex-start}
.rc-sbadge{width:34px;height:34px;border-radius:9px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:14px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-step h3{font-size:.93rem;font-weight:700;margin:0 0 4px;color:var(--offblack)}
.rc-step p{font-size:.84rem;color:var(--gray);line-height:1.6;margin:0}
.rc-tip{background:#fffde6;border:1px solid var(--yellow);border-radius:12px;padding:15px 17px;margin-bottom:16px;font-size:.87rem;color:var(--darkgray);line-height:1.6}
.rc-tip strong{color:var(--offblack)}
.rc-video-wrap{position:relative;width:100%;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:10px;margin-bottom:8px;background:var(--offblack)}
.rc-video-wrap iframe{position:absolute;top:0;left:0;width:100%;height:100%;border:0}
.rc-video-cap{font-size:.8rem;color:var(--gray);text-align:center;margin-bottom:4px;font-style:italic}
.rc-pricing-card{border-radius:12px;padding:18px 20px;margin-bottom:10px;border:1px solid var(--lightgray)}
.rc-pricing-card.free{background:#f0fff4;border-color:#86efac}
.rc-pricing-card.usage{background:#fffde6;border-color:var(--yellow)}
.rc-pricing-label{font-size:.76rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;margin-bottom:6px}
.rc-pricing-card.free .rc-pricing-label{color:#16a34a}
.rc-pricing-card.usage .rc-pricing-label{color:#92400e}
.rc-pricing-card h4{font-size:.93rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
.rc-pricing-card p{font-size:.84rem;color:var(--gray);margin:0;line-height:1.5}
.rc-checklist{background:var(--offwhite);border-radius:14px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:18px}
.rc-cl-header{padding:13px 19px;border-bottom:1px solid var(--lightgray);display:flex;align-items:center;gap:9px;background:var(--offblack)}
.rc-cl-header h3{font-size:.82rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
.rc-cli{padding:11px 19px;border-bottom:1px solid var(--brightgray);display:flex;gap:11px;align-items:flex-start}
.rc-cli:last-child{border-bottom:none}
.rc-cb{width:19px;height:19px;border-radius:5px;border:2px solid var(--lightgray);flex-shrink:0;margin-top:1px;background:#fff}
.rc-clab{font-size:.85rem;color:var(--darkgray);line-height:1.4}
.rc-clab span{display:block;font-size:.75rem;color:var(--gray);margin-top:2px}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.87rem;text-decoration:none;border:1px solid var(--lightgray)}
.rc-btn-prev{background:#fff;color:var(--darkgray)}
.rc-btn-prev:hover{background:var(--brightgray);text-decoration:none}
.rc-btn-next{background:var(--yellow);color:var(--offblack);border-color:var(--yellow)}
.rc-btn-next:hover{opacity:.92;text-decoration:none}
.rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default;pointer-events:none}
.rc-link-btn{background:var(--yellow);color:var(--offblack);border-color:var(--yellow);margin:0 8px 8px 0}
.rc-link-btn:hover{opacity:.9;text-decoration:none}
.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
.rc-link-sec:hover{background:var(--brightgray);text-decoration:none}
.rc-resources{margin-top:32px}
.rc-resources h3{font-size:.84rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--gray);margin:0 0 12px}
@media(max-width:640px){.rc-hero{padding:30px 16px 26px}.rc-hero h1{font-size:1.65rem}.rc-2col{grid-template-columns:1fr}.rc-hero-stats{gap:14px}.rc-sec-header{flex-direction:column}.rc-sec-nav{flex-direction:column;align-items:stretch}}
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">🚀 Navigate · Launchpad Phase 1</div>
    <h1>Enable Gateway Failover</h1>
    <p>Protect your revenue from third-party outages. If your primary gateway goes down, Recurly automatically reroutes payments to your backup to ensure continuity.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Step 5</div><div class="rc-lbl">Phase 1</div></div>
      <div><div class="rc-num">Automatic</div><div class="rc-lbl">Rerouting</div></div>
      <div><div class="rc-num">Zero</div><div class="rc-lbl">Downtime Churn</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="#"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="#"><span class="rc-snum">1</span>Production Testing</a>
    <a href="#"><span class="rc-snum">2</span>Dunning</a>
    <a href="#"><span class="rc-snum">3</span>Account Updater</a>
    <a href="#"><span class="rc-snum">4</span>Branding</a>
    <a href="#" class="rc-active"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="#"><span class="rc-snum">✓</span>Review &amp; Resources</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔌</div>
      <div>
        <h2>Your Payment Safety Net</h2>
        <p>Gateway Failover monitors the health of your primary gateway. If communication errors reach a specific threshold, Recurly shifts traffic to your backup gateway until the primary recovers.</p>
      </div>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">▶ Trail Guide: Business Continuity — Gateway Failover</p>
      <div class="rc-video-wrap">
        <iframe src="https://share.synthesia.io/f05bd8df-772f-4b7c-a561-848420075bb1" loading="lazy" title="Navigate Launchpad — Gateway Failover" allow="encrypted-media; fullscreen;" allowfullscreen></iframe>
      </div>
      <p class="rc-video-cap">See how Recurly detects gateway outages and how transactions are seamlessly rerouted to maintain your uptime.</p>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">🛡️ Failover Logic &amp; Constraints</p>
      <div class="rc-2col">
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Error Threshold Detection</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Recurly tracks "Communication Errors." When these errors hit a high velocity in a short window, failover is triggered automatically.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Automatic Recovery</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Recurly continues to probe the primary gateway. Once healthy responses return, traffic is shifted back to your primary provider.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Vaulted Cards Only</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Failover works best for cards stored in Recurly's vault. Gateway-only tokens (like Stripe-only tokens) cannot be failed over to other providers.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Smart Rerouting</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">If you exclude a gateway from failover, Recurly will ignore it as a backup option—ideal for specialty or high-cost gateways.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>⚠️ Plan Note:</strong> Gateway Failover is available on <strong>Professional and Elite plans</strong>. If you are on a Starter plan, you will need to upgrade to enable this feature.
    </div>

    <p class="rc-subhead" style="margin-bottom:12px">🪜 Step-by-Step: Configuration</p>
    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Add a Backup Gateway</h3>
          <p>Ensure you have at least two gateways configured in <strong>Configuration → Payment Gateways</strong>. Both should support the same currencies and card types.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Enable Failover</h3>
          <p>On the Payment Gateways page, find the <strong>Gateway Failover</strong> modal on the right-hand sidebar. Click "Enable" to activate the monitoring logic.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Set Exclusions (Optional)</h3>
          <p>If a gateway should <em>never</em> be used as a backup, click <strong>Options → Edit Gateway</strong> and check the box "Exclude from Gateway Failover."</p>
        </div>
      </div>
    </div>

    <p class="rc-subhead" style="margin-bottom:12px">✅ Gateway Failover Checklist</p>
    <div class="rc-checklist">
      <div class="rc-cl-header"><h3>Verify Before Launch</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Confirmed site is on a Professional or Elite plan</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">At least two gateways are configured for primary currencies</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Gateway Failover toggled to "Enabled" in the sidebar</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Excluded any specialty gateways from being used as backups</div></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="#">← Branding</a>
      <a class="rc-btn-next" href="#">Final Step: Review →</a>
    </div>

    <div class="rc-resources">
      <h3>Additional Resources</h3>
      <a class="rc-link-btn" href="https://docs.recurly.com/docs/gateway-failover" target="_blank">📖 Failover Documentation</a>
      <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">✉ Contact Support</a>
    </div>
  </div>

</div>
`}</HTMLBlock>

<br />
