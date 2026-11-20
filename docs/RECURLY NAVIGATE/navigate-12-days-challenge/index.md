---
title: 'Sleigh your success: Navigate 12-day challenge'
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
}
.rc-hero::before { top: 0; } .rc-hero::after { bottom: 0; }
.rc-logo { height: 28px; display: block; margin: 0 auto 4px; }
.rc-day-pill {
  display: inline-flex; align-items: center; gap: 8px; background: var(--poppy); color: #fff;
  font-size: .78rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 18px; border-radius: 20px; margin: 22px 0 14px;
}
.rc-hero h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: #FCFBF7 !important; margin: 0 0 14px; }
.rc-hero p { font-size: 1.02rem; color: #D1CFC4 !important; max-width: 720px; margin: 0 auto; line-height: 1.6; }
.rc-hero-meta { margin-top: 22px; font-size: .9rem; font-weight: 700; color: var(--yellow) !important; letter-spacing: .4px; }

/* SECTIONS */
.rc-section { margin: 40px 0; }
.rc-section h2 {
  font-size: 1.45rem; font-weight: 800; color: var(--offblack) !important; margin: 0 0 16px;
  display: flex; align-items: center; gap: 12px;
}
.rc-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-section > p { font-size: .95rem; line-height: 1.65; margin: 0 0 16px; }
.rc-fa { color: var(--poppy); font-size: 1.1rem; }

/* PRIZES + SCORING */
.rc-grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
.rc-card {
  background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px;
}
.rc-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack) !important; margin: 10px 0 6px; }
.rc-card p { font-size: .88rem; color: var(--gray) !important; line-height: 1.55; margin: 0; }
.rc-card-icon { font-size: 1.5rem; }
.rc-tag {
  display: inline-block; margin-top: 10px; padding: 4px 12px; border-radius: 20px;
  font-size: .7rem; font-weight: 800; letter-spacing: .5px; text-transform: uppercase; color: #fff;
}

/* DAY CALENDAR */
.rc-day-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
a.rc-day-card {
  display: flex; flex-direction: column; gap: 8px; background: var(--offwhite);
  border: 1px solid var(--lightgray); border-radius: 14px; padding: 20px; color: var(--darkgray) !important;
  transition: all .2s ease;
}
a.rc-day-card:hover { border-color: var(--poppy); box-shadow: 0 6px 22px rgba(255,81,38,.18); transform: translateY(-2px); text-decoration: none !important; }
.rc-day-head { display: flex; align-items: center; justify-content: space-between; gap: 8px; }
.rc-day-badge {
  display: inline-flex; align-items: center; gap: 6px; color: #fff; padding: 4px 11px;
  border-radius: 16px; font-size: .72rem; font-weight: 800; letter-spacing: .5px; text-transform: uppercase;
}
.rc-day-pts { font-size: .76rem; font-weight: 800; color: var(--poppy) !important; white-space: nowrap; }
.rc-day-date { font-size: .72rem; font-weight: 700; color: var(--gray) !important; text-transform: uppercase; letter-spacing: .6px; }
a.rc-day-card h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack) !important; margin: 0; line-height: 1.35; }
.rc-day-theme { font-size: .84rem; color: var(--gray) !important; line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-day-cta { font-size: .84rem; font-weight: 700; color: var(--blue) !important; margin-top: 4px; }

/* HOW IT WORKS */
.rc-steps { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
.rc-step { background: var(--brightgray); border-radius: 12px; padding: 20px; }
.rc-step-num {
  display: inline-flex; align-items: center; justify-content: center; width: 32px; height: 32px;
  border-radius: 50%; background: var(--green); color: #fff; font-weight: 800; margin-bottom: 10px;
}
.rc-step h4 { font-size: 1rem; font-weight: 800; color: var(--offblack) !important; margin: 0 0 6px; }
.rc-step p { font-size: .88rem; color: var(--gray) !important; line-height: 1.5; margin: 0; }

/* RESOURCES */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--green); border-radius: 10px; padding: 20px 24px; margin-top: 32px; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray) !important; margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 6px 20px; }
.rc-resource-links a { color: var(--gray) !important; text-decoration: underline !important; font-size: .88rem; font-weight: 500; }

