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
.rc-tip { border-left: 4px solid #FFD706; background-color: #FFFDF2; padding: 24px; border-radius: 0 12px 12px 0; margin: 24px 0; }
.rc-warning { border-left: 4px solid #FF8200; background-color: #FFF8F0; padding: 24px; border-radius: 0 12px 12px 0; margin: 24px 0; }
.rc-sec-nav { display: flex; justify-content: space-between; align-items: center; margin-top: 48px; padding: 24px 40px; border-top: 1px solid #CCC9B8; background: #FFFFFF; }
.rc-btn-next { background-color: #FFD706; color: #0D0D0B; padding: 12px 28px; border-radius: 10px; font-weight: 700; text-decoration: none; border: 1px solid #FFD706; }
.rc-btn-prev { color: #32312D; text-decoration: none; font-weight: 600; }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-hero-topo"></div>
    <img src="Retain-icon-white.png" alt="Retain" class="rc-flywheel-icon" /> 
    <div class="rc-badge">Subscriptions</div>
    <h1>Pause, Not Cancel</h1>
    <p>Success with Pause requires more than a toggle. Learn the business logic and guardrails that protect your revenue.</p>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions"><span class="rc-snum">1</span> What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits"><span class="rc-snum">2</span> Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-considerations" class="rc-active"><span class="rc-snum">3</span> Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-fit"><span class="rc-snum">4</span> When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-enable"><span class="rc-snum">5</span> How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-data"><span class="rc-snum">6</span> Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-use-case"><span class="rc-snum">7</span> Pitch to Leadership</a>
  </nav>

  <div style="padding: 0 40px 40px;">
    <div class="rc-sec-header">
      <div class="rc-sec-icon"><img src="package-check.svg" alt="Considerations" /></div>
      <div>
        <h2 style="margin:0; font-size:24px;">Things to Consider</h2>
        <p style="margin:4px 0 0; color:#807D73;">Before enabling Pause, ensure your billing logic and communication plans are ready.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 style="margin-top:0;">Billing Logic & Timing</h3>
      <p>The most important consideration is <strong>when</strong> the pause begins. In Recurly, a pause is "scheduled" to start at the end of the current billing cycle. This prevents messy mid-cycle prorations and ensures the subscriber receives the full value of the service they have already paid for.</p>
      <p>You must also decide on the <strong>duration</strong>. You can allow subscribers to pause for a specific number of billing cycles (e.g., 1, 2, or 3 months). Recurly will automatically resume billing once those cycles have passed, so you don't have to worry about manual "reactivation" tasks.</p>
    </div>

    <div class="rc-subhead">Key Operational Questions</div>

    <div class="rc-step">
      <div class="rc-sbadge">1</div>
      <div>
        <h4 style="margin:0 0 8px;">Will you allow "Indefinite" pauses?</h4>
        <p style="margin:0;">Recurly supports specific cycle counts. If a subscriber needs an indefinite break, it’s usually better to have them cancel or use a very long pause duration (e.g., 12 cycles) with a reminder strategy.</p>
      </div>
    </div>

    <div class="rc-step">
      <div class="rc-sbadge">2</div>
      <div>
        <h4 style="margin:0 0 8px;">What happens to active coupons?</h4>
        <p style="margin:0;">Pause does not "stop the clock" on a coupon’s expiration date. If a coupon is set to expire in 3 months and the subscriber pauses for 2 months, they will only have 1 month of discount remaining when they return.</p>
      </div>
    </div>

    <div class="rc-step">
      <div class="rc-sbadge">3</div>
      <div>
        <h4 style="margin:0 0 8px;">How will you notify them?</h4>
        <p style="margin:0;">A frictionless return depends on communication. We recommend sending a reminder email 3–7 days before the pause ends, letting the subscriber know their service and billing will resume shortly.</p>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Customizing the Hosted Page</strong>
      <p style="margin:8px 0 0;">If you use Recurly's Hosted Payment Pages, you can easily toggle Pause on. Use the description fields to explain <em>exactly</em> what happens when they pause, reducing support tickets and confusion.</p>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Warning: Prorated Add-ons</strong>
      <p style="margin:8px 0 0;">If a subscription has "bill-at-rest" or usage-based add-ons, those charges are typically processed at the start of the pause for the usage incurred in the final active month. Make sure your finance team is aware of this final invoice behavior.</p>
    </div>
  </div>

  <div class="rc-sec-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits" class="rc-btn-prev">← Previous</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-fit" class="rc-btn-next">Next: When Not to Use It →</a>
  </div>
</div>
`}</HTMLBlock>

<br />
