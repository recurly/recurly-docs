---
title: Tracking Impact
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html><html lang="en"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><title>Preview: Account Updater</title><link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet"><style>*, *::before, *::after { box-sizing: border-box; }body { margin: 0; background: #f5f5f0; font-family: Inter, -apple-system, sans-serif; }.pv-bar { position: sticky; top: 0; z-index: 1000; background: #0D0D0B; padding: 10px 16px; display: flex; gap: 6px; overflow-x: auto; align-items: center; }.pv-bar::before { content: "PREVIEW"; color: #FFD706; font-size: 11px; font-weight: 700; letter-spacing: 1px; margin-right: 8px; flex-shrink: 0; }.pv-tab { padding: 7px 14px; border-radius: 6px; color: #CCC9B8; background: transparent; border: 1px solid transparent; cursor: pointer; font-size: 12px; font-family: Inter, sans-serif; white-space: nowrap; transition: all 0.15s; text-decoration: none; }.pv-tab:hover { background: #32312D; color: #FFFDF2; }.pv-tab.active { background: #FFD706; color: #0D0D0B; font-weight: 600; border-color: #FFD706; }.pv-panel { display: block; padding: 32px 16px; }</style></head><body><div class="pv-bar"><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" class="pv-tab">1. What Is It?</a><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits" class="pv-tab">2. Why Use It?</a><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations" class="pv-tab">3. Things to Consider</a><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-fit" class="pv-tab">4. When Not to Use It</a><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable" class="pv-tab">5. How to Enable It</a><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data" class="pv-tab active">6. Tracking Impact</a><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case" class="pv-tab">7. Pitch to Leadership</a></div>

<div class="pv-panel active"><style>
:root { --yellow: #FFD706; --orange: #FF8200; --vermillion: #FF5810; --salmon: #FF9D88; --offblack: #0D0D0B; --darkgray: #32312D; --gray: #807D73; --lightgray: #CCC9B8; --brightgray: #F1EFE3; --offwhite: #FFFDF2; }
.rc-guide { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; color: var(--offblack); max-width: 900px; margin: 0 auto; }
.rc-hero { background: var(--offblack); color: white; padding: 48px 40px; border-radius: 16px 16px 0 0; text-align: center; }
.rc-badge { background: var(--yellow); color: var(--offblack); padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; }
.rc-nav { display: flex; gap: 0; background: var(--brightgray); padding: 0; overflow-x: auto; border-bottom: 2px solid var(--lightgray); }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: var(--gray); font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: var(--offblack); background: var(--offwhite); }
.rc-nav a.is-active { color: var(--offblack); font-weight: 600; border-bottom-color: var(--yellow); background: var(--offwhite); }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: var(--lightgray); color: var(--gray); display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-sec { padding: 40px; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: var(--yellow); border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px; flex-shrink: 0; }
.rc-card { background: var(--offwhite); border-radius: 12px; padding: 28px; margin-bottom: 20px; }
.rc-steps { display: flex; flex-direction: column; gap: 16px; margin: 20px 0; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: var(--offwhite); border-radius: 12px; padding: 20px; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: 14px; flex-shrink: 0; }
.rc-tip { border-left: 4px solid var(--yellow); background: var(--offwhite); padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-warning { border-left: 4px solid var(--orange); background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-checklist { background: var(--offwhite); border-radius: 12px; padding: 24px; margin: 20px 0; }
.rc-cl-header { font-size: 16px; font-weight: 600; margin-bottom: 16px; }
.rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
.rc-cb { width: 20px; height: 20px; border-radius: 4px; border: 2px solid var(--lightgray); flex-shrink: 0; cursor: pointer; margin-top: 2px; }
.rc-cli label { font-size: 14px; color: var(--darkgray); line-height: 1.5; cursor: pointer; }
.rc-3col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
.rc-2col { display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px; margin: 20px 0; }
.rc-wi { background: var(--offwhite); border-radius: 12px; padding: 24px; text-align: center; }
.rc-sec-nav { display: flex; justify-content: space-between; padding: 0 40px 40px; }
.rc-btn-prev, .rc-btn-next { display: inline-flex; align-items: center; gap: 8px; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; transition: all 0.2s; }
.rc-btn-prev { background: var(--brightgray); color: var(--offblack); }
.rc-btn-next { background: var(--yellow); color: var(--offblack); }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <span class="rc-badge">Subscriptions</span>
    <h1>Save Your Revenue: Account Updater</h1>
    <p class="rc-subtitle">Learn how to measure and monitor the impact of Account Updater.</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
  </div>

  <div class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater"><span class="rc-snum">1</span> What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits"><span class="rc-snum">2</span> Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations"><span class="rc-snum">3</span> Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-fit"><span class="rc-snum">4</span> When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable"><span class="rc-snum">5</span> How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data" class="is-active"><span class="rc-snum">6</span> Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case"><span class="rc-snum">7</span> Pitch to Leadership</a>
  </div>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1gyrfwrpUd15NA_lJ-Te4PCpQqYgJv0l4" alt="chart icon" style="width:28px;height:28px;"></div>
      <div><h2>Tracking Impact</h2><p>Quantify value and ROI using Recurly reporting tools.</p></div>
    </div>

    <div class="rc-card">
      <h3>Establish Your Baseline</h3>
      <p>Before enabling, record your current involuntary churn rate and monthly revenue lost to failed payments. This is your benchmark for success.</p>
    </div>

    <div class="rc-subhead">Key Metrics to Monitor</div>
    <div class="rc-3col">
      <div class="rc-wi"><h4>Cards Updated</h4><p>Total number of records successfully refreshed in a given period.</p></div>
      <div class="rc-wi"><h4>Revenue Recovered</h4><p>Dollar value of renewals that succeeded on updated details vs. hard-declined.</p></div>
      <div class="rc-wi"><h4>Decline Rate Change</h4><p>Comparing churn rates before and after activation.</p></div>
    </div>

    <div class="rc-subhead">How to Calculate ROI</div>
    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge">1</div><div class="rc-step-content"><h4>Track Successful Renewals</h4><p>Cross-reference updated cards against successful transactions in the same cycle.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">2</div><div class="rc-step-content"><h4>Calculate Net Impact</h4><p>Net Revenue Saved = (Recovered Revenue) - (Account Updater Fees).</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">3</div><div class="rc-step-content"><h4>Measure Lifetime Value</h4><p>Retained subscribers represent months or years of revenue beyond the single renewal.</p></div></div>
    </div>

    <div class="rc-tip"><strong>💡 Pro Tip: Isolate Contribution</strong><p>Account Updater prevents declines. track this as "pre-dunning recovery" to separate it from reactive dunning recovery.</p></div>
  </div>

  <div class="rc-sec-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable" class="rc-btn-prev">← Previous</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case" class="rc-btn-next">Next →</a>
  </div>
</div></div></body></html>
`}</HTMLBlock>

<br />
