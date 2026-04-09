---
title: Pause API Test - Considerations
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
/* Master Page Background Override */
body, .theme-doc, .main-content { background-color: #F5F5F0 !important; }

.rc-guide { font-family: "Inter", -apple-system, sans-serif; color: #0D0D0B; max-width: 900px; margin: 0 auto; background: #F5F5F0; }

.rc-hero { background: #0D0D0B; color: white; padding: 48px 40px; text-align: center; position: relative; overflow: hidden; border-radius: 16px 16px 0 0; }
.rc-hero-topo { position: absolute; top: 0; left: 0; right: 0; bottom: 0; background-image: url('INSERT_TOPO_URL'); opacity: 0.1; pointer-events: none; }
.rc-badge { background: #FFD706; color: #0D0D0B; padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; position: relative; z-index: 1; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; position: relative; z-index: 1; }
.rc-subtitle { color: #CCC9B8; font-size: 16px; margin: 0; position: relative; z-index: 1; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; background: #FF9D88; color: #0D0D0B; position: relative; z-index: 1; }

.rc-nav { display: flex; background: #F1EFE3; padding: 0; overflow-x: auto; border-bottom: 2px solid #CCC9B8; }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: #807D73; font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: #0D0D0B; background: #F5F5F0; }
.rc-nav a.is-active { color: #0D0D0B; font-weight: 600; border-bottom-color: #FFD706; background: #F5F5F0; }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: #CCC9B8; color: #807D73; display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: #FFD706; color: #0D0D0B; }

.rc-sec { padding: 40px; background: #F5F5F0; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: #FFD706; border-radius: 12px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }

.rc-card { background: #F1EFE3; border-radius: 12px; padding: 28px; margin-bottom: 20px; border: 1px solid #CCC9B8; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: #32312D; line-height: 1.7; margin: 0 0 12px; font-size: 15px; }

.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: #0D0D0B; }
.rc-3col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
.rc-wi { background: #F1EFE3; border-radius: 12px; padding: 24px; text-align: center; border: 1px solid #CCC9B8; }
.rc-wi h4 { font-size: 16px; margin: 12px 0 8px; font-weight: 600; }
.rc-wi p { font-size: 13px; color: #807D73; margin: 0; }

.rc-tip { border-left: 4px solid #FFD706; background: #F1EFE3; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 24px 0; border: 1px solid #CCC9B8; border-left-width: 4px; border-left-color: #FFD706; }
.rc-warning { border-left: 4px solid #FF8200; background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 24px 0; border: 1px solid #CCC9B8; border-left-width: 4px; border-left-color: #FF8200; }

.rc-sec-nav { display: flex; justify-content: space-between; padding: 0 40px 40px; align-items: center; background: #F5F5F0; }
.rc-btn-prev { background: #F1EFE3; color: #0D0D0B; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; border: 1px solid #CCC9B8; }
.rc-btn-next { background: #FFD706; color: #0D0D0B; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; border: 1px solid #FFD706; }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-hero-topo"></div>
    <img src="INSERT_RETAIN_WHITE_URL" alt="Retain" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;position:relative;z-index:1;" />
    <span class="rc-badge">Subscriptions</span>
    <h1>Pause, Not Cancel</h1>
    <p class="rc-subtitle">Success with Pause requires more than a toggle. Learn the business logic and guardrails that protect your revenue.</p>
    <div class="rc-flywheel-badge">RETAIN</div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions"><span class="rc-snum">1</span> What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits"><span class="rc-snum">2</span> Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-considerations" class="is-active"><span class="rc-snum">3</span> Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-fit"><span class="rc-snum">4</span> When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-enable"><span class="rc-snum">5</span> How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-data"><span class="rc-snum">6</span> Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-use-case"><span class="rc-snum">7</span> Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon"><img src="INSERT_LIGHTBULB_URL" alt="lightbulb" width="28" height="28" /></div>
      <div>
        <h2>Things to Consider</h2>
        <p>Before enabling pause, understand the billing mechanics and strategic decisions that will shape your implementation.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>Billing Logic & Timing</h3>
      <p>The most important consideration is <strong>when</strong> the pause begins. In Recurly, a pause starts at the end of the current billing cycle. This prevents messy mid-cycle prorations and ensures the subscriber receives the full value of the service they've already paid for.</p>
      <p>You must also decide on the <strong>duration</strong>. Industry data suggests that subscribers who pause for 30–60 days resume at significantly higher rates than those pausing for 90+ days.</p>
    </div>

    <div class="rc-subhead">Operational Guardrails</div>
    <div class="rc-3col">
      <div class="rc-wi">
        <img src="INSERT_BELL_URL" alt="alert" style="width:28px;height:28px;margin-bottom:8px;" />
        <h4>Notifications</h4>
        <p>A frictionless return depends on communication. Send a reminder 3–7 days before the pause ends.</p>
      </div>
      <div class="rc-wi">
        <img src="INSERT_PACKAGE_URL" alt="access" style="width:28px;height:28px;margin-bottom:8px;" />
        <h4>Access Rules</h4>
        <p>Decide if paused subscribers retain limited functionality or lose access entirely until they resume.</p>
      </div>
      <div class="rc-wi">
        <img src="INSERT_CREDIT_CARD_URL" alt="payment" style="width:28px;height:28px;margin-bottom:8px;" />
        <h4>Payment Method</h4>
        <p>Cards may expire during a long pause. Use Recurly's Account Updater to keep billing details fresh.</p>
      </div>
    </div>

    <div class="rc-warning">
      <strong>⚠ Revenue Recognition Impact</strong>
      <p>Since no performance obligation is being fulfilled during the pause period, no revenue should be recognized. Coordinate with your finance team to handle paused subscription states in your accounting system.</p>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Customizing the Hosted Page</strong>
      <p>If you use Recurly's Hosted Payment Pages, you can easily toggle Pause on. Use the description fields to explain exactly what happens during a pause to reduce support tickets.</p>
    </div>
  </div>

  <div class="rc-sec-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits" class="rc-btn-prev">← Previous</a>
    <span style="color:#807D73; font-weight:600; font-size:14px;">● Page 3 of 7</span>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-fit" class="rc-btn-next">Next: When Not to Use It →</a>
  </div>
</div>
`}</HTMLBlock>

<br />