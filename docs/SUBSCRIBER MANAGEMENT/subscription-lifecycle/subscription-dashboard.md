---
title: Subscription dashboard
excerpt: >-
  Navigate your Recurly subscription management with ease. Our Subscription
  Dashboard offers comprehensive tools to manage, modify, and understand your
  customer subscriptions effectively.
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

- Active Recurly account with necessary administrative permissions.
- Basic understanding of Recurly's subscription models and billing cycles.

### Limitations

- Inability to reactivate expired subscriptions.

# Definition

The Subscription Dashboard in Recurly is a centralized platform for managing customer subscriptions. It allows for the creation, modification, and analysis of subscriptions, providing tools to handle upgrades, downgrades, postponements, and terminations of customer subscriptions.

# Key benefits

- **Flexible subscription management**: Easily create and modify customer subscriptions, offering versatility with options to upgrade, downgrade, or change billing methods.
- **Efficient renewal and postponement tools**: Seamlessly manage subscription renewals and implement postponements, catering to diverse customer needs and scenarios.
- **Clarity in subscription lifecycle**: Gain a clear understanding of the subscription lifecycle stages, from active and paused states to cancellation and expiration, ensuring accurate customer account management.

# Key details

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/862f5f4-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% ",
      "border": true
    }
  ]
}
[/block]


This dashboard provides an overview of your subscriptions, providing many ways to organize, search and examine subscriptions. 

## Subscription lifecycle

#### Future

Future subscriptions have a start date that is yet to come. They are typically used in B2B contracts where the agreement specifies a future commencement date. Customers are not invoiced for these subscriptions until the start date arrives.

#### Active

Active subscriptions include regular paying subscriptions as well as those currently in a trial period.

#### Canceled

Canceled subscriptions are set to automatically expire at the end of the current term. This status can occur if a customer decides to cancel their auto-renewing subscription, or if the subscription is designed to end after the current term.

#### Expired

Expired subscriptions are those that have churned and cannot be reactivated. They may expire due to involuntary churn, such as failing the dunning cycle, or voluntary churn through cancellation.

## View your subscriptions

The subscriptions dashboard gives an overview of all accounts with subscriptions managed by Recurly. In this dashboard, you can sort subscriptions by account, plan code, subscription status, creation date, or next invoice date. Filters allow you to categorize accounts by subscription status for efficient sorting. Note that categories can overlap and are not mutually exclusive. For instance, the **Live** filter includes both **Renewing** and **Canceled** subscriptions.

| Category            | Description                                                                                              |
| ------------------- | -------------------------------------------------------------------------------------------------------- |
| All                 | Shows all subscriptions.                                                                                 |
| Renewing            | Covers active subscriptions set to renew, including paused subscriptions.                                |
| Future start        | Includes subscriptions scheduled to activate on a future date.                                           |
| Last billing period | Encompasses subscriptions in their final billing cycle of the current term, set to expire at term's end. |
| Paused              | Highlights active subscriptions that are currently paused and will not generate invoices.                |
| Canceled            | Shows subscriptions that will end at the close of their current subscription term.                       |
| Expired             | Displays subscriptions that are no longer active.                                                        |
| Trial               | Captures active subscriptions currently in a trial phase.                                                |
| Paying              | Refers to active subscriptions that have moved past the trial period.                                    |

## Create a subscription

To enroll your customers in one of your plans, you can create a subscription on their account. A customer may have multiple subscriptions to different plans or multiple subscriptions to the same plan. [Learn more](https://docs.recurly.com/docs/create-subscription).

## Change a subscription

Changes to a customer’s subscription often involve upgrades or downgrades but can also include modifications to the subscription's invoicing method. These changes can be applied immediately within the current billing cycle or deferred to the next term renewal. [Learn more](https://docs.recurly.com/docs/change-subscription).

## Postpone a subscription's renewal date

Postponing a subscription allows you to shorten or lengthen a customer’s current billing period. This feature is particularly useful for putting them on pause. [Learn more](https://docs.recurly.com/docs/postpone-subscription).

## Expire a subscription

When a customer chooses to end their subscription at the next billing date, it is referred to as **canceling** the subscription. If you opt to terminate the subscription early, mid-cycle, this is known as **terminating** the subscription. Both actions lead to the subscription **expiring**. Once a subscription has expired, it cannot be reactivated. However, a canceled subscription can be **reactivated** if the customer decides to continue the subscription before its scheduled expiration date. [Learn more](https://docs.recurly)