---
title: 'Day 2: The gift of feedback'
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

.rc-wrap { max-width:1120px; margin:0 auto; padding:0 32px 40px; }
.rc-topnav { max-width:1120px; margin:0 auto; padding:20px 32px 12px; }
.rc-guide a.rc-back { color:var(--gray) !important; font-weight:700; font-size:.9rem; }
.rc-guide a.rc-back:hover { color:var(--poppy) !important; text-decoration:none !important; }

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

/* SECTION HEADINGS */
.rc-section-head { display:flex; align-items:center; gap:14px; margin:52px 0 18px; }
.rc-section-head h2 { font-size:1.4rem; font-weight:800; color:var(--offblack) !important; margin:0; white-space:nowrap; }
.rc-section-head::after { content:""; flex:1; height:1px; background:var(--lightgray); }
.rc-section-head i { color:var(--poppy); font-size:1.1rem; }

/* TASK DETAILS */
.rc-task-body { max-width:860px; }
.rc-eyebrow {
  display:inline-block; font-size:.75rem; font-weight:800; letter-spacing:1.2px; text-transform:uppercase;
  color:var(--poppy); margin:0 0 10px;
}
.rc-task-title { font-size:2rem; font-weight:800; line-height:1.2; color:var(--offblack) !important; margin:0 0 14px; }
.rc-task-body p { font-size:1.02rem; line-height:1.7; color:var(--darkgray) !important; margin:0 0 16px; }
.rc-task-body p strong { color:var(--offblack) !important; }

.rc-steps { list-style:none; margin:0 0 24px; padding:0; counter-reset:step; }
.rc-steps li {
  display:flex; align-items:flex-start; gap:14px; font-size:1.02rem; line-height:1.6;
  color:var(--darkgray) !important; margin-bottom:14px;
}
.rc-steps li::before {
  counter-increment:step; content:counter(step); flex-shrink:0;
  width:28px; height:28px; border-radius:50%; background:var(--yellow); color:var(--offblack);
  font-weight:800; font-size:.9rem; display:flex; align-items:center; justify-content:center; margin-top:1px;
}
.rc-steps li strong { color:var(--offblack) !important; }

/* BUTTONS */
.rc-cta-left { display:flex; justify-content:flex-start; margin:8px 0 28px; }
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

/* GIFT CARD IMAGE */
.rc-gift-img {
  display:block; max-width:360px; width:100%; height:auto; margin:0 0 28px;
  border-radius:14px; border:1px solid var(--lightgray); background:var(--offwhite);
}

/* FORM CARD (matches Day 1) */
.rc-form-outer { max-width:860px; }
.rc-form-box {
  position:relative; background:#FFFFFF; border:2px solid #0D0D0B; border-radius:16px;
  padding:30px 28px 28px; box-shadow:0 14px 36px rgba(13,13,11,.14);
}
.rc-form-box::before {
  content:""; position:absolute; left:-2px; right:-2px; top:-2px; height:8px;
  background:#FFD706; border-radius:16px 16px 0 0;
}
.rc-form-box iframe { display:block; width:100%; border:0; }

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
.rc-guide a.rc-btn-prev {
  background:var(--brightgray) !important; color:var(--darkgray) !important; padding:13px 24px;
  border-radius:10px; font-weight:700; font-size:.9rem; border:2px solid var(--lightgray) !important;
  display:inline-flex; align-items:center; white-space:nowrap; text-decoration:none !important;
}
.rc-guide a.rc-btn-prev:hover { border-color:var(--gray) !important; text-decoration:none !important; }
.rc-back-center { text-align:center; margin:26px 0 0; }

@media (max-width: 900px) {
  .rc-task-title { font-size:1.7rem; }
}
@media (max-width: 768px) {
  .rc-wrap, .rc-topnav { padding-left:20px; padding-right:20px; }
  .rc-hero { padding:44px 20px 46px; }
  .rc-hero h1 { font-size:1.9rem; }
  .rc-task-title { font-size:1.5rem; }
  .rc-form-box { padding:24px 18px 20px; }
  .rc-cta-left { justify-content:center; }
  .rc-tease { padding:24px 22px; }
  .rc-tease h3 { font-size:1.3rem; }
  .rc-lp-nav { justify-content:center; }
}
</style>

