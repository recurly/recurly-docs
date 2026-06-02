---
title: Code Test Course Page 7
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
.rc-oneliner{background:var(--offblack);border-radius:16px;padding:40px;text-align:center;margin-bottom:28px}
.rc-oneliner h2{color:var(--yellow);font-size:1.1rem;font-weight:800;text-transform:uppercase;letter-spacing:1px;margin:0 0 12px}
.rc-oneliner p{color:var(--lightgray);font-size:1.05rem;line-height:1.6;margin:0;font-style:italic}
.rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
.rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
.rc-sbadge{width:38px;height:38px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
.rc-audience-grid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
.rc-audience{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray)}
.rc-audience h4{font-size:.88rem;font-weight:700;color:var(--offblack);margin:0 0 8px}
.rc-audience p{font-size:.8rem;color:var(--gray);line-height:1.55;margin:0}
.rc-objections{display:flex;flex-direction:column;gap:12px;margin-bottom:24px}
.rc-objection{background:var(--offwhite);border-radius:14px;border:1px solid var(--lightgray);overflow:hidden}
.rc-obj-q{background:var(--brightgray);padding:14px 20px;font-size:.88rem;font-weight:700;color:var(--offblack)}
.rc-obj-a{padding:14px 20px;font-size:.85rem;color:var(--gray);line-height:1.6}
.rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:28px}
.rc-cl-header{padding:16px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:center;gap:10px;background:var(--offblack)}
.rc-cl-header h3{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
.rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:flex-start;gap:14px}.rc-cli:last-child{border-bottom:none}
.rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;background:#fff}
.rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}.rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
.rc-office-hours{background:linear-gradient(135deg,var(--offblack) 0%,#1a1a1a 100%);color:#fff;border-radius:16px;padding:32px;margin:32px 0;border:1px solid var(--yellow)}
.rc-office-hours h4{color:var(--yellow);margin:0 0 8px;font-size:1.1rem;font-weight:800;text-transform:uppercase;letter-spacing:1px}
.rc-office-hours p{color:var(--lightgray);font-size:.95rem;line-height:1.6;margin:0 0 20px}
.rc-office-hours a{display:inline-flex;align-items:center;gap:8px;background:var(--yellow);color:var(--offblack);padding:12px 24px;border-radius:10px;font-weight:700;font-size:.9rem;text-decoration:none}
.rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
.rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none;border:1px solid var(--lightgray)}
.rc-btn-prev{background:#fff;color:var(--darkgray)}.rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
.rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);border-color:var(--yellow);margin:0 8px 8px 0}.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border-color:var(--lightgray)}
@media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-audience-grid{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-best-practices"><span class="rc-snum">5</span>Best Practices</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-pitch"><span class="rc-snum">6</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🎤</div>
      <div>
        <h2>Pitch Recurly Engage to leadership</h2>
        <p>Build a compelling case for Recurly Engage's payment banners — with a ready-made framework, ROI talking points, and answers to the questions leadership will ask.</p>
      </div>
    </div>

    <div class="rc-oneliner">
      <h2>The one-line pitch</h2>
      <p>"Recurly Engage delivers payment banners that catch at-risk subscribers while they're already using our product — reducing involuntary churn with zero engineering lift and measurable revenue impact from day one."</p>
    </div>

    <h3 class="rc-subhead">📋 The pitch framework — step by step</h3>
    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Open with the revenue leak</h3><p>Start with a number that lands: up to 40% of subscription losses are involuntary — customers who didn't choose to leave but whose payment method failed. Pull your own involuntary churn rate from Recurly Analytics and translate it to dollar value. "Last quarter we lost $X in MRR to failed payments — none of those customers intended to cancel."</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Explain why email isn't enough</h3><p>Dunning emails are reactive and inbox-dependent. Average billing email open rates are well below 50% — meaning more than half of at-risk subscribers never see the message. Payment banners reach subscribers while they're actively in your product, at the highest-intent moment to act.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Introduce Recurly Engage</h3><p>Recurly Engage is a subscriber experience layer built into Recurly that automatically detects at-risk accounts and surfaces payment banners in-session. No engineering work required — configure triggers, messaging, and timing directly in the Recurly dashboard and activate the same day.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>Make the ROI case</h3><p>Use this formula: (Monthly involuntary churn MRR × expected banner recovery rate) = Monthly revenue saved. A 10–15% improvement in involuntary churn recovery on a $500K MRR business saves $5K–$7.5K per month. Multiply by average subscriber lifetime for the full picture. Engaged subscribers also spend 3x more — Engage's value extends beyond just payment recovery.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">5</div><div><h3>Close with a 30-day pilot ask</h3><p>Request a 30-day trial of Recurly Engage focused specifically on payment banner campaigns. Set clear success metrics upfront — banner CTR, payment update completion rate, and involuntary churn delta. Frame it as a low-risk, high-signal test that produces real data before any long-term commitment.</p></div></div>
    </div>

    <h3 class="rc-subhead">🎯 Talking points by audience</h3>
    <div class="rc-audience-grid">
      <div class="rc-audience"><h4>💼 CFO / Finance</h4><p>Involuntary churn MRR × subscriber lifetime = recoverable revenue. Retaining one subscriber costs a fraction of acquiring a new one. Engage's impact is directly measurable in your MRR dashboard.</p></div>
      <div class="rc-audience"><h4>🔧 VP Engineering / CTO</h4><p>Zero engineering lift required — no backend work, no frontend build, no deployment. Engage runs on Recurly's infrastructure. Your team doesn't touch it.</p></div>
      <div class="rc-audience"><h4>📱 VP Product / GM</h4><p>Payment banners improve the subscriber experience — proactively helping customers avoid service disruptions. It reduces support tickets from confused users whose access was cut off unexpectedly.</p></div>
    </div>

    <h3 class="rc-subhead">❓ Objection handling</h3>
    <div class="rc-objections">
      <div class="rc-objection">
        <div class="rc-obj-q">"We already send dunning emails — isn't that enough?"</div>
        <div class="rc-obj-a">Dunning emails are reactive and inbox-dependent. Payment banners are proactive and in-session. They work differently and reach different subscribers. Banners catch the ones who open your app but don't check their email — which is a significant segment. Together, they provide full coverage that neither channel achieves alone.</div>
      </div>
      <div class="rc-objection">
        <div class="rc-obj-q">"What does Recurly Engage cost?"</div>
        <div class="rc-obj-a">Recurly Engage is an add-on to your Recurly subscription. Contact your CSM for pricing specific to your account. The ROI conversation is straightforward: take your monthly involuntary churn MRR, apply a conservative 10% recovery rate, and compare that to the Engage cost. For most businesses the math is compelling.</div>
      </div>
      <div class="rc-objection">
        <div class="rc-obj-q">"Can't our dev team just build this with webhooks?"</div>
        <div class="rc-obj-a">Yes — and Tab 3 of this learning path covers exactly how to do that. But consider the engineering cost: scoping, building, testing, and maintaining a webhook-based banner system takes meaningful developer time. Engage delivers the same outcome out of the box, immediately, with no ongoing maintenance burden on your team.</div>
      </div>
      <div class="rc-objection">
        <div class="rc-obj-q">"How quickly will we see results?"</div>
        <div class="rc-obj-a">Banner impressions begin as soon as qualifying subscribers log in — typically within 24–48 hours of activation. You'll see CTR and completion data within the first week. Meaningful involuntary churn impact shows up within 30–90 days depending on your billing cycle cadence.</div>
      </div>
      <div class="rc-objection">
        <div class="rc-obj-q">"Will this annoy our subscribers?"</div>
        <div class="rc-obj-a">Only if configured poorly. With proper frequency capping and relevant, personalised messaging, payment banners feel like helpful service — not spam. A subscriber who sees a timely "your card expires in 30 days" banner appreciates the heads-up far more than finding their account suddenly suspended.</div>
      </div>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header"><h3>Pre-meeting checklist</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Pull your involuntary churn rate and MRR impact from Recurly Analytics<span>This is your opening number — make it specific to your business</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Calculate your ARPU and average subscriber lifetime<span>Needed to convert "subscribers retained" into long-term revenue value</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Note your current dunning email open rate<span>The gap between open rate and 100% is your addressable banner opportunity</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Confirm Recurly Engage pricing with your CSM<span>Have the cost ready so you can present the full ROI calculation</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Prepare 3 slides: Problem → Solution → 30-Day Pilot Proposal<span>Keep it concise — leadership wants the headline numbers, not the full detail</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Review objection handling above so you're ready for questions<span>The engineering cost question comes up almost every time</span></div></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">🎯</span>
      <div><h4>Lead with the number they care about most</h4><p>Every leadership team is different — but almost all of them respond to a specific dollar figure. "We could recover an estimated $X per month in revenue we're currently losing to involuntary churn" lands harder than any feature description. Pull your number from Recurly Analytics before the meeting and make it the first thing you say.</p></div>
    </div>

    <div class="rc-office-hours">
      <h4>🗓️ Want help building your case?</h4>
      <p>Join a <strong>Customer Success Global Office Hours</strong> session and our CSMs will walk through your Recurly data with you, help you calculate your specific involuntary churn opportunity, and prepare you for the leadership conversation.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">Register for Office Hours →</a>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners-best-practices">← Best Practices</a>
      <span class="rc-btn-disabled">🎉 You're Ready to Go!</span>
    </div>

    <h3 class="rc-subhead" style="margin-top:40px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-engage" target="_blank" rel="noopener noreferrer">✨ Recurly Engage Docs</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-payment-banners">🧭 Return to Start</a>
  </div>
</div>
`}</HTMLBlock>

<br />
