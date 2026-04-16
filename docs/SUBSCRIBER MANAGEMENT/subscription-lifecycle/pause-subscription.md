---
title: Pause subscription
excerpt: >-
  Enhance customer retention by leveraging Recurly's Pause Subscription feature.
  Offer flexibility without canceling the subscription entirely.
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

# Definition

The Pause Subscription feature provides merchants with the ability to temporarily halt a subscription, allowing customers to skip certain billing cycles without entirely terminating their subscription.

# Key benefits

* **Reduce churn rates:** By giving customers the option to pause, it prevents outright cancellations and the need to win back lost customers.
* **Maintain revenue stream:** As the service remains active till the end of the current billing cycle, there's no immediate loss in revenue or the need for prorated refunds.
* **Flexibility:** Cater to diverse customer needs, whether they are going on a vacation or using a season-specific service.
* **Ease of management:** Streamlined through both the Admin Console and API.
* **Improved customer experience:** By providing tailored solutions, enhance customer trust and satisfaction.

# Key details

Having a Pause Subscription feature is more than just an administrative function; it's a strategic tool in the subscription-based business world. Sometimes, customers may not want to entirely sever ties with a service but might have specific reasons to discontinue temporarily. This can be due to budget constraints, changing frequency of use, traveling, or even when the service is season-based like sports streaming.

When the pause is initiated, the subscription remains active until the end of the current billing cycle. This respects the payments already made by the subscriber, ensuring they get the value they paid for. From a business standpoint, there’s minimal disruption as no mid-cycle billing adjustments are required.

Keep in mind, when resuming paused subscriptions, the EU mandates 3DS / SCA to re-authenticate the consumer prior to resuming the subscription. You can use Recurly's API to re-verify stored billing info and allow consumers to complete these flows.

### Why pause a subscription?

