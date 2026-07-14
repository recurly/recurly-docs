---
title: 'Overview: App Management'
excerpt: >-
  Recurly App Management integrates subscription metrics from the Apple App
  Store and Google Play into a unified view — with real-time notifications,
  automation, and full subscriber lifecycle visibility.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<div class="rp-page">
  <div class="rp-overview">Recurly App Management brings your Apple App Store and Google Play subscription data into one place. Connect your stores, automate subscription lifecycle tracking, and get a unified view of your mobile subscribers alongside your other Recurly data — without requiring an SDK in your mobile app.</div>
  <div style={{position: "relative", paddingTop: "56.25%", marginBottom: "28px", borderRadius: "10px", overflow: "hidden"}}>
    <iframe src="https://fast.wistia.net/embed/iframe/k1vgnmix5h"
      title="App Management product tour"
      allow="autoplay; fullscreen"
      allowtransparency="true"
      frameBorder="0"
      scrolling="no"
      allowFullScreen
      style={{position: "absolute", top: 0, left: 0, width: "100%", height: "100%", border: "none"}}></iframe>
  </div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Not included in Starter or Pro — contact <a href="https://recurly.com/demo/contact-sales/" target="_blank">Recurly Sales</a> to upgrade</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">1</span>Key details</a>
  </div>
</div>

<div class="rp-cost">
  <strong>Additional cost</strong><br/>
  App Management requires an additional cost. Contact <a href="mailto:support@recurly.com">support@recurly.com</a> or your Recurly account manager for pricing details.
</div>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Sell Apple subscriptions through Recurly</strong>You can also sell and manage Apple App Store subscriptions directly through Recurly. <a href="https://docs.recurly.com/docs/sell-and-manage-apple-subscriptions-through-recurly#/" target="_blank">Learn more</a>.</div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>App Management is only available to Recurly customers</li>
  <li>Recurly does <strong>not</strong> require you to implement an SDK within your mobile app</li>
  <li><strong>Configuration access permissions</strong> are required within Recurly. To confirm or set permissions, see the <a href="https://docs.recurly.com/docs/user-roles-and-permissions" target="_blank">user roles and permissions guide</a></li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Recurly currently supports auto-renewing subscriptions only. For Apple: non-renewing subscriptions, consumable in-app purchases, and non-consumable in-app purchases are not supported. For Google: one-time products (managed products) are not supported</li>
  <li>Recurly processes all real-time notifications from Apple and Google for full subscriber lifecycle visibility. Apple's optional <a href="https://developer.apple.com/documentation/appstoreserverapi/send_consumption_information/" target="_blank">consumption request</a> is not currently processed — it requires building a custom workflow to submit data back to Apple and managing subscriber consent</li>
  <li>To get visibility into mobile app subscriptions created before connecting Recurly, a historical event migration must be initiated. See the <a href="https://docs.recurly.com/docs/step-by-step-process#migration" target="_blank">migration guide</a> for details</li>
  <li>Recurly currently offers pre-built integrations for the Apple App Store and Google Play</li>
</ul>

# Key details

<div class="rp-nav-grid">

<Cards>
  <Card title="Apple App Store integration" href="https://docs.recurly.com/docs/sell-and-manage-apple-subscriptions-through-recurly#/" target="_blank">
    Connect your Apple App Store to sync subscription events, manage subscriber lifecycle, and view Apple subscription data alongside your Recurly metrics.
  </Card>
  <Card title="Google Play integration">
    Connect Google Play to bring auto-renewing subscription metrics and real-time notifications into Recurly for a unified view of your mobile subscribers.
  </Card>
</Cards>
</div>

<br />
