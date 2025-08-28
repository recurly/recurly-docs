---
title: Integration best practices
excerpt: >-
  Recurly Professional Services has put together the following guide to help
  ensure you are successful integrating Recurly with Apple and Google. It is
  important to still carefully read through the <a
  href="https://docs.recurly.com/docs/app-management" target="_blank">App
  Management help pages</a> prior to this guide, as those pages cover additional
  key details.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
If you are already successfully viewing Apple or Google subscription lifecycle  events within Recurly based on reading the prior help pages, you are welcome to skip this guide.

# Configuration

You will need to configure App Management on your Recurly site in order for you to use any App Management features and to prepare for the migration. There are step-by-step guides to configure both Apple App Store and Google Play Store on your Recurly subdomain.

<a href="https://docs.recurly.com/docs/step-by-step-process#apple-app-store" target="_blank">Apple App Store Step-By-Step Guide</a>  \|\|  <a href="https://docs.recurly.com/docs/step-by-step-process#google-play" target="_blank">Google Play App Store Step-By-Step Guide</a>

# Testing

Before configuring App Management with your production data, we strongly recommend starting with sandbox/test data from each external store. Apple and Google have different ways of allowing developers to test on their platforms. Testing out all of your various use cases is crucial to a successful App Management integration.  

## Apple

Apple allows developers to use a “Sandbox Server URL” endpoint for testing. If that term is unfamiliar, you may have to set up your “Sandbox Server URL” in App Store Connect. You can learn about that <a href="https://developer.apple.com/help/app-store-connect/configure-in-app-purchase-settings/enter-server-urls-for-app-store-server-notifications/" target="_blank">here</a> under “Enter a URL for testing App Store Server Notifications in a Sandbox environment.” When configuring your sandbox site for testing in Recurly, you’ll want to edit the “Sandbox Server URL” instead of your “Production  Server URL.”

## Google

Google uses Pub/Sub topics for notifications and only allows notifications to go to one topic. However, you can create a second subscription to the same Pub/Sub topic for testing. Both endpoints, defined in their respective Pub/Sub subscription, will receive all test and prod notifications. Recurly evaluates every payload and will denote if the notification is production or test. You will likely see test and production notifications going to your non-prod Recurly subdomain and your prod Recurly subdomain. You can learn about that <a href="https://docs.recurly.com/docs/using-app-management#if-we-need-to-test-occasionally-eg-test-a-new-introductory-offer-to-ensure-everything-looks-good-within-recurly-how-can-we-ensure-that-testing-does-not-interfere-with-our-real-production-subscriptions" target="_blank">here</a>. Additionally, if you have two apps, e.g., one for dev and one for production, you can use your dev app, along with its Pub/Sub topic, on your sandbox site in Recurly for testing.

# Data Sync

Once you have properly configured the external stores to your Recurly site, whether for sandbox or production, they will be synced and their notifications will be sent to Recurly. We do not ignore or delete notifications, however, we do store them until we are able to successfully process them. In order for Recurly to properly process a notification and  associate it to a subscription related event from Apple or Google, we need to have a unique ID established for each customer. We  will look for that unique ID in the notification from each platform. It is important that those unique IDs are incorporated into your subscription purchasing workflows for Apple and Google. You can learn more about configuring and setting that up <a href="https://docs.recurly.com/docs/app-management#1-uniquely-identifying-your-customers" target="_blank">here</a>.

Additionally, if you have any historical data within the platforms, you will need to perform a data migration of said data into Recurly in order for us to properly process notifications related to those historical accounts/subscriptions. You will also need to generate unique IDs for them if you have not done so already.  **Do not turn on** the production sync before you’re ready for migration! This can lead to issues with the integration. We will create a shared folder on  Google Drive to send to you a daily report of unprocessed notifications when you are live on your production site with App Management. You can use this report to determine what needs to be done for those external subscriptions, which you will just need to import in most cases.

# External Products

External products are created in order for Recurly to correctly associate your unique Apple and Google subscriptions to a single product within Recurly. This makes it easier for you to track one type of subscription, which may be available via web or your mobile apps. You can learn more about configuring and setting that up <a href="https://docs.recurly.com/docs/step-by-step-process#creating-external-products" target="_blank">here</a>. If you don’t make the association,  the purchases will go to <a href="https://docs.recurly.com/docs/using-app-management#unassigned-purchases" target="_blank">unassigned purchases</a>.

Upgrades and downgrades within Recurly  for Apple subscriptions can behave in unexpected ways depending on how you set up your “Subscription Order” in App Store Connect. You will need to ensure that your highest upgrade is “1” and your lowest downgrade is the highest number. If numbers are shared for particular subscriptions, they may be considered a “downgrade” when changing between them.

# Webhooks & API

 Recurly follows industry standards and does not recommend using webhooks as the source of truth. Webhooks may be sent out of order, retried,  or sent multiple times due to failed delivery or other server related errors. Please, ensure that your endpoint can receive the same notification multiple times and notifications that may arrive out of order. Webhook payloads can be in JSON or XML formats. Before processing a webhook, send Recurly a success response. This will prevent Recurly from resending a webhook. After sending the response receipt, you can process the webhook.

The API is the most reliable data source so always make an API call when you receive a webhook that you take action on, such as sending an email to a customer. You can  use the receipt of the webhook to trigger an API query to validate the notification details against the current API data. Make sure you are using  the latest version of the API (current version v2021-02-25) to ensure you have access to our newest features.

<a href="https://recurly.com/developers/reference/webhooks/" target="_blank">Developer Reference</a>  \|\|   <a href="https://docs.recurly.com/docs/webhooks" target="_blank">Recurly Docs</a>   \|\|   <a href="https://docs.recurly.com/docs/api-support-and-webhooks" target="_blank">App Management API & Webhooks Docs</a>

# Automated Exports

Our Automated Exports feature is a much more efficient and reliable way to get data than cycling through resources in the API and can be used  for data warehousing. We have Automated Exports for External Subscriptions and External Invoices. They can be used to track events triggered in the last 24hr, ensuring systems are never more than 24hr out of sync.

<a href="https://docs.recurly.com/docs/automated-exports" target="_blank">Automated Exports Documentation</a>   \|\|   <a href="https://recurly.com/developers/api/v2021-02-25/index.html#tag/automated_exports" target="_blank">Automated Exports API</a>