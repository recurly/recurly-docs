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

### Step 2: Obtain the token from the response

Upon submitting your API request you will receive a response that looks like this:

```text
TBD -- token response handling 
```

PayPay requires consumer authentication, and so interacting with Recurly.js is necessary to allow consumers to authenticate their identity and authorize payments in their mobile apps. You will need to use the `three_d_secure_action_token_id` value to render the modal for this process.

### Step 3: Interact with Recurly.js

You can follow along in our Redirect Guide, starting at Step 3: [Recurly.js Token-ID Redirect Guide](https://docs.recurly.com/recurly-subscriptions/docs/3d-secure-20-integration-guide#/step-3-process-the-responsew)

### Step 4: Resubmit the Purchase request with the Action Result Token

Once the user has interacted with the modal, and you will receive a `three_d_secure_action_result_token_id` from Recurly.js, you must resubmit your original request with the results token ID.

Use the `three_d_secure_action_result_token_id` from Step 3 in a new API call (e.g., Create Purchase) to finalize authentication. The account/billing info must match the original request. Changing these details may cause a token mismatch error.

Your JSON payload may look like this:

```text
{
    "subscriptions": [
		{
			"plan_code": "monthly-plan" 

		}
	],
    "account": {
        "code": "miyamoto",
        "email":"miyamotosan@example.com",
        "billing_info": {
            "first_name":"Shigeru",
            "last_name":"Miyamoto",
            "address":{
                "street1":"Sunshine Building 4022-3-4 Kabukicho",
                "city":Tokyo",
                "region":"Tokyo-to",
                "postal_code":"〒100-8994",
                "country":"JP",
                "phone":"+81-70-123-1234"
            },
            "three_d_secure_action_result_token_id":"action-result-id"
        }
    },
    "currency": "JPY"
}
```
