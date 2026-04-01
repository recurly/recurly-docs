---
title: 'Section 5: Rewind & Review'
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
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-launchpad-phase2-churn"><span class="rc-snum">4</span>Churn & Retention</a>
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-launchpad-phase2-revenue-recovery"><span class="rc-snum">5</span>Revenue Recovery</a>
    <a class="rc-active" href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-launchpad-phase2-rewind-review"><span class="rc-snum">✓</span>Rewind & Review</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-phase-tag">📊 Phase 2 · Launchpad Complete</div>

    <div class="rc-sec-header">
      <div class="rc-sec-icon">🏁</div>
      <div>
        <h2>Rewind &amp; Review: You've Completed Launchpad!</h2>
        <p>This final section brings together everything from Phase 1 and Phase 2 — the webinar, the cheatsheets, and your full completion checklist.</p>
      </div>
    </div>

    <div class="rc-complete">
      <div style="font-size:48px;">🎊</div>
      <h2>You've Completed Navigate Launchpad!</h2>
      <p>Over 12 weeks you've tested your production environment, optimized your revenue recovery stack, branded your customer communications, and built a strong understanding of the metrics that drive subscription growth. Well done.</p>
    </div>

    <div class="rc-sec-header" style="margin-top:8px;">
      <div class="rc-sec-icon">🎥</div>
      <div>
        <h2>Benchmarks Series: Stack Up Against the Competition</h2>
        <p>Smarter Subscription Strategy Series, Part 2 — with Daniel Shipley, Senior CSM at Recurly</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📹 Watch On-Demand</h3>
      <p style="font-size:.88rem;color:var(--gray);margin:0 0 16px;">Dan Shipley walks through all 8 benchmark KPIs in detail — with definitions, calculations, real merchant examples (including a merchant who saw major involuntary churn improvements after enabling Account Updater), and strategic guidance for using benchmarks to drive business decisions.</p>
      <div class="video-wrap">
        <iframe src="https://navigate.recurly.com/on-demand/[BENCHMARKS-SESSION-ID]"
          title="Stack Up Against the Competition: Using Benchmarks Strategically"
          allowfullscreen allow="encrypted-media; fullscreen"></iframe>
      </div>
      <p style="margin-top:10px;font-size:.8rem;color:var(--gray);">📌 Replace [BENCHMARKS-SESSION-ID] with the actual on-demand URL before publishing.</p>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📹 Trail Guide: Exploring Your Benchmarks Dashboard</h3>
      <p style="font-size:.88rem;color:var(--gray);margin:0 0 16px;">A great refresher — get re-oriented in your Benchmarks Overview with all 8 KPIs in view.</p>
      <div class="video-wrap">
        <iframe src="https://share.synthesia.io/embeds/videos/5079f299-d1fa-47f9-aaf2-9cc14a556c67"
          title="Navigate Trail Guide: Exploring your benchmarks dashboard"
          allowfullscreen allow="encrypted-media; fullscreen; microphone; screen-wake-lock;"></iframe>
      </div>
    </div>

    <h3 class="rc-subhead">📋 Your Metrics Cheatsheet</h3>
    <iframe src="https://go.recurly.com/rs/439-LSC-903/images/Recurly%20Navigate%20Metrics%20Cheatsheet.pdf" width="100%" height="800px" style="border:none;border-radius:12px;margin-bottom:24px;display:block;"></iframe>

    <h3 class="rc-subhead">📁 Full Launchpad Cheatsheet: Phase 1 &amp; 2</h3>
    <p style="font-size:.88rem;color:var(--darkgray);line-height:1.6;margin:0 0 16px;">Your complete two-page reference for all 12 weeks. Use it to verify every step is complete — and keep it as a refresher as your business grows.</p>
    <iframe src="https://go.recurly.com/rs/439-LSC-903/images/Recurly%20Navigate%20Launchpad%20Complete%20Cheatsheet.pdf" width="100%" height="900px" style="border:none;border-radius:12px;margin-bottom:24px;display:block;"></iframe>

    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Launchpad Complete — Master Checklist</h3></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Accessed the Benchmarks Overview and can read all 8 KPIs<span>Analytics → Benchmarks Overview</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Watched "Beyond the Dashboard" and know Recurly's 4 reporting tools<span>Tab 2: Reporting Tools</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Know my Acquisition Rate and Sign-Up Decline Rate vs. industry benchmark<span>Tab 3: Acquisition &amp; Growth</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Know my voluntary vs. involuntary churn split and top reasons for each<span>Tab 4: Churn &amp; Retention</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Know my Dunning Recovery Rate and Renewal Invoice Paid Rate<span>Tab 5: Revenue Recovery — Week 11</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Explored Recovered Revenue dashboard and noted my AU vs. Dunning split<span>Tab 5: Revenue Recovery — Week 12</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Watched the Benchmarks webinar and can discuss KPIs in context<span>Tab 6: Rewind &amp; Review — Benchmarks Series</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Downloaded the Metrics Cheatsheet and Launchpad Complete Cheatsheet<span>Both embedded above</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Monthly Metrics review habit started — 30-min calendar block set<span>Review all 8 KPIs monthly and act on trends</span></div></div>
    </div>

    <h3 class="rc-subhead">🚀 What's Next After Launchpad?</h3>
    <div class="rc-3col">
      <div class="rc-wi"><div class="rc-wi-icon">📅</div><h4>Monthly Metrics Scorecard</h4><p>Watch for your first scorecard two Tuesdays after your 90-day production mark — your personalized monthly performance report from Recurly.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🎓</div><h4>Navigate Office Hours</h4><p>Live, small-group sessions (max 30) with Recurly experts. Bring specific questions. Topics rotate monthly. <a href="https://recurly.com/events" target="_blank" rel="noopener noreferrer" style="color:var(--orange);">See upcoming events.</a></p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🔮</div><h4>More Learning Paths</h4><p>Navigate continues with advanced learning paths on Account Updater, Backup Payment Methods, Billing Insights, and more.</p></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-launchpad-phase2-revenue-recovery">← Revenue Recovery</a>
      <span class="rc-btn-disabled">🎉 Launchpad Complete!</span>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://navigate.recurly.com/beyond-the-dashboard-reporting/" target="_blank" rel="noopener noreferrer">▶ Reporting That Drives Growth</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/using-benchmarks-strategically/" target="_blank" rel="noopener noreferrer">📊 Using Benchmarks Strategically</a>
    <a class="rc-link-btn rc-link-sec" href="https://go.recurly.com/Recurly-Navigate-Metrics-Cheatsheet.html" target="_blank" rel="noopener noreferrer">📋 Metrics Cheatsheet</a>
    <a class="rc-link-btn rc-link-sec" href="https://support.recurly.com/hc/en-us" target="_blank" rel="noopener noreferrer">🆘 Support Portal</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">🎧 Contact Customer Success</a>
  </div>

</div>
</body>
</html>
`}</HTMLBlock>

<br />