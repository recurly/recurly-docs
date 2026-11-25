---
title: 'LOCKED PAGE TEMPLATE: KEEP PRIVATE'
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
@media (prefers-reduced-motion: reduce) {
  .rc-rise, .rc-rise-2, .rc-rise-3, .rc-spark { animation: none !important; }
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
.rc-hero-pill {
  display:inline-flex; align-items:center; gap:8px; position:relative; z-index:3;
  background:rgba(93,197,46,.16); border:1.5px solid #5DC32E; color:#5DC32E;
  font-size:.8rem; font-weight:800; letter-spacing:1px; text-transform:uppercase;
  padding:6px 18px; border-radius:20px; margin:26px auto 16px;
}
.rc-hero h1 { font-size:2.6rem; font-weight:800; line-height:1.12; color:#FCFBF7 !important; margin:0 0 14px; position:relative; z-index:3; }
.rc-hero p { font-size:1.02rem; color:#D1CFC4 !important; max-width:720px; margin:0 auto; line-height:1.6; position:relative; z-index:3; }
.rc-hero-meta { margin-top:20px; font-size:.9rem; font-weight:700; color:#FFD706 !important; position:relative; z-index:3; }

/* LOCKED CARD */
.rc-locked-card {
  position:relative; background:#F7F8F9; border:1px dashed #C8CCD0; border-radius:16px;
  padding:40px 32px; margin:44px 0 0; text-align:center;
}
.rc-lock-icon {
  width:72px; height:72px; border-radius:50%; background:#E5E4DE; color:#807D75;
  display:flex; align-items:center; justify-content:center; font-size:1.8rem; margin:0 auto 18px;
}
.rc-locked-card h2 { font-size:1.8rem; font-weight:800; line-height:1.2; color:var(--offblack) !important; margin:0 0 12px; }
.rc-locked-card p { font-size:1.02rem; line-height:1.7; color:var(--darkgray) !important; max-width:620px; margin:0 auto 14px; }
.rc-unlock-pill {
  display:inline-flex; align-items:center; gap:8px; background:rgba(93,197,46,.16); border:1.5px solid #5DC32E;
  color:#2F8A12 !important; font-size:.9rem; font-weight:800; padding:8px 18px; border-radius:20px; margin-top:8px;
}
.rc-unlock-pill i { color:#2F8A12; }

/* BUTTONS */
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
.rc-guide a.rc-btn-prev {
  display:inline-flex; align-items:center; gap:8px; white-space:nowrap;
  background:transparent; color:#0D0D0B !important; padding:13px 24px;
  border-radius:10px; font-weight:700; font-size:.9rem;
  border:2px solid #D1CFC4 !important; border-bottom:2px solid #D1CFC4 !important;
  text-decoration:none !important; transition:all .2s;
}
.rc-guide a.rc-btn-prev:hover { border:2px solid #0D0D0B !important; border-bottom:2px solid #0D0D0B !important; text-decoration:none !important; }

/* NAVIGATION */
.rc-lp-nav { display:flex; align-items:center; justify-content:space-between; gap:16px; margin:40px 0 16px; flex-wrap:wrap; }
.rc-lp-nav-indicator { font-size:.85rem; font-weight:700; color:var(--gray); letter-spacing:.5px; white-space:nowrap; }
.rc-back-center { text-align:center; margin:26px 0 0; }

/* RESPONSIVE */
@media (max-width: 768px) {
  .rc-wrap, .rc-topnav { padding-left:20px; padding-right:20px; }
  .rc-hero { padding:44px 20px 46px; }
  .rc-hero h1 { font-size:1.9rem; }
  .rc-locked-card { padding:28px 20px; }
  .rc-locked-card h2 { font-size:1.4rem; }
  .rc-lp-nav { justify-content:center; }
  .rc-lp-nav-indicator { width:100%; text-align:center; order:-1; }
  .rc-guide a.rc-btn-prev, .rc-guide a.rc-btn-next { padding:10px 16px; font-size:.82rem; }
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
      <h1>Oops! This task is still locked</h1>
      <p>Good things come to those who wait. Your next task isn't open yet, but it's on its way.</p>
      <div class="rc-hero-meta">Opens Friday, December 18, 2026 at 8:00 AM CT</div>
      <div class="rc-lights-bottom"></div>
    </div>

    <!-- LOCKED CARD -->
    <div class="rc-locked-card rc-rise-2">
      <div class="rc-lock-icon"><i class="fa-solid fa-lock"></i></div>
      <h2>This task opens soon</h2>
      <p>It will open on <strong>Friday, December 18, 2026</strong> at <strong>8:00 AM CT</strong>. We'll send you an email as soon as it's ready, so keep an eye on your inbox.</p>
      <span class="rc-unlock-pill"><i class="fa-solid fa-envelope"></i> We'll email you when it opens</span>
    </div>

    <!-- NAVIGATION -->
    <div class="rc-lp-nav rc-rise-3">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge" class="rc-btn-prev">← Challenge home</a>
      <span class="rc-lp-nav-indicator">Locked</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge" class="rc-btn-next">Back to challenge home →</a>
    </div>

    <div class="rc-back-center rc-rise-3">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge" class="rc-back"><i class="fa-solid fa-house"></i> Back to challenge home</a>
    </div>

  </div>
</div>
`}</HTMLBlock>
