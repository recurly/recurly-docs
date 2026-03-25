---
title: 'Section 6: Metrics'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<HTMLBlock>{\`
<style>
  .rc-guide{--yellow:#FFD706;--orange:#FF8200;--vermillion:#FF5810;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
  .rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px;margin-bottom:0}
  .rc-badge{display:inline-block;background:var(--orange);color:#fff;border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
  .rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
  .rc-hero>p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 32px;color:var(--lightgray)}
  .rc-hero-stats{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}
  .rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:8px;padding:10px 14px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s,background .2s,color .2s}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack);text-decoration:none}
  .rc-nav a.rc-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-sec{margin-bottom:56px}
  .rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--orange)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
  .rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-metric-card{background:var(--offwhite);border-radius:16px;padding:24px;border:1px solid var(--lightgray);margin-bottom:20px;transition:box-shadow .2s}
  .rc-metric-card:hover{box-shadow:0 4px 16px rgba(13,13,11,.08)}
  .rc-metric-header{display:flex;align-items:center;gap:14px;margin-bottom:14px}
  .rc-metric-icon{width:44px;height:44px;border-radius:12px;background:var(--offblack);color:var(--yellow);font-size:20px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-metric-header h3{font-size:1rem;font-weight:800;color:var(--offblack);margin:0 0 3px}
  .rc-metric-header p{font-size:.8rem;color:var(--gray);margin:0}
  .rc-metric-body{font-size:.87rem;color:var(--darkgray);line-height:1.6}
  .rc-metric-body strong{color:var(--offblack)}
  .rc-metric-row{display:grid;grid-template-columns:1fr 1fr 1fr;gap:10px;margin-top:14px}
  .rc-metric-pill{background:var(--brightgray);border-radius:10px;padding:10px 12px}
  .rc-metric-pill .pill-label{font-size:10px;font-weight:700;color:var(--gray);text-transform:uppercase;letter-spacing:.5px;margin-bottom:3px}
  .rc-metric-pill .pill-val{font-size:.82rem;color:var(--offblack);font-weight:700}
  .rc-phase-banner{background:var(--darkgray);border:2px solid var(--orange);border-radius:16px;padding:28px 32px;margin-bottom:24px;display:flex;align-items:center;gap:20px}
  .rc-phase-icon{font-size:36px;flex-shrink:0}
  .rc-phase-banner h3{font-size:1.05rem;font-weight:800;color:var(--orange);margin:0 0 4px;text-transform:uppercase;letter-spacing:.5px}
  .rc-phase-banner p{font-size:.88rem;color:var(--lightgray);margin:0;line-height:1.5}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;margin-bottom:24px;display:flex;gap:16px;align-items:flex-start}
  .rc-tipicon{font-size:24px;flex-shrink:0}
  .rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
  .rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-complete-banner{background:var(--offblack);border-radius:16px;padding:40px;text-align:center;margin-bottom:24px}
  .rc-complete-banner h2{font-size:1.8rem;font-weight:800;color:var(--yellow);margin:10px 0 10px}
  .rc-complete-banner p{color:var(--lightgray);font-size:.95rem;margin:0}
  .rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:28px}
  .rc-cl-header{padding:16px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:center;gap:10px;background:var(--offblack)}
  .rc-cl-header h3{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
  .rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:flex-start;gap:14px}
  .rc-cli:last-child{border-bottom:none}
  .rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;margin-top:1px;background:#fff;display:flex;align-items:center;justify-content:center;font-size:12px;color:var(--gray)}
  .rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}
  .rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
  .rc-phase-tag{display:inline-flex;align-items:center;gap:6px;background:var(--darkgray);color:var(--orange);border-radius:20px;padding:4px 14px;font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;margin-bottom:20px}
  .rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray);text-align:center}
  .rc-wi-icon{font-size:30px;margin-bottom:10px}
  .rc-wi h4{font-size:.88rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
  .rc-wi p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none;border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  .rc-link-sec:hover{background:var(--brightgray)}
  @media(max-width:640px){
    .rc-hero h1{font-size:1.7rem}
    .rc-2col,.rc-3col,.rc-metric-row{grid-template-columns:1fr}
    .rc-hero{padding:36px 20px 32px}
    .rc-hero-stats{gap:20px}
    .rc-nav,.rc-sec-nav,.rc-sec-header,.rc-phase-banner{flex-direction:column}
    .rc-sec-nav{align-items:stretch}
  }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">📊 Phase 2: Mastering Metrics</div>
    <h1>Navigate Launchpad</h1>
    <p>Phase 1 is complete — now let's turn your Recurly data into your most powerful growth tool.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">6</div><div class="rc-lbl">Core Metrics</div></div>
      <div><div class="rc-num">Phase 2</div><div class="rc-lbl">Mastering Metrics</div></div>
      <div><div class="rc-num">~30</div><div class="rc-lbl">Min to Complete</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-welcome"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-production-testing"><span class="rc-snum">1</span>Production Testing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-dunning"><span class="rc-snum">2</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-account-updater"><span class="rc-snum">3</span>Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-branding"><span class="rc-snum">4</span>Branding</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a class="rc-active" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-metrics"><span class="rc-snum">6</span>Metrics & Growth</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-phase-tag">📊 Phase 2 · Weeks 7–12</div>

    <div class="rc-sec-header">
      <div class="rc-sec-icon">📊</div>
      <div>
        <h2>Mastering Your Subscription Metrics</h2>
        <p>Data doesn't drive decisions on its own — you have to know which numbers to watch, what they mean, and how to act on them. This module covers the six metrics every subscription business should track.</p>
      </div>
    </div>

    <div class="rc-phase-banner">
      <div class="rc-phase-icon">🎓</div>
      <div>
        <h3>Welcome to Phase 2</h3>
        <p>You've optimized your Recurly setup. Now it's time to build your data instincts. The six metrics in this module are the ones Recurly's most successful merchants track consistently — and use to make confident, strategic decisions about growth, retention, and revenue.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📍 Where to Find Your Metrics in Recurly</h3>
      <p style="font-size:0.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">All six metrics below are available in the <strong>Analytics section</strong> of your Recurly admin. The <strong>Benchmarks Dashboard</strong> is a great starting point — it shows your key performance indicators alongside industry benchmarks so you can see how you compare to peers in your category.</p>
      <p style="font-size:0.92rem;color:var(--darkgray);line-height:1.6;margin:0;">Navigate to <strong>Analytics → Benchmarks</strong> to see your metrics side by side with industry data. This context is invaluable when setting targets and identifying areas for improvement.</p>
    </div>

    <h3 class="rc-subhead">📈 Your 6 Core Subscription Metrics</h3>

    <div class="rc-metric-card">
      <div class="rc-metric-header">
        <div class="rc-metric-icon">1️⃣</div>
        <div>
          <h3>Subscriber Acquisition Rate</h3>
          <p>How many new subscribers you gain each month</p>
        </div>
      </div>
      <div class="rc-metric-body">
        <p><strong>What it tells you:</strong> Your acquisition rate is the clearest signal of whether your top-of-funnel is working. It reflects the combined effect of your marketing, promotions, trials, and checkout experience.</p>
        <p style="margin-top:10px;"><strong>Where to find it:</strong> Analytics → Subscriber Acquisition</p>
        <p style="margin-top:10px;"><strong>What to do with it:</strong> If acquisition is flat or declining, investigate your checkout conversion rate and marketing funnel. If it's growing, understand which channels are driving it so you can double down.</p>
        <div class="rc-metric-row">
          <div class="rc-metric-pill"><div class="pill-label">Influenced by</div><div class="pill-val">Marketing & promotions</div></div>
          <div class="rc-metric-pill"><div class="pill-label">Check frequency</div><div class="pill-val">Monthly</div></div>
          <div class="rc-metric-pill"><div class="pill-label">Found in</div><div class="pill-val">Analytics → Acquisition</div></div>
        </div>
      </div>
    </div>

    <div class="rc-metric-card">
      <div class="rc-metric-header">
        <div class="rc-metric-icon">2️⃣</div>
        <div>
          <h3>Sign-Up Decline Rate</h3>
          <p>How often initial payment attempts fail during checkout</p>
        </div>
      </div>
      <div class="rc-metric-body">
        <p><strong>What it tells you:</strong> A high sign-up decline rate means you're losing potential subscribers at the exact moment they're trying to give you money. This could be due to checkout friction, fraud filters set too aggressively, or card-not-present decline patterns.</p>
        <p style="margin-top:10px;"><strong>What to do with it:</strong> A rate above industry benchmarks is a signal to review your checkout configuration, payment retry logic, and gateway settings. Small improvements here can meaningfully increase your effective acquisition rate.</p>
        <div class="rc-metric-row">
          <div class="rc-metric-pill"><div class="pill-label">Good sign</div><div class="pill-val">Declining over time</div></div>
          <div class="rc-metric-pill"><div class="pill-label">Watch for</div><div class="pill-val">Spikes vs. baseline</div></div>
          <div class="rc-metric-pill"><div class="pill-label">Found in</div><div class="pill-val">Analytics → Acquisition</div></div>
        </div>
      </div>
    </div>

    <div class="rc-metric-card">
      <div class="rc-metric-header">
        <div class="rc-metric-icon">3️⃣</div>
        <div>
          <h3>Voluntary Churn Rate</h3>
          <p>The rate at which subscribers actively choose to cancel</p>
        </div>
      </div>
      <div class="rc-metric-body">
        <p><strong>What it tells you:</strong> Voluntary churn is the clearest signal of whether subscribers find enough value to stay. High voluntary churn can indicate pricing issues, product-market fit gaps, or lack of engagement — and the cancellation reasons your subscribers give are your most direct source of intelligence.</p>
        <p style="margin-top:10px;"><strong>What to do with it:</strong> Enable cancellation surveys to capture exit reasons. Look for patterns — if the same reason appears repeatedly, prioritize addressing it. Consider offering pause or skip options before cancel to retain subscribers who just need a break.</p>
        <div class="rc-metric-row">
          <div class="rc-metric-pill"><div class="pill-label">Data source</div><div class="pill-val">Cancellation surveys</div></div>
          <div class="rc-metric-pill"><div class="pill-label">Check frequency</div><div class="pill-val">Monthly</div></div>
          <div class="rc-metric-pill"><div class="pill-label">Found in</div><div class="pill-val">Analytics → Churn</div></div>
        </div>
      </div>
    </div>

    <div class="rc-metric-card">
      <div class="rc-metric-header">
        <div class="rc-metric-icon">4️⃣</div>
        <div>
          <h3>Involuntary Churn Rate</h3>
          <p>Subscribers lost due to payment failures — not cancellations</p>
        </div>
      </div>
      <div class="rc-metric-body">
        <p><strong>What it tells you:</strong> Involuntary churn is the most actionable category — because it's almost entirely preventable with the right tools. If your dunning is optimized and Account Updater is enabled, this rate should be meaningfully lower than benchmarks.</p>
        <p style="margin-top:10px;"><strong>What to do with it:</strong> Compare your involuntary churn rate against the Recurly benchmark for your industry. If it's higher than average, start with your dunning retry schedule, email open rates, and Account Updater status. These three levers together drive the biggest improvements.</p>
        <div class="rc-metric-row">
          <div class="rc-metric-pill"><div class="pill-label">Key tool</div><div class="pill-val">Dunning + AU</div></div>
          <div class="rc-metric-pill"><div class="pill-label">Target</div><div class="pill-val">Below benchmark</div></div>
          <div class="rc-metric-pill"><div class="pill-label">Found in</div><div class="pill-val">Analytics → Churn</div></div>
        </div>
      </div>
    </div>

    <div class="rc-metric-card">
      <div class="rc-metric-header">
        <div class="rc-metric-icon">5️⃣</div>
        <div>
          <h3>Renewal Invoice Paid Rate</h3>
          <p>The percentage of renewal invoices that are successfully paid</p>
        </div>
      </div>
      <div class="rc-metric-body">
        <p><strong>What it tells you:</strong> This is your ultimate revenue reliability indicator. A high renewal invoice paid rate means your billing engine is working — payments are being authorized, dunning is recovering failures, and your subscribers are staying current. It directly informs revenue forecasting.</p>
        <p style="margin-top:10px;"><strong>What to do with it:</strong> Track this month over month. Dips indicate either a surge in payment failures or a decline in dunning effectiveness. Use it as an early warning signal — a downward trend here means revenue is about to follow.</p>
        <div class="rc-metric-row">
          <div class="rc-metric-pill"><div class="pill-label">Importance</div><div class="pill-val">Forecasting signal</div></div>
          <div class="rc-metric-pill"><div class="pill-label">Target</div><div class="pill-val">Consistently high</div></div>
          <div class="rc-metric-pill"><div class="pill-label">Found in</div><div class="pill-val">Analytics → Renewals</div></div>
        </div>
      </div>
    </div>

    <div class="rc-metric-card">
      <div class="rc-metric-header">
        <div class="rc-metric-icon">6️⃣</div>
        <div>
          <h3>Recovered Revenue</h3>
          <p>The total revenue saved after invoices initially failed</p>
        </div>
      </div>
      <div class="rc-metric-body">
        <p><strong>What it tells you:</strong> Recovered Revenue shows you how much subscription revenue would have been lost — and wasn't, because of tools like Account Updater, Dunning, and Backup Payment Method. It's both a success metric and a diagnostic one: it tells you how well your recovery stack is performing and where there's still opportunity to improve.</p>
        <p style="margin-top:10px;"><strong>Where to find it:</strong> Analytics → Churn Management → Recovered Revenue. The dashboard breaks down recovery by method (AU, dunning, customer action) so you can see exactly where your wins are coming from.</p>
        <div class="rc-metric-row">
          <div class="rc-metric-pill"><div class="pill-label">Sources</div><div class="pill-val">AU, Dunning, BPM</div></div>
          <div class="rc-metric-pill"><div class="pill-label">Target</div><div class="pill-val">Growing each month</div></div>
          <div class="rc-metric-pill"><div class="pill-label">Found in</div><div class="pill-val">Analytics → Churn Mgmt</div></div>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Pro Tip · Use Benchmarks, Not Just Absolutes</h4>
        <p>Numbers in isolation are less useful than numbers in context. Recurly's Benchmarks Dashboard lets you compare each metric against industry averages for your subscription category. Use it to identify whether your performance is strong, average, or needs improvement relative to peers — not just whether the number went up or down last month.</p>
      </div>
    </div>

    <div class="rc-complete-banner">
      <div style="font-size:48px;">🎊</div>
      <h2>You've Completed Navigate Launchpad!</h2>
      <p>Over the past 90 days, you've tested your production environment, optimized your revenue recovery stack, branded your customer communications, and built a strong understanding of the metrics that drive subscription growth. That's no small thing — well done.</p>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Phase 2 Checklist: Metrics & Growth</h3></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Visited and bookmarked the Benchmarks Dashboard<span>Analytics → Benchmarks</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Reviewed your Subscriber Acquisition Rate and identified key drivers<span>Compare against benchmarks for your category</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Reviewed your Sign-Up Decline Rate and identified any action items<span>Spikes above benchmark warrant checkout review</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Reviewed Voluntary Churn Rate and enabled cancellation surveys<span>Exit reason data is essential for retention strategy</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Reviewed Involuntary Churn Rate — confirmed AU and dunning are working<span>Cross-reference with dunning recovery and AU data</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Reviewed Renewal Invoice Paid Rate and established a baseline<span>This is your primary recurring revenue health indicator</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Reviewed Recovered Revenue dashboard and noted AU + dunning breakdown<span>Analytics → Churn Management → Recovered Revenue</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Set a monthly cadence to review all 6 metrics<span>Block 30 minutes each month to review and act</span></div></div>
    </div>

    <h3 class="rc-subhead">🚀 What's Next After Launchpad?</h3>
    <div class="rc-3col">
      <div class="rc-wi"><div class="rc-wi-icon">📅</div><h4>Monthly Metrics Scorecard</h4><p>Watch for your first Monthly Metrics Scorecard two Tuesdays after your 90-day production mark. It's your personalized monthly performance report.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🎓</div><h4>Navigate Office Hours</h4><p>Join live Office Hours and Lunch & Learns to go deeper on Recurly features, hear from other merchants, and get your questions answered.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🔮</div><h4>More Learning Paths</h4><p>Navigate continues beyond Launchpad with advanced learning paths on features like Pause, Backup Payment Methods, Billing Insights, and more.</p></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-gateway-failover">← Gateway Failover</a>
      <span class="rc-btn-disabled">🎉 Launchpad Complete!</span>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://navigate.recurly.com/beyond-the-dashboard-reporting/" target="_blank" rel="noopener noreferrer">▶ Reporting That Drives Growth</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/using-benchmarks-strategically/" target="_blank" rel="noopener noreferrer">📊 Using Benchmarks Strategically</a>
    <a class="rc-link-btn rc-link-sec" href="https://go.recurly.com/Recurly-Navigate-Metrics-Cheatsheet.html" target="_blank" rel="noopener noreferrer">📋 Metrics Cheatsheet</a>
    <a class="rc-link-btn rc-link-sec" href="https://recurly.com/events/subscriptionsessions-on-demand/" target="_blank" rel="noopener noreferrer">🎧 Subscription Sessions On-Demand</a>
  </div>
</div>
\`}</HTMLBlock>
`}</HTMLBlock>

<br />
