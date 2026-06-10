---
title: 'Introduction to Navigate: Welcome'
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
  .rc-wi h4{font-size:.88rem;font-weight:700;margin:0 0 6px;color:var(--offblack)}.rc-wi p{font-size:.82rem;color:var(--gray);line-height:1.5;margin:0 0 10px}
  .rc-wi a{font-size:.82rem;color:var(--offblack);font-weight:700;text-decoration:underline}
  .rc-wi-header{background:var(--offblack);margin:-20px -20px 16px -20px;padding:12px 16px;border-radius:10px 10px 0 0;display:flex;align-items:center;gap:10px}
  .rc-wi-header h4{margin:0;font-size:.9rem;font-weight:700;color:var(--yellow)}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-video-placeholder{background:var(--offblack);border-radius:14px;padding:48px 24px;text-align:center;margin-bottom:0}
  .rc-video-play{width:72px;height:72px;border-radius:50%;background:var(--yellow);display:flex;align-items:center;justify-content:center;margin:0 auto 16px;font-size:28px;color:var(--offblack)}
  .rc-4col{display:grid;grid-template-columns:1fr 1fr 1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-pillar-card{border-radius:14px;padding:20px;text-align:center;border:1px solid var(--lightgray);background:var(--offwhite)}
  .rc-pillar-card h4{font-size:.88rem;font-weight:700;margin:10px 0 6px;color:var(--offblack)}.rc-pillar-card p{font-size:.78rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev,.rc-btn-disabled{border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-2col,.rc-4col{grid-template-columns:1fr}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-welcome"><span class="rc-snum">1</span>Official Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-flywheel"><span class="rc-snum">2</span>The Flywheel</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-home"><span class="rc-snum">3</span>Navigate Home</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-expect"><span class="rc-snum">4</span>What to Expect</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🎬</div>
      <div>
        <h2>Official Welcome</h2>
        <p>Watch the Navigate welcome video, then learn what Customer Success means at Recurly and the full range of support available to every Navigate member.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📹 Welcome video</h3>
      <div class="rc-video-placeholder">
        <div class="rc-video-play">▶</div>
        <p style="margin:0 0 6px;font-size:1rem;font-weight:700;color:var(--offwhite);">Official Navigate Welcome</p>
        <p style="margin:0;font-size:.85rem;color:var(--gray);">[ Insert official welcome video embed here — recommended runtime: 3–5 minutes ]</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🤝 What is Customer Success?</h3>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Customer Success is about more than answering questions — it's about making sure you're getting <strong>real, measurable value</strong> from Recurly. Our Customer Success team connects what Recurly can do with what your business actually needs, proactively guiding you toward better outcomes at every stage of growth.</p>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0;">At its core, Customer Success means helping you achieve your goals — not just use the software. We proactively identify opportunities to improve your results, share what works across thousands of subscription businesses, and stay invested in your success for the long haul.</p>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🧭 What is Recurly Navigate?</h3>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;"><strong>Navigate is Recurly's digital Customer Success program</strong> — built to bring the best of our expertise directly to you at scale. We know every subscription business is different and your priorities change over time. Navigate was designed to meet you exactly where you are — whether you're launching, growing subscribers, reducing churn, or scaling globally.</p>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0;">Here's what Navigate gives you access to:</p>
    </div>

    <h3 class="rc-subhead">🎯 What's included in Navigate</h3>
    <div class="rc-2col">
      <div class="rc-wi">
        <div class="rc-wi-header">
          <span style="font-size:20px;">🗓️</span>
          <h4>Open Office Hours</h4>
        </div>
        <p>Drop in and ask a Customer Success Manager anything. No agenda required — just show up with your questions. An open forum for guidance, best practices, and peer learning from others in the subscription space.</p>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer">Browse the Office Hours schedule →</a>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-header">
          <span style="font-size:20px;">🤝</span>
          <h4>1:1 Expert Sessions</h4>
        </div>
        <p>Need dedicated strategy time? Request a 1:1 session with a Customer Success Manager to dig into a specific challenge, review your setup, and map out next steps — focused entirely on your priorities.</p>
        <a href="mailto:recurlynavigate@recurly.com">Request an Expert Session →</a>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-header">
          <span style="font-size:20px;">📡</span>
          <h4>Webinars &amp; Feature Sessions</h4>
        </div>
        <p>Regular webinars on new Recurly features, optimization strategies, and subscription trends. Live sessions include Q&amp;A, and every session is available on demand afterward.</p>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">See upcoming webinars →</a>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-header">
          <span style="font-size:20px;">📚</span>
          <h4>Learning Paths &amp; On-Demand</h4>
        </div>
        <p>Self-paced learning paths, how-to guides, best practice articles, and thought leadership content — all organized so you can find what's most relevant to where you are right now.</p>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs" target="_blank" rel="noopener noreferrer">Explore Navigate Home →</a>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">🔄</span>
      <div>
        <h4>Coming up next: The Recurly Flywheel</h4>
        <p>Everything in Navigate — content, webinars, learning paths — is organized around a framework called the Recurly Flywheel. It maps to the four core phases of a healthy subscription business: Launch, Acquire, Retain, and Scale. In the next section, we'll show you how it works and how we've built all of Navigate around it.</p>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro">← Introduction to Navigate</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-flywheel">Next: The Flywheel →</a>
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
