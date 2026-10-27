---
title: Custom Gateway Routing
excerpt: >-
  Learn how to use Custom gateway routing via our V3 and V2 APIs when performing
  orchestrated routing from your own platform.
deprecated: false
hidden: false
metadata:
  robots: noindex
---
# Overview&#x20;

Custom gateway routing involves using the `gateway_code` parameter intelligently to route your transactions instead of using Recurly's selection logic or set Default a gateway to do so. For example, if your default gateway for credit cards is Stripe, but you want a specific signup transaction to use Braintree, you can pass in the unique ID (the gateway code) of that gateway instance, to bypass defaults, and use the gateway of your choice.&#x20;

Read more about gateway routing in our dedicated overview: [Custom gateway routing](/recurly-subscriptions/docs/custom-gateway-routing-configuration)

## Placement Definitions

Where you place your gateway_code matters. Depending on the effect you want, ensuring that the gateway code is sent appropriately is exceptionally important.

* **In the&#x20;**`billing_info `**object**: Placement here affects the transaction in progress, and will direct the transaction to the gateway_code you send. Sending the `gateway_code` in this object does _not_ control which gateway is used for renewals or trial conversions. This is also where a `backup_gateway_code` can be set.
* **In the Subscription endpoint, top level:&#x20;**&#x50;lacement here affects renewals only, and will not affect the gateway used for the signup transaction.
* **In the Purchase endpoint, within the subscription object:&#x20;**&#x53;imilar to the previous point, this affects where renewals are sent, and does not control the signup gateway used.&#x20;
* **To control both:&#x20;**&#x53;end the `gateway_code` parameter and value in both places. This ensures you get the effect you want, such as signup and renewal or trial conversion continuity on the same gateway, or different if you prefer.&#x20;

**Guides:&#x20;**

* [One time transaction routing](/recurly-subscriptions/docs/one-time-payments-gateway-routing)
* [Trial and Subscription continuity](https://docs.recurly.com/recurly-subscriptions/docs/free-trial-gateway-routing-continuity)
* Backup gateway routing

<br />

<br />