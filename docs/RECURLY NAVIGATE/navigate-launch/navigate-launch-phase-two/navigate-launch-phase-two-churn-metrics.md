---
title: 'Section 3: Churn & Retention'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html>

<html>
<head>
<meta charset="UTF-8" />
<style>
  .rc-guide{
    --yellow:#FFD706;--orange:#FF8200;--vermillion:#FF5810;--salmon:#FF9D88;
    --offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;
    --brightgray:#F1EFE3;--offwhite:#FFFDF2;
    font-family:'Segoe UI',system-ui,sans-serif;
  }
  *{box-sizing:border-box}
  body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
  .rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px}
  .rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
  .rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
  .rc-hero>p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 32px;color:var(--lightgray)}
  .rc-hero-stats{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}
  .rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:8px;padding:10px 14px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s,background .2s,color .2s}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack);text-decoration:none}
  .rc-nav a.rc-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack);box-shadow:0 2px 10px rgba(255,215,6,.25)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-sec{margin-bottom:56px}
  .rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
  .rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:26px}
  .rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray);text-align:center}
  .rc-wi-icon{font-size:30px;margin-bottom:10px}
  .rc-wi h4{font-size:.88rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
  .rc-wi p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
  .rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start;transition:box-shadow .2s}
  .rc-step:hover{box-shadow:0 4px 16px rgba(13,13,11,.08)}
  .rc-sbadge{width:38px;height:38px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-sbadge-dark{width:38px;height:38px;border-radius:10px;background:var(--darkgray);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
  .rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}
  .rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
  .rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start;margin-bottom:24px}
  .rc-wicon{font-size:20px;flex-shrink:0}
  .rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-opt{background:var(--offwhite);border-radius:14px;border:1px solid var(--lightgray);padding:18px;transition:border-color .2s,box-shadow .2s}
  .rc-opt:hover{border-color:var(--yellow);box-shadow:0 2px 12px rgba(255,215,6,.2)}
  .rc-oicon{font-size:22px;margin-bottom:8px}
  .rc-opt h4{font-size:.92rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
  .rc-opt p{font-size:.82rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-tag{display:inline-block;margin-top:10px;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;background:var(--offblack);color:var(--yellow)}
  .rc-tag-green{background:#2E7D32;color:#fff}
  .rc-stat-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-stat{background:var(--offblack);border-radius:14px;padding:24px 16px;text-align:center}
  .rc-stat-num{font-size:1.5rem;font-weight:800;color:var(--yellow)}
  .rc-stat-label{font-size:.78rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px;margin-top:4px}
  .rc-phase-tag{display:inline-flex;align-items:center;gap:6px;background:var(--offblack);color:var(--yellow);border-radius:20px;padding:4px 14px;font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;margin-bottom:20px}
  .rc-handoff{background:var(--darkgray);border:2px solid var(--yellow);border-radius:16px;padding:28px 32px;margin-bottom:28px;display:flex;align-items:flex-start;gap:20px}
  .rc-handoff-icon{font-size:36px;flex-shrink:0}
  .rc-handoff h3{font-size:1.05rem;font-weight:800;color:var(--yellow);margin:0 0 6px;text-transform:uppercase;letter-spacing:.5px}
  .rc-handoff p{font-size:.88rem;color:var(--lightgray);margin:0;line-height:1.55}
  .rc-handoff a{color:var(--yellow);font-weight:700}
  .rc-complete{background:var(--offblack);border-radius:16px;padding:40px;text-align:center;margin-bottom:28px;color:#fff}
  .rc-complete h2{font-size:1.8rem;font-weight:800;margin:12px 0 10px;color:var(--yellow)}
  .rc-complete p{color:var(--lightgray);font-size:.95rem;margin:0}
  .rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:28px}
  .rc-cl-header{padding:16px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:center;gap:10px;background:var(--offblack)}
  .rc-cl-header h3{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
  .rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;gap:14px;align-items:flex-start}
  .rc-cli:last-child{border-bottom:none}
  .rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;margin-top:1px;background:#fff;display:flex;align-items:center;justify-content:center;font-size:12px;color:var(--gray)}
  .rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}
  .rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
  .video-wrap{position:relative;overflow:hidden;aspect-ratio:1920/1080;border-radius:14px}
  .video-wrap iframe{position:absolute;width:100%;height:100%;top:0;left:0;border:none;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none;border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}
  .rc-btn-next{background:var(--yellow);color:var(--offblack);border-color:var(--yellow)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0;transition:opacity .2s}
  .rc-link-btn:hover{opacity:.85;text-decoration:none}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  .rc-link-sec:hover{background:var(--brightgray)}
  @media(max-width:640px){
    .rc-hero h1{font-size:1.7rem}
    .rc-3col,.rc-2col,.rc-stat-grid{grid-template-columns:1fr}
    .rc-hero{padding:36px 20px 32px}
    .rc-hero-stats{gap:20px}
    .rc-nav,.rc-sec-nav,.rc-sec-header,.rc-handoff{flex-direction:column}
    .rc-sec-nav{align-items:stretch}
  }
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">📊 Launchpad Phase 2</div>
    <h1>Mastering Metrics</h1>
    <p>Turn your Recurly data into decisions. Learn the 8 benchmark KPIs, 4 reporting tools, and the strategies that power subscription growth.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">8</div><div class="rc-lbl">Benchmark KPIs</div></div>
      <div><div class="rc-num">4</div><div class="rc-lbl">Reporting Tools</div></div>
      <div><div class="rc-num">6 wks</div><div class="rc-lbl">Weeks 7–12</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-launchpad-phase2-welcome"><span class="rc-snum">1</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-launchpad-phase2-reporting-tools"><span class="rc-snum">2</span>Reporting Tools</a>
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-launchpad-phase2-acquisition"><span class="rc-snum">3</span>Acquisition & Growth</a>
    <a class="rc-active" href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-launchpad-phase2-churn"><span class="rc-snum">4</span>Churn & Retention</a>
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-launchpad-phase2-revenue-recovery"><span class="rc-snum">5</span>Revenue Recovery</a>
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-launchpad-phase2-rewind-review"><span class="rc-snum">✓</span>Rewind & Review</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-phase-tag">📊 Phase 2 · Week 10</div>

    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔄</div>
      <div>
        <h2>Churn &amp; Retention: Understanding Why Subscribers Leave</h2>
        <p>Retaining subscribers is just as important as acquiring them. Three churn metrics tell you why people leave — and which tools can bring them back.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🧩 The Three Types of Churn</h3>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 16px;">Recurly breaks churn into three types — and that distinction is critical, because each requires a completely different response strategy. Understanding your split between voluntary and involuntary is the first step toward an effective retention plan.</p>
    </div>

    <div class="rc-3col">
      <div class="rc-wi"><div class="rc-wi-icon">📉</div><h4>Total Churn Rate</h4><p>All subscribers lost — payment failures and cancellations combined. Your broadest retention health signal.<br><br><em>Churned ÷ total subscribers = %</em></p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🚫</div><h4>Involuntary Churn Rate</h4><p>Subscribers lost because a payment failed — expired cards, insufficient funds, processor declines. Preventable with the right tools.<br><br><em>Involuntary churned ÷ total subscribers = %</em></p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🚪</div><h4>Voluntary Churn Rate</h4><p>Subscribers who actively chose to cancel. Your clearest signal on perceived value and satisfaction.<br><br><em>Voluntary churned ÷ total subscribers = %</em></p></div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🔗 How Your Phase 1 Tools Reduce Involuntary Churn</h3>
      <p style="font-size:.88rem;color:var(--darkgray);line-height:1.6;margin:0 0 16px;">Involuntary churn is almost entirely preventable. The three mechanisms Recurly uses — all configured in Phase 1 — work together to ensure the highest rate of paid invoices:</p>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Expiration Date Changes</h3><p>Recurly detects upcoming card expirations and proactively updates billing info before the next renewal attempt.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Account Updater (Phase 1, Week 3)</h3><p>Requests updated card info before scheduled payments AND after any failure — both proactive and reactive. If your involuntary churn is high and AU isn't enabled, that's your first lever.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Dunning Retries (Phase 1, Week 2)</h3><p>Your configured retry sequence works through the dunning window with multiple attempts and email touchpoints. Longer windows mean more recovery opportunities.</p></div></div>
      </div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Churn data takes time to complete.</strong> Depending on your dunning cycle, churn data can take up to <strong>60 days to finalize</strong>. The current month will always appear to have lower churn than prior months — this is expected. Never compare current-month raw counts to a prior full month.</p>
    </div>

    <h3 class="rc-subhead">📍 Where to Find Your Churn Dashboards</h3>
    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge-dark">1</div><div><h3>Subscriber Churn Benchmarks — for context</h3><p><strong>Analytics → Churn Management → Subscriber Churn Benchmarks</strong><br>Your combined, voluntary, and involuntary churn rates vs. industry peers. Use this to know whether your churn is a real problem or within normal range for your segment.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge-dark">2</div><div><h3>Subscriber Churn Analysis — for root cause</h3><p><strong>Analytics → Churn Management → Subscriber Churn Analysis</strong><br>Set a custom date range and timeframe (weekly or monthly) to spot patterns and seasonality. You'll see: overall churn rate → involuntary churn reasons (failure types) → voluntary churn reasons (non-renewal, account closure) → all churn by reason over time.</p></div></div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📹 Trail Guide: Voluntary &amp; Involuntary Churn Rate</h3>
      <p style="font-size:.88rem;color:var(--gray);margin:0 0 16px;">Walk through your churn dashboards — where to find the data, what it's telling you, and how to use it to keep subscribers around longer.</p>
      <div class="video-wrap">
        <iframe src="https://share.synthesia.io/embeds/videos/[CHURN-VIDEO-ID]"
          title="Navigate Trail Guide: Voluntary & Involuntary Churn Rate"
          allowfullscreen allow="encrypted-media; fullscreen; microphone; screen-wake-lock;"></iframe>
      </div>
      <p style="margin-top:10px;font-size:.8rem;color:var(--gray);">📌 Replace [CHURN-VIDEO-ID] with the actual Synthesia video ID before publishing.</p>
    </div>

    <h3 class="rc-subhead">🛡️ Retention Strategies by Churn Type</h3>
    <div class="rc-2col">
      <div class="rc-opt"><div class="rc-oicon">💳</div><h4>For Involuntary Churn</h4><p>Enable or verify Account Updater. Extend your dunning window. Add a Backup Payment Method prompt at signup. Review your dunning email open rates and update subject lines.</p><span class="rc-tag">Phase 1 Tools</span></div>
      <div class="rc-opt"><div class="rc-oicon">⏸️</div><h4>For Voluntary Churn</h4><p>Offer subscription pause instead of cancel. Enable cancellation surveys to capture exit reasons. Sort voluntary churn reasons by volume to find your top cancellation driver and address it.</p><span class="rc-tag">Experience &amp; Value</span></div>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Week 10 Completion Checklist</h3></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Know my total, voluntary, and involuntary churn rates<span>Analytics → Churn Management → Subscriber Churn Benchmarks</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Identified my top involuntary churn reason<span>Subscriber Churn Analysis → Involuntary Churn Reasons</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Identified my top voluntary churn reason<span>Subscriber Churn Analysis → Voluntary Churn Reasons</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Confirmed Account Updater is active (Phase 1 check)<span>Settings → Payment Settings — verify AU is enabled</span></div></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-launchpad-phase2-acquisition">← Acquisition &amp; Growth</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-launchpad-phase2-revenue-recovery">Next: Revenue Recovery →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/docs/subscriber-churn-benchmarks" target="_blank" rel="noopener noreferrer">📖 Subscriber Churn Benchmarks</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/docs/churn-benchmarks" target="_blank" rel="noopener noreferrer">📉 Churn Benchmarks Overview</a>
    <a class="rc-link-btn rc-link-sec" href="https://go.recurly.com/rs/439-LSC-903/images/Recurly%20Navigate%20Metrics%20Cheatsheet.pdf" target="_blank" rel="noopener noreferrer">📥 Metrics Cheatsheet</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">🎧 Contact Customer Success</a>
  </div>

</div>
</body>
</html>
`}</HTMLBlock>

<br />