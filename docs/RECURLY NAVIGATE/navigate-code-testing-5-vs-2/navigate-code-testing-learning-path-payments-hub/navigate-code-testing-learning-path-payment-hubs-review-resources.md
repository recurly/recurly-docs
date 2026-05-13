---
title: Navigate Code Testing Learning Path Payment Hubs Review Resources
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
/* 1. Core Variables & Reset */
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

/* 2. Hero & Badge Styling */
.rc-hero { background: var(--offblack); color: #fff; padding: 56px 40px 48px; text-align: center; border-radius: 16px; margin-bottom: 24px; }
.rc-badge { display: inline-flex; align-items: center; gap: 8px; background: var(--yellow); color: var(--offblack); border-radius: 20px; padding: 6px 18px; font-size: 13px; font-weight: 700; letter-spacing: 1px; text-transform: uppercase; margin-bottom: 20px; }
.rc-badge img { width: 16px; height: 16px; display: block; object-fit: contain; }
.rc-hero h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; margin: 0 0 14px; color: var(--offwhite); }
.rc-hero p { font-size: 1.05rem; opacity: .8; max-width: 700px; margin: 0 auto; color: var(--lightgray); }

/* 3. Top Navigation (Flex Pill Style) */
.rc-nav { display: flex; flex-wrap: wrap; gap: 10px; margin: 24px 0 28px; }
.rc-nav a { display: inline-flex; align-items: center; gap: 10px; padding: 10px 18px; border-radius: 12px; border: 1px solid var(--lightgray); background: #fff; color: var(--darkgray); text-decoration: none !important; font-size: .88rem; font-weight: 700; transition: border-color .2s, box-shadow .2s; }
.rc-nav a:hover { border-color: var(--yellow); box-shadow: 0 2px 8px rgba(255,215,6,.2); color: var(--offblack); }
.rc-nav a.is-active { background: var(--yellow); border-color: var(--yellow); color: var(--offblack); box-shadow: 0 2px 10px rgba(255,215,6,.25); }
.rc-snum { display: inline-flex; align-items: center; justify-content: center; width: 24px; height: 24px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: 12px; font-weight: 700; flex-shrink: 0; }

/* 4. Content Sections */
.rc-sec { margin-bottom: 56px; }
.rc-subhead { font-size: 1.1rem; font-weight: 800; margin: 32px 0 16px; color: var(--offblack); }
.rc-card { background: var(--offwhite); border-radius: 16px; padding: 28px; border: 1px solid var(--lightgray); margin-bottom: 24px; }

/* 5. Video Embed Styling */
.rc-video-container { border: 1px solid var(--lightgray); border-radius: 14px; overflow: hidden; margin-bottom: 32px; background: var(--offblack); }
.rc-video-frame { position: relative; aspect-ratio: 16/9; }
.rc-video-frame iframe { position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; }

/* 6. Checklist & Callouts */
.rc-checklist { background: var(--offwhite); border-radius: 16px; border: 1px solid var(--lightgray); overflow: hidden; margin-bottom: 28px; }
.rc-cl-header { padding: 16px 22px; display: flex; align-items: center; gap: 10px; background: var(--offblack); }
.rc-cl-header h3 { font-size: .88rem; font-weight: 700; text-transform: uppercase; letter-spacing: .5px; color: var(--yellow); margin: 0; }
.rc-cli { padding: 13px 22px; border-bottom: 1px solid var(--brightgray); display: flex; align-items: flex-start; gap: 14px; }
.rc-cb { width: 22px; height: 22px; border-radius: 6px; border: 2px solid var(--lightgray); flex-shrink: 0; background: #fff; margin-top: 2px; }
.rc-clab { font-size: .88rem; color: var(--darkgray); line-height: 1.4; }
.rc-clab span { display: block; font-size: .78rem; color: var(--gray); margin-top: 2px; }

.rc-tip { background: var(--offwhite); border: 2px solid var(--yellow); border-radius: 14px; padding: 20px 24px; display: flex; gap: 16px; align-items: flex-start; margin-bottom: 24px; }
.rc-tip h4 { font-size: .82rem; font-weight: 700; color: var(--offblack); text-transform: uppercase; margin: 0 0 4px; }
.rc-tip p { font-size: .87rem; color: var(--darkgray); line-height: 1.55; margin: 0; }

.rc-warning { background: #FFF8E6; border: 1px solid var(--orange); border-radius: 14px; padding: 16px 20px; display: flex; gap: 14px; align-items: flex-start; margin-bottom: 24px; }

/* 7. Footer Nav Buttons & Link Grid */
.rc-sec-nav { display: flex; justify-content: space-between; align-items: center; gap: 12px; margin-top: 40px; flex-wrap: wrap; }
.rc-btn-prev, .rc-btn-next { display: inline-flex; align-items: center; justify-content: center; padding: 11px 18px; border-radius: 10px; font-weight: 700; font-size: .88rem; text-decoration: none !important; }
.rc-btn-prev { background: #fff; color: var(--darkgray); border: 1px solid var(--lightgray) !important; }
.rc-btn-next { background: var(--yellow); color: var(--offblack); border: 1px solid var(--yellow); }

.rc-link-btn { display: inline-flex; align-items: center; gap: 8px; padding: 11px 18px; border-radius: 10px; font-weight: 700; font-size: .88rem; text-decoration: none !important; background: var(--offwhite); color: var(--darkgray); border: 1px solid var(--lightgray); margin: 0 8px 8px 0; }
.rc-link-btn:hover { border-color: var(--yellow); }

.rc-full-footer { border-top: 1px solid var(--lightgray); padding-top: 32px; margin-top: 48px; text-align: center; }
.rc-footer-grid { display: flex; flex-wrap: wrap; gap: 20px; justify-content: center; align-items: center; }
.rc-footer-link { color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .85rem; display: flex; align-items: center; gap: 6px; }
.rc-footer-link img { width: 14px !important; height: 14px !important; object-fit: contain; opacity: 0.6; }
.rc-footer-link:hover { color: var(--offblack); }

@media(max-width:640px){ .rc-nav, .rc-sec-nav { flex-direction: column; align-items: stretch; } }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">
      <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Scale">
      Scale
    </div>
    <h1>Account Updater Dashboard</h1>
    <p>Monitor how much revenue was protected through proactive, automatic card updates — before those payments ever had a chance to fail.</p>
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
    <img src="https://files.readme.io/2e488cefdf0e0cbbac44170f4774480b23c60e9445a66061c27f83f040bccf4c-Account_Updater_Dashboard.png" style="width:100%;border-radius:14px;border:1px solid var(--lightgray);margin-bottom:24px;" alt="Account Updater Dashboard" />

    <h3 class="rc-subhead">📹 Account Updater Dashboard Walkthrough</h3>
    <div class="rc-video-container">
      <div class="rc-video-frame">
        <iframe src="https://share.synthesia.io/embeds/videos/REPLACE_WITH_ID" loading="lazy" allowfullscreen></iframe>
      </div>
    </div>

    <div class="rc-warning">
      <span style="font-size:20px; flex-shrink:0;">⚠️</span>
      <p style="font-size:.87rem; color:var(--darkgray); line-height:1.55; margin:0;">
        <strong>Not seeing Account Updater data?</strong> This dashboard requires Account Updater to be enabled on your Recurly site. If you see no data, Account Updater may not be active. <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" target="_blank" style="color:var(--orange); font-weight:700;">Learn about Account Updater →</a>
      </p>
    </div>

    <h3 class="rc-subhead">📋 What's on this dashboard</h3>
    <div class="rc-card">
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.75;margin:0;">
        <strong>Successful card updates</strong> — Total number of cards successfully updated in the period, with comparison to previous period.<br><br>
        <strong>Successful updates over time</strong> — A line chart showing the daily count of card updates.<br><br>
        <strong>Payments authorized on updated cards</strong> — The total payment volume authorized on updated cards.<br><br>
        <strong>Update type</strong> — A breakdown of card number changes vs. expiration date updates.
      </p>
    </div>

    <div class="rc-tip">
      <span style="font-size:24px; flex-shrink:0;">💡</span>
      <div>
        <h4>What to look for in Update Type</h4>
        <p>A card number change means the subscriber received an entirely new card. These carry more disruption risk than an expiry update. If you see a high proportion of card number changes, it may indicate a fraud event at a major issuer.</p>
      </div>
    </div>

    <h3 class="rc-subhead">✅ Activity: Explore Account Updater</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Account updater activity</h3></div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label class="rc-clab">How much revenue was authorized on updated cards in the last 30 days?<span>This is revenue you likely would have lost without Account Updater.</span></label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label class="rc-clab">Look at the Update Type chart. What percentage of your updates are card number changes?<span>High card number changes may indicate recent fraud events.</span></label>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing">← Payment processing</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries">Next: Payment retry recovery →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <div style="display: flex; flex-wrap: wrap;">
      <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" target="_blank">📖 Navigate: Account Updater Learning</a>
      <a class="rc-link-btn" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>
      <a class="rc-link-btn" href="https://navigate.recurly.com/event-hub/" target="_blank">🌐 Join Global Office Hours</a>
    </div>

    <div class="rc-full-footer">
      <div class="rc-footer-grid">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
          <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview" class="rc-footer-link">1. Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing" class="rc-footer-link">2. Processing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater" class="rc-footer-link">3. Account Updater</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries" class="rc-footer-link">4. Retries</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention" class="rc-footer-link">5. Fraud</a>
        <a href="mailto:support@recurly.com" class="rc-footer-link">support@recurly.com</a>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
