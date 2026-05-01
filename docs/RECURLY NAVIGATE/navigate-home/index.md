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

/* HERO */
.rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 52px;text-align:center;border-radius:16px}
.rc-badge{display:inline-flex;align-items:center;gap:8px;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
.rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
.rc-hero>p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 0;color:var(--lightgray);line-height:1.6}
.rc-hero-stats{display:grid;grid-template-columns:1fr 1fr 1fr;gap:0;margin-top:44px;padding-top:36px;border-top:1px solid rgba(255,255,255,.1);text-align:center}
.rc-hero-stat{padding:0 20px;position:relative}
.rc-hero-stat+.rc-hero-stat::before{content:"";position:absolute;left:0;top:50%;transform:translateY(-50%);height:60%;width:1px;background:rgba(255,255,255,.12)}
.rc-hero-stat-num{font-size:2.1rem;font-weight:800;color:var(--yellow);line-height:1;margin-bottom:8px}
.rc-hero-stat-label{font-size:.72rem;font-weight:700;letter-spacing:.8px;text-transform:uppercase;color:var(--lightgray);line-height:1.5}

/* SECTIONS */
.rc-sec{margin-bottom:56px}
.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
.rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
.rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
.rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
.rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}

/* CARD */
.rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
.rc-card p{font-size:.95rem;color:var(--darkgray);line-height:1.7;margin:0}

/* FLYWHEEL */
.rc-flywheel-wrap{display:grid;grid-template-columns:220px 1fr;gap:24px;align-items:center;margin-bottom:24px}
.rc-flywheel-img{border-radius:14px;background:var(--offblack);border:1px solid rgba(255,255,255,.08);display:flex;align-items:center;justify-content:center;padding:20px;aspect-ratio:1/1}
.rc-flywheel-img img{width:100%;height:100%;object-fit:contain}
.rc-flywheel-pillars{display:flex;flex-direction:column;gap:10px}

/* PILLAR TILES */
.rc-pillar{border-radius:14px;padding:16px 20px;border:1px solid var(--lightgray);background:var(--offwhite);display:flex;align-items:center;gap:16px;text-decoration:none;color:inherit;transition:border-color .2s,box-shadow .2s}
.rc-pillar:hover{border-color:var(--yellow);box-shadow:0 2px 10px rgba(255,215,6,.2)}
.rc-pillar-icon{width:44px;height:44px;border-radius:10px;background:var(--offblack);display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-pillar-icon img{width:22px;height:22px;object-fit:contain}
.rc-pillar-body{flex:1;min-width:0}
.rc-pillar-body h4{font-size:.95rem;font-weight:700;margin:0 0 3px;color:var(--offblack)}
.rc-pillar-body p{font-size:.8rem;color:var(--gray);margin:0;line-height:1.4}
.rc-pillar-tag{font-size:.72rem;font-weight:700;letter-spacing:.5px;text-transform:uppercase;color:var(--gray);flex-shrink:0;white-space:nowrap}

/* 2-COL WIDGETS */
.rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
.rc-wi{background:var(--offwhite);border-radius:14px;padding:22px;border:1px solid var(--lightgray)}
.rc-wi-icon{font-size:26px;margin-bottom:10px}
.rc-wi h4{font-size:.9rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}
.rc-wi p{font-size:.82rem;color:var(--gray);line-height:1.55;margin:0}

/* TIP */
.rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
.rc-tipicon{font-size:24px;flex-shrink:0}
.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}

