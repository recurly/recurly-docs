---
title: Recurly
deprecated: false
hidden: true
metadata:
  robots: index
---
#### Metadata description

<br />Configuration guide for the Recurly connector in Recurly Engage, including activation, data sync, and 1-Click subscription actions.<br />

# Overview

<br />The **Recurly** integration allows you to sync your subscription data and execute billing actions directly from prompts in Recurly Engage, leveraging your Recurly account.<br />

### Required plan

<br />This feature or setting is available to all customers on any Recurly Engage subscription plan.<br />

### Prerequisites & limitations

<br />- Company or App Administrator permissions in Recurly Engage.
  * A Recurly account with API access and valid API key.
    * If your application uses custom User IDs (Account Codes), enable **Use Account Code** in the connector settings.
      <br />

# Definition

<br />The **Recurly** connector imports subscription traits nightly and provides actions for managing subscriptions—coupon application, plan changes, pauses, resumes—via prompts.<br />

# Key benefits

<br />- **Seamless billing workflows**: Manage subscriptions without leaving the prompt interface.
  * **Real-time data**: Keep segments and prompts in sync with nightly data imports.
    * **Flexible configurations**: Support custom account codes and multiple subscription actions.
      <br />

# Key details

<br /><br />

## Overview

<br />

\<iframe width="712" height="400" src="https\://www\.loom.com/embed/46bc074c2ae84fcd8fd55d7b342859d2?sid=d12f25e0-c01d-4ce7-b63c-a6c26f28f83d" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen>\</iframe>
\`}\</HTMLBlock>





## Activation

<br />1) Generate an **API Key** in the Recurly console.
   2. In Recurly Engage, navigate to **Settings > Integrations > Recurly** and paste your API Key.
      3. Toggle **Use Account Code** to **On** if you map your own user IDs to Recurly Account Codes.
         4. Toggle **Active** to **On**.
            * API Key ([Instructions](https://docs.recurly.com/docs/api-keys) )
              <br />

## Data Integration

to enable the automated sync.

Once enabled, the following traits are imported nightly:

| Trait Name                  | Description                                                                      |
| --------------------------- | -------------------------------------------------------------------------------- |
| `state`                     | Current state of subscription (`pending`, `active`, `canceled`, `expired`)       |
| `plan_code`                 | Plan code the customer is subscribed to                                          |
| `currency`                  | Currency of the subscription                                                     |
| `current_period_started_at` | Date/time when the current billing period starts                                 |
| `current_period_ends_at`    | Date/time when the current billing period ends                                   |
| `trial_started_at`          | Date/time when the trial period began                                            |
| `trial_ends_at`             | Date/time when the trial period ends                                             |
| `activated_at`              | Date/time the subscription became active                                         |
| `canceled_at`               | Date/time the subscription was canceled                                          |
| `expires_at`                | Date/time when the subscription will churn                                       |
| `status`                    | Invoice status (`pending`, `processing`, `past_due`, `paid`, `failed`, `voided`) |
| `maintenance_url`           | Link to the customer’s hosted account maintenance page (if enabled)              |

## Supported Actions

Once your connector is active and data is synced, you can attach these 1-Click actions to prompt interactions. The **account\_code** or **account\_number** trait must be present on users.

| Action                    | Description                                                 | API Integration         | Additional Instructions                     |
| ------------------------- | ----------------------------------------------------------- | ----------------------- | ------------------------------------------- |
| Apply Coupon Code         | Applies a coupon code to the user's account or subscription | Coupon Redemption       | Select the coupon code                      |
| Pause Subscription        | Pauses a user's subscription                                | Pause Subscription      | Select how many billing cycles to pause for |
| Resume Subscription       | Resumes a paused subscription                               | Resume Subscription     |                                             |
| Switch Subscription       | Switches the user to a new plan                             | Subscription Change     | Select the plan                             |
| Create Subscription       | Creates a subscription for an existing account              | Create Subscription     | Select the plan and enter the currency      |
| Reactivate Subscription   | Reactivate a cancelled subscription                         | Reactivate Subscription |                                             |
| Update Subscription Price | Update price of an active subscription                      | Subscription Change     |                                             |
| Convert Trial             | Convert trial to paid subscription                          | Convert Trial           |                                             |
| Record Usage              | Logs a usage record for a subscription add-on               | Log Usage Record        | Select the add-on and amount                |
| Cancel Subscription       | Stops auto-renewal for an active subscription               | Cancel Subscription     | Select refund option                        |