---
title: 'Section 3: Churn & Retention'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
.rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif;max-width:960px;margin:0 auto;padding:0 20px 60px}
.rc-hero{background:var(--offblack);border-radius:16px;padding:52px 40px 44px;text-align:center;margin-bottom:0}
.rc-badge{display:inline-block;background:var(--orange);color:#fff;border-radius:20px;padding:6px 20px;font-size:12px;font-weight:800;letter-spacing:1px;text-transform:uppercase;margin-bottom:18px}
.rc-hero h1{font-size:2.3rem;font-weight:800;line-height:1.15;margin:0 0 12px;color:#fff}
.rc-hero>p{font-size:1rem;max-width:680px;margin:0 auto 28px;color:#CCC9B8;line-height:1.6}
.rc-hero-stats{display:flex;justify-content:center;gap:36px;flex-wrap:wrap}
.rc-num{font-size:1.7rem;font-weight:800;color:var(--orange)}
.rc-lbl{font-size:.76rem;color:#CCC9B8;text-transform:uppercase;letter-spacing:.5px}
.rc-nav{display:flex;flex-wrap:wrap;gap:8px;margin:22px 0 32px;padding:16px;background:var(--offwhite);border-radius:14px;border:1px solid var(--lightgray)}
.rc-nav a{display:inline-flex;align-items:center;gap:7px;padding:9px 13px;border-radius:10px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.83rem;font-weight:700;transition:all .2s}
.rc-nav a:hover{border-color:var(--orange);box-shadow:0 2px 8px rgba(255,130,0,.2);color:var(--offblack);text-decoration:none}
.rc-nav a.rc-active{background:var(--orange);border-color:var(--orange);color:#fff}
.rc-snum{display:inline-flex;align-items:center;justify-content:center;width:22px;height:22px;border-radius:50%;background:var(--offblack);color:var(--orange);font-size:11px;font-weight:800;flex-shrink:0}
.rc-nav a.rc-active .rc-snum{background:rgba(255,255,255,.2);color:#fff}
.rc-sec{margin-bottom:48px}
.rc-sec-header{display:flex;align-items:flex-start;gap:18px;margin-bottom:28px}
.rc-sec-icon{width:52px;height:52px;border-radius:14px;background:var(--orange);display:flex;align-items:center;justify-content:center;font-size:24px;flex-shrink:0}
.rc-sec-header h2{font-size:1.45rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
.rc-sec-header p{font-size:.9rem;color:var(--gray);margin:0;line-height:1.6}
.rc-card{background:#fff;border:1px solid var(--lightgray);border-radius:14px;padding:20px 22px;margin-bottom:16px;box-shadow:0 2px 6px rgba(13,13,11,.04)}
.rc-subhead{font-size:.98rem;font-weight:800;color:var(--offblack);margin:0 0 10px}
.rc-metric{background:#fff;border:1px solid var(--lightgray);border-radius:14px;padding:20px 22px;margin-bottom:14px}
.rc-metric-head{display:flex;align-items:center;gap:12px;margin-bottom:10px}
.rc-metric-icon{width:40px;height:40px;border-radius:10px;background:var(--offblack);color:var(--orange);font-size:18px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-metric h3{font-size:.96rem;font-weight:800;margin:0;color:var(--offblack)}
.rc-metric p{font-size:.85rem;color:var(--gray);margin:0 0 10px;line-height:1.6}
.rc-formula{background:var(--brightgray);border-radius:8px;padding:10px 14px;font-size:.83rem;font-family:monospace;color:var(--darkgray);margin-bottom:10px}
.rc-pills{display:flex;gap:8px;flex-wrap:wrap}
.rc-pill{padding:4px 12px;border-radius:20px;font-size:.75rem;font-weight:700;background:var(--offwhite);border:1px solid var(--lightgray);color:var(--darkgray)}
.rc-pill.down{background:rgba(22,163,74,.1);color:#15803d;border-color:#86efac}
.rc-churn-compare{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:16px}
.rc-churn-type{border-radius:12px;padding:17px 19px;border:1px solid var(--lightgray)}
.rc-churn-type.vol{background:#fff5f0;border-color:#fca5a5}
.rc-churn-type.inv{background:#fff6ee;border-color:#ffcb99}
.rc-churn-type h4{font-size:.9rem;font-weight:800;margin:0 0 6px}
.rc-churn-type.vol h4{color:#dc2626}
.rc-churn-type.inv h4{color:#b45309}
.rc-churn-type p{font-size:.83rem;color:var(--gray);line-height:1.5;margin:0 0 8px}
.rc-churn-type .rc-fix{font-size:.78rem;font-weight:700;color:var(--offblack)}
.rc-tip{background:#fff6ee;border:1px solid #ffcb99;border-radius:12px;padding:15px 17px;margin-bottom:16px;font-size:.87rem;color:var(--darkgray);line-height:1.6}
.rc-tip strong{color:var(--offblack)}
.rc-video-wrap{position:relative;width:100%;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:10px;margin-bottom:8px;background:var(--offblack)}
.rc-video-wrap iframe{position:absolute;top:0;left:0;width:100%;height:100%;border:0;overflow:hidden}
.rc-video-cap{font-size:.8rem;color:var(--gray);text-align:center;margin-bottom:4px;font-style:italic}
.rc-clip{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:14px;padding:16px 18px;margin-bottom:16px}
.rc-clip-label{display:inline-flex;align-items:center;gap:5px;background:var(--offblack);color:var(--orange);border-radius:6px;padding:3px 10px;font-size:.73rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;margin-bottom:10px}
.rc-clip p{font-size:.87rem;color:var(--gray);margin:0 0 10px;line-height:1.5}
.rc-clip-title{font-size:.93rem;font-weight:700;color:var(--offblack);margin:0 0 6px}
.rc-webinar-link{display:inline-flex;align-items:center;gap:6px;font-size:.83rem;font-weight:700;color:var(--orange);text-decoration:none}
.rc-webinar-link:hover{text-decoration:underline}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.87rem;text-decoration:none;border:1px solid var(--lightgray)}
.rc-btn-prev{background:#fff;color:var(--darkgray)}
.rc-btn-prev:hover{background:var(--brightgray);text-decoration:none}
.rc-btn-next{background:var(--orange);color:#fff;border-color:var(--orange)}
.rc-btn-next:hover{opacity:.92;text-decoration:none}
.rc-link-btn{background:var(--orange);color:#fff;border-color:var(--orange);margin:0 8px 8px 0}
.rc-link-btn:hover{opacity:.9;text-decoration:none}
.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
.rc-link-sec:hover{background:var(--brightgray);text-decoration:none}
.rc-resources{margin-top:32px}
.rc-resources h3{font-size:.84rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--gray);margin:0 0 12px}
@media(max-width:640px){.rc-hero{padding:30px 16px 26px}.rc-hero h1{font-size:1.65rem}.rc-churn-compare{grid-template-columns:1fr}.rc-hero-stats{gap:14px}.rc-sec-header{flex-direction:column}.rc-sec-nav{flex-direction:column;align-items:stretch}}
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">📊 Navigate · Launchpad Phase 2</div>
    <h1>Voluntary &amp; Involuntary Churn</h1>
    <p>Not all churn is the same — and knowing the difference is what separates reactive businesses from proactive ones. These metrics tell you why subscribers are leaving and what you can do about it.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Step 3</div><div class="rc-lbl">Phase 2</div></div>
      <div><div class="rc-num">2</div><div class="rc-lbl">Types of Churn</div></div>
      <div><div class="rc-num">↓</div><div class="rc-lbl">Both Should Trend Down</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two"><span class="rc-snum">🏠</span>Phase 2 Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-benchmarks-dashboard"><span class="rc-snum">1</span>Benchmarks &amp; Reporting</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-acquisition-metrics"><span class="rc-snum">2</span>Acquisition &amp; Decline</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-churn-metrics" class="rc-active"><span class="rc-snum">3</span>Churn Metrics</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-retention-metrics"><span class="rc-snum">4</span>Revenue &amp; Recovery</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-review"><span class="rc-snum">✓</span>Full Course Review</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">📉</div>
      <div>
        <h2>Understanding Why Subscribers Leave</h2>
        <p>Total churn tells you the size of your retention problem. Voluntary vs. Involuntary churn tells you the cause — and each requires a completely different solution. Treating them the same means solving for the wrong problem.</p>
      </div>
    </div>

    <div class="rc-churn-compare">
      <div class="rc-churn-type vol">
        <h4>👋 Voluntary Churn</h4>
        <p>Subscribers who actively chose to cancel. This reflects satisfaction, perceived value, and engagement with your product.</p>
        <p class="rc-fix">Fix with: Product improvements, better onboarding, pause options, cancellation save flows, loyalty offers.</p>
      </div>
      <div class="rc-churn-type inv">
        <h4>💳 Involuntary Churn</h4>
        <p>Subscribers lost due to payment failures — expired cards, insufficient funds, or bank declines. These subscribers didn't want to leave.</p>
        <p class="rc-fix">Fix with: Account Updater, Dunning optimization, Intelligent Retry, clearer payment failure emails.</p>
      </div>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">▶ Trail Guide: Voluntary &amp; Involuntary Churn Rate</p>
      <div class="rc-video-wrap">
        <iframe src="https://share.synthesia.io/embeds/videos/94ebc34a-579b-4129-9a0f-ee926d42a34a" loading="lazy" title="Navigate Launchpad — Churn Metrics" allow="encrypted-media; fullscreen;" allowfullscreen></iframe>
      </div>
      <p class="rc-video-cap">A walkthrough of the Churn benchmarks — how to find them, how to interpret the voluntary vs. involuntary split, and what actions to take based on what you see.</p>
    </div>

    <div class="rc-metric">
      <div class="rc-metric-head">
        <div class="rc-metric-icon">👋</div>
        <h3>Voluntary Churn Rate</h3>
      </div>
      <p>The percentage of subscribers who actively cancel each month. High voluntary churn signals a product-value mismatch — subscribers aren't finding enough reason to stay.</p>
      <div class="rc-formula">Subscribers who canceled ÷ Active subscribers (start of period) = Voluntary Churn Rate %</div>
      <div class="rc-pills">
        <span class="rc-pill down">↓ Lower is better</span>
        <span class="rc-pill">Check monthly</span>
        <span class="rc-pill">Analytics → Dashboards → Benchmarks</span>
      </div>
    </div>

    <div class="rc-metric">
      <div class="rc-metric-head">
        <div class="rc-metric-icon">💳</div>
        <h3>Involuntary Churn Rate</h3>
      </div>
      <p>The percentage of subscribers lost to dunning expiration. This is directly influenced by Account Updater and dunning configuration — if you enabled both in Phase 1, you should expect to see this metric improve.</p>
      <div class="rc-formula">Subscribers lost to payment failures ÷ Active subscribers (start of period) = Involuntary Churn Rate %</div>
      <div class="rc-pills">
        <span class="rc-pill down">↓ Lower is better</span>
        <span class="rc-pill">Check monthly</span>
        <span class="rc-pill">Analytics → Dashboards → Benchmarks</span>
      </div>
    </div>

    <div class="rc-clip">
      <div class="rc-clip-label">🎬 Where in the Webinar?</div>
      <p class="rc-clip-title">Deep Dive: Monitoring the Impact of Your Retention Strategy</p>
      <p>Fast-forward to the <strong>Churn Benchmarking</strong> section of this session. CSM Dan Shipley provides a walkthrough on using the three specific churn views (combined, voluntary, and involuntary) to diagnose business health and shares a real-world case study on how Account Updater directly lowers involuntary loss.</p>
      <a class="rc-webinar-link" href="https://navigate.recurly.com/lunch-and-learn/stack-up-benchmarks/" target="_blank" rel="noopener noreferrer">▶ Watch "Stack Up Against the Competition" On-Demand →</a>
    </div>

    <div class="rc-tip">
      <strong>💡 Separate your diagnosis from your treatment:</strong> If total churn is high but you don't know the voluntary/involuntary split, you might invest heavily in product improvements when the real problem is simply that Account Updater isn't enabled. Always look at the split first.
    </div>

    <div class="rc-card">
      <p class="rc-subhead">🔗 Connecting Churn to Phase 1 Work</p>
      <p style="font-size:.88rem;color:var(--gray);line-height:1.7;margin:0 0 10px">The Phase 1 optimizations you completed directly influence your involuntary churn rate. Here's how to trace the connection:</p>
      <p style="font-size:.87rem;line-height:1.6;color:var(--darkgray);margin:0 0 6px"><strong>Account Updater</strong> → Reduces involuntary churn by refreshing expired cards before renewals fail</p>
      <p style="font-size:.87rem;line-height:1.6;color:var(--darkgray);margin:0 0 6px"><strong>Dunning Optimization</strong> → Recovers failed invoices before they result in subscriber loss</p>
      <p style="font-size:.87rem;line-height:1.6;color:var(--darkgray);margin:0"><strong>Gateway Failover</strong> → Prevents outage-driven payment failures that would otherwise register as involuntary churn</p>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-acquisition-metrics">← Acquisition &amp; Decline</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-retention-metrics">Step 4: Revenue &amp; Recovery →</a>
    </div>

    <div class="rc-resources">
      <h3>Additional Resources</h3>
      <a class="rc-link-btn" href="https://docs.recurly.com/docs/subscriber-churn-benchmarks" target="_blank" rel="noopener noreferrer">📖 Churn Benchmarks Guide</a>
      <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">🎧 Webinars On-Demand</a>
      <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">✉ Contact Customer Support</a>
    </div>
  </div>

</div>
`}</HTMLBlock>

<br />
