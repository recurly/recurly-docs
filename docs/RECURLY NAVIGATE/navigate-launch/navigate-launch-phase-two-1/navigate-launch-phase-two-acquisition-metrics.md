---
title: 'Section 2: Acquisition & Growth'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
.rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif;max-width:960px;margin:0 auto;padding:0 20px 60px}
.rc-hero{background:var(--offblack);border-radius:16px;padding:52px 40px 44px;text-align:center;margin-bottom:0}
.rc-badge{display:inline-block;background:var(--orange);color:#fff;border-radius:20px;padding:6px 20px;font-size:12px;font-weight:800;letter-spacing:1px;text-transform:uppercase;margin-bottom:18px}
.rc-hero h1{font-size:2.3rem;font-weight:800;line-height:1.15;margin:0 0 12px;color:#fff}
.rc-hero>p{font-size:1rem;max-width:680px;margin:0 auto 28px;color:#CCC9B8;line-height:1.6}
.rc-hero-stats{display:flex;justify-content:center;gap:36px;flex-wrap:wrap}
.rc-num{font-size:1.7rem;font-weight:800;color:var(--orange)}
.rc-lbl{font-size:.76rem;color:#CCC9B8;text-transform:uppercase;letter-spacing:.5px}
.rc-nav{display:flex;flex-wrap:wrap;gap:8px;margin:22px 0 32px;padding:16px;background:var(--offwhite);border-radius:14px;border:1px solid var(--lightgray)}
.rc-nav a{display:inline-flex;align-items:center;gap:7px;padding:9px 13px;border-radius:10px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.83rem;font-weight:700;transition:all .2s}
.rc-nav a:hover{border-color:var(--orange);box-shadow:0 2px 8px rgba(255,130,0,.2);color:var(--offblack);text-decoration:none}
.rc-nav a.rc-active{background:var(--orange);border-color:var(--orange);color:#fff}
.rc-snum{display:inline-flex;align-items:center;justify-content:center;width:22px;height:22px;border-radius:50%;background:var(--offblack);color:var(--orange);font-size:11px;font-weight:800;flex-shrink:0}
.rc-nav a.rc-active .rc-snum{background:rgba(255,255,255,.2);color:#fff}
.rc-sec{margin-bottom:48px}
.rc-sec-header{display:flex;align-items:flex-start;gap:18px;margin-bottom:28px}
.rc-sec-icon{width:52px;height:52px;border-radius:14px;background:var(--orange);display:flex;align-items:center;justify-content:center;font-size:24px;flex-shrink:0}
.rc-sec-header h2{font-size:1.45rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
.rc-sec-header p{font-size:.9rem;color:var(--gray);margin:0;line-height:1.6}
.rc-card{background:#fff;border:1px solid var(--lightgray);border-radius:14px;padding:20px 22px;margin-bottom:16px;box-shadow:0 2px 6px rgba(13,13,11,.04)}
.rc-subhead{font-size:.98rem;font-weight:800;color:var(--offblack);margin:0 0 10px}
.rc-metric{background:#fff;border:1px solid var(--lightgray);border-radius:14px;padding:20px 22px;margin-bottom:14px}
.rc-metric-head{display:flex;align-items:center;gap:12px;margin-bottom:10px}
.rc-metric-icon{width:40px;height:40px;border-radius:10px;background:var(--offblack);color:var(--orange);font-size:18px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-metric h3{font-size:.96rem;font-weight:800;margin:0;color:var(--offblack)}
.rc-metric p{font-size:.85rem;color:var(--gray);margin:0 0 10px;line-height:1.6}
.rc-formula{background:var(--brightgray);border-radius:8px;padding:10px 14px;font-size:.83rem;font-family:monospace;color:var(--darkgray);margin-bottom:10px}
.rc-pills{display:flex;gap:8px;flex-wrap:wrap}
.rc-pill{padding:4px 12px;border-radius:20px;font-size:.75rem;font-weight:700;background:var(--offwhite);border:1px solid var(--lightgray);color:var(--darkgray)}
.rc-pill.up{background:rgba(22,163,74,.1);color:#15803d;border-color:#86efac}
.rc-pill.down{background:rgba(220,38,38,.1);color:#dc2626;border-color:#fca5a5}
.rc-tip{background:#fff6ee;border:1px solid #ffcb99;border-radius:12px;padding:15px 17px;margin-bottom:16px;font-size:.87rem;color:var(--darkgray);line-height:1.6}
.rc-tip strong{color:var(--offblack)}
.rc-warning{background:#fff5f0;border:1px solid #ffb894;border-radius:12px;padding:15px 17px;margin-bottom:16px;font-size:.87rem;color:var(--darkgray);line-height:1.6}
.rc-warning strong{color:#cc4400}
.rc-video-wrap{position:relative;width:100%;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:10px;margin-bottom:8px;background:var(--offblack)}
.rc-video-wrap iframe{position:absolute;top:0;left:0;width:100%;height:100%;border:0}
.rc-video-cap{font-size:.8rem;color:var(--gray);text-align:center;margin-bottom:4px;font-style:italic}
.rc-clip{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:14px;padding:16px 18px;margin-bottom:16px}
.rc-clip-label{display:inline-flex;align-items:center;gap:5px;background:var(--offblack);color:var(--orange);border-radius:6px;padding:3px 10px;font-size:.73rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;margin-bottom:10px}
.rc-clip p{font-size:.87rem;color:var(--gray);margin:0 0 10px;line-height:1.5}
.rc-clip-title{font-size:.93rem;font-weight:700;color:var(--offblack);margin:0 0 6px}
.rc-webinar-link{display:inline-flex;align-items:center;gap:6px;font-size:.83rem;font-weight:700;color:var(--orange);text-decoration:none}
.rc-webinar-link:hover{text-decoration:underline}
.rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:16px}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.87rem;text-decoration:none;border:1px solid var(--lightgray)}
.rc-btn-prev{background:#fff;color:var(--darkgray)}
.rc-btn-prev:hover{background:var(--brightgray);text-decoration:none}
.rc-btn-next{background:var(--orange);color:#fff;border-color:var(--orange)}
.rc-btn-next:hover{opacity:.92;text-decoration:none}
.rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default;pointer-events:none}
.rc-link-btn{background:var(--orange);color:#fff;border-color:var(--orange);margin:0 8px 8px 0}
.rc-link-btn:hover{opacity:.9;text-decoration:none}
.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
.rc-link-sec:hover{background:var(--brightgray);text-decoration:none}
.rc-resources{margin-top:32px}
.rc-resources h3{font-size:.84rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--gray);margin:0 0 12px}
@media(max-width:640px){.rc-hero{padding:30px 16px 26px}.rc-hero h1{font-size:1.65rem}.rc-2col{grid-template-columns:1fr}.rc-hero-stats{gap:14px}.rc-sec-header{flex-direction:column}.rc-sec-nav{flex-direction:column;align-items:stretch}}
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">📊 Navigate · Launchpad Phase 2</div>
    <h1>Subscriber Acquisition &amp; Sign-Up Decline Rate</h1>
    <p>These two metrics tell you how effectively you're growing — and how much friction is getting in the way of subscribers who want to sign up but can't.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Step 2</div><div class="rc-lbl">Phase 2</div></div>
      <div><div class="rc-num">↑</div><div class="rc-lbl">Acquisition Rate Goal</div></div>
      <div><div class="rc-num">↓</div><div class="rc-lbl">Decline Rate Goal</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two"><span class="rc-snum">🏠</span>Phase 2 Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-benchmarks-dashboard"><span class="rc-snum">1</span>Benchmarks &amp; Reporting</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-acquisition-metrics" class="rc-active"><span class="rc-snum">2</span>Acquisition &amp; Decline</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-churn-metrics"><span class="rc-snum">3</span>Churn Metrics</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-retention-metrics"><span class="rc-snum">4</span>Revenue &amp; Recovery</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-review"><span class="rc-snum">✓</span>Full Course Review</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">📈</div>
      <div>
        <h2>Growth Starts at the Top of the Funnel</h2>
        <p>Acquisition Rate and Sign-Up Decline Rate are your two growth-layer metrics. Together they tell you how fast your subscriber base is expanding — and how many potential subscribers are being lost before they ever complete their first payment.</p>
      </div>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">▶ Trail Guide: Subscriber Acquisition &amp; Sign-Up Decline Rate</p>
      <div class="rc-video-wrap">
        <iframe src="https://drive.google.com/file/d/[ACQUISITION-VIDEO-ID]/preview" allow="autoplay" allowfullscreen></iframe>
      </div>
      <p class="rc-video-cap">A deep dive into Acquisition Rate and Sign-Up Decline Rate — where to find them in the Benchmarks Dashboard, how they're calculated, and how to act on what you see.</p>
    </div>

    <div class="rc-metric">
      <div class="rc-metric-head">
        <div class="rc-metric-icon">📈</div>
        <h3>Acquisition Rate</h3>
      </div>
      <p>Measures how effectively you're bringing in new paid subscribers each month. A rising acquisition rate means your growth strategy is working. A flat or declining rate signals a need to investigate marketing, pricing, or checkout conversion.</p>
      <div class="rc-formula">New paid subscribers ÷ Total paid subscribers = Acquisition Rate %</div>
      <div class="rc-pills">
        <span class="rc-pill up">↑ Higher is better</span>
        <span class="rc-pill">Check monthly</span>
        <span class="rc-pill">Analytics → Benchmarks</span>
      </div>
    </div>

    <div class="rc-metric">
      <div class="rc-metric-head">
        <div class="rc-metric-icon">⚡</div>
        <h3>Sign-Up Decline Rate</h3>
      </div>
      <p>The percentage of first transaction attempts during sign-up that are declined. A high sign-up decline rate means real customers are trying to sign up and failing — these aren't rejections, they're missed conversions. Even a 1% improvement can meaningfully impact growth.</p>
      <div class="rc-formula">Failed first-attempt sign-ups ÷ Total sign-up attempts = Sign-Up Decline Rate %</div>
      <div class="rc-pills">
        <span class="rc-pill down">↓ Lower is better</span>
        <span class="rc-pill">Check monthly</span>
        <span class="rc-pill">Analytics → Benchmarks</span>
      </div>
    </div>

    <div class="rc-clip">
      <div class="rc-clip-label">🎬 Webinar Clip</div>
      <p class="rc-clip-title">Sign-Up Decline Rate: What a Spike Tells You About Your Checkout</p>
      <p>Suggested clip: The Sign-Up Decline Benchmarks section from this webinar — covering how to spot fraud via checkout (a 500% spike in fraud responses), how to compare gateway performance for sign-ups, and how to identify card-type-specific issues. Presenter: Daniel Shipley.</p>
      <a class="rc-webinar-link" href="https://recurly.com/events/" target="_blank" rel="noopener noreferrer">▶ Watch "Stack Up Against the Competition" On-Demand →</a>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">🎯 What to Do If Sign-Up Declines Are High</p>
      <div class="rc-2col">
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Check for fraud patterns</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">A sudden spike in sign-up declines — especially with fraud response codes — may indicate card testing activity on your checkout. Review with your CSM and gateway team immediately.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Compare gateway performance</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Different gateways approve different card types at different rates. If your decline rate is high, compare approval rates by gateway to identify whether a routing change might help.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Check payment method coverage</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Are you accepting the payment methods your customers prefer? Offering PayPal, Apple Pay, or local payment methods in key markets can dramatically reduce friction for international subscribers.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Review 3DS / checkout UX</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">If the 3DS authentication flow is confusing or non-obvious, subscribers may abandon mid-authentication — registering as a failed attempt. Review your checkout flow from a subscriber's perspective.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 A note on timing:</strong> Sign-up decline numbers for the current month are always lower than prior months because the month isn't over yet — more sign-up attempts will happen as the month continues. Always compare full prior months for accurate trend analysis.
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-benchmarks-dashboard">← Benchmarks &amp; Reporting</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two-churn-metrics">Step 3: Churn Metrics →</a>
    </div>

    <div class="rc-resources">
      <h3>Additional Resources</h3>
      <a class="rc-link-btn" href="https://docs.recurly.com/docs/subscriber-benchmarks" target="_blank" rel="noopener noreferrer">📖 Subscriber Benchmarks Docs</a>
      <a class="rc-link-btn rc-link-sec" href="https://recurly.com/events/" target="_blank" rel="noopener noreferrer">🎧 Webinars On-Demand</a>
      <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">✉ Contact Customer Success</a>
    </div>
  </div>

</div>
`}</HTMLBlock>

<br />
