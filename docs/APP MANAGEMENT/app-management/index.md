---
title: App Management
excerpt: >-
  Review this page to see to gain a better understanding of what App Management
  offers, and how it works
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: >-
    Review the subpages in this section to read more about how to setup App
    Management, and use it on a daily basis
---
# Definition

App Management gives you a complete picture of your subscription business by combining analytics across App Stores with web through a simple, automated data sync. In addition, App Management streamlines your processes for entitlement checking and centralizes all of your subscription lifecycle notifications.

> 👍 Sell and manage Apple subscriptions through Recurly
>
> You can also sell and manage Apple App Store subscriptions directly through Recurly. [Learn more here](https://docs.recurly.com/docs/sell-and-manage-apple-subscriptions-through-recurly#/).

# Key Benefits

* Grow subscription revenue by uncovering new subscription acquisition and retention insights and opportunities through cross-platform analytics
* Enhance the subscriber experience by gaining a holistic, cross-platform view of subscribers and building an optimal communication and engagement strategy
* Increase operational efficiencies by developing new cross-platform subscription processes and workflows through robust APIs and webhooks
* Save development time and resources by eliminating the need to build and maintain App Store data integrations, saving scarce resources across web and mobile engineering teams

# Key Details

At a high level, Recurly is listening to real-time notifications sent from the Apple App Store and Google Play Store, processing subscription related events, and providing you a clear view into the subscription lifecycle for all your mobile app subscriptions.

For a deeper understanding of how App Management works, and to understand some of the technical requirements, read through the detailed walkthrough below.

Note: Recurly does **not** require customers to implement a SDK within their mobile app.

## 1. Uniquely identifying your customers

In order for Recurly to properly associate a subscription related event from Apple or Google, Recurly needs to have a unique ID established for each customer. For mobile app subscriptions, Recurly will look for that unique ID in the notification from Apple or Google. It is important that those unique IDs are incorporated into your subscription purchasing workflows for your mobile apps. The below list highlights requirements for this unique ID.

* For Apple subscriptions, <a href="https://developer.apple.com/documentation/appstoreserverapi/appaccounttoken" target="_blank">appAccountToken</a> is the unique ID. To learn how to set this unique ID (UUID), see <a href="https://developer.apple.com/documentation/storekit/product/purchaseoption/3749440-appaccounttoken" target="_blank">appAccountToken</a>.
* For Google subscriptions, <a href="https://developers.google.com/android-publisher/api-ref/rest/v3/purchases.subscriptionsv2#externalaccountidentifiers" target="_blank">obfuscatedExternalAccountId</a> is the unique ID. To learn how to set this unique ID within your billing flow, see the Google <a href="https://developer.android.com/reference/com/android/billingclient/api/BillingFlowParams.Builder#setObfuscatedAccountId(java.lang.String)" target="_blank">setObfuscatedAccountId method</a>. For additional information from Google about how this account identifier is used for integrations, see <a href="https://developers.google.com/android-publisher/api-ref/rest/v3/purchases.subscriptionsv2#externalaccountidentifiers" target="_blank">ExternalAccountIdentifiers</a>.
* To conform with Recurly accounts, the unique ID needs to be 50 characters or less.
* Once the unique ID is established for a customer, it should not change.

To help you decipher that unique ID when in Recurly and view information such as name and e-mail address for your customer, Recurly does need you to share that contact information once per customer. Recurly offers a few different ways to provide that info, which can be selected depending on your preferred workflow.

**Scenario 1:** A brand new customer subscribes through your mobile app **\<-- Most common**

* In this scenario, Recurly is not yet aware of the new customer, and therefore does not have a customer account within Recurly. So, you have two options and can select one that works best for you.

1. Before the customer purchases your subscription, POST to <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_account" target="_blank">Create an account</a> using the above unique ID as 'code' and share important customer details such as name and e-mail. When Recurly receives a notification associated with that unique ID, the subscription activity will be automatically associated with the correct account and you will immediately have the customer details available.
   1. If you have a requirement that does not allow you to use the unique ID (appAccountToken for Apple, or obfuscatedExternalAccountId for Google) as the 'code', you can still use your naming convention (e.g., acme|UUID) for the 'code'. However, you must provide the unique ID as 'external\_account\_code' within external\_accounts when you POST. This key step ensures Recurly can match the incoming notifications to the correct Recurly account.
2. After the customer purchases your subscription, PUT to <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/update_account" target="_blank">Update an account</a> using the unique ID as the account code for 'account\_id' and share important customer details such as name and e-mail. For example, PUT /accounts/code-\{unique ID} and include those details. The outcome is the same as the above option, because Recurly will automatically create a customer account for you when the first subscription purchase occurs.
   1. Please note that this option assumes the unique ID (appAccountToken for Apple, or obfuscatedExternalAccountId for Google) is the 'account\_id'. In other words, this option does not work if you use a different convention for your Recurly account.

**Scenario 2:** Your customer has already purchased one of your subscriptions through the web, and is now purchasing your mobile app subscription. This is typically a temporary scenario as a customer transitions from a web to mobile app subscription.

* In this scenario, Recurly is aware of the customer, and already has a customer account within Recurly. To ensure their mobile app subscription is connected with that existing Recurly account, it is important that you POST to <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_account_external_account" target="_blank">Create an external account</a> to associate their unique ID to the existing Recurly customer account. If not, your customer may show up in Recurly under two different customer accounts.
* Assuming your customer will not end up with two subscriptions, you will likely want to cancel the web-based subscription with a PUT to <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/cancel_subscription" target="_blank">Cancel a subscription</a>.

As seen above, Recurly is flexible and has several API endpoints to support your workflow.

## 2. Receiving real-time notifications

After completing the [Step-by-Step process](https://docs.recurly.com/docs/step-by-step-process) to connect and configure App Management, Recurly will begin to receive real-time notifications specific to subscription related activity in your mobile apps. This allows Recurly to be aware of important events, such as a new customer purchased a subscription, or if a subscription failed to renew.

Depending on the notification, Recurly will use the provided API key to pull additional information to help provide a complete picture into the specific subscription related event.

## 3. Updating Recurly with subscription lifecycle activity

For each event, Recurly will map the subscription to the corresponding existing customer account. For example, if a paid renewal event is received, Recurly will note that renewal activity for the correct customer account, and associate a paid invoice showing the amount.

## 4. Notifying you for any subsequent actions

Immediately after Recurly has processed the notification, Recurly will trigger the respective webhook to your endpoint. This allows you to take any subsequent action (e.g., e-mail your customer) based on that webhook notification.

**With this information in mind, continue reading the subpages to review how to setup App Management, and learn more about how you can use it on a daily basis.**

# Helpful Resources

To hear more about App Management, and see a walkthrough of App Management, watch these <a href="https://recurly.com/resources/webinar/app-management-webinar-series/" target="_blank">two on-demand webinars</a>.