---
title: 'Day 1: Defending your workshop'
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
.rc-guide, .rc-guide * { font-family: "Figtree", "Helvetica Neue", Helvetica, arial, sans-serif !important; box-sizing: border-box; }
.rc-guide [class^="fa-"], .rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide h1, .rc-guide h2, .rc-guide h3, .rc-guide h4 { border-bottom: none !important; padding-bottom: 0 !important; margin-top: 0; }
.rc-guide {
  --yellow:#FFD706; --poppy:#FF5126; --green:#5DC32E; --blue:#008CFF;
  --offblack:#0D0D0B; --darkgray:#32312D; --gray:#807D75; --lightgray:#D1CFC4;
  --brightgray:#F2F1EA; --offwhite:#FCFBF7;
  color: var(--darkgray) !important; background:#fff;
}
.rc-guide a, .rc-guide a:link, .rc-guide a:visited { color:#008CFF !important; text-decoration:none !important; border-bottom:0 !important; }
.rc-guide a:hover { color:#0067BE !important; text-decoration:underline !important; }

.rc-wrap { max-width:1120px; margin:0 auto; padding:0 32px; }
.rc-topnav { max-width:1120px; margin:0 auto; padding:20px 32px 12px; }
.rc-guide a.rc-back { color:var(--gray) !important; font-weight:700; font-size:.9rem; }
.rc-guide a.rc-back:hover { color:var(--poppy) !important; text-decoration:none !important; }

/* ── ANIMATIONS ── */
@keyframes rc-fade-up { from { opacity:0; transform:translateY(16px); } to { opacity:1; transform:translateY(0); } }
@keyframes rc-twinkle { 0%,100% { opacity:.25; transform:scale(.9); } 50% { opacity:1; transform:scale(1.15); } }
.rc-rise { animation:rc-fade-up .7s ease both; }
.rc-rise-2 { animation:rc-fade-up .7s .12s ease both; }
@media (prefers-reduced-motion: reduce) {
  .rc-rise, .rc-rise-2, .rc-spark { animation:none !important; }
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
.rc-spark { position:absolute; color:#FFD706; font-size:14px; z-index:1; animation:rc-twinkle 2.8s ease-in-out infinite; }
.rc-spark.s1 { top:22%; left:9%; }
.rc-spark.s2 { top:30%; right:11%; color:#5DC32E; animation-delay:.9s; }
.rc-spark.s3 { bottom:26%; left:16%; color:#FF5126; font-size:11px; animation-delay:1.6s; }
.rc-spark.s4 { bottom:20%; right:14%; animation-delay:.4s; }

/* POINTS / TASK BANNER */
.rc-points {
  display:flex; align-items:center; justify-content:space-between; gap:16px; flex-wrap:wrap;
  margin:32px 0 0; background:var(--offwhite); border:1px solid var(--lightgray);
  border-left:5px solid var(--poppy); border-radius:14px; padding:20px 24px;
}
.rc-points-main { flex:1; min-width:260px; }
.rc-points-num { font-size:2.2rem; font-weight:900; line-height:1; color:var(--poppy); }
.rc-points-label { font-size:.8rem; font-weight:800; text-transform:uppercase; letter-spacing:.8px; color:var(--gray) !important; margin-top:6px; }
.rc-points-text { font-size:1rem; line-height:1.65; color:var(--darkgray) !important; margin:14px 0 0; }
.rc-bonus {
  display:inline-flex; align-items:center; gap:6px;
  background:#FFF3B0; color:#0D0D0B !important; font-size:.8rem; font-weight:800;
  padding:6px 12px; border-radius:8px;
}
.rc-bonus i { color:#FF5126; }

/* SECTION HEADINGS */
.rc-section-head { display:flex; align-items:center; gap:14px; margin:52px 0 18px; }
.rc-section-head h2 { font-size:1.4rem; font-weight:800; color:var(--offblack) !important; margin:0; white-space:nowrap; }
.rc-section-head::after { content:""; flex:1; height:1px; background:var(--lightgray); }
.rc-section-head i { color:var(--poppy); font-size:1.1rem; }

/* LUNCH + LEARN DETAILS */
.rc-lnl { max-width:860px; }
.rc-eyebrow {
  display:inline-block; font-size:.75rem; font-weight:800; letter-spacing:1.2px; text-transform:uppercase;
  color:var(--poppy); margin:0 0 10px;
}
.rc-lnl-title { font-size:2rem; font-weight:800; line-height:1.2; color:var(--offblack) !important; margin:0 0 10px; }
.rc-lnl-sub { font-size:1.15rem; line-height:1.5; color:var(--darkgray) !important; margin:0 0 18px; }
.rc-when { display:flex; align-items:center; gap:10px; font-size:1rem; font-weight:800; color:var(--offblack) !important; margin:0 0 22px; }
.rc-when i { color:var(--poppy); }

/* BUTTON: left aligned, label centered */
.rc-cta-left { display:flex; justify-content:flex-start; margin:0 0 30px; }
.rc-guide a.rc-btn-path {
  display:inline-flex; align-items:center; justify-content:center; gap:10px; text-align:center;
  background:#FFD706 !important; color:#0D0D0B !important;
  padding:14px 32px; border-radius:10px; font-weight:800; font-size:1rem;
  border:2px solid #FFD706 !important; text-decoration:none !important;
}
.rc-guide a.rc-btn-path:hover {
  background:#0D0D0B !important; color:#FFD706 !important;
  border:2px solid #0D0D0B !important; text-decoration:none !important;
}
.rc-guide a.rc-btn-path i { color:inherit; }

/* DESCRIPTION */
.rc-desc h3 { font-size:1.3rem; font-weight:800; line-height:1.35; color:var(--offblack) !important; margin:0 0 14px; }
.rc-desc p { font-size:1.02rem; line-height:1.7; color:var(--darkgray) !important; margin:0 0 16px; }
.rc-desc p strong { color:var(--offblack) !important; }
.rc-desc h4 { font-size:1.1rem; font-weight:800; color:var(--offblack) !important; margin:26px 0 12px; }
.rc-checks { list-style:none; margin:0 0 20px; padding:0; }
.rc-checks li {
  display:flex; align-items:flex-start; gap:12px; font-size:1.02rem; line-height:1.6;
  color:var(--darkgray) !important; margin-bottom:12px;
}
.rc-checks li i { color:var(--green); font-size:1.15rem; margin-top:3px; flex-shrink:0; }
.rc-checks li strong { color:var(--offblack) !important; }
.rc-note { font-size:.95rem !important; color:var(--gray) !important; }

/* HOSTS (compact) */
.rc-hosts { display:flex; flex-wrap:wrap; gap:12px; margin:0; }
.rc-host {
  display:flex; align-items:center; gap:12px; background:var(--offwhite); border:1px solid var(--lightgray);
  border-radius:12px; padding:12px 18px;
}
.rc-host strong { display:block; font-size:.98rem; font-weight:800; color:var(--offblack) !important; }
.rc-host span { display:block; font-size:.85rem; color:var(--gray) !important; margin-top:2px; }

@media (max-width: 768px) {
  .rc-wrap, .rc-topnav { padding-left:20px; padding-right:20px; }
  .rc-hero { padding:44px 20px 46px; }
  .rc-hero h1 { font-size:1.9rem; }
  .rc-lnl-title { font-size:1.6rem; }
  .rc-cta-left { justify-content:center; }
}
</style>

<div class="rc-guide">

  <div class="rc-topnav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge" class="rc-back">← Back to challenge home</a>
  </div>

  <div class="rc-wrap">

    <!-- HERO -->
    <div class="rc-hero rc-rise">
      <div class="rc-lights-top"></div>
      <span class="rc-spark s1"><i class="fa-solid fa-snowflake"></i></span>
      <span class="rc-spark s2"><i class="fa-solid fa-star"></i></span>
      <span class="rc-spark s3"><i class="fa-solid fa-snowflake"></i></span>
      <span class="rc-spark s4"><i class="fa-solid fa-star"></i></span>
      <img class="rc-logo" src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly">
      <div><span class="rc-hero-pill"><i class="fa-solid fa-tree"></i> Sleigh your success</span></div>
      <h1>Day 1: Defending your workshop</h1>
      <p>Chargebacks can sneak up on even the best subscription businesses. Get ahead of them this season by joining our Lunch + Learn on December 10, and start your 12 days with a win.</p>
      <div class="rc-hero-meta">Thursday, December 3, 2026</div>
      <div class="rc-lights-bottom"></div>
    </div>

    <!-- TASK -->
    <div class="rc-points rc-rise-2">
      <div class="rc-points-main">
        <div class="rc-points-num">15 pts</div>
        <div class="rc-points-label">Register to earn</div>
        <p class="rc-points-text">Register below to earn 15 points. If you attend, you'll earn an extra 50. If you registered previously and are participating in this challenge, no worries! We'll check attendance after the Lunch + Learn and add your points to your total.</p>
      </div>
      <span class="rc-bonus"><i class="fa-solid fa-star"></i> +50 bonus points for attending</span>
    </div>

    <!-- LUNCH + LEARN -->
    <div class="rc-section-head"><i class="fa-solid fa-utensils"></i><h2>Lunch + Learn</h2></div>
    <div class="rc-lnl">
      <span class="rc-eyebrow">Lunch + Learn</span>
      <h2 class="rc-lnl-title">From renewal to dispute: Protecting subscription revenue in 2027</h2>
      <p class="rc-lnl-sub">Catch friction early, stop chargeback abuse, and fix broken customer journeys.</p>
      <div class="rc-when"><i class="fa-regular fa-calendar"></i> December 10, 10:30 AM to 11:00 AM CST</div>

      <div class="rc-cta-left"><a href="#register" class="rc-btn-path">Save your seat <i class="fa-solid fa-arrow-down"></i></a></div>

      <div class="rc-desc">
        <h3>Even with a great customer experience, illegitimate chargebacks will remain an unavoidable reality for subscription businesses heading into 2027.</h3>
        <p><strong>Join Recurly and Justt to get ahead of the curve with a pragmatic look at both sides of the equation</strong>: practical steps you can take throughout the customer journey to prevent disputes, and strategies for recovering revenue when they do happen.</p>
        <p>We'll cover how to spot emerging chargeback trends across payment methods and seasonal shifts, using your dispute data to uncover hidden operational breakdowns and keep more of the money you earn.</p>

        <h4>You'll learn how to:</h4>
        <ul class="rc-checks">
          <li><i class="fa-solid fa-circle-check"></i><span><strong>Uncover broken cx habits</strong> behind your chargeback trends</span></li>
          <li><i class="fa-solid fa-circle-check"></i><span><strong>Find the root causes</strong> in your chargeback data</span></li>
          <li><i class="fa-solid fa-circle-check"></i><span><strong>Catch customer friction</strong> before it turns into a chargeback</span></li>
        </ul>

        <p class="rc-note">Reserve your spot now to lock in early registration. More session details will be added soon.</p>
      </div>
    </div>

    <!-- HOSTS (compact) -->
    <div class="rc-section-head"><i class="fa-solid fa-microphone"></i><h2>Your hosts</h2></div>
    <div class="rc-hosts">
      <div class="rc-host"><div><strong>Sarah Boehmer</strong><span>Senior Director, Payments &amp; Chargebacks Strategy, Justt</span></div></div>
      <div class="rc-host"><div><strong>Christian Oldroyd</strong><span>Customer Success Manager, Recurly</span></div></div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<GoldcastWebinarForm />

<HTMLBlock>{`
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Figtree:wght@400;500;600;700;800;900&display=swap">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
.rc-guide, .rc-guide * { font-family: "Figtree", "Helvetica Neue", Helvetica, arial, sans-serif !important; box-sizing: border-box; }
.rc-guide [class^="fa-"], .rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide {
  --yellow:#FFD706; --poppy:#FF5126; --green:#5DC32E; --blue:#008CFF;
  --offblack:#0D0D0B; --darkgray:#32312D; --gray:#807D75; --lightgray:#D1CFC4;
  --brightgray:#F2F1EA; --offwhite:#FCFBF7;
  color: var(--darkgray) !important; background:#fff;
}
.rc-guide a, .rc-guide a:link, .rc-guide a:visited { color:#008CFF !important; text-decoration:none !important; border-bottom:0 !important; }
.rc-guide a:hover { color:#0067BE !important; text-decoration:underline !important; }

.rc-wrap { max-width:1120px; margin:0 auto; padding:0 32px 40px; }

/* TOMORROW TEASER */
.rc-tease {
  position:relative; overflow:hidden; margin:40px 0 0; border-radius:16px;
  background:linear-gradient(135deg, #0D0D0B 0%, #1E2A1B 100%);
  border:1px solid rgba(255,215,6,.35); padding:30px 32px; color:#FCFBF7;
}
.rc-tease-eyebrow { font-size:.75rem; font-weight:800; letter-spacing:1.4px; text-transform:uppercase; color:#FFD706; margin:0 0 8px; }
.rc-tease h3 { font-size:1.6rem; font-weight:800; line-height:1.25; color:#FCFBF7 !important; margin:0 0 12px; }
.rc-tease p { font-size:1rem; line-height:1.65; color:#D1CFC4 !important; margin:0 0 14px; max-width:720px; }
.rc-tease-points {
  display:inline-flex; align-items:center; gap:8px; background:rgba(93,197,46,.16); border:1.5px solid #5DC32E;
  color:#5DC32E; font-size:.85rem; font-weight:800; padding:6px 16px; border-radius:20px;
}
.rc-tease-points i { color:#FFD706; }

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
.rc-guide span.rc-btn-start {
  background:var(--brightgray); color:var(--gray) !important; padding:13px 24px;
  border-radius:10px; font-weight:700; font-size:.9rem; border:2px solid var(--lightgray);
  cursor:default; display:inline-flex; align-items:center; white-space:nowrap;
}
.rc-guide a.rc-btn-path {
  display:inline-flex; align-items:center; justify-content:center; gap:8px; text-align:center;
  background:#FFD706 !important; color:#0D0D0B !important;
  padding:13px 28px; border-radius:10px; font-weight:800; font-size:.95rem;
  border:2px solid #FFD706 !important; text-decoration:none !important;
}
.rc-guide a.rc-btn-path:hover {
  background:#0D0D0B !important; color:#FFD706 !important;
  border:2px solid #0D0D0B !important; text-decoration:none !important;
}
.rc-guide a.rc-btn-path i { color:inherit; }

.rc-back-center { text-align:center; margin:26px 0 0; }
.rc-guide a.rc-back { color:var(--gray) !important; font-weight:700; font-size:.9rem; }
.rc-guide a.rc-back:hover { color:var(--poppy) !important; text-decoration:none !important; }

@media (max-width: 768px) {
  .rc-wrap { padding-left:20px; padding-right:20px; }
  .rc-tease { padding:24px 22px; }
  .rc-tease h3 { font-size:1.3rem; }
  .rc-lp-nav { justify-content:center; }
}
</style>

<div class="rc-guide">
  <div class="rc-wrap">

    <!-- TOMORROW TEASER -->
    <div class="rc-tease">
      <p class="rc-tease-eyebrow">Tomorrow</p>
      <h3>Something new is coming your way.</h3>
      <p>Keep an eye on your inbox tomorrow morning. Your next hint, your updated point total, and a chance to earn 25 more points on Day 2 will be waiting for you.</p>
      <span class="rc-tease-points"><i class="fa-solid fa-gift"></i> Up to 25 points on Day 2</span>
    </div>

    <!-- FUN FACT -->
    <div class="rc-fact">
      <div class="rc-fact-icon"><i class="fa-solid fa-lightbulb"></i></div>
      <div>
        <strong>Did you know?</strong>
        <p>Up to 75% of holiday chargebacks stem from "friendly fraud," where customers dispute legitimate subscription renewals simply because they didn't recognize the charge or forgot to pause their plan!</p>
      </div>
    </div>

    <!-- NAVIGATION -->
    <div class="rc-lp-nav">
      <span class="rc-btn-start">← Start</span>
      <span class="rc-lp-nav-indicator">Day 1 of 12</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-2" class="rc-btn-path">Go to Day 2 →</a>
    </div>

    <div class="rc-back-center">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge" class="rc-back"><i class="fa-solid fa-house"></i> Back to challenge home</a>
    </div>

  </div>
</div>
`}</HTMLBlock>