---
title: Pause Subscription - API Test
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
.rc-guide { max-width: 900px; margin: 20px auto; font-family: "Inter", -apple-system, sans-serif; color: #0D0D0B; line-height: 1.6; background-color: #ffffff; border-radius: 16px; overflow: hidden; box-shadow: 0 4px 24px rgba(0,0,0,0.08); }
.rc-hero { background-color: #0D0D0B; color: #FFFFFF; padding: 56px 40px 48px; text-align: center; position: relative; overflow: hidden; }
.rc-hero-topo { position: absolute; top: 0; left: 0; right: 0; bottom: 0; background-image: url('Topo-for-Black-Background-1.png'); opacity: 0.1; pointer-events: none; }
.rc-flywheel-icon { width: 48px; height: 48px; margin-bottom: 16px; position: relative; z-index: 1; }
.rc-badge { display: inline-block; background-color: #FFD706; color: #0D0D0B; border-radius: 20px; padding: 6px 18px; font-size: 13px; font-weight: 700; text-transform: uppercase; margin-bottom: 20px; letter-spacing: 0.5px; position: relative; z-index: 1; }
.rc-hero h1 { font-size: 32px; margin: 0 0 12px; font-weight: 700; position: relative; z-index: 1; }
.rc-hero p { color: #CCC9B8; font-size: 1.1rem; margin: 0 auto; max-width: 600px; position: relative; z-index: 1; }
.rc-nav { display: flex; flex-wrap: wrap; gap: 10px; margin: 32px 0 40px; padding: 0 40px; }
.rc-nav a { display: inline-flex; align-items: center; gap: 10px; padding: 12px 16px; border-radius: 12px; border: 1px solid #CCC9B8; background-color: #FFFFFF; color: #32312D; text-decoration: none; font-size: 0.9rem; font-weight: 700; transition: all 0.2s ease; }
.rc-nav a:hover { border-color: #FFD706; box-shadow: 0 4px 12px rgba(255, 215, 6, 0.2); color: #0D0D0B; }
.rc-nav a.rc-active { border-color: #FFD706; background-color: #FFD706; color: #0D0D0B; }
.rc-snum { display: inline-flex; align-items: center; justify-content: center; width: 24px; height: 24px; border-radius: 50%; background-color: #0D0D0B; color: #FFD706; font-size: 11px; font-weight: 700; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 52px; height: 52px; background-color: #FFD706; border-radius: 14px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
.rc-sec-icon img { width: 28px; height: 28px; }
.rc-card { background-color: #FFFDF2; border-radius: 16px; padding: 32px; border: 1px solid #CCC9B8; margin-bottom: 24px; }
.rc-subhead { font-size: 1.5rem; font-weight: 700; margin: 40px 0 20px; }
.rc-step { display: flex; gap: 20px; background-color: #FFFDF2; border-radius: 12px; padding: 24px; border: 1px solid #CCC9B8; margin-bottom: 16px; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background-color: #FFD706; color: #0D0D0B; display: flex; align-items: center; justify-content: center; font-weight: 700; flex-shrink: 0; }
.rc-2col { display: flex; gap: 16px; margin: 20px 0; }
.rc-wi { flex: 1; background-color: #FFFDF2; border-radius: 12px; padding: 24px; text-align: center; border: 1px solid #CCC9B8; }
.rc-tip { border-left: 4px solid #FFD706; background-color: #FFFDF2; padding: 24px; border-radius: 0 12px 12px 0; margin: 24px 0; }
.rc-warning { border-left: 4px solid #FF8200; background-color: #FFF8F0; padding: 24px; border-radius: 0 12px 12px 0; margin: 24px 0; }
.rc-sec-nav { display: flex; justify-content: space-between; align-items: center; margin-top: 48px; padding: 24px 40px; border-top: 1px solid #CCC9B8; background: #FFFFFF; }
.rc-btn-next { background-color: #FFD706; color: #0D0D0B; padding: 12px 28px; border-radius: 10px; font-weight: 700; text-decoration: none; border: 1px solid #FFD706; }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-hero-topo"></div>
    <img src="Retain-icon-white.png" alt="Retain" class="rc-flywheel-icon" /> 
    <div class="rc-badge">Subscriptions</div>
    <h1>Pause, Not Cancel</h1>
    <p>Decrease voluntary churn by offering subscribers a pause option instead of forcing a binary stay-or-cancel decision.</p>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions" class="rc-active"><span class="rc-snum">1</span> What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits"><span class="rc-snum">2</span> Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-considerations"><span class="rc-snum">3</span> Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-fit"><span class="rc-snum">4</span> When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-enable"><span class="rc-snum">5</span> How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-data"><span class="rc-snum">6</span> Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-use-case"><span class="rc-snum">7</span> Pitch to Leadership</a>
  </nav>

  <div style="padding: 0 40px 40px;">
    <div class="rc-sec-header">
      <div class="rc-sec-icon"><img src="package-check.svg" alt="package" /></div>
      <div>
        <h2 style="margin:0; font-size:24px;">What Is Pause Subscriptions?</h2>
        <p style="margin:4px 0 0; color:#807D73;">Understand how Recurly's Pause feature works as a churn-reduction tool.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 style="margin-top:0;">The Pause Concept in a Nutshell</h3>
      <p>Recurly's Pause Subscriptions feature lets you temporarily halt a subscriber's billing cycle without canceling their subscription. Instead of losing a subscriber entirely when they need a break—whether due to travel, seasonal usage patterns, budget constraints, or simply wanting time away—you give them a middle option. The subscription enters a paused state: no invoices are generated, no charges occur, and the subscriber's account remains intact.</p>
      <p>When the pause period ends, billing resumes automatically on the next renewal date. Think of it this way: cancellation is a door that's hard to reopen. A pause is a bookmark—the subscriber's place is held, their payment method stays on file, and their return path is frictionless. This distinction has a profound impact on your retention metrics and lifetime revenue per subscriber.</p>
    </div>

    <div class="rc-subhead">How the Pause Lifecycle Works</div>

    <div class="rc-step">
      <div class="rc-sbadge">1</div>
      <div>
        <h4 style="margin:0 0 8px;">Pause Is Initiated</h4>
        <p style="margin:0;">A pause can be triggered in multiple ways: by the subscriber through a self-service hosted page, by your team through the Recurly Admin Console, or programmatically via the Recurly API. You specify a <strong>remaining billing cycles</strong> value, which tells Recurly how many renewal periods to skip before automatically resuming.</p>
      </div>
    </div>

    <div class="rc-step">
      <div class="rc-sbadge">2</div>
      <div>
        <h4 style="margin:0 0 8px;">Current Period Completes</h4>
        <p style="margin:0;">Importantly, the pause does not take effect immediately mid-cycle. The subscriber continues to have access through the end of their current billing period. Once that period expires, the subscription transitions into the <strong>paused</strong> state.</p>
      </div>
    </div>

    <div class="rc-step">
      <div class="rc-sbadge">3</div>
      <div>
        <h4 style="margin:0 0 8px;">Subscription Enters Paused State</h4>
        <p style="margin:0;">While paused, Recurly will not generate any invoices for that subscription. The subscriber's account, plan details, add-ons, and stored payment methods all remain intact. No dunning cycles are triggered.</p>
      </div>
    </div>

    <div class="rc-step">
      <div class="rc-sbadge">4</div>
      <div>
        <h4 style="margin:0 0 8px;">Automatic Resumption</h4>
        <p style="margin:0;">When the specified number of paused cycles have elapsed, Recurly automatically resumes the subscription. A new invoice is generated, the stored payment method is charged, and the subscriber's billing cycle continues as if they'd never left.</p>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Pair Pause with Cancel-Save Flows</strong>
      <p style="margin:8px 0 0;">Recurly's Pause feature is most powerful when integrated into your cancel-save flows. When a subscriber clicks "Cancel," present pause as an alternative before they finalize. This intercept can convert a significant percentage of would-be cancellations into temporary pauses.</p>
    </div>
  </div>

  <div class="rc-sec-nav">
    <span style="color:#807D73; font-weight:600;">● Page 1 of 7</span>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits" class="rc-btn-next">Next: Why Use It? →</a>
  </div>
</div>
`}</HTMLBlock>

<br />
