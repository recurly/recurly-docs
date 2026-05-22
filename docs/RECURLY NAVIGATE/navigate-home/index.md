---
title: 'Welcome to Navigate: Home Page'
excerpt: >-
  Explore Recurly Navigate, your Subscription Success Hub. Access expert
  learning paths to launch, acquire, retain, and scale your recurring revenue
  business.
deprecated: false
hidden: true
metadata:
  description: >-
    Explore Recurly Navigate, your Subscription Success Hub. Access expert
    learning paths to launch, acquire, retain, and scale your recurring revenue
    business.
  keywords:
    - Recurly Navigate
    - Subscription Success Hub
    - Subscription Growth Strategy
    - Recurring Revenue Management
    - Involuntary Churn Recovery
    - Subscriber Acquisition Strategies
    - Subscription Business Scaling
    - Dunning Management
    - Churn Reduction Best Practices
    - and Merchant Education
  robots: index
---
<HTMLBlock>{`
<style>
html { scroll-behavior: smooth; scroll-padding-top: 80px; }

.rc-guide {
  --yellow:    #FFD706;
  --orange:    #FF8200;
  --offblack:  #0D0D0B;
  --darkgray:  #32312D;
  --gray:      #807D73;
  --lightgray: #CCC9B8;
  --brightgray:#F1EFE3;
  --offwhite:  #FFFDF2;
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--darkgray);
}
.rc-guide * { box-sizing: border-box; }
body { margin: 0; background: #fff; }

/* ── HOST-THEME ARMOR — resets ReadMe's global link styles ── */
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:hover,
.rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

/* ── LAYOUT WRAPPER ── */
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* ── ANNOUNCEMENT BAR — hidden by default, show with rc-active ── */
.rc-announce-bar {
  display: none;
  background: var(--yellow);
  color: var(--offblack);
  align-items: center;
  justify-content: space-between;
  padding: 10px 20px;
  font-size: .88rem;
  font-weight: 600;
  border-radius: 10px;
  margin-bottom: 16px;
  gap: 12px;
  line-height: 1.4;
}
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 12px; flex: 1; flex-wrap: wrap; }
.rc-announce-link {
  color: var(--offblack) !important;
  font-weight: 800;
  text-decoration: none !important;
  white-space: nowrap;
  padding: 4px 12px;
  background: rgba(0,0,0,0.10);
  border-radius: 6px;
  transition: background 0.2s;
}
.rc-announce-link:hover { background: rgba(0,0,0,0.20); }
.rc-announce-close {
  background: none; border: none; font-size: 1.4rem; line-height: 1; cursor: pointer;
  color: var(--offblack); padding: 0 2px; opacity: 0.45; transition: opacity 0.2s; flex-shrink: 0;
}
.rc-announce-close:hover { opacity: 1; }

/* ── HERO ── */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack);
  background-size: cover;
  color: #fff;
  padding: 48px 40px 44px;
  text-align: center;
  border-radius: 16px;
  margin-bottom: 0;
}

/* FIX #1 + #2: logo height 28px, margin-bottom 0 */
.rc-brand-header { display: flex; align-items: center; justify-content: center; margin-bottom: 0; }
.rc-logo-image { height: 28px; width: auto; display: block; }

/* FIX #3: Home title block with 44px top margin */
.rc-home-title-block { margin-top: 44px; }
.rc-home-title-block h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0 0 24px; }

.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto; color: var(--lightgray); line-height: 1.6; }

/* Hero stats */
.rc-hero-stats {
  display: grid; grid-template-columns: repeat(3, 1fr); gap: 0;
  border-top: 1px solid rgba(255,255,255,0.12);
  padding-top: 24px; margin-top: 32px;
}
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); line-height: 1.3; }

/* ── STICKY NAV — collapsed on load (no open attr) ── */
details.rc-sticky-nav-wrap {
  position: sticky;
  top: 0;
  z-index: 100;
  background-color: var(--brightgray);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px 0;
  border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08);
  overflow: hidden;
}
details.rc-sticky-nav-wrap > summary {
  list-style: none;
  display: flex;
  align-items: center;
  padding: 15px 24px;
  cursor: pointer;
  user-select: none;
}
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label {
  display: inline-flex; align-items: center; gap: 8px;
  font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase;
  color: var(--offblack);
}
.rc-nav-chevron {
  font-size: .72rem; color: var(--offblack); opacity: 0.55; line-height: 1;
  transition: transform 0.25s ease;
}
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
.rc-sticky-link {
  color: var(--offblack) !important;
  text-decoration: none !important;
  font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase;
  padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap;
  display: inline-flex; align-items: center; gap: 6px;
}
.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: var(--offblack) !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge {
  display: inline-flex; align-items: center; justify-content: center;
  width: 20px; height: 20px; border-radius: 50%;
  background: var(--offblack); color: var(--yellow);
  font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1;
}
.rc-sticky-link:hover .rc-step-badge { background: var(--yellow); color: var(--offblack); }
.rc-sticky-link-active { font-weight: 800; }
.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: var(--offblack) !important; }

/* ── SECTION HEADER ── */
.rc-sec-header { text-align: center; margin-bottom: 24px; }
.rc-sec-header h2 { font-size: 2rem; font-weight: 800; margin: 0 0 8px; color: var(--offblack); }
.rc-sec-header p { font-size: .95rem; color: var(--gray); margin: 0; }

/* ── GETTING STARTED CTA — dark card, hex + !important required ── */
.rc-starter-cta {
  background: #0D0D0B !important;
  border: 2px solid #FFD706 !important;
  border-radius: 16px;
  padding: 28px 32px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
  margin-bottom: 32px;
}
.rc-starter-text h3 { margin: 0 0 6px; font-size: 1.2rem; font-weight: 800; color: #FFD706 !important; }
.rc-starter-text p { margin: 0; font-size: .95rem; color: #CCC9B8 !important; line-height: 1.5; }

/* Primary button */
.rc-guide a.rc-btn-primary {
  background: #FFD706 !important;
  color: #0D0D0B !important;
  text-decoration: none !important;
  padding: 12px 26px;
  border-radius: 10px;
  font-weight: 800;
  font-size: .9rem;
  white-space: nowrap;
  transition: all .2s;
  border: 2px solid #FFD706 !important;
  border-bottom: 2px solid #FFD706 !important;
  display: inline-flex; align-items: center;
}
.rc-guide a.rc-btn-primary:hover {
  background: transparent !important;
  color: #FFD706 !important;
  border: 2px solid #FFD706 !important;
  border-bottom: 2px solid #FFD706 !important;
}

/* ── HUB GRID ── */
.rc-hub-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px; margin-bottom: 24px; }
.rc-hub-card {
  background: var(--offwhite); border: 1px solid var(--lightgray);
  border-radius: 16px; padding: 32px 24px;
  text-decoration: none !important; color: inherit;
  transition: all .2s ease; display: flex; flex-direction: column; align-items: center; text-align: center;
}
.rc-guide a.rc-hub-card { border-bottom: 1px solid var(--lightgray) !important; }
.rc-guide a.rc-hub-card:hover {
  border-color: var(--yellow);
  border-bottom: 1px solid var(--yellow) !important;
  box-shadow: 0 8px 24px rgba(255,215,6,.15);
  transform: translateY(-4px);
}
.rc-hub-icon { width: 64px; height: 64px; border-radius: 14px; display: flex; align-items: center; justify-content: center; margin-bottom: 20px; }
.rc-hub-icon img { width: 32px; height: 32px; object-fit: contain; }
.rc-hub-card h3 { font-size: 1.3rem; font-weight: 800; margin: 0 0 10px; color: var(--offblack); }
.rc-hub-card p { font-size: .9rem; color: var(--gray); line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-hub-arrow { margin-top: 20px; color: var(--orange); font-weight: 700; font-size: .9rem; }

/* ── FOOTER SUMMARY ── */
.rc-footer-summary {
  background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 16px;
  padding: 40px; margin: 48px auto 0; text-align: center; max-width: 900px;
  display: flex; flex-direction: column; align-items: center; gap: 16px;
}
.rc-footer-summary h3 { font-size: 1.5rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-footer-summary p { color: var(--darkgray); font-size: 1.05rem; line-height: 1.6; margin: 0; max-width: 750px; }
.rc-support-link {
  display: inline-block; color: var(--orange); font-weight: 700;
  text-decoration: none !important; padding: 10px 20px;
  background: rgba(255,130,0,0.1); border-radius: 8px; transition: all 0.2s ease;
}
.rc-support-link:hover { background: var(--orange); color: white !important; transform: translateY(-2px); }

/* ── FOOTER NAV — grouped rc-footer-section structure ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label {
  font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px;
  color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px;
}
.rc-footer-link {
  color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .88rem;
  transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px;
}
.rc-footer-link:hover { color: var(--orange); }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* ── CONSOLIDATED RESPONSIVE BLOCK ── */
@media(max-width:900px){ .rc-hub-grid { grid-template-columns: repeat(2, 1fr); } }
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-home-title-block h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-starter-cta { flex-direction: column; align-items: flex-start; }
  .rc-hub-grid { grid-template-columns: 1fr; }
  .rc-announce-bar { flex-direction: column; align-items: flex-start; gap: 8px; }
}
</style>

<div class="rc-guide">
  <div class="rc-content-wrap">

    <!-- ── ANNOUNCEMENT BAR — hidden; add class rc-active to show ── -->
    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>This Thursday:</strong> Global Office Hours — Dunning windows &amp; payment recovery with our lead CSMs.
        <!-- FIX #4: event-hub → global-office-hours -->
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- ── HERO ── -->
    <div class="rc-hero">
      <!-- FIX #1 + #2: logo height 28px, margin-bottom 0 -->
      <div class="rc-brand-header">
        <img src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly" class="rc-logo-image">
      </div>
      <!-- FIX #3: Home title block with 44px top margin -->
      <div class="rc-home-title-block">
        <h1>Your Subscription Success Hub</h1>
        <p>Everything you need to get the most out of Recurly. Select a path below to uncover best practices, expert guidance, and on-demand education tailored to your KPIs.</p>
      </div>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">Weekly</div>
          <div class="rc-hero-stat-label">Global Office Hours</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">Quarterly</div>
          <div class="rc-hero-stat-label">Merchant Spotlight</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">24/7</div>
          <div class="rc-hero-stat-label">On-demand paths</div>
        </div>
      </div>
    </div>

    <!-- ── STICKY NAV — collapsed on load, title = "Navigation Menu" ── -->
    <details class="rc-sticky-nav-wrap">
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <!-- Active page: black map pin replaces badge entirely -->
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Navigate Home
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-sticky-link">Launch</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-sticky-link">Acquire</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-sticky-link">Retain</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale" class="rc-sticky-link">Scale</a>
            <a href="https://navigate.recurly.com/event-hub/" class="rc-sticky-link" target="_blank" rel="noopener noreferrer">Events ↗</a>
            <!-- FIX #4: event-hub → global-office-hours -->
            <a href="https://navigate.recurly.com/global-office-hours/" class="rc-sticky-link" target="_blank" rel="noopener noreferrer">Office Hours ↗</a>
          </div>
        </div>
      </div>
    </details>

    <!-- ── EXPLORE NAVIGATE ── -->
    <div class="rc-sec-header">
      <h2>Explore Navigate</h2>
      <p>Choose your objective to access self-serve learning paths and resources.</p>
    </div>

    <!-- ── NEW TO NAVIGATE — dark card ── -->
    <div class="rc-starter-cta">
      <div class="rc-starter-text">
        <h3>👋 New to Navigate?</h3>
        <p>Welcome! Start here to learn how to use this program and find support.</p>
      </div>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home-getting-started" class="rc-btn-primary">Get Started Here</a>
    </div>

    <!-- ── HUB GRID ── -->
    <div class="rc-hub-grid">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-hub-card">
        <div class="rc-hub-icon" style="background-color:#CCC9B8;"><img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png" alt="Launch"></div>
        <h3>Launch</h3>
        <p>Get configured and live fast. Build a solid subscription foundation.</p>
        <div class="rc-hub-arrow">View Paths →</div>
      </a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-hub-card">
        <div class="rc-hub-icon" style="background-color:#FFD706;"><img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Acquire"></div>
        <h3>Acquire</h3>
        <p>Convert more customers and grow your subscriber base.</p>
        <div class="rc-hub-arrow">View Paths →</div>
      </a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-hub-card">
        <div class="rc-hub-icon" style="background-color:#FF9D88;"><img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt="Retain"></div>
        <h3>Retain</h3>
        <p>Reduce involuntary churn and recover revenue.</p>
        <div class="rc-hub-arrow">View Paths →</div>
      </a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale" class="rc-hub-card">
        <div class="rc-hub-icon" style="background-color:#FF5810;"><img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Scale"></div>
        <h3>Scale</h3>
        <p>Expand your business and launch new products.</p>
        <div class="rc-hub-arrow">View Paths →</div>
      </a>
      <a href="https://navigate.recurly.com/event-hub/" class="rc-hub-card" target="_blank" rel="noopener noreferrer">
        <div class="rc-hub-icon" style="background-color:#0075FF;"><img src="https://files.readme.io/563321926f2e7a38fe472432f8618ced99db3e226b70d30b21bbb66ce3c89a97-Events_Icon.png" alt="Events"></div>
        <h3>Events</h3>
        <p>Register for webinars and peer learning sessions.</p>
        <div class="rc-hub-arrow">View Schedule ↗</div>
      </a>
      <!-- FIX #4: event-hub → global-office-hours -->
      <a href="https://navigate.recurly.com/global-office-hours/" class="rc-hub-card" target="_blank" rel="noopener noreferrer">
        <div class="rc-hub-icon" style="background-color:#FF8200;"><img src="https://files.readme.io/3b9d50b3933f927bb9ae2d6e1529d666c17eb63f7305d688d48bb1ce383ac6de-Office_Hours_Icon.png" alt="Office Hours"></div>
        <h3>Office Hours</h3>
        <p>Connect with a Recurly CSM live to ask questions.</p>
        <div class="rc-hub-arrow">Register Now ↗</div>
      </a>
    </div>

    <!-- ── FOOTER SUMMARY ── -->
    <div class="rc-footer-summary">
      <h3>Maximizing your subscription potential</h3>
      <p>Navigate puts Recurly's strategic insights in your hands. Have questions about the program?</p>
      <a href="mailto:support@recurly.com" class="rc-support-link">Reach out to support@recurly.com →</a>
    </div>

    <!-- ── FOOTER NAV — grouped rc-footer-section structure ── -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">

        <div class="rc-footer-section">
          <span class="rc-footer-label">Navigate</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-footer-link">Launch</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-footer-link">Acquire</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-footer-link">Retain</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale" class="rc-footer-link">Scale</a>
        </div>

        <div class="rc-footer-utility">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
            <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt="Home"> Navigate Home
          </a>
          <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
        </div>

      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
