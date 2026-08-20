---
title: PayPay integration guide
excerpt: >-
  Create subscriptions via Purchase API using PayPay wallet using Adyen's
  Sandbox environment
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This guide shows you how to use the [Purchase endpoint](https://developers.recurly.com/api/latest/#tag/purchase) to create new subscriptions using the PayPay wallet payment method. We’ll also illustrate how to work with the Adyen sandbox simulator.

### Prerequisites & limitations

- Familiarity with Recurly’s V3 API, Webhooks, and basic REST concepts
- [Completed the Quickstart Guide](https://docs.recurly.com/recurly-subscriptions/docs/quick-start-guide#/)
- Familiarity with Recurly.js&#x20;
- An Adyen gateway account with PayPay enabled with a **SALE** Acquirer setup.
  - If you are using only Auth and Capture, you may do so for one time transactions only. Recurring cannot be supported with an AUTH acquirer setup.
- Your Adyen gateway account is set up to send your Recurly sandbox and/or production site the proper **webhooks** so that **tokens** and **status updates&#x20;**&#x6F;ccur seamlessly. Please see Adyen configuration with Recurly and follow all steps if you have not yet done so.&#x20;
  - If you do not set up proper webhooks, your testing and production behavior will experience significant degradation and errors.

# Definition

**Creating Purchases** refers to the process of generating new customer accounts alongside subscriptions in a single, consolidated call to the Recurly Purchase endpoint. This streamlines checkout experiences by bundling all required resources into one request.

***

# Creating Purchases&#x20;

### Step 1: Generate a PayPay Wallet Payment Request

Use a supported client library and Recurly.js to configure your checkout setup. Our client libraries help you build out our APIs easily and process transactions faster. PayPay uses Recurly.js whether or not you are using our native Recurly.js checkout or Adyen Web Components via Third Party Checkout.

- Send a request to the `create_purchase` method on Recurly’s API, including:
  - Customer account data (e.g., code, name, billing info, phone number, email address)
  - Subscriptions (with plan codes)
  - Recurly.js token&#x20;

```text
TBD
```

### Step 2: Obtain the action result value from the response

You'll receive a redirect blob in `transactions.gateway_response_values.action_result` response.

```json
"action_result": "{\"method\":\"GET\",\"paymentMethodType\":\"paypay\",\"type\":\"redirect\",\"url\":\"https://checkoutshopper-test.adyen.com/checkoutshopper/checkoutPaymentRedirect?redirectData=X3XtfGC9%2...eWteWFSyDxkTo3iXeATHjO%2BxTyV4nnN155A%3D\"}",
```

PayPay requires consumer authentication, and so interacting with Recurly.js is necessary to allow consumers to authenticate their identity and authorize payments in their mobile apps. You will need to submit the action result value to Recurly.js in order to render the modal for this process.

### Step 3: Handle the Action Result using Recurly.js&#x20;

With the action result, `paymentMethod.handleAction(action_result)` can be called. Follow our general [Alternative Payment Methods documentation](https://docs.recurly.com/recurly-subscriptions/docs/boleto-ideal-sofort-and-cashapp) for additional details.&#x20;

This will allow the customer to interact with the PayPay app on their phones.&#x20;

### Reminder

Adyen will return the result of that interaction to Recurly via webhooks, including the final transaction status and the token for renewals, upon approval. Ensure you have your Adyen webhooks enabled properly by following our gateway setup documentation around webhooks.&#x20;

**Minimum required webhooks**: Standard and Token Lifecycle events are critical.
