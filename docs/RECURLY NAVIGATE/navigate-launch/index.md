---
title: 'Recurly Navigate: Launch'
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
<title>Launch — Recurly Navigate</title>
<style>
.rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
*{box-sizing:border-box}
body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray);background-color:#fff;}

/* TOP BACK NAVIGATION */
.rc-top-nav{padding:20px 0 16px; margin-bottom: 8px;}
.rc-back-link{color:var(--gray);text-decoration:none;font-weight:700;font-size:.9rem;display:inline-flex;align-items:center;gap:6px;transition:color .2s;}
.rc-back-link:hover{color:var(--orange);}

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
  margin-bottom:48px;
}

.rc-brand-header {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
  margin-bottom: 30px; 
}
.rc-logo-image {
  height: 40px; /* Updated to 40px */
  width: auto;
}

/* Pillar specific hero additions */
.rc-pillar-hero-icon {
  width: 72px;
  height: 72px;
  border-radius: 16px;
  background-color: var(--lightgray); /* Launch color */
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 24px;
}
.rc-pillar-hero-icon img {
  width: 36px;
  height: 36px;
  object-fit: contain;
}

.rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 16px;color:var(--offwhite)}
.rc-hero>p{font-size:1.1rem;opacity:.9;max-width:700px;margin:0 auto 0;color:var(--lightgray);line-height:1.6}

/* MAIN CONTENT HEADER */
.rc-sec-header{margin-bottom:28px;}
.rc-sec-header h2{font-size:1.8rem;font-weight:800;margin:0 0 8px;color:var(--offblack)}
.rc-sec-header p{color:var(--gray);font-size:1.05rem;max-width:600px;margin:0;}

/* LEARNING PATH GRID (Responsive auto-fill for any number of paths) */
.rc-path-grid{display:grid;grid-template-columns:repeat(auto-fill, minmax(320px, 1fr));gap:24px;margin-bottom:56px;}

/* CARDS */
.rc-path-card{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:16px;padding:32px 28px;text-decoration:none !important;color:inherit;transition:all .2s ease;display:flex;flex-direction:column;align-items:flex-start;text-align:left;}
.rc-path-card:hover{border-color:var(--yellow);box-shadow:0 8px 24px rgba(255,215,6,.15);transform:translateY(-4px);text-decoration:none !important;}
.rc-path-icon{width:56px;height:56px;border-radius:12px;display:flex;align-items:center;justify-content:center;margin-bottom:20px;background:var(--brightgray);border:1px solid rgba(0,0,0,0.05);}
.rc-path-icon img{width:28px;height:28px;object-fit:contain;}
.rc-path-card h3{font-size:1.25rem;font-weight:800;margin:0 0 10px;color:var(--offblack);text-decoration:none !important;line-height:1.3;}
.rc-path-card p{font-size:.92rem;color:var(--gray);line-height:1.55;margin:0;flex-grow:1;text-decoration:none !important;}
.rc-path-arrow{margin-top:24px;color:var(--orange);font-weight:700;font-size:.9rem;text-decoration:none !important;display:inline-flex;align-items:center;gap:6px;}

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
@media(max-width:640px){
  .rc-hero h1{font-size:2rem}
  .rc-hero{padding:36px 20px 40px}
  .rc-starter-cta{flex-direction:column;align-items:flex-start;text-align:left;}
  .rc-path-grid{grid-template-columns:1fr;}
}
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="#" class="rc-back-link">← Back to Navigate Hub</a>
  </div>

  <div class="rc-hero">
    <div class="rc-brand-header">
      <img src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly" class="rc-logo-image">
    </div>

    <div class="rc-pillar-hero-icon" style="background-color: #ccc9b8;">
      <img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png" alt="Launch" />
    </div>

    <h1>Launch</h1>
    <p>Get configured and live fast. Build a solid subscription foundation from day one by mastering the core elements of the Recurly platform.</p>
  </div>

  <div class="rc-sec-header">
    <h2>Learning Paths</h2>
    <p>Select a path below to begin optimizing your platform setup.</p>
  </div>

  <div class="rc-path-grid">
    
    <a href="#" class="rc-path-card">
      <div class="rc-path-icon">
        <img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png" alt="Optimize Icon" style="opacity: 0.6;" />
      </div>
      <h3>Launchpad Phase One: Optimize</h3>
      <p>Ensure your Recurly instance is configured for maximum impact. Learn best practices for site settings, payment gateways, and baseline security.</p>
      <div class="rc-path-arrow">Start Path →</div>
    </a>

    <a href="#" class="rc-path-card">
      <div class="rc-path-icon">
        <img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png" alt="Metrics Icon" style="opacity: 0.6;" />
      </div>
      <h3>Launchpad Phase Two: Mastering Metrics</h3>
      <p>Dive deep into Recurly Analytics. Understand your core subscription KPIs, how to read your dashboards, and track success from day one.</p>
      <div class="rc-path-arrow">Start Path →</div>
    </a>

  </div>

  <div class="rc-starter-cta">
    <div class="rc-starter-text">
      <h3>👋 Need live guidance on your Launch?</h3>
      <p>Bring your configuration questions directly to our experts during our weekly open-forum sessions.</p>
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

</div>
</body>
</html>
`}</HTMLBlock>

<br />
