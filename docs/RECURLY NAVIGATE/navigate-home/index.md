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
/* Smooth scrolling for page anchors */
html { scroll-behavior: smooth; scroll-padding-top: 90px; }

.rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
*{box-sizing:border-box}
body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray);background-color:#fff;}

/* HERO */
.rc-hero{
  background: linear-gradient(rgba(13, 13, 11, 0.8), rgba(13, 13, 11, 0.8)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack);
  background-size: cover; 
  color:#fff;
  padding:56px 40px 40px;
  text-align:center;
  border-radius:16px;
  margin-bottom:0; 
}

.rc-brand-header {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
  margin-bottom: 30px; 
}
.rc-logo-image {
  height: 40px; 
  width: auto;
}
.rc-logo-text {
  color: white;
  font-family: 'Plus Jakarta Sans', 'Inter', system-ui, sans-serif;
  font-weight: 500;
  font-size: 1rem;
  white-space: nowrap;
  letter-spacing: 0.2px;
}
.rc-logo-divider {
  color: rgba(255, 255, 255, 0.4); 
  margin: 0 4px;
}

.rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
.rc-hero>p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 0;color:var(--lightgray);line-height:1.6}

.rc-hero-stats{display:grid;grid-template-columns:1fr 1fr 1fr;gap:0;margin-top:35px;padding-top:0px;text-align:center}

.rc-hero-stat{padding:0 20px;position:relative}
.rc-hero-stat-num{font-size:1.8rem;font-weight:800;color:var(--yellow);line-height:1;margin-bottom:8px}
.rc-hero-stat-label{font-size:.72rem;font-weight:600;letter-spacing:.8px;text-transform:uppercase;color:var(--lightgray);line-height:1.5}

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
.rc-sticky-nav::-webkit-scrollbar { 
  display: none; 
}

.rc-sticky-link {
  color: var(--offblack);
  text-decoration: none !important;
  font-weight: 800; 
  font-size: .9rem;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  position: relative;
  transition: opacity .2s;
}

/* Home Pin Alignment Class */
.rc-sticky-home {
  display: inline-flex;
  align-items: center;
  gap: 6px;
}
.rc-sticky-home img {
  width: 16px;
  height: 16px;
  object-fit: contain;
}

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
.rc-sticky-link:hover::after {
  width: 100%;
}
.rc-sticky-link:hover {
  opacity: 0.7;
}

/* FEATURED BANNER */
.rc-featured{background:var(--offwhite);border:2px solid var(--yellow);border-radius:16px;padding:24px 32px;display:flex;align-items:center;justify-content:space-between;gap:24px;margin-bottom:48px;}
.rc-featured-content h3{margin:0 0 6px;font-size:1.2rem;font-weight:800;color:var(--offblack);}
.rc-featured-content p{margin:0;font-size:.95rem;color:var(--darkgray);line-height:1.5;}
.rc-featured-tag{display:inline-block;background:var(--offblack);color:var(--yellow);font-size:.7rem;font-weight:700;text-transform:uppercase;letter-spacing:1px;padding:4px 10px;border-radius:6px;margin-bottom:10px;}
.rc-btn{background:var(--yellow);color:var(--offblack);text-decoration:none;padding:12px 24px;border-radius:10px;font-weight:700;font-size:.9rem;white-space:nowrap;transition:transform .2s;}
.rc-btn:hover{transform:translateY(-2px);}

/* MAIN NAVIGATION HUB */
.rc-sec-header{text-align:center;margin-bottom:32px;}
.rc-sec-header h2{font-size:2rem;font-weight:800;margin:0 0 10px;color:var(--offblack)}
.rc-sec-header p{color:var(--gray);font-size:1.05rem;max-width:600px;margin:0 auto;}

.rc-hub-grid{display:grid;grid-template-columns:repeat(3, 1fr);gap:24px;margin-bottom:24px;}
.rc-hub-card{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:16px;padding:32px 24px;text-decoration:none !important;color:inherit;transition:all .2s ease;display:flex;flex-direction:column;align-items:center;text-align:center;}
.rc-hub-card:hover{border-color:var(--yellow);box-shadow:0 8px 24px rgba(255,215,6,.15);transform:translateY(-4px);text-decoration:none !important;}
.rc-hub-icon{width:64px;height:64px;border-radius:14px;display:flex;align-items:center;justify-content:center;margin-bottom:20px;}
.rc-hub-icon img{width:32px;height:32px;object-fit:contain;}
.rc-hub-icon.emoji{font-size:32px;background:var(--brightgray);}
.rc-hub-card h3{font-size:1.3rem;font-weight:800;margin:0 0 10px;color:var(--offblack);text-decoration:none !important;}
.rc-hub-card p{font-size:.9rem;color:var(--gray);line-height:1.5;margin:0;flex-grow:1;text-decoration:none !important;}
.rc-hub-arrow{margin-top:20px;color:var(--orange);font-weight:700;font-size:.9rem;text-decoration:none !important;}

