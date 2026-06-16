---
title: Using Gateway Tokens and External NTIDs with Recurly APIs
excerpt: >-
  Merchants who are self-importing or running CIT transactions through a point
  of sale system or other external means can provide Recurly with the original
  NTID for use with future renewals.
deprecated: false
hidden: false
metadata:
  robots: index
next:
  description: >-
    Now that you know how to create new accounts, and future-dated
    subscriptions, take a look at the Subscription Management guide to learn
    more about how to manage the subscription changes after the initial
    purchase.
---
# Overview

This guide is intended to walk you through the process of creating **future dated subscriptions** using a “reusable gateway token” or a reference to payment details from one of our supported gateway partners and an external NTID.

> 📘 Feature Flag and API Requirement
>
> Please note, this only functions in our V3 API with a special feature flag. Reach out to support to enable this feature flag.

You may be reading this guide due to a recent migration from a different payment provider, or you have a third party integration where you generate payment tokens and customer-initiated transactions with your gateway and want to set up subscriptions or customer accounts on Recurly with those tokens and resulting NTIDs.

External payment implementations can capture customer data through a physical payment terminal or other means and then develop and integration to Recurly to send the resulting gateway token and Network Transaction ID via API for future dated renewals where Recurly is not involved in the initial signup process.

Before continuing with this guide, it’s recommended that you have completed the Quickstart Guide first.
In this guide, we’ll be using the Accounts and Subscription endpoints of Recurly API, powerful endpoints designed to back signup and onboarding experiences. With these endpoints, you have the flexibility to create accounts and subscriptions with an external NTID for a future dated renewal.

A subscription request can contain several different resources, but we’ll focus on the account references, gateway\_token (legacy), gateway\_code and network\_transaction\_id  parameters in this guide.

Since `gateway_code` may be deprecated in the future, using `payment_gateway_references.token` is preferred.

## Limitations

### Supported Gateways

- FreedomPay
- Adyen
- Commerce Hub
- Braintree
- Stripe

### Supported Endpoints

Currently we only support this in the `/subscriptions` and `/purchases` endpoint when adding future-dated subscriptions.

### Supported Behaviors&#x20;

When using the Payment gateway references array, billing info updates are not yet supported. You must _delete billing info and re-add_.&#x20;**&#x20;**

### Required Feature Flags

This step is incredibly important, as the network transaction ID field cannot be passed without this feature flag enabled.

- **Allow NTIDs in APIs**

This flag is important to allow Recurly to update meta-data on tokens so we can understand the card brand, display the correct BIN (first 6) and Last 4 of card data, and show the accurate payment method and expiration date if applicable.

- **Enables Backfilling External Tokens**

## Step 1: Gather Required Information for using a Gateway Token

For this portion of the guide, you’ll assess your current implementations that are external to Recurly and identify how you can obtain your gateway tokens from your gateway provider or previous subscription provider. This step will be specific to your business practices and historical integrations. The goal here is to ensure you have access to the correct tokens and data so that you can send them to Recurly properly.

For customers who are integrated with a Point of Sale system with a supported gateway, Recurly will require an NTID passed in with the gateway token and subscription addition when adding or updating billing information and subscriptions.

**Note**: The NTID does not need to be sent for every transaction – we will store it on file for future reference. If you are not using gateway tokens or a POS system for future dated subscriptions or importing, you do not need to pass us an NTID on subscription additions.

<br />

| Parameter                                                | Value                                                                                                                                                         | Description                                                                                                                                                                                                                                                                                                                                |
| :------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `billing_info.gateway_token`                             | **String.&#x20;**&#x54;his will be the gateway token itself.                                                                                                  | **String**. Child of billing\_info. An identifier for the given gateway’s payment method token. Must be used in conjunction with gateway\_code and in some cases account\_reference and network\_transaction\_id. **Legacy usage only. This field does not support Stripe tokens.**                                                        |
| `billing_info.payment_gateway_references.token`          | **String.&#x20;**&#x54;his will be the gateway token itself.                                                                                                  | **String**. Child of billing\_info. An identifier for the given gateway’s payment method token. Must be used in conjunction with gateway\_code and in some cases account\_reference and network\_transaction\_id.  **Go-forward parameter. Use for all gateways. Certain gateways also require the&#x20;**`reference_type` value (Stripe). |
| `billing_info.payment_gateway_references.reference_type` | **String.&#x20;**&#x54;his will be the gateway token type. Options: `stripe_payment_method` or `stripe_customer`                                              | **String**. Child of billing\_info. An identifier for the given gateway’s payment method token. Must be used in conjunction with gateway\_code and the token.  **Go-forward parameter. Use for all gateways. Required for Stripe.**                                                                                                        |
| `billing_info.gateway_code`                              | **String.&#x20;**&#x59;our gateway code.                                                                                                                      | **String**. Child of billing\_info. An identifier for a specific payment gateway. Must be used in conjunction with `gateway_token`.                                                                                                                                                                                                        |
| `billing_info.gateway_attributes.account_reference`      | **String.&#x20;**&#x54;he Adyen Shopper reference ID. Omit when not using Adyen.                                                                              | **String**. Child of billing\_info/gateway\_attributes. Required when using **Adyen** Tokens, and should contain the shopper reference ID.                                                                                                                                                                                                 |
| `billing_info_id`                                        | **String.&#x20;**&#x59;our billing info Id.                                                                                                                   | **String**. Billing Info ID for the account. This required.                                                                                                                                                                                                                                                                                |
| `network_transaction_id`                                 | **String**. The NTID returned to you in the point of sale transaction, where your customer authorized the subscription via card-present terminal interaction. | **String**. The network transaction ID associated with the subscription or billing information (token) where required. Must be passed in when using a gateway that does not handle NTIDs on their own when using a gateway token.                                                                                                          |
| `starts_at`                                              | **Date.&#x20;**&#x54;he date you want the renewal to start billing in the future.                                                                             | **String**. Date/time of the future renewal. This field is incredibly important. If omitted, a transaction will be attempted.                                                                                                                                                                                                              |

