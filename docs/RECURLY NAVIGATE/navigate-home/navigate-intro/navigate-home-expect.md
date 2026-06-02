---
title: 'Introduction to Navigate: What to expect'
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
  .rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
  *{box-sizing:border-box}body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
  .rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px}
  .rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
  .rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
  .rc-hero p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 32px;color:var(--lightgray)}
  .rc-hero-stats{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}.rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-flywheel-badges{display:flex;justify-content:center;gap:8px;flex-wrap:wrap;margin-top:20px}
  .rc-flywheel-badge{padding:4px 12px;border-radius:20px;font-size:11px;font-weight:700;display:inline-block;text-transform:uppercase;letter-spacing:.5px}
  .rc-flywheel-launch{background:var(--lightgray);color:var(--offblack)}
  .rc-flywheel-acquire{background:var(--yellow);color:var(--offblack)}
  .rc-flywheel-retain{background:#FF9D88;color:var(--offblack)}
  .rc-flywheel-scale{background:var(--orange);color:var(--offwhite)}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:10px;padding:10px 18px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack);box-shadow:0 2px 10px rgba(255,215,6,.25)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-sec{margin-bottom:56px}.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}.rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray)}
  .rc-wi-head{background:var(--offblack);margin:-20px -20px 14px -20px;padding:12px 16px;border-radius:10px 10px 0 0;display:flex;align-items:center;gap:10px}
  .rc-wi-head h4{margin:0;font-size:.9rem;font-weight:700;color:var(--yellow)}
  .rc-wi p{font-size:.85rem;color:var(--gray);line-height:1.6;margin:0 0 10px}
  .rc-wi a{font-size:.82rem;color:var(--offblack);font-weight:700;text-decoration:underline}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start;margin-bottom:24px}
  .rc-wicon{font-size:20px;flex-shrink:0}.rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  /* Scorecard illustration */
  .rc-scorecard{border-radius:16px;overflow:hidden;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-sc-nav-bar{background:var(--offblack);padding:12px 20px;display:flex;align-items:center;justify-content:space-between}
  .rc-sc-nav-bar .rc-sc-logo{display:flex;align-items:center;gap:6px}
  .rc-sc-logo-r{font-size:14px;font-weight:800;color:var(--yellow)}
  .rc-sc-logo-n{font-size:14px;font-weight:400;color:var(--offwhite)}
  .rc-sc-badge{font-size:10px;background:var(--yellow);color:var(--offblack);padding:2px 8px;border-radius:10px;font-weight:700}
  .rc-sc-yellow-bar{background:var(--yellow);padding:16px 20px}
  .rc-sc-yellow-bar h3{margin:0 0 3px;font-size:14px;font-weight:800;color:var(--offblack)}
  .rc-sc-yellow-bar p{margin:0;font-size:11px;color:var(--darkgray)}
  .rc-sc-body{padding:0}
  .rc-sc-metric{padding:14px 20px;border-bottom:1px dashed var(--lightgray);display:flex;align-items:flex-start;gap:12px;background:var(--offwhite)}
  .rc-sc-metric:last-child{border-bottom:none}
  .rc-sc-num-badge{width:26px;height:26px;border-radius:50%;display:flex;align-items:center;justify-content:center;flex-shrink:0;font-size:11px;font-weight:800}
  .rc-sc-metric-label h4{font-size:12px;font-weight:700;color:var(--offblack);margin:0 0 2px}
  .rc-sc-metric-label p{font-size:10px;color:var(--gray);margin:0 0 8px}
  .rc-sc-values{display:flex;gap:16px;flex-wrap:wrap}
  .rc-sc-val{text-align:center}
  .rc-sc-val-num{font-size:16px;font-weight:800}
  .rc-sc-val-label{font-size:9px;color:var(--gray);margin-top:2px}
  .rc-sc-footer{background:var(--offblack);padding:10px 20px;text-align:center}
  .rc-sc-footer p{margin:0;font-size:10px;color:var(--gray)}
  /* Checklist */
  .rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:28px}
  .rc-cl-header{padding:16px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:center;gap:10px;background:var(--offblack)}
  .rc-cl-header h3{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
  .rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:flex-start;gap:14px}.rc-cli:last-child{border-bottom:none}
  .rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;background:#fff;display:flex;align-items:center;justify-content:center;font-size:12px;color:var(--gray)}
  .rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}.rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
  /* Complete block */
  .rc-complete{background:var(--offblack);border-radius:16px;padding:40px;text-align:center;margin-bottom:28px;color:#fff}
  .rc-complete h2{font-size:1.8rem;font-weight:800;margin:12px 0 10px;color:var(--yellow)}
  .rc-complete p{color:var(--lightgray);font-size:.95rem;margin:0 0 20px;line-height:1.6}
  .rc-complete-btns{display:flex;gap:12px;justify-content:center;flex-wrap:wrap}
  .rc-complete-btn-primary{display:inline-flex;align-items:center;padding:12px 24px;background:var(--yellow);color:var(--offblack);border-radius:10px;font-weight:700;font-size:.9rem;text-decoration:none}
  .rc-complete-btn-sec{display:inline-flex;align-items:center;padding:12px 24px;background:transparent;color:var(--yellow);border-radius:10px;font-weight:700;font-size:.9rem;text-decoration:none;border:1px solid var(--yellow)}
  /* Office hours CTA */
  .rc-oh-cta{background:var(--offblack);color:#fff;border-radius:16px;padding:32px;margin:32px 0;border:1px solid var(--yellow)}
  .rc-oh-cta h4{color:var(--yellow);margin:0 0 8px;font-size:1.1rem;font-weight:800;text-transform:uppercase;letter-spacing:1px}
  .rc-oh-cta p{color:var(--lightgray);font-size:.95rem;line-height:1.6;margin:0 0 20px}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev,.rc-btn-disabled{border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-2col{grid-template-columns:1fr}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}.rc-complete-btns{flex-direction:column;align-items:center}}
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">🧭 Navigate Program</div>
    <h1>Introduction to Recurly Navigate</h1>
    <p>Your official orientation to Navigate — Recurly's digital Customer Success program built to help you get the most out of Recurly at every stage of your journey.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">5</div><div class="rc-lbl">Sections</div></div>
      <div><div class="rc-num">15</div><div class="rc-lbl">Min Read</div></div>
      <div><div class="rc-num">100%</div><div class="rc-lbl">Free</div></div>
    </div>
    <div class="rc-flywheel-badges">
      <span class="rc-flywheel-badge rc-flywheel-launch">🚀 Launch</span>
      <span class="rc-flywheel-badge rc-flywheel-acquire">➕ Acquire</span>
      <span class="rc-flywheel-badge rc-flywheel-retain">🔄 Retain</span>
      <span class="rc-flywheel-badge rc-flywheel-scale">📈 Scale</span>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro">Introduction to Navigate</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-welcome"><span class="rc-snum">1</span>Official Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-flywheel"><span class="rc-snum">2</span>The Flywheel</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-home"><span class="rc-snum">3</span>Navigate Home</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-expect"><span class="rc-snum">4</span>What to Expect</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">✅</div>
      <div>
        <h2>What to Expect from Navigate</h2>
        <p>Navigate isn't a set-it-and-forget-it resource library. It's an active, ongoing program. Here's exactly how we'll show up for you — proactively, consistently, and focused entirely on your success with Recurly.</p>
      </div>
    </div>

    <!-- MONTHLY SCORECARD -->
    <h3 class="rc-subhead">📊 Monthly Scorecard</h3>
    <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 18px;">Every <strong>second Tuesday of the month</strong>, you'll receive your Navigate Monthly Scorecard — a clear, consolidated snapshot of your most important subscription health metrics, benchmarked against your prior year and industry averages.</p>

    <!-- Scorecard illustration -->
    <div class="rc-scorecard">
      <div class="rc-sc-nav-bar">
        <div class="rc-sc-logo">
          <span class="rc-sc-logo-r">Recurly</span>
          <span class="rc-sc-logo-n">Navigate</span>
        </div>
        <span class="rc-sc-badge">NAVIGATE PROGRAM</span>
      </div>
      <div class="rc-sc-yellow-bar">
        <h3>Navigate at a glance</h3>
        <p>A quick performance snapshot of your last complete month in Recurly to help you monitor key metrics.</p>
      </div>
      <div class="rc-sc-body">
        <div class="rc-sc-metric">
          <div class="rc-sc-num-badge" style="background:var(--yellow);color:var(--offblack);">1</div>
          <div class="rc-sc-metric-label">
            <h4>Subscriber acquisition rate</h4>
            <p>New subscribers / Total subscribers = %</p>
            <div class="rc-sc-values">
              <div class="rc-sc-val"><div class="rc-sc-val-num" style="color:#16A34A;">3.2%</div><div class="rc-sc-val-label">This month</div></div>
              <div class="rc-sc-val"><div class="rc-sc-val-num" style="color:var(--gray);">4.1%</div><div class="rc-sc-val-label">Prior year</div></div>
              <div class="rc-sc-val"><div class="rc-sc-val-num" style="color:var(--offblack);">2.0%</div><div class="rc-sc-val-label">Industry benchmark</div></div>
            </div>
          </div>
        </div>
        <div class="rc-sc-metric">
          <div class="rc-sc-num-badge" style="background:var(--orange);color:#fff;">2</div>
          <div class="rc-sc-metric-label">
            <h4>Involuntary churn rate</h4>
            <p>Subscribers lost to payment failure / Total = %</p>
            <div class="rc-sc-values">
              <div class="rc-sc-val"><div class="rc-sc-val-num" style="color:#FF5810;">2.4%</div><div class="rc-sc-val-label">This month</div></div>
              <div class="rc-sc-val"><div class="rc-sc-val-num" style="color:var(--gray);">2.0%</div><div class="rc-sc-val-label">Prior year</div></div>
              <div class="rc-sc-val"><div class="rc-sc-val-num" style="color:var(--offblack);">1.0%</div><div class="rc-sc-val-label">Industry benchmark</div></div>
            </div>
          </div>
        </div>
        <div class="rc-sc-metric">
          <div class="rc-sc-num-badge" style="background:var(--offblack);color:var(--yellow);">3</div>
          <div class="rc-sc-metric-label">
            <h4>Renewal invoice paid rate</h4>
            <p>Paid invoices / Total renewal invoices = %</p>
            <div class="rc-sc-values">
              <div class="rc-sc-val"><div class="rc-sc-val-num" style="color:#16A34A;">97.0%</div><div class="rc-sc-val-label">This month</div></div>
              <div class="rc-sc-val"><div class="rc-sc-val-num" style="color:var(--gray);">60.0%</div><div class="rc-sc-val-label">Prior year</div></div>
              <div class="rc-sc-val"><div class="rc-sc-val-num" style="color:var(--offblack);">95.0%</div><div class="rc-sc-val-label">Industry benchmark</div></div>
            </div>
          </div>
        </div>
        <div class="rc-sc-metric">
          <div class="rc-sc-num-badge" style="background:var(--yellow);color:var(--offblack);">4</div>
          <div class="rc-sc-metric-label">
            <h4>Dunning recovery rate</h4>
            <p>Recovered invoices / Total invoices in recovery = %</p>
            <div class="rc-sc-values">
              <div class="rc-sc-val"><div class="rc-sc-val-num" style="color:#FF5810;">13.0%</div><div class="rc-sc-val-label">This month</div></div>
              <div class="rc-sc-val"><div class="rc-sc-val-num" style="color:var(--gray);">12.0%</div><div class="rc-sc-val-label">Prior year</div></div>
              <div class="rc-sc-val"><div class="rc-sc-val-num" style="color:var(--offblack);">44.0%</div><div class="rc-sc-val-label">Industry benchmark</div></div>
            </div>
          </div>
        </div>
      </div>
      <div class="rc-sc-footer">
        <p>Recurly Navigate &nbsp;·&nbsp; recurlynavigate@recurly.com &nbsp;·&nbsp; Delivered the 2nd Tuesday of every month</p>
      </div>
    </div>

    <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 28px;">Each metric includes context on what it means, why it matters, and a direct link to insights and resources to help you improve. Think of it as your monthly subscription health check — delivered automatically so you never have to go looking for it.</p>

    <!-- WHAT'S INCLUDED IN NAVIGATE -->
    <h3 class="rc-subhead">🎯 How Navigate shows up for you</h3>
    <div class="rc-2col">
      <div class="rc-wi">
        <div class="rc-wi-head"><span style="font-size:18px;">📬</span><h4>Monthly Newsletter</h4></div>
        <p>Your curated monthly briefing: new Recurly features, upcoming events, optimization tips, industry insights, and highlights from the Navigate community.</p>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-head"><span style="font-size:18px;">🗓️</span><h4>Open Office Hours</h4></div>
        <p>Drop in and ask a Customer Success Manager anything — no appointment, no agenda required. Live, open sessions for guidance and peer learning.</p>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer">View Office Hours schedule →</a>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-head"><span style="font-size:18px;">📡</span><h4>Webinars &amp; Events</h4></div>
        <p>Regular live sessions on new features, optimization strategies, and subscription trends — with Q&amp;A and on-demand recordings for everything.</p>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">Browse upcoming webinars →</a>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-head"><span style="font-size:18px;">🤝</span><h4>1:1 Expert Sessions</h4></div>
        <p>Available upon request. Dedicated 1:1 time with a CSM to review your setup, strategize on a goal, or work through a specific challenge — focused entirely on your priorities.</p>
        <a href="mailto:recurlynavigate@recurly.com">Request an Expert Session →</a>
      </div>
    </div>

    <!-- EMAIL WHITELIST WARNING -->
    <div class="rc-warning">
      <span class="rc-wicon">📧</span>
      <p><strong>Action required: Whitelist our email.</strong> All Navigate communications come from <strong>recurlynavigate@recurly.com</strong>. Please add this address to your email whitelist to ensure scorecards, newsletters, and event invitations reach your inbox. If you're not seeing our emails, check your spam folder and mark us as a trusted sender.</p>
    </div>

    <!-- PROACTIVE MONITORING -->
    <div class="rc-card">
      <h3 class="rc-subhead">👀 Proactive monitoring &amp; outreach</h3>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0 0 12px;">Your Navigate team proactively monitors your subscription health metrics. If we spot an opportunity to meaningfully improve your results — a gap in your dunning setup, an underutilized feature, or a benchmark that suggests room for improvement — we'll reach out and offer to help.</p>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin:0;">When you hear from us proactively, it means we've seen something worth your attention. We'll share what we found and offer to work through it with you in an Expert Session. Our goal is to make sure you're getting the most out of every capability Recurly offers — not just the ones you've already discovered.</p>
    </div>

    <!-- OPT OUT NOTE -->
    <div class="rc-tip">
      <span class="rc-tipicon">🚪</span>
      <div>
        <h4>A note on opting out</h4>
        <p>You can opt out of Navigate at any time by reaching out to <a href="mailto:recurlynavigate@recurly.com" style="color:var(--orange);font-weight:700;text-decoration:none;">recurlynavigate@recurly.com</a>. That said, opting out means stepping away from your monthly scorecard, newsletter, proactive monitoring, live events, Office Hours, and Expert Sessions. The program is designed to give you consistent value without requiring significant time investment — we'd love for you to stay.</p>
      </div>
    </div>

    <!-- COURSE COMPLETE CHECKLIST -->
    <h3 class="rc-subhead">🎓 Course complete — you're ready</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Introduction to Recurly Navigate — completion checklist</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">What Customer Success is<span>And how Navigate brings it to you digitally, at scale</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">The Recurly Flywheel<span>The four pillars — Launch, Acquire, Retain, Scale — and how all Navigate content maps to each</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Navigate Home in Recurly Docs<span>Your central hub for learning paths, webinars, on-demand content, and resources</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">What to expect from Navigate<span>Monthly scorecards, newsletters, Office Hours, Expert Sessions, and proactive outreach</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">recurlynavigate@recurly.com is whitelisted in your email client<span>Ensures all Navigate communications reach your inbox</span></div></div>
    </div>

    <!-- FINAL CTA BLOCK -->
    <div class="rc-complete">
      <div style="font-size:48px;">🚀</div>
      <h2>You're all set.</h2>
      <p>Head to Navigate Home and explore the learning path that matches your biggest priority right now. If you're not sure where to start, drop in at the next Office Hours session and ask.</p>
      <div class="rc-complete-btns">
        <a class="rc-complete-btn-primary" href="https://docs.recurly.com/recurly-subscriptions/docs" target="_blank" rel="noopener noreferrer">Go to Navigate Home →</a>
        <a class="rc-complete-btn-sec" href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer">Join Office Hours →</a>
      </div>
    </div>

    <div class="rc-oh-cta">
      <h4>🗓️ Not sure where to start?</h4>
      <p>Join a <strong>Customer Success Global Office Hours</strong> session to speak directly with our team. We'll review where you are in your Recurly journey and recommend the most relevant learning path for your current priorities.</p>
      <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" style="background:var(--yellow);color:var(--offblack);text-decoration:none;padding:12px 24px;border-radius:10px;font-weight:700;font-size:.9rem;display:inline-flex;align-items:center;gap:8px;">Register for Office Hours →</a>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-home">← Section 3: Navigate Home</a>
      <span class="rc-btn-disabled">🎉 Course Complete!</span>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs" target="_blank" rel="noopener noreferrer">🏠 Navigate Home in Recurly Docs</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer">🗓️ Global Office Hours</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">📡 Webinar &amp; Event Hub</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:recurlynavigate@recurly.com">🎧 Contact Navigate</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro">🔁 Restart This Course</a>
  </div>

</div>
</body>
</html>
`}</HTMLBlock>

<br />
