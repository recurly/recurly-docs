---
title: Code Test Course Page 5
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
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
.rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack);box-shadow:0 2px 10px rgba(255,215,6,.25)}
.rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
.rc-sec{margin-bottom:56px}.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
.rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
.rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}.rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
.rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
.rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
.rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
.rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
.rc-sbadge{width:38px;height:38px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
.rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
.rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray);text-align:center}
.rc-wi-icon{font-size:30px;margin-bottom:10px}.rc-wi h4{font-size:.88rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-wi p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
.rc-engage-callout{background:linear-gradient(135deg,var(--offblack) 0%,#1a1a1a 100%);border-radius:16px;padding:32px;margin-bottom:24px;border:1px solid var(--yellow)}
.rc-engage-callout h3{color:var(--yellow);font-size:1.1rem;font-weight:800;margin:0 0 10px;text-transform:uppercase;letter-spacing:1px}
.rc-engage-callout p{color:var(--lightgray);font-size:.92rem;line-height:1.6;margin:0 0 20px}
.rc-engage-callout a{display:inline-flex;align-items:center;gap:8px;background:var(--yellow);color:var(--offblack);padding:12px 24px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
.rc-trigger-grid{display:flex;flex-direction:column;gap:10px;margin-bottom:24px}
.rc-trigger{background:var(--offwhite);border-radius:12px;padding:16px 20px;border:1px solid var(--lightgray);display:flex;align-items:flex-start;gap:16px}
.rc-trigger-icon{font-size:22px;flex-shrink:0}
.rc-trigger h5{font-size:.88rem;font-weight:700;color:var(--offblack);margin:0 0 3px}
.rc-trigger p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
.rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
.rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
.rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:28px}
.rc-cl-header{padding:16px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:center;gap:10px;background:var(--offblack)}
.rc-cl-header h3{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
.rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:flex-start;gap:14px}.rc-cli:last-child{border-bottom:none}
.rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;background:#fff}
.rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}.rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
.rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
.rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
@media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-3col{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">🔔 Subscriber Experience</div>
    <h1>Payment Banners</h1>
    <p>Meet your subscribers where they are — with in-app prompts that turn at-risk payments into seamless renewals, before they ever become churn.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">3x</div><div class="rc-lbl">More spend from engaged subscribers</div></div>
      <div><div class="rc-num">40%</div><div class="rc-lbl">Of churn is involuntary</div></div>
      <div><div class="rc-num">337%</div><div class="rc-lbl">Lift when proactive retention tools are used</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners">Payment Banners</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-why"><span class="rc-snum">1</span>Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-use-cases"><span class="rc-snum">2</span>Use Cases</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-webhooks"><span class="rc-snum">3</span>Webhooks</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage"><span class="rc-snum">4</span>Recurly Engage</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-best-practices"><span class="rc-snum">5</span>Best Practices</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-pitch"><span class="rc-snum">6</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">✨</div>
      <div>
        <h2>Payment banners via Recurly Engage</h2>
        <p>The no-code path to payment banners. Recurly Engage automatically detects at-risk subscribers and surfaces banners on your hosted pages and subscriber portal — zero engineering required.</p>
      </div>
    </div>

    <div class="rc-engage-callout">
      <h3>✨ What is Recurly Engage?</h3>
      <p>Recurly Engage is the subscriber experience layer built directly into Recurly. It monitors your subscriber base in real time, identifies at-risk accounts, and automatically triggers targeted in-session experiences — including payment banners — without any code from your team. Configure triggers, messaging, and timing from a simple dashboard, and let Engage do the rest.</p>
      <a href="https://docs.recurly.com/recurly-engage" target="_blank" rel="noopener noreferrer">Explore Recurly Engage Docs →</a>
    </div>

    <h3 class="rc-subhead">⚡ Why choose Engage over webhooks?</h3>
    <div class="rc-3col">
      <div class="rc-wi"><div class="rc-wi-icon">🚀</div><h4>No Engineering Lift</h4><p>Zero development work required. Configure and launch payment banners directly from the Recurly dashboard — no backend, no frontend build, no deployment.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">⏱️</div><h4>Fast Time to Value</h4><p>Go from setup to live banners in a single session. While a webhook implementation can take weeks, Engage banners can be active today.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🎯</div><h4>Built-In Intelligence</h4><p>Engage uses Recurly's subscriber data to automatically identify who needs a banner, when to show it, and how often — without manual segmentation.</p></div>
    </div>

    <h3 class="rc-subhead">🔔 Available trigger options in Recurly Engage</h3>
    <div class="rc-trigger-grid">
      <div class="rc-trigger"><span class="rc-trigger-icon">📅</span><div><h5>Expiring Card</h5><p>Automatically detects cards approaching expiration and shows a banner prompting the subscriber to update — configurable from 60 days to 7 days before expiry.</p></div></div>
      <div class="rc-trigger"><span class="rc-trigger-icon">❌</span><div><h5>Failed Payment</h5><p>Fires immediately after a payment decline, surfacing an urgent banner on the subscriber's next session to resolve the issue before dunning escalates.</p></div></div>
      <div class="rc-trigger"><span class="rc-trigger-icon">⏰</span><div><h5>Past Due Status</h5><p>Triggers when a subscription enters past-due state, reinforcing your dunning emails with an in-session prompt for subscribers who haven't updated via email.</p></div></div>
      <div class="rc-trigger"><span class="rc-trigger-icon">🔄</span><div><h5>Renewal Upcoming</h5><p>Proactively prompts subscribers — particularly annual plan holders — to verify their payment method is current before a high-value renewal charge.</p></div></div>
    </div>

    <h3 class="rc-subhead">🗺️ How to set up a payment banner in Recurly Engage</h3>
    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Access Recurly Engage in your dashboard</h3><p>Navigate to <strong>Engage</strong> in your Recurly admin. From the Engage dashboard you'll see your active campaigns, subscriber risk signals, and the option to create a new experience.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Create a new payment banner campaign</h3><p>Select <strong>New Campaign → Payment Banner</strong>. Choose the trigger event that should activate the banner — expiring card, failed payment, past due, or upcoming renewal. You can create separate campaigns for each trigger type to customise messaging per scenario.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Customise your message and timing</h3><p>Write the banner headline and body copy that will appear to subscribers. Set how far in advance of the trigger the banner should appear (e.g., 30 days before expiry) and configure frequency capping so the same subscriber isn't shown the banner on every single session.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>Select where the banner renders</h3><p>Choose whether the banner displays on your Recurly-hosted subscriber portal, your hosted payment pages, or both. Engage handles the rendering automatically — no changes to your app code required.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">5</div><div><h3>Review and activate</h3><p>Preview the banner experience, confirm your trigger and audience settings, then activate the campaign. Engage immediately begins monitoring your subscriber base and will surface the banner to qualifying subscribers on their next session.</p></div></div>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header"><h3>Engage setup checklist</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Recurly Engage is active on your account<span>Contact your CSM or support@recurly.com if you're unsure</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Campaign created for expiring card trigger<span>Recommended: set to fire 30 days before expiry with a 14-day reminder</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Campaign created for failed payment trigger<span>Fires on next login after a decline — your highest-urgency scenario</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Frequency cap configured<span>Recommended: no more than once per 3–5 sessions to avoid subscriber fatigue</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Banner copy reviewed for tone and clarity<span>Helpful and friendly, not alarming — see Best Practices tab for messaging guidance</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Campaign activated and monitoring confirmed<span>Check the Engage dashboard after 24–48 hours to see impressions begin</span></div></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Not yet on Recurly Engage?</h4><p>If Recurly Engage isn't currently part of your plan, talk to your CSM or join a Global Office Hours session to learn more. Head to Tab 6 — Pitch to Leadership — for a ready-made business case you can use to get internal approval for Engage.</p></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-webhooks">← Webhooks</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-best-practices">Next: Best Practices →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-engage" target="_blank" rel="noopener noreferrer">✨ Recurly Engage Docs</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
  </div>
</div>
`}</HTMLBlock>

<br />
