---
title: 'Benchmarks 101: Best practices'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8" />
<style>
  .rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
  *{box-sizing:border-box}body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
  .rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px}
  .rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
  .rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
  .rc-hero p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 32px;color:var(--lightgray)}
  .rc-hero-stats{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}.rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:10px;padding:10px 18px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack);box-shadow:0 2px 10px rgba(255,215,6,.25)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-nav a.is-active .rc-snum{background:var(--offblack);color:var(--yellow)}
  .rc-sec{margin-bottom:56px}.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}.rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray);text-align:center}
  .rc-wi-icon{font-size:30px;margin-bottom:10px}.rc-wi h4{font-size:.88rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-wi p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
  .rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
  .rc-sbadge{width:38px;height:38px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start;margin-bottom:24px}
  .rc-wicon{font-size:20px;flex-shrink:0}.rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:28px}
  .rc-cl-header{padding:16px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:center;gap:10px;background:var(--offblack)}
  .rc-cl-header h3{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
  .rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:flex-start;gap:14px}.rc-cli:last-child{border-bottom:none}
  .rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;background:#fff}
  .rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}.rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
  /* PLAYBOOK SECTION */
  .rc-playbook-section{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:20px}
  .rc-pb-header{background:var(--offblack);padding:14px 22px;display:flex;align-items:center;gap:12px}
  .rc-pb-icon{font-size:20px;flex-shrink:0}
  .rc-pb-title{font-size:.9rem;font-weight:800;color:var(--offwhite);flex:1}
  .rc-pb-badge{background:var(--yellow);color:var(--offblack);font-size:.7rem;font-weight:800;padding:3px 10px;border-radius:20px;letter-spacing:.04em;text-transform:uppercase;white-space:nowrap}
  .rc-pb-body{padding:4px 0}
  .rc-pb-item{display:flex;align-items:flex-start;gap:12px;padding:12px 22px;border-bottom:1px solid var(--brightgray);font-size:.87rem;color:var(--darkgray);line-height:1.5}
  .rc-pb-item:last-child{border-bottom:none}
  .rc-pb-check{color:var(--yellow);font-weight:900;font-size:14px;flex-shrink:0;margin-top:1px}
  /* COMPLETE CARD */
  .rc-complete{background:var(--offblack);border-radius:16px;padding:40px;text-align:center;margin-bottom:28px;color:#fff;border:1px solid var(--yellow)}
  .rc-complete h2{font-size:1.8rem;font-weight:800;margin:12px 0 10px;color:var(--yellow)}.rc-complete p{color:var(--lightgray);font-size:.95rem;margin:0 0 24px;line-height:1.6;max-width:560px;margin-left:auto;margin-right:auto}
  .rc-complete-btns{display:flex;gap:12px;justify-content:center;flex-wrap:wrap}
  .rc-btn-complete-primary{background:var(--yellow);color:var(--offblack);text-decoration:none;font-size:.88rem;font-weight:800;padding:12px 24px;border-radius:10px}
  .rc-btn-complete-sec{background:var(--darkgray);color:var(--offwhite);text-decoration:none;font-size:.88rem;font-weight:600;padding:12px 24px;border-radius:10px}
  .rc-office-hours{background:linear-gradient(135deg,var(--offblack) 0%,#1a1a1a 100%);color:#fff;border-radius:16px;padding:32px;margin:32px 0;display:flex;gap:24px;align-items:center;border:1px solid var(--yellow)}
  .rc-oh-content h4{color:var(--yellow);margin:0 0 8px;font-size:1.1rem;font-weight:800;text-transform:uppercase;letter-spacing:1px}
  .rc-oh-content p{color:var(--lightgray);font-size:.95rem;line-height:1.6;margin:0 0 20px}
  .rc-resources-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:24px}
  .rc-res-card{background:var(--brightgray);border-radius:12px;padding:16px 18px;display:flex;align-items:flex-start;gap:10px;text-decoration:none;border:1px solid var(--lightgray)}
  .rc-res-card:hover{border-color:var(--yellow);background:#fffbe6}
  .rc-res-icon{font-size:20px;flex-shrink:0}
  .rc-res-title{font-size:.88rem;font-weight:700;color:var(--darkgray);margin-bottom:3px}
  .rc-res-sub{font-size:.78rem;color:var(--gray);line-height:1.4}
  .rc-tag{display:inline-block;margin-top:10px;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;background:var(--offblack);color:var(--yellow)}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev,.rc-btn-disabled{border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-3col,.rc-2col,.rc-resources-grid{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}.rc-office-hours{flex-direction:column}.rc-complete-btns{flex-direction:column;align-items:center}}
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">📊 Reporting</div>
    <h1>Benchmarks</h1>
    <p>See how you stack up against thousands of subscription businesses — and know exactly where to focus to improve.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">2,200+</div><div class="rc-lbl">Merchants in the benchmark</div></div>
      <div><div class="rc-num">76M</div><div class="rc-lbl">Unique subscribers analyzed</div></div>
      <div><div class="rc-num">10</div><div class="rc-lbl">KPIs benchmarked</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101">Benchmarks</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-subscriber"><span class="rc-snum">1</span>Subscriber</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-churn"><span class="rc-snum">2</span>Churn</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-renewal"><span class="rc-snum">3</span>Renewal</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-dunning"><span class="rc-snum">4</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-best-practices"><span class="rc-snum">5</span>Best Practices</a>
  </nav>


  <div class="rc-sec">

    <div class="rc-sec-header">
      <div class="rc-sec-icon">🏆</div>
      <div>
        <h2>Best Practices &amp; Your Optimization Playbook</h2>
        <p>You've learned what every benchmark measures. Now here's how to act on it — organized by where you're underperforming, with the highest-impact actions to take first.</p>
      </div>
    </div>

    <!-- INTRO -->
    <div class="rc-card">
      <h3 class="rc-subhead">🧩 Benchmarks are a starting point, not an end state</h3>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">A benchmark score tells you where you stand. Your job is to use that context to decide where to invest. Not every business below benchmark on churn has a product problem — some have a payment recovery gap. Not every business below benchmark on acquisition has a pricing problem — some have checkout friction.</p>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0;">The playbook below maps the right actions to the right metrics — so you always know which lever to pull first.</p>
    </div>

    <!-- LIFECYCLE MAP -->
    <h3 class="rc-subhead">🗺️ Where each benchmark sits in your subscriber lifecycle</h3>
    <div class="rc-3col" style="margin-bottom:32px;">
      <div class="rc-wi" style="border-top:4px solid var(--orange);">
        <div class="rc-wi-icon">🚀</div>
        <h4>Acquire</h4>
        <p>Acquisition Rate<br>Sign-Up Decline Rate</p>
        <span class="rc-tag">Section 1</span>
      </div>
      <div class="rc-wi" style="border-top:4px solid #c0392b;">
        <div class="rc-wi-icon">💛</div>
        <h4>Retain</h4>
        <p>Voluntary Churn<br>Combined Churn</p>
        <span class="rc-tag">Section 2</span>
      </div>
      <div class="rc-wi" style="border-top:4px solid var(--offblack);">
        <div class="rc-wi-icon">🔄</div>
        <h4>Renew &amp; Recover</h4>
        <p>Invoice Paid Rate<br>Dunning Recovery Rate</p>
        <span class="rc-tag">Sections 3 &amp; 4</span>
      </div>
    </div>

    <!-- PLAYBOOK SECTIONS -->
    <h3 class="rc-subhead">🎯 Playbooks — actions organized by where you're underperforming</h3>

    <!-- ACQUISITION -->
    <div class="rc-playbook-section">
      <div class="rc-pb-header">
        <div class="rc-pb-icon">🚀</div>
        <div class="rc-pb-title">If Acquisition Rate is below benchmark</div>
        <div class="rc-pb-badge">Acquire</div>
      </div>
      <div class="rc-pb-body">
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Audit your checkout flow for friction — form length, required fields, and payment method options all affect conversion</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>A/B test your payment method ordering — wallet-based options (Apple Pay, Google Pay) often convert higher than card-only flows in the U.S.</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Consider micro-subscription entry points (day/week passes) — they convert 13% of non-trial buyers into recurring subscribers</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Localize your checkout for key markets — payment method preferences differ significantly between U.S. and EMEA audiences</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Build Q1 acquisition campaigns — consumer intent peaks in January–March as New Year resolutions and post-holiday budgets reset</div></div>
      </div>
    </div>

    <!-- SIGN-UP DECLINES -->
    <div class="rc-playbook-section">
      <div class="rc-pb-header">
        <div class="rc-pb-icon">🚫</div>
        <div class="rc-pb-title">If Sign-Up Decline Rate is above benchmark</div>
        <div class="rc-pb-badge">Acquire</div>
      </div>
      <div class="rc-pb-body">
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Filter declines by gateway immediately — a spike in one processor often means a configuration issue, not a broader problem</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Monitor for fraud patterns — sudden spikes in "Do Not Honor" or CVV failure codes may indicate card testing on your checkout</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Enable retry logic for soft declines at signup — many first-attempt failures succeed on a second attempt within seconds</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Review your 3DS/authentication settings — overly aggressive authentication adds friction that increases declines, especially on mobile</div></div>
      </div>
    </div>

    <!-- VOLUNTARY CHURN -->
    <div class="rc-playbook-section">
      <div class="rc-pb-header">
        <div class="rc-pb-icon">🖐️</div>
        <div class="rc-pb-title">If Voluntary Churn is above benchmark</div>
        <div class="rc-pb-badge">Retain</div>
      </div>
      <div class="rc-pb-body">
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Add a "pause before cancel" option — 38% of consumers prefer pausing over canceling, and 3 in 4 paused subscribers return within months</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Build cancel-save journeys personalized to the stated reason — "too expensive" should trigger a downgrade offer; "not using it" should trigger engagement nudges or a pause</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Invest in early lifecycle engagement — 52% of cancels happen because subscribers aren't using the product. Improve onboarding in days 1–30</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Create a win-back segment for former subscribers — 1 in 4 new signups in 2025 came from a previously canceled customer</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Offer flexible commitment options — monthly-to-annual incentives, flexible pause durations, and downgrade paths reduce cancel pressure</div></div>
      </div>
    </div>

    <!-- INVOLUNTARY CHURN / RENEWAL -->
    <div class="rc-playbook-section">
      <div class="rc-pb-header">
        <div class="rc-pb-icon">💳</div>
        <div class="rc-pb-title">If Involuntary Churn or Renewal Decline is above benchmark</div>
        <div class="rc-pb-badge">Renew</div>
      </div>
      <div class="rc-pb-body">
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Enable Account Updater immediately — the single highest-impact action for reducing involuntary churn. It silently updates card details before failures occur. Go to <strong>Configuration → Payment Settings</strong></div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Build pre-renewal playbooks for annual subscribers — send payment reminder emails 2–4 weeks before annual renewal dates</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Compare your decline rate by gateway — if one processor shows consistently higher renewal declines, explore routing alternatives</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Analyze your top decline codes — soft declines (insufficient funds) and hard declines (stolen card, invalid) require different responses and dunning strategies</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Prompt subscribers to add a backup payment method at signup — a quiet insurance policy for renewal failures</div></div>
      </div>
    </div>

    <!-- DUNNING RECOVERY -->
    <div class="rc-playbook-section">
      <div class="rc-pb-header">
        <div class="rc-pb-icon">💰</div>
        <div class="rc-pb-title">If Dunning Recovery Rate is below benchmark</div>
        <div class="rc-pb-badge">Recover</div>
      </div>
      <div class="rc-pb-body">
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Enable Intelligent Retries — AI-powered retry scheduling outperforms fixed cadences by targeting the optimal retry moment for each subscriber</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Review your dunning window length — longer windows give more recovery opportunity for soft declines that resolve over days</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Design separate dunning cadences for monthly vs. annual subscribers — annual invoice recovery needs different timing and urgency</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Audit your dunning email sequence — are messages reaching subscribers? Test subject lines, timing, and calls-to-action for updating payment details</div></div>
        <div class="rc-pb-item"><div class="rc-pb-check">✓</div><div>Track which recovery mechanisms contribute most to your rate — double down on what's working, investigate what isn't</div></div>
      </div>
    </div>

    <!-- SEASONAL STRATEGY -->
    <div class="rc-card">
      <h3 class="rc-subhead">📅 Seasonal strategy — timing your benchmark actions to the calendar</h3>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step">
          <div class="rc-sbadge">Q1</div>
          <div>
            <h3>Jan–Mar: Peak acquisition window</h3>
            <p>New Year intent drives sign-ups. Unpause rates peak in March. Run acquisition campaigns and first-year retention plays to lock in early-year subscribers.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-sbadge">Q2</div>
          <div>
            <h3>Apr–Jun: Optimization season</h3>
            <p>Stable period for dunning improvements, cohort retention analysis, and gateway configuration reviews. Use this window to act on what your benchmarks are telling you.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-sbadge">Q3</div>
          <div>
            <h3>Jul–Sep: LTV and plan mix review</h3>
            <p>Analyze annual vs. monthly plan performance, subscriber cohort LTV, and renewal decline patterns before Q4 pressure hits.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-sbadge">Q4</div>
          <div>
            <h3>Oct–Dec: Holiday pressure + win-backs</h3>
            <p>Renewal declines may rise as financial priorities shift. Run save campaigns, pre-renewal nudges, and win-back campaigns targeting former subscribers.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- FOUNDATIONAL SETUP -->
    <h3 class="rc-subhead">⚙️ Foundational setup — before you benchmark</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>⚙️</span><h3>Setup checklist — confirm before comparing</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Set your industry in Analytics Settings<span>Go to Analytics → Settings → Industry. An incorrect classification skews every comparison. Changes take up to 24 hours.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Review analytics on a consistent monthly schedule<span>Monthly reviews tied to billing cycles give the most actionable signal. Also review after major changes — new gateway, new plan, new market.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Confirm Account Updater is enabled<span>If not already on, enable under Configuration → Payment Settings. It's the highest-ROI recovery tool available.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Confirm Intelligent Retries is active<span>Check your dunning settings to ensure AI-powered retry logic is enabled alongside your dunning cadence.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Connect subscription data to your CRM and support tools<span>Benchmarks are most powerful when churn and recovery signals can be linked to subscriber behavior and support history.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Bring in your CSM<span>Your Recurly Customer Success Manager can help you interpret benchmark results and prioritize the highest-impact actions for your specific business model.</span></div></div>
    </div>

    <!-- OFFICE HOURS CTA -->
    <div class="rc-office-hours">
      <div class="rc-oh-content">
        <h4>🗓️ Talk strategy with your CSM</h4>
        <p>Join our <strong>Customer Success Global Office Hours</strong>! Meet face-to-face with our CSMs to walk through your benchmark results, prioritize your playbook, and get strategic advice tailored to your specific business model and growth stage.</p>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" style="background-color:#FFD706;color:#0D0D0B;text-decoration:none;padding:12px 24px;border-radius:10px;font-weight:700;font-size:.9rem;display:inline-flex;align-items:center;gap:10px;">Register for Office Hours →</a>
      </div>
    </div>

    <!-- COMPLETION CARD -->
    <div class="rc-complete">
      <div style="font-size:48px;">🎉</div>
      <h2>You've completed the Benchmarks learning path!</h2>
      <p>You now know what every Recurly benchmark measures, why it matters, and exactly what to do when you find a gap. The next step is opening your dashboards and putting it into practice.</p>
      <div class="rc-complete-btns">
        <a class="rc-btn-complete-primary" href="https://app.recurly.com">Open Recurly Analytics →</a>
        <a class="rc-btn-complete-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/built-in-benchmarks">View All Benchmark Docs</a>
      </div>
    </div>

    <!-- ALL RESOURCES GRID -->
    <h3 class="rc-subhead">📚 All resources from this learning path</h3>
    <div class="rc-resources-grid">
      <a class="rc-res-card" href="https://docs.recurly.com/recurly-subscriptions/docs/built-in-benchmarks" target="_blank" rel="noopener noreferrer">
        <div class="rc-res-icon">📄</div>
        <div><div class="rc-res-title">Built-In Benchmarks Docs</div><div class="rc-res-sub">Complete documentation for all benchmark dashboards</div></div>
      </a>
      <a class="rc-res-card" href="https://docs.recurly.com/recurly-subscriptions/docs/subscriber-benchmarks" target="_blank" rel="noopener noreferrer">
        <div class="rc-res-icon">👥</div>
        <div><div class="rc-res-title">Subscriber Benchmarks Docs</div><div class="rc-res-sub">Acquisition rate and sign-up decline documentation</div></div>
      </a>
      <a class="rc-res-card" href="https://docs.recurly.com/recurly-subscriptions/docs/subscriber-churn-benchmarks" target="_blank" rel="noopener noreferrer">
        <div class="rc-res-icon">📉</div>
        <div><div class="rc-res-title">Churn Benchmarks Docs</div><div class="rc-res-sub">Voluntary, involuntary, and combined churn documentation</div></div>
      </a>
      <a class="rc-res-card" href="https://docs.recurly.com/recurly-subscriptions/docs/renewal-benchmarks" target="_blank" rel="noopener noreferrer">
        <div class="rc-res-icon">🔄</div>
        <div><div class="rc-res-title">Renewal Benchmarks Docs</div><div class="rc-res-sub">Invoice paid rate and renewal decline documentation</div></div>
      </a>
      <a class="rc-res-card" href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-benchmarks" target="_blank" rel="noopener noreferrer">
        <div class="rc-res-icon">💰</div>
        <div><div class="rc-res-title">Dunning Benchmarks Docs</div><div class="rc-res-sub">Recovery rate dashboard documentation</div></div>
      </a>
      <a class="rc-res-card" href="https://docs.recurly.com/recurly-subscriptions/docs/analytics-settings" target="_blank" rel="noopener noreferrer">
        <div class="rc-res-icon">⚙️</div>
        <div><div class="rc-res-title">Analytics Settings</div><div class="rc-res-sub">Set your industry for accurate benchmarking</div></div>
      </a>
      <a class="rc-res-card" href="https://recurly.com/research/" target="_blank" rel="noopener noreferrer">
        <div class="rc-res-icon">📊</div>
        <div><div class="rc-res-title">Recurly Research Hub</div><div class="rc-res-sub">2026 State of Subscriptions Report and industry data</div></div>
      </a>
      <a class="rc-res-card" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" target="_blank" rel="noopener noreferrer">
        <div class="rc-res-icon">💳</div>
        <div><div class="rc-res-title">Navigate: Account Updater</div><div class="rc-res-sub">Full learning path for reducing involuntary churn</div></div>
      </a>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-benchmarks-dunning">← Section 4: Dunning Benchmarks</a>
      <span class="rc-btn-disabled">🎉 Path Complete!</span>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/built-in-benchmarks" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Built-In Benchmarks</a>
    <a class="rc-link-btn rc-link-sec" href="https://recurly.com/research/" target="_blank" rel="noopener noreferrer">📊 Recurly Research Hub</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-benchmarks-overview">🧭 Return to Start</a>

  </div>
</div>
</body>
</html>
`}</HTMLBlock>

<br />
