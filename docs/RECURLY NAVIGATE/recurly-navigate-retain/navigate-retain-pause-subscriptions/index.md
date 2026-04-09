---
title: Pause Subscription - API Test
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
.rc-guide { font-family: "Inter", -apple-system, sans-serif; color: #0D0D0B; max-width: 900px; margin: 0 auto; background: #ffffff; border-radius: 16px; overflow: hidden; box-shadow: 0 4px 24px rgba(0,0,0,0.08); }
.rc-hero { background: #0D0D0B; color: white; padding: 48px 40px; text-align: center; position: relative; overflow: hidden; }
.rc-hero-topo { position: absolute; top: 0; left: 0; right: 0; bottom: 0; background-image: url('Topo-for-Black-Background-1.png'); opacity: 0.1; pointer-events: none; }
.rc-badge { background: #FFD706; color: #0D0D0B; padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; position: relative; z-index: 1; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; position: relative; z-index: 1; }
.rc-subtitle { color: #CCC9B8; font-size: 16px; margin: 0; position: relative; z-index: 1; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; background: #FF9D88; color: #0D0D0B; position: relative; z-index: 1; }
.rc-nav { display: flex; background: #F1EFE3; padding: 0; overflow-x: auto; border-bottom: 2px solid #CCC9B8; }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: #807D73; font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: #0D0D0B; background: #FFFDF2; }
.rc-nav a.is-active { color: #0D0D0B; font-weight: 600; border-bottom-color: #FFD706; background: #FFFDF2; }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: #CCC9B8; color: #807D73; display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: #FFD706; color: #0D0D0B; }
.rc-sec { padding: 40px; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: #FFD706; border-radius: 12px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
.rc-card { background: #FFFDF2; border-radius: 12px; padding: 28px; margin-bottom: 20px; border: 1px solid #CCC9B8; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: #32312D; line-height: 1.7; margin: 0 0 12px; font-size: 15px; }
.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: #0D0D0B; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: #FFFDF2; border-radius: 12px; padding: 20px; margin-bottom: 16px; border: 1px solid #CCC9B8; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: #FFD706; color: #0D0D0B; display: flex; align-items: center; justify-content: center; font-weight: 700; flex-shrink: 0; }
.rc-2col { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 20px 0; }
.rc-wi { background: #FFFDF2; border-radius: 12px; padding: 24px; text-align: center; border: 1px solid #CCC9B8; }
.rc-tip { border-left: 4px solid #FFD706; background: #FFFDF2; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-warning { border-left: 4px solid #FF8200; background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-sec-nav { display: flex; justify-content: space-between; padding: 0 40px 40px; align-items: center; }
.rc-btn-next { background: #FFD706; color: #0D0D0B; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; }
.rc-link-sec { padding: 32px 40px; background: #F1EFE3; border-top: 1px solid #CCC9B8; }
.rc-link-btn { display: inline-flex; align-items: center; background: #ffffff; border: 1px solid #CCC9B8; padding: 10px 20px; border-radius: 8px; text-decoration: none; color: #0D0D0B; font-size: 14px; font-weight: 500; margin-right: 10px; }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-hero-topo"></div>
    <img src="Retain-icon-white.png" alt="Retain" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;position:relative;z-index:1;" />
    <span class="rc-badge">Subscriptions</span>
    <h1>Pause, Not Cancel</h1>
    <p class="rc-subtitle">Decrease voluntary churn by offering subscribers a pause option instead of forcing a binary stay-or-cancel decision.</p>
    <div class="rc-flywheel-badge">RETAIN</div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions" class="is-active"><span class="rc-snum">1</span> What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits"><span class="rc-snum">2</span> Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-considerations"><span class="rc-snum">3</span> Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-fit"><span class="rc-snum">4</span> When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-enable"><span class="rc-snum">5</span> How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-data"><span class="rc-snum">6</span> Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-use-case"><span class="rc-snum">7</span> Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon"><img src="package-check.svg" alt="package" width="28" height="28" /></div>
      <div>
        <h2>What Is Pause Subscriptions?</h2>
        <p>Understand how Recurly's Pause feature works and why it's a powerful tool in your churn-reduction toolkit.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>The Pause Concept in a Nutshell</h3>
      <p>Recurly's Pause Subscriptions feature lets you temporarily halt a subscriber's billing cycle without canceling their subscription. Instead of losing a subscriber entirely when they need a break—whether due to travel, seasonal usage patterns, or budget constraints—you give them a middle option.</p>
      <p>Think of it this way: cancellation is a door that's hard to reopen. A pause is a bookmark—the subscriber's place is held, their payment method stays on file, and their return path is frictionless.</p>
    </div>

    <div class="rc-subhead">How the Pause Lifecycle Works</div>

    <div class="rc-step">
      <div class="rc-sbadge">1</div>
      <div style="flex:1;">
        <h4 style="margin:0 0 4px; font-size:16px;">Pause Is Initiated</h4>
        <p style="margin:0; font-size:14px; color:#32312D;">A pause can be triggered by the subscriber via self-service, by your team in the Admin Console, or via the Recurly API.</p>
      </div>
    </div>

    <div class="rc-step">
      <div class="rc-sbadge">2</div>
      <div style="flex:1;">
        <h4 style="margin:0 0 4px; font-size:16px;">Current Period Completes</h4>
        <p style="margin:0; font-size:14px; color:#32312D;">The pause does not take effect immediately mid-cycle. The subscriber continues to have access through the end of their current billing period.</p>
      </div>
    </div>

    <div class="rc-step">
      <div class="rc-sbadge">3</div>
      <div style="flex:1;">
        <h4 style="margin:0 0 4px; font-size:16px;">Subscription Enters Paused State</h4>
        <p style="margin:0; font-size:14px; color:#32312D;">While paused, Recurly will not generate any invoices. The subscriber's account, plan details, and coupons all remain intact.</p>
      </div>
    </div>

    <div class="rc-step">
      <div class="rc-sbadge">4</div>
      <div style="flex:1;">
        <h4 style="margin:0 0 4px; font-size:16px;">Automatic Resumption</h4>
        <p style="margin:0; font-size:14px; color:#32312D;">When the specified cycles elapse, Recurly automatically resumes the subscription and generates a new invoice.</p>
      </div>
    </div>

    <div class="rc-subhead">Pause vs. Cancel: A Critical Distinction</div>

    <div class="rc-2col">
      <div class="rc-wi">
        <h4 style="font-size:16px; margin:0 0 8px;">⏸️ Pause</h4>
        <p style="font-size:13px; color:#807D73; margin:0;">Billing stops temporarily. Account stays active. Payment method retained. Automatic resumption.</p>
      </div>
      <div class="rc-wi">
        <h4 style="font-size:16px; margin:0 0 8px;">❌ Cancel</h4>
        <p style="font-size:13px; color:#807D73; margin:0;">Subscription terminates. Subscriber must re-sign up. Reacquisition cost is high.</p>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Pair Pause with Cancel-Save Flows</strong>
      <p>When a subscriber clicks "Cancel," present pause as an alternative before they finalize. This intercept can convert would-be cancellations into temporary pauses.</p>
    </div>
  </div>

  <div class="rc-sec-nav">
    <span style="color:#807D73; font-weight:600; font-size:14px;">● Page 1 of 7</span>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits" class="rc-btn-next">Next: Why Use It? →</a>
  </div>

  <div class="rc-link-sec">
    <h3 style="font-size:18px; margin:0 0 16px;">Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">📄 Pause Documentation</a>
    <a href="#" class="rc-link-btn">🎥 Video Walkthrough</a>
  </div>
</div>
`}</HTMLBlock>

<br />
