---
title: Recurly Recover
excerpt: >-
  Retry failed invoice collection independently of your billing platform using
  Recurly Recover — a flexible, API-driven dunning engine with support for
  Vindicia and A/B testing.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature may not be included in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Additional cost

This feature requires an additional cost. Please reach out to your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) for more pricing details.

### Prerequisites

* Generate an API key for an active Recurly account
* Configure a supported payment gateway; Recurly Recover currently supports [Stripe](https://docs.recurly.com/recurly-subscriptions/docs/stripe) and [Braintree](https://docs.recurly.com/recurly-subscriptions/docs/braintree-rd)
* Configure dunning campaigns and dunning emails in the Recurly Admin UI
* For Vindicia integration, configure Vindicia credentials and token options on the Vindicia Retain page in Recurly

### Limitations

* Recurly Recover is not intended to be combined with Recurly's full subscription management product
* Account creation is only available via API and cannot be done through the Admin UI
* Each successful API call creates one account with one invoice; calling the API with an existing account code returns an error
* Only Stripe and Braintree are supported as payment gateways at this time
* Only one payment method can be designated as primary and one as backup per account

***

# Definition

Recurly Recover is a standalone retry engine that lets you collect on failed invoices without using Recurly as your primary subscription management or billing platform. It is built for merchants who need a dedicated dunning engine that works independently of the rest of Recurly's infrastructure.

When you submit a past due invoice via API, Recurly creates a shell account, creates a past due invoice with a corresponding failed transaction, and stores the provided payment methods. Recurly then calculates a retry schedule and manages collection until the invoice is paid or the dunning campaign is exhausted.

> **Note:** There is no need to create or configure plans, items, currencies, or taxes. Setup is limited to what's described in the Prerequisites above.

***

# Key benefits

* **Independent of your billing stack:** Use Recurly Recover without using Recurly for subscription management. Recurly Recover integrates with your existing infrastructure and is self-serve.
* **Flexible dunning campaign control:** Assign dunning campaigns per API request to test different retry windows and strategies.
* **Vindicia integration support:** If you're integrated with Vindicia, Recurly can hand off retry attempts at a configurable point in the dunning campaign.

***

# Key details

## How it works

The recovery API is the entry point into Recurly Recover. When a request succeeds, Recurly creates an account with a past due invoice, a corresponding failed transaction, and any other relevant account-level objects.

**Path:** `/invoices/recovery`

**Request:**

```json
{
  "currency": "str",
  "due_at": "2019-08-24T14:15:22Z",
  "po_number": "string",
  "external_recovery_eligible": true,
  "account": {
    "address": {
      "phone": "string",
      "street1": "string",
      "street2": "string",
      "city": "string",
      "region": "string",
      "postal_code": "string",
      "country": "string"
    },
    "billing_infos": [
      {
        "first_name": "string",
        "last_name": "string",
        "company": "string",
        "address": {
          "phone": "string",
          "street1": "string",
          "street2": "string",
          "city": "string",
          "region": "string",
          "postal_code": "string",
          "country": "string"
        },
        "ip_address": "string",
        "gateway_code": "string",
        "primary_payment_method": true,
        "backup_payment_method": true,
        "payment_gateway_references": [
          {
            "token": "string",
            "reference_type": "stripe_confirmation_token"
          }
        ],
        "network_transaction_id": "string",
        "transactions": [
          {
            "gateway_error_code": "string",
            "merchant_advice_code": "st",
            "attempted_collection_date": "2019-08-24T14:15:22Z"
          }
        ]
      }
    ],
    "code": "string",
    "email": "user@example.com",
    "custom_fields": [
      {
        "name": "string",
        "value": "string"
      }
    ],
    "dunning_campaign_id": "string"
  },
  "line_items": [
    {
      "tax": 0,
      "custom_fields": [
        {
          "name": "string",
          "value": "string"
        }
      ],
      "harmonized_system_code": "string",
      "product_code": "string",
      "quantity": 1,
      "description": "string",
      "unit_amount": 0
    }
  ]
}
```

***

## Retry and collection flow

Recurly calculates the next collection attempt date from the data in the API request. The retry process follows this logic:

* If collection succeeds at any point, the invoice is marked as **Paid** and a webhook event is fired
* If the first attempt fails, Recurly continues retrying for the length of the specified dunning campaign
* If no dunning campaign is provided, Recurly uses your site's default campaign
* If the campaign is exhausted without a successful collection, the invoice is marked as **Failed** and a webhook event is fired

While an invoice is in a Past Due state, you can cancel future collection attempts by marking the invoice as Failed or Paid using the [Recurly Invoice API](https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_account_invoices).

***

## Dunning campaigns and emails

Dunning campaigns can have different lengths. Pass a dunning campaign ID in the API request to set the retry period for that invoice. Because each request can specify a different campaign, you can run A/B tests across retry strategies.

Each dunning campaign includes dunning emails by default. If you're managing dunning-related communications through your own system, you can remove emails from individual campaigns or disable them in **Email Templates**.

***

## Wallet

When the Wallet feature is enabled, payment methods are designated as primary or backup based on the API request. You can submit multiple payment methods, but only one can be primary and one can be backup.

***

## Vindicia integration

If you're integrated with Vindicia, Recurly can hand off retry attempts to Vindicia at a configurable point in the dunning campaign. To enable this:

1. Enter your Vindicia credentials on the **Vindicia Retain** page in Recurly
2. Select your token option on the same page
3. Update your dunning campaign's Vindicia retry window

After configuration, Vindicia is notified of the past due invoice based on the retry window set in the associated dunning campaign.

<Image align="center" border={true} width="75%" src="https://files.readme.io/4f74266ccee53a04e7c6be4fff2a4da6237e6d7b41ff7ca3f0c356f2fcf3c6a5-Screenshot_2026-04-21_at_11.56.39_AM.png" className="border" />

### Splitting the dunning window between Recurly and Vindicia

The **collection window in days** setting in your Vindicia Retry Dunning Settings determines how the dunning campaign is split between Recurly and Vindicia.

**Example:** If your dunning campaign is 27 days and the Vindicia retry window is set to 10, Recurly retries for 17 days and then hands off to Vindicia for the remaining 10.

| Vindicia window setting                      | Behavior                                                                      |
| :------------------------------------------- | :---------------------------------------------------------------------------- |
| Set to `0`                                   | Only Recurly retries — Vindicia is not notified                               |
| Set to a value less than the campaign length | Recurly retries first, then Vindicia handles the remainder                    |
| Set equal to the full campaign length        | Recurly does not retry — the past due invoice is sent to Vindicia immediately |

In all cases, Recurly still creates the account and its associated objects. Each dunning campaign can have a unique retry window value. Combined with the ability to pass dunning campaign IDs per API request, this lets you run A/B tests across retry strategies.

***

## Webhooks

Recurly fires webhook events at key points in the collection lifecycle, including when an invoice is marked as Paid or Failed. See the [webhooks documentation](https://docs.recurly.com/recurly-subscriptions/docs/overview-webhooks) for details.

***

# FAQs

**Do I need to use Recurly as my subscription management platform to use Recurly Recover?**

No. Recurly Recover is designed to work independently, so you can retry failed invoice collection even if Recurly isn't your subscription management or billing platform. We don't recommend combining Recurly Recover with Recurly's full subscription management product at this time.

**What happens when a past due invoice is submitted via the API?**

Recurly creates an account (without a subscription), along with a charge, a past due invoice, and one or more failed transactions. Billing information is stored on the account, and Recurly automatically calculates the next collection attempt date based on the data in the request.

**How does the retry process work if I'm also integrated with Vindicia?**

The dunning campaign length is split between Recurly and Vindicia based on the **collection window in days** setting in your Vindicia Retry Dunning Settings. For example, if your campaign is 27 days and the Vindicia window is set to 10, Recurly retries for 17 days and then hands off to Vindicia for the remaining 10.

**Can I stop retry attempts on a past due invoice?**

Yes. While an invoice is in a Past Due state, you can cancel future collection attempts by marking the invoice as Failed or Paid using the [Recurly Invoice API](https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_account_invoices).