---
title: 'Section 5: Phase 2 Review'
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
.rc-celebration{background:linear-gradient(135deg,var(--offblack) 0%,#1a0f00 100%);border-radius:16px;padding:44px 36px;text-align:center;margin-bottom:28px;border:2px solid rgba(255,130,0,.3)}
.rc-celebration h2{font-size:1.8rem;font-weight:800;color:#fff;margin:0 0 10px}
.rc-celebration p{font-size:.96rem;color:#CCC9B8;margin:0 auto;max-width:560px;line-height:1.7}
.rc-cel-emoji{font-size:48px;margin-bottom:14px;display:block}
.rc-two-phase{display:grid;grid-template-columns:1fr 1fr;gap:18px;margin-bottom:28px}
.rc-phase-summary{border-radius:14px;padding:22px}
.rc-phase-summary.p1{background:var(--offblack);border:2px solid var(--yellow)}
.rc-phase-summary.p2{background:var(--offblack);border:2px solid var(--orange)}
.rc-phase-summary h3{font-size:1rem;font-weight:800;margin:0 0 14px}
.rc-phase-summary.p1 h3{color:var(--yellow)}
.rc-phase-summary.p2 h3{color:var(--orange)}
.rc-recap-item{display:flex;align-items:flex-start;gap:9px;padding:7px 0;border-bottom:1px solid rgba(255,255,255,.07);font-size:.84rem;color:#CCC9B8}
.rc-recap-item:last-child{border-bottom:none}
.rc-ri-dot{width:22px;height:22px;border-radius:50%;font-size:10px;font-weight:800;display:flex;align-items:center;justify-content:center;flex-shrink:0;margin-top:1px}
.rc-ri-dot.y{background:var(--yellow);color:var(--offblack)}
.rc-ri-dot.o{background:var(--orange);color:#fff}
.rc-safe-sender{background:var(--offblack);border:1px solid var(--yellow);border-radius:12px;padding:16px 20px;margin-bottom:20px;display:flex;align-items:center;gap:15px}
.rc-safe-sender p{font-size:.86rem;color:#fff;margin:0;line-height:1.5}
.rc-safe-sender strong{color:var(--yellow)}
.rc-next-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:16px}
.rc-next-card{background:#fff;border:1px solid var(--lightgray);border-radius:12px;padding:17px 19px;display:flex;flex-direction:column}
.rc-next-card h4{font-size:.9rem;font-weight:800;color:var(--offblack);margin:0 0 6px}
.rc-next-card p{font-size:.83rem;color:var(--gray);line-height:1.5;margin:0 0 14px;flex-grow:1}
.rc-tip{background:#fff6ee;border:1px solid #ffcb99;border-radius:12px;padding:15px 17px;margin-bottom:16px;font-size:.87rem;color:var(--darkgray);line-height:1.6}
.rc-tip strong{color:var(--offblack)}
.rc-video-wrap{position:relative;width:100%;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:10px;margin-bottom:8px;background:var(--offblack)}
.rc-video-wrap iframe{position:absolute;top:0;left:0;width:100%;height:100%;border:0;overflow:hidden}
.rc-video-cap{font-size:.8rem;color:var(--gray);text-align:center;margin-bottom:4px;font-style:italic}
.rc-kpi-table{width:100%;border-collapse:collapse;margin-bottom:18px;font-size:.85rem}
.rc-kpi-table th{background:var(--offblack);color:var(--brightgray);font-size:.75rem;text-transform:uppercase;letter-spacing:.5px;padding:10px 14px;text-align:left}
.rc-kpi-table td{padding:10px 14px;border-bottom:1px solid var(--brightgray);color:var(--darkgray);vertical-align:top}
.rc-kpi-table tr:last-child td{border-bottom:none}
.rc-kpi-table tr:nth-child(even) td{background:var(--offwhite)}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.87rem;text-decoration:none;border:1px solid var(--lightgray)}
.rc-btn-prev{background:#fff;color:var(--darkgray)}
.rc-btn-prev:hover{background:var(--brightgray);text-decoration:none}
.rc-btn-next{background:var(--orange);color:#fff;border-color:var(--orange)}
.rc-btn-next:hover{opacity:.92;text-decoration:none}
.rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default;pointer-events:none;border-color:var(--lightgray)}
.rc-link-btn{background:var(--orange);color:#fff;border-color:var(--orange);margin:0 8px 8px 0}
.rc-link-btn:hover{opacity:.9;text-decoration:none}
.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
.rc-link-sec:hover{background:var(--brightgray);text-decoration:none}
.rc-link-yellow{background:var(--yellow);color:var(--offblack);border-color:var(--yellow)}
.rc-link-yellow:hover{opacity:.9;text-decoration:none}
.rc-resources{margin-top:32px}
.rc-resources h3{font-size:.84rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--gray);margin:0 0 12px}
@media(max-width:640px){.rc-hero{padding:30px 16px 26px}.rc-hero h1{font-size:1.65rem}.rc-two-phase,.rc-next-grid{grid-template-columns:1fr}.rc-hero-stats{gap:14px}.rc-sec-header{flex-direction:column}.rc-sec-nav{flex-direction:column;align-items:stretch}}
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">📊 Navigate · Launchpad Complete</div>
    <h1>Full Course Review</h1>
    <p>You've completed both phases of Launchpad. Here's a recap of everything you've built — and what comes next to keep the momentum going.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">2</div><div class="rc-lbl">Phases Complete</div></div>
      <div><div class="rc-num">9</div><div class="rc-lbl">Modules Finished</div></div>
      <div><div class="rc-num">🎉</div><div class="rc-lbl">Launchpad Done</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two"><span class="rc-snum">🏠</span>Phase 2 Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-benchmarks-dashboard"><span class="rc-snum">1</span>Benchmarks &amp; Reporting</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-acquisition-metrics"><span class="rc-snum">2</span>Acquisition &amp; Decline</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-churn-metrics"><span class="rc-snum">3</span>Churn Metrics</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-retention-metrics"><span class="rc-snum">4</span>Revenue &amp; Recovery</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-review" class="rc-active"><span class="rc-snum">✓</span>Full Course Review</a>
  </nav>

  <div class="rc-sec">

    <div class="rc-celebration">
      <span class="rc-cel-emoji">🎉</span>
      <h2>You've Completed Launchpad!</h2>
      <p>From production testing and dunning configuration to benchmarking your KPIs and understanding your revenue recovery funnel — you've done the work that sets high-performing subscription businesses apart. Recurly is now fully optimized and fully understood.</p>
    </div>

    <p class="rc-subhead" style="margin-bottom:14px">🗂 Everything You've Accomplished</p>
    <div class="rc-two-phase">
      <div class="rc-phase-summary p1">
        <h3>⚙️ Phase 1 · Optimization</h3>
        <div class="rc-recap-item"><div class="rc-ri-dot y">1</div>Final Production Testing — validated your checkout end-to-end</div>
        <div class="rc-recap-item"><div class="rc-ri-dot y">2</div>Dunning Optimization — Intelligent Retry, recovery emails, expiration rules</div>
        <div class="rc-recap-item"><div class="rc-ri-dot y">3</div>Account Updater — proactive card refresh before renewals fail</div>
        <div class="rc-recap-item"><div class="rc-ri-dot y">4</div>Branding — on-brand emails, invoices, and dunning communications</div>
        <div class="rc-recap-item"><div class="rc-ri-dot y">5</div>Gateway Failover — automatic rerouting when primary gateway is down</div>
      </div>
      <div class="rc-phase-summary p2">
        <h3>📊 Phase 2 · Mastering Metrics</h3>
        <div class="rc-recap-item"><div class="rc-ri-dot o">1</div>Benchmarks Dashboard — found KPIs in Analytics → Dashboards → Benchmarks</div>
        <div class="rc-recap-item"><div class="rc-ri-dot o">2</div>Acquisition &amp; Sign-Up Decline Rate — growth metrics, checkout friction</div>
        <div class="rc-recap-item"><div class="rc-ri-dot o">3</div>Voluntary &amp; Involuntary Churn — why subscribers leave and how to act on it</div>
        <div class="rc-recap-item"><div class="rc-ri-dot o">4</div>Renewal &amp; Recovery — Paid rate, Dunning recovery, and Renewal decline</div>
      </div>
    </div>

    <p class="rc-subhead" style="margin-bottom:12px">📋 Your KPI Quick Reference</p>
    <table class="rc-kpi-table">
      <thead>
        <tr>
          <th>Metric</th>
          <th>What It Measures</th>
          <th>Direction</th>
          <th>Linked to Phase 1?</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>Acquisition Rate</strong></td>
          <td>New paid subs / Active subs (start of period)</td>
          <td>↑ Higher</td>
          <td>No — driven by marketing &amp; pricing</td>
        </tr>
        <tr>
          <td><strong>Sign-Up Decline Rate</strong></td>
          <td>Failed unique transaction attempts / total attempts</td>
          <td>↓ Lower</td>
          <td>Partially — Gateway Failover, 3DS setup</td>
        </tr>
        <tr>
          <td><strong>Voluntary Churn Rate</strong></td>
          <td>Subscribers who canceled / Active subs (start of period)</td>
          <td>↓ Lower</td>
          <td>No — product &amp; experience driven</td>
        </tr>
        <tr>
          <td><strong>Involuntary Churn Rate</strong></td>
          <td>Subs lost to dunning expiration / Active subs (start of period)</td>
          <td>↓ Lower</td>
          <td>Yes — Account Updater, Dunning</td>
        </tr>
        <tr>
          <td><strong>Renewal Invoice Paid Rate</strong></td>
          <td>Successfully paid renewals / all renewals issued</td>
          <td>↑ Higher</td>
          <td>Yes — all Phase 1 tools contribute</td>
        </tr>
        <tr>
          <td><strong>Dunning Recovery Rate</strong></td>
          <td>Invoices recovered / invoices entering dunning</td>
          <td>↑ Higher</td>
          <td>Yes — directly tied to dunning config</td>
        </tr>
      </tbody>
    </table>

    <p class="rc-subhead" style="margin-bottom:14px">🚀 What Comes Next</p>
    
    <div class="rc-safe-sender">
      <div style="font-size: 24px;">📧</div>
      <p><strong>Never miss an update:</strong> Please add <strong>RecurlyNavigate@Recurly.com</strong> to your contact list. This ensures you always receive Navigate updates, exclusive invites, and your personalized learning paths.</p>
    </div>

    <div class="rc-next-grid">
      <div class="rc-next-card">
        <h4>✉ Your Customer Success Team</h4>
        <p>Your CSM is your strategic partner. Join a live <strong>Global Office Hours</strong> session to ask questions around strategy, share learnings with other merchants, and stay current with new features.</p>
        <a class="rc-link-btn" style="font-size:.81rem;padding:8px 14px" href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">Join Office Hours</a>
      </div>
      <div class="rc-next-card">
        <h4>🎧 Spotlight &amp; On-Demand</h4>
        <p>Watch our <strong>Customer Spotlight Series</strong> for peer-led leadership sessions, or revisit the Navigate webinar library anytime your team needs a technical refresher.</p>
        <a class="rc-link-btn rc-link-sec" style="font-size:.81rem;padding:8px 14px" href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">Watch Sessions</a>
      </div>
      <div class="rc-next-card">
        <h4>🤖 Compass AI</h4>
        <p>Recurly's AI-powered assistant inside the admin. Ask it questions about your account, interpret your metrics, or get configuration recommendations — available 24/7.</p>
        <a class="rc-link-btn rc-link-sec" style="font-size:.81rem;padding:8px 14px" href="https://docs.recurly.com" target="_blank" rel="noopener noreferrer">Explore Compass AI</a>
      </div>
      <div class="rc-next-card">
        <h4>🎓 Proactive Learning Paths</h4>
        <p>Keep an eye on your inbox! We will proactively provide additional <strong>Navigate Learning Paths</strong> tailored to your individual progress and performance in Recurly.</p>
        <a class="rc-link-btn rc-link-sec" style="font-size:.81rem;padding:8px 14px" href="mailto:RecurlyNavigate@Recurly.com?subject=Whitelisting%20Recurly%20Navigate">Whitelist Our Email</a>
      </div>
    </div>

    <div class="rc-card" style="margin-top:24px;">
      <p class="rc-subhead">📋 Revisiting Your Monthly Metrics Scorecard</p>
      <p style="font-size:.87rem; color:var(--gray); line-height:1.6; margin-bottom:16px;">Watch this trail guide as it walks you step-by-step through your Monthly Metrics Scorecard. You will begin receiving your personalized snapshot via email on the <strong>second Tuesday of the month</strong> after you have been in production for <strong>90 days</strong>.</p>
      <div class="rc-video-wrap">
        <iframe src="https://share.synthesia.io/embeds/videos/a9ab0aa1-ef60-4b08-aaa8-95c0275e245f" loading="lazy" title="Understanding Your Monthly Metrics Scorecard" allow="encrypted-media; fullscreen;" allowfullscreen></iframe>
      </div>
      <p class="rc-video-cap">A guided walkthrough on how to read and act on your monthly performance data.</p>
    </div>

    <div class="rc-tip" style="margin-top:28px;">
      <strong>💡 Keep the cadence going:</strong> Treat your Benchmarks Dashboard like a monthly scorecard — review it at the start of each month, compare to the prior period, and flag any metric that moved more than expected.
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two-retention-metrics">← Revenue &amp; Recovery</a>
      <span class="rc-btn-disabled">🎉 You've Completed Launchpad!</span>
    </div>

    <div class="rc-resources">
      <h3>All Your Launchpad Resources</h3>
      <a class="rc-link-btn rc-link-yellow" href="https://go.recurly.com/Recurly_Navigate-Launchpad-Complete-Cheatsheet.html" target="_blank" rel="noopener noreferrer">⬇ Full Launchpad Cheatsheet</a>
      <a class="rc-link-btn" href="https://go.recurly.com/Recurly-Navigate-Metrics-Cheatsheet.html" target="_blank" rel="noopener noreferrer">⬇ Metrics Cheatsheet</a>
      <a class="rc-link-btn rc-link-sec" href="https://go.recurly.com/recurly_navigate_resource_guide.html" target="_blank" rel="noopener noreferrer">📖 Navigate Resource Guide</a>
      <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">🎧 Events &amp; Webinars</a>
      <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">✉ Contact Customer Support</a>
    </div>
  </div>

</div>
`}</HTMLBlock>

<br />