---
title: 'Why Use It? '
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html><html lang="en"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><title>Preview: Account Updater</title><link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet"><style>*, *::before, *::after { box-sizing: border-box; }body { margin: 0; background: #f5f5f0; font-family: Inter, -apple-system, sans-serif; }.pv-bar { position: sticky; top: 0; z-index: 1000; background: #0D0D0B; padding: 10px 16px; display: flex; gap: 6px; overflow-x: auto; align-items: center; }.pv-bar::before { content: "PREVIEW"; color: #FFD706; font-size: 11px; font-weight: 700; letter-spacing: 1px; margin-right: 8px; flex-shrink: 0; }.pv-tab { padding: 7px 14px; border-radius: 6px; color: #CCC9B8; background: transparent; border: 1px solid transparent; cursor: pointer; font-size: 12px; font-family: Inter, sans-serif; white-space: nowrap; transition: all 0.15s; text-decoration: none; }.pv-tab:hover { background: #32312D; color: #FFFDF2; }.pv-tab.active { background: #FFD706; color: #0D0D0B; font-weight: 600; border-color: #FFD706; }.pv-panel { display: block; padding: 32px 16px; }</style></head><body><div class="pv-bar"><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" class="pv-tab">1. What Is It?</a><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits" class="pv-tab active">2. Why Use It?</a><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations" class="pv-tab">3. Things to Consider</a><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-fit" class="pv-tab">4. When Not to Use It</a><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable" class="pv-tab">5. How to Enable It</a><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data" class="pv-tab">6. Tracking Impact</a><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case" class="pv-tab">7. Pitch to Leadership</a></div>

