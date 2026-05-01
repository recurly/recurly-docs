---
title: 'Recurly Navigate: Acquire'
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
<title>Acquire — Recurly Navigate</title>
<style>
/* Added scroll-behavior and scroll-padding so the sticky nav doesn't cover section titles */
html { scroll-behavior: smooth; scroll-padding-top: 90px; }

.rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
*{box-sizing:border-box}
body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray);background-color:#fff;}

/* TOP BACK NAVIGATION */
.rc-top-nav{padding:20px 40px 16px; margin-bottom: 8px; max-width: 1200px; margin: 0 auto;}
.rc-back-link{color:var(--gray);text-decoration:none;font-weight:700;font-size:.9rem;display:inline-flex;align-items:center;gap:6px;transition:color .2s;}
.rc-back-link:hover{color:var(--orange);}

/* CONTENT WRAPPER */
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* PILLAR HERO */
.rc-hero{
  background: linear-gradient(rgba(13, 13, 11, 0.8), rgba(13, 13, 11, 0.8)), 
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack);
  background-size: cover; 
  color:#fff;
  padding:48px 40px 56px;
  text-align:center;
  border-radius:16px;
  margin-bottom:0; /* Removed margin to let sticky nav sit flush below if needed, but we will add margin below the nav */
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

/* Floating icon styles */
.rc-pillar-hero-icon {
  width: 72px;
  height: 72px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 24px;
}
.rc-pillar-hero-icon img {
  width: 48px;
  height: 48px;
  object-fit: contain;
}

.rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 16px;color:var(--offwhite)}
.rc-hero>p{font-size:1.1rem;opacity:.9;max-width:700px;margin:0 auto 0;color:var(--lightgray);line-height:1.6}

/* STICKY CATEGORY NAVIGATION - UPDATED */
.rc-sticky-nav-wrap {
  position: sticky;
  top: 0;
  z-index: 100;
  background-color: var(--yellow);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08); /* Slight shadow to lift it off the page */
  margin: 24px 0 48px 0;
  border-radius: 12px;
}
.rc-sticky-nav {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 40px; /* Space between text links */
  padding: 18px 24px;
  overflow-x: auto;
  white-space: nowrap;
}
.rc-sticky-link {
  color: var(--offblack);
  text-decoration: none;
  font-weight: 800; /* Bold to stand out */
  font-size: .95rem;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  position: relative;
  transition: opacity .2s;
}
/* Clean underline hover effect instead of buttons */
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
  opacity: 0.8;
}

/* CATEGORY SECTIONS */
.rc-category {
  margin-bottom: 56px;
}
.rc-category h2 {
  font-size: 1.6rem;
  font-weight: 800;
  margin: 0 0 24px;
  color: var(--offblack);
  display: flex;
  align-items: center;
  gap: 12px;
}
.rc-category h2::after {
  content: "";
  flex-grow: 1;
  height: 1px;
  background: var(--lightgray);
}

/* COMPACT HORIZONTAL CARDS */
.rc-path-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
}
.rc-path-card{
  background:var(--offwhite);
  border:1px solid var(--lightgray);
  border-radius:12px;
  padding:20px 24px;
  text-decoration:none !important;
  color:inherit;
  transition:all .2s ease;
  display:grid;
  grid-template-columns: auto 1fr auto; 
  gap: 24px;
  align-items: center;
}
.rc-path-card:hover{
  border-color:var(--yellow);
  box-shadow:0 4px 16px rgba(255,215,6,.12);
  transform:translateY(-2px);
  text-decoration:none !important;
}
.rc-path-icon{
  width:48px;
  height:48px;
  border-radius:10px;
  display:flex;
  align-items:center;
  justify-content:center;
  background:var(--brightgray);
  border:1px solid rgba(0,0,0,0.05);
  flex-shrink: 0;
}
.rc-path-icon img{
  width:24px;
  height:24px;
  object-fit:contain;
}
.rc-path-content {
  min-width: 0; 
}
.rc-path-content h3{
  font-size:1.1rem;
  font-weight:800;
  margin:0 0 6px;
  color:var(--offblack);
  text-decoration:none !important;
}
.rc-path-content p{
  font-size:.92rem;
  color:var(--gray);
  line-height:1.5;
  margin:0;
  text-decoration:none !important;
}
.rc-path-arrow{
  color:var(--orange);
  font-weight:700;
  font-size:.9rem;
  text-decoration:none !important;
  white-space: nowrap;
}

/* GETTING STARTED CTA */
.rc-starter-cta{background:var(--brightgray);border:1px solid var(--lightgray);border-radius:16px;padding:24px 32px;display:flex;align-items:center;justify-content:space-between;gap:24px;margin-bottom:56px;}
.rc-starter-text h3{margin:0 0 6px;font-size:1.2rem;font-weight:800;color:var(--offblack);}
.rc-starter-text p{margin:0;font-size:.95rem;color:var(--darkgray);line-height:1.5;}
.rc-btn-secondary{background:transparent;color:var(--offblack);text-decoration:none;padding:10px 24px;border-radius:10px;font-weight:700;font-size:.9rem;border:2px solid var(--offblack);white-space:nowrap;transition:all .2s;}
.rc-btn-secondary:hover{background:var(--offblack);color:var(--yellow);}

