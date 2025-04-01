---
title: Subscription billing terms
excerpt: >-
  Unlock flexible subscription terms, decouple billing periods from plan length,
  and offer tailored commitments to your customers.
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

This feature (or setting) is available to all customers on any Recurly subscription plan.

# Definition

Subscription Billing Terms is a feature designed to enhance your billing strategy. With this, you can establish subscription terms featuring multiple billing periods, ensuring customers stick around, all while granting the freedom to modify, cancel, or extend terms as needed.

# Key benefits

* **Clarity in subscription management**: Detailed breakdown of adjusting or canceling subscriptions ensures predictable outcomes for revenue and customer satisfaction.

* **Tailored business strategies**: Enables merchants to flexibly modify subscriptions, enhancing upsell opportunities and customer loyalty.

* **Operational efficiency**: Step-by-step guides and visual aids streamline complex subscription processes, boosting customer service and decision-making.

# Subscription billing terms

The Subscription Billing Terms feature introduces the possibility of binding customers to a subscription term, offering multiple billing cycles within. This grants you the freedom to set billing intervals independently of the plan's overall duration. Imagine an annual subscription billed quarterly, or a one-year commitment, that shifts to a monthly cycle after the first year – all these scenarios are achievable.

# Billing structure for plans

This feature brings novel improvements to the billing setup during the plan creation process.

* **Subscription Term**: The inherent commitment length for subscriptions linked to the current plan. However, it can be adjusted during subscription creation or editing. A term might contain one or several billing periods.
* **End of Term Behavior**: Dictates whether the subscription gets renewed automatically, after the current term-

## Billing period and price per billing period

Plans must have a billing period. Once a plan is created, the billing period cannot be changed because it would affect the term length of active subscriptions. If you need to make changes to the billing period, create a new plan.

<Image align="center" className="border" border={true} src="https://files.readme.io/b0a3676-Billing_Period_And_Price_Per_Billing_Period.png" />

#### Subscription billing term length

The term length of a subscription is determined by its billing intervals. By default, the subscription adheres to the term configuration of the plan unless specified otherwise during creation or editing.

<Image align="center" className="border" border={true} src="https://files.readme.io/62a7d19-Subscription_Billing_Term_Length.png" />

> 📘 Month to month subscriptions
>
> For businesses mainly relying on monthly and auto-renewing plans, opt for plans with a monthly billing frequency and a term length spanning a single billing cycle.

## End of Billing Term Behavior

The renewal behavior post the end of a subscription term must be specified during plan creation. Subscriptions can be set to renew automatically post the term's end after the term's completion.

<Image align="center" className="border" border={true} src="https://files.readme.io/9da2dd2-End_of_Billing_Term_Behavior.png" />

Depending on business needs, you can either opt for auto-renewal or allow subscriptions to expire. For instance, streaming platforms might prefer auto-renewals to minimize churn, while businesses selling physical devices via installment payments might favor expiration post the completion of all payment installments.

# Adding a subscription

While associating a subscription to an account, the default behavior is adopted from the plan’s term settings. However, custom configurations are possible.

<Image align="center" alt="Price per Billing Period" border={true} caption="***Note:** &#x22;Price per Billing Period&#x22; refers to the recurring charge for each billing interval. Default price and quantity can be overridden as needed.*" src="https://files.readme.io/5a493f0-Screen_Shot_2018-06-05_at_9.28.50_AM.png" />

#### Timing

This section provides information about when the subscription starts (it can start immediately or be scheduled to start at a later date) and the settings that determine the length of the subscription term.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/de09aa30d62445d0bb29151bd72e6cf5dd99ebd3d7c3c476ba13ddf0ca6566a0-StartSubPastDate_1.png" />

#### Subscription details

Our revamped subscription details interface now accommodates information pertinent to terms. Subscription details can include:

* **Current Period**: Identifies the ongoing billing cycle.
* **Current Term**: Indicates the start and end dates of the active subscription term.
* **Remaining Periods**: Specifies outstanding billing cycles within the current term.
* **Term Balance**: Estimates outstanding billable amounts.
* **Renews On**: Indicates the renewal date for subscriptions set to auto-renew.
* **Ends On**: Marks the expiry date for subscriptions intended to cease post the term.
* **Started On**: Notes the date when the subscription got activated.

<Image align="center" alt="Multiple Billing Period Subscription Term" border={true} caption="\_" src="https://files.readme.io/18d6c96-FireShot_Capture_35_-_Internal__Subscription_Terms_-_Google___-_https___docs.google.com_document_d.png" />

<Image align="center" className="border" border={true} src="https://files.readme.io/914c3ae-FireShot_Capture_36_-_Internal__Subscription_Terms_-_Google___-_https___docs.google.com_document_d.png" />

# Changing a subscription

Adjustments to a customer's subscription typically involve upgrades or downgrades. However, they can also include alterations to the subscription's invoicing method. These modifications can be executed instantly within the ongoing billing cycle, at the upcoming billing date, or upon term renewal.

## **Immediate changes**

1. **Log into Recurly Dashboard**: Access your Recurly admin account.
2. **Navigate to Subscriptions**: Locate the customer's subscription you wish to change.
3. **Select 'Change Subscription'**: This option will be available for active subscriptions.
4. **Choose 'Immediate Change'**: This ensures that the changes are applied right away.
5. **Update Subscription Details**: Modify the plan, add-ons, or other subscription attributes as needed.
6. **Review Invoice Impact**: Check how the change will impact the current billing.
7. **Confirm and Save**: Once satisfied with the changes, confirm to immediately reflect them on the account

## Timing of modifications