/* OFFICE HOURS */
.rc-office{background:var(--offblack);color:#fff;border-radius:16px;padding:28px 32px;margin:28px 0;border:1px solid var(--yellow)}
.rc-office h4{color:var(--yellow);margin:0 0 10px;font-size:1rem;font-weight:800;text-transform:uppercase;letter-spacing:1px}
.rc-office p{color:var(--lightgray);font-size:.92rem;line-height:1.6;margin:0 0 18px}
.rc-office a{background:var(--yellow);color:var(--offblack);text-decoration:none;padding:10px 22px;border-radius:10px;font-weight:700;font-size:.88rem;display:inline-flex;align-items:center;gap:8px}

/* LINK BUTTONS */
.rc-link-btn{display:inline-flex;align-items:center;gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0;padding:10px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}

/* RESPONSIVE */
@media(max-width:640px){
  .rc-hero h1{font-size:1.7rem}
  .rc-hero{padding:36px 20px 40px}
  .rc-hero-stats{grid-template-columns:1fr;gap:24px;padding-top:28px}
  .rc-hero-stat+.rc-hero-stat::before{display:none}
  .rc-flywheel-wrap{grid-template-columns:1fr}
  .rc-flywheel-img{aspect-ratio:auto;min-height:180px}
  .rc-2col{grid-template-columns:1fr}
  .rc-sec-header{flex-direction:column}
}
</style>
</head>
<body>
<div class="rc-guide">

  <!-- HERO -->
  <div class="rc-hero">
    <div class="rc-badge">📋 Recurly Navigate · Home</div>
    <h1>Your Subscription Success Hub</h1>
    <p>Everything you need to get the most out of Recurly — best practices, expert guidance, and on-demand education. All in one place, on your schedule.</p>
    <div class="rc-hero-stats">
      <div class="rc-hero-stat">
        <div class="rc-hero-stat-num">Weekly</div>
        <div class="rc-hero-stat-label">Global Office Hours<br>live expert access</div>
      </div>
      <div class="rc-hero-stat">
        <div class="rc-hero-stat-num">Quarterly</div>
        <div class="rc-hero-stat-label">Merchant Spotlight Webinars<br>peer learning sessions</div>
      </div>
      <div class="rc-hero-stat">
        <div class="rc-hero-stat-num">Always On</div>
        <div class="rc-hero-stat-label">On-demand learning paths<br>for every stage</div>
      </div>
    </div>
  </div>

  <!-- WHAT IS NAVIGATE -->
  <div class="rc-sec" style="margin-top:36px">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🧭</div>
      <div>
        <h2>What is Navigate?</h2>
        <p>Your always-on resource for getting the most out of Recurly — from initial setup through ongoing optimization and growth.</p>
      </div>
    </div>
    <div class="rc-card">
      <p>Navigate was built on a simple belief: every Recurly merchant deserves access to expert best practices and strategic guidance. Through structured learning paths, live expert sessions, personalized insights, and peer-led events, Navigate makes it easy to self-serve the answers you need — and discover opportunities you didn't know you were missing. Whether you're setting up for the first time or fine-tuning a mature subscription program, Navigate meets you where you are and helps you get to the next level.</p>
    </div>
  </div>

  <!-- THE FLYWHEEL -->
  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔄</div>
      <div>
        <h2>The Recurly Flywheel</h2>
        <p>Navigate content is organized around the four pillars of a healthy subscription business. Select a pillar below to explore its learning paths.</p>
      </div>
    </div>

    <div class="rc-flywheel-wrap">
      <div class="rc-flywheel-img">
        <img src="https://files.readme.io/85e931cea7e5f65844bb1928786a705578636d4a0e6a258be4f0f4a8cb871cac-Recurly-Flywheel.png" alt="Recurly Flywheel — Launch, Acquire, Retain, Scale" />
      </div>
      <div class="rc-flywheel-pillars">

        <a class="rc-pillar" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch">
          <div class="rc-pillar-icon">
            <img src="https://files.readme.io/b6c93b0c856b23bcb18d1c1f5106eb9c83d23d9b505dc37e5ce9ea0d8dcfe89b-Launch-icon-white.png" alt="Launch" />
          </div>
          <div class="rc-pillar-body">
            <h4>Launch</h4>
            <p>Get configured and live fast. Build a solid foundation from day one.</p>
          </div>
          <span class="rc-pillar-tag">Foundation →</span>
        </a>

        <a class="rc-pillar" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-acquire">
          <div class="rc-pillar-icon">
            <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire" />
          </div>
          <div class="rc-pillar-body">
            <h4>Acquire</h4>
            <p>Convert more customers and grow your subscriber base.</p>
          </div>
          <span class="rc-pillar-tag">Growth →</span>
        </a>

        <a class="rc-pillar" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain">
          <div class="rc-pillar-icon">
            <img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt="Retain" />
          </div>
          <div class="rc-pillar-body">
            <h4>Retain</h4>
            <p>Reduce churn, recover revenue, and keep subscribers engaged.</p>
          </div>
          <span class="rc-pillar-tag">Retention →</span>
        </a>

        <a class="rc-pillar" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-scale">
          <div class="rc-pillar-icon">
            <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Scale" />
          </div>
          <div class="rc-pillar-body">
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
        <p>Start with the pillar that matches your biggest challenge right now. Every learning path is self-contained — you can jump in anywhere and get immediate value. Brand new to Recurly? Start with <strong>Launch</strong>.</p>
      </div>
    </div>
  </div>

  <!-- HOW NAVIGATE SUPPORTS YOU -->
  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🗺️</div>
      <div>
        <h2>How Navigate supports you</h2>
        <p>Navigate is a full ecosystem of resources designed to work together across your entire subscription journey.</p>
      </div>
    </div>

    <div class="rc-2col">
      <div class="rc-wi">
        <div class="rc-wi-icon">📚</div>
        <h4>Learning Paths</h4>
        <p>Structured, step-by-step guides organized by the flywheel. Each one covers what a feature is, why it matters, how to access it, and the best practices to follow.</p>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">🗓️</div>
        <h4>Global Office Hours</h4>
        <p>Live, open-forum sessions with a Recurly CSM. Ask questions, learn alongside other merchants, and leave with clear next steps. No appointment needed.</p>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">📊</div>
        <h4>Monthly Scorecards</h4>
        <p>Personalized performance data delivered to your inbox monthly — subscriber trends, churn rates, recovery rates, and industry benchmarks.</p>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">🎤</div>
        <h4>Merchant Spotlight Webinars</h4>
        <p>Peer-led sessions where real Recurly customers share the strategies and workflows driving results in their own subscription businesses.</p>
      </div>
    </div>
  </div>

  <!-- OFFICE HOURS CTA -->
  <div class="rc-office">
    <h4>🗓️ Connect with a CSM Live</h4>
    <p>Global Office Hours are your direct line to a Recurly Customer Success Manager. Bring your questions, your data, or just come to listen. Free, open to all merchants, running regularly.</p>
    <a href="https://navigate.recurly.com/global-office-hours/" target="_blank">Register for Office Hours →</a>
  </div>

  <!-- ADDITIONAL RESOURCES -->
  <h3 class="rc-subhead" style="margin-top:28px">📚 Additional resources</h3>
  <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" target="_blank"><img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png" style="width:14px;height:14px;object-fit:contain" alt="" /> Launch</a>
  <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-acquire" target="_blank"><img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" style="width:14px;height:14px;object-fit:contain" alt="" /> Acquire</a>
  <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" target="_blank"><img src="https://files.readme.io/2d6b0dfecebc907c932c4a7a27f8d76daeb9f8ff7ba76f775e1878a15c658e69-Retain-icon-black.png" style="width:14px;height:14px;object-fit:contain" alt="" /> Retain</a>
  <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-scale" target="_blank"><img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" style="width:14px;height:14px;object-fit:contain" alt="" /> Scale</a>
  <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/global-office-hours/" target="_blank">🌐 Office Hours</a>
  <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/" target="_blank">📅 Events</a>
  <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Support</a>

</div>
</body>
</html>
`}</HTMLBlock>

<br />
