---
title: 'Welcome to Navigate: Home Page'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Navigate — Recurly Customer Success Program</title>
<style>
.rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
*{box-sizing:border-box}
body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}

.rc-hero{background:var(--offblack);color:#fff;padding:64px 40px 56px;text-align:center;border-radius:16px;position:relative;overflow:hidden}
.rc-hero::before{content:"";position:absolute;inset:0;background:radial-gradient(ellipse 80% 60% at 50% 0%,rgba(255,215,6,.12) 0%,transparent 70%);pointer-events:none}
.rc-badge{display:inline-flex;align-items:center;gap:8px;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
.rc-hero h1{font-size:2.8rem;font-weight:800;line-height:1.1;margin:0 0 16px;color:#FFFDF2}
.rc-hero p{font-size:1.05rem;opacity:.85;max-width:680px;margin:0 auto 28px;color:#CCC9B8;line-height:1.65}
.rc-hero-ctas{display:flex;gap:12px;justify-content:center;flex-wrap:wrap}
.rc-btn-primary{display:inline-flex;align-items:center;gap:8px;background:var(--yellow);color:var(--offblack);padding:12px 24px;border-radius:10px;font-weight:700;font-size:.9rem;text-decoration:none}
.rc-btn-ghost{display:inline-flex;align-items:center;gap:8px;background:transparent;color:#fff;border:1px solid rgba(255,255,255,.3);padding:12px 24px;border-radius:10px;font-weight:700;font-size:.9rem;text-decoration:none}

.rc-sec{margin-bottom:52px}
.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:28px}
.rc-sec-icon{width:52px;height:52px;border-radius:14px;display:flex;align-items:center;justify-content:center;font-size:24px;flex-shrink:0;background:var(--yellow)}
.rc-sec-header h2{font-size:1.6rem;font-weight:800;margin:0 0 5px;color:var(--offblack)}
.rc-sec-header>div>p{color:var(--gray);font-size:.93rem;line-height:1.55;margin:0}
.rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}

.rc-intro-card{background:var(--offwhite);border-radius:16px;padding:28px 32px;border:1px solid var(--lightgray);margin-bottom:28px}
.rc-intro-card p{font-size:.95rem;color:var(--darkgray);line-height:1.7;margin:0}

.rc-stats{background:var(--offblack);border-radius:16px;padding:28px 32px;display:grid;grid-template-columns:1fr 1fr 1fr;gap:0;margin-bottom:28px;text-align:center}
.rc-stat{padding:8px 20px;position:relative}
.rc-stat+.rc-stat::before{content:"";position:absolute;left:0;top:50%;transform:translateY(-50%);height:50%;width:1px;background:rgba(255,255,255,.12)}
.rc-stat-num{font-size:2rem;font-weight:800;color:var(--yellow);line-height:1;margin-bottom:5px}
.rc-stat-label{font-size:.8rem;color:#CCC9B8;line-height:1.4}

.rc-flywheel-wrap{display:grid;grid-template-columns:1fr 1.4fr;gap:28px;align-items:center;margin-bottom:28px}
.rc-flywheel-img{border-radius:14px;overflow:hidden;border:1px solid var(--lightgray);background:var(--offwhite);display:flex;align-items:center;justify-content:center;padding:16px;min-height:220px}
.rc-flywheel-img img{max-width:100%;max-height:240px;object-fit:contain}
.rc-flywheel-pillars{display:flex;flex-direction:column;gap:12px}

.rc-pillar{border-radius:14px;padding:18px 20px;border:1px solid var(--lightgray);background:var(--offwhite);display:flex;align-items:center;gap:16px;text-decoration:none;color:inherit;transition:border-color .2s,box-shadow .2s}
.rc-pillar:hover{border-color:var(--yellow);box-shadow:0 2px 12px rgba(255,215,6,.2)}
.rc-pillar-icon{width:42px;height:42px;border-radius:10px;background:var(--offblack);display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-pillar-icon img{width:22px;height:22px;object-fit:contain}
.rc-pillar h4{font-size:.95rem;font-weight:700;margin:0 0 3px;color:var(--offblack)}
.rc-pillar p{font-size:.8rem;color:var(--gray);margin:0;line-height:1.45}
.rc-pillar-tag{margin-left:auto;font-size:.72rem;font-weight:700;letter-spacing:.5px;text-transform:uppercase;color:var(--gray);flex-shrink:0}

.rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
.rc-wi{background:var(--offwhite);border-radius:14px;padding:22px;border:1px solid var(--lightgray)}
.rc-wi-icon{font-size:28px;margin-bottom:10px}
.rc-wi h4{font-size:.9rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
.rc-wi p{font-size:.82rem;color:var(--gray);line-height:1.55;margin:0}

.rc-office{background:var(--offblack);color:#fff;border-radius:16px;padding:28px 32px;border:1px solid var(--yellow)}
.rc-office h4{color:var(--yellow);margin:0 0 8px;font-size:1rem;font-weight:800;text-transform:uppercase;letter-spacing:1px}
.rc-office p{color:#CCC9B8;font-size:.92rem;line-height:1.6;margin:0 0 16px}
.rc-office a{background:var(--yellow);color:var(--offblack);text-decoration:none;padding:10px 22px;border-radius:10px;font-weight:700;font-size:.88rem;display:inline-flex;align-items:center;gap:8px}

.rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:18px 22px;display:flex;gap:14px;align-items:flex-start;margin-bottom:24px}
.rc-tipicon{font-size:22px;flex-shrink:0}
.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}

.rc-link-btn{display:inline-flex;align-items:center;gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0;padding:10px 18px;border-radius:10px;font-weight:700;font-size:.87rem;text-decoration:none}
.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}

@media(max-width:680px){
  .rc-hero h1{font-size:1.9rem}
  .rc-hero{padding:40px 20px 36px}
  .rc-flywheel-wrap{grid-template-columns:1fr}
  .rc-2col{grid-template-columns:1fr}
  .rc-stats{grid-template-columns:1fr;gap:16px}
  .rc-stat+.rc-stat::before{display:none}
  .rc-sec-header{flex-direction:column}
}
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">✦ Navigate</div>
    <h1>Your Guide to Getting the Most<br>Out of Recurly</h1>
    <p>Navigate is your home for Recurly best practices, expert guidance, and on-demand education. Everything you need to fully optimize your Recurly instance — available anytime, all in one place.</p>
    <div class="rc-hero-ctas">
      <a class="rc-btn-primary" href="https://navigate.recurly.com/event-hub/" target="_blank">🗓️ Join Office Hours</a>
      <a class="rc-btn-ghost" href="https://navigate.recurly.com/event-hub/" target="_blank">📅 Upcoming Events</a>
    </div>
  </div>

  <div class="rc-sec" style="margin-top:36px">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🧭</div>
      <div>
        <h2>What is Navigate?</h2>
        <p>Your always-on resource for getting the most out of Recurly — from initial setup through ongoing optimization and growth.</p>
      </div>
    </div>

    <div class="rc-intro-card">
      <p>Navigate was built on a simple belief: every Recurly merchant deserves access to expert best practices and strategic guidance. Through structured learning paths, live expert sessions, personalized insights, and peer-led events, Navigate makes it easy to self-serve the answers you need — and discover opportunities you didn't know you were missing. Whether you're setting up for the first time or fine-tuning a mature subscription program, Navigate meets you where you are and helps you get to the next level.</p>
    </div>

    <div class="rc-stats">
      <div class="rc-stat">
        <div class="rc-stat-num">Weekly</div>
        <div class="rc-stat-label">Global Office Hours — live access<br>to Recurly experts, no appointment needed</div>
      </div>
      <div class="rc-stat">
        <div class="rc-stat-num">Quarterly</div>
        <div class="rc-stat-label">Merchant Spotlight Webinars — peer<br>learning from real Recurly customers</div>
      </div>
      <div class="rc-stat">
        <div class="rc-stat-num">Always On</div>
        <div class="rc-stat-label">On-demand learning paths covering<br>every stage of your subscription journey</div>
      </div>
    </div>
  </div>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔄</div>
      <div>
        <h2>The Recurly Flywheel</h2>
        <p>Navigate content is organized around the four pillars of a healthy subscription business. Wherever you are in the lifecycle, there's a learning path for you.</p>
      </div>
    </div>

    <div class="rc-flywheel-wrap">
      <div class="rc-flywheel-img">
        <img src="https://files.readme.io/85e931cea7e5f65844bb1928786a705578636d4a0e6a258be4f0f4a8cb871cac-Recurly-Flywheel.png" alt="Recurly Flywheel — Launch, Acquire, Retain, Scale" />
      </div>
      <div class="rc-flywheel-pillars">

        <a class="rc-pillar" href="#">
          <div class="rc-pillar-icon">
            <img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png" alt="Launch" style="filter:invert(1)" />
          </div>
          <div>
            <h4>Launch</h4>
            <p>Get configured and live fast. Build a solid foundation from day one.</p>
          </div>
          <span class="rc-pillar-tag">Foundation →</span>
        </a>

        <a class="rc-pillar" href="#">
          <div class="rc-pillar-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Acquire" style="filter:invert(1)" />
          </div>
          <div>
            <h4>Acquire</h4>
            <p>Convert more customers and grow your subscriber base.</p>
          </div>
          <span class="rc-pillar-tag">Growth →</span>
        </a>

        <a class="rc-pillar" href="#">
          <div class="rc-pillar-icon">
            <img src="https://files.readme.io/2d6b0dfecebc907c932c4a7a27f8d76daeb9f8ff7ba76f775e1878a15c658e69-Retain-icon-black.png" alt="Retain" style="filter:invert(1)" />
          </div>
          <div>
            <h4>Retain</h4>
            <p>Reduce churn, recover revenue, and keep subscribers engaged.</p>
          </div>
          <span class="rc-pillar-tag">Retention →</span>
        </a>

        <a class="rc-pillar" href="#">
          <div class="rc-pillar-icon">
            <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Scale" style="filter:invert(1)" />
          </div>
          <div>
            <h4>Scale</h4>
            <p>Expand your business and optimize payments and analytics.</p>
          </div>
          <span class="rc-pillar-tag">Optimization →</span>
        </a>

      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Not sure where to start?</h4>
        <p>Start with the pillar that matches your biggest challenge right now. Every learning path is self-contained — you can jump in anywhere and get immediate value. If you're brand new to Recurly, start with <strong>Launch</strong>.</p>
      </div>
    </div>
  </div>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🗺️</div>
      <div>
        <h2>How Navigate supports you</h2>
        <p>Navigate isn't a single thing — it's a full ecosystem of resources designed to work together across your entire merchant lifecycle.</p>
      </div>
    </div>

    <div class="rc-2col">
      <div class="rc-wi">
        <div class="rc-wi-icon">📚</div>
        <h4>Learning Paths</h4>
        <p>Structured, step-by-step guides organized by the flywheel. Each one covers what a feature is, why it matters, how to access it, and the best practices to follow. Self-serve, on your schedule.</p>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">🗓️</div>
        <h4>Global Office Hours</h4>
        <p>Live, open-forum sessions where you can ask questions, learn alongside other merchants, and get direct guidance from a Recurly CSM. No appointment needed.</p>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">📊</div>
        <h4>Monthly Scorecards</h4>
        <p>Personalized performance data delivered to your inbox monthly — subscriber trends, churn, recovery rates, and industry benchmarks. Know your numbers and what to do about them.</p>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">🎤</div>
        <h4>Merchant Spotlight Webinars</h4>
        <p>Peer-led sessions where real Recurly customers share the strategies driving results in their own subscription businesses. Learn from people who've been in your shoes.</p>
      </div>
    </div>
  </div>

  <div class="rc-office" style="margin-bottom:52px">
    <h4>🗓️ Connect with a CSM Live</h4>
    <p>Global Office Hours are your direct line to a Recurly Customer Success Manager. Bring your questions, your data, or just come to listen. Free, open to all merchants, and running regularly.</p>
    <a href="https://navigate.recurly.com/event-hub/" target="_blank">Register for Office Hours →</a>
  </div>

  <h3 class="rc-subhead">📚 Explore Navigate resources</h3>
  <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/" target="_blank">🌐 Global Office Hours</a>
  <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/lunch-and-learn/new-payment-hub/" target="_blank">▶ On-demand Learning</a>
  <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>

</div>
</body>
</html>
`}</HTMLBlock>

<br />
