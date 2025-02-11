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

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Recurly Event
      </th>

      <th style={{ textAlign: "left" }}>
        Apple Event
      </th>

      <th style={{ textAlign: "left" }}>
        Google Event
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        canceled
      </td>

      <td style={{ textAlign: "left" }}>
        DID\_CHANGE\_RENEWAL\_STATUS > AUTO\_RENEW\_DISABLED
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_CANCELED
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        consumption\_requested
      </td>

      <td style={{ textAlign: "left" }}>
        CONSUMPTION\_REQUEST
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        created (i.e., new subscription)
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIBED > INITIAL\_BUY
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_PURCHASED
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        downgraded
      </td>

      <td style={{ textAlign: "left" }}>
        DID\_CHANGE\_RENEWAL\_PREF > DOWNGRADE
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        downgrade\_canceled
      </td>

      <td style={{ textAlign: "left" }}>
        DID\_CHANGE\_RENEWAL\_PREF
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        expired
      </td>

      <td style={{ textAlign: "left" }}>
        EXPIRED > VOLUNTARY\
        EXPIRED > BILLING\_RETRY\
        EXPIRED > PRICE\_INCREASE
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_EXPIRED
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        extended\_renewal
      </td>

      <td style={{ textAlign: "left" }}>
        RENEWAL\_EXTENDED
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_DEFERRED
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        failed\_renewal
      </td>

      <td style={{ textAlign: "left" }}>
        DID\_FAIL\_TO\_RENEW
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_ON\_HOLD
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        failed\_renewal\_with\_grace\_period
      </td>

      <td style={{ textAlign: "left" }}>
        DID\_FAIL\_TO\_RENEW > GRACE\_PERIOD
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_IN\_GRACE\_PERIOD
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        grace\_period\_expired
      </td>

      <td style={{ textAlign: "left" }}>
        GRACE\_PERIOD\_EXPIRED
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        pause\_schedule\_changed
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_PAUSE\_SCHEDULE\_CHANGED
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        paused
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_PAUSED
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        plan\_changed
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_PURCHASED
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        price\_change\_confirmed
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_PRICE\_CHANGE\_CONFIRMED
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        reactivated
      </td>

      <td style={{ textAlign: "left" }}>
        DID\_CHANGE\_RENEWAL\_STATUS > AUTO\_RENEW\_ENABLED
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_RESTARTED
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        recovered
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_RECOVERED
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        refunded
      </td>

      <td style={{ textAlign: "left" }}>
        REFUND
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        refund\_declined
      </td>

      <td style={{ textAlign: "left" }}>
        REFUND\_DECLINED
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        refund\_reversed
      </td>

      <td style={{ textAlign: "left" }}>
        REFUND\_REVERSED
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        renewed
      </td>

      <td style={{ textAlign: "left" }}>
        DID\_RENEW\
        DID\_RENEW > BILLING\_RECOVERY
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_RENEWED
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        resubscribed
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIBED > RESUBSCRIBE
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        resubscribed\_incorrect\_account
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIBED > RESUBSCRIBE
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        revoked
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_REVOKED
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        upgraded
      </td>

      <td style={{ textAlign: "left" }}>
        DID\_CHANGE\_RENEWAL\_PREF > UPGRADE
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        voided
      </td>

      <td style={{ textAlign: "left" }}>
        N/A
      </td>

      <td style={{ textAlign: "left" }}>
        SUBSCRIPTION\_VOIDED
      </td>
    </tr>
  </tbody>
</Table>

## Viewing triggered webhooks

All triggered webhooks are viewable within Recurly by navigating to **Integrations -> Webhooks**. In addition, when viewing the details of an Account or External Subscription, there is a link for Webhooks that will take you to a filtered view of the triggered webhooks.
