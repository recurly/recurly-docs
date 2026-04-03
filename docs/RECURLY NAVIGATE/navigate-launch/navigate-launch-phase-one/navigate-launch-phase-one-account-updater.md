---
title: 'Section 3: Account Updater'
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
    <h1>Enable Account Updater</h1>
    <p>Keep billing information current automatically so subscribers aren't lost over expired or replaced cards — protecting renewals and revenue before failures ever happen.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Step 3</div><div class="rc-lbl">Phase 1</div></div>
      <div><div class="rc-num">Proactive</div><div class="rc-lbl">Card Updates</div></div>
      <div><div class="rc-num">↓ Churn</div><div class="rc-lbl">Involuntary</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-production-testing"><span class="rc-snum">1</span>Production Testing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-dunning-optimization"><span class="rc-snum">2</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-account-updater" class="rc-active"><span class="rc-snum">3</span>Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-branding"><span class="rc-snum">4</span>Branding</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-review"><span class="rc-snum">✓</span>Review &amp; Resources</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">💳</div>
      <div>
        <h2>Stop Card Failures Before They Start</h2>
        <p>Account Updater works silently in the background — checking with card networks to get fresh card numbers before renewal attempts, so payments succeed the first time without any subscriber action.</p>
      </div>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">▶ Trail Guide: Secure Your Launch — Account Updater</p>
      <div class="rc-video-wrap">
        <iframe src="https://share.synthesia.io/embeds/videos/b86fe7bd-1f74-491f-8632-acebd4794615" loading="lazy" title="Navigate Launchpad — Account Updater" allow="encrypted-media; fullscreen;" allowfullscreen></iframe>
      </div>
      <p class="rc-video-cap">Learn how Account Updater works, what card networks are supported, how to enable it in Recurly, and how to measure its impact on involuntary churn.</p>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">🔁 How Account Updater Works</p>
      <div class="rc-2col">
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Card networks maintain update files</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Visa, Mastercard, Discover, and Amex maintain files of updated card numbers. Recurly queries these files to catch changes in card numbers or expiry dates.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Updates happen before billing</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">For most gateways, checks occur days before renewal. However, Stripe and Adyen support <strong>Real-Time</strong> updates during the transaction attempt.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">No subscriber action required</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Subscribers never know this happened — their subscription just keeps renewing. This directly reduces involuntary churn without any friction.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Works alongside dunning</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Account Updater and dunning are complementary. AU reduces the volume of payments that fail; dunning recovers the ones that still do (like NSF or lost cards).</p>
        </div>
      </div>
    </div>

    <p class="rc-subhead" style="margin-bottom:10px">💰 Pricing Overview</p>
    <div class="rc-pricing-card free">
      <div class="rc-pricing-label">Included — Visa &amp; Discover</div>
      <h4>Account Updater for Visa &amp; Discover</h4>
      <p>Visa and Discover card network updates are enabled directly in Payment Settings. These can be turned on without any additional plan changes.</p>
    </div>
    <div class="rc-pricing-card usage" style="margin-bottom:16px">
      <div class="rc-pricing-label">Configuration Required — Mastercard &amp; Amex</div>
      <h4>Mastercard &amp; American Express Coverage</h4>
      <p>Mastercard requires your 4-digit <strong>MCC code</strong>. Amex requires a 10-digit <strong>SE Number</strong> (direct accounts only; OptBlue not supported).</p>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip:</strong> You can find your <strong>MCC (Merchant Category Code)</strong> on your bank processing statement. For <strong>Amex</strong>, the SE number is found on your direct American Express merchant statement.
    </div>

    <p class="rc-subhead" style="margin-bottom:12px">🪜 Step-by-Step: Enable Account Updater</p>
    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Navigate to Payment Settings</h3>
          <p>In your Recurly admin, go to <strong>Configuration → Payment Settings</strong>. Account Updater is located at the top of this page. You'll see toggle controls for each supported card network.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Enable Visa and Discover</h3>
          <p>Toggle on Account Updater for Visa and Discover — these can be enabled directly. These two networks cover a large share of most subscriber bases.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Enter Mastercard &amp; Amex Codes</h3>
          <p>Provide your 4-digit <strong>MCC</strong> for Mastercard and 10-digit <strong>SE Number</strong> for Amex. If you are using <strong>Amex OptBlue</strong> via your gateway, you cannot enable Amex here.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div>
          <h3>Monitor impact in Phase 2</h3>
          <p>In Phase 2 of Launchpad, you'll track your Involuntary Churn Rate and Decline Rate at Renewal on the Benchmarks Dashboard. Watch for a decline in both metrics over time.</p>
        </div>
      </div>
    </div>

    <p class="rc-subhead" style="margin-bottom:12px">✅ Account Updater Checklist</p>
    <div class="rc-checklist">
      <div class="rc-cl-header"><h3>Complete Before Moving to Branding</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Located Account Updater in Configuration → Payment Settings</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Enabled Account Updater for Visa and Discover</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Entered MCC (Mastercard) and SE Number (Amex) if you have a direct Amex account</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Noted your current Involuntary Churn Rate as a baseline for Phase 2 benchmarking</div></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-dunning-optimization">← Dunning</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-branding">Step 4: Branding →</a>
    </div>

    <div class="rc-resources">
      <h3>Additional Resources</h3>
      <a class="rc-link-btn" href="https://docs.recurly.com/docs/account-updater" target="_blank" rel="noopener noreferrer">📖 Account Updater Docs</a>
      <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">✉ Contact Customer Success</a>
    </div>
  </div>

</div>
`}</HTMLBlock>

<br />
