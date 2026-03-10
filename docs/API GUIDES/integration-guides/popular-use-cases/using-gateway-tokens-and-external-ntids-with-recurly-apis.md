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

A subscription request can contain several different resources, but we’ll focus on the account references, gateway_token (legacy), gateway_code and network_transaction_id  parameters in this guide.

Since `gateway_code` may be deprecated in the future, using `payment_gateway_references.token` is preferred.

## Limitations

### Supported Gateways

* FreedomPay
* Adyen
* Commerce Hub
* Braintree

### Supported Endpoints

Currently we only support this in the `/subscriptions` and `/purchases` endpoint when adding future-dated subscriptions.

### Required Feature Flags

This step is incredibly important, as the network transaction ID field cannot be passed without this feature flag enabled.

* **Allow NTIDs in APIs**

## Step 1: Gather Required Information for using a Gateway Token

For this portion of the guide, you’ll assess your current implementations that are external to Recurly and identify how you can obtain your gateway tokens from your gateway provider or previous subscription provider. This step will be specific to your business practices and historical integrations. The goal here is to ensure you have access to the correct tokens and data so that you can send them to Recurly properly.

For customers who are integrated with a Point of Sale system with a supported gateway, Recurly will require an NTID passed in with the gateway token and subscription addition when adding or updating billing information and subscriptions.

**Note**: The NTID does not need to be sent for every transaction – we will store it on file for future reference. If you are not using gateway tokens or a POS system for future dated subscriptions or importing, you do not need to pass us an NTID on subscription additions.

<br />

| Parameter                                           | Description                                                                                                                                                                                                                             |
| :-------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `billing_info.gateway_token`                        | **String**. Child of billing_info. An identifier for the given gateway’s payment method token. Must be used in conjunction with gateway_code and in some cases account_reference and network_transaction_id. **Legacy usage only.**     |
| `billing_info.payment_gateway_references.token`     | **String**. Child of billing_info. An identifier for the given gateway’s payment method token. Must be used in conjunction with gateway_code and in some cases account_reference and network_transaction_id.  **Go-forward parameter.** |
| `billing_info.gateway_code`                         | **String**. Child of billing_info. An identifier for a specific payment gateway. Must be used in conjunction with `gateway_token`.                                                                                                      |
| `billing_info.gateway_attributes.account_reference` | **String**. Child of billing_info/gateway_attributes. Required when using Adyen Tokens, and should contain the shopper reference ID.                                                                                                    |
| `billing_info_id`                                   | **String**. Billing Info ID for the account. This required.                                                                                                                                                                             |
| `network_transaction_id`                            | **String**. The network transaction ID associated with the subscription or billing information (token) where required. Must be passed in when using a gateway that does not handle NTIDs on their own when using a gateway token.       |
| `starts_at`                                         | **String**. Date/time of the future renewal. This field is incredibly important. If omitted, a transaction will be attempted.                                                                                                           |

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
        "gateway_token":"token-here" // Deprecated Parameter
    }
}

```

**Note:** In place of the gateway_token parameter you may pass the `payment_gateway_references.token` value instead.

```json
"payment_gateway_references": [{
	"token": "gateway-token-here",
}]
```

## Step 3: Create a Subscription Request

Next, we’ll make a request to the subscription endpoint, passing in the customer account and billing information (using the gateway token from above), along with one or more subscription plan codes. In the example below, one subscription is generated using the plan code created in the Quickstart Guide.

It’s recommended, at this point, to already have an account ready to pass in and billing information added, as you will need to provide the billing info ID to associate the NTID with.

Updating an existing subscription is not supported at this time.

**Endpoint**: `/subscriptions`

```json
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

If you are using the `/purchases` endpoint, the logic is much the same, though the payload is slightly different.

**Endpoint**: `/purchases`

```json
{
    "currency": "USD",
    "account": {
        "code":"account-code"
    },
    "billing_info_id": "123456789", // Required Field
	  "subscriptions": [
		{
			"plan_code": "monthly",
            "starts_at":"2026-12-15T14:15:22Z" // Must be a future date
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
