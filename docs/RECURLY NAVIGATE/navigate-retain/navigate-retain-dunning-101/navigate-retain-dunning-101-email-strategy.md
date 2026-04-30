---
title: 'Dunning 101: Email strategy'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
  .rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
  *{box-sizing:border-box}
  .rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px}
  .rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
  .rc-hero h1{font-size:2.2rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
  .rc-hero p{font-size:1.05rem;opacity:.8;max-width:680px;margin:0 auto 32px;color:var(--lightgray)}
  .rc-hero-stats{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}
  .rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:10px;padding:10px 18px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-nav a.is-active .rc-snum{background:var(--offblack);color:var(--yellow)}
  .rc-sec{margin-bottom:40px}
  .rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:28px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.6rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
  .rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-body-text{font-size:.92rem;color:var(--darkgray);line-height:1.7;margin:0 0 16px}
  .rc-body-text a{color:var(--orange);font-weight:600;text-decoration:none}
  .rc-subhead{font-size:1.1rem;font-weight:700;margin:32px 0 14px;color:var(--offblack)}
  .rc-subhead-sm{font-size:.95rem;font-weight:700;margin:20px 0 10px;color:var(--offblack)}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:20px}
  .rc-card h3{font-size:1rem;font-weight:700;margin:0 0 12px;color:var(--offblack)}
  .rc-card p{font-size:.88rem;color:var(--darkgray);line-height:1.7;margin:0 0 10px}
  .rc-card p:last-child{margin-bottom:0}
  .rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:20px}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:20px}
  .rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray);text-align:center}
  .rc-wi-icon{font-size:28px;margin-bottom:10px}
  .rc-wi h4{font-size:.88rem;font-weight:700;margin:0 0 6px;color:var(--offblack)}
  .rc-wi p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-dark-stat{background:var(--offblack);border-radius:14px;padding:24px 16px;text-align:center}
  .rc-dark-stat-num{font-size:1.8rem;font-weight:800;color:var(--yellow);display:block;margin-bottom:6px}
  .rc-dark-stat-lbl{font-size:.78rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-dark-card{background:var(--offblack);border-radius:14px;padding:24px 28px;margin-bottom:14px}
  .rc-dark-card h3{font-size:1rem;font-weight:700;color:var(--yellow);margin:0 0 8px}
  .rc-dark-card p{font-size:.88rem;color:var(--lightgray);margin:0;line-height:1.65}
  .rc-dark-card a{color:var(--yellow);font-weight:700}
  .rc-flow{background:var(--offblack);border-radius:14px;padding:28px 20px;display:flex;align-items:center;gap:8px;flex-wrap:wrap;margin-bottom:20px;justify-content:center}
  .rc-flow-node{background:rgba(255,253,242,.07);border:1px solid rgba(255,253,242,.14);border-radius:10px;padding:14px 16px;text-align:center;min-width:110px}
  .rc-flow-node.hl{background:rgba(255,215,6,.14);border-color:rgba(255,215,6,.38)}
  .rc-flow-icon{font-size:20px;display:block;margin-bottom:6px}
  .rc-flow-lbl{font-size:12px;font-weight:700;color:#FFFDF2;display:block}
  .rc-flow-sub{font-size:10px;color:rgba(255,253,242,.48);display:block;margin-top:2px}
  .rc-flow-arrow{color:rgba(255,253,242,.3);font-size:20px}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:20px}
  .rc-tipicon{font-size:24px;flex-shrink:0}
  .rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
  .rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-tip a{color:var(--orange);font-weight:600;text-decoration:none}
  .rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start;margin-bottom:20px}
  .rc-wicon{font-size:20px;flex-shrink:0}
  .rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-table{width:100%;border-collapse:collapse;font-size:13.5px;margin-bottom:20px;border-radius:10px;overflow:hidden;border:1px solid var(--lightgray)}
  .rc-table thead{background:var(--offblack);color:#FFFDF2}
  .rc-table thead th{padding:12px 16px;text-align:left;font-size:12px;font-weight:700;letter-spacing:.5px;text-transform:uppercase}
  .rc-table tbody tr:nth-child(even){background:var(--brightgray)}
  .rc-table tbody tr:nth-child(odd){background:var(--offwhite)}
  .rc-table tbody td{padding:12px 16px;color:var(--darkgray);border-bottom:1px solid var(--lightgray);vertical-align:top;font-size:.87rem}
  .rc-table tbody td strong{color:var(--offblack)}
  .rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:24px}
  .rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
  .rc-sbadge{width:38px;height:38px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.95rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
  .rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
  .rc-step p code{background:var(--brightgray);padding:2px 6px;border-radius:4px;font-size:.85em}
  .rc-tip-badge{display:flex;align-items:stretch;border-radius:12px;overflow:hidden;margin:28px 0 16px;border:1px solid var(--lightgray)}
  .rc-tip-num{background:var(--yellow);color:var(--offblack);font-size:12px;font-weight:800;display:flex;align-items:center;justify-content:center;padding:0 18px;min-width:60px;text-align:center;line-height:1.3;text-transform:uppercase;letter-spacing:.3px}
  .rc-tip-title{background:var(--brightgray);padding:14px 18px;font-size:.92rem;font-weight:700;color:var(--offblack);display:flex;align-items:center}
  .rc-tag{display:inline-block;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;background:var(--offblack);color:var(--yellow);margin-top:8px}
  .rc-checklist{list-style:none;padding:0;margin:0 0 20px}
  .rc-checklist li{display:flex;align-items:flex-start;gap:12px;font-size:.88rem;color:var(--darkgray);line-height:1.6;padding:9px 0;border-bottom:1px solid var(--brightgray)}
  .rc-checklist li:last-child{border-bottom:none}
  .rc-check{width:22px;height:22px;border:2px solid var(--lightgray);border-radius:6px;flex-shrink:0;background:#fff;margin-top:2px}
  .rc-result-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-bottom:20px}
  .rc-result-card{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:12px;padding:20px}
  .rc-result-num{font-size:1.8rem;font-weight:800;color:var(--offblack);display:block;margin-bottom:6px}
  .rc-result-tag{display:inline-block;background:var(--yellow);color:var(--offblack);font-size:11px;font-weight:700;padding:3px 10px;border-radius:20px;margin-bottom:10px}
  .rc-result-card p{font-size:.8rem;color:var(--darkgray);margin:0;line-height:1.6}
  .rc-divider{border:none;border-top:2px solid var(--brightgray);margin:32px 0}
  .rc-metric-card{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:12px;padding:22px;margin-bottom:14px}
  .rc-metric-card h4{font-size:.95rem;font-weight:700;color:var(--offblack);margin:0 0 6px}
  .rc-metric-where{font-size:.78rem;font-weight:700;color:var(--gray);margin:0 0 10px;text-transform:uppercase;letter-spacing:.4px;display:block}
  .rc-metric-card p{font-size:.87rem;color:var(--darkgray);margin:0;line-height:1.65}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:32px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-btn-disabled{display:inline-flex;align-items:center;justify-content:center;padding:11px 20px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}
  .rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default;border:1px solid var(--lightgray)}
  .rc-link-sec{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);padding:28px;margin-top:32px}
  .rc-link-sec h3{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-link-btn{display:inline-flex;align-items:center;gap:8px;background:var(--yellow);color:var(--offblack);padding:9px 16px;border-radius:8px;text-decoration:none;font-size:.85rem;font-weight:700;margin:0 8px 8px 0}
  .rc-link-btn-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  .rc-body-ul{padding-left:20px;margin:0 0 16px;color:var(--darkgray);font-size:.88rem;line-height:1.8}
  .rc-body-ul li{margin-bottom:4px}
  @media(max-width:640px){.rc-hero{padding:36px 20px 32px}.rc-hero h1{font-size:1.6rem}.rc-hero-stats{gap:20px}.rc-3col,.rc-2col,.rc-result-grid{grid-template-columns:1fr}.rc-sec-nav{flex-direction:column;align-items:stretch}.rc-flow{flex-direction:column}}
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">&#128197; Recurly Navigate &middot; Dunning 101</div>
    <h1>Dunning 101</h1>
    <p>Five tips covering everything about how your dunning emails look, feel, and communicate.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">5 Tips</div><div class="rc-lbl">Email Strategy</div></div>
      <div><div class="rc-num">4&ndash;5 Days</div><div class="rc-lbl">Between Each Email</div></div>
      <div><div class="rc-num">+12%</div><div class="rc-lbl">Uplift From Branding</div></div>
    </div>
  </div>
  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-basics"><span class="rc-snum">1</span> Dunning Basics</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-setup"><span class="rc-snum">2</span> Setup &amp; Configuration</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-email-strategy" class="is-active"><span class="rc-snum">3</span> Email Strategy</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-subscriber-engagement"><span class="rc-snum">4</span> Subscriber Engagement</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-advanced-configuration"><span class="rc-snum">5</span> Advanced Configuration</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-metrics"><span class="rc-snum">6</span> Metrics &amp; Tracking</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-strategy-and-resources"><span class="rc-snum">&#10003;</span> Strategy &amp; Resources</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">&#128231;</div>
      <div>
        <h2>Email Strategy</h2>
        <p>Five tips covering everything about how your dunning emails look, feel, and communicate — the foundation of effective payment recovery.</p>
      </div>
    </div>

    <div class="rc-tip-badge">
      <div class="rc-tip-num">Tip 1</div>
      <div class="rc-tip-title">Match Your Branding to Your Other Communications</div>
    </div>
    <p class="rc-body-text">Your dunning emails should look and feel exactly like every other email you send — same logo, brand colors, font, button styles, and tone of voice. Brand recognition is your first line of trust.</p>
    <ul class="rc-body-ul">
      <li>Go to Configuration &rarr; Email Templates &rarr; Dunning</li>
      <li>Set a branded header: your logo, background color, and primary font</li>
      <li>Set a branded footer: copyright, links to your terms and support pages</li>
      <li>Update the CTA button color and label to match your product's style</li>
      <li>Send a test email to yourself — if it doesn't feel on-brand, keep refining</li>
    </ul>
    <div class="rc-tip">
      <span class="rc-tipicon">&#128161;</span>
      <div><h4>Why This Works</h4><p>One Recurly customer achieved a 12% uplift in dunning recovery rate simply by rebranding their dunning emails to match their product design. Subscribers recognized them immediately and clicked through.</p></div>
    </div>

    <hr class="rc-divider" />

    <div class="rc-tip-badge">
      <div class="rc-tip-num">Tip 2</div>
      <div class="rc-tip-title">Leave 4–5 Days Between Each Message — 27 or 60 Days for the Full Cycle</div>
    </div>
    <p class="rc-body-text">The length of your dunning window and the spacing between emails are two of the highest-impact settings in your setup. Most accounts start with a 10-day default window and emails sent every 1–2 days — both too short and too frequent.</p>
    <table class="rc-table">
      <thead><tr><th>Plan Type</th><th>Recommended Window</th><th>Email Cadence</th></tr></thead>
      <tbody>
        <tr><td><strong>Monthly</strong></td><td>27 days</td><td>4–5 emails, every 4–5 days</td></tr>
        <tr><td><strong>Annual / 6-month</strong></td><td>60 days</td><td>8–10 emails, every 8–10 days</td></tr>
        <tr><td><strong>Short-term / trial</strong></td><td>10–14 days</td><td>2–3 emails, every 3–5 days</td></tr>
      </tbody>
    </table>
    <div class="rc-tip">
      <span class="rc-tipicon">&#128161;</span>
      <div><h4>The 27-Day Rule</h4><p>We recommend 27 days (not 30) for monthly plans because it prevents two monthly invoices from overlapping in the dunning window, keeping accounting clean and avoiding confusing subscribers with duplicate payment requests.</p></div>
    </div>

    <hr class="rc-divider" />

    <div class="rc-tip-badge">
      <div class="rc-tip-num">Tip 3</div>
      <div class="rc-tip-title">Use Different Email Tones — Changing Message With Each Send</div>
    </div>
    <p class="rc-body-text">Sending the same dunning email template multiple times is one of the most common setup mistakes. Each email should be a distinct communication with a unique message, different tone, and evolving focus.</p>
    <table class="rc-table">
      <thead><tr><th>Email</th><th>Timing</th><th>Tone</th><th>Focus</th></tr></thead>
      <tbody>
        <tr><td><strong>Email 1</strong></td><td>Day 0–3</td><td>Helpful &amp; informative</td><td>Notify: "We noticed an issue with your payment."</td></tr>
        <tr><td><strong>Email 2</strong></td><td>Day 5–8</td><td>Friendly &amp; reassuring</td><td>Remind: "Still active — just update billing to keep it."</td></tr>
        <tr><td><strong>Email 3</strong></td><td>Day 12–16</td><td>Warm but direct</td><td>Value: "Here's what you'd lose if your subscription expires."</td></tr>
        <tr><td><strong>Email 4</strong></td><td>Day 20–22</td><td>Urgent</td><td>Countdown: "Your account closes in [X] days — act now."</td></tr>
        <tr><td><strong>Email 5</strong></td><td>Day 25–27</td><td>Final notice</td><td>Last chance: "This is the final notice before expiry."</td></tr>
      </tbody>
    </table>
    <div class="rc-tip">
      <span class="rc-tipicon">&#128161;</span>
      <div><h4>Use Recurly's Dynamic Variables</h4><p>Personalize each email with the subscriber's name, plan name, invoice amount, card type, last four digits, and days remaining — making each email feel personal and credible.</p></div>
    </div>

    <hr class="rc-divider" />

    <div class="rc-tip-badge">
      <div class="rc-tip-num">Tip 4</div>
      <div class="rc-tip-title">Offer Alternative CTAs — Links to FAQ, Support, Community, and More</div>
    </div>
    <p class="rc-body-text">Not every subscriber who receives a dunning email is ready or able to update their payment immediately. A dunning email that offers only one path misses the opportunity to meet them where they are.</p>
    <div class="rc-2col">
      <div class="rc-wi"><div class="rc-wi-icon">&#128172;</div><h4>Chat With Support</h4><p>Some subscribers have billing questions or disputes. A direct line to help can save the subscription entirely — use in all stages.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">&#10067;</div><h4>Visit Our Help Center</h4><p>Many subscribers hesitate because they're unsure about something. Answers remove that barrier — especially effective early in the cycle.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">&#9208;&#65039;</div><h4>Pause Instead of Cancel</h4><p>If you offer subscription pauses, include this as a CTA in late-stage emails. Subscribers who pause are far more likely to return than those who lapse.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">&#127760;</div><h4>Join Our Community</h4><p>Keeps the subscriber connected to your brand even if they don't immediately fix their payment — a soft retention lever worth using.</p></div>
    </div>
    <div class="rc-tip">
      <span class="rc-tipicon">&#128161;</span>
      <div><h4>One Primary CTA, Multiple Secondary Options</h4><p>Keep "Update My Payment Method" as your primary, visually dominant button. Secondary options should be smaller, text-link style. Remove barriers — don't overwhelm.</p></div>
    </div>

    <hr class="rc-divider" />

    <div class="rc-tip-badge">
      <div class="rc-tip-num">Tip 5</div>
      <div class="rc-tip-title">Build Urgency Progressively With Each Send</div>
    </div>
    <p class="rc-body-text">Your first dunning email should be calm and helpful. Your last should be firm and direct. Most businesses get this wrong by being too aggressive from the start or too gentle all the way through.</p>
    <table class="rc-table">
      <thead><tr><th>Day</th><th>Example Subject Line</th></tr></thead>
      <tbody>
        <tr><td>Day 0</td><td>We couldn't process your [Product] payment</td></tr>
        <tr><td>Day 7</td><td>Your [Product] subscription needs attention</td></tr>
        <tr><td>Day 14</td><td>Your access expires in [X] days — here's what you'll lose</td></tr>
        <tr><td>Day 21</td><td>Last chance — [X] days to keep your [Product] subscription</td></tr>
        <tr><td>Day 26</td><td>Final notice: Your subscription expires tomorrow</td></tr>
      </tbody>
    </table>
    <div class="rc-tip">
      <span class="rc-tipicon">&#128161;</span>
      <div><h4>Escalation Without Hostility</h4><p>Progressive urgency doesn't mean threatening language. The tone should always reflect care for the subscriber — you want them to stay. Escalation is about making sure they know the clock is ticking.</p></div>
    </div>
  <div class="rc-sec-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-setup" class="rc-btn-prev">&larr; Setup &amp; Configuration</a>
    <span style="color:var(--gray);font-size:.85rem;font-weight:600">Page 3 of 7</span>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-subscriber-engagement" class="rc-btn-next">Subscriber Engagement &rarr;</a>
  </div>
  </div>

  <div class="rc-link-sec">
    <h3>&#128218; Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-management" class="rc-link-btn" target="_blank" rel="noopener noreferrer">&#128214; Dunning Management Docs</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-benchmarks" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#128202; Dunning Benchmarks</a>
    <a href="https://share.synthesia.io/7f58d816-a65c-42f4-950d-59b11953d1aa" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#127909; Trail Guide Video</a>
    <a href="https://navigate.recurly.com/event-hub/" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#127775; Join Global Office Hours</a>
    <a href="https://recurly.ondemand.goldcast.io/on-demand/a65f472f-9876-4736-9209-5b7b669de773" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#127925; On-Demand Webinar: Stop the Leak</a>
  </div>
</div>
`}</HTMLBlock>

<br />
