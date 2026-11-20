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
.rc-guide h1, .rc-guide h2, .rc-guide h3, .rc-guide h4 { border-bottom: none !important; padding-bottom: 0 !important; }
.rc-guide {
  --yellow: #FFD706; --poppy: #FF5126; --green: #5DC32E; --blue: #008CFF;
  --offblack: #0D0D0B; --darkgray: #32312D; --gray: #807D75; --lightgray: #D1CFC4;
  --brightgray: #F2F1EA; --offwhite: #FCFBF7;
  color: var(--darkgray) !important; background: #ffffff;
}
.rc-guide a, .rc-guide a:link, .rc-guide a:visited { color: #008CFF !important; text-decoration: none !important; border-bottom: 0 !important; }
.rc-guide a:hover { color: #0067BE !important; text-decoration: underline !important; }

.rc-content-wrap { max-width: 1100px; margin: 0 auto; padding: 0 32px; }
.rc-top-nav { max-width: 1100px; margin: 0 auto; padding: 20px 32px 12px; }
a.rc-back-link { color: var(--gray) !important; font-weight: 700; font-size: .9rem; display: inline-flex; gap: 6px; }
a.rc-back-link:hover { color: var(--poppy) !important; }

/* HERO */
.rc-hero {
  position: relative; background: var(--offblack); color: #fff; text-align: center;
  padding: 56px 40px 52px; border-radius: 16px; border: 1px solid rgba(255,215,6,.3);
  box-shadow: 0 8px 30px rgba(0,0,0,.45); overflow: hidden;
}
.rc-hero::before, .rc-hero::after {
  content: ""; position: absolute; left: 0; right: 0; height: 6px;
  background: repeating-linear-gradient(90deg, #FFD706 0 22px, #FF5126 22px 44px, #5DC32E 44px 66px, #008CFF 66px 88px);
  opacity: .9;
}
.rc-hero::before { top: 0; } .rc-hero::after { bottom: 0; }
.rc-logo { height: 28px; display: block; margin: 0 auto 4px; }
.rc-day-pill {
  display: inline-flex; align-items: center; gap: 8px; background: var(--poppy); color: #fff;
  font-size: .78rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 18px; border-radius: 20px; margin: 22px 0 14px;
}
.rc-hero h1 { font-size: 2.3rem; font-weight: 800; line-height: 1.15; color: #FCFBF7 !important; margin: 0 0 14px; }
.rc-hero p { font-size: 1.02rem; color: #D1CFC4 !important; max-width: 700px; margin: 0 auto; line-height: 1.6; }
.rc-hero-meta { margin-top: 22px; font-size: .9rem; font-weight: 700; color: var(--yellow) !important; letter-spacing: .4px; }

/* POINTS BANNER */
.rc-points-banner {
  background: var(--offwhite); border: 1px solid var(--lightgray); border-left: 5px solid var(--poppy);
  border-radius: 12px; padding: 18px 24px; display: flex; align-items: center; gap: 18px; margin: 32px 0;
}
.rc-points-badge {
  background: var(--poppy); color: #fff; font-size: 1.15rem; font-weight: 900;
  padding: 8px 16px; border-radius: 10px; white-space: nowrap;
}
.rc-points-text strong { display: block; font-size: .95rem; color: var(--offblack) !important; margin-bottom: 2px; }
.rc-points-text p { font-size: .88rem; color: var(--gray) !important; margin: 0; line-height: 1.5; }

/* SECTIONS */
.rc-section { margin-bottom: 40px; }
.rc-section h2 {
  font-size: 1.45rem; font-weight: 800; color: var(--offblack) !important; margin: 0 0 16px;
  display: flex; align-items: center; gap: 12px;
}
.rc-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-section p { font-size: .95rem; line-height: 1.65; margin: 0 0 14px; }
.rc-fa { color: var(--poppy); font-size: 1.1rem; }

/* STEPS */
.rc-steps { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 8px 0 0; }
.rc-step {
  background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px;
}
.rc-step-num {
  display: inline-flex; align-items: center; justify-content: center; width: 32px; height: 32px;
  border-radius: 50%; background: var(--green); color: #fff; font-weight: 800; margin-bottom: 10px;
}
.rc-step h4 { font-size: 1rem; font-weight: 800; color: var(--offblack) !important; margin: 0 0 6px; }
.rc-step p { font-size: .88rem; color: var(--gray) !important; margin: 0; line-height: 1.5; }

/* EVENT CARD */
.rc-event-card {
  display: grid; grid-template-columns: 1fr 1fr; gap: 0; border: 1px solid var(--lightgray);
  border-radius: 14px; overflow: hidden; margin-bottom: 40px;
}
.rc-event-info { background: var(--offblack); color: #fff; padding: 30px 32px; }
.rc-event-info h3 { color: var(--yellow) !important; font-size: .8rem; text-transform: uppercase; letter-spacing: .8px; margin: 0 0 12px; }
.rc-event-info h4 { color: #fff !important; font-size: 1.2rem; font-weight: 800; margin: 0 0 12px; line-height: 1.3; }
.rc-event-info p { color: #D1CFC4 !important; font-size: .9rem; line-height: 1.55; margin: 0 0 14px; }
.rc-event-info ul { margin: 0; padding-left: 18px; color: #D1CFC4; font-size: .9rem; line-height: 1.6; }
.rc-event-info li strong { color: #fff; }
.rc-event-when { font-weight: 800; color: #FCFBF7 !important; font-size: .92rem; margin-bottom: 12px !important; }

/* FORM PLACEHOLDER (replace with Goldcast embed) */
.rc-form-wrap { background: var(--brightgray); padding: 30px 32px; }
.rc-form-wrap h3 { font-size: 1.3rem; font-weight: 800; color: var(--offblack) !important; margin: 0 0 6px; }
.rc-form-wrap .rc-form-sub { font-size: .85rem; color: var(--gray) !important; margin: 0 0 18px; }
.rc-faux-field { margin-bottom: 14px; }
.rc-faux-field label { display: block; font-size: .85rem; font-weight: 700; color: var(--offblack) !important; margin-bottom: 4px; }
.rc-faux-field label span { color: var(--poppy); }
.rc-faux-field div {
  background: #fff; border: 1px solid #bfbcb0; border-radius: 8px; height: 40px;
}
.rc-faux-submit {
  display: inline-block; background: var(--yellow); color: var(--offblack) !important; font-weight: 800;
  padding: 12px 26px; border-radius: 10px; margin-top: 6px; border: 0 !important;
}
#goldcast-registration-form { min-height: 10px; }

/* BUTTONS + NAV */
.rc-btn {
  display: inline-flex; align-items: center; gap: 8px; background: var(--poppy) !important; color: #fff !important;
  padding: 13px 26px; border-radius: 10px; font-weight: 800; font-size: .95rem; border: 2px solid var(--poppy) !important;
}
.rc-btn:hover { background: transparent !important; color: var(--poppy) !important; text-decoration: none !important; }
.rc-btn-ghost { background: var(--brightgray) !important; color: var(--gray) !important; border: 2px solid var(--lightgray) !important; }
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; flex-wrap: wrap; }
.rc-lp-nav-indicator { font-size: .85rem; font-weight: 700; color: var(--gray) !important; letter-spacing: .5px; }

.rc-callout {
  background: var(--offwhite); border: 1px solid var(--lightgray); border-left: 5px solid var(--green);
  border-radius: 12px; padding: 18px 24px; display: flex; gap: 14px; margin: 20px 0 32px;
}
.rc-callout strong { display: block; color: var(--offblack) !important; font-weight: 800; margin-bottom: 4px; }
.rc-callout p { margin: 0; font-size: .9rem; line-height: 1.55; }

.rc-resources { background: var(--brightgray); border-left: 4px solid var(--green); border-radius: 10px; padding: 20px 24px; margin-top: 32px; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray) !important; margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 6px 20px; }
.rc-resource-links a { color: var(--gray) !important; text-decoration: underline !important; font-size: .88rem; font-weight: 500; }

@media (max-width: 768px) {
  .rc-content-wrap, .rc-top-nav { padding-left: 20px; padding-right: 20px; }
  .rc-hero { padding: 44px 20px 40px; }
  .rc-hero h1 { font-size: 1.75rem; }
  .rc-steps, .rc-event-card { grid-template-columns: 1fr; }
  .rc-points-banner { flex-direction: column; align-items: flex-start; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge" class="rc-back-link">← Back to challenge overview</a>
  </div>

  <div class="rc-content-wrap">

    <!-- HERO -->
    <div class="rc-hero">
      <img class="rc-logo" src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly">
      <span class="rc-day-pill"><i class="fa-solid fa-snowflake"></i> Day 1 of 12 · Thu, Dec 3</span>
      <h1>Defending your workshop</h1>
      <p>Keep the Grinches at bay this season. Register for our upcoming chargeback webinar and start your 12-day challenge with a win.</p>
      <div class="rc-hero-meta">Live webinar: Thursday, December 10 · 10:30–11:00 AM CST</div>
    </div>

    <!-- POINTS -->
    <div class="rc-points-banner">
      <div class="rc-points-badge"><i class="fa-solid fa-gift"></i> +15 pts</div>
      <div class="rc-points-text">
        <strong>Register today to earn 15 points</strong>
        <p>Attend the live webinar or watch on demand to earn an additional 50 bonus points. Bonus points are added after the event.</p>
      </div>
    </div>

    <!-- EVENT CARD -->
    <div class="rc-event-card">
      <div class="rc-event-info">
        <h3>Lunch + Learn</h3>
        <h4>From renewal to dispute: Protecting subscription revenue in 2027</h4>
        <p class="rc-event-when"><i class="fa-regular fa-calendar"></i> December 10 · 10:30–11:00 AM CST</p>
        <p>Catch friction early, stop chargeback abuse, and fix broken customer journeys.</p>
        <ul>
          <li><strong>Uncover</strong> broken CX habits behind your chargeback trends</li>
          <li><strong>Find</strong> the root causes in your chargeback data</li>
          <li><strong>Catch</strong> customer friction before it turns into a chargeback</li>
        </ul>
      </div>
      <div class="rc-form-wrap" id="register">
        <h3>Register here</h3>
        <p class="rc-form-sub">Save your seat. You'll earn 15 points when you register.</p>

        <!-- PLACEHOLDER: replace this block with the Goldcast registration embed when support provides it.
             Hidden field: 12_days (should auto-fill from URL parameter ?12_days=yes). -->
        <div id="goldcast-registration-form">
          <div class="rc-faux-field"><label>First Name <span>*</span></label><div></div></div>
          <div class="rc-faux-field"><label>Last Name <span>*</span></label><div></div></div>
          <div class="rc-faux-field"><label>Email <span>*</span></label><div></div></div>
          <div class="rc-faux-field"><label>Company <span>*</span></label><div></div></div>
          <div class="rc-faux-field"><label>Job Title</label><div></div></div>
          <span class="rc-faux-submit">Submit</span>
        </div>
      </div>
    </div>

    <!-- HOW IT WORKS -->
    <div class="rc-section">
      <h2><i class="fa-solid fa-list-check rc-fa"></i> How to complete today's task</h2>
      <div class="rc-steps">
        <div class="rc-step">
          <span class="rc-step-num">1</span>
          <h4>Register</h4>
          <p>Fill out the registration form above to save your seat for the December 10 webinar.</p>
        </div>
        <div class="rc-step">
          <span class="rc-step-num">2</span>
          <h4>Confirm your points</h4>
          <p>Registering earns you 15 points. You'll see them added to your challenge total.</p>
        </div>
        <div class="rc-step">
          <span class="rc-step-num">3</span>
          <h4>Show up on Dec 10</h4>
          <p>Attend live or watch on demand to earn 50 bonus points, added after the event.</p>
        </div>
      </div>
    </div>

    <!-- CALLOUT -->
    <div class="rc-callout">
      <div><i class="fa-solid fa-lightbulb" style="color: var(--green); font-size: 1.2rem;"></i></div>
      <div>
        <strong>Why this matters</strong>
        <p>Chargebacks happen even when your customer experience is strong. This session shows you how to spot the trends early and protect the revenue you've already earned.</p>
      </div>
    </div>

    <!-- NAV -->
    <div class="rc-lp-nav">
      <span class="rc-btn rc-btn-ghost">← Start</span>
      <span class="rc-lp-nav-indicator">Day 1 of 12</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-2" class="rc-btn">Next: Day 2 →</a>
    </div>

    <!-- RESOURCES -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open" style="color: var(--green);"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home">Recurly Navigate home</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge">Challenge overview</a>
        <a href="mailto:support@recurly.com">Contact support</a>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>
