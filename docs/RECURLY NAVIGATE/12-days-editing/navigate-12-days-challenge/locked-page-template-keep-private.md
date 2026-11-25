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
  --brightgray:#F2F1EA; --offwhite:#FCFBF7; --ice:#BFE3FF;
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
  padding:54px 40px 56px; border-radius:16px; border:1px solid rgba(191,227,255,.35);
  box-shadow:0 8px 30px rgba(0,0,0,.45), inset 0 0 40px rgba(191,227,255,.10); overflow:hidden;
}
/* Frost band: icy gradient with faint snowflake marks, top and bottom */
.rc-frost {
  position:absolute; left:0; right:0; height:64px; pointer-events:none; z-index:2;
  background-image:
    url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='90' height='60' viewBox='0 0 90 60'%3E%3Cg stroke='%23BFE3FF' stroke-width='1.6' stroke-linecap='round' fill='none' opacity='0.55'%3E%3Cpath d='M20 8v16M12 16h16M14 10l12 12M26 10L14 22'/%3E%3Cpath d='M66 30v14M59 37h14M61 32l10 10M71 32L61 42'/%3E%3C/g%3E%3C/svg%3E"),
    linear-gradient(180deg, rgba(191,227,255,.30) 0%, rgba(191,227,255,0) 100%);
  background-repeat:repeat-x, no-repeat;
  background-position:top center, top center;
}
.rc-frost-top { top:0; }
.rc-frost-bottom { bottom:0; transform:rotate(180deg); }
.rc-spark { position:absolute; z-index:3; font-size:.95rem; color:#FFD706; pointer-events:none; animation: rc-twinkle 2.4s ease-in-out infinite; }
.rc-spark.s1 { top:22%; left:12%; }
.rc-spark.s2 { top:30%; right:13%; color:#BFE3FF; animation-delay:.6s; }
.rc-spark.s3 { bottom:24%; left:20%; color:#FFFFFF; animation-delay:1.2s; }
.rc-spark.s4 { bottom:20%; right:18%; color:#BFE3FF; animation-delay:1.8s; }
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
  width:72px; height:72px; border-radius:50%; background:#E3F2FD; color:#3A8FC7;
  display:flex; align-items:center; justify-content:center; font-size:1.8rem; margin:0 auto 18px;
  border:1px solid #BFE3FF;
}
.rc-locked-card h2 { font-size:1.8rem; font-weight:800; line-height:1.2; color:var(--offblack) !important; margin:0 0 12px; }
.rc-locked-card p { font-size:1.02rem; line-height:1.7; color:var(--darkgray) !important; max-width:620px; margin:0 auto 14px; }
.rc-unlock-pill {
  display:inline-flex; align-items:center; gap:8px; background:rgba(93,197,46,.16); border:1.5px solid #5DC32E;
  color:#2F8A12 !important; font-size:.9rem; font-weight:800; padding:8px 18px; border-radius:20px; margin-top:8px;
}
.rc-unlock-pill i { color:#2F8A12; }

/* LARGE CTA */
.rc-cta-large { display:flex; flex-direction:column; align-items:center; gap:10px; margin:44px 0 16px; }
.rc-guide a.rc-btn-large {
  display:inline-flex; align-items:center; justify-content:center; gap:12px; white-space:nowrap;
  background:#FFD706 !important; color:#0D0D0B !important;
  padding:18px 44px; border-radius:12px; font-weight:800; font-size:1.1rem;
  border:2px solid #FFD706 !important; border-bottom:2px solid #FFD706 !important;
  text-decoration:none !important; transition:transform .2s ease, background .2s ease;
}
.rc-guide a.rc-btn-large:hover {
  background:#0D0D0B !important; color:#FFD706 !important;
  border:2px solid #0D0D0B !important; border-bottom:2px solid #0D0D0B !important;
  text-decoration:none !important; transform:translateY(-2px);
}

/* RESPONSIVE */
@media (max-width: 768px) {
  .rc-wrap, .rc-topnav { padding-left:20px; padding-right:20px; }
  .rc-hero { padding:44px 20px 46px; }
  .rc-hero h1 { font-size:1.9rem; }
  .rc-locked-card { padding:28px 20px; }
  .rc-locked-card h2 { font-size:1.4rem; }
  .rc-guide a.rc-btn-large { width:100%; padding:16px 24px; font-size:1rem; }
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
      <div class="rc-frost rc-frost-top"></div>

      <div><span class="rc-hero-pill"><i class="fa-solid fa-tree"></i> Sleigh your success</span></div>
      <h1>Oops! This task is still locked</h1>
      <p>Good things come to those who wait. Your next task isn't open yet, but it's on its way.</p>
      <div class="rc-hero-meta">Opens Friday, December 18, 2026 at 8:00 AM CT</div>
      <div class="rc-frost rc-frost-bottom"></div>
    </div>

    <!-- LOCKED CARD -->
    <div class="rc-locked-card rc-rise-2">
      <div class="rc-lock-icon"><i class="fa-solid fa-lock"></i></div>
      <h2>This task opens soon</h2>
      <p>It will open on <strong>Friday, December 18, 2026</strong> at <strong>8:00 AM CT</strong>. We'll send you an email as soon as it's ready, so keep an eye on your inbox.</p>
      <span class="rc-unlock-pill"><i class="fa-solid fa-envelope"></i> We'll email you when it opens</span>
    </div>

    <!-- LARGE CTA -->
    <div class="rc-cta-large rc-rise-3">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge" class="rc-btn-large"><i class="fa-solid fa-house"></i> Return to challenge home</a>
    </div>

  </div>
</div>
`}</HTMLBlock>
