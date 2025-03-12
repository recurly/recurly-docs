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

* <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_external_products" target="_blank">List all External Products by Site</a>.
* <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/get_external_product" target="_blank">Fetch an External Product</a>.

## External subscriptions

These endpoints are used to view information about external subscriptions, which are Apple or Google subscriptions that your customers have purchased.

* <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_external_subscriptions" target="_blank">List all External Subscriptions by Site</a>
* <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_account_external_subscriptions" target="_blank">List all External Subscriptions by Account</a>
* <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/get_external_subscription" target="_blank">Fetch an External Subscription</a>

## Entitlements

This endpoint is used to view information about the entitlements granted to a specific customer (aka: account).

* <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_entitlements" target="_blank">List Entitlements granted to an Account</a>

**For a complete list of the endpoints specific to App Management**, start at <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_external_subscriptions" target="_blank">External Subscription</a> and scroll down.

# Webhooks

For pertinent events in the subscription lifecycle, Recurly triggers a webhook. This allows you to take any subsequent action (e.g., e-mail your customer) based on that webhook notification.

> 👍 **Important:**
>
> **Webhooks** can be configured via the Recurly Admin UI and **cannot be configured via API.**

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

| Recurly Event                        | Apple Event                                                                        | Google Event                           |
| ------------------------------------ | ---------------------------------------------------------------------------------- | -------------------------------------- |
| canceled                             | DID\_CHANGE\_RENEWAL\_STATUS > AUTO\_RENEW\_DISABLED                               | SUBSCRIPTION\_CANCELED                 |
| consumption\_requested               | CONSUMPTION\_REQUEST                                                               | N/A                                    |
| created (i.e., new subscription)     | SUBSCRIBED > INITIAL\_BUY                                                          | SUBSCRIPTION\_PURCHASED                |
| downgraded                           | DID\_CHANGE\_RENEWAL\_PREF > DOWNGRADE                                             | N/A                                    |
| downgrade\_canceled                  | DID\_CHANGE\_RENEWAL\_PREF                                                         | N/A                                    |
| expired                              | EXPIRED > VOLUNTARY\<br>EXPIRED > BILLING\\\_RETRY\<br>EXPIRED > PRICE\\\_INCREASE | SUBSCRIPTION\_EXPIRED                  |
| extended\_renewal                    | RENEWAL\_EXTENDED                                                                  | SUBSCRIPTION\_DEFERRED                 |
| failed\_renewal                      | DID\_FAIL\_TO\_RENEW                                                               | SUBSCRIPTION\_ON\_HOLD                 |
| failed\_renewal\_with\_grace\_period | DID\_FAIL\_TO\_RENEW > GRACE\_PERIOD                                               | SUBSCRIPTION\_IN\_GRACE\_PERIOD        |
| grace\_period\_expired               | GRACE\_PERIOD\_EXPIRED                                                             | N/A                                    |
| pause\_schedule\_changed             | N/A                                                                                | SUBSCRIPTION\_PAUSE\_SCHEDULE\_CHANGED |
| paused                               | N/A                                                                                | SUBSCRIPTION\_PAUSED                   |
| plan\_changed                        | N/A                                                                                | SUBSCRIPTION\_PURCHASED                |
| price\_change\_confirmed             | N/A                                                                                | SUBSCRIPTION\_PRICE\_CHANGE\_CONFIRMED |
| reactivated                          | DID\_CHANGE\_RENEWAL\_STATUS > AUTO\_RENEW\_ENABLED                                | SUBSCRIPTION\_RESTARTED                |
| recovered                            | N/A                                                                                | SUBSCRIPTION\_RECOVERED                |
| refunded                             | REFUND                                                                             | N/A                                    |
| refund\_declined                     | REFUND\_DECLINED                                                                   | N/A                                    |
| refund\_reversed                     | REFUND\_REVERSED                                                                   | N/A                                    |
| renewed                              | DID\\\_RENEW\<br>DID\\\_RENEW > BILLING\\\_RECOVERY                                | SUBSCRIPTION\_RENEWED                  |
| resubscribed                         | SUBSCRIBED > RESUBSCRIBE                                                           | N/A                                    |
| resubscribed\_incorrect\_account     | SUBSCRIBED > RESUBSCRIBE                                                           | N/A                                    |
| revoked                              | N/A                                                                                | SUBSCRIPTION\_REVOKED                  |
| upgraded                             | DID\_CHANGE\_RENEWAL\_PREF > UPGRADE                                               | N/A                                    |
| voided                               | N/A                                                                                | SUBSCRIPTION\_VOIDED                   |

## Viewing triggered webhooks

All triggered webhooks are viewable within Recurly by navigating to **Integrations -> Webhooks**. In addition, when viewing the details of an Account or External Subscription, there is a link for Webhooks that will take you to a filtered view of the triggered webhooks.