---
title: 'Dunning 101: Strategy & resources'
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
    <p>Strategic prompts to deepen your thinking, a full action checklist, and everything you need to go further.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">6</div><div class="rc-lbl">Strategy Prompts</div></div>
      <div><div class="rc-num">11</div><div class="rc-lbl">Checklist Items</div></div>
      <div><div class="rc-num">2</div><div class="rc-lbl">On-Demand Resources</div></div>
    </div>
  </div>
  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-basics"><span class="rc-snum">1</span> Dunning Basics</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-setup"><span class="rc-snum">2</span> Setup &amp; Configuration</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-email-strategy"><span class="rc-snum">3</span> Email Strategy</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-subscriber-engagement"><span class="rc-snum">4</span> Subscriber Engagement</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-advanced-configuration"><span class="rc-snum">5</span> Advanced Configuration</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-metrics"><span class="rc-snum">6</span> Metrics &amp; Tracking</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-strategy-and-resources" class="is-active"><span class="rc-snum">&#10003;</span> Strategy &amp; Resources</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">&#129517;</div>
      <div>
        <h2>Strategy &amp; Resources</h2>
        <p>Strategic prompts to deepen your thinking, a full action checklist, and everything you need to go further.</p>
      </div>
    </div>

    <p class="rc-body-text">Use these prompts to have better conversations with your team, your Recurly CSM, and your subscribers — and to build a dunning approach that truly fits your business model.</p>

    <div class="rc-tip">
      <span class="rc-tipicon">&#128172;</span>
      <div><h4>Do You Know Your Passive Churn Rate?</h4><p>Most subscription businesses track total churn without separating passive churn (payment failures) from active churn (intentional cancellations). Pull your renewal decline rate from Recurly analytics and compare it to your total churn rate — the gap is your involuntary churn number, and it's the addressable opportunity for your dunning investment.</p></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">&#128172;</span>
      <div><h4>Are You Treating All Subscribers the Same?</h4><p>A monthly consumer subscriber at $12/month and an annual enterprise account at $12,000/year have very different relationships with your product — and very different tolerances for billing friction. Have you created distinct dunning experiences for your most valuable subscribers?</p></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">&#128172;</span>
      <div><h4>Is a Long Dunning Window Giving Away Free Access?</h4><p>This concern stops many businesses from extending their window — but it doesn't have to. Recurly Webhooks let you decouple dunning status from product access. You can run a full 27-day recovery window while restricting access after a 3–5 day grace period. What's the right grace period for your business model?</p></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">&#128172;</span>
      <div><h4>Is Email Still Your Primary Recovery Channel?</h4><p>If your subscribers spend more time in your app than their inbox, in-app banners and push notifications may be your highest-conversion recovery channel. Have you measured where your subscribers actually respond?</p></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">&#128172;</span>
      <div><h4>Should You Offer a Pause Before Letting a Subscription Lapse?</h4><p>Subscribers who pause are significantly more likely to reactivate than those who cancel outright. Is a pause option available in your late-stage dunning CTAs?</p></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">&#128172;</span>
      <div><h4>How Often Are You Reviewing Your Dunning Setup?</h4><p>Card expiry patterns change seasonally. New payment methods introduce new failure types. Review your dunning setup at least once a year — and after any major pricing, product, or subscriber base change.</p></div>
    </div>

    <hr class="rc-divider" />

    <h3 class="rc-subhead">Action Checklist</h3>
    <ul class="rc-checklist">
      <li><div class="rc-check"></div> Audit your current setup against all 10 best practices using the Dunning Optimization Checklist</li>
      <li><div class="rc-check"></div> Calculate your passive churn rate separately from active churn</li>
      <li><div class="rc-check"></div> Create at least two campaigns — monthly (27 days) and annual (60 days)</li>
      <li><div class="rc-check"></div> Update email branding to match your current product design</li>
      <li><div class="rc-check"></div> Implement 4–5 distinct email templates with escalating urgency and personalization</li>
      <li><div class="rc-check"></div> Add dynamic variables to every email (name, amount, days remaining, card type)</li>
      <li><div class="rc-check"></div> Implement an in-app payment overdue banner using Recurly Webhooks</li>
      <li><div class="rc-check"></div> Set up correct SPF, DKIM, and DMARC records for email deliverability</li>
      <li><div class="rc-check"></div> Track Dunning Recovery Rate monthly and benchmark against industry peers</li>
      <li><div class="rc-check"></div> Watch the Trail Guide: Dunning Done Right</li>
      <li><div class="rc-check"></div> Watch the on-demand webinar: Stop the Leak</li>
    </ul>

    <hr class="rc-divider" />

    <h3 class="rc-subhead">Video Resources</h3>

    <div class="rc-dark-card">
      <h3>&#9654;&#65039; Trail Guide: Easy Wins — Dunning Done Right</h3>
      <p>A 5-minute video walkthrough of dunning fundamentals and quick wins. Watch this first for a quick orientation before diving deeper.</p>
      <p style="margin-top:10px"><a href="https://share.synthesia.io/7f58d816-a65c-42f4-950d-59b11953d1aa" target="_blank">Watch the Trail Guide &rarr;</a></p>
    </div>

    <div class="rc-dark-card">
      <h3>&#9654;&#65039; On-Demand Webinar: Stop the Leak — How to Optimize Dunning for Growth</h3>
      <p>A 60-minute deep dive into dunning strategy led by Hannah Wheeldon, Strategic CSM at Recurly. Covers all 10 tips with real customer examples, live Recurly UI walkthroughs, and benchmarking guidance.</p>
      <p style="margin-top:10px"><a href="https://recurly.ondemand.goldcast.io/on-demand/a65f472f-9876-4736-9209-5b7b669de773" target="_blank">Watch the Webinar &rarr;</a></p>
    </div>

    <div class="rc-card" style="background:var(--offblack);border-color:var(--yellow)">
      <h3 style="color:var(--yellow)">&#128361;&#65039; Ready for a Deeper Conversation?</h3>
      <p style="color:var(--lightgray)">Join a live Dunning Office Hours session with Recurly's CS team to walk through your specific setup and get personalized recommendations. Bring your current campaign config and recovery metrics — the team will help identify your highest-impact optimizations.</p>
      <p style="margin-top:14px"><a href="https://navigate.recurly.com/event-hub/" target="_blank" style="background:var(--yellow);color:var(--offblack);padding:10px 20px;border-radius:8px;font-weight:700;font-size:.88rem;text-decoration:none;display:inline-block">Register for Office Hours &rarr;</a></p>
    </div>
  <div class="rc-sec-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-101-metrics" class="rc-btn-prev">&larr; Metrics &amp; Tracking</a>
    <span style="color:var(--gray);font-size:.85rem;font-weight:600">Page 7 of 7</span>
    <span class="rc-btn-disabled">&#127881; Complete!</span>
  </div>
  </div>

  <div class="rc-link-sec">
    <h3>&#128218; Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-management" class="rc-link-btn" target="_blank" rel="noopener noreferrer">&#128214; Dunning Management Docs</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-benchmarks" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#128202; Dunning Benchmarks</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-optimization-checklist" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#9989; Optimization Checklist</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/retry-logic" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#128260; Intelligent Retries</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-configuration-for-3ds-2-declines" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#128274; 3DS Dunning Setup</a>
    <a href="https://navigate.recurly.com/event-hub/" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#127775; Join Global Office Hours</a>
    <a href="https://recurly.ondemand.goldcast.io/on-demand/a65f472f-9876-4736-9209-5b7b669de773" class="rc-link-btn rc-link-btn-sec" target="_blank" rel="noopener noreferrer">&#127909; On-Demand Webinar</a>
  </div>
</div>
`}</HTMLBlock>

<br />
