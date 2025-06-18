---
title: Stripe
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
#### Metadata description

<br />

Configuration guide for the Stripe connector in Recurly Engage—activation, data sync, 1-Click actions, and subscription management.

<br />

# Overview

<br />

The **Stripe** integration lets you manage subscriptions, trials, coupons, and usage-based workflows directly from Recurly Engage prompts by connecting to your Stripe account.

<br />

### Required plan

<br />

This feature or setting is available to all customers on any Recurly Engage subscription plan.

<br />

### Prerequisites & limitations

<br />

* Company or App Administrator permissions in Recurly Engage.
  * A Stripe account with API access credentials and webhook capability.
    * Users in Recurly Engage must have `stripe_id` or `email_address` traits for action targeting and webhook syncing.
      <br />

# Definition

<br />

The **Stripe** connector offers two activation methods—Stripe Connect or API Key—and supports real-time and nightly data syncs, plus 1-Click billing actions from prompts.

<br />

# Key benefits

<br />

* **Flexible activation**: Choose OAuth-based Stripe Connect or API Key authentication.
  * **Real-time updates**: Webhook-driven trait sync for subscription status and billing events.
    * **Comprehensive actions**: Upgrade, extend trials, apply coupons, and manage subscriptions without leaving prompts.
      <br />

# Key details

<br />

<br />

## Activation

<br />

You may activate the Stripe connector utilizing one of two methods: Stripe Connect or API Key. Stripe Connect allows integration with Recurly Engage by authenticating with an existing Stripe user account. Alternatively, you may opt to generate a new API Key.

<br />

### Option 1: Stripe Connect

<br />

Visit **Settings → Actions → Stripe** and click the following button to authenticate via Stripe.com.

<Image align="center" src="https://files.readme.io/c2a06fc-Stripe_Connect.png" />

<br />

### Option 2: API Key

<br />

In the Stripe Dashboard, navigate to **Developers → API Keys**. Create a new **Restricted Key** and grant these permissions:

<Image align="center" src="https://files.readme.io/3020621-Stripe_key.png" />

| Resource Type   | Permissions | Connect Permissions |
| --------------- | ----------- | ------------------- |
| Customers       | Write       | None                |
| Subscriptions   | Write       | None                |
| Products        | Read        | None                |
| Prices          | Read        | None                |
| Coupons         | Read        | None                |
| Promotion Codes | Read        | None                |

Finally, copy the generated API key into the **Settings → Actions → Stripe** form in Recurly Engage.

<br />

## Data Integration

<br />

<br />

### 1-Click Actions

<br />

After activation, available Plans and Coupons sync periodically for use in prompts. Ensure each user record includes `stripe_id` or `email_address`.

<br />

### Automated Data Sync

When using Stripe Connect, a webhook is created to sync subscription events in real time. Traits imported include:

| Trait Name                 | Values                                                                                                         |
| :------------------------- | :------------------------------------------------------------------------------------------------------------- |
| `subscription_status`      | `incomplete`, `incomplete_expired`, `trialing`, `active`, `past_due`, `canceled`, `unpaid`, `paused` or `NONE` |
| `delinquent`               | `true`, `false` (set to `true` when a payment fails)                                                           |
| `current_period_start`     | \<Start date of current billing period>                                                                        |
| `current_period_end`       | \<End date of current billing period>                                                                          |
| `canceled_at`              | \<Date of cancellation>                                                                                        |
| `cancel_at_period_end`     | `true`, `false`                                                                                                |
| `trial_start`              | \<Start date of trial>                                                                                         |
| `trial_end`                | \<End date of trial>                                                                                           |
| `subscription_plan`        | \<Name of current or most recent subscription plan>                                                            |
| `recurring_interval`       | `day`, `week`, `month`, `year`                                                                                 |
| `coupon`                   | \<Coupon name>                                                                                                 |
| `payment_card_brand`       | `<card brand>` (e.g., `visa`, `mastercard`, `amex`, `unknown`)                                                 |
| `payment_card_country`     | `<country code>` (2-character ISO)                                                                             |
| `payment_card_expiration`  | \<Payment card expiration date>                                                                                |
| `payment_card_wallet_type` | `<wallet type>` (e.g., `apple_pay`, `google_pay`, etc.)                                                        |

*Note: You must also perform a nightly CSV sync mapping your internal user IDs to Stripe Customer IDs.*

## Supported Actions

Attach these 1-Click actions to prompt interactions once your data sync is active:

| Action                       | Description                        | User Dependencies              | Additional Instructions                  |
| ---------------------------- | ---------------------------------- | ------------------------------ | ---------------------------------------- |
| Update existing subscription | Switch user to a different product | `stripe_id` or `email_address` | Multiple proration options available—see |

<br />

## Additional Information

<br />

* [Stripe API Key Setup](https://docs.stripe.com/keys)
  * [Stripe Proration Guide](https://stripe.com/docs/billing/subscriptions/upgrade-downgrade#proration)