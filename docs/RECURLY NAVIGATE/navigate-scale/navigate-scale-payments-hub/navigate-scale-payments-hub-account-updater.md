---
title: 'Payments Hub: Account Updater'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
.rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
*{box-sizing:border-box}body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
.rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px}
.rc-badge{display:inline-flex;align-items:center;gap:8px;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
.rc-badge img{width:16px;height:16px;display:block;object-fit:contain}
.rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
.rc-hero p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 0;color:var(--lightgray)}
.rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
.rc-nav a{display:inline-flex;align-items:center;gap:10px;padding:10px 18px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s}
.rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
.rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack);box-shadow:0 2px 10px rgba(255,215,6,.25)}
.rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
.rc-sec{margin-bottom:56px}
.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
.rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
.rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
.rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
.rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
.rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
.rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
.rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray)}
.rc-wi h4{font-size:.9rem;font-weight:700;margin:0 0 6px;color:var(--offblack)}
.rc-wi p{font-size:.82rem;color:var(--gray);line-height:1.5;margin:0}
.rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
.rc-tipicon{font-size:24px;flex-shrink:0}
.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
.rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start;margin-bottom:24px}
.rc-wicon{font-size:20px;flex-shrink:0}
.rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
.rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:28px}
.rc-cl-header{padding:16px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:center;gap:10px;background:var(--offblack)}
.rc-cl-header h3{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
.rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:flex-start;gap:14px}
.rc-cli:last-child{border-bottom:none}
.rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;background:#fff}
.rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}
.rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
.rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}
.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
.rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
.rc-office{background:var(--offblack);color:#fff;border-radius:16px;padding:28px 32px;margin:28px 0;border:1px solid var(--yellow)}
.rc-office h4{color:var(--yellow);margin:0 0 10px;font-size:1rem;font-weight:800;text-transform:uppercase;letter-spacing:1px}
.rc-office p{color:var(--lightgray);font-size:.92rem;line-height:1.6;margin:0 0 18px}
.rc-office a{background:var(--yellow);color:var(--offblack);text-decoration:none;padding:10px 22px;border-radius:10px;font-weight:700;font-size:.88rem;display:inline-flex;align-items:center;gap:8px}
@media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-2col{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">
      <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Scale">
      Scale
    </div>
    <h1>Account Updater Dashboard</h1>
    <p>The Account Updater dashboard shows you how much revenue was protected through automatic card updates — before those payments ever had a chance to fail.</p>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub">Payments Hub</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview"><span class="rc-snum">1</span>Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing"><span class="rc-snum">2</span>Payment processing</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater"><span class="rc-snum">3</span>Account updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries"><span class="rc-snum">4</span>Payment retry recovery</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention"><span class="rc-snum">5</span>Fraud prevention</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources"><span class="rc-snum">6</span>Review &amp; resources</a>
  </nav>

  <img src="https://files.readme.io/2e488cefdf0e0cbbac44170f4774480b23c60e9445a66061c27f83f040bccf4c-Account_Updater_Dashboard.png" style="width:100%;border-radius:14px;border:1px solid var(--lightgray);margin-bottom:24px;" />
    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Not seeing Account Updater data?</strong> This dashboard requires Account Updater to be enabled on your Recurly site. If you see no data or a "Learn More" prompt, Account Updater may not be active for your account. <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" target="_blank" style="color:var(--orange);font-weight:700;">Learn about Account Updater →</a></p>
    </div>


    <h3 class="rc-subhead">📋 What's on this dashboard</h3>
    <div class="rc-card">
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.75;margin:0;">
        <strong>Successful card updates</strong> — Total number of cards successfully updated in the period, with comparison to previous period.<br><br>
        <strong>Successful updates over time</strong> — A line chart showing the daily count of card updates. A sudden drop may signal an issue worth investigating.<br><br>
        <strong>Payments authorized on updated cards</strong> — The total payment volume authorized on updated cards — this includes cards that were updated prior to the time period in view.<br><br>
        <strong>Successful payments over time</strong> — A bar chart showing the revenue volume on updated cards by day.<br><br>
        <strong>Update type</strong> — A breakdown of card number changes vs. expiration date updates. Card number changes carry more disruption risk; expiry updates are more routine.<br><br>
        <strong>Updates by card type</strong> — Which card networks (Visa, Mastercard, Amex, Discover) are driving the most update activity.
      </p>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>What to look for in Update Type</h4><p>A card number change means the subscriber received an entirely new card — often due to fraud or bank migration. These carry more risk than an expiry update because the old number is fully invalid. If you see a high proportion of card number changes, it may indicate a fraud event at a major issuer affecting your subscriber base.</p></div>
    </div>


    <h3 class="rc-subhead">✅ Activity: Explore Account Updater</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Account updater activity</h3></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="au1"><label for="au1" class="rc-clab">How much revenue was authorized on updated cards in the last 30 days?<span>This is the revenue you would have likely lost without Account Updater running in the background</span></label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="au2"><label for="au2" class="rc-clab">Look at the Update Type chart. What percentage of your updates are card number changes vs. expiry updates?<span>A high proportion of card number changes may indicate a recent fraud event at an issuer</span></label></div>
      <div class="rc-cli"><input type="checkbox" class="rc-cb" id="au3"><label for="au3" class="rc-clab">Check Updates by Card Type. Which card network is generating the most update activity?<span>While a small number of updates for a lesser-used card brand is normal, zero updates could indicate a problem.</span></label></div>
    </div>

    <div class="rc-office">
      <h4>🗓️ Not using Account Updater yet?</h4>
      <p>Join Global Office Hours to talk with a CSM about whether Account Updater is right for your business and how to get it enabled. It's one of the most impactful, proactive revenue recovery tools available to Recurly merchants.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank">Register for office hours →</a>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing">← Payment processing</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries">Next: Payment retry recovery →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
<a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" target="_blank">📚 Navigate: Account Updater Customer Learning</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/" target="_blank">🌐 Join Global Office Hours</a>
  </div>
</div>
`}</HTMLBlock>

<br />
