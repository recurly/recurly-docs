---
title: Pause Subscription - API Test
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
/* 1. MASTER PAGE OVERRIDES - Forces the entire ReadMe page color */
body, .theme-doc, .main-content { background-color: #F5F5F0 !important; }

.rc-guide { font-family: "Inter", -apple-system, sans-serif; color: #0D0D0B; max-width: 900px; margin: 0 auto; background: #F5F5F0; }

/* 2. HERO SECTION - Black background with topo texture */
.rc-hero { background: #0D0D0B; color: white; padding: 48px 40px; border-radius: 16px 16px 0 0; text-align: center; position: relative; overflow: hidden; }
.rc-hero-topo { position: absolute; top: 0; left: 0; right: 0; bottom: 0; background-image: url('https://drive.google.com/thumbnail?sz=w1000&id=1gLpfq5s-rR8anlQVCGhpNTPzPopYdPEd'); opacity: 0.1; pointer-events: none; }
.rc-badge { background: #FFD706; color: #0D0D0B; padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; position: relative; z-index: 1; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; position: relative; z-index: 1; }
.rc-subtitle { color: #CCC9B8; font-size: 16px; margin: 0; position: relative; z-index: 1; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; background: #FF9D88; color: #0D0D0B; position: relative; z-index: 1; }
.rc-stats { display: flex; justify-content: center; gap: 32px; margin-top: 24px; position: relative; z-index: 1; }
.rc-stat { color: #CCC9B8; font-size: 14px; }
.rc-stat-num { color: #FFD706; font-weight: 700; font-size: 20px; display: block; }

/* 3. NAVIGATION - Tan bar with numbered tabs */
.rc-nav { display: flex; background: #F1EFE3; padding: 0; overflow-x: auto; border-bottom: 2px solid #CCC9B8; }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: #807D73; font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: #0D0D0B; background: #F5F5F0; }
.rc-nav a.is-active { color: #0D0D0B; font-weight: 600; border-bottom-color: #FFD706; background: #F5F5F0; }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: #CCC9B8; color: #807D73; display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: #FFD706; color: #0D0D0B; }

/* 4. CONTENT CARDS - Tan cards on gray background */
.rc-sec { padding: 40px; background: #F5F5F0; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: #FFD706; border-radius: 12px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
.rc-card { background: #F1EFE3; border-radius: 12px; padding: 28px; margin-bottom: 20px; border: 1px solid #CCC9B8; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: #32312D; line-height: 1.7; margin: 0 0 12px; font-size: 15px; }

.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: #0D0D0B; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: #F1EFE3; border-radius: 12px; padding: 20px; margin-bottom: 16px; border: 1px solid #CCC9B8; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: #FFD706; color: #0D0D0B; display: flex; align-items: center; justify-content: center; font-weight: 700; flex-shrink: 0; }

.rc-2col { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 20px 0; }
.rc-wi { background: #F1EFE3; border-radius: 12px; padding: 24px; text-align: center; border: 1px solid #CCC9B8; }
.rc-wi h4 { font-size: 16px; margin: 12px 0 8px; font-weight: 600; }
.rc-wi p { font-size: 13px; color: #807D73; margin: 0; }

.rc-checklist { background: #F1EFE3; border-radius: 12px; padding: 24px; margin: 20px 0; border: 1px solid #CCC9B8; }
.rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
.rc-cb { width: 18px; height: 18px; border-radius: 4px; border: 2px solid #CCC9B8; flex-shrink: 0; margin-top: 3px; background: white; }

.rc-tip { border-left: 4px solid #FFD706; background: #F1EFE3; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 24px 0; border: 1px solid #CCC9B8; border-left-width: 4px; border-left-color: #FFD706; }

.rc-sec-nav { display: flex; justify-content: space-between; padding: 0 40px 40px; align-items: center; background: #F5F5F0; }
.rc-btn-next { background: #FFD706; color: #0D0D0B; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; border: 1px solid #FFD706; }

.rc-link-sec { padding: 32px 40px; background: #F1EFE3; border-top: 1px solid #CCC9B8; border-radius: 0 0 16px 16px; }
.rc-link-btn { display: inline-flex; align-items: center; background: #ffffff; border: 1px solid #CCC9B8; padding: 10px 20px; border-radius: 8px; text-decoration: none; color: #0D0D0B; font-size: 14px; font-weight: 500; margin: 4px; }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-hero-topo"></div>
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1MSOWNl7V9UgaV9oQHU-mMirnV02uQpjp" alt="Retain stage" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;position:relative;z-index:1;" />
    <span class="rc-badge">Subscriptions</span>
    <h1>Pause, Not Cancel</h1>
    <p class="rc-subtitle">Decrease voluntary churn by offering subscribers a pause option instead of forcing a binary stay-or-cancel decision.</p>
    <div class="rc-flywheel-badge">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">25</span> min read</div>
    </div>
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
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1UJTHa-pq_K0ParoEOE7Mh5gzSKX73xzR" alt="package-check" width="28" height="28" /></div>
      <div>
        <h2 style="margin:0; font-size:24px;">What Is Pause Subscriptions?</h2>
        <p style="margin:4px 0 0; color:#807D73;">Understand how Recurly's Pause feature works and why it's a powerful tool in your retention toolkit.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>The Pause Concept in a Nutshell</h3>
      <p>Recurly's Pause Subscriptions feature lets you temporarily halt a subscriber's billing cycle without canceling their subscription. Instead of losing a subscriber entirely when they need a break—whether due to travel, seasonal usage patterns, budget constraints, or simply wanting time away—you give them a middle option. The subscription enters a paused state: no invoices are generated, no charges occur, and the subscriber's account remains intact.</p>
      <p>Think of it this way: cancellation is a door that's hard to reopen. A pause is a bookmark—the subscriber's place is held, their payment method stays on file, and their return path is frictionless. This distinction has a profound impact on your retention metrics and lifetime revenue per subscriber.</p>
    </div>

    <div class="rc-subhead">How the Pause Lifecycle Works</div>

    <div class="rc-step">
      <div class="rc-sbadge">1</div>
      <div style="flex:1;">
        <h4 style="margin:0 0 4px; font-size:16px;">Pause Is Initiated</h4>
        <p style="margin:0; font-size:14px; color:#32312D;">A pause can be triggered by the subscriber via self-service, by your team in the Admin Console, or via the Recurly API. You specify a <strong>remaining billing cycles</strong> value to skip.</p>
      </div>
    </div>

    <div class="rc-step">
      <div class="rc-sbadge">2</div>
      <div style="flex:1;">
        <h4 style="margin:0 0 4px; font-size:16px;">Current Period Completes</h4>
        <p style="margin:0; font-size:14px; color:#32312D;">The pause starts at the end of the current billing period—ensuring the subscriber gets the full value of what they've paid for without needing refunds.</p>
      </div>
    </div>

    <div class="rc-step">
      <div class="rc-sbadge">3</div>
      <div style="flex:1;">
        <h4 style="margin:0 0 4px; font-size:16px;">Subscription Enters Paused State</h4>
        <p style="margin:0; font-size:14px; color:#32312D;">While paused, Recurly will not generate any invoices. The subscriber's account, plan details, coupons, and payment methods all remain intact.</p>
      </div>
    </div>

    <div class="rc-step">
      <div class="rc-sbadge">4</div>
      <div style="flex:1;">
        <h4 style="margin:0 0 4px; font-size:16px;">Automatic Resumption</h4>
        <p style="margin:0; font-size:14px; color:#32312D;">When the specified cycles elapse, Recurly automatically resumes the subscription and generates a new invoice. No manual action is required.</p>
      </div>
    </div>

    <div class="rc-subhead">Pause vs. Cancel: A Critical Distinction</div>

    <div class="rc-2col">
      <div class="rc-wi">
        <h4 style="font-size:16px; margin:0 0 8px;">⏸️ Pause</h4>
        <p style="font-size:13px; color:#807D73; margin:0;">Billing stops temporarily. Account stays active. Payment method retained. Automatic resumption. Frictionless return.</p>
      </div>
      <div class="rc-wi">
        <h4 style="font-size:16px; margin:0 0 8px;">❌ Cancel</h4>
        <p style="font-size:13px; color:#807D73; margin:0;">Subscription terminates. Subscriber must re-signup. Reacquisition cost is high. Stored data may be lost.</p>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Pair Pause with Cancel-Save Flows</strong>
      <p>When a subscriber clicks "Cancel," present pause as an alternative before they finalize. This intercept can convert would-be cancellations into temporary pauses.</p>
    </div>

    <div class="rc-checklist">
      <h3 style="font-size:18px; margin:0 0 16px;">Quick Concepts to Remember</h3>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Pause halts billing but keeps the subscription record fully intact</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">The current billing period completes before the pause takes effect</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Resumption is automatic—no action needed from the subscriber</label></div>
    </div>
  </div>

  <div class="rc-sec-nav">
    <span style="color:#807D73; font-weight:600; font-size:14px;">● Page 1 of 7</span>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits" class="rc-btn-next">Next: Why Use It? →</a>
  </div>

  <div class="rc-link-sec">
    <h3 style="font-size:18px; margin:0 0 16px;">Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">📄 Pause Documentation</a>
    <a href="https://docs.google.com/videos/d/1pq5dvNPwOEp7mksTP7XSmPjGaebdujtXluiHpebjTKQ/edit?usp=sharing" class="rc-link-btn">🎥 Video Walkthrough</a>
  </div>
</div>
`}</HTMLBlock>

<br />