/* GETTING STARTED CTA */
.rc-starter-cta{background:var(--brightgray);border:1px solid var(--lightgray);border-radius:16px;padding:24px 32px;display:flex;align-items:center;justify-content:space-between;gap:24px;margin-bottom:56px;}
.rc-starter-text h3{margin:0 0 6px;font-size:1.2rem;font-weight:800;color:var(--offblack);}
.rc-starter-text p{margin:0;font-size:.95rem;color:var(--darkgray);line-height:1.5;}
.rc-btn-secondary{background:transparent;color:var(--offblack);text-decoration:none;padding:10px 24px;border-radius:10px;font-weight:700;font-size:.9rem;border:2px solid var(--offblack);white-space:nowrap;transition:all .2s;}
.rc-btn-secondary:hover{background:var(--offblack);color:var(--yellow);}

/* BOTTOM CONTEXT (Flywheel & Info) */
.rc-context-wrap{display:grid;grid-template-columns:1fr 1fr;gap:40px;align-items:center;background:var(--offwhite);border:1px solid var(--lightgray);padding:40px;border-radius:16px;margin-bottom:24px;}
.rc-context-info h3{font-size:1.5rem;font-weight:800;margin:0 0 16px;color:var(--offblack);}
.rc-context-info p{font-size:1rem;color:var(--darkgray);line-height:1.7;margin:0 0 16px;}
.rc-flywheel-img{background:var(--offblack);border-radius:16px;padding:24px;display:flex;justify-content:center;}
.rc-flywheel-img img{max-width:100%;height:auto;max-height:300px;}

/* BOTTOM PLAIN TEXT NAVIGATION */
.rc-footer-nav{border-top:1px solid var(--lightgray);padding-top:32px;margin-top:20px;text-align:center;}
.rc-footer-links{display:flex;flex-wrap:wrap;gap:24px;justify-content:center;}
.rc-footer-link{color:var(--gray);text-decoration:none;font-weight:600;font-size:.9rem;transition:color .2s;}
.rc-footer-link:hover{color:var(--orange);text-decoration:underline;}

/* FOOTER SUMMARY */
.rc-footer-summary{margin-top:40px;padding-top:32px;border-top:1px solid var(--lightgray);text-align:center;color:var(--gray);font-size:.95rem;line-height:1.6;max-width:800px;margin-left:auto;margin-right:auto;margin-bottom:24px;}
.rc-footer-summary strong{color:var(--darkgray);}
.rc-footer-summary a{color:var(--orange);text-decoration:none;font-weight:700;}
.rc-footer-summary a:hover{text-decoration:underline;}

/* RESPONSIVE */
@media(max-width:900px){
  .rc-hub-grid{grid-template-columns:repeat(2, 1fr);}
  .rc-context-wrap{grid-template-columns:1fr;}
}
@media(max-width:640px){
  .rc-hero h1{font-size:1.7rem}
  .rc-hero{padding:36px 20px 40px}
  .rc-hero-stats{grid-template-columns:1fr;gap:24px;padding-top:28px}
  .rc-featured, .rc-starter-cta{flex-direction:column;align-items:flex-start;text-align:left;}
  .rc-hub-grid{grid-template-columns:1fr;}
  .rc-context-wrap{padding:24px;}
  
  .rc-sticky-nav { 
    justify-content: flex-start; 
    gap: 24px; 
    padding: 14px 20px;
  }
}
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-hero">
    
    <div class="rc-brand-header">
      <img src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly" class="rc-logo-image">
    </div>

    <h1>Your Subscription Success Hub</h1>
    <p>Everything you need to get the most out of Recurly. Select a path below to uncover best practices, expert guidance, and on-demand education tailored to your KPIs.</p>
    
    <div class="rc-hero-stats">
      <div class="rc-hero-stat">
        <div class="rc-hero-stat-num">Weekly</div>
        <div class="rc-hero-stat-label">Global Office Hours<br>live expert access</div>
      </div>
      <div class="rc-hero-stat">
        <div class="rc-hero-stat-num">Quarterly</div>
        <div class="rc-hero-stat-label">Merchant Spotlight<br>peer learning sessions</div>
      </div>
      <div class="rc-hero-stat">
        <div class="rc-hero-stat-num">24/7</div>
        <div class="rc-hero-stat-label">On-demand paths<br>for every stage</div>
      </div>
    </div>
  </div>

  <div class="rc-sticky-nav-wrap">
    <div class="rc-sticky-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link rc-sticky-home">
        <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt="Navigate Hub">
        Home
      </a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-sticky-link">Launch</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-sticky-link">Acquire</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-sticky-link">Retain</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale" class="rc-sticky-link">Scale</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-events" class="rc-sticky-link">Events</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-office-hours" class="rc-sticky-link">Office Hours</a>
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

  <div class="rc-hub-grid">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-hub-card">
      <div class="rc-hub-icon" style="background-color: #ccc9b8;">
        <img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png" alt="Launch" />
      </div>
      <h3>Launch</h3>
      <p>Get configured and live fast. Build a solid subscription foundation from day one.</p>
      <div class="rc-hub-arrow">View Learning Paths →</div>
    </a>

    <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-acquire" class="rc-hub-card">
      <div class="rc-hub-icon" style="background-color: #ffd706;">
        <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Acquire" />
      </div>
      <h3>Acquire</h3>
      <p>Convert more customers, optimize sign-ups, and grow your subscriber base.</p>
      <div class="rc-hub-arrow">View Learning Paths →</div>
    </a>

    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-hub-card">
      <div class="rc-hub-icon" style="background-color: #ff9d88;">
        <img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt="Retain" />
      </div>
      <h3>Retain</h3>
      <p>Reduce involuntary churn, recover revenue, and keep subscribers engaged.</p>
      <div class="rc-hub-arrow">View Learning Paths →</div>
    </a>

    <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-scale" class="rc-hub-card">
      <div class="rc-hub-icon" style="background-color: #ff5810;">
        <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Scale" />
      </div>
      <h3>Scale</h3>
      <p>Expand your business, launch new products, and optimize payments and analytics.</p>
      <div class="rc-hub-arrow">View Learning Paths →</div>
    </a>

    <a href="https://navigate.recurly.com/event-hub/" class="rc-hub-card" target="_blank">
      <div class="rc-hub-icon emoji">📅</div>
      <h3>Events</h3>
      <p>Register for Merchant Spotlight Webinars and peer-led learning sessions.</p>
      <div class="rc-hub-arrow">View Schedule ↗</div>
    </a>

    <a href="https://navigate.recurly.com/global-office-hours/" class="rc-hub-card" target="_blank">
      <div class="rc-hub-icon emoji">💬</div>
      <h3>Office Hours</h3>
      <p>Connect with a Recurly CSM live. Bring your data, ask questions, or just listen.</p>
      <div class="rc-hub-arrow">Register Now ↗</div>
    </a>
  </div>

  <div class="rc-starter-cta">
    <div class="rc-starter-text">
      <h3>👋 New to Navigate?</h3>
      <p>Welcome! Start here to learn how to use this program, discover everything we offer, and find out how to get support.</p>
    </div>
    <a href="#" class="rc-btn-secondary">Get Started Here</a>
  </div>

  <div class="rc-context-wrap">
    <div class="rc-context-info">
      <h3>The Recurly Flywheel</h3>
      <p>Navigate was built to act as your digital Customer Success Manager. Every resource is structured around the four pillars of a healthy subscription business.</p>
      <p>Whether you're exploring Account Updater to fix retention issues or setting up Dunning windows for the first time, Navigate meets you where you are and helps you get to the next level.</p>
    </div>
    <div class="rc-flywheel-img">
      <img src="https://files.readme.io/85e931cea7e5f65844bb1928786a705578636d4a0e6a258be4f0f4a8cb871cac-Recurly-Flywheel.png" alt="Recurly Flywheel — Launch, Acquire, Retain, Scale" />
    </div>
  </div>
  
  <div class="rc-footer-summary">
    <h3><strong>Maximizing your subscription potential.</strong></h3>
    <br>
    <p>Navigate is designed to put Recurly’s strategic insights directly in your hands, ensuring you have the resources needed to drive revenue and scale efficiently. Have questions about the program? Reach out to <a href="mailto:support@recurly.com">support@recurly.com</a>.</p>
  </div>

  <div class="rc-footer-nav">
    <div class="rc-footer-links">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">Home</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-footer-link">Launch</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-acquire" class="rc-footer-link">Acquire</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-footer-link">Retain</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-scale" class="rc-footer-link">Scale</a>
      <a href="https://navigate.recurly.com/event-hub/" class="rc-footer-link" target="_blank">Events</a>
      <a href="https://navigate.recurly.com/global-office-hours/" class="rc-footer-link" target="_blank">Office Hours</a>
    </div>
  </div>

</div>
</body>
</html>
`}</HTMLBlock>

<br />
