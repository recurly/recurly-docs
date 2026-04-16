---
title: Dunning - API TEST
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html><html lang="en"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><title>Dunning Management 101 — Why Use It?</title><link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet"></head><body style="background:#f5f5f0;margin:0;"><style>
:root {
  --yellow: #FFD706;
  --orange: #FF8200;
  --vermillion: #FF5810;
  --salmon: #FF9D88;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
}
.rc-guide { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; color: var(--offblack); max-width: 900px; margin: 0 auto; }
.rc-hero { background: var(--offblack); color: white; padding: 48px 40px; border-radius: 16px 16px 0 0; text-align: center; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; }
.rc-subtitle { color: var(--lightgray); font-size: 16px; }
.rc-badge { background: var(--yellow); color: var(--offblack); padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; }
.rc-flywheel-launch { background: var(--lightgray); color: var(--offblack); }
.rc-flywheel-acquire { background: var(--yellow); color: var(--offblack); }
.rc-flywheel-retain { background: var(--salmon); color: var(--offblack); }
.rc-flywheel-scale { background: var(--orange); color: var(--offblack); }
.rc-stats { display: flex; justify-content: center; gap: 32px; margin-top: 24px; }
.rc-stat { color: var(--lightgray); font-size: 14px; }
.rc-stat-num { color: var(--yellow); font-weight: 700; font-size: 20px; display: block; }
.rc-nav { display: flex; gap: 0; background: var(--brightgray); padding: 0; overflow-x: auto; border-bottom: 2px solid var(--lightgray); }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: var(--gray); font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: var(--offblack); background: var(--offwhite); }
.rc-nav a.is-active { color: var(--offblack); font-weight: 600; border-bottom-color: var(--yellow); background: var(--offwhite); }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: var(--lightgray); color: var(--gray); display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: var(--yellow); color: var(--offblack); }
.rc-sec { padding: 40px; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: var(--yellow); border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px; flex-shrink: 0; }
.rc-sec-header h2 { font-size: 24px; margin: 0 0 4px; font-weight: 700; }
.rc-sec-header p { color: var(--gray); margin: 0; font-size: 15px; }
.rc-card { background: var(--offwhite); border-radius: 12px; padding: 28px; margin-bottom: 20px; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: var(--darkgray); line-height: 1.7; margin: 0 0 12px; font-size: 15px; }
.rc-card p:last-child { margin-bottom: 0; }
.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: var(--offblack); }
.rc-steps { display: flex; flex-direction: column; gap: 16px; margin: 20px 0; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: var(--offwhite); border-radius: 12px; padding: 20px; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: 14px; flex-shrink: 0; }
.rc-step-content h4 { margin: 0 0 4px; font-size: 16px; font-weight: 600; }
.rc-step-content p { margin: 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-tip { border-left: 4px solid var(--yellow); background: var(--offwhite); padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-tip strong { color: var(--offblack); }
.rc-tip p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-warning { border-left: 4px solid var(--orange); background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-warning strong { color: var(--offblack); }
.rc-warning p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-checklist { background: var(--offwhite); border-radius: 12px; padding: 24px; margin: 20px 0; }
.rc-cl-header { font-size: 16px; font-weight: 600; margin-bottom: 16px; }
.rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
.rc-cb { width: 20px; height: 20px; border-radius: 4px; border: 2px solid var(--lightgray); flex-shrink: 0; cursor: pointer; margin-top: 2px; }
.rc-cli label { font-size: 14px; color: var(--darkgray); line-height: 1.5; cursor: pointer; }
.rc-3col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
.rc-2col { display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px; margin: 20px 0; }
.rc-wi { background: var(--offwhite); border-radius: 12px; padding: 24px; text-align: center; }
.rc-wi h4 { font-size: 16px; margin: 12px 0 8px; font-weight: 600; }
.rc-wi p { font-size: 13px; color: var(--gray); margin: 0; }
.rc-sec-nav { display: flex; justify-content: space-between; padding: 0 40px 40px; }
.rc-btn-prev, .rc-btn-next { display: inline-flex; align-items: center; gap: 8px; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; transition: all 0.2s; }
.rc-btn-prev { background: var(--brightgray); color: var(--offblack); }
.rc-btn-next { background: var(--yellow); color: var(--offblack); }
.rc-btn-prev:hover { background: var(--lightgray); }
.rc-btn-next:hover { filter: brightness(0.95); }
.rc-btn-disabled { opacity: 0.4; pointer-events: none; }
.rc-link-btn { display: inline-flex; align-items: center; gap: 8px; padding: 10px 20px; background: var(--brightgray); border-radius: 8px; text-decoration: none; color: var(--offblack); font-size: 14px; font-weight: 500; margin: 4px; transition: all 0.2s; }
.rc-link-btn:hover { background: var(--lightgray); }
.rc-link-sec { padding: 32px 40px; background: var(--brightgray); border-radius: 0 0 16px 16px; }
.rc-link-sec h3 { font-size: 18px; margin: 0 0 16px; font-weight: 600; }
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1rpQ40zAs49C7xuFkSau7-UimkPNxwMa2" alt="Retain stage" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;">
    <span class="rc-badge">Subscriptions</span>
    <h1>Dunning Management 101</h1>
    <p class="rc-subtitle">Master dunning configuration to maximize revenue recovery and reduce involuntary churn across your subscription business.</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">24</span> min read</div>
    </div>
  </div>

  <div class="rc-nav">
    <a href="/docs/dunning-management-101-1">
      <span class="rc-snum">1</span> What Is It?
    </a>
    <a href="/docs/dunning-management-101-2" class="is-active">
      <span class="rc-snum">2</span> Why Use It?
    </a>
    <a href="/docs/dunning-management-101-3">
      <span class="rc-snum">3</span> Things to Consider
    </a>
    <a href="/docs/dunning-management-101-4">
      <span class="rc-snum">4</span> When Not to Use It
    </a>
    <a href="/docs/dunning-management-101-5">
      <span class="rc-snum">5</span> How to Enable It
    </a>
    <a href="/docs/dunning-management-101-6">
      <span class="rc-snum">6</span> Tracking Impact
    </a>
    <a href="/docs/dunning-management-101-7">
      <span class="rc-snum">7</span> Pitch to Leadership
    </a>
  </div>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">
        <!-- lightbulb-02.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1dQpFxnm38HN6ZNeRBSjP3R4Tt--R_wON" alt="lightbulb icon" style="width:28px;height:28px;">
      </div>
      <div>
        <h2>Why Use Dunning Management?</h2>
        <p>Understand the business case for optimized dunning — from revenue recovery to subscriber retention and lifetime value growth.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>The Silent Revenue Leak You Can't Afford to Ignore</h3>
      <p>Involuntary churn — subscribers lost due to failed payments rather than a conscious decision to cancel — typically accounts for 8–12% of total churn for subscription businesses. Unlike voluntary churn, where a customer makes an active choice, involuntary churn is almost entirely preventable. Every subscriber who churns because of an expired credit card, an insufficient-funds decline, or a bank fraud filter is revenue that slipped through a crack in your billing infrastructure.</p>
      <p>Without an optimized dunning strategy, Recurly's default behavior will eventually cancel subscriptions after failed payment attempts. But "default" and "optimized" are worlds apart. The difference between a 3-day dunning window and a 14-day window with intelligent retry timing can mean the difference between recovering a few percent of failed payments versus recovering the majority of them. For a business processing $10M in annual recurring revenue, even a 2–3 percentage point improvement in recovery translates directly to hundreds of thousands of dollars retained annually — with zero incremental acquisition cost.</p>
      <p>Dunning management isn't just a billing feature. It's a core retention lever that directly protects the recurring revenue base you've already invested heavily to build.</p>
    </div>

    <div class="rc-subhead">The Five Strategic Reasons to Optimize Dunning</div>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div class="rc-step-content">
          <h4>Recover Revenue That Would Otherwise Vanish</h4>
          <p>Every failed transaction is a potential lost subscriber. Recurly's advanced dunning campaigns use machine-learning-optimized retry logic to attempt charges at the times most likely to succeed — factoring in card type, bank behavior, time zones, and historical success patterns. Merchants who extend their dunning window and enable intelligent retries consistently recover significantly more revenue than those using static, manually configured retry schedules. This recovered revenue flows directly to your bottom line with no additional customer acquisition cost.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div class="rc-step-content">
          <h4>Preserve Subscriber Relationships and Lifetime Value</h4>
          <p>When a subscriber involuntarily churns, you don't just lose their current month's payment — you lose their entire remaining lifetime value. If your average subscriber stays for 18 months at $30/month, a single involuntary churn event costs $540 in future revenue. Dunning management preserves these relationships by giving the payment issue time to resolve (cards get renewed, bank holds get lifted, funds get deposited) while keeping the subscriber engaged through thoughtful communication. The subscriber often never realizes how close they came to losing access.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div class="rc-step-content">
          <h4>Reduce the Burden on Support and Success Teams</h4>
          <p>Without automated dunning, failed payments generate support tickets. Subscribers contact your team confused about lost access, or CSMs must manually reach out to salvage accounts. Well-configured dunning campaigns handle the communication automatically — sending branded, escalating emails that inform subscribers of the issue, provide a direct link to update their payment method, and remind them of the value they'll lose. This frees your support and customer success teams to focus on proactive retention rather than reactive firefighting.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div class="rc-step-content">
          <h4>Improve Financial Forecasting and Revenue Predictability</h4>
          <p>High involuntary churn introduces noise into your revenue forecasts. When 8–12% of your subscriber base is at risk of uncontrolled loss each billing cycle, your finance team is forecasting with significant uncertainty. Optimized dunning brings predictability to your recovery rates. Once you've established a mature dunning configuration, you can reliably forecast what percentage of failed payments will be recovered, making MRR projections far more accurate. This helps finance, leadership, and investor relations all operate with greater confidence.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div class="rc-step-content">
          <h4>Compound Retention Gains Across the Flywheel</h4>
          <p>Dunning management doesn't operate in isolation — it amplifies every other retention initiative. Your cancel-save flows only work if subscribers make it to the cancel button voluntarily; otherwise, involuntary churn silently removes them before your retention offers ever trigger. Your Account Updater integration catches card changes proactively, and dunning handles the remaining failures. Together with Recurly's AI/ML revenue recovery engine, an optimized dunning configuration creates a multi-layered defense against passive churn that compounds over time.</p>
        </div>
      </div>
    </div>

    <div class="rc-subhead">The Cost of Inaction: What You Lose Without Optimization</div>

    <div class="rc-3col">
      <div class="rc-wi">
        <!-- wallet-01.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zog70GXF8MGG0LH8XR1pClQj4Xp41PBe" alt="wallet icon" style="width:28px;height:28px;">
        <h4>Lost Revenue</h4>
        <p>Default dunning windows are often too short to capture payments that would succeed with a longer retry period. Short windows leave money on the table every single billing cycle.</p>
      </div>
      <div class="rc-wi">
        <!-- heart-hand.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zK3mlZEE50CjiIH_pQo1ytqaz3gVvgjP" alt="heart hand icon" style="width:28px;height:28px;">
        <h4>Damaged Relationships</h4>
        <p>Subscribers who are silently canceled due to payment failure feel abandoned. When they discover they've lost access, the trust damage is difficult to repair — even if they resubscribe.</p>
      </div>
      <div class="rc-wi">
        <!-- bar-chart-11.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=18clYe_73mC2yDcICqfLcwtDvAXSiuAN4" alt="bar chart icon" style="width:28px;height:28px;">
        <h4>Inflated Churn Metrics</h4>
        <p>High involuntary churn distorts your overall churn rate, making it harder to isolate and address voluntary churn drivers. Your retention story becomes muddied.</p>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: The Dunning Window Is Your Biggest Lever</strong>
      <p>Recurly data consistently shows that merchants who extend their dunning window beyond the default — particularly to 14 days or more — see measurably higher recovery rates. A longer window gives more time for card updates to propagate, for temporary bank holds to clear, and for subscribers to respond to email prompts. If you only change one thing about your dunning setup, extend the window. It's the single highest-impact configuration change you can make.</p>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Don't Confuse Recovery Rate with Churn Rate</strong>
      <p>When evaluating dunning performance, keep your metrics clear. The 8–12% figure represents the typical involuntary churn rate — the percentage of subscribers who enter dunning due to payment failures. Your <em>recovery rate</em> is the percentage of those dunning subscribers you successfully recover. A strong dunning setup might recover 50–70% of failed payments, meaning the net involuntary churn impact drops significantly. Track both numbers to tell the complete story to leadership.</p>
    </div>

    <div class="rc-subhead">Who Benefits from Optimized Dunning?</div>

    <div class="rc-2col">
      <div class="rc-card">
        <h3>Revenue Operations & Billing Teams</h3>
        <p>RevOps managers gain a measurable, high-ROI lever to plug revenue leaks without requiring engineering resources or new subscriber acquisition. Billing administrators get a clear configuration framework — dunning campaigns, retry schedules, and email templates — that they can tune and iterate on independently. Optimized dunning becomes one of the fastest ways to demonstrate operational impact on the revenue line.</p>
      </div>
      <div class="rc-card">
        <h3>Retention Marketers & Customer Success</h3>
        <p>Dunning emails are not just payment reminders — they are retention touchpoints. Retention marketers can use branded, value-driven dunning messages to reinforce why the subscriber signed up in the first place. CSMs gain visibility into at-risk accounts during the dunning window, allowing targeted outreach to high-value subscribers. When dunning is treated as a retention marketing channel, recovery rates climb.</p>
      </div>
      <div class="rc-card">
        <h3>Product & Engineering Teams</h3>
        <p>Product managers can architect graceful degradation experiences — showing in-app banners or limiting features for subscribers in dunning rather than cutting off access entirely. Engineers can implement Webhook listeners for dunning events, trigger custom workflows, and build integrations that keep the subscriber engaged throughout the recovery process. Dunning becomes a product experience, not just a billing process.</p>
      </div>
      <div class="rc-card">
        <h3>Finance & Executive Leadership</h3>
        <p>Executives see the direct P&L impact: recovered revenue drops straight to the bottom line with zero CAC. Finance teams get more predictable MRR forecasts when involuntary churn is managed rather than left to chance. The ROI story is straightforward — dunning optimization typically delivers returns within the first billing cycle, making it one of the fastest-payback retention investments available.</p>
      </div>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header">✅ Quick Self-Assessment: Is Your Dunning Optimized?</div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Have you extended your dunning window beyond the default setting (ideally 14+ days)?</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Are you using Recurly's ML-optimized retry logic rather than static retry schedules?</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Have you customized your dunning email templates with branding and value reminders?</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Do you have separate dunning campaigns configured for different plan tiers or subscriber segments?</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Are your dunning emails authenticated with SPF, DKIM, and DMARC for deliverability?</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Do you track recovery rate, time-to-recovery, and net involuntary churn as distinct metrics?</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Have you implemented in-app or on-site notifications for subscribers in dunning?</label>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Navigate Insight: The Retention Flywheel Effect</strong>
      <p>Dunning management sits at the heart of Recurly's Retain stage in the Subscription Growth Flywheel. When combined with Account Updater (which proactively catches card changes before they cause failures), cancel-save flows (which address voluntary churn), and AI/ML revenue recovery (which optimizes retry timing), you create a compounding retention engine. Each layer reduces the load on the next, driving down overall churn and increasing subscriber lifetime value with every billing cycle.</p>
    </div>

  </div>

  <div class="rc-sec-nav">
    <a href="/docs/dunning-management-101-1" class="rc-btn-prev">← Previous</a>
    <a href="/docs/dunning-management-101-3" class="rc-btn-next">Next →</a>
  </div>

  <div class="rc-link-sec">
    <h3>Additional Resources</h3>
    <a href="https://docs.google.com/document/d/126f5qxy8Ss4YfFpwZfebQgEHYBgj0f9t6NPOUbhuUBU/edit?tab=t.0" class="rc-link-btn">📄 Dunning Management Documentation</a>
    <a href="https://docs.recurly.com/docs/dunning" class="rc-link-btn">📘 Recurly Dunning Docs</a>
    <a href="https://recurly.com/research/churn-rate-benchmarks/" class="rc-link-btn">📊 Churn Rate Benchmarks</a>
  </div>

</div></body></html>
`}</HTMLBlock>

<br />