* **Immediate Changes**: The subscription alteration takes effect instantly, and the billing for the change is immediate.
* **Next Bill Date Changes**: The modification is reflected on the customer's subsequent invoice.
* **Term Renewal Changes**: The change is mirrored on the invoice when the subscription term renews.

### **At next bill date**

1. **Log into Recurly Dashboard**: Access your Recurly admin account.
2. **Navigate to Subscriptions**: Search and select the specific customer subscription.
3. **Select 'Change Subscription'**.
4. **Opt for 'At Next Bill Date'**: Ensure the change applies when the subscription next bills.
5. **Make Desired Changes**: Adjust plan, add-ons, or other details.
6. **Save and Exit**: Confirm your changes. They will be applied on the next billing date.

### **At term renewal**

1. **Log into Recurly Dashboard**.
2. **Navigate to Subscriptions**.
3. **Select 'Change Subscription'**.
4. **Choose 'At Term Renewal'**: Opt for this to save changes for the term renewal.
5. **Update Subscription Attributes**: Make necessary modifications.
6. **Review and Save**: Confirm your changes. They will be applied when the subscription term renews.

It's common for merchants to prefer to offer immediate upgrades, allowing instant access to a premium product and immediate revenue collection. Downgrades, on the other hand, are often set for the next billing date or term renewal, ensuring the customer continues to receive the higher-tier product until the specified time.

## Immediate adjustments

When a subscription is altered immediately, the difference in cost is billed right away. This action generates an invoice, and if automatic collection is enabled, a transaction attempt is made using the payment method listed in the customer's Billing Information. Should the transaction fail, the invoice and subscription enter the Dunning process.

**Note**: Solely altering the subscription's term length won't generate an invoice if that's the only modification.

For a detailed breakdown of the proration logic for immediate changes, refer [here](https://docs.recurly.com/docs/change-subscription#section-immediate-changes).

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/2344d3d-2019-09-04_1129.png" />

## Adjustments for the next billing date

When set to "When subscription next bills", Recurly will store the modifications and apply them on the customer's next invoice. For instance, if an annual plan is upgraded to reflect on the next bill date, the upgrade will begin at the conclusion of the current billing cycle.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/ece1cd8-2019-09-04_1233.png" />

## Adjustments for term renewal

When set to "When subscription term renews", Recurly stores the changes and implements them upon the subscription term's renewal. For instance, if an annual plan is upgraded to be effective upon term renewal, the upgrade will take place at the conclusion of the initial annual plan.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/579cbf6-2019-09-04_1233.png" />

### One change request limitation

Recurly retains only a single change request. If a change request is submitted to be effective at renewal and another change request is made before that renewal, the initial request is nullified. The subsequent request is either applied immediately or at renewal, based on the specified timeframe. For "At renewal" change requests, proration isn't necessary; Recurly will adjust the subscription accordingly and invoice the user at the new amount on the renewal invoice.

### Adjustments to plan terms

When transitioning a subscription to a different plan, it's crucial to consider the new plan's billing structure, including billing periods, and term lengths.

#### Transitioning to a plan with identical billing period and term length

Immediate changes that retain the same term structure will maintain the remaining billing periods and adhere to standard proration rules. If you wish to modify the term length, you have the option to do so.

#### Transitioning to a plan with a different billing period or term length

If the immediate change results in a different term structure, the subscription term restarts and the new charges aren't prorated.

For more details, visit [Change Subscription](https://docs.recurly.com/docs/change-subscription#section-plan-period-changes).

> 🚧 **Note**: If a subscription is set to expire at the term's end and you're editing it to apply changes upon renewal, saving these changes will automatically update the subscription to renew at the term's end and apply the pending changes.

# Canceling a subscription

When a customer chooses to cancel their subscription at the next billing date or at the term's end, it's known as canceling the subscription. If you opt to terminate the subscription prematurely, within the cycle, it's called terminating the subscription. Both actions result in the subscription's expiration. Once expired, a subscription can't be reactivated. However, a canceled subscription can be reactivated if the customer decides to continue before the renewal date.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/fc695d5-2019-09-04_1238.png" />

## Immediate termination

Immediate termination shifts the subscription's status from active to expired. If the termination occurs mid-cycle, you can choose to refund the customer for any upfront fixed fees or bill the customer for any unbilled usage fees.

1. **Log into Recurly Dashboard**.
2. **Go to Subscriptions**: Locate the desired customer subscription.
3. **Choose 'Cancel Subscription'**.
4. **Select 'Terminate Immediately'**.
5. **Determine Refunds/Charges**: Decide if the customer should be refunded for fixed fees or charged for unbilled usage.
6. **Confirm Termination**: Review the impact and confirm to immediately terminate the subscription.

## Canceling at the next billing date

For subscriptions set to auto-renew, some customers might wish to cancel. This option ensures the subscription continues until the current period ends, after which it expires.

1. **Log into Recurly Dashboard**.
2. **Navigate to Subscriptions**.
3. **Choose 'Cancel Subscription'**.
4. **Opt for 'At Next Bill Date'**: This will halt the subscription before the next invoice is generated.
5. **Confirm and Save**: Ensure the subscription will run for the remainder of the current period and then expire.

## Canceling at the term's end

For auto-renewing subscriptions, some customers might opt for cancellation at the end of their term. This option ensures the subscription continues billing for the remainder of the term, and once the term end date is reached, the subscription expires.

1. **Log into Recurly Dashboard**.
2. **Go to Subscriptions**.
3. **Select 'Cancel Subscription'**.
4. **Choose 'End of Term'**: This ensures the subscription bills for the entire term before expiring.
5. **Review and Confirm**: The subscription will bill until the end of its term and then terminate.