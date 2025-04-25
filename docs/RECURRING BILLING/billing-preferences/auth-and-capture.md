---
title: Authorization and capture
excerpt: >-
  Seamlessly Authorize and Capture your subscriber's payment details with
  Recurly, ensuring a smooth and efficient transaction process.
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

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

* Integration with Recurly's API or select client libraries.
* Recurly's Authorization and Capture feature is compatible with several credit card gateways, including Braintree, Stripe, Adyen, PayPal Complete, Cybersource, Authorize.net, and CardConnect. Additional gateways will be integrated based on merchant demand.

### Limitations

* No support for "partial captures" or "multiple captures."
* Cannot capture more than the authorized amount.
* Recurly does not automatically authorize cards before recurring subscription renewals.
* Delayed capture is not customizable.
* Some features, like Auth and Capture, are not fully supported with 3rd party integrations such as Xero or Quickbooks Online.

# Definition

Recurly's "Authorization and Capture" feature allows merchants to initially authorize a subscriber's credit card to ensure its validity and fund availability. Subsequently, merchants can capture the funds at a later, more suitable time.

# Key benefits

* **Enhanced payment security**: Authorize credit cards to ensure legitimacy and fund sufficiency before capturing.
* **Flexible transaction management**: Capture funds when it's most convenient, optimizing cash flow and customer relations.
* **Efficient error handling**: Quickly identify and rectify payment issues, reducing transaction failures.

## Benefits of authorizing first

By authorizing before capturing, merchants can:

* Ensure product availability before capturing funds for physical goods.
* Conduct manual fraud reviews prior to fund capture and order fulfillment.
* Authorize at the start of a free trial and capture funds at the subscription's start.

# Key details

## Authorization and capture

Recurly’s "Authorization and Capture" functionality enables merchants to first validate a subscriber's credit card for legitimacy and fund availability. Once verified, merchants can capture the due amount at their convenience.

## Definitions

* **Authorize**: A preliminary check with the subscriber's bank to validate the credit card's legitimacy and ensure sufficient funds. This places a hold on the funds but doesn't transfer them.

* **Capture**: Post-authorization, this step collects the funds from the subscriber's account, completing the transaction.

* **Cancel**: If funds aren't captured, this step releases the hold on the subscriber's account.

### Auth and Capture Flow

#### Part 1: Initiating authorization

* **Step 1**: Access Recurly's API or select client libraries.
* **Step 2**: Submit a POST request to `v2/purchases/authorize` OR `v3/purchases/authorize` (based on your current API version).
* **Step 3**: Ensure the transaction details are correctly entered.

#### Part 2: Capturing the authorized amount

* **Step 1**: To capture an authorized transaction, use the `/capture` endpoint.
* **Step 2**: Include the transaction UUID from the original authorization: `v2/purchases/transaction-uuid-<AUTHORIZED-TXN-UUID-HERE>/capture`or `v3/purchase/{transaction_id}/capture`flow depending on your version.

#### Part 3: Canceling the authorization

* **Step 1**: If you decide not to capture the funds, use the `/cancel` endpoint.
* **Step 2**: Include the transaction UUID from the original authorization: `v2/purchases/transaction-uuid-<AUTHORIZED-TXN-UUID-HERE>/cancel`or `v3/purchase/{transaction_id}/cancel`, again depending on your version in use.

**For V2 Implementations**: You can find all documentation for [V2 Authorize](https://recurly.com/developers/api-v2/v2.29/#operation/authorizePurchase), [V2 Capture](https://recurly.com/developers/api-v2/v2.29/#operation/capturePurchase) and [V2 Cancel](https://recurly.com/developers/api-v2/v2.29/#operation/cancelPurchase) documentation in Recurly's developer hub.

**For V3 Implementations**: You can find [V3 Authorize](https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_authorize_purchase), [V3 Capture](https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_capture_purchase) and [V3 Cancel](https://recurly.com/developers/api/v2021-02-25/index.html#operation/cancelPurchase) as well in the [latest V3 documentation](https://recurly.com/developers/api/v2021-02-25/index.html).