---
title: 'Overview: App Management'
excerpt: >-
  Recurly App Management combines subscription metrics across Apple App Store
  and Google Play through a simple, automated data sync.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

###  App Management product tour

Discover how Recurly seamlessly integrates subscription metrics from both Apple App Store and Google Play. Experience the power of automation and gain a unified view of your data. Do not miss out on unlocking the full potential of our App Management product.

[block:embed]
{
  "html": false,
  "url": "https://fast.wistia.net/embed/iframe/k1vgnmix5h?videoFoam=true",
  "title": "iframe",
  "provider": "fast.wistia.net",
  "href": "https://fast.wistia.net/embed/iframe/k1vgnmix5h?videoFoam=true",
  "typeOfEmbed": "iframe",
  "height": "450px",
  "width": "800px",
  "iframe": true
}
[/block]


### Required plan

This feature is only available to customers on the Professional or Elite subscription plan. To request to upgrade to your plan, please reach out to your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) for more details.

### Additional cost

This feature requires an additional cost. Please reach out to your Recurly Account Manager or [support@recurly.com](mailto:support@recurly.com) for pricing details.

### Prerequisites

- App Management is only available to Recurly customers.
- Recurly does **not** require customers to implement a SDK within their mobile app.
- **Important access requirement:** To access Recurly App Management, you need **Configuration ** access permissions within Recurly. To confirm or set these permissions, consult this <a href="https://docs.recurly.com/docs/user-roles-and-permissions" target="_blank">comprehensive guide</a>.

### Limitations

- Recurly currently focuses on auto-renewing subscriptions. For Apple, non-renewing subscriptions, consumable in-app purchases, and non-consumable in-app purchases are not supported. For Google, one-time products (aka: managed products) are not supported.
- Recurly processes all real-time notifications coming from Apple and Google, to ensure that Recurly customers have full visibility into the complete subscriber lifecycle for all subscribers. Apple does include an optional <a href="https://developer.apple.com/documentation/appstoreserverapi/send_consumption_information/" target="_blank">consumption request</a> which Recurly does not currently process. This request requires customers to build a new workflow to submit several details back to Apple to assist with refunds. In addition, it requires customers to manage consent from subscribers, which can be complicated.
- If you want visibility into mobile app subscriptions created prior to connecting Recurly, a migration of the historical events will need to be initiated as described <a href="https://docs.recurly.com/docs/step-by-step-process#migration" target="_blank">here</a>.
- Recurly offers API endpoints to support several different types of integrations. As of today, there are pre-built integrations for the Apple App Store and Google Play.