---
title: 'Welcome to Navigate: Home Page'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
/* Smooth scrolling for page anchors */
html { scroll-behavior: smooth; scroll-padding-top: 90px; }

.rc-guide {
  --yellow: #FFD706;
  --orange: #FF8200;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--darkgray);
}

.rc-guide * { box-sizing: border-box; }

/* HERO */
.rc-hero {
  background: linear-gradient(rgba(13, 13, 11, 0.8), rgba(13, 13, 11, 0.8)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack);
  background-size: cover; 
  color: #fff;
  padding: 56px 40px 40px;
  text-align: center;
  border-radius: 16px;
  margin-bottom: 0; 
}

.rc-brand-header { display: flex; align-items: center; justify-content: center; gap: 16px; margin-bottom: 30px; }
.rc-logo-image { height: 40px; width: auto; }

.rc-hero h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; margin: 0 0 14px; color: var(--offwhite); }
.rc-hero > p { font-size: 1.05rem; opacity: .8; max-width: 700px; margin: 0 auto; color: var(--lightgray); line-height: 1.6; }

.rc-hero-stats { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 0; margin-top: 35px; text-align: center; }
.rc-hero-stat-num { font-size: 1.8rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 8px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); }

/* STICKY MAIN NAVIGATION */
.rc-sticky-nav-wrap {
  position: sticky;
  top: 0; 
  z-index: 100;
  background-color: var(--brightgray); 
  box-shadow: 0 4px 12px rgba(0,0,0,0.06); 
  margin: 24px 0 48px 0;
  border-radius: 12px;
  border: 1px solid var(--lightgray); 
}
.rc-sticky-nav {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 36px; 
  padding: 16px 24px;
  overflow-x: auto;
  white-space: nowrap;
  -webkit-overflow-scrolling: touch; 
  scrollbar-width: none; 
}
.rc-sticky-nav::-webkit-scrollbar { display: none; }

.rc-sticky-link, .rc-sticky-link:hover {
  color: var(--offblack);
  text-decoration: none !important; 
  font-weight: 800; 
  font-size: .9rem;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  position: relative;
  transition: opacity .2s;
}

.rc-sticky-home { display: inline-flex; align-items: center; gap: 6px; }
.rc-sticky-home img { width: 16px; height: 16px; object-fit: contain; }

.rc-sticky-link::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  bottom: -4px;
  left: 50%;
  background-color: var(--offblack);
  transition: all 0.2s ease-in-out;
  transform: translateX(-50%);
}
.rc-sticky-link:hover::after { width: 100%; }
.rc-sticky-link:hover { opacity: 0.7; }

/* FEATURED BANNER (Classic Block Style) */
.rc-featured { background: var(--offwhite); border: 2px solid var(--yellow); border-radius: 16px; padding: 24px 32px; display: flex; align-items: center; justify-content: space-between; gap: 24px; margin-bottom: 48px; }
.rc-featured-content h3 { margin: 0 0 6px; font-size: 1.2rem; font-weight: 800; color: var(--offblack); }
.rc-featured-content p { margin: 0; font-size: .95rem; color: var(--darkgray); line-height: 1.5; }
.rc-featured-tag { display: inline-block; background: var(--offblack); color: var(--yellow); font-size: .7rem; font-weight: 700; text-transform: uppercase; letter-spacing: 1px; padding: 4px 10px; border-radius: 6px; margin-bottom: 10px; }
.rc-btn { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 12px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; white-space: nowrap; transition: transform .2s; }
.rc-btn:hover { transform: translateY(-2px); }

/* GETTING STARTED CTA */
.rc-starter-cta { background: var(--brightgray); border: 1px solid var(--lightgray); border-radius: 16px; padding: 24px 32px; display: flex; align-items: center; justify-content: space-between; gap: 24px; margin-bottom: 56px; }
.rc-starter-text h3 { margin: 0 0 6px; font-size: 1.2rem; font-weight: 800; color: var(--offblack); }
.rc-starter-text p { margin: 0; font-size: .95rem; color: var(--darkgray); line-height: 1.5; }
.rc-btn-secondary { background: transparent; color: var(--offblack); text-decoration: none; padding: 10px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid var(--offblack); white-space: nowrap; transition: all .2s; }
.rc-btn-secondary:hover { background: var(--offblack); color: var(--yellow); }

