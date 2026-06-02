---
title: Code Test Course Page 4
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
.rc-event-grid{display:flex;flex-direction:column;gap:10px;margin-bottom:24px}
.rc-event{background:var(--offwhite);border-radius:12px;padding:16px 20px;border:1px solid var(--lightgray);display:flex;align-items:flex-start;gap:16px}
.rc-event-code{background:var(--offblack);color:var(--yellow);padding:6px 12px;border-radius:8px;font-size:.8rem;font-weight:700;font-family:monospace;flex-shrink:0;white-space:nowrap}
.rc-event-desc h5{font-size:.88rem;font-weight:700;color:var(--offblack);margin:0 0 3px}
.rc-event-desc p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
.rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:28px}
.rc-cl-header{padding:16px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:center;gap:10px;background:var(--offblack)}
.rc-cl-header h3{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
.rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:flex-start;gap:14px}.rc-cli:last-child{border-bottom:none}
.rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;background:#fff}
.rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}.rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
.rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
.rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
.rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start;margin-bottom:24px}
.rc-wicon{font-size:20px;flex-shrink:0}.rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
.rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
.rc-opt{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:14px;padding:18px}
.rc-opt h4{font-size:.92rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-opt p{font-size:.82rem;color:var(--gray);line-height:1.5;margin:0}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
.rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
.rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
@media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-2col{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}.rc-event{flex-direction:column}}
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
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-webhooks"><span class="rc-snum">3</span>Webhooks</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage"><span class="rc-snum">4</span>Recurly Engage</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-best-practices"><span class="rc-snum">5</span>Best Practices</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-pitch"><span class="rc-snum">6</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔗</div>
      <div>
        <h2>Payment banners via webhooks</h2>
        <p>Build custom, fully branded payment banners inside your own app by listening to Recurly webhook events. This path gives you full control over design, placement, and subscriber experience.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🧩 How this works — the plain-language version</h3>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">When something important happens in Recurly — a card expires, a payment fails, an account goes past due — Recurly fires a <strong>webhook</strong>: a real-time notification sent to a URL your team specifies. Your developers listen for these events and use them as triggers to display a payment banner inside your app, exactly when and where it's most effective.</p>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0;">This approach requires development work to build and maintain, but gives you complete control over the banner's appearance, placement, messaging, and behaviour. If you want the banner to look and feel exactly like the rest of your product, this is the path.</p>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Dev resources required:</strong> The webhook approach requires your engineering team to build the listener, the banner UI, and the update flow. If you need payment banners without any engineering lift, skip to <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage" style="color:var(--orange);font-weight:700;">Tab 4: Recurly Engage</a> — it handles all of this automatically with no code required.</p>
    </div>

    <h3 class="rc-subhead">⚡ Key webhook events for payment banners</h3>
    <div class="rc-event-grid">
      <div class="rc-event">
        <div class="rc-event-code">billing_info_expiration_warning</div>
        <div class="rc-event-desc"><h5>Card Expiring Soon</h5><p>Fires when a stored card is approaching its expiration date. Use this to trigger a proactive banner before the card expires — the easiest and highest-converting use case.</p></div>
      </div>
      <div class="rc-event">
        <div class="rc-event-code">payment_declined</div>
        <div class="rc-event-desc"><h5>Payment Declined</h5><p>Fires immediately when a payment attempt fails. Triggers your highest-urgency banner — the subscriber needs to act now to maintain access.</p></div>
      </div>
      <div class="rc-event">
        <div class="rc-event-code">subscription_past_due</div>
        <div class="rc-event-desc"><h5>Subscription Past Due</h5><p>Fires when a subscription enters past-due status after a failed renewal. Use alongside dunning to reinforce the message in-session.</p></div>
      </div>
      <div class="rc-event">
        <div class="rc-event-code">billing_info_updated</div>
        <div class="rc-event-desc"><h5>Billing Info Updated</h5><p>Fires when Account Updater returns a result. If the status is "closed" or "contact cardholder", use this as a trigger for a banner asking the subscriber to add a new payment method.</p></div>
      </div>
      <div class="rc-event">
        <div class="rc-event-code">subscription_renewal_upcoming</div>
        <div class="rc-event-desc"><h5>Renewal Upcoming</h5><p>Fires ahead of an upcoming renewal. Ideal for annual subscribers — prompt them to verify their payment method is current before the high-value charge.</p></div>
      </div>
    </div>

    <h3 class="rc-subhead">🗺️ What to ask your dev team to build</h3>
    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Set up a webhook endpoint</h3><p>Your team creates a URL on your server that Recurly can send event notifications to. This endpoint receives the JSON payload from Recurly whenever a relevant event fires. Share the Recurly Webhooks documentation (linked below) with your developers as the technical reference for this step.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Configure webhook notifications in Recurly</h3><p>In your Recurly admin, navigate to <strong>Integrations → Webhooks</strong> and add your endpoint URL. Select the specific events you want to listen for from the list above. Recurly will begin sending notifications to your endpoint immediately.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Parse the event and identify the subscriber</h3><p>When your endpoint receives a webhook, your app reads the event type and the associated account code. This tells you which subscriber is affected and what the issue is — the information you need to decide whether and how to show a banner.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>Store a flag for the subscriber's session</h3><p>Your backend sets a flag or state for that subscriber (e.g., in your database or session store) indicating that a payment banner should be shown on their next login. This ensures the banner fires at the right moment — when they're actively in your app — rather than being triggered asynchronously.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">5</div><div><h3>Render the banner in your app</h3><p>When the subscriber logs in, your frontend checks for the flag and renders the appropriate banner. The banner should include a clear message, the reason for the prompt, and a direct link or modal to update billing info. Design it to match your product's UI.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">6</div><div><h3>Handle the update and clear the banner</h3><p>When the subscriber updates their payment method, Recurly fires a confirmation event. Your app listens for this, clears the flag, and dismisses the banner. The subscriber's experience is seamless — issue resolved, no disruption to their session.</p></div></div>
    </div>

    <h3 class="rc-subhead">🔍 What your team needs to build this</h3>
    <div class="rc-2col">
      <div class="rc-opt"><h4>🖥️ Backend</h4><p>A webhook endpoint that can receive and parse Recurly JSON payloads, authenticate the request, and update your subscriber state or database accordingly.</p></div>
      <div class="rc-opt"><h4>🎨 Frontend</h4><p>A banner component in your app UI that conditionally renders based on the subscriber's payment status flag. Typically a dismissible notification bar or modal.</p></div>
      <div class="rc-opt"><h4>🔐 Webhook Security</h4><p>Recurly signs webhook payloads with a secret key. Your team should validate this signature to ensure the request is genuinely from Recurly.</p></div>
      <div class="rc-opt"><h4>🔁 Update Flow</h4><p>A path from the banner to where the subscriber can update their billing info — either a hosted page, an embedded form, or a redirect to your billing settings.</p></div>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header"><h3>Pre-build checklist for your dev team</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Webhook endpoint URL created and ready to receive POST requests<span>Your team will register this URL in Recurly admin</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Webhook notifications configured in Recurly admin<span>Integrations → Webhooks → add endpoint and select events</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Webhook signature validation implemented<span>Verify the X-Recurly-Signature header to authenticate requests</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Subscriber state flag logic built in your backend<span>Stores which subscribers need a banner shown on next login</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Banner UI component built in your frontend<span>Dismissible, clearly branded, with a direct CTA to update billing</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Update flow tested end-to-end in a staging environment<span>Confirm banner fires, subscriber updates, banner clears correctly</span></div></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Want this without the build work?</h4><p>If your team doesn't have the bandwidth to build a custom webhook integration right now, Recurly Engage delivers payment banners out of the box — no development required. Head to Tab 4 to see how it works.</p></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-use-cases">← Use Cases</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage">Next: Recurly Engage →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/webhooks" target="_blank" rel="noopener noreferrer">🔗 Recurly Webhooks Documentation</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/webhook-notifications" target="_blank" rel="noopener noreferrer">📋 Webhook Event Reference</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
  </div>
</div>
`}</HTMLBlock>

<br />
