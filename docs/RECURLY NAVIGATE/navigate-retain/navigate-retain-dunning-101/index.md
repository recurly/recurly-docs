---
title: 'Dunning 101: The Basics'
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
    <p>Recover more revenue, reduce passive churn, and build a dunning strategy that works quietly in the background.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">3&ndash;5%</div><div class="rc-lbl">Avg Recovery Uplift</div></div>
      <div><div class="rc-num">27%</div><div class="rc-lbl">Avg Recovery Rate</div></div>
      <div><div class="rc-num">Up to 40%</div><div class="rc-lbl">Of Churn Is Passive</div></div>
    </div>
  </div>
  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-basics" class="is-active"><span class="rc-snum">1</span> Dunning Basics</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-setup"><span class="rc-snum">2</span> Setup &amp; Configuration</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-email-strategy"><span class="rc-snum">3</span> Email Strategy</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-subscriber-engagement"><span class="rc-snum">4</span> Subscriber Engagement</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-advanced-configuration"><span class="rc-snum">5</span> Advanced Configuration</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-metrics"><span class="rc-snum">6</span> Metrics &amp; Tracking</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-strategy-and-resources"><span class="rc-snum">&#10003;</span> Strategy &amp; Resources</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">&#128260;</div>
      <div>
        <h2>Dunning Basics</h2>
        <p>What dunning is, how it works, why it matters, and where it fits in your revenue recovery toolkit.</p>
      </div>
    </div>

    <p class="rc-body-text">Dunning is Recurly's automated system for recovering failed subscription payments. When a renewal charge doesn't go through, dunning kicks in — retrying the payment at the optimal time and reaching out to the subscriber so they can update their billing information before their subscription expires.</p>

    <div class="rc-flow">
      <div class="rc-flow-node"><span class="rc-flow-icon">&#128179;</span><span class="rc-flow-lbl">Payment Fails</span><span class="rc-flow-sub">Invoice becomes past_due</span></div>
      <span class="rc-flow-arrow">&#8594;</span>
      <div class="rc-flow-node hl"><span class="rc-flow-icon">&#129302;</span><span class="rc-flow-lbl">Intelligent Retries</span><span class="rc-flow-sub">ML-powered timing</span></div>
      <span class="rc-flow-arrow">&#8594;</span>
      <div class="rc-flow-node hl"><span class="rc-flow-icon">&#128231;</span><span class="rc-flow-lbl">Dunning Emails</span><span class="rc-flow-sub">Customer outreach</span></div>
      <span class="rc-flow-arrow">&#8594;</span>
      <div class="rc-flow-node"><span class="rc-flow-icon">&#9989;</span><span class="rc-flow-lbl">Recovery or Expiry</span><span class="rc-flow-sub">Invoice resolved</span></div>
    </div>

    <div class="rc-3col">
      <div class="rc-wi"><div class="rc-wi-icon">&#129302;</div><h4>Intelligent Retries</h4><p>Recurly's ML engine analyzes transaction data to determine the optimal moment to retry a declined payment. It runs fully automatically — no setup required beyond configuring your dunning window.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">&#128235;</div><h4>Dunning Emails</h4><p>Automated email sequences sent to subscribers prompting them to update billing info. You control the day, template, and tone of every email in the sequence.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">&#128151;</div><h4>Dunning Window</h4><p>The time period during which Recurly retries payments and sends emails. Recurly recommends 27 days for monthly plans and 60 days for annual plans.</p></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">&#128161;</span>
      <div><h4>Key Distinction</h4><p>Retries and emails are independent systems. An email being sent does NOT trigger a retry — they run on separate schedules. This gives you full flexibility to optimize payment recovery timing and communication cadence independently.</p></div>
    </div>

    <h3 class="rc-subhead">Who enters the dunning process?</h3>
    <p class="rc-body-text">Any invoice that becomes <code>past_due</code> enters dunning. What happens next depends on the type of decline received from the payment gateway.</p>

    <table class="rc-table">
      <thead><tr><th>Failure Type</th><th>Common Example</th><th>Retries?</th><th>Emails?</th></tr></thead>
      <tbody>
        <tr><td><strong>Soft Decline</strong></td><td>Insufficient funds, card limit</td><td>&#9989; Yes &mdash; ML-optimized</td><td>&#9989; Yes &mdash; per your schedule</td></tr>
        <tr><td><strong>Hard Decline</strong></td><td>Invalid card number, fraud block</td><td>&#10060; Typically no</td><td>&#9989; Yes &mdash; send on Day 0</td></tr>
        <tr><td><strong>Any past_due Invoice</strong></td><td>Any failed renewal payment</td><td>If soft decline</td><td>&#9989; Yes &mdash; per your campaign</td></tr>
      </tbody>
    </table>

    <div class="rc-warning">
      <span class="rc-wicon">&#9888;&#65039;</span>
      <p><strong>Hard declines require fast action.</strong> Since Recurly typically won't retry hard declines, email is your only automated recovery tool. Make sure your first dunning email fires immediately on Day 0 for hard decline events — not delayed to Day 3 like soft declines.</p>
    </div>

    <hr class="rc-divider" />

    <h3 class="rc-subhead">Why dunning matters</h3>
    <p class="rc-body-text">Payment failures are a normal part of running a subscription business — industry-wide, 5–10% of subscription payments fail on first attempt. What separates high-performing businesses is what happens next.</p>

    <div class="rc-2col">
      <div class="rc-dark-card"><h3>3&ndash;5% uplift is the norm</h3><p>Recurly customers typically see a 3–5% uplift in dunning recovery rate after following the 10 optimization tips — from changes that take a few hours to implement.</p></div>
      <div class="rc-dark-card"><h3>Passive churn is the hidden problem</h3><p>Passive churn — losing subscribers due to failed payments rather than intent — can account for up to 40% of total churn. These are customers who want to stay subscribed.</p></div>
    </div>

    <h3 class="rc-subhead">Real customer results</h3>
    <div class="rc-result-grid">
      <div class="rc-result-card"><span class="rc-result-num">+12%</span><span class="rc-result-tag">Branding &amp; Window</span><p>Enhanced email branding, updated dunning window length, and optimized communication frequency.</p></div>
      <div class="rc-result-card"><span class="rc-result-num">+11%</span><span class="rc-result-tag">Window Extension</span><p>Extended the dunning window by 13 days and added emails reminding customers of the value they would lose.</p></div>
      <div class="rc-result-card"><span class="rc-result-num">+8%</span><span class="rc-result-tag">Email Frequency</span><p>Modified window length and adjusted frequency — leaving more days between each message.</p></div>
    </div>

    <div class="rc-dark-card"><h3>+279% recovery revenue in one month</h3><p>My Music Workshop implemented all 10 dunning best practices from scratch and saw a 279% increase in dunning recovery revenue in their first month.</p></div>

    <hr class="rc-divider" />

    <h3 class="rc-subhead">Where dunning fits in your recovery toolkit</h3>
    <table class="rc-table">
      <thead><tr><th>Tool</th><th>What It Does</th><th>Type</th></tr></thead>
      <tbody>
        <tr><td><strong>Account Updater</strong></td><td>Automatically updates expired or replaced card details before billing fails</td><td>Proactive</td></tr>
        <tr><td><strong>Expired Card Management</strong></td><td>Updates expired card info to prevent billing interruptions at renewal</td><td>Proactive</td></tr>
        <tr><td><strong>Intelligent Retries</strong></td><td>ML-optimized retry timing for declined payments — runs automatically within dunning</td><td>Reactive</td></tr>
        <tr><td><strong>Dunning Management</strong></td><td>Email sequences + retry window — the focus of this learning path</td><td>Reactive</td></tr>
        <tr><td><strong>Backup Payment Method</strong></td><td>Tries a secondary card on file if the primary payment method fails</td><td>Reactive</td></tr>
        <tr><td><strong>External Recovery</strong></td><td>Syncs successful recoveries from external systems back into Recurly</td><td>Reactive</td></tr>
      </tbody>
    </table>
  <div class="rc-sec-nav">
    <span class="rc-btn-disabled">&#127919; Start</span>
    <span style="color:var(--gray);font-size:.85rem;font-weight:600">Page 1 of 7</span>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-setup" class="rc-btn-next">Setup &amp; Configuration &rarr;</a>
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