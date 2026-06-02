---
title: Code Test Course - Page 2
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
.rc-stat-grid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
.rc-stat{background:var(--offblack);border-radius:14px;padding:24px 16px;text-align:center}
.rc-stat-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}.rc-stat-label{font-size:.78rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px;margin-top:4px}
.rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:26px}
.rc-opt{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:14px;padding:18px}
.rc-oicon{font-size:22px;margin-bottom:8px}.rc-opt h4{font-size:.92rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-opt p{font-size:.82rem;color:var(--gray);line-height:1.5;margin:0}
.rc-tag{display:inline-block;margin-top:10px;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;background:var(--offblack);color:var(--yellow)}
.rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:28px}
.rc-cl-header{padding:16px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:center;gap:10px;background:var(--offblack)}
.rc-cl-header h3{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
.rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:flex-start;gap:14px}.rc-cli:last-child{border-bottom:none}
.rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;background:#fff;display:flex;align-items:center;justify-content:center;font-size:12px;color:var(--gray)}
.rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}.rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
.rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
.rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
.rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start;margin-bottom:24px}
.rc-wicon{font-size:20px;flex-shrink:0}.rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
.rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
.rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
@media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-stat-grid,.rc-2col{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-why"><span class="rc-snum">1</span>Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-use-cases"><span class="rc-snum">2</span>Use Cases</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-webhooks"><span class="rc-snum">3</span>Webhooks</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage"><span class="rc-snum">4</span>Recurly Engage</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-best-practices"><span class="rc-snum">5</span>Best Practices</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-pitch"><span class="rc-snum">6</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">📈</div>
      <div>
        <h2>Why use payment banners?</h2>
        <p>Email gets ignored. In-session banners get results. Understand the business case for catching at-risk subscribers while they're already engaged.</p>
      </div>
    </div>

    <div class="rc-stat-grid">
      <div class="rc-stat"><div class="rc-stat-num">40%</div><div class="rc-stat-label">Of all subscriber losses are involuntary — not intentional cancellations</div></div>
      <div class="rc-stat"><div class="rc-stat-num">3x</div><div class="rc-stat-label">More revenue generated by actively engaged subscribers</div></div>
      <div class="rc-stat"><div class="rc-stat-num">337%</div><div class="rc-stat-label">Increase in saves when proactive retention tools are deployed</div></div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🎯 The core problem payment banners solve</h3>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Involuntary churn is a silent killer. A subscriber's card expires, a payment fails, or an account goes past due — and unless you reach them fast, you lose a customer who never intended to leave. The challenge with traditional dunning emails is that they require the subscriber to do three things: open the email, read it, and click through. That's three opportunities to drop off.</p>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0;">Payment banners eliminate that friction. When a subscriber is already logged in and using your product, that's your highest-intent moment. A well-timed in-session banner converts at dramatically higher rates than email alone — because the subscriber is already engaged, already in context, and already in the mindset of getting value from your product.</p>
    </div>

    <h3 class="rc-subhead">💼 Key business benefits</h3>
    <div class="rc-2col">
      <div class="rc-opt"><div class="rc-oicon">🛡️</div><h4>Stop Churn Before It Starts</h4><p>Payment banners catch at-risk subscribers while they're active — before a failed payment triggers the dunning cycle or results in a cancelled subscription.</p><span class="rc-tag">Proactive Retention</span></div>
      <div class="rc-opt"><div class="rc-oicon">⚡</div><h4>Higher Conversion Than Email</h4><p>In-session prompts meet subscribers at peak intent. No competing inbox noise, no link to click through — just a direct path to resolve the issue right now.</p><span class="rc-tag">Better Outcomes</span></div>
      <div class="rc-opt"><div class="rc-oicon">🤝</div><h4>Seamless Subscriber Experience</h4><p>A friendly, contextual banner feels like helpful service — not a warning. It reinforces that you're looking out for them, which builds loyalty and trust.</p><span class="rc-tag">CX Improvement</span></div>
      <div class="rc-opt"><div class="rc-oicon">🔁</div><h4>Complements Your Dunning Stack</h4><p>Banners don't replace dunning emails — they enhance them. Banners catch in-session users; emails catch everyone else. Together, they maximise recovery coverage.</p><span class="rc-tag">Layered Defense</span></div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Don't rely on email alone:</strong> The average email open rate for billing-related messages is well below 50%. That means more than half of your at-risk subscribers may never see your dunning communication. Payment banners reach the subscribers dunning emails miss.</p>
    </div>

    <h3 class="rc-subhead">✅ Is this right for your business?</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><h3>Quick fit assessment</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">You have subscribers who log into your app or portal regularly<span>High login frequency = more opportunities for banners to fire</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">You're seeing involuntary churn from expired or declined cards<span>Payment banners directly address this failure mode</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Your dunning email engagement has plateaued or is declining<span>Banners provide a channel that doesn't depend on inbox behaviour</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">You have annual subscribers approaching renewal<span>High-value moments where a banner saves significant revenue</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">You want to improve subscriber experience without adding support burden<span>Banners resolve issues proactively so subscribers don't need to contact support</span></div></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Layer it with Account Updater</h4><p>Account Updater silently fixes card credential issues for eligible cards — no subscriber action needed. Payment Banners handle the cases AU can't: closed accounts, insufficient funds, or any situation where the subscriber needs to take action. Use both for the most complete involuntary churn prevention strategy available.</p></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners">← Payment Banners</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-use-cases">Next: Use Cases →</a>
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