/* HUB GRID */
.rc-sec-header { text-align: center; margin-bottom: 32px; }
.rc-sec-header h2 { font-size: 2rem; font-weight: 800; margin: 0; color: var(--offblack); }
.rc-hub-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px; margin-bottom: 24px; }
.rc-hub-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 16px; padding: 32px 24px; text-decoration: none !important; color: inherit; transition: all .2s ease; display: flex; flex-direction: column; align-items: center; text-align: center; }
.rc-hub-card:hover { border-color: var(--yellow); box-shadow: 0 8px 24px rgba(255,215,6,.15); transform: translateY(-4px); }
.rc-hub-icon { width: 64px; height: 64px; border-radius: 14px; display: flex; align-items: center; justify-content: center; margin-bottom: 20px; }
.rc-hub-icon img { width: 32px; height: 32px; object-fit: contain; }
.rc-hub-card h3 { font-size: 1.3rem; font-weight: 800; margin: 0 0 10px; color: var(--offblack); }
.rc-hub-card p { font-size: .9rem; color: var(--gray); line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-hub-arrow { margin-top: 20px; color: var(--orange); font-weight: 700; font-size: .9rem; }

/* FOOTER SUMMARY CARD */
.rc-footer-summary { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 16px; padding: 40px; margin: 64px auto 32px; text-align: center; max-width: 900px; display: flex; flex-direction: column; align-items: center; gap: 16px; }
.rc-footer-summary h3 { font-size: 1.5rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-footer-summary p { color: var(--darkgray); font-size: 1.05rem; line-height: 1.6; margin: 0; max-width: 750px; }
.rc-support-link { display: inline-block; color: var(--orange); font-weight: 700; text-decoration: none; padding: 10px 20px; background: rgba(255, 130, 0, 0.1); border-radius: 8px; transition: all 0.2s ease; }
.rc-support-link:hover { background: var(--orange); color: white; transform: translateY(-2px); }

/* BOTTOM NAV */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 32px; margin-top: 20px; text-align: center; }
.rc-footer-links { display: flex; flex-wrap: wrap; gap: 24px; justify-content: center; }
.rc-footer-link { color: var(--gray); text-decoration: none; font-weight: 600; font-size: .9rem; }

/* RESPONSIVE */
@media(max-width:900px){ .rc-hub-grid { grid-template-columns: repeat(2, 1fr); } }
@media(max-width:640px){
  .rc-hero h1 { font-size: 1.7rem; }
  .rc-hero-stats { grid-template-columns: 1fr; }
  .rc-featured, .rc-starter-cta { flex-direction: column; align-items: flex-start; text-align: left; }
  .rc-hub-grid { grid-template-columns: 1fr; }
  .rc-sticky-nav { justify-content: flex-start; gap: 24px; padding: 14px 20px; }
}
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-brand-header">
      <img src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly" class="rc-logo-image">
    </div>
    <h1>Your Subscription Success Hub</h1>
    <p>Everything you need to get the most out of Recurly. Select a path below to uncover best practices, expert guidance, and on-demand education tailored to your KPIs.</p>
    <div class="rc-hero-stats">
      <div class="rc-hero-stat"><div class="rc-hero-stat-num">Weekly</div><div class="rc-hero-stat-label">Global Office Hours</div></div>
      <div class="rc-hero-stat"><div class="rc-hero-stat-num">Quarterly</div><div class="rc-hero-stat-label">Merchant Spotlight</div></div>
      <div class="rc-hero-stat"><div class="rc-hero-stat-num">24/7</div><div class="rc-hero-stat-label">On-demand paths</div></div>
    </div>
  </div>

  <div class="rc-sticky-nav-wrap">
    <div class="rc-sticky-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link rc-sticky-home">
        <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt="Home"> Home
      </a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-sticky-link">Launch</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-sticky-link">Acquire</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-sticky-link">Retain</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale" class="rc-sticky-link">Scale</a>
      <a href="https://navigate.recurly.com/event-hub/" class="rc-sticky-link" target="_blank">Events</a>
      <a href="https://navigate.recurly.com/global-office-hours/" class="rc-sticky-link" target="_blank">Office Hours</a>
    </div>
  </div>

  <div class="rc-featured">
    <div class="rc-featured-content">
      <span class="rc-featured-tag">Featured Event</span>
      <h3>Upcoming: Global Office Hours</h3>
      <p>Join our lead CSMs this Thursday to discuss optimizing your Dunning windows and recovering failed payments.</p>
    </div>
    <a href="https://navigate.recurly.com/global-office-hours/" class="rc-btn" target="_blank">Register Now</a>
  </div>

  <div class="rc-sec-header">
    <h2>Explore Navigate</h2>
    <p>Choose your objective to access self-serve learning paths and resources.</p>
  </div>

  <div class="rc-starter-cta">
    <div class="rc-starter-text">
      <h3>👋 New to Navigate?</h3>
      <p>Welcome! Start here to learn how to use this program and find support.</p>
    </div>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home-getting-started" class="rc-btn-secondary">Get Started Here</a>
  </div>

  <div class="rc-hub-grid">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-hub-card">
      <div class="rc-hub-icon" style="background-color: #ccc9b8;"><img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png"></div>
      <h3>Launch</h3><p>Get configured and live fast. Build a solid subscription foundation.</p><div class="rc-hub-arrow">View Paths →</div>
    </a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-hub-card">
      <div class="rc-hub-icon" style="background-color: #ffd706;"><img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png"></div>
      <h3>Acquire</h3><p>Convert more customers and grow your subscriber base.</p><div class="rc-hub-arrow">View Paths →</div>
    </a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-hub-card">
      <div class="rc-hub-icon" style="background-color: #ff9d88;"><img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png"></div>
      <h3>Retain</h3><p>Reduce involuntary churn and recover revenue.</p><div class="rc-hub-arrow">View Paths →</div>
    </a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale" class="rc-hub-card">
      <div class="rc-hub-icon" style="background-color: #ff5810;"><img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png"></div>
      <h3>Scale</h3><p>Expand your business and launch new products.</p><div class="rc-hub-arrow">View Paths →</div>
    </a>
    <a href="https://navigate.recurly.com/event-hub/" class="rc-hub-card" target="_blank">
      <div class="rc-hub-icon" style="background-color: #0075ff;"><img src="https://files.readme.io/563321926f2e7a38fe472432f8618ced99db3e226b70d30b21bbb66ce3c89a97-Events_Icon.png"></div>
      <h3>Events</h3><p>Register for Webinars and peer learning sessions.</p><div class="rc-hub-arrow">View Schedule ↗</div>
    </a>
    <a href="https://navigate.recurly.com/global-office-hours/" class="rc-hub-card" target="_blank">
      <div class="rc-hub-icon" style="background-color: #ff8200;"><img src="https://files.readme.io/3b9d50b3933f927bb9ae2d6e1529d666c17eb63f7305d688d48bb1ce383ac6de-Office_Hours_Icon.png"></div>
      <h3>Office Hours</h3><p>Connect with a Recurly CSM live to ask questions.</p><div class="rc-hub-arrow">Register Now ↗</div>
    </a>
  </div>

  <div class="rc-footer-summary">
    <h3>Maximizing your subscription potential</h3>
    <p>Navigate puts Recurly’s strategic insights in your hands. Have questions about the program?</p>
    <a href="mailto:support@recurly.com" class="rc-support-link">Reach out to support@recurly.com →</a>
  </div>

  <div class="rc-footer-nav">
    <div class="rc-footer-links">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">Home</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-footer-link">Launch</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-footer-link">Acquire</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-footer-link">Retain</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale" class="rc-footer-link">Scale</a>
    </div>
  </div>
</div>
`}</HTMLBlock>

<br />