<div class="pv-panel active"><style>
:root { --yellow: #FFD706; --orange: #FF8200; --vermillion: #FF5810; --salmon: #FF9D88; --offblack: #0D0D0B; --darkgray: #32312D; --gray: #807D73; --lightgray: #CCC9B8; --brightgray: #F1EFE3; --offwhite: #FFFDF2; }
.rc-guide { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; color: var(--offblack); max-width: 900px; margin: 0 auto; }
.rc-hero { background: var(--offblack); color: white; padding: 48px 40px; border-radius: 16px 16px 0 0; text-align: center; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; }
.rc-subtitle { color: var(--lightgray); font-size: 16px; }
.rc-badge { background: var(--yellow); color: var(--offblack); padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; }
.rc-flywheel-retain { background: var(--salmon); color: var(--offblack); }
.rc-stats { display: flex; justify-content: center; gap: 32px; margin-top: 24px; }
.rc-stat { color: var(--lightgray); font-size: 14px; }
.rc-stat-num { color: var(--yellow); font-weight: 700; font-size: 20px; display: block; }
.rc-nav { display: flex; gap: 0; background: var(--brightgray); padding: 0; overflow-x: auto; border-bottom: 2px solid var(--lightgray); }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: var(--gray); font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: var(--offblack); background: var(--offwhite); }
.rc-nav a.is-active { color: var(--offblack); font-weight: 600; border-bottom-color: var(--yellow); background: var(--offwhite); }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: var(--lightgray); color: var(--gray); display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-sec { padding: 40px; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: var(--yellow); border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px; flex-shrink: 0; }
.rc-sec-header h2 { font-size: 24px; margin: 0 0 4px; font-weight: 700; }
.rc-sec-header p { color: var(--gray); margin: 0; font-size: 15px; }
.rc-card { background: var(--offwhite); border-radius: 12px; padding: 28px; margin-bottom: 20px; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: var(--darkgray); line-height: 1.7; margin: 0 0 12px; font-size: 15px; }
.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: var(--offblack); }
.rc-steps { display: flex; flex-direction: column; gap: 16px; margin: 20px 0; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: var(--offwhite); border-radius: 12px; padding: 20px; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: 14px; flex-shrink: 0; }
.rc-step-content h4 { margin: 0 0 4px; font-size: 16px; font-weight: 600; }
.rc-step-content p { margin: 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-tip { border-left: 4px solid var(--yellow); background: var(--offwhite); padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-tip strong { color: var(--offblack); }
.rc-warning { border-left: 4px solid var(--orange); background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-checklist { background: var(--offwhite); border-radius: 12px; padding: 24px; margin: 20px 0; }
.rc-cl-header { font-size: 16px; font-weight: 600; margin-bottom: 16px; }
.rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
.rc-cb { width: 20px; height: 20px; border-radius: 4px; border: 2px solid var(--lightgray); flex-shrink: 0; cursor: pointer; margin-top: 2px; }
.rc-cli label { font-size: 14px; color: var(--darkgray); line-height: 1.5; cursor: pointer; }
.rc-3col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
.rc-wi { background: var(--offwhite); border-radius: 12px; padding: 24px; text-align: center; }
.rc-sec-nav { display: flex; justify-content: space-between; padding: 0 40px 40px; }
.rc-btn-prev, .rc-btn-next { display: inline-flex; align-items: center; gap: 8px; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; transition: all 0.2s; }
.rc-btn-prev { background: var(--brightgray); color: var(--offblack); }
.rc-btn-next { background: var(--yellow); color: var(--offblack); }
.rc-link-btn { display: inline-flex; align-items: center; gap: 8px; padding: 10px 20px; background: var(--brightgray); border-radius: 8px; text-decoration: none; color: var(--offblack); font-size: 14px; font-weight: 500; margin: 4px; transition: all 0.2s; }
.rc-link-sec { padding: 32px 40px; background: var(--brightgray); border-radius: 0 0 16px 16px; }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1rpQ40zAs49C7xuFkSau7-UimkPNxwMa2" alt="Retain stage" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;">
    <span class="rc-badge">Recurly Subscriptions</span>
    <h1>Save Your Revenue: Account Updater</h1>
    <p class="rc-subtitle">Learn how Account Updater helps reduce involuntary churn by automatically keeping card details current.</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">24</span> min read</div>
    </div>
  </div>

  <div class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater"><span class="rc-snum">1</span> What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits" class="is-active"><span class="rc-snum">2</span> Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations"><span class="rc-snum">3</span> Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-fit"><span class="rc-snum">4</span> When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable"><span class="rc-snum">5</span> How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data"><span class="rc-snum">6</span> Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case"><span class="rc-snum">7</span> Pitch to Leadership</a>
  </div>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1dQpFxnm38HN6ZNeRBSjP3R4Tt--R_wON" alt="lightbulb icon" style="width:28px;height:28px;"></div>
      <div><h2>Why Use Account Updater?</h2><p>Understand the business impact of outdated credentials and recovered revenue.</p></div>
    </div>

    <div class="rc-card">
      <h3>The Hidden Revenue Leak You Can't Afford to Ignore</h3>
      <p>Every year, hundreds of millions of cards are reissued. Banks replace cards when they expire, when fraud is detected, or simply as part of security cycles. Each time this happens, the billing info your platform has on file becomes instantly outdated.</p>
      <p>For subscription businesses, outdated card details are the single largest driver of <strong>involuntary churn</strong>. Industry data shows that involuntary churn accounts for <strong>20–40% of all subscriber losses</strong>. Account Updater addresses this at the source by proactively obtaining refreshed credentials before the next billing cycle.</p>
    </div>

    <div class="rc-subhead">The Revenue Impact by the Numbers</div>
    <div class="rc-3col">
      <div class="rc-wi"><img src="https://drive.google.com/thumbnail?sz=w200&id=1zog70GXF8MGG0LH8XR1pClQj4Xp41PBe" alt="wallet icon" style="width:28px;height:28px;"><h4>Up to 12% Revenue Recovered</h4><p>Merchants typically recover 8–12% of revenue that would otherwise be lost to failed payments from outdated cards.</p></div>
      <div class="rc-wi"><img src="https://drive.google.com/thumbnail?sz=w200&id=1zK3mlZEE50CjiIH_pQo1ytqaz3gVvgjP" alt="heart hand icon" style="width:28px;height:28px;"><h4>Reduced Subscriber Friction</h4><p>Subscribers never have to manually update their details, leading to seamless renewals and higher satisfaction.</p></div>
      <div class="rc-wi"><img src="https://drive.google.com/thumbnail?sz=w200&id=1IvV473EacJuzoqsAw0D-wrs4MY-gx2SI" alt="speedometer icon" style="width:28px;height:28px;"><h4>Lower Dunning Load</h4><p>Fewer failed transactions mean fewer dunning emails, fewer support tickets, and less operational overhead.</p></div>
    </div>

    <div class="rc-subhead">A Proactive Layer in Your Stack</div>
    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge">1</div><div class="rc-step-content"><h4>Prevents the Decline Before It Happens</h4><p>Unlike reactive retry logic, Account Updater proactively refreshes credentials days or weeks before a renewal.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">2</div><div class="rc-step-content"><h4>Eliminates the "Update Your Card" Experience</h4><p>Sending emails creates friction. Many subscribers never complete the update. This removes that hurdle entirely.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">3</div><div class="rc-step-content"><h4>Compounds Over Time</h4><p>The larger your base grows, the more cards expire each month, and the more revenue Account Updater protects.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">4</div><div class="rc-step-content"><h4>Complements AI Revenue Recovery</h4><p>Account Updater fixes credentials, while intelligent retries and dunning handle transient bank declines.</p></div></div>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header">Quick Self-Assessment: Is Account Updater Right for You?</div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="c1"><label for="c1">You bill subscribers on a recurring basis (monthly, quarterly, or annually)</label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="c2"><label for="c2">Your decline reports show "expired card" as a top decline reason</label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="c3"><label for="c3">You have subscribers on annual plans (higher risk of card changes)</label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="c6"><label for="c6">You accept Visa, Mastercard, American Express, or Discover</label></div>
    </div>
  </div>

  <div class="rc-sec-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" class="rc-btn-prev">← Previous</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations" class="rc-btn-next">Next →</a>
  </div>
</div></div></body></html>
`}</HTMLBlock>

<br />
