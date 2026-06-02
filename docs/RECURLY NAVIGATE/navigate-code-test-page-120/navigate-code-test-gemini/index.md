---
title: Code Test Course
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
.rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
.rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray);text-align:center}
.rc-wi-icon{font-size:30px;margin-bottom:10px}.rc-wi h4{font-size:.88rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-wi p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
.rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
.rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
.rc-sbadge{width:38px;height:38px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
.rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
.rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
.rc-compare{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
.rc-compare-card{border-radius:14px;padding:24px;border:1px solid var(--lightgray)}
.rc-compare-card.webhook{background:var(--offwhite);border-top:4px solid var(--orange)}
.rc-compare-card.engage{background:var(--offwhite);border-top:4px solid var(--yellow)}
.rc-compare-card h4{font-size:.95rem;font-weight:700;margin:0 0 12px;color:var(--offblack)}
.rc-compare-card ul{margin:0;padding-left:18px;font-size:.85rem;color:var(--gray);line-height:1.8}
.rc-tag{display:inline-block;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;margin-bottom:12px}
.rc-tag-orange{background:var(--orange);color:#fff}
.rc-tag-yellow{background:var(--yellow);color:var(--offblack)}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
.rc-btn-prev,.rc-btn-disabled{border:1px solid var(--lightgray)}
.rc-btn-prev{background:#fff;color:var(--darkgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
.rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
.rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
@media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-3col,.rc-compare{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners">Payment Banners</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-why"><span class="rc-snum">1</span>Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-use-cases"><span class="rc-snum">2</span>Use Cases</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-webhooks"><span class="rc-snum">3</span>Webhooks</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage"><span class="rc-snum">4</span>Recurly Engage</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-best-practices"><span class="rc-snum">5</span>Best Practices</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-pitch"><span class="rc-snum">6</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔔</div>
      <div>
        <h2>What are Payment Banners?</h2>
        <p>In-app and on-page notifications that prompt subscribers to update their payment method at exactly the right moment — while they're already engaged with your product.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🧩 The simple version</h3>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">When a subscriber's card is about to expire, has already been declined, or their account is past due, the worst thing that can happen is silence. They don't know there's a problem — and you lose them without either of you intending it. That's involuntary churn, and it accounts for up to 40% of all subscription losses.</p>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0;">Payment Banners solve this by surfacing a targeted, in-session notification — inside your app, on your subscriber portal, or on your hosted pages — that asks subscribers to update their payment details right now, while they're already logged in and engaged. No waiting for an email to be opened. No hoping they click a link. Just a clear, timely prompt at the highest-intent moment possible.</p>
    </div>

    <h3 class="rc-subhead">💡 How payment banners differ from dunning emails</h3>
    <div class="rc-3col">
      <div class="rc-wi"><div class="rc-wi-icon">📧</div><h4>Dunning Emails</h4><p>Sent after a payment fails. Relies on the subscriber opening their inbox, reading the email, and clicking through to update. Reactive and easy to miss.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🔔</div><h4>Payment Banners</h4><p>Triggered while the subscriber is actively using your product. Catches them in the moment with the highest intent to act. Proactive and impossible to ignore.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🔄</div><h4>Together</h4><p>Banners and dunning emails are complementary, not competing. Banners catch in-session users; emails catch everyone else. Use both for maximum coverage.</p></div>
    </div>

    <h3 class="rc-subhead">🗺️ How it works — the subscriber journey</h3>
    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>A payment risk event occurs</h3><p>A card is approaching expiration, a renewal attempt fails, or an account becomes past due. Recurly detects this and either fires a webhook event or triggers Recurly Engage automatically.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>The subscriber logs in or visits your app</h3><p>This is the key moment. Instead of waiting for them to check their email, the payment banner surfaces immediately within their session — in your app, subscriber portal, or hosted pages.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>The banner prompts action</h3><p>A clear, friendly message explains the issue and provides a direct path to update their payment method. No friction. No hunting through account settings.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>The subscriber updates their payment</h3><p>With one click they're taken directly to their billing info. They update their card. The risk event is resolved — silently, seamlessly, with zero churn.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">5</div><div><h3>The next renewal charges successfully</h3><p>Because the payment method is now current, the subscription renews without interruption. The subscriber never experiences a service disruption. Revenue protected.</p></div></div>
    </div>

    <h3 class="rc-subhead">⚡ Two ways to implement payment banners</h3>
    <div class="rc-compare">
      <div class="rc-compare-card webhook">
        <span class="rc-tag rc-tag-orange">Dev Required</span>
        <h4>🔗 Via Webhooks</h4>
        <ul>
          <li>Recurly fires an event when a risk is detected</li>
          <li>Your dev team listens for the event</li>
          <li>They build and render the banner in your app</li>
          <li>Full control over design and placement</li>
          <li>Best for custom app experiences</li>
        </ul>
      </div>
      <div class="rc-compare-card engage">
        <span class="rc-tag rc-tag-yellow">No Code</span>
        <h4>✨ Via Recurly Engage</h4>
        <ul>
          <li>Recurly detects the risk automatically</li>
          <li>Engage surfaces the banner with no dev work</li>
          <li>Configure triggers, messaging, and timing in-app</li>
          <li>Works on hosted pages and subscriber portal</li>
          <li>Best for fast deployment with no engineering lift</li>
        </ul>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Account Updater + Payment Banners = Your Two-Layer Defense</h4><p>Account Updater silently fixes card issues behind the scenes for eligible cards. Payment Banners handle everything AU can't — they bring the subscriber into the loop when a human action is needed. Together, they cover the full spectrum of involuntary churn prevention.</p></div>
    </div>

    <div class="rc-sec-nav">
      <span class="rc-btn-disabled">🎯 Start</span>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-why">Next: Why Use It? →</a>
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