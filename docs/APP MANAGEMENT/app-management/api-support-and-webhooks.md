---
title: API support and webhooks
excerpt: >-
  This page provides detail about the API endpoints involved with App
  Management, and the webhook events that are triggered as part of subscription
  lifecycle events
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# REST API endpoints

The following REST API endpoints allow you to programmatically pull pertinent information in a JSON format from Recurly regarding your mobile app subscriptions.

## External products

These endpoints are used to view information related to the External Products you configured during setup.

- <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_external_products" target="_blank">List all External Products by Site</a>.
- <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/get_external_product" target="_blank">Fetch an External Product</a>.

## External subscriptions

These endpoints are used to view information about external subscriptions, which are Apple or Google subscriptions that your customers have purchased.

- <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_external_subscriptions" target="_blank">List all External Subscriptions by Site</a>
- <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_account_external_subscriptions" target="_blank">List all External Subscriptions by Account</a>
- <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/get_external_subscription" target="_blank">Fetch an External Subscription</a>

## Entitlements

This endpoint is used to view information about the entitlements granted to a specific customer (aka: account).

- <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_entitlements" target="_blank">List Entitlements granted to an Account</a>

**For a complete list of the endpoints specific to App Management**, start at <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_external_subscriptions" target="_blank">External Subscription</a> and scroll down.

# Webhooks

For pertinent events in the subscription lifecycle, Recurly triggers a webhook. This allows you to take any subsequent action (e.g., e-mail your customer) based on that webhook notification.

Recurly webhook payloads are “lightweight” in nature and will require a subsequent call to the REST API in order to obtain the most up to date information about the App Store subscriptions. The below XML and JSON representations show an example of a webhook notification for a new External subscription. To get more info about the subscription, you would then utilize the <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/get_external_subscription" target="_blank">Fetch an External Subscription</a> endpoint with the "id" provided in the webhook.

```json
{
  "id": "s0lo0hdfmauc",
  "object_type": "external_subscription",
  "site_id": "qpem7fkwr763",
  "event_type": "created",
  "event_time": "2022-12-06T22:19:15Z"
}
```
```xml
<new_external_subscription_notification>
  <external_subscription>
    <id>uuid</>
  </external_subscription>
  <external_resource>
    <id></id>
    <external_object_reference></external_object_reference>
  </external_resource>
  <external_product_reference>
    <id></id>
    <reference_code></reference_code>
    <created_at></created_at>
    <updated_at></updated_at>
  </external_product_reference>
</new_external_subscription_notification>
```

## Configuring Recurly to send webhooks

To configure Recurly to send webhooks specific to Recurly App Management, navigate to **Integrations -> Webhooks** within Recurly. From the top right, click **Configure** . Depending on what works best for you, you can either create a **New Endpoint**, or select **Options -> Edit** for an existing endpoint. When configuring the endpoint, scroll down to view the External Subscription section of webhooks. For any event that you are interested in, select the checkbox corresponding to that event. For more detail about those events, read the next section. If you want to learn more about Recurly webhooks in general, visit our <a href="https://recurly.com/developers/reference/webhooks/#webhooks" target="_blank">Webhooks developer documentation</a>.

## Complete list of webhook events

The following tables provides a complete list of the webhooks Recurly will send related to mobile app subscriptions. Each webhook maps to a specific Apple or Google notification, as shown below in the table. To see JSON and XML examples for each of the webhooks listed below, view the <a href="https://recurly.com/developers/reference/webhooks/#external-subscription-notifications" target="_blank">External Subscription Notifications</a> section of the Webhooks page in our Recurly Development Hub.