/* BOTTOM NAVIGATION */
.rc-footer-nav{border-top:1px solid var(--lightgray);padding-top:32px;margin-top:20px;text-align:center;}
.rc-footer-title{font-size:.85rem;font-weight:700;text-transform:uppercase;letter-spacing:1px;color:var(--gray);margin-bottom:16px;}
.rc-footer-links{display:flex;flex-wrap:wrap;gap:12px;justify-content:center;}
.rc-footer-link{color:var(--darkgray);text-decoration:none;font-weight:700;font-size:.9rem;padding:8px 20px;background:var(--brightgray);border-radius:8px;transition:all .2s;}
.rc-footer-link:hover{background:var(--offblack);color:var(--yellow);}

/* FOOTER SUMMARY */
.rc-footer-summary{margin-top:40px;padding-top:32px;border-top:1px solid var(--lightgray);text-align:center;color:var(--gray);font-size:.95rem;line-height:1.6;max-width:800px;margin-left:auto;margin-right:auto;margin-bottom:24px;}
.rc-footer-summary strong{color:var(--darkgray);}
.rc-footer-summary a{color:var(--orange);text-decoration:none;font-weight:700;}
.rc-footer-summary a:hover{text-decoration:underline;}

/* RESPONSIVE */
@media(max-width:768px){
  .rc-path-card { grid-template-columns: 1fr; gap: 16px; text-align: left; }
  .rc-path-icon { margin-bottom: 0; }
  .rc-path-arrow { margin-top: 8px; }
  .rc-hero { padding: 36px 20px 40px; }
  .rc-content-wrap { padding: 0 20px; }
  .rc-starter-cta{flex-direction:column;align-items:flex-start;}
}
@media(max-width:640px){
  .rc-sticky-nav { justify-content: flex-start; gap: 24px; } /* Ensures left-to-right scrolling on small mobile */
}
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="index.html" class="rc-back-link">← Back to Navigate Hub</a>
  </div>

  <div class="rc-content-wrap">
    
    <div class="rc-hero">
      <div class="rc-brand-header">
        <img src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly" class="rc-logo-image">
      </div>

      <div class="rc-pillar-hero-icon">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire" />
      </div>

      <h1>Acquire</h1>
      <p>Convert more customers, optimize sign-ups, and sustainably grow your subscriber base by leveraging Recurly's powerful acquisition tools.</p>
    </div>

    <div class="rc-sticky-nav-wrap">
      <div class="rc-sticky-nav">
        <a href="#plans" class="rc-sticky-link">Plans & Pricing</a>
        <a href="#incentives" class="rc-sticky-link">Incentives</a>
        <a href="#gifting" class="rc-sticky-link">Gifting</a>
        <a href="#payments" class="rc-sticky-link">Payments</a>
      </div>
    </div>

    <div id="plans" class="rc-category">
      <h2>Plans & Pricing</h2>
      <div class="rc-path-list">
        
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Plans Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Plans</h3>
            <p>Learn how to seamlessly structure and configure your core subscription plans to attract and convert your target audience.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Pricing Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Pricing Models: Tiers vs Ramp</h3>
            <p>Explore advanced pricing strategies, including tiered models and ramp pricing, to maximize early conversions and lifetime value.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Flexibility Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Plan Flexibility</h3>
            <p>Understand how to offer flexible plan options, allowing subscribers to pause, seamlessly upgrade, or alter their cadence.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

      </div>
    </div>

    <div id="incentives" class="rc-category">
      <h2>Incentives</h2>
      <div class="rc-path-list">
        
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Trials Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Trials</h3>
            <p>Set up and optimize free trials to lower the barrier to entry and effectively turn curious prospects into paying subscribers.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Coupons Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Coupons</h3>
            <p>Create targeted coupon campaigns to drive flash promotions, reward loyalty, and incentivize new sign-ups during key seasons.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

      </div>
    </div>

    <div id="gifting" class="rc-category">
      <h2>Gifting & Expansion</h2>
      <div class="rc-path-list">

        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Gift Cards Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Gift Cards</h3>
            <p>Leverage gift cards as a powerful secondary acquisition channel to reach entirely new audiences and drive immediate prepaid revenue.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Gift Subs Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Gift Subscriptions</h3>
            <p>Enable gift subscriptions so your biggest brand advocates can easily purchase and share your service with friends and family.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

      </div>
    </div>

    <div id="payments" class="rc-category">
      <h2>Payments</h2>
      <div class="rc-path-list">
        
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Payments Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Payments for Acquisition</h3>
            <p>Optimize your checkout experience and payment gateway configurations to reduce friction and boost your overall conversion rates.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

      </div>
    </div>

    <div class="rc-starter-cta">
      <div class="rc-starter-text">
        <h3>👋 Need live guidance on your acquisition strategy?</h3>
        <p>Bring your configuration and growth questions directly to our experts during our weekly open-forum sessions.</p>
      </div>
      <a href="https://navigate.recurly.com/global-office-hours/" class="rc-btn-secondary" target="_blank">Register for Office Hours</a>
    </div>

    <div class="rc-footer-summary">
      <h3><strong>Maximizing your subscription potential.</strong></h3>
      <br>
      <p>Navigate is designed to put Recurly’s strategic insights directly in your hands, ensuring you have the resources needed to drive revenue and scale efficiently. Have questions about the program? Reach out to <a href="mailto:support@recurly.com">support@recurly.com</a>.</p>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-title">Jump to a section</div>
      <div class="rc-footer-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-footer-link">Launch</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-acquire" class="rc-footer-link">Acquire</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-footer-link">Retain</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-scale" class="rc-footer-link">Scale</a>
        <a href="https://navigate.recurly.com/event-hub/" class="rc-footer-link" target="_blank">Events</a>
        <a href="https://navigate.recurly.com/global-office-hours/" class="rc-footer-link" target="_blank">Office Hours</a>
      </div>
    </div>

  </div> </div>
</body>
</html>
`}</HTMLBlock>

<br />