<div class="rc-guide">

  <div class="rc-topnav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge" class="rc-back">← Back to challenge home</a>
  </div>

  <div class="rc-wrap">

    <!-- HERO -->
    <div class="rc-hero">
      <div class="rc-lights-top"></div>
      <img class="rc-logo" src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly">
      <div><span class="rc-hero-pill"><i class="fa-solid fa-tree"></i> Sleigh your success</span></div>
      <h1>Day 2: The gift of feedback</h1>
      <p>Tis the season for giving, and we'd love a little something back. Share your experience with Recurly on G2 and you could unwrap an early holiday bonus.</p>
      <div class="rc-hero-meta">Friday, December 4, 2026</div>
      <div class="rc-lights-bottom"></div>
    </div>

    <!-- POINTS -->
    <div class="rc-points">
      <div class="rc-points-main">
        <div class="rc-points-num">25 pts</div>
        <div class="rc-points-label">Confirm to earn</div>
        <p class="rc-points-text">Visit the Recurly G2 review page, then confirm your visit with the form below to earn 25 points.</p>
      </div>
    </div>

    <!-- ACTION -->
    <div class="rc-section-head"><i class="fa-solid fa-gift"></i><h2>Your early holiday bonus</h2></div>
    <div class="rc-task-body">
      <span class="rc-eyebrow">Advocacy</span>
      <h2 class="rc-task-title">Get an early Christmas bonus from Recurly!</h2>
      <p>Share your experience with Recurly on G2 and you could receive a <strong>$25 Amazon gift card</strong> for your review. Here's how it works:</p>

      <ol class="rc-steps">
        <li><span><strong>Visit the G2 review page</strong> using the button below, then confirm your visit with the form to earn 25 points.</span></li>
        <li><span><strong>Leave your G2 review</strong> to get your $25 Amazon gift card.</span></li>
      </ol>

      <div class="rc-cta-left"><a href="https://www.g2.com/contributor/2026-navigate-12-day-challenge-e40fd4eb-de57-426b-ac8f-2eb70d93d844?secure%5Bpage_id%5D=2026-navigate-12-day-challenge-e40fd4eb-de57-426b-ac8f-2eb70d93d844&amp;secure%5Brewards%5D=true&amp;secure%5Btoken%5D=d90a52a0565d5c1639ccbc649d3a3dc9797b42fd4cc3b228b4462a05f3b4c44b" class="rc-btn-path" target="_blank" rel="noopener">Visit the G2 review page <i class="fa-solid fa-arrow-up-right-from-square"></i></a></div>

      <img class="rc-gift-img" src="https://images.g2crowd.com/uploads/landing_page/reward_image/1682742/7f419f323dd105688fb55313a661c78e%282%29.png" alt="$25 Amazon gift card">
    </div>

    <!-- FORM -->
    <div class="rc-section-head"><i class="fa-solid fa-circle-check"></i><h2>Confirm your visit</h2></div>
    <div class="rc-form-outer">
      <div class="rc-form-box">
        <iframe src="https://docs.google.com/forms/d/e/1FAIpQLSfj_s4iYUGRkyPv6OT-QdbHN6i3QXj3y73MtLki7XXnt25KKQ/viewform?embedded=true" width="100%" height="839" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
      </div>
    </div>

    <!-- TOMORROW TEASER -->
    <div class="rc-tease">
      <p class="rc-tease-eyebrow">Next up</p>
      <h3>Something new is coming your way.</h3>
      <p>Keep an eye on your inbox Monday morning. Your next hint, your updated point total, and more points to earn on Day 3 will be waiting for you.</p>
      <span class="rc-tease-points"><i class="fa-solid fa-gift"></i> Day 3 opens Monday, Dec 7</span>
    </div>

    <!-- FUN FACT -->
    <div class="rc-fact">
      <div class="rc-fact-icon"><i class="fa-solid fa-lightbulb"></i></div>
      <div>
        <strong>Did you know?</strong>
        <p>Before cash holiday bonuses became standard in the early 1900s, people were traditionally rewarded at the end of the year with live turkeys, pocket watches, or candy.</p>
      </div>
    </div>

    <!-- NAVIGATION -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-1" class="rc-btn-prev">← Day 1</a>
      <span class="rc-lp-nav-indicator">Day 2 of 12</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-3" class="rc-btn-path">Go to Day 3 →</a>
    </div>

    <div class="rc-back-center">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge" class="rc-back"><i class="fa-solid fa-house"></i> Back to challenge home</a>
    </div>

  </div>
</div>
`}</HTMLBlock>