## Step 2: Create an Account and Store Billing Info ID

Next, we’ll make a request to the accounts endpoint, passing in the customer account and billing information (using the gateway token from above). Learn more about accounts in our dedicated documentation.
It’s recommended, at this point, to store the billing info ID for the next step, as it is a required element.

```json
{
    "code": "account-code",
    "email": "johndoe@example.comm",
    "preferred_locale": "en-US",
    "preferred_time_zone": "America/Chicago",
    "billing_info": {
        "first_name": "John",
        "last_name": "Rambo",
        "address": {
            "phone": "1234567890",
            "street1": "23 Recurly Ave",
            "city": "Chicago",
            "region": "IL",
            "postal_code": "60601",
            "country": "US"
        },
      "gateway_attributes":{
        "account_reference":"adyen-shopper-reference" // Only send for Adyen
      },

        "gateway_token":"token-here" // Deprecated Parameter
    }
}

```

**Note:** In place of the gateway\_token parameter you may pass the `payment_gateway_references.token` value instead if your gateway supports a one to one field exchange.&#x20;

```json
"payment_gateway_references": [{
	"token": "gateway-token-here",
}]
```

**If you are using Stripe**, you must provide the `reference_type` object and there will be two objects in the `payment_gateway_references` array like so:&#x20;

```json
{
"payment_gateway_references": [
        {
            "token": "pm_xxxxxxxxxx",
            "reference_type": "stripe_payment_method"
        },
        {
            "token": "cus_xxxxxxxxxx",
            "reference_type": "stripe_customer"
        }
    ]
}
```

## Examples of Each Gateway&#x20;

```json Adyen 
{
  "gateway)attributes": {
    "account_reference": "adyen-shopper-reference"
  },
  "gateway_token": "adyen-recurring-detail-reference",
  "gateway_code": "recurly-gateway-code"
}

// OR 

{
  "gateway)attributes": {
    "account_reference": "adyen-shopper-reference"
  },
  "payment_gateway_references": [
    {
      "token": "adyen-recurring-detail-reference"
    }
  ],
  "gateway_code": "recurly-gateway-code"
}
```
```json Stripe
{
  "payment_gateway_references": [
    {
      "token": "stripe-payment-method-id",
      "reference_type": "stripe_payment_method"
    },
    {
      "token": "stripe-customer-id",
      "reference_type": "stripe_customer"
    }
  ],
  "gateway_code": "recurly-gateway-code"
}
```
```json Braintree
{
  "gateway_token": "braintree-legacy-tokene",
  "gateway_code": "recurly-gateway-code"
}

// OR 

{
  "payment_gateway_references": [
    {
      "token": "braintree-legacy-token",
    }
  ],
  "gateway_code": "recurly-gateway-code"
}
```
```json FreedomPay
{
  "gateway_token": "freedompay-token",
  "gateway_code": "recurly-gateway-code"
}

// OR 

{
  "payment_gateway_references": [
    {
      "token": "freedompay-token"
    }
  ],
  "gateway_code": "recurly-gateway-code"
}
```
```json Commerce Hub
...
"gateway_token":"transarmor-token",
"gateway_code":"recurly-gateway-code"
...
}

// OR 

...
"payment_gateway_references":[{
  "token":"transarmor-token"
	}],
"gateway_code":"recurly-gateway-code"
...
}
```

After submitting this step, store the resulting `billing-info-id`. You will need it for the next step. If you do not have the `billing-info-id` value, query the account to get it.&#x20;

You can use the [Fetch Account endpoint](https://recurly.com/developers/api/v2021-02-25/#operation/get_account) to accomplish this.&#x20;

## Step 3: Create a Subscription Request

Next, we’ll make a request to the subscription endpoint, passing in the customer account and billing information (using the gateway token from above), along with one or more subscription plan codes. In the example below, one subscription is generated using the plan code created in the Quickstart Guide.

It’s recommended, at this point, to already have an account ready to pass in and billing information added, as you will need to provide the billing info ID to associate the NTID with.

Updating an existing subscription is not supported at this time.

**Endpoint**: `/subscriptions`

If you are using the `/purchases` endpoint, the logic is much the same, though the payload is slightly different.

```json JSON
{
    "currency": "USD",
      "account": {
 	    "code": "account-code",
      },
    "billing_info_id":"123456789", // Required Field
    "plan_code": "monthly",
    "starts_at": "2026-12-30T14:15:22Z", // Must be a future date
    "network_transaction_id": "320036244781105" // NTID from a Customer Initiated Transaction
}
```

**Endpoint**: `/purchases`

```json
{
    "currency": "USD",
    "account": {
        "code":"account-code"
    },
    "billing_info_id": "123456789", // Required Field
    "subscriptions": [{
      "plan_code": "monthly",
      "starts_at":"2026-12-15T14:15:22Z" // Future date
    }
	],
    "gateway_code":"gateway-code",
    "network_transaction_id": "320036244781105" // NTID from a Customer Initiated Transaction
}
```

<br />

## Step 4: Verify and Finish

If the subscription addition was successful, you should now be able to access all associated objects that were created as a result. Since this is a future-dated subscription, you will not find a transaction attempt for this subscription.

You can verify through the API or the admin console that no purchase occurred, and that a subscription exists for this customer.

<br />
