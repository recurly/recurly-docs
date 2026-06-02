---
title: Code Test Course Page 6
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
.rc-bp-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
.rc-bp{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray)}
.rc-bp-icon{font-size:24px;margin-bottom:10px}
.rc-bp h4{font-size:.92rem;font-weight:700;color:var(--offblack);margin:0 0 6px}
.rc-bp p{font-size:.82rem;color:var(--gray);line-height:1.55;margin:0}
.rc-do-dont{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
.rc-do{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray);border-top:4px solid #2E7D32}
.rc-dont{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray);border-top:4px solid var(--orange)}
.rc-do h4{font-size:.88rem;font-weight:700;color:#2E7D32;margin:0 0 10px;text-transform:uppercase;letter-spacing:.5px}
.rc-dont h4{font-size:.88rem;font-weight:700;color:var(--orange);margin:0 0 10px;text-transform:uppercase;letter-spacing:.5px}
.rc-do ul,.rc-dont ul{margin:0;padding-left:16px;font-size:.82rem;color:var(--gray);line-height:1.8}
.rc-kpi-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
.rc-kpi{background:var(--offblack);border-radius:14px;padding:20px;text-align:center}
.rc-kpi-num{font-size:1.4rem;font-weight:800;color:var(--yellow);margin-bottom:4px}
.rc-kpi-label{font-size:.78rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
.rc-kpi-desc{font-size:.78rem;color:var(--gray);margin-top:6px;line-height:1.4}
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
@media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-bp-grid,.rc-do-dont,.rc-kpi-grid{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage"><span class="rc-snum">4</span>Recurly Engage</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-best-practices"><span class="rc-snum">5</span>Best Practices</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-pitch"><span class="rc-snum">6</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">⭐</div>
      <div>
        <h2>Best practices & tracking impact</h2>
        <p>From timing and messaging to KPIs and reporting cadence — everything you need to optimise your payment banners and prove their value.</p>
      </div>
    </div>

    <h3 class="rc-subhead">⏰ Timing: when to fire your banners</h3>
    <div class="rc-bp-grid">
      <div class="rc-bp"><div class="rc-bp-icon">📅</div><h4>Expiring Card: 30 Days Out</h4><p>Fire the first banner 30 days before card expiry. This gives the subscriber plenty of time to update without feeling rushed. If not updated, send a second banner at the 14-day mark.</p></div>
      <div class="rc-bp"><div class="rc-bp-icon">⚡</div><h4>Failed Payment: Next Login</h4><p>Show the banner immediately on the subscriber's very next session after a payment failure. This is your highest-urgency scenario — act fast while the issue is fresh.</p></div>
      <div class="rc-bp"><div class="rc-bp-icon">🔄</div><h4>Annual Renewal: 30 Days Prior</h4><p>For annual subscribers, surface a banner 30 days before renewal. Annual renewals only recover at 23.3% once they fail — prevention is everything here.</p></div>
      <div class="rc-bp"><div class="rc-bp-icon">📧</div><h4>Dunning Cycle: Any Login</h4><p>Show the banner on every login during an active dunning cycle — it reinforces the email channel for subscribers who haven't acted yet. Stop showing it once resolved.</p></div>
    </div>

    <h3 class="rc-subhead">✍️ Messaging: what to say (and what not to say)</h3>
    <div class="rc-do-dont">
      <div class="rc-do">
        <h4>✅ Do</h4>
        <ul>
          <li>Be specific: mention the card ending in XXXX</li>
          <li>State the consequence clearly but calmly</li>
          <li>Use a direct, single CTA: "Update payment"</li>
          <li>Keep it under 2 sentences</li>
          <li>Match your product's tone of voice</li>
          <li>Make it easy to dismiss for low-urgency cases</li>
        </ul>
      </div>
      <div class="rc-dont">
        <h4>❌ Don't</h4>
        <ul>
          <li>Use alarming language like "URGENT" or "WARNING"</li>
          <li>Show the same message regardless of the trigger</li>
          <li>Use vague CTAs like "Click here" or "Learn more"</li>
          <li>Show the banner on every single page view</li>
          <li>Skip frequency capping — it creates fatigue</li>
          <li>Forget to dismiss the banner after resolution</li>
        </ul>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">💬 Example banner copy by scenario</h3>
      <p style="font-size:.88rem;color:var(--darkgray);line-height:1.7;margin:0 0 10px;"><strong>Expiring card:</strong> "Your card ending in 4242 expires in 28 days. Update your payment method to keep your subscription active." → <em>Update now</em></p>
      <p style="font-size:.88rem;color:var(--darkgray);line-height:1.7;margin:0 0 10px;"><strong>Failed payment:</strong> "We couldn't process your last payment. Update your billing info to restore full access to your account." → <em>Update billing info</em></p>
      <p style="font-size:.88rem;color:var(--darkgray);line-height:1.7;margin:0 0 10px;"><strong>Annual pre-renewal:</strong> "Your annual plan renews on March 15. Confirm your payment method is up to date to avoid any interruption." → <em>Review payment method</em></p>
      <p style="font-size:.88rem;color:var(--darkgray);line-height:1.7;margin:0;"><strong>Post-dunning:</strong> "We still haven't been able to process your payment. Update your billing info now to keep your access." → <em>Resolve now</em></p>
    </div>

    <h3 class="rc-subhead">📊 KPIs to track</h3>
    <div class="rc-kpi-grid">
      <div class="rc-kpi"><div class="rc-kpi-num">Banner CTR</div><div class="rc-kpi-label">Click-through rate</div><div class="rc-kpi-desc">% of subscribers who click the update CTA after seeing the banner. Benchmark: aim for 15–25% on expiring card banners.</div></div>
      <div class="rc-kpi"><div class="rc-kpi-num">Completion Rate</div><div class="rc-kpi-label">Payment updated</div><div class="rc-kpi-desc">% of subscribers who complete the payment update after clicking the CTA. Drop-off here indicates friction in your update flow.</div></div>
      <div class="rc-kpi"><div class="rc-kpi-num">Involuntary Churn Δ</div><div class="rc-kpi-label">Before vs. after</div><div class="rc-kpi-desc">Compare your involuntary churn rate in the 90 days before and after enabling banners. This is your headline ROI metric.</div></div>
      <div class="rc-kpi"><div class="rc-kpi-num">Revenue Saved</div><div class="rc-kpi-label">Recovered MRR</div><div class="rc-kpi-desc">Multiply subscribers retained via banners by ARPU. Annual subscribers saved × annual plan value gives you an immediate revenue impact figure.</div></div>
    </div>

    <h3 class="rc-subhead">🔁 Frequency capping & subscriber fatigue</h3>
    <div class="rc-card">
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Showing the same banner every session is one of the fastest ways to train subscribers to ignore it. Frequency capping ensures banners remain meaningful and actionable rather than background noise.</p>
      <p style="font-size:.88rem;color:var(--darkgray);line-height:1.6;margin:0 0 8px;"><strong>Recommended caps:</strong></p>
      <p style="font-size:.88rem;color:var(--gray);line-height:1.7;margin:0 0 6px;">• Expiring card: once every 5 sessions, or once per week</p>
      <p style="font-size:.88rem;color:var(--gray);line-height:1.7;margin:0 0 6px;">• Failed payment: every session for the first 3 days, then every 3 sessions</p>
      <p style="font-size:.88rem;color:var(--gray);line-height:1.7;margin:0;">• Annual renewal: once per week in the 30-day pre-renewal window</p>
    </div>

    <h3 class="rc-subhead">🏆 Optimisation checklist</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><h3>Make your banners as effective as possible</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Separate banner campaigns configured per trigger type<span>Expiring card, failed payment, and annual renewal should each have tailored messaging</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Frequency cap set on all campaigns<span>Prevents subscriber fatigue and keeps banners feeling relevant</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">CTA is specific and action-oriented<span>"Update payment method" outperforms generic CTAs every time</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Banner dismisses automatically once issue is resolved<span>Don't show a resolved banner — it erodes trust</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Account Updater enabled alongside banners<span>AU handles silent fixes; banners handle everything that needs human action</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Monthly KPI review scheduled<span>Track CTR, completion rate, and involuntary churn delta each month</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Banners are mobile-optimised<span>Many subscribers access your product on mobile — test the experience on small screens</span></div></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>The 90-day rule</h4><p>Give your payment banners 90 days before drawing firm conclusions about their impact. Card expiry cycles, billing periods, and subscriber behaviour patterns take time to fully reflect in your metrics. Use the first 30 days to validate the banner is firing correctly, the second 30 to watch CTR and completion rates, and the third 30 to measure the churn delta.</p></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-engage">← Recurly Engage</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-pitch">Next: Pitch to Leadership →</a>
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