@media (max-width: 900px) {
  .rc-grid-3, .rc-day-grid, .rc-steps { grid-template-columns: 1fr 1fr; }
}
@media (max-width: 768px) {
  .rc-content-wrap, .rc-top-nav { padding-left: 20px; padding-right: 20px; }
  .rc-hero { padding: 44px 20px 40px; }
  .rc-hero h1 { font-size: 1.8rem; }
  .rc-grid-3, .rc-day-grid, .rc-steps { grid-template-columns: 1fr; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-back-link">← Back to Navigate home</a>
  </div>

  <div class="rc-content-wrap">

    <!-- HERO -->
    <div class="rc-hero">
      <img class="rc-logo" src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly">
      <span class="rc-day-pill"><i class="fa-solid fa-snowflake"></i> 12 weekdays · Dec 3–18, 2026</span>
      <h1>Sleigh your success: Navigate 12-day challenge</h1>
      <p>Complete one short task each weekday, earn points, and compete for the top prize. Each task opens at midnight on its date and stays open through December 18.</p>
      <div class="rc-hero-meta">Start with Day 1 on Thursday, December 3</div>
    </div>

    <!-- HOW IT WORKS -->
    <div class="rc-section">
      <h2><i class="fa-solid fa-list-check rc-fa"></i> How it works</h2>
      <div class="rc-steps">
        <div class="rc-step">
          <span class="rc-step-num">1</span>
          <h4>Open today's task</h4>
          <p>A new task opens at midnight Central on each weekday from Dec 3 to Dec 18.</p>
        </div>
        <div class="rc-step">
          <span class="rc-step-num">2</span>
          <h4>Complete the task</h4>
          <p>Each task has a short activity, and some ask you to submit a form or screenshot.</p>
        </div>
        <div class="rc-step">
          <span class="rc-step-num">3</span>
          <h4>Earn your points</h4>
          <p>Points are added to your challenge total. Some tasks include bonus points.</p>
        </div>
      </div>
    </div>

    <!-- PRIZES -->
    <div class="rc-section">
      <h2><i class="fa-solid fa-trophy rc-fa"></i> Prizes</h2>
      <div class="rc-grid-3">
        <div class="rc-card">
          <i class="fa-solid fa-award card-icon rc-card-icon" style="color: var(--poppy);"></i>
          <h4>1st place</h4>
          <p>Your choice of an extended Engage trial with 10 hours of professional services, or a $250 gift card.</p>
          <span class="rc-tag" style="background: var(--poppy);">Grand prize</span>
        </div>
        <div class="rc-card">
          <i class="fa-solid fa-basket-shopping rc-card-icon" style="color: var(--green);"></i>
          <h4>2nd and 3rd place</h4>
          <p>A Navigate gift basket for each of the two runners-up.</p>
          <span class="rc-tag" style="background: var(--green);">Runners-up</span>
        </div>
        <div class="rc-card">
          <i class="fa-solid fa-star rc-card-icon" style="color: var(--yellow);"></i>
          <h4>Scoring</h4>
          <p>Each day lists its points on its card below. Bonus points are added to your total after the activity is verified.</p>
          <span class="rc-tag" style="background: var(--offblack);">255+ base points</span>
        </div>
      </div>
    </div>

    <!-- DAY CALENDAR -->
    <div class="rc-section">
      <h2><i class="fa-solid fa-calendar-days rc-fa"></i> The 12 days</h2>
      <p>Select a day to open its task page. Tasks open at midnight Central on the date shown.</p>

      <div class="rc-day-grid">

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-1" class="rc-day-card">
          <div class="rc-day-head"><span class="rc-day-badge" style="background: var(--poppy);">Day 1</span><span class="rc-day-pts">15 pts</span></div>
          <div class="rc-day-date">Thu, Dec 3</div>
          <h4>Defending your workshop</h4>
          <p class="rc-day-theme">Register for the Chargeback webinar on Dec 10.</p>
          <span class="rc-day-cta">Open task →</span>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-2" class="rc-day-card">
          <div class="rc-day-head"><span class="rc-day-badge" style="background: var(--green);">Day 2</span><span class="rc-day-pts">25 pts</span></div>
          <div class="rc-day-date">Fri, Dec 4</div>
          <h4>The gift of feedback</h4>
          <p class="rc-day-theme">Submit a G2 review and earn a $25 Amazon gift card.</p>
          <span class="rc-day-cta">Open task →</span>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-3" class="rc-day-card">
          <div class="rc-day-head"><span class="rc-day-badge" style="background: var(--gold, #FFD706); color: var(--offblack);">Day 3</span><span class="rc-day-pts">10 pts each</span></div>
          <div class="rc-day-date">Mon, Dec 7</div>
          <h4>Defrost failed payments</h4>
          <p class="rc-day-theme">Test your dunning knowledge with a short quiz.</p>
          <span class="rc-day-cta">Open task →</span>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-4" class="rc-day-card">
          <div class="rc-day-head"><span class="rc-day-badge" style="background: var(--blue);">Day 4</span><span class="rc-day-pts">20 pts</span></div>
          <div class="rc-day-date">Tue, Dec 8</div>
          <h4>Check your industry twice</h4>
          <p class="rc-day-theme">Verify your industry setting and submit a screenshot.</p>
          <span class="rc-day-cta">Open task →</span>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-5" class="rc-day-card">
          <div class="rc-day-head"><span class="rc-day-badge" style="background: var(--poppy);">Day 5</span><span class="rc-day-pts">30 pts</span></div>
          <div class="rc-day-date">Wed, Dec 9</div>
          <h4>Warm up your emails</h4>
          <p class="rc-day-theme">Audit one customer email template and submit an update.</p>
          <span class="rc-day-cta">Open task →</span>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-6" class="rc-day-card">
          <div class="rc-day-head"><span class="rc-day-badge" style="background: var(--green);">Day 6</span><span class="rc-day-pts">15 pts</span></div>
          <div class="rc-day-date">Thu, Dec 10</div>
          <h4>The "snowed in" subscriber</h4>
          <p class="rc-day-theme">Pick the right feature to keep a subscriber from churning.</p>
          <span class="rc-day-cta">Open task →</span>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-7" class="rc-day-card">
          <div class="rc-day-head"><span class="rc-day-badge" style="background: var(--blue);">Day 7</span><span class="rc-day-pts">20 pts</span></div>
          <div class="rc-day-date">Fri, Dec 11</div>
          <h4>Spread the joy</h4>
          <p class="rc-day-theme">Share what you value about working with your CSM. Optional video for bonus points.</p>
          <span class="rc-day-cta">Open task →</span>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-8" class="rc-day-card">
          <div class="rc-day-head"><span class="rc-day-badge" style="background: var(--poppy);">Day 8</span><span class="rc-day-pts">15 pts</span></div>
          <div class="rc-day-date">Mon, Dec 14</div>
          <h4>Behind-the-scenes magic</h4>
          <p class="rc-day-theme">Find the feature that updates expired cards automatically.</p>
          <span class="rc-day-cta">Open task →</span>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-9" class="rc-day-card">
          <div class="rc-day-head"><span class="rc-day-badge" style="background: var(--green);">Day 9</span><span class="rc-day-pts">25 pts</span></div>
          <div class="rc-day-date">Tue, Dec 15</div>
          <h4>A season of savings</h4>
          <p class="rc-day-theme">Check your coupon redemption rules. Optional creative promo code for bonus points.</p>
          <span class="rc-day-cta">Open task →</span>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-10" class="rc-day-card">
          <div class="rc-day-head"><span class="rc-day-badge" style="background: var(--blue);">Day 10</span><span class="rc-day-pts">25 pts</span></div>
          <div class="rc-day-date">Wed, Dec 16</div>
          <h4>The data snow globe</h4>
          <p class="rc-day-theme">Pick one benchmark metric to improve in the new year.</p>
          <span class="rc-day-cta">Open task →</span>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-11" class="rc-day-card">
          <div class="rc-day-head"><span class="rc-day-badge" style="background: var(--poppy);">Day 11</span><span class="rc-day-pts">25 pts</span></div>
          <div class="rc-day-date">Thu, Dec 17</div>
          <h4>Global winter festivities</h4>
          <p class="rc-day-theme">Choose the right alternative payment method for international customers.</p>
          <span class="rc-day-cta">Open task →</span>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-12" class="rc-day-card">
          <div class="rc-day-head"><span class="rc-day-badge" style="background: var(--green);">Day 12</span><span class="rc-day-pts">25 pts</span></div>
          <div class="rc-day-date">Fri, Dec 18</div>
          <h4>The star on top</h4>
          <p class="rc-day-theme">Nominate a team or customer for the Recurly Customer Awards.</p>
          <span class="rc-day-cta">Open task →</span>
        </a>

      </div>
    </div>

    <!-- RESOURCES -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open" style="color: var(--green);"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home">Recurly Navigate home</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-12-days-challenge-day-1">Start Day 1</a>
        <a href="mailto:support@recurly.com">Contact support</a>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>
