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
a.rc-back { color:var(--gray) !important; font-weight:700; font-size:.9rem; }
a.rc-back:hover { color:var(--poppy) !important; }

/* ── HERO ── */
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

/* ── POINTS BANNER ── */
.rc-points {
  display:flex; align-items:center; justify-content:space-between; gap:16px; flex-wrap:wrap;
  margin:32px 0 0; background:var(--offwhite); border:1px solid var(--lightgray);
  border-left:5px solid var(--poppy); border-radius:14px; padding:20px 24px;
}
.rc-points-left { display:flex; align-items:center; gap:16px; }
.rc-points-num { font-size:2.2rem; font-weight:900; line-height:1; color:var(--poppy); }
.rc-points-label { font-size:.8rem; font-weight:800; text-transform:uppercase; letter-spacing:.8px; color:var(--gray) !important; }
.rc-bonus {
  display:inline-flex; align-items:center; gap:6px;
  background:#FFF3B0; color:#0D0D0B !important; font-size:.8rem; font-weight:800;
  padding:6px 12px; border-radius:8px;
}
.rc-bonus i { color:#FF5126; }

/* ── SECTION HEADINGS ── */
.rc-section-head { display:flex; align-items:center; gap:14px; margin:48px 0 18px; }
.rc-section-head h2 { font-size:1.4rem; font-weight:800; color:var(--offblack) !important; margin:0; white-space:nowrap; }
.rc-section-head::after { content:""; flex:1; height:1px; background:var(--lightgray); }
.rc-section-head i { color:var(--poppy); font-size:1.1rem; }

/* ── TASK CONTENT ── */
.rc-task-card {
  background:var(--offwhite); border:1px solid var(--lightgray); border-radius:14px; padding:28px 30px;
}
.rc-task-card p { font-size:1rem; line-height:1.65; color:var(--darkgray) !important; margin:0 0 16px; }
.rc-task-card p strong { color:var(--offblack) !important; }
.rc-webinar-img { display:block; width:100%; height:auto; border-radius:12px; border:1px solid var(--lightgray); margin:8px 0 0; }

/* ── FORM ── */
.rc-form-card { border:1px solid var(--lightgray); border-radius:14px; overflow:hidden; background:#fff; }
.rc-form-header {
  background:var(--offblack); padding:16px 22px; display:flex; align-items:center; justify-content:space-between; gap:10px;
}
.rc-form-header h3 { font-size:.9rem; font-weight:700; text-transform:uppercase; letter-spacing:.7px; color:#FFD706 !important; margin:0; }
.rc-form-header span { font-size:.8rem; color:#5DC32E; font-weight:800; }
.rc-form-body { padding:24px; min-height:420px; }

/* ── FUN FACT ── */
.rc-fact {
  display:flex; gap:16px; align-items:flex-start; margin:40px 0 0;
  background:var(--offwhite); border:1px solid var(--lightgray); border-left:5px solid var(--green);
  border-radius:14px; padding:22px 26px;
}
.rc-fact-icon { font-size:1.4rem; color:var(--green); flex-shrink:0; line-height:1.3; }
.rc-fact strong { display:block; font-size:.95rem; font-weight:800; color:var(--offblack) !important; margin-bottom:4px; }
.rc-fact p { font-size:.95rem; line-height:1.6; color:var(--darkgray) !important; margin:0; }

/* ── NAVIGATION ── */
.rc-nav { display:flex; align-items:center; justify-content:space-between; gap:16px; flex-wrap:wrap; margin:48px 0 48px; }
a.rc-btn {
  display:inline-flex; align-items:center; gap:8px; padding:13px 24px; border-radius:10px;
  font-weight:800; font-size:.95rem; background:#FF5126 !important; color:#ffffff !important;
  border:2px solid #FF5126 !important; border-bottom:2px solid #FF5126 !important; text-decoration:none !important;
}
a.rc-btn:hover { background:transparent !important; color:#FF5126 !important; }
a.rc-btn-ghost {
  background:var(--brightgray) !important; color:var(--darkgray) !important;
  border:2px solid var(--lightgray) !important; border-bottom:2px solid var(--lightgray) !important;
}
a.rc-btn-ghost:hover { background:var(--lightgray) !important; color:var(--offblack) !important; }

/* ── RESPONSIVE ── */
@media (max-width: 768px) {
  .rc-wrap, .rc-topnav { padding-left:20px; padding-right:20px; }
  .rc-hero { padding:44px 20px 46px; }
  .rc-hero h1 { font-size:1.9rem; }
  .rc-task-card { padding:22px 20px; }
  .rc-form-body { padding:16px; }
  .rc-nav { justify-content:center; }
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
      <h1>Day 1: Defending your workshop</h1>
      <p>Chargebacks can sneak up on even the best subscription businesses. Get ahead of them this season by joining our live Chargeback webinar, and start your 12 days with a win.</p>
      <div class="rc-hero-meta">Thursday, December 3, 2026</div>
      <div class="rc-lights-bottom"></div>
    </div>

    <!-- POINTS -->
    <div class="rc-points">
      <div class="rc-points-left">
        <div class="rc-points-num">15 pts</div>
        <div class="rc-points-label">Earn for registering</div>
      </div>
      <span class="rc-bonus"><i class="fa-solid fa-star"></i> +50 bonus points available</span>
    </div>

    <!-- TASK -->
    <div class="rc-section-head"><i class="fa-solid fa-list-check"></i><h2>Your task</h2></div>
    <div class="rc-task-card">
      <p><strong>Keep the Grinches at bay this season!</strong> Register for our Chargeback webinar, <em>From renewal to dispute: Protecting subscription revenue in 2027</em>, on Thursday, December 10 at 10:30 AM CT. Recurly and Justt will share practical steps to prevent disputes and recover revenue when they happen.</p>
      <p>Attend live on December 10 to unlock 50 bonus points.</p>
      <img class="rc-webinar-img" src="https://files.readme.io/862a611951d98903da5272b81dbb20bca7af514220ff607adbffe8d650b9f242-REcurly_navigate___Justt_Webinar_slide_1.png" alt="Recurly Navigate and Justt webinar slide">
    </div>

    <!-- FORM -->
    <div class="rc-section-head"><i class="fa-solid fa-pen-to-square"></i><h2>Register</h2></div>
    <div class="rc-form-card">
      <div class="rc-form-header">
        <h3>Chargeback webinar registration</h3>
        <span>+15 pts</span>
      </div>
      <div class="rc-form-body">
        <script src="https://form-embed-sdk.goldcast.io/embed.js"></script>
        <div id="goldcast-registration-form"></div>
        <script>
          const url = new URL(window.location.href);
          if (!url.searchParams.has('12_days')) {
            url.searchParams.set('12_days', 'yes');
            window.history.replaceState({}, '', url);
          }
          const widget = new window.GOLDCAST.RegistrationWidget({
            event_id: 'fefc2076-a74f-4126-9ad4-e8e84411d1d3',
            mode: 'embed',
            containerSelector: '#goldcast-registration-form',
            theme_obj: {},
            backendUrl: 'https://backend.goldcast.io'
          });
        </script>
      </div>
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
    <div class="rc-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge" class="rc-btn rc-btn-ghost"><i class="fa-solid fa-house"></i> Challenge home</a>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-2" class="rc-btn">Go to Day 2 <i class="fa-solid fa-arrow-right"></i></a>
    </div>

  </div>
</div>
`}</HTMLBlock>
