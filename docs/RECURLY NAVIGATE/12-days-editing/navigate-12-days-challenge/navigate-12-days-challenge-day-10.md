---
title: 'Day 10: The data snowglobe'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Figtree:wght@400;500;600;700;800;900&display=swap">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
body { background: #ffffff !important; }
.rc-guide h1, .rc-guide h2, .rc-guide h3, .rc-guide h4 { border-bottom: none !important; padding-bottom: 0 !important; margin-top: 0; }
.rc-guide, .rc-guide * { font-family: "Figtree", "Helvetica Neue", Helvetica, arial, sans-serif !important; box-sizing: border-box; }
.rc-guide [class^="fa-"], .rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide {
  --yellow:#FFD706; --poppy:#FF5126; --green:#5DC32E; --blue:#008CFF;
  --offblack:#0D0D0B; --darkgray:#32312D; --gray:#807D75; --lightgray:#D1CFC4;
  --brightgray:#F2F1EA; --offwhite:#FCFBF7;
  color: #32312D !important; background:#fff;
}
.rc-guide a, .rc-guide a:link, .rc-guide a:visited { color:#008CFF !important; text-decoration:none !important; border-bottom:0 !important; }
.rc-guide a:hover { color:#0067BE !important; text-decoration:underline !important; }

.rc-wrap { max-width:1120px; margin:0 auto; padding:0 32px 40px; }
.rc-topnav { max-width:1120px; margin:0 auto; padding:20px 32px 12px; }
.rc-guide a.rc-back { color:var(--gray) !important; font-weight:700; font-size:.9rem; }
.rc-guide a.rc-back:hover { color:var(--poppy) !important; text-decoration:none !important; }

/* MOTION */
@keyframes rc-fade-up { from { opacity:0; transform:translateY(16px); } to { opacity:1; transform:none; } }
@keyframes rc-twinkle { 0%,100% { opacity:.25; transform:scale(.8); } 50% { opacity:1; transform:scale(1.15); } }
.rc-rise   { animation: rc-fade-up .7s ease both; }
.rc-rise-2 { animation: rc-fade-up .7s ease .12s both; }
.rc-rise-3 { animation: rc-fade-up .7s ease .24s both; }
.rc-rise-4 { animation: rc-fade-up .7s ease .36s both; }
@media (prefers-reduced-motion: reduce) {
  .rc-rise, .rc-rise-2, .rc-rise-3, .rc-rise-4, .rc-spark { animation: none !important; }
}

/* HERO */
.rc-hero {
  position:relative; background:#0D0D0B; color:#fff; text-align:center;
  padding:54px 40px 56px; border-radius:16px; border:1px solid rgba(255,215,6,.3);
  box-shadow:0 8px 30px rgba(0,0,0,.45); overflow:hidden;
}
.rc-lights-top, .rc-lights-bottom {
  position:absolute; left:0; right:0; height:38px; pointer-events:none; z-index:2;
  background-repeat:repeat-x; background-position:top center;
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='240' height='38' viewBox='0 0 240 38'%3E%3Cpath d='M0,4 Q60,24 120,4 Q180,24 240,4' fill='none' stroke='%231b2e20' stroke-width='2' stroke-linecap='round'/%3E%3Cg%3E%3Ccircle cx='35' cy='22' r='9' fill='%23FFD706' fill-opacity='0.40'/%3E%3Crect x='33' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='35' cy='21' rx='4.5' ry='6.5' fill='%23FFD706'/%3E%3Ccircle cx='33.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='60' cy='27' r='9' fill='%23FF5126' fill-opacity='0.40'/%3E%3Crect x='58' y='17' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='60' cy='26' rx='4.5' ry='6.5' fill='%23FF5126'/%3E%3Ccircle cx='58.5' cy='24' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='85' cy='22' r='9' fill='%235DC32E' fill-opacity='0.40'/%3E%3Crect x='83' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='85' cy='21' rx='4.5' ry='6.5' fill='%235DC32E'/%3E%3Ccircle cx='83.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='155' cy='22' r='9' fill='%23008CFF' fill-opacity='0.40'/%3E%3Crect x='153' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='155' cy='21' rx='4.5' ry='6.5' fill='%23008CFF'/%3E%3Ccircle cx='153.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='180' cy='27' r='9' fill='%23FFD706' fill-opacity='0.40'/%3E%3Crect x='178' y='17' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='180' cy='26' rx='4.5' ry='6.5' fill='%23FFD706'/%3E%3Ccircle cx='178.5' cy='24' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='205' cy='22' r='9' fill='%23FF5126' fill-opacity='0.40'/%3E%3Crect x='203' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='205' cy='21' rx='4.5' ry='6.5' fill='%23FF5126'/%3E%3Ccircle cx='203.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3C/svg%3E");
}
.rc-lights-top { top:0; }
.rc-lights-bottom { bottom:0; transform:rotate(180deg); }
.rc-spark { position:absolute; z-index:3; font-size:.95rem; color:#FFD706; pointer-events:none; animation: rc-twinkle 2.4s ease-in-out infinite; }
.rc-spark.s1 { top:22%; left:12%; }
.rc-spark.s2 { top:30%; right:13%; color:#5DC32E; animation-delay:.6s; }
.rc-spark.s3 { bottom:24%; left:20%; color:#FFFFFF; animation-delay:1.2s; }
.rc-spark.s4 { bottom:20%; right:18%; animation-delay:1.8s; }
.rc-logo { height:28px; display:block; margin:0 auto; position:relative; z-index:3; }
.rc-hero-pill {
  display:inline-flex; align-items:center; gap:8px; position:relative; z-index:3;
  background:rgba(93,197,46,.16); border:1.5px solid #5DC32E; color:#5DC32E;
  font-size:.8rem; font-weight:800; letter-spacing:1px; text-transform:uppercase;
  padding:6px 18px; border-radius:20px; margin:26px auto 16px;
}
.rc-hero h1 { font-size:2.6rem; font-weight:800; line-height:1.12; color:#FCFBF7 !important; margin:0 0 14px; position:relative; z-index:3; }
.rc-hero p { font-size:1.02rem; color:#D1CFC4 !important; max-width:720px; margin:0 auto; line-height:1.6; position:relative; z-index:3; }
.rc-hero-meta { margin-top:20px; font-size:.9rem; font-weight:700; color:#FFD706 !important; position:relative; z-index:3; }

/* POINTS BANNER */
.rc-points {
  display:flex; align-items:center; justify-content:space-between; gap:16px; flex-wrap:wrap;
  margin:32px 0 0; background:var(--offwhite); border:1px solid var(--lightgray);
  border-left:5px solid var(--poppy); border-radius:14px; padding:20px 24px;
}
.rc-points-main { flex:1; min-width:260px; }
.rc-points-num { font-size:2.2rem; font-weight:900; line-height:1; color:var(--poppy); }
.rc-points-label { font-size:.8rem; font-weight:800; text-transform:uppercase; letter-spacing:.8px; color:var(--gray) !important; margin-top:6px; }
.rc-points-text { font-size:1rem; line-height:1.65; color:var(--darkgray) !important; margin:14px 0 0; }
.rc-points-perks { display:flex; flex-direction:column; align-items:flex-end; gap:8px; }
.rc-perk {
  display:inline-flex; align-items:center; gap:8px; font-size:.82rem; font-weight:800;
  padding:7px 14px; border-radius:10px; white-space:nowrap; color:#0D0D0B !important;
}
.rc-perk i { color:#2F8A12; }
.rc-perk-pts { background:rgba(93,197,46,.16); border:1.5px solid #5DC32E; }

/* SECTION HEADINGS */
.rc-section-head { display:flex; align-items:center; gap:14px; margin:52px 0 18px; }
.rc-section-head h2 { font-size:1.4rem; font-weight:800; color:var(--offblack) !important; margin:0; white-space:nowrap; }
.rc-section-head::after { content:""; flex:1; height:1px; background:var(--lightgray); }
.rc-section-head i { color:var(--poppy); font-size:1.1rem; }

/* STORY CARD (image left, text right) */
.rc-story {
  display:grid; grid-template-columns:300px 1fr; gap:28px; align-items:center;
  background:var(--offwhite); border:1px solid var(--lightgray); border-radius:14px; padding:22px;
}
.rc-story-img { width:100%; border-radius:12px; display:block; border:1px solid var(--lightgray); }
.rc-eyebrow {
  display:inline-block; font-size:.75rem; font-weight:800; letter-spacing:1.2px; text-transform:uppercase;
  color:var(--poppy); margin:0 0 10px;
}
.rc-story h3 { font-size:1.5rem; font-weight:800; line-height:1.25; color:var(--offblack) !important; margin:0 0 12px; }
.rc-story p { font-size:1.02rem; line-height:1.7; color:var(--darkgray) !important; margin:0 0 14px; }
.rc-story p:last-child { margin-bottom:0; }

/* HINT CARD */
.rc-hint {
  display:flex; gap:18px; align-items:center; flex-wrap:wrap;
  background:var(--offwhite); border:1px solid var(--lightgray); border-left:5px solid var(--blue);
  border-radius:14px; padding:20px 24px; margin:0 0 22px;
}
.rc-hint-icon { font-size:1.4rem; color:var(--blue); flex-shrink:0; }
.rc-hint-body { flex:1; min-width:240px; }
.rc-hint-body strong { display:block; font-size:1rem; font-weight:800; color:var(--offblack) !important; margin-bottom:4px; }
.rc-hint-body p { font-size:.95rem; line-height:1.6; color:var(--darkgray) !important; margin:0; }
.rc-guide a.rc-btn-path {
  display:inline-flex; align-items:center; justify-content:center; gap:8px; white-space:nowrap;
  background:#FFD706 !important; color:#0D0D0B !important;
  padding:13px 26px; border-radius:10px; font-weight:800; font-size:.95rem;
  border:2px solid #FFD706 !important; border-bottom:2px solid #FFD706 !important;
  text-decoration:none !important; transition:transform .2s ease, background .2s ease;
}
.rc-guide a.rc-btn-path:hover {
  background:#0D0D0B !important; color:#FFD706 !important;
  border:2px solid #0D0D0B !important; border-bottom:2px solid #0D0D0B !important;
  text-decoration:none !important; transform:translateY(-2px);
}

/* FORM CARD */
.rc-form-intro { font-size:1.02rem; line-height:1.6; color:var(--darkgray) !important; margin:0 0 18px; }
.rc-form-box {
  position:relative; background:#FFFFFF; border:2px solid #0D0D0B; border-radius:16px;
  padding:26px 24px 22px; box-shadow:0 14px 36px rgba(13,13,11,.14);
}
.rc-form-box::before {
  content:""; position:absolute; left:-2px; right:-2px; top:-2px; height:8px;
  background:#FFD706; border-radius:16px 16px 0 0;
}
.rc-form-box iframe { display:block; width:100%; height:1180px; border:0; }

/* TEASER */
.rc-tease {
  position:relative; overflow:hidden; margin:44px 0 0; border-radius:16px;
  background:linear-gradient(135deg, #0D0D0B 0%, #1E2A1B 100%);
  border:1px solid rgba(255,215,6,.35); padding:30px 32px; color:#FCFBF7;
}
.rc-tease-eyebrow { font-size:.75rem; font-weight:800; letter-spacing:1.4px; text-transform:uppercase; color:#FFD706 !important; margin:0 0 8px; }
.rc-tease h3 { font-size:1.6rem; font-weight:800; line-height:1.25; color:#FCFBF7 !important; margin:0 0 12px; }
.rc-tease p { font-size:1rem; line-height:1.65; color:#D1CFC4 !important; margin:0 0 14px; max-width:720px; }
.rc-tease-pill {
  display:inline-flex; align-items:center; gap:8px; background:rgba(93,197,46,.16); border:1.5px solid #5DC32E;
  color:#5DC32E !important; font-size:.85rem; font-weight:800; padding:6px 16px; border-radius:20px;
}
.rc-tease-pill i { color:#FFD706; }

/* FUN FACT */
.rc-fact {
  display:flex; gap:16px; align-items:flex-start; margin:40px 0 0;
  background:var(--offwhite); border:1px solid var(--lightgray); border-left:5px solid var(--green);
  border-radius:14px; padding:22px 26px;
}
.rc-fact-icon { font-size:1.4rem; color:var(--green); flex-shrink:0; line-height:1.3; }
.rc-fact strong { display:block; font-size:.95rem; font-weight:800; color:var(--offblack) !important; margin-bottom:4px; }
.rc-fact p { font-size:.95rem; line-height:1.6; color:var(--darkgray) !important; margin:0; }

/* NAVIGATION */
.rc-lp-nav { display:flex; align-items:center; justify-content:space-between; gap:16px; margin:40px 0 16px; flex-wrap:wrap; }
.rc-lp-nav-indicator { font-size:.85rem; font-weight:700; color:var(--gray); letter-spacing:.5px; white-space:nowrap; }
.rc-guide a.rc-btn-prev {
  display:inline-flex; align-items:center; gap:8px; white-space:nowrap;
  background:transparent; color:#0D0D0B !important; padding:13px 24px;
  border-radius:10px; font-weight:700; font-size:.9rem;
  border:2px solid #D1CFC4 !important; border-bottom:2px solid #D1CFC4 !important;
  text-decoration:none !important; transition:all .2s;
}
.rc-guide a.rc-btn-prev:hover { border:2px solid #0D0D0B !important; border-bottom:2px solid #0D0D0B !important; text-decoration:none !important; }
.rc-guide a.rc-btn-next {
  display:inline-flex; align-items:center; justify-content:center; gap:8px; white-space:nowrap;
  background:#FFD706 !important; color:#0D0D0B !important;
  padding:13px 28px; border-radius:10px; font-weight:800; font-size:.95rem;
  border:2px solid #FFD706 !important; border-bottom:2px solid #FFD706 !important;
  text-decoration:none !important; transition:transform .2s ease, background .2s ease;
}
.rc-guide a.rc-btn-next:hover {
  background:#0D0D0B !important; color:#FFD706 !important;
  border:2px solid #0D0D0B !important; border-bottom:2px solid #0D0D0B !important;
  text-decoration:none !important; transform:translateY(-2px);
}
.rc-back-center { text-align:center; margin:26px 0 0; }

/* RESPONSIVE */
@media (max-width: 900px) {
  .rc-story { grid-template-columns:1fr; }
  .rc-story-img { max-width:280px; margin:0 auto; }
  .rc-points-perks { align-items:flex-start; }
}
@media (max-width: 768px) {
  .rc-wrap, .rc-topnav { padding-left:20px; padding-right:20px; }
  .rc-hero { padding:44px 20px 46px; }
  .rc-hero h1 { font-size:1.9rem; }
  .rc-points { padding:20px 18px; }
  .rc-points-perks { width:100%; }
  .rc-section-head h2 { font-size:1.2rem; }
  .rc-story h3 { font-size:1.3rem; }
  .rc-form-box { padding:18px 14px 16px; }
  .rc-form-box iframe { height:1180px; }
  .rc-tease { padding:24px 22px; }
  .rc-tease h3 { font-size:1.3rem; }
  .rc-lp-nav { justify-content:center; }
  .rc-lp-nav-indicator { width:100%; text-align:center; order:-1; }
  .rc-guide a.rc-btn-prev, .rc-guide a.rc-btn-next, .rc-guide a.rc-btn-path { padding:10px 16px; font-size:.82rem; }
}
</style>

<div class="rc-guide">

  <div class="rc-topnav rc-rise">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge" class="rc-back">← Back to challenge home</a>
  </div>

  <div class="rc-wrap">

    <!-- HERO -->
    <div class="rc-hero rc-rise">
      <span class="rc-spark s1"><i class="fa-solid fa-snowflake"></i></span>
      <span class="rc-spark s2"><i class="fa-solid fa-star"></i></span>
      <span class="rc-spark s3"><i class="fa-solid fa-snowflake"></i></span>
      <span class="rc-spark s4"><i class="fa-solid fa-star"></i></span>
      <div class="rc-lights-top"></div>

      <div><span class="rc-hero-pill"><i class="fa-solid fa-tree"></i> Sleigh your success</span></div>
      <h1>Day 10: The data snow globe</h1>
      <p>Shake a snow globe and the flakes swirl until they settle into a clear picture. Your benchmark data works the same way. Look closely and one metric will stand out.</p>
      <div class="rc-hero-meta">Wednesday, December 16, 2026</div>
      <div class="rc-lights-bottom"></div>
    </div>

    <!-- POINTS BANNER -->
    <div class="rc-points rc-rise-2">
      <div class="rc-points-main">
        <div class="rc-points-num">25 pts</div>
        <div class="rc-points-label">Earn for this task</div>
        <p class="rc-points-text">Look at your benchmark reporting, pick one metric to improve in the New Year, and tell us why in the form below.</p>
      </div>
      <div class="rc-points-perks">
        <span class="rc-perk rc-perk-pts"><i class="fa-solid fa-circle-check"></i> 25 pts for sharing your metric</span>
      </div>
    </div>

    <!-- STORY -->
    <div class="rc-section-head rc-rise-2"><i class="fa-solid fa-chart-line"></i><h2>Shake the snow globe</h2></div>
    <div class="rc-story rc-rise-3">
      <img class="rc-story-img" src="https://files.readme.io/cce2a36907fdbc6cb19ffd8b501dcb4d6b162ef0621f41da2d46a75c8343ae67-Gemini_Generated_Image_7e9tol7e9tol7e9t.jpeg" alt="A glass snow globe with a small scene of a dashboard and charts inside">
      <div>
        <span class="rc-eyebrow">A winter reflection</span>
        <h3>What would you change first?</h3>
        <p>Your benchmark dashboard has a lot of flakes swirling around: churn, subscriber acquisition, payment metrics, and more. Once they settle, which one of them usually stands out?</p>
        <p>Open your benchmarks, check your Navigate Monthly Merchant Scorecard for inspiration, and decide which metric you want to move in the New Year.</p>
      </div>
    </div>

    <!-- REFLECTION -->
    <div class="rc-section-head rc-rise-3"><i class="fa-solid fa-pen-to-square"></i><h2>Pick your metric</h2></div>
    <p class="rc-form-intro rc-rise-3">Tell us the one metric you want to improve in the New Year and why it matters most to your business.</p>

    <div class="rc-hint rc-rise-3">
      <i class="fa-solid fa-wand-magic-sparkles rc-hint-icon"></i>
      <div class="rc-hint-body">
        <strong>Need a hint?</strong>
        <p>You'll find the answers here.</p>
      </div>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101?utm_campaign=client+success&amp;utm_medium=event+recurly&amp;utm_source=recurly&amp;utm_content=navigate+12+days+challenge+day+10+resource&amp;utm_term=tactic-clientsuccess;offer-content" class="rc-btn-path" target="_blank" rel="noopener">Explore the path <i class="fa-solid fa-arrow-up-right-from-square"></i></a>
    </div>

    <div class="rc-form-box rc-rise-4">
      <iframe src="https://docs.google.com/forms/d/e/1FAIpQLSez0tPYXYRiZoq4KDVIKDY8V4hqko0AQdrFpXuYnhgh2A16Pw/viewform?embedded=true" width="100%" height="1180" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
    </div>

    <!-- TEASER -->
    <div class="rc-tease rc-rise-4">
      <p class="rc-tease-eyebrow">Next up</p>
      <h3>The next surprise is almost here.</h3>
      <p>Keep an eye on your inbox tomorrow morning for your next hint, your updated point total, and a fresh task to earn more points.</p>
      <span class="rc-tease-pill"><i class="fa-solid fa-gift"></i> Day 11 opens Thursday, Dec 17</span>
    </div>

    <!-- FUN FACT -->
    <div class="rc-fact rc-rise-4">
      <div class="rc-fact-icon"><i class="fa-solid fa-lightbulb"></i></div>
      <div>
        <strong>Did you know?</strong>
        <p>Companies that use subscription analytics to benchmark themselves can increase customer retention rates by up to 60%!</p>
      </div>
    </div>

    <!-- NAVIGATION -->
    <div class="rc-lp-nav rc-rise-4">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-9" class="rc-btn-prev">← Day 9</a>
      <span class="rc-lp-nav-indicator">Day 10 of 12</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-11" class="rc-btn-next">Go to Day 11 →</a>
    </div>

    <div class="rc-back-center rc-rise-4">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge" class="rc-back"><i class="fa-solid fa-house"></i> Back to challenge home</a>
    </div>

  </div>
</div>
`}</HTMLBlock>
