---
title: 'Introduction to Navigate: Home'
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
  .rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray)}
  .rc-wi-top{font-size:28px;margin-bottom:10px}
  .rc-wi h4{font-size:.88rem;font-weight:700;margin:0 0 6px;color:var(--offblack)}.rc-wi p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-video-placeholder{background:var(--offblack);border-radius:14px;padding:48px 24px;text-align:center;margin-bottom:0}
  .rc-video-play{width:72px;height:72px;border-radius:50%;background:var(--yellow);display:flex;align-items:center;justify-content:center;margin:0 auto 16px;font-size:28px;color:var(--offblack)}
  .rc-module-structure{background:var(--offblack);border-radius:14px;padding:24px 28px;margin-bottom:24px}
  .rc-module-structure h4{font-size:.88rem;font-weight:700;color:var(--yellow);text-transform:uppercase;letter-spacing:.5px;margin:0 0 16px}
  .rc-module-row{display:flex;align-items:flex-start;gap:14px;padding:10px 0;border-bottom:1px solid rgba(255,255,255,.08)}
  .rc-module-row:last-child{border-bottom:none}
  .rc-module-icon{font-size:20px;flex-shrink:0;width:28px;text-align:center}
  .rc-module-label{font-size:.9rem;font-weight:700;color:var(--offwhite);margin:0 0 2px}
  .rc-module-desc{font-size:.82rem;color:var(--lightgray)}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev,.rc-btn-disabled{border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-2col,.rc-3col{grid-template-columns:1fr}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-home"><span class="rc-snum">3</span>Navigate Home</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-expect"><span class="rc-snum">4</span>What to Expect</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🏠</div>
      <div>
        <h2>Navigate Home Overview</h2>
        <p>Navigate Home in Recurly Docs is your central hub for every learning path, webinar, on-demand resource, and event the program offers — all organized around the Recurly Flywheel.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📹 Navigate Home walkthrough</h3>
      <div class="rc-video-placeholder">
        <div class="rc-video-play">▶</div>
        <p style="margin:0 0 6px;font-size:1rem;font-weight:700;color:var(--offwhite);">Navigate Home Walkthrough</p>
        <p style="margin:0;font-size:.85rem;color:var(--gray);">[ Insert Navigate Home walkthrough video here — recommended runtime: 2–3 minutes ]</p>
      </div>
    </div>

    <h3 class="rc-subhead">🧭 How to access Navigate Home</h3>
    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Go to Recurly Docs</h3>
          <p>Visit <a href="https://docs.recurly.com" target="_blank" rel="noopener noreferrer" style="color:var(--orange);font-weight:700;text-decoration:none;">docs.recurly.com</a> — the same documentation hub you already use for product guidance and API references.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Find the Navigate section</h3>
          <p>Look for the <strong>Navigate</strong> section in the sidebar. You'll see content organized by the four Flywheel pillars — Launch, Acquire, Retain, and Scale — at the top of the section.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Pick your starting point</h3>
          <p>Choose the Flywheel pillar that matches your current priority and start exploring. You can take a full learning path from start to finish, or jump to the individual module that's most relevant right now. There's no wrong place to start.</p>
        </div>
      </div>
    </div>

    <h3 class="rc-subhead">📦 What you'll find on Navigate Home</h3>
    <div class="rc-3col">
      <div class="rc-wi">
        <div class="rc-wi-top">📘</div>
        <h4>Full learning paths</h4>
        <p>Complete guided paths for each Flywheel pillar — structured to build on each other, covering every topic within that focus area from beginning to end.</p>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-top">🎯</div>
        <h4>Flexible &amp; modular</h4>
        <p>Take a full path or jump straight to the module most relevant right now. Come back anytime — there's no expiration on any content in Navigate.</p>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-top">📅</div>
        <h4>Webinar registrations</h4>
        <p>Browse and register for upcoming live webinars, feature sessions, and optimization workshops — all listed directly from Navigate Home.</p>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-top">🕐</div>
        <h4>Office Hours schedule</h4>
        <p>The next open Office Hours session is always listed here — no appointment needed, no agenda required. Just show up.</p>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-top">🎥</div>
        <h4>On-demand library</h4>
        <p>Recorded webinars, how-to videos, and optimization walkthroughs available any time — not just when live sessions are scheduled.</p>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-top">📁</div>
        <h4>Resources &amp; references</h4>
        <p>Benchmark reports, best practice guides, industry data, and configuration references — everything you need to go deeper, in one place.</p>
      </div>
    </div>

    <h3 class="rc-subhead">📋 How each learning module is structured</h3>
    <div class="rc-module-structure">
      <h4>Every Navigate module follows the same format</h4>
      <div class="rc-module-row">
        <div class="rc-module-icon">🔍</div>
        <div>
          <p class="rc-module-label">What it is</p>
          <span class="rc-module-desc">A clear explanation of the feature or concept</span>
        </div>
      </div>
      <div class="rc-module-row">
        <div class="rc-module-icon">💡</div>
        <div>
          <p class="rc-module-label">Why it matters</p>
          <span class="rc-module-desc">The business case and real impact for subscription businesses</span>
        </div>
      </div>
      <div class="rc-module-row">
        <div class="rc-module-icon">🔧</div>
        <div>
          <p class="rc-module-label">How to access it</p>
          <span class="rc-module-desc">Step-by-step guidance on where to find and configure it in Recurly</span>
        </div>
      </div>
      <div class="rc-module-row">
        <div class="rc-module-icon">✅</div>
        <div>
          <p class="rc-module-label">Best practices</p>
          <span class="rc-module-desc">What high-performing subscription businesses do — and what to think about</span>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Pro tip: You can take partial paths</h4>
        <p>Not everyone has time to complete an entire learning path at once — and that's completely fine. Navigate is designed for flexibility. Bookmark any module and return whenever it's convenient. Your knowledge compounds over time.</p>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-flywheel">← Section 2: The Flywheel</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-expect">Next: What to Expect →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs" target="_blank" rel="noopener noreferrer">🏠 Navigate Home in Recurly Docs</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer">🗓️ Global Office Hours</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">📡 Webinar &amp; Event Hub</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:recurlynavigate@recurly.com">🎧 Contact Navigate</a>
  </div>

</div>
</body>
</html>
`}</HTMLBlock>

<br />
