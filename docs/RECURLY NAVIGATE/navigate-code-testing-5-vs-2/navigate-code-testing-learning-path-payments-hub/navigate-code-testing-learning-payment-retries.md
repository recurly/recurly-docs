---
title: Navigate Code Testing Learning Payment Retries
deprecated: false
hidden: false
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
/* 1. Global Variables & Base Styles */
.rc-guide {
  --yellow:    #FFD706;
  --orange:    #FF8200;
  --offblack:  #0D0D0B;
  --darkgray:  #32312D;
  --gray:      #807D73;
  --lightgray: #CCC9B8;
  --brightgray:#F1EFE3;
  --offwhite:  #FFFDF2;
  --scale:     #FF5810;
  font-family: 'Segoe UI', system-ui, sans-serif;
}
.rc-guide * { box-sizing: border-box; }

/* 2. Hero & Badge */
.rc-hero { background: var(--offblack); color: #fff; padding: 56px 40px 48px; text-align: center; border-radius: 16px; margin-bottom: 24px; }
.rc-badge { display: inline-flex; align-items: center; gap: 8px; background: var(--scale); color: #fff; border-radius: 20px; padding: 6px 18px; font-size: 13px; font-weight: 700; letter-spacing: 1px; text-transform: uppercase; margin-bottom: 20px; }
.rc-badge img { width: 16px; height: 16px; display: block; object-fit: contain; }
.rc-hero h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; margin: 0 0 14px; color: var(--offwhite); }
.rc-hero p { font-size: 1.05rem; opacity: .8; max-width: 700px; margin: 0 auto; color: var(--lightgray); }

/* 3. Navigation */
.rc-nav { display: flex; flex-wrap: wrap; gap: 10px; margin: 0 0 28px; }
.rc-nav a { display: inline-flex; align-items: center; gap: 10px; padding: 10px 18px; border-radius: 12px; border: 1px solid var(--lightgray); background: #fff; color: var(--darkgray); text-decoration: none !important; font-size: .88rem; font-weight: 700; transition: all .2s; }
.rc-nav a:hover { border-color: var(--scale); box-shadow: 0 2px 8px rgba(255,88,16,.2); color: var(--offblack); }
.rc-nav a.is-active { background: var(--scale); border-color: var(--scale); color: #fff; }
.rc-snum { display: inline-flex; align-items: center; justify-content: center; width: 24px; height: 24px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: #fff; color: var(--scale); }

/* 4. Content Sections */
.rc-sec { margin-bottom: 56px; }
.rc-sec-header { display: flex; align-items: flex-start; gap: 20px; margin-bottom: 32px; }
.rc-sec-icon { width: 56px; height: 56px; border-radius: 16px; display: flex; align-items: center; justify-content: center; font-size: 26px; flex-shrink: 0; background: var(--scale); color: #fff; }
.rc-sec-header h2 { font-size: 1.7rem; font-weight: 800; margin: 0 0 6px; color: var(--offblack); }
.rc-sec-header p { color: var(--gray); font-size: .95rem; line-height: 1.5; margin: 0; }

.rc-card { background: var(--offwhite); border-radius: 16px; padding: 28px; border: 1px solid var(--lightgray); margin-bottom: 32px; }
.rc-subhead { font-size: 1.1rem; font-weight: 800; margin: 40px 0 16px; color: var(--offblack); display: flex; align-items: center; gap: 10px; }

/* 5. Video Embed */
.rc-video-box { border: 1px solid var(--lightgray); border-radius: 14px; overflow: hidden; margin-bottom: 32px; background: var(--offblack); }
.rc-video-label { background: var(--offblack); padding: 12px 20px; color: var(--yellow); font-size: .85rem; font-weight: 800; text-transform: uppercase; }
.rc-video-frame { position: relative; aspect-ratio: 16/9; }
.rc-video-frame iframe { position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; }

/* 6. Callouts & Checklist */
.rc-warning { background: #FFF8E6; border: 1px solid var(--orange); border-radius: 14px; padding: 16px 20px; display: flex; gap: 14px; align-items: flex-start; margin-bottom: 24px; }
.rc-tip { background: var(--offwhite); border: 2px solid var(--scale); border-radius: 14px; padding: 20px 24px; display: flex; gap: 16px; align-items: flex-start; margin-bottom: 24px; }
.rc-checklist { background: var(--offwhite); border-radius: 16px; border: 1px solid var(--lightgray); overflow: hidden; margin-bottom: 28px; }
.rc-cl-header { padding: 16px 22px; display: flex; align-items: center; gap: 10px; background: var(--offblack); }
.rc-cl-header h3 { font-size:.88rem; font-weight:700; text-transform:uppercase; color:var(--yellow); margin:0; }
.rc-cli { padding: 13px 22px; border-bottom: 1px solid var(--brightgray); display: flex; align-items: flex-start; gap: 14px; }
.rc-cb { width: 22px; height: 22px; border-radius: 6px; border: 2px solid var(--lightgray); flex-shrink: 0; background: #fff; margin-top: 2px; }
.rc-clab { font-size: .88rem; color: var(--darkgray); line-height: 1.4; }
.rc-clab span { display: block; font-size: .78rem; color: var(--gray); margin-top: 2px; }

/* 7. Footer & Buttons */
.rc-sec-nav { display: flex; justify-content: space-between; align-items: center; gap: 12px; margin-top: 40px; }
.rc-btn-prev, .rc-btn-next { display: inline-flex; align-items: center; justify-content: center; padding: 12px 20px; border-radius: 10px; font-weight: 700; font-size: .88rem; text-decoration: none !important; transition: all .2s; }
.rc-btn-prev { background: #fff; color: var(--darkgray); border: 1px solid var(--lightgray); }
.rc-btn-prev:hover { border-color: var(--offblack); background: var(--brightgray); }
.rc-btn-next { background: var(--yellow); color: var(--offblack); border: 1px solid var(--yellow); }
.rc-btn-next:hover { background: transparent; }

.rc-footer-mini { border-top: 1px solid var(--lightgray); padding-top: 24px; margin-top: 40px; display: flex; justify-content: center; gap: 24px; }
.rc-footer-link { color: var(--gray); font-size: .85rem; font-weight: 600; text-decoration: none !important; display: flex; align-items: center; gap: 6px; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.6; }

@media(max-width:640px){ .rc-sec-nav { flex-direction: column; align-items: stretch; } }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">
      <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Scale">
      Scale
    </div>
    <h1>Account Updater Dashboard</h1>
    <p>Monitor how much revenue is protected through proactive, automatic card updates—before payments ever fail.</p>
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

  <div class="rc-sec">
    <img src="https://files.readme.io/2e488cefdf0e0cbbac44170f4774480b23c60e9445a66061c27f83f040bccf4c-Account_Updater_Dashboard.png" style="width:100%;border-radius:14px;border:1px solid var(--lightgray);margin-bottom:32px;" alt="Account Updater Dashboard" />

    <h3 class="rc-subhead">📹 Account Updater Dashboard Walkthrough</h3>
    <div class="rc-video-box">
      <div class="rc-video-label">Watch the walkthrough</div>
      <div class="rc-video-frame">
        <iframe src="https://share.synthesia.io/embeds/videos/REPLACE_WITH_ID" loading="lazy" allowfullscreen></iframe>
      </div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Not seeing data?</strong> This dashboard requires Account Updater to be enabled. If you see no activity, it may not be active for your site. <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" target="_blank" style="color:var(--orange);font-weight:700;">Learn more →</a></p>
    </div>

    <h3 class="rc-subhead">📋 What's on this dashboard</h3>
    <div class="rc-card">
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.75;margin:0;">
        <strong>Successful card updates</strong> — Total number of cards successfully updated.<br><br>
        <strong>Successful updates over time</strong> — Line chart showing the daily count of card updates.<br><br>
        <strong>Payments authorized on updated cards</strong> — Total payment volume authorized on cards that were updated.<br><br>
        <strong>Update type</strong> — Breakdown of card number changes vs. expiration date updates.
      </p>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>What to look for in Update Type</h4>
        <p>A card number change carries more disruption risk than an expiry update. High proportions of card number changes can indicate a fraud event at a major issuer affecting your base.</p>
      </div>
    </div>

    <h3 class="rc-subhead">✅ Activity: Explore Account Updater</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Account updater activity</h3></div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label class="rc-clab">How much revenue was authorized on updated cards in the last 30 days?<span>This is revenue you likely would have lost without AU.</span></label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label class="rc-clab">Check the Update Type chart. What percentage are card number changes?<span>High changes may indicate external bank fraud migrations.</span></label>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing">← Payment processing</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries">Next: Payment retry recovery →</a>
    </div>

    <div class="rc-footer-mini">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
        <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
      </a>
      <a href="mailto:support@recurly.com" class="rc-footer-link">support@recurly.com</a>
    </div>
  </div>
</div>
`}</HTMLBlock>

<br />