[block:parameters]
{
  "data": {
    "h-0": "Recurly Event",
    "h-1": "Apple Event",
    "h-2": "Google Event",
    "0-0": "canceled",
    "0-1": "DID_CHANGE_RENEWAL_STATUS > AUTO_RENEW_DISABLED",
    "0-2": "SUBSCRIPTION_CANCELED",
    "1-0": "consumption_requested",
    "1-1": "CONSUMPTION_REQUEST",
    "1-2": "N/A",
    "2-0": "created (i.e., new subscription)",
    "2-1": "SUBSCRIBED > INITIAL_BUY",
    "2-2": "SUBSCRIPTION_PURCHASED",
    "3-0": "downgraded",
    "3-1": "DID_CHANGE_RENEWAL_PREF > DOWNGRADE",
    "3-2": "N/A",
    "4-0": "downgrade_canceled",
    "4-1": "DID_CHANGE_RENEWAL_PREF",
    "4-2": "N/A",
    "5-0": "expired",
    "5-1": "EXPIRED > VOLUNTARY  \nEXPIRED > BILLING_RETRY  \nEXPIRED > PRICE_INCREASE",
    "5-2": "SUBSCRIPTION_EXPIRED",
    "6-0": "extended_renewal",
    "6-1": "RENEWAL_EXTENDED",
    "6-2": "SUBSCRIPTION_DEFERRED",
    "7-0": "failed_renewal",
    "7-1": "DID_FAIL_TO_RENEW",
    "7-2": "SUBSCRIPTION_ON_HOLD",
    "8-0": "failed_renewal_with_grace_period",
    "8-1": "DID_FAIL_TO_RENEW > GRACE_PERIOD",
    "8-2": "SUBSCRIPTION_IN_GRACE_PERIOD",
    "9-0": "grace_period_expired",
    "9-1": "GRACE_PERIOD_EXPIRED",
    "9-2": "N/A",
    "10-0": "pause_schedule_changed",
    "10-1": "N/A",
    "10-2": "SUBSCRIPTION_PAUSE_SCHEDULE_CHANGED",
    "11-0": "paused",
    "11-1": "N/A",
    "11-2": "SUBSCRIPTION_PAUSED",
    "12-0": "plan_changed",
    "12-1": "N/A",
    "12-2": "SUBSCRIPTION_PURCHASED",
    "13-0": "price_change_confirmed",
    "13-1": "N/A",
    "13-2": "SUBSCRIPTION_PRICE_CHANGE_CONFIRMED",
    "14-0": "reactivated",
    "14-1": "DID_CHANGE_RENEWAL_STATUS > AUTO_RENEW_ENABLED",
    "14-2": "SUBSCRIPTION_RESTARTED",
    "15-0": "recovered",
    "15-1": "N/A",
    "15-2": "SUBSCRIPTION_RECOVERED",
    "16-0": "refunded",
    "16-1": "REFUND",
    "16-2": "N/A",
    "17-0": "refund_declined",
    "17-1": "REFUND_DECLINED",
    "17-2": "N/A",
    "18-0": "refund_reversed",
    "18-1": "REFUND_REVERSED",
    "18-2": "N/A",
    "19-0": "renewed",
    "19-1": "DID_RENEW  \nDID_RENEW > BILLING_RECOVERY",
    "19-2": "SUBSCRIPTION_RENEWED",
    "20-0": "resubscribed",
    "20-1": "SUBSCRIBED > RESUBSCRIBE",
    "20-2": "N/A",
    "21-0": "resubscribed_incorrect_account",
    "21-1": "SUBSCRIBED > RESUBSCRIBE",
    "21-2": "N/A",
    "22-0": "revoked",
    "22-1": "N/A",
    "22-2": "SUBSCRIPTION_REVOKED",
    "23-0": "upgraded",
    "23-1": "DID_CHANGE_RENEWAL_PREF > UPGRADE",
    "23-2": "N/A",
    "24-0": "voided",
    "24-1": "N/A",
    "24-2": "SUBSCRIPTION_VOIDED"
  },
  "cols": 3,
  "rows": 25,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


## Viewing triggered webhooks

All triggered webhooks are viewable within Recurly by navigating to **Integrations -> Webhooks**. In addition, when viewing the details of an Account or External Subscription, there is a link for Webhooks that will take you to a filtered view of the triggered webhooks.