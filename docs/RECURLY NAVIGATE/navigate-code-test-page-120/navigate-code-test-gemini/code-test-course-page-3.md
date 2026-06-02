---
title: Code Test Course Page 3
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
.rc-usecase{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);margin-bottom:20px;overflow:hidden}
.rc-usecase-header{background:var(--offblack);padding:18px 24px;display:flex;align-items:center;gap:16px}
.rc-usecase-num{width:36px;height:36px;border-radius:10px;background:var(--yellow);color:var(--offblack);font-weight:800;font-size:16px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-usecase-header h3{font-size:1rem;font-weight:700;color:var(--offwhite);margin:0}
.rc-usecase-header p{font-size:.8rem;color:var(--lightgray);margin:0}
.rc-usecase-body{padding:24px}
.rc-usecase-grid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:12px;margin-top:16px}
.rc-uc-item{background:var(--brightgray);border-radius:10px;padding:14px}
.rc-uc-item h5{font-size:.82rem;font-weight:700;color:var(--offblack);margin:0 0 4px;text-transform:uppercase;letter-spacing:.5px}
.rc-uc-item p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
.rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
.rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
.rc-decision{background:var(--offblack);border-radius:16px;padding:28px;margin-bottom:24px}
.rc-decision h3{color:var(--yellow);font-size:1rem;font-weight:700;margin:0 0 16px}
.rc-decision-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.rc-dec-item{background:rgba(255,255,255,.06);border-radius:12px;padding:16px}
.rc-dec-item h5{color:var(--yellow);font-size:.82rem;font-weight:700;margin:0 0 6px}
.rc-dec-item p{color:var(--lightgray);font-size:.8rem;line-height:1.5;margin:0}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
.rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
.rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
@media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-usecase-grid,.rc-decision-grid{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-use-cases"><span class="rc-snum">2</span>Use Cases</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-webhooks"><span class="rc-snum">3</span>Webhooks</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage"><span class="rc-snum">4</span>Recurly Engage</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-best-practices"><span class="rc-snum">5</span>Best Practices</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-pitch"><span class="rc-snum">6</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🗂️</div>
      <div>
        <h2>Use cases & when to deploy</h2>
        <p>Payment banners aren't one-size-fits-all. The right trigger, message, and timing depends on the subscriber's situation. Here are the five key scenarios where banners deliver the most impact.</p>
      </div>
    </div>

    <div class="rc-usecase">
      <div class="rc-usecase-header">
        <div class="rc-usecase-num">1</div>
        <div><h3>Expiring Card</h3><p>Card on file is approaching its expiration date</p></div>
      </div>
      <div class="rc-usecase-body">
        <p style="font-size:.88rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">This is the highest-volume use case and the easiest win. When a subscriber's card is 30–60 days from expiry, show a banner prompting them to update before their next renewal. This is entirely preventable churn — the subscriber wants to stay, they just haven't thought about their card yet.</p>
        <div class="rc-usecase-grid">
          <div class="rc-uc-item"><h5>When to fire</h5><p>30 days before expiration; remind again at 14 days if not updated</p></div>
          <div class="rc-uc-item"><h5>Suggested message</h5><p>"Your card ending in XXXX expires soon. Update now to keep your subscription active."</p></div>
          <div class="rc-uc-item"><h5>Webhook event</h5><p><code>billing_info_expiration_warning</code></p></div>
        </div>
      </div>
    </div>

    <div class="rc-usecase">
      <div class="rc-usecase-header">
        <div class="rc-usecase-num">2</div>
        <div><h3>Failed Payment / Past Due</h3><p>A renewal attempt has already been declined</p></div>
      </div>
      <div class="rc-usecase-body">
        <p style="font-size:.88rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">When a payment fails and the subscriber logs back in, show a banner immediately. This is your best recovery moment — they're already engaged and motivated to keep access. A clear, urgent but non-alarming banner with a direct link to update billing info converts at the highest rate of any scenario.</p>
        <div class="rc-usecase-grid">
          <div class="rc-uc-item"><h5>When to fire</h5><p>On the very next login after a failed payment or past-due status</p></div>
          <div class="rc-uc-item"><h5>Suggested message</h5><p>"There was an issue with your last payment. Update your billing info to keep your access uninterrupted."</p></div>
          <div class="rc-uc-item"><h5>Webhook event</h5><p><code>payment_declined</code> / <code>subscription_past_due</code></p></div>
        </div>
      </div>
    </div>

    <div class="rc-usecase">
      <div class="rc-usecase-header">
        <div class="rc-usecase-num">3</div>
        <div><h3>Annual Plan Pre-Renewal</h3><p>High-value subscriber approaching their annual renewal date</p></div>
      </div>
      <div class="rc-usecase-body">
        <p style="font-size:.88rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Annual subscribers generate 50–60% more revenue per user than monthly subscribers — and their renewal moment is the highest-risk moment in their lifecycle. A banner 30 days before annual renewal ensures their card is current and primes them for a successful charge. Annual renewals only have a 23.3% recovery rate once they fail, so prevention is critical.</p>
        <div class="rc-usecase-grid">
          <div class="rc-uc-item"><h5>When to fire</h5><p>30 days before the annual renewal date for all active annual subscribers</p></div>
          <div class="rc-uc-item"><h5>Suggested message</h5><p>"Your annual plan renews on [date]. Confirm your payment method is up to date to avoid any interruption."</p></div>
          <div class="rc-uc-item"><h5>Webhook event</h5><p><code>subscription_renewal_upcoming</code></p></div>
        </div>
      </div>
    </div>

    <div class="rc-usecase">
      <div class="rc-usecase-header">
        <div class="rc-usecase-num">4</div>
        <div><h3>Post-Dunning Recovery</h3><p>Subscriber logs in after dunning has begun but not yet completed</p></div>
      </div>
      <div class="rc-usecase-body">
        <p style="font-size:.88rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">If a subscriber is in an active dunning cycle — they've received emails but haven't updated yet — a banner on their next login reinforces the message across channels. Some subscribers ignore emails but respond immediately when prompted inside the product. This is your second-chance moment.</p>
        <div class="rc-usecase-grid">
          <div class="rc-uc-item"><h5>When to fire</h5><p>Any login during an active dunning cycle where billing info is still unresolved</p></div>
          <div class="rc-uc-item"><h5>Suggested message</h5><p>"We still haven't been able to process your payment. Update your billing info now to restore full access."</p></div>
          <div class="rc-uc-item"><h5>Webhook event</h5><p><code>subscription_past_due</code> with active dunning state</p></div>
        </div>
      </div>
    </div>

    <div class="rc-usecase">
      <div class="rc-usecase-header">
        <div class="rc-usecase-num">5</div>
        <div><h3>Payment Method Change Needed</h3><p>Subscriber's bank or card type has changed</p></div>
      </div>
      <div class="rc-usecase-body">
        <p style="font-size:.88rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Sometimes Account Updater returns a "closed account" or "contact cardholder" status — meaning the card cannot be automatically updated. The subscriber has closed their account, switched banks, or changed card types. In these cases, only the subscriber can resolve it. A banner prompts them to add a new payment method before the next renewal attempt.</p>
        <div class="rc-usecase-grid">
          <div class="rc-uc-item"><h5>When to fire</h5><p>After Account Updater returns a non-updatable status on an upcoming renewal</p></div>
          <div class="rc-uc-item"><h5>Suggested message</h5><p>"We weren't able to update your payment details automatically. Please add a new payment method to continue your subscription."</p></div>
          <div class="rc-uc-item"><h5>Webhook event</h5><p><code>billing_info_updated</code> with closed/contact status</p></div>
        </div>
      </div>
    </div>

    <div class="rc-decision">
      <h3>🧭 Which use case is right for your subscribers?</h3>
      <div class="rc-decision-grid">
        <div class="rc-dec-item"><h5>Monthly subscribers</h5><p>Focus on failed payment and post-dunning recovery banners. Monthly plans have higher volatility but better recoverability (53%).</p></div>
        <div class="rc-dec-item"><h5>Annual subscribers</h5><p>Prioritise pre-renewal and expiring card banners. Annual renewals are higher risk once they fail — prevention is worth far more than recovery.</p></div>
        <div class="rc-dec-item"><h5>High-LTV subscribers</h5><p>Deploy banners earlier and with more urgency. The cost of losing a high-value subscriber is significantly higher than the friction of a well-timed prompt.</p></div>
        <div class="rc-dec-item"><h5>Re-engaged or returning subscribers</h5><p>Use post-dunning recovery banners. Subscribers who have previously churned and returned are highly motivated — don't let a payment issue send them back out the door.</p></div>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Pair banners with Account Updater for maximum coverage</h4><p>Deploy Account Updater first to silently fix eligible card issues. Then use payment banners as the escalation layer — they fire when AU can't resolve the issue and a human action is required. This two-layer approach covers the full range of involuntary churn scenarios.</p></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-why">← Why Use It?</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-webhooks">Next: Webhooks →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-engage" target="_blank" rel="noopener noreferrer">✨ Recurly Engage Docs</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/webhooks" target="_blank" rel="noopener noreferrer">🔗 Recurly Webhooks Docs</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
  </div>
</div>
`}</HTMLBlock>

<br />
