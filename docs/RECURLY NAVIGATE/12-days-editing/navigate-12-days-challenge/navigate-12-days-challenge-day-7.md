---
title: 'Day 7: Spread the joy'
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
  display:inline-flex; align-items:center; gap:8px; font-size:.8rem; font-weight:800;
  padding:6px 12px; border-radius:8px; white-space:nowrap; color:#0D0D0B !important;
}
.rc-perk i { color:#0D0D0B; }
.rc-perk-pts { background:rgba(93,197,46,.16); border:1.5px solid #5DC32E; }
.rc-perk-pts i { color:#2F8A12; }
.rc-perk-gift { background:#FFF3B0; }
.rc-perk-gift i { color:#FF5126; }

/* SECTION HEADINGS */
.rc-section-head { display:flex; align-items:center; gap:14px; margin:52px 0 18px; }
.rc-section-head h2 { font-size:1.4rem; font-weight:800; color:var(--offblack) !important; margin:0; white-space:nowrap; }
.rc-section-head::after { content:""; flex:1; height:1px; background:var(--lightgray); }
.rc-section-head i { color:var(--poppy); font-size:1.1rem; }

/* VIDEO CARD (featured video, design system Component 12a) */
.rc-video-card { border:1px solid var(--lightgray); border-radius:14px; overflow:hidden; background:var(--offwhite); margin:0 0 40px; }
.rc-video-header { background:#0D0D0B; padding:16px 22px; display:flex; align-items:center; gap:10px; }
.rc-video-header h4 { font-size:.88rem; font-weight:700; text-transform:uppercase; letter-spacing:.7px; color:#FFD706 !important; margin:0; }
.rc-video-header span { font-size:.78rem; color:#D1CFC4 !important; margin-left:auto; }
.rc-video-embed { background:#0D0D0B; }
/* Placeholder: shows until the real embed URL is added */
.rc-video-placeholder {
  aspect-ratio:16/9; display:flex; flex-direction:column; align-items:center; justify-content:center;
  gap:12px; padding:24px; text-align:center;
  background:linear-gradient(135deg, #0D0D0B 0%, #1E2A1B 100%);
}
.rc-video-placeholder i { font-size:2.6rem; color:#FFD706; }
.rc-video-placeholder strong { font-size:1rem; font-weight:800; color:#FCFBF7 !important; }
.rc-video-placeholder span { font-size:.88rem; color:#D1CFC4 !important; }
/* When the real embed is added, the iframe uses this rule */
.rc-video-embed iframe { display:block; width:100%; aspect-ratio:16/9; height:auto; border:0; }
.rc-video-caption { padding:12px 22px; font-size:.9rem; color:#807D75 !important; background:#F2F1EA; border-top:1px solid #D1CFC4; line-height:1.5; }

/* TASK CARD */
.rc-story-card {
  background:var(--offwhite); border:1px solid var(--lightgray); border-radius:14px; padding:24px 26px; margin:0 0 4px;
}
.rc-story-card p { font-size:1.02rem; line-height:1.7; color:var(--darkgray) !important; margin:0 0 14px; }
.rc-story-card p:last-child { margin-bottom:0; }
.rc-eyebrow {
  display:inline-block; font-size:.75rem; font-weight:800; letter-spacing:1.2px; text-transform:uppercase;
  color:var(--poppy); margin:0 0 10px;
}
.rc-story-card h3 { font-size:1.4rem; font-weight:800; line-height:1.25; color:var(--offblack) !important; margin:0 0 12px; }
.rc-checks { list-style:none; margin:18px 0 0; padding:0; }
.rc-checks li {
  display:flex; align-items:flex-start; gap:12px; font-size:1.02rem; line-height:1.6;
  color:var(--darkgray) !important; margin-bottom:12px;
}
.rc-checks li:last-child { margin-bottom:0; }
.rc-checks li i { color:var(--green); font-size:1.15rem; margin-top:3px; flex-shrink:0; }
.rc-checks li strong { color:var(--offblack) !important; }

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
.rc-form-box iframe { display:block; width:100%; height:1069px; border:0; }

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

@media (max-width: 900px) {
  .rc-points-perks { align-items:flex-start; }
}
@media (max-width: 768px) {
  .rc-wrap, .rc-topnav { padding-left:20px; padding-right:20px; }
  .rc-hero { padding:44px 20px 46px; }
  .rc-hero h1 { font-size:1.9rem; }
  .rc-points { padding:20px 18px; }
  .rc-points-perks { width:100%; }
  .rc-section-head h2 { font-size:1.2rem; }
  .rc-story-card h3 { font-size:1.2rem; }
  .rc-video-placeholder { padding:18px; }
  .rc-form-box { padding:18px 14px 16px; }
  .rc-form-box iframe { height:1069px; }
  .rc-tease { padding:24px 22px; }
  .rc-tease h3 { font-size:1.3rem; }
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
      <img class="rc-logo" src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly">
      <div><span class="rc-hero-pill"><i class="fa-solid fa-tree"></i> Sleigh your success</span></div>
      <h1>Day 7: Spread the joy</h1>
      <p>Your CSMs have something to say, and so do you. Watch their thank-you, then tell them what you love about working together.</p>
      <div class="rc-hero-meta">Friday, December 11, 2026</div>
      <div class="rc-lights-bottom"></div>
    </div>

    <!-- POINTS BANNER -->
    <div class="rc-points rc-rise-2">
      <div class="rc-points-main">
        <div class="rc-points-num">70 pts</div>
        <div class="rc-points-label">Earn for this task</div>
        <p class="rc-points-text">Send a quote, a video, or both to earn points. Your words are a gift to the team that works with you every day.</p>
      </div>
      <div class="rc-points-perks">
        <span class="rc-perk rc-perk-pts"><i class="fa-solid fa-circle-check"></i> 20 pts for your quote</span>
        <span class="rc-perk rc-perk-gift"><i class="fa-solid fa-star"></i> +50 bonus points for a video</span>
      </div>
    </div>

    <!-- VIDEO -->
    <div class="rc-section-head rc-rise-3"><i class="fa-solid fa-heart"></i><h2>A thank-you from your CSMs</h2></div>
    <div class="rc-video-card rc-rise-3">
      <div class="rc-video-header">
        <h4>A message from your CSMs</h4>
        <span>Watch first</span>
      </div>
      <div class="rc-video-embed">
        <div class="rc-video-placeholder">
          <i class="fa-solid fa-circle-play"></i>
          <strong>CSM video coming soon</strong>
          <span>The thank-you video will appear here.</span>
        </div>
        <!--
          When the video is ready, replace the rc-video-placeholder div above with:
          <iframe src="YOUR_VIDEO_EMBED_URL" loading="lazy" title="A thank-you message from Recurly CSMs" allowfullscreen allow="encrypted-media; fullscreen; microphone; screen-wake-lock;"></iframe>
        -->
      </div>
      <div class="rc-video-caption">Thank you for being part of the Recurly community. Watch the full message, then share what you love.</div>
    </div>

    <!-- TASK -->
    <div class="rc-section-head rc-rise-3"><i class="fa-solid fa-clipboard-list"></i><h2>Your task</h2></div>
    <div class="rc-story-card rc-rise-3">
      <span class="rc-eyebrow">Spread the joy</span>
      <h3>What brings you joy working with your CSM?</h3>
      <p>Your CSM is in your corner every step of the way. Let them know what that means to you.</p>
      <ul class="rc-checks">
        <li><i class="fa-solid fa-circle-check"></i><span><strong>Complete the sentence:</strong> "One thing I love about my Recurly CSM or Navigate is ______."</span></li>
        <li><i class="fa-solid fa-circle-check"></i><span><strong>Bonus:</strong> Record a short video answering "What I love most about my Recurly Customer Success Manager or Navigate is..." Your video is shared with our customer success team as a message from you.</span></li>
      </ul>
    </div>

    <!-- FORM -->
    <div class="rc-section-head rc-rise-4"><i class="fa-solid fa-pen-to-square"></i><h2>Share your joy</h2></div>
    <p class="rc-form-intro rc-rise-4">Submit your quote, your video, or both, so your CSM and the Navigate team can hear from you.</p>
    <div class="rc-form-box rc-rise-4">
      <iframe src="https://docs.google.com/forms/d/e/1FAIpQLScD7v7LKjypOrNBZxDoSPmcW9spdYDFGEXnnp8065VT88HdRQ/viewform?embedded=true" width="100%" height="1069" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
    </div>

    <!-- TEASER -->
    <div class="rc-tease rc-rise-4">
      <p class="rc-tease-eyebrow">Next up</p>
      <h3>See you on Monday.</h3>
      <p>Keep an eye on your inbox Monday morning for your next hint, your updated point total, and a fresh task to earn more points.</p>
      <span class="rc-tease-pill"><i class="fa-solid fa-gift"></i> Day 8 opens Monday, Dec 14</span>
    </div>

    <!-- FUN FACT -->
    <div class="rc-fact rc-rise-4">
      <div class="rc-fact-icon"><i class="fa-solid fa-lightbulb"></i></div>
      <div>
        <strong>Did you know?</strong>
        <p>Giving thanks is the ultimate holiday cheer booster! Expressing authentic gratitude triggers a "warm glow" in the brain that can make you 25% happier, lifting team morale and sparking higher workplace energy!</p>
      </div>
    </div>

    <!-- NAVIGATION -->
    <div class="rc-lp-nav rc-rise-4">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-6" class="rc-btn-prev">← Day 6</a>
      <span class="rc-lp-nav-indicator">Day 7 of 12</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-8" class="rc-btn-next">Go to Day 8 →</a>
    </div>

    <div class="rc-back-center rc-rise-4">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge" class="rc-back"><i class="fa-solid fa-house"></i> Back to challenge home</a>
    </div>

  </div>
</div>
`}</HTMLBlock>