**Retaining customers:** Allowing subscribers to [pause instead of cancel](https://recurly.com/blog/why-pausing-a-subscription-can-be-a-powerful-retention-tactic/) their subscription can deter voluntary churn. When subscribers opt for pausing, they indicate a likelihood to return, thus saving businesses marketing costs associated with winning them back.

**Consumer needs:** Various reasons could drive a customer to halt subscription billing, such as:

* Financial constraints.
* Infrequent service usage during specific periods.
* Temporary unavailability, like vacation or travel.
* Seasonal relevance of a service, as seen with [seasonal services like sports streaming](https://recurly.com/blog/addressing-seasonality-in-your-subscription-business/).

**Billing and Finance Implications:** Pausing ensures subscriptions remain active until the end of the current billing period. Since most are paid upfront, subscribers can utilize services they've financed. For businesses, this model eliminates complications linked to mid-cycle changes, like prorated refunds or credit issuance for unused service durations.

### How It works

**Prerequisites for Pausing:**

* The subscription should be active.
* The subscription cannot be set to a future date, in-trial, a non-converted gift, canceled, or terminated.
* There should be no overdue invoices on the account.
* The pause is always tied to the next billing date.
* Usage logging for add-ons isn't possible during the pause.
* Bill date changes and postponing paused subscriptions have specific conditions to be met.

# How to pause subscriptions

There are 3 ways to pause subscriptions - through the Subscription Details section in the UI, the Account section in the UI or the use of APIs.

## Pausing from subscription details

* Navigate to desired subscription details.
* Select **Pause Subscription** from the **Subscription Actions** dropdown.

<Image align="center" border={true} src="https://files.readme.io/1732a4e-image.png" className="border" />

* The **Configure Pause Duration** window appears. Here, two fields need attention:

**Pause Start Date**: It's the onset date for the pause, defaulting to the subscription's billing date.

![Pause Date Configuration](https://files.readme.io/5b4473e-Screen_Shot_2020-03-16_at_1.44.49_PM.png)

**Number of Billing Cycles to Skip**: Dictates the duration for the subscription pause.

![Billing Cycle Configuration](https://files.readme.io/175d7c5-Screen_Shot_2020-03-16_at_1.45.39_PM.png)

* Post-configuration, selecting **Schedule Pause** finalizes the process. A confirmation banner appears, providing pause details.

<Image align="center" border={true} src="https://files.readme.io/da2449e-Screen_Shot_2018-07-27_at_2.10.13_PM.png" className="border" />

## Pausing from account

* Locate the account and desired subscription.
* Click **Options** → **Pause Subscription**.

<Image align="center" border={true} src="https://files.readme.io/78e6cb7-image.png" className="border" />

## Pause from subscription details

* Restarting brings a subscription back to its active state, billing the customer for the new cycle. Paused subscriptions can be resumed from the Subscription Details or Account.
  * If you are subject to PSD2 / SCA Compliance, you can verify your customer's billing information and re-authenticate 3DS using these steps: [3D secure with stored Billing Information](https://docs.recurly.com/v1.1/docs/using-3d-secure-with-stored-billing-information#/)
  * Scheduled pauses can be canceled via **Pause** under the subscription's **Options** or **Subscription Actions**.

> 🚧 Current Term Renewal Dates
>
> While a subscription is paused, the original term renewal date of the subscription will not be updated (in the API this is represented as the current_term_ends_at timestamp). This is due to the fact that the scheduled pause can be canceled, the subscription could be resumed earlier, or the number of pause cycles could be updated. Any of the former events could potentially change the renewal date. Once a subscription is returned to active, the term renewal date will be updated.
>
> To calculate the new renewal date while a subscription is paused, you will want to take original renewal date and add the length of the pause period.

<Image align="center" border={true} src="https://files.readme.io/ce39f10-image.png" className="border" />

* The pause duration can be adjusted under **Edit Pause** in both Account and Subscription Details.

**API Integration:**

Pausing, restarting, and other related actions can be executed through the API, as detailed in the [API documentation](https://developers.recurly.com/api/latest.html#operation/pause_subscription).

## Resuming a subscription

> 📘 SCA Notice
>
> Please note: In regions where SCA is required, resuming or reactivating a subscription via the Dashboard may result in renewal failures and therefore is not recommended. Your customer must be involved in the resume/reactivation of a subscription if 3DS Authentication is required, and dashboard updates cannot be used. Please see API integration for more details.

To resume a subscription that is currently paused:

1. **Navigate** to the subscription's **Account** page or **access** the **Subscription Details**.
2. In the **Subscription Details**, use the **Subscription Action** dropdown menu and select **Resume** to reactivate the subscription.
   1. **EU Compliance Note**If you are subject to PSD2 / SCA Compliance, you will need to re-authenticate your customer prior to resuming a subscription. Re-authentication must be handled by the consumer directly. You can verify your customer's billing information and re-authenticate 3DS using these steps: [3D secure with stored Billing Information](https://docs.recurly.com/v1.1/docs/using-3d-secure-with-stored-billing-information#/). After a successful billing info verification, feel free to resume the subscription using these steps.
3. If resuming from the **Account** page, **locate** the individual subscription and select **Resume** from the **Options** dropdown menu.
4. Upon resuming, the subscription will move from the paused state to an active state, initiating a new billing cycle.
5. The customer will receive an immediate invoice for the new billing cycle, and the payment method will be charged if the collection method is automatic.
6. If the [Calendar Billing](doc:calendar-billing) feature is in use, the subscription will align with the predetermined billing date, and any invoice generated will be prorated accordingly.

<Image align="center" border={true} src="https://files.readme.io/3b26eb5-Screenshot_2018-03-14_19.26.15.png" className="border" />

## Closing an account with paused subscriptions

Closing an account that has subscriptions in a paused state will result in the immediate termination of those subscriptions.

## Usage-based add-ons

For usage-based add-ons, billing occurs prior to a subscription entering a paused state. For instance, if usage is recorded for a subscription set to pause on April 2nd, an invoice for any accrued usage-based charges will be issued on that date. It is not possible to log usage while a subscription is paused.

## Considerations and examples

* **Indefinite Pauses:** For longer pauses, a high value (like 1200 for a monthly subscription, translating to 100 years) can be set, but this may [impact churn rate calculations](https://recurly.com/blog/better-way-to-calculate-your-churn-rate/).
* **Implications of Subscription Changes During a Pause Period:** When a subscription is set to pause or is currently in a paused state, any immediate changes made to the subscription will cancel the pause. This means that if you adjust the subscription details after the pause has been scheduled or while it is active, the pause will no longer be in effect.

**Example scenarios:**

1. Joe, a football streaming subscriber, requests a 4-month pause post season. With his next billing on March 1st, the pause ensures no billing until July 1st.
2. If Joe's subscription, set for a February 1st pause, gets upgraded on January 20th to include baseball streaming, the scheduled pause is canceled. He will be billed on February 1st for the new plan.  
   1st pause, gets upgraded on January 20th to include baseball streaming, the scheduled pause is canceled. He will be billed on February 1st for the new plan.

## Billing and invoicing

* **During pause:** No invoices will be generated, and the subscriber won't be charged.
* **After restart:** Once the subscription restarts, invoicing continues as per the subscription terms. If there were any changes to the subscription plan or add-ons during the pause, they would reflect in the invoice.

## Coupons

When a subscription is paused, we will not pause the duration of a coupon applied to the subscription.  
Coupons can be a great tool to incentivize customers to return to paying for a service. Offering a promotional discount for the customer to upgrade their plan and resume their subscription can be beneficial. Making an immediate subscription change to a new plan and applying the coupon will automatically resume the customer's subscription, returning them to a paying status.

#### Example 1

Joe is subscribed to the Silver Sports Package plan and has a 2-month subscription-level coupon. He decides to pause his subscription for 4 months. After 2 months of the pause, the coupon will expire. When the subscription restarts, the 2-month duration coupon won't apply to the invoice.

#### Example 2

Joe, a Silver Sports Package subscriber, has his subscription paused for several months. To incentivize Joe to return to the service, a discount coupon is offered for upgrading to the Platinum Package. Joe accepts, upgrades using the coupon, and his subscription immediately restarts  with the Platinum plan.

## Email

Subscribers with paused subscriptions may  wish to be notified about the upcoming restart of their subscription. Similarly, those with an upcoming pause at the next renewal may also want a notification. Leveraging the Renewal Reminder email with fields `{{subscription_paused_at}}` and `{{remaining_pause_cycles}}` can display the pause date and remaining paused billing cycles, respectively. Learn more in our **[Email templates](https://docs.recurly.com/docs/email-templates#/)** dedicated page.

## Webhook notifications

Recurly's Pause Subscription feature can send six notification events:

* Scheduled subscription pause
* Subscription pause canceled
* Subscription paused
* Subscription pause modified
* Paused subscription renewal
* Subscription resumed  
  For each pause notification's specifics, refer to the [Webhooks](https://docs.recurly.com/v1.0/docs/webhooks) documentation.

## **Exports**

Two columns on the Subscriptions Export support this feature:

* `{{_paused_at}}` shows when the subscription was paused.
* `{{remaining_pause_cycles}}` presents the remaining paused billing cycles.

## **Analytics**

In Recurly Analytics, the subscriber count encompasses all accounts with at least one active, paused, or canceled subscription, including trials. Paused subscriptions equate to active ones in calculations and aren't seen as churned.  
Paused subscriptions don't influence MRR while on pause. Given that no invoices are issued during a pause, the subscription contributes zero charges to MRR.

## **Hosted account management**

Currently, subscribers cannot pause or resume their subscriptions using Hosted Account Management. But a subscription can be manually paused or resumed through the API or Admin Console. In Hosted Account Management, the subscription status will display as "paused" if applicable.

# FAQs

**Q: What happens when a paused subscription reaches its resumption date?**

**A:** The subscription will automatically resume, and the subscriber will be billed for the next cycle.

**Q: Can a subscription be paused more than once?**

**A:** Yes, but each pause must conclude before initiating another. Concurrent pauses aren't permitted.

**Q: Do paused subscriptions impact Monthly Recurring Revenue (MRR)?**

**A:** While the subscription remains paused, it won't contribute to MRR because no invoices are generated.

**Q: What's the difference between pausing and canceling a subscription?**

**A:** Pausing temporarily halts billing but retains the subscriber's intent to return. Canceling ends the subscription, indicating the subscriber doesn't plan to continue the service.

Occasionally, customers may want to[ pause their subscription instead of outright canceling](https://recurly.com/blog/why-pausing-a-subscription-can-be-a-powerful-retention-tactic/) their subscription. Having the option to pause instead of cancel is a great way to avoid voluntary churn and reduce marketing dollars to win customers back.
