---
title: 'Section 1: Final Production Testing'
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
.rc-warning{background:#fff5f0;border:1px solid #ffb894;border-radius:12px;padding:15px 17px;margin-bottom:16px;font-size:.87rem;color:var(--darkgray);line-height:1.6}
.rc-warning strong{color:#cc4400}
.rc-video-wrap{position:relative;width:100%;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:10px;margin-bottom:8px;background:var(--offblack)}
.rc-video-wrap iframe{position:absolute;top:0;left:0;width:100%;height:100%;border:0}
.rc-video-cap{font-size:.8rem;color:var(--gray);text-align:center;margin-bottom:4px;font-style:italic}
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
    <h1>Final Production Testing</h1>
    <p>Walk through checkout from your customer's perspective to catch payment or compliance issues before they affect real subscribers.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Step 1</div><div class="rc-lbl">Phase 1</div></div>
      <div><div class="rc-num">~30</div><div class="rc-lbl">Min to Complete</div></div>
      <div><div class="rc-num">PSD2</div><div class="rc-lbl">Compliance Check</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-production-testing" class="rc-active"><span class="rc-snum">1</span>Production Testing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-dunning-optimization"><span class="rc-snum">2</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-account-updater"><span class="rc-snum">3</span>Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-branding"><span class="rc-snum">4</span>Branding</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-review"><span class="rc-snum">✓</span>Review &amp; Resources</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🧪</div>
      <div>
        <h2>Why Test in Production?</h2>
        <p>Testing from your customer's perspective surfaces friction you'd never catch from the admin side — expired test cards, missing compliance flows, checkout errors that quietly block signups.</p>
      </div>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">▶ Trail Guide: Final Production Testing</p>
      <div class="rc-video-wrap">
        <iframe src="https://share.synthesia.io/embeds/videos/f3384551-b4b2-4ab3-83fa-c8fe6e88c62f" loading="lazy" title="Navigate Launchpad — Final Production Testing" allow="encrypted-media; fullscreen;" allowfullscreen></iframe>
      </div>
      <p class="rc-video-cap">A walkthrough of Recurly's production testing best practices — what to test, how to test it, and what to look for.</p>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">🔍 What Production Testing Covers</p>
      <div class="rc-2col">
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 6px">Checkout Experience</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.6;margin:0">Sign up as a real customer using a live test card. Does the flow feel right? Are the right plan details displayed?</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 6px">Payment Processing</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.6;margin:0">Confirm your gateway is processing correctly, decline codes are handled gracefully, and successful payments complete as expected.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 6px">PSD2 &amp; 3DS Compliance</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.6;margin:0">If you sell to European subscribers, verify your 3D Secure (3DS) authentication flow is triggering correctly per PSD2 requirements.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 6px">Subscriber Notifications</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.6;margin:0">Trigger a test transaction and verify that your confirmation email is sent, styled correctly, and contains the right subscription details.</p>
        </div>
      </div>
    </div>

    <p class="rc-subhead" style="margin-bottom:12px">🪜 Step-by-Step: Run Your Production Test</p>
    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Use a real payment method</h3>
          <p>Use a live card (not a sandbox test card) to complete a real transaction. Use the lowest-price plan available, then cancel and refund immediately after confirming it worked.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Walk through the entire checkout flow</h3>
          <p>Navigate from plan selection → checkout → confirmation, exactly as a new subscriber would. Note any confusion, missing information, or friction points.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Verify your confirmation email</h3>
          <p>Check that the post-signup email arrives promptly, looks correct, includes the right plan name and pricing, and links to your subscriber portal.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div>
          <h3>Simulate a failed payment</h3>
          <p>Use a card that will decline (Recurly docs list specific test decline codes for production testing). Confirm the error message shown to the subscriber is clear and actionable.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div>
          <h3>Check PSD2 / 3DS if selling in Europe</h3>
          <p>Attempt a transaction that should trigger 3D Secure authentication. Confirm the challenge flow appears, completes, and that the payment succeeds after authentication.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Best Practice:</strong> Run your production test from a different device and browser than your usual admin setup — ideally a mobile device. Many checkout issues are device-specific and won't surface in a desktop-only test.
    </div>

    <div class="rc-warning">
      <strong>⚠ PSD2 Reminder:</strong> If you process payments from EU subscribers and haven't verified your 3DS setup, you may face declined transactions. Review Recurly's PSD2 compliance documentation before moving to the next step.
    </div>

    <p class="rc-subhead" style="margin-bottom:12px">✅ Production Testing Checklist</p>
    <div class="rc-checklist">
      <div class="rc-cl-header"><h3>Complete Before Moving to Dunning</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Completed a live test transaction using a real payment method.<span>Use the cheapest plan — refund immediately after</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Confirmed a successful test transation.<span>Log in to your Recurly App and confirm the test transaction shows a successful payment</span>.</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Refunded the test transaction.<span>In Recurly, confirm the refund processed successfully.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Verified PSD2 / 3DS authentication.<span>(EU merchants only). Resources are linked below.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Reviewed your payment gateway and checkout configuration.<span>Use the provided documentation below for assistance, and contact support or use Compass AI Assistant if issues persist.</span></div></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one">← Welcome</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-dunning-optimization">Step 2: Dunning →</a>
    </div>

    <div class="rc-resources">
      <h3>Additional Resources</h3>
      <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/revised-payment-services-directive-psd2" target="_blank" rel="noopener noreferrer">📖 PSD2 Compliance Docs</a>
      <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/test" target="_blank" rel="noopener noreferrer">🧪 Test Gateway</a>
			<a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/checkout#configuration-landing-page" target="_blank" rel="noopener noreferrer">✔️ Review Checkout Configuration</a>
      <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">✉ Contact Customer Support</a>
    </div>
  </div>

</div>
`}</HTMLBlock>
