---
title: 'Payments Hub: Account Updater'
excerpt: >-
  Monitor how automatic card updates proactively protect your revenue by
  preventing payment failures before they occur. Learn to analyze update types,
  track authorized volume on updated cards, and identify trends across different
  card networks.
deprecated: false
hidden: false
metadata:
  keywords:
    - Proactive revenue recovery
    - automatic card updates
    - Account Updater analytics
    - credit card lifecycle management
    - authorized payment volume
    - card network trends.
  robots: index
---
<HTMLBlock>{`
<div class="rp-navigate-guide">
  <div class="rp-navigate-hero">
    <div class="rp-navigate-badge">
      <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Scale">
      Scale
    </div>
    <h1>Account Updater Dashboard</h1>
    <p>The Account Updater dashboard shows you how much revenue was protected through proactive, automatic card updates — before those payments ever had a chance to fail.</p>
  </div>

  <nav class="rp-navigate-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub">Payments Hub</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview"><span class="rp-navigate-snum">1</span>Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing"><span class="rp-navigate-snum">2</span>Payment processing</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater"><span class="rp-navigate-snum">3</span>Account updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries"><span class="rp-navigate-snum">4</span>Payment retry recovery</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention"><span class="rp-navigate-snum">5</span>Fraud prevention</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources"><span class="rp-navigate-snum">6</span>Review &amp; resources</a>
  </nav>

  <div class="rp-navigate-sec">

    <input type="checkbox" id="zoom-account-updater-dashboard" class="rp-navigate-zoom-toggle">
    <label class="rp-navigate-zoom" for="zoom-account-updater-dashboard">
      <img class="rp-navigate-zoom-img"
           src="https://files.readme.io/2e488cefdf0e0cbbac44170f4774480b23c60e9445a66061c27f83f040bccf4c-Account_Updater_Dashboard.png"
           alt="Account Updater dashboard overview">
      <span class="rp-navigate-zoom-overlay">
        <img src="https://files.readme.io/2e488cefdf0e0cbbac44170f4774480b23c60e9445a66061c27f83f040bccf4c-Account_Updater_Dashboard.png" alt="">
      </span>
    </label>

    <div class="rp-navigate-warning">
      <span class="rp-navigate-wicon">⚠️</span>
      <p><strong>Not seeing Account Updater data?</strong> This dashboard requires Account Updater to be enabled on your Recurly site. If you see no data or a "Learn More" prompt, Account Updater may not be active for your account. <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" target="_blank" rel="noopener noreferrer">Learn about Account Updater →</a></p>
    </div>

    <h3 class="rp-navigate-subhead" id="whats-on-this-dashboard">
      <a class="rp-navigate-anchor" href="#whats-on-this-dashboard">📋 What's on this dashboard</a>
    </h3>
    <div class="rp-navigate-card">
      <p style="font-size:.92rem;color:var(--nav-darkgray);line-height:1.75;margin:0;">
        <strong>Successful card updates</strong> — Total number of cards successfully updated in the period, with comparison to previous period.<br><br>
        <strong>Successful updates over time</strong> — A line chart showing the daily count of card updates. A sudden drop may signal an issue worth investigating.<br><br>
        <strong>Payments authorized on updated cards</strong> — The total payment volume authorized on updated cards — this includes cards that were updated prior to the time period in view.<br><br>
        <strong>Successful payments over time</strong> — A bar chart showing the revenue volume on updated cards by day.<br><br>
        <strong>Update type</strong> — A breakdown of card number changes vs. expiration date updates. Card number changes carry more disruption risk; expiry updates are more routine.<br><br>
        <strong>Updates by card type</strong> — Which card networks (Visa, Mastercard, Amex, Discover) are driving the most update activity.
      </p>
    </div>

    <div class="rp-navigate-tip">
      <span class="rp-navigate-tipicon">💡</span>
      <div>
        <h4>What to look for in Update Type</h4>
        <p>A card number change means the subscriber received an entirely new card — often due to fraud or bank migration. These carry more risk than an expiry update because the old number is fully invalid. If you see a high proportion of card number changes, it may indicate a fraud event at a major issuer affecting your subscriber base.</p>
      </div>
    </div>

    <h3 class="rp-navigate-subhead" id="activity-explore-account-updater">
      <a class="rp-navigate-anchor" href="#activity-explore-account-updater">✅ Activity: Explore Account Updater</a>
    </h3>
    <div class="rp-navigate-checklist">
      <div class="rp-navigate-cl-header">
        <span>✅</span>
        <h3>Account updater activity</h3>
      </div>
      <div class="rp-navigate-cli">
        <input type="checkbox" class="rp-navigate-cb" id="au1">
        <label for="au1" class="rp-navigate-clab">
          How much revenue was authorized on updated cards in the last 30 days?
          <span>This is the revenue you would have likely lost without Account Updater running in the background</span>
        </label>
      </div>
      <div class="rp-navigate-cli">
        <input type="checkbox" class="rp-navigate-cb" id="au2">
        <label for="au2" class="rp-navigate-clab">
          Look at the Update Type chart. What percentage of your updates are card number changes vs. expiry updates?
          <span>A high proportion of card number changes may indicate a recent fraud event at an issuer</span>
        </label>
      </div>
      <div class="rp-navigate-cli">
        <input type="checkbox" class="rp-navigate-cb" id="au3">
        <label for="au3" class="rp-navigate-clab">
          Check Updates by Card Type. Which card network is generating the most update activity?
          <span>While a small number of updates for a lesser-used card brand is normal, zero updates could indicate a problem.</span>
        </label>
      </div>
    </div>

    <div class="rp-navigate-office">
      <h4>🗓️ Not using Account Updater yet?</h4>
      <p>Join Global Office Hours to talk with a CSM about whether Account Updater is right for your business and how to get it enabled. It's one of the most impactful, proactive revenue recovery tools available to Recurly merchants.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">Register for office hours →</a>
    </div>

    <div class="rp-navigate-sec-nav">
      <a class="rp-navigate-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing">← Payment processing</a>
      <a class="rp-navigate-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries">Next: Payment retry recovery →</a>
    </div>

    <h3 class="rp-navigate-subhead" id="additional-resources" style="margin-top:28px;">
      <a class="rp-navigate-anchor" href="#additional-resources">📚 Additional resources</a>
    </h3>
    <a class="rp-navigate-link-btn rp-navigate-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" target="_blank" rel="noopener noreferrer">📚 Navigate: Account Updater Customer Learning</a>
    <a class="rp-navigate-link-btn rp-navigate-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>
    <a class="rp-navigate-link-btn rp-navigate-link-sec" href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">🌐 Join Global Office Hours</a>

  </div>
</div>
`}</HTMLBlock>
