---
title: 'Welcome to Navigate: Getting started'
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
  .rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
  .rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
  .rc-sbadge{width:38px;height:38px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-agenda-row{display:grid;grid-template-columns:auto 1fr 1fr;gap:0;border-bottom:1px solid var(--brightgray)}
  .rc-agenda-row:last-child{border-bottom:none}
  .rc-agenda-num{width:40px;padding:14px 12px;font-weight:800;font-size:.9rem;color:var(--yellow);background:var(--offblack);display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-agenda-name{padding:14px 16px;font-weight:700;font-size:.9rem;color:var(--offblack);background:var(--offwhite)}
  .rc-agenda-desc{padding:14px 16px;font-size:.87rem;color:var(--gray);background:var(--offwhite)}
  .rc-agenda{border-radius:14px;overflow:hidden;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-agenda-header{display:grid;grid-template-columns:auto 1fr 1fr;background:var(--offblack)}
  .rc-agenda-header span{padding:10px 16px;font-size:.78rem;font-weight:700;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-agenda-header span:first-child{width:40px;text-align:center}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev,.rc-btn-disabled{border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}.rc-agenda-row,.rc-agenda-header{grid-template-columns:auto 1fr}}
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
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro">Introduction to Navigate</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-welcome"><span class="rc-snum">1</span>Official Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-flywheel"><span class="rc-snum">2</span>The Flywheel</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-home"><span class="rc-snum">3</span>Navigate Home</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-expect"><span class="rc-snum">4</span>What to Expect</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🧭</div>
      <div>
        <h2>Welcome to Recurly Navigate</h2>
        <p>Get oriented on the Navigate program, understand what's inside this course, and learn how Navigate will support your success with Recurly from day one.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🗺️ What is this course?</h3>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">This learning path is your official introduction to <strong>Recurly Navigate</strong> — a digital Customer Success program designed to make sure you always have the best practices, expert guidance, and product insights you need, right when you need them.</p>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0;">Whether you're brand new to Recurly or just joining the Navigate program, this course walks you through everything: how we support you, where to find every resource, and what to expect from us on an ongoing basis.</p>
    </div>

    <h3 class="rc-subhead">📋 What you'll cover</h3>
    <div class="rc-agenda">
      <div class="rc-agenda-header">
        <span>#</span>
        <span>Section</span>
        <span>What you'll learn</span>
      </div>
      <div class="rc-agenda-row">
        <div class="rc-agenda-num" style="background:var(--yellow);color:var(--offblack);">→</div>
        <div class="rc-agenda-name">Introduction to Navigate <span style="display:inline-block;margin-left:8px;background:var(--yellow);color:var(--offblack);padding:2px 8px;border-radius:10px;font-size:11px;font-weight:700;">You are here</span></div>
        <div class="rc-agenda-desc">Overview of the program and what's inside this course</div>
      </div>
      <div class="rc-agenda-row">
        <div class="rc-agenda-num">1</div>
        <div class="rc-agenda-name">Official Welcome</div>
        <div class="rc-agenda-desc">What Customer Success is and how Navigate brings it to you</div>
      </div>
      <div class="rc-agenda-row">
        <div class="rc-agenda-num">2</div>
        <div class="rc-agenda-name">The Recurly Flywheel</div>
        <div class="rc-agenda-desc">The four pillars of subscription success and how all content is organized around them</div>
      </div>
      <div class="rc-agenda-row">
        <div class="rc-agenda-num">3</div>
        <div class="rc-agenda-name">Navigate Home</div>
        <div class="rc-agenda-desc">Your hub for learning paths, webinars, on-demand content, and resources</div>
      </div>
      <div class="rc-agenda-row">
        <div class="rc-agenda-num">4</div>
        <div class="rc-agenda-name">What to Expect</div>
        <div class="rc-agenda-desc">Scorecards, newsletters, events, proactive outreach — how Navigate shows up for you</div>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">💡 Why Navigate exists</h3>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Subscription businesses have a lot to manage — acquiring customers, retaining them, recovering revenue, and scaling efficiently. Navigate was built to make sure you always have the expertise you need, without waiting for a support ticket or scheduled call.</p>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0;">This isn't a static knowledge base. Navigate is a living program that grows alongside Recurly — with new content, events, and resources added regularly, all organized around what's most relevant to your business right now.</p>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">⏱️</span>
      <div>
        <h4>Estimated time to complete</h4>
        <p>About 15–20 minutes at your own pace. You can take it all at once or return to any section whenever you need a refresher — there's no expiration on any content in Navigate.</p>
      </div>
    </div>

    <div class="rc-sec-nav">
      <span class="rc-btn-disabled">🎯 Start</span>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-welcome">Next: Official Welcome →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer">🗓️ Global Office Hours</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">📡 Webinar &amp; Event Hub</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:recurlynavigate@recurly.com">🎧 Contact Navigate</a>
  </div>

</div>
</body>
</html>
`}</HTMLBlock>

<br />
