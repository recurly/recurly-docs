---
title: 'Dunning 101: Advanced configuration'
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
    <p>Three tips for the more technical and strategic setup decisions that take dunning from good to great.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">3 Tips</div><div class="rc-lbl">Advanced Setup</div></div>
      <div><div class="rc-num">~60%</div><div class="rc-lbl">In-App CTR</div></div>
      <div><div class="rc-num">3 Options</div><div class="rc-lbl">Email Delivery</div></div>
    </div>
  </div>
  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-basics"><span class="rc-snum">1</span> Dunning Basics</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-setup"><span class="rc-snum">2</span> Setup &amp; Configuration</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-email-strategy"><span class="rc-snum">3</span> Email Strategy</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-subscriber-engagement"><span class="rc-snum">4</span> Subscriber Engagement</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-advanced-configuration" class="is-active"><span class="rc-snum">5</span> Advanced Configuration</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-metrics"><span class="rc-snum">6</span> Metrics &amp; Tracking</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-strategy-and-resources"><span class="rc-snum">&#10003;</span> Strategy &amp; Resources</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">&#128295;</div>
      <div>
        <h2>Advanced Configuration</h2>
        <p>Three tips for the more technical and strategic setup decisions that take dunning from good to great.</p>
      </div>
    </div>

    <div class="rc-tip-badge">
      <div class="rc-tip-num">Tip 8</div>
      <div class="rc-tip-title">Use Multiple Campaigns — Targeting Different Plans &amp; User Groups</div>
    </div>
    <p class="rc-body-text">Out of the box, Recurly applies a single default dunning campaign to every subscriber. That means your monthly consumer customer and your annual enterprise account receive the same window length, same cadence, and same messaging. One-size-fits-all dunning is far less effective than targeted campaigns.</p>
    <h3 class="rc-subhead-sm">Start With Two: Monthly &amp; Annual</h3>
    <table class="rc-table">
      <thead><tr><th>Campaign</th><th>Window</th><th>Email Cadence</th><th>Tone</th></tr></thead>
      <tbody>
        <tr><td><strong>Monthly</strong></td><td>27 days</td><td>4–5 emails every 4–5 days</td><td>Consumer-friendly, concise, value-focused</td></tr>
        <tr><td><strong>Annual</strong></td><td>60 days</td><td>8–10 emails every 8–10 days</td><td>Higher-touch, more formal, higher-stakes messaging</td></tr>
      </tbody>
    </table>
    <h3 class="rc-subhead-sm">Additional Campaigns to Consider</h3>
    <table class="rc-table">
      <thead><tr><th>Segment</th><th>Recommended Approach</th></tr></thead>
      <tbody>
        <tr><td><strong>Student / low-value plans</strong></td><td>Friendly, casual language. Consider offering a pause or discount. These subscribers are more price-sensitive.</td></tr>
        <tr><td><strong>Enterprise / team plans</strong></td><td>Formal language. Reference the contract. Consider copying a CSM on late-stage emails. Keep the invoice open at window end rather than expiring immediately.</td></tr>
        <tr><td><strong>Trial-ending plans</strong></td><td>Separate campaign for subscriptions where a trial is ending with no payment method on file. This is onboarding, not recovery.</td></tr>
      </tbody>
    </table>
    <div class="rc-tip">
      <span class="rc-tipicon">&#128161;</span>
      <div><h4>Assign Plans to Campaigns</h4><p>After creating new campaigns, navigate to each Plan in your catalog and assign it to the correct campaign. Plans not manually assigned continue using your default. Double-check every plan is correctly assigned.</p></div>
    </div>

    <hr class="rc-divider" />

    <div class="rc-tip-badge">
      <div class="rc-tip-num">Tip 9</div>
      <div class="rc-tip-title">Use the Right Email Delivery Service for Your Dunning Emails</div>
    </div>
    <p class="rc-body-text">A beautifully branded, perfectly timed dunning email is useless if it lands in a spam folder. Email deliverability is as important as email content — and it's something many businesses overlook until recovery rates plateau unexpectedly.</p>
    <table class="rc-table">
      <thead><tr><th>Option</th><th>Best For</th><th>Notes</th></tr></thead>
      <tbody>
        <tr><td><strong>Recurly Default</strong></td><td>Most businesses starting out</td><td>Recurly sends on your behalf. Configure DMARC to remove the "via recurly.com" label from the sender address.</td></tr>
        <tr><td><strong>SendGrid</strong></td><td>Businesses already using SendGrid</td><td>Add your API key into Recurly. Templates built in Recurly, sent via SendGrid with full tracking and deliverability tools.</td></tr>
        <tr><td><strong>Mailchimp</strong></td><td>Businesses already using Mailchimp</td><td>Same approach as SendGrid. Build in Recurly, send via Mailchimp.</td></tr>
        <tr><td><strong>Braze</strong></td><td>Enterprise / sophisticated marketing stacks</td><td>Build and manage dunning templates in Braze. Recurly sends the trigger events; Braze handles the send.</td></tr>
      </tbody>
    </table>
    <div class="rc-tip">
      <span class="rc-tipicon">&#128161;</span>
      <div><h4>DMARC Matters More Than You Think</h4><p>Without proper DMARC configuration, your dunning emails may display "via recurly.com" in Gmail and Outlook — significantly reducing the perceived authenticity of the email and suppressing click-through rates.</p></div>
    </div>

    <hr class="rc-divider" />

    <div class="rc-tip-badge">
      <div class="rc-tip-num">Tip 10</div>
      <div class="rc-tip-title">Add an In-App 'Payment Overdue' Banner Within Your Product</div>
    </div>
    <p class="rc-body-text">Not every subscriber checks their email regularly — especially daily active users who live in your product. An in-app banner that surfaces when a subscriber logs in with a past-due invoice is one of the most effective, high-trust recovery channels available.</p>

    <div class="rc-dark-card"><h3>~60% click-through rate</h3><p>One Recurly customer saw approximately 60% click-through rate on their in-app payment overdue banner after launch — significantly higher than email alone. For products with daily active users, in-app is a primary recovery channel.</p></div>

    <h3 class="rc-subhead-sm">How to Implement</h3>
    <ul class="rc-body-ul">
      <li>Use Recurly Webhooks to listen for the <code>invoice.past_due</code> event</li>
      <li>When the event fires, store the dunning status in your application state</li>
      <li>Show a persistent, dismissible banner at the top of your app when a user logs in with a past-due invoice</li>
      <li>Link the banner directly to the billing update page — one click, straight there</li>
      <li>Dismiss the banner automatically when the invoice is recovered or payment method updated</li>
    </ul>

    <h3 class="rc-subhead-sm">Banner Copy by Stage</h3>
    <table class="rc-table">
      <thead><tr><th>Stage</th><th>Banner Text</th></tr></thead>
      <tbody>
        <tr><td><strong>Day 0–5</strong></td><td>We couldn't process your last payment. Update your billing to keep your access. [Update Now]</td></tr>
        <tr><td><strong>Day 10–20</strong></td><td>Your subscription expires in [X] days. Update your billing to avoid losing access. [Fix It Now]</td></tr>
        <tr><td><strong>Day 25–27</strong></td><td>Your subscription expires tomorrow. Last chance to keep your access. [Update Billing]</td></tr>
      </tbody>
    </table>

    <div class="rc-tip">
      <span class="rc-tipicon">&#128161;</span>
      <div><h4>Don't Restrict Access Too Early</h4><p>There's a difference between showing a warning banner (start Day 1) and restricting actual product access (most businesses delay to Day 3–5 or later). Lead with the banner as a trust-building prompt before using access restriction as a harder nudge.</p></div>
    </div>

    <hr class="rc-divider" />

    <h3 class="rc-subhead">Want a More Powerful In-App Experience?</h3>
    <p class="rc-body-text">Building and managing in-app payment recovery prompts yourself using Webhooks works well — but if you want more control over targeting, messaging, and timing without ongoing engineering effort, it's worth knowing that <strong>Recurly Engage</strong> is built specifically for this.</p>

    <div class="rc-card">
      <h3>&#9889; Recurly Engage — In-App Prompts for Payment Recovery</h3>
      <p>Recurly Engage is a subscriber engagement platform that lets you create, target, and launch in-app prompts — including payment failure recovery flows — without writing code for every change. It connects directly to Recurly's billing data, so it already knows which subscribers have past-due invoices and can trigger the right prompt at the right moment.</p>
      <p>For payment failure specifically, Engage supports overlay prompts, inline banners, interstitials, and paywall experiences — each configurable by dunning stage, subscriber segment, or plan type. You can A/B test messaging, set frequency limits, and track conversion without involving your engineering team every time.</p>
      <p>It's particularly useful if you want to move beyond a single "payment overdue" banner and deliver a more layered recovery experience — different messages for different subscriber segments, escalating at different points in the dunning window.</p>
    </div>

    <div class="rc-3col">
      <div class="rc-wi"><div class="rc-wi-icon">&#127919;</div><h4>Targeted by Dunning Status</h4><p>Prompts trigger automatically based on real-time Recurly billing data — no manual segment updates needed.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">&#129514;</div><h4>Built-in A/B Testing</h4><p>Test different messages, designs, and CTAs to find what converts best for your specific subscriber base.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">&#128640;</div><h4>No Code Changes to Launch</h4><p>Update messaging, timing, and targeting from the Engage dashboard — without engineering deployment for every iteration.</p></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">&#128216;</span>
      <div><h4>Learn More About Recurly Engage</h4><p>See the <a href="https://docs.recurly.com/recurly-engage/docs/failed-rebill" target="_blank">Recurly Engage Payment Failure use case</a> for a walkthrough of how to set up payment recovery prompts, or explore the <a href="https://docs.recurly.com/recurly-engage/" target="_blank">full Recurly Engage documentation</a>. If you're interested in whether Engage is included in your plan, reach out to your CSM.</p></div>
    </div>
  <div class="rc-sec-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-subscriber-engagement" class="rc-btn-prev">&larr; Subscriber Engagement</a>
    <span style="color:var(--gray);font-size:.85rem;font-weight:600">Page 5 of 7</span>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-metrics" class="rc-btn-next">Metrics &amp; Tracking &rarr;</a>
  </div>
  </div>

  <div class="rc-link-sec">
    <h3>&#128218; Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-management" class="rc-link-btn" target="_blank" rel="noopener noreferrer">&#128214; Dunning Management Docs</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-benchmarks" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#128202; Dunning Benchmarks</a>
    <a href="https://share.synthesia.io/7f58d816-a65c-42f4-950d-59b11953d1aa" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#127909; Trail Guide Video</a>
    <a href="https://navigate.recurly.com/event-hub/" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#127775; Join Global Office Hours</a>
    <a href="https://recurly.ondemand.goldcast.io/on-demand/a65f472f-9876-4736-9209-5b7b669de773" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#127925; On-Demand Webinar: Stop the Leak</a>
    <a href="https://docs.recurly.com/recurly-engage/docs/failed-rebill" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#9889; Recurly Engage: Payment Failure</a>
    <a href="https://docs.recurly.com/recurly-engage/" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#128196; Recurly Engage Docs</a>
  </div>
</div>
`}</HTMLBlock>

<br />
