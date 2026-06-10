---
title: 'Introduction to Navigate: The Subscription Flywheel'
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
  .rc-flywheel-hero{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);padding:32px;margin-bottom:24px;display:flex;gap:32px;align-items:center;flex-wrap:wrap}
  .rc-flywheel-img-wrap{flex:0 0 240px;background:var(--offblack);border-radius:12px;overflow:hidden;display:flex;align-items:center;justify-content:center;min-height:240px}
  .rc-flywheel-text{flex:1;min-width:220px}
  .rc-flywheel-text h3{font-size:1.3rem;font-weight:800;color:var(--offblack);margin:0 0 12px}
  .rc-flywheel-text p{font-size:.92rem;color:var(--darkgray);line-height:1.65;margin:0 0 10px}
  .rc-pillar-grid{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:24px}
  .rc-pillar{border-radius:16px;overflow:hidden;border:1px solid var(--lightgray)}
  .rc-pillar-head{padding:18px 20px;display:flex;align-items:center;gap:14px}
  .rc-pillar-head-icon{width:40px;height:40px;background:var(--offblack);border-radius:8px;display:flex;align-items:center;justify-content:center;font-size:20px;flex-shrink:0}
  .rc-pillar-head h3{font-size:1.05rem;font-weight:800;margin:0 0 2px;color:var(--offblack)}.rc-pillar-head p{font-size:.8rem;margin:0;color:var(--darkgray)}
  .rc-pillar-scale .rc-pillar-head h3,.rc-pillar-scale .rc-pillar-head p{color:var(--offwhite)}
  .rc-pillar-body{padding:18px 20px;background:var(--offwhite)}
  .rc-pillar-body p{font-size:.88rem;color:var(--darkgray);line-height:1.65;margin:0 0 12px}
  .rc-tags{display:flex;flex-wrap:wrap;gap:6px}
  .rc-tag{display:inline-block;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;background:var(--offblack);color:var(--yellow)}
  .rc-pillar-launch .rc-pillar-head{background:var(--lightgray)}
  .rc-pillar-acquire .rc-pillar-head{background:var(--yellow)}
  .rc-pillar-retain .rc-pillar-head{background:#FF9D88}
  .rc-pillar-scale .rc-pillar-head{background:var(--orange)}
  .rc-starttip{background:var(--offblack);border-radius:14px;padding:24px 28px;margin-bottom:24px}
  .rc-starttip h4{font-size:.88rem;font-weight:700;color:var(--yellow);text-transform:uppercase;letter-spacing:.5px;margin:0 0 16px}
  .rc-starttip-row{display:flex;align-items:center;gap:16px;padding:10px 0;border-bottom:1px solid rgba(255,255,255,.08)}
  .rc-starttip-row:last-child{border-bottom:none}
  .rc-starttip-q{font-size:.88rem;color:var(--lightgray);width:200px;flex-shrink:0}
  .rc-starttip-a{font-size:.88rem;font-weight:700;color:var(--offwhite)}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev,.rc-btn-disabled{border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-pillar-grid{grid-template-columns:1fr}.rc-flywheel-hero{flex-direction:column}.rc-flywheel-img-wrap{width:100%;flex:0 0 auto}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-flywheel"><span class="rc-snum">2</span>The Flywheel</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-home"><span class="rc-snum">3</span>Navigate Home</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-expect"><span class="rc-snum">4</span>What to Expect</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔄</div>
      <div>
        <h2>The Recurly Flywheel</h2>
        <p>Navigate was built around the Recurly Flywheel — the four pillars of a healthy subscription business. Every piece of content, every webinar, and every learning path maps directly to one of these pillars.</p>
      </div>
    </div>

    <!-- Flywheel hero card: image + description side by side -->
    <div class="rc-flywheel-hero">
      <div class="rc-flywheel-img-wrap">
        <!-- Primary: Google Drive hosted flywheel image -->
        <img
          src="https://drive.google.com/uc?export=view&id=190stbfxuO7mFxVG_7-O49pvIkfGmpv_g"
          alt="The Recurly Flywheel: Launch, Acquire, Retain, Scale"
          style="width:100%;height:auto;display:block;"
          onerror="this.parentElement.style.padding='32px';this.style.display='none';this.insertAdjacentHTML('afterend','<div style=\'text-align:center;\'><div style=\'font-size:64px;margin-bottom:8px;\'>🔄</div><p style=\'color:#CCC9B8;font-size:.85rem;margin:0;\'>Recurly Flywheel</p></div>');"
        />
      </div>
      <div class="rc-flywheel-text">
        <h3>The Recurly Flywheel</h3>
        <p><strong>Navigate was built to act as your digital Customer Success Manager.</strong> Every resource is structured around the four pillars of a healthy subscription business.</p>
        <p>Whether you're exploring Account Updater to fix retention issues or setting up Dunning windows for the first time, Navigate meets you where you are and helps you get to the next level.</p>
        <p>The Flywheel is continuous — subscription businesses are always cycling through these phases, and the best operators are actively working across multiple pillars at once.</p>
      </div>
    </div>

    <h3 class="rc-subhead">🎯 The four pillars, in depth</h3>

    <div class="rc-pillar-grid">

      <div class="rc-pillar rc-pillar-launch">
        <div class="rc-pillar-head">
          <div class="rc-pillar-head-icon">🚀</div>
          <div>
            <h3>Launch</h3>
            <p>Get your subscription engine running</p>
          </div>
        </div>
        <div class="rc-pillar-body">
          <p>Build a solid foundation — configure your plans, set up payment flows, and make sure your subscriber experience is exactly what you want it to be from day one.</p>
          <div class="rc-tags">
            <span class="rc-tag">Subscription setup</span>
            <span class="rc-tag">Billing models</span>
            <span class="rc-tag">Checkout</span>
            <span class="rc-tag">Free trials</span>
            <span class="rc-tag">Gateway config</span>
          </div>
        </div>
      </div>

      <div class="rc-pillar rc-pillar-acquire">
        <div class="rc-pillar-head">
          <div class="rc-pillar-head-icon">➕</div>
          <div>
            <h3>Acquire</h3>
            <p>Grow your subscriber base</p>
          </div>
        </div>
        <div class="rc-pillar-body">
          <p>Focus on bringing in new subscribers efficiently and converting them effectively. Pricing strategy, promotional mechanics, and a front door that converts.</p>
          <div class="rc-tags">
            <span class="rc-tag">Pricing strategy</span>
            <span class="rc-tag">Coupons &amp; promos</span>
            <span class="rc-tag">Trial conversion</span>
            <span class="rc-tag">Gift subscriptions</span>
          </div>
        </div>
      </div>

      <div class="rc-pillar rc-pillar-retain">
        <div class="rc-pillar-head">
          <div class="rc-pillar-head-icon">🔄</div>
          <div>
            <h3>Retain</h3>
            <p>Protect revenue, reduce churn</p>
          </div>
        </div>
        <div class="rc-pillar-body">
          <p>Retention is where subscription businesses win or lose. This pillar covers dunning, payment recovery, cancellation prevention, and everything in between.</p>
          <div class="rc-tags">
            <span class="rc-tag">Dunning strategy</span>
            <span class="rc-tag">Account Updater</span>
            <span class="rc-tag">Intelligent retries</span>
            <span class="rc-tag">Cancel-save flows</span>
          </div>
        </div>
      </div>

      <div class="rc-pillar rc-pillar-scale">
        <div class="rc-pillar-head">
          <div class="rc-pillar-head-icon">📈</div>
          <div>
            <h3>Scale</h3>
            <p>Expand with confidence</p>
          </div>
        </div>
        <div class="rc-pillar-body">
          <p>When you're ready to grow beyond your initial market — international expansion, advanced analytics, revenue recognition, and high-performance configurations.</p>
          <div class="rc-tags">
            <span class="rc-tag">Global payments</span>
            <span class="rc-tag">Revenue recognition</span>
            <span class="rc-tag">Advanced analytics</span>
            <span class="rc-tag">AI insights</span>
          </div>
        </div>
      </div>

    </div>

    <h3 class="rc-subhead">💡 Not sure where to start?</h3>
    <div class="rc-starttip">
      <h4>Ask yourself: What's my biggest priority right now?</h4>
      <div class="rc-starttip-row">
        <span class="rc-starttip-q">Getting set up properly</span>
        <span class="rc-starttip-a">→ Start with Launch</span>
      </div>
      <div class="rc-starttip-row">
        <span class="rc-starttip-q">Growing subscriber numbers</span>
        <span class="rc-starttip-a">→ Start with Acquire</span>
      </div>
      <div class="rc-starttip-row">
        <span class="rc-starttip-q">Stopping revenue leakage</span>
        <span class="rc-starttip-a">→ Start with Retain</span>
      </div>
      <div class="rc-starttip-row">
        <span class="rc-starttip-q">Expanding or scaling globally</span>
        <span class="rc-starttip-a">→ Start with Scale</span>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">🏠</span>
      <div>
        <h4>Up next: Navigate Home</h4>
        <p>Now that you understand the Flywheel and how Navigate is structured around it, the next section walks you through Navigate Home in Recurly Docs — your central hub for every learning path, webinar, and resource in the program.</p>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-welcome">← Section 1: Official Welcome</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-home">Next: Navigate Home →</a>
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
