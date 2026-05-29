---
title: Retention by plan
excerpt: >-
  Delve deep with Recurly's 'Subscriber Retention by Plan': An intricate
  breakdown of subscriber activity and churn across diverse plans.
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

* Users must have Analytics user role permission.

# Definition

The "Subscriber Retention by Plan Section" in Recurly delivers a detailed examination of subscribers, segmenting them by their specific plans. It brings to the forefront a spectrum of data, from active subscribers to churned ones, while making distinctions based on their initial plan choices.

> **Note:** It's essential to note the distinction between a subscriber and a subscription. While a single subscriber might hold multiple active subscriptions, this dashboard focuses on counting the individual subscriber, not the number of subscriptions they possess.
>
> **Note**: Data only includes plans that have had at least 1 subscriber.
>
> **For additional guidance on navigating and utilizing filter tools, consult our documentation<a href="https://docs.recurly.com/docs/recurly-analytics-overview#navigation-features" target="_blank">here</a>.**

# Key benefits

* **Plan-specific insights:** Obtain a granular perspective on subscriber activity and trends, filtering specifically by plan, to understand unique retention dynamics.
* **Clear data segmentation:** With explicit differentiation between initial plans and subsequent plan changes, ensure data clarity and accuracy in subscriber retention analysis.
* **Informed strategy development:** Harness these insights to craft targeted retention initiatives for specific plans, maximizing subscriber longevity.

# Subscriber retention by plan section

This section provides a granular view of active and churned subscribers, differentiated by their plans.

* The "Subscriber Retention by Plan" includes reactivations and is presented at the subscription level, reflecting every subscription's retention based on the plan it was activated with.

On the other hand, "Subscriber Retention" is evaluated at the subscriber level. It amalgamates concurrent subscriptions, taking into account the first activation and the last expiration. If there's an interval wherein a subscriber has no active subscription, their subsequent activation will be considered a new subscriber cycle, and they will be counted again. For further details on returning subscribers, kindly refer to the Subscribers dashboard topic.

## Subscriber retention by plan status

This report displays Subscriber Retention based on the initial subscription plan. The plan referenced corresponds to the one activated with the subscription.

If a subscriber activates a second subscription, they will be counted again in the month and plan for that second activation.

Any subsequent changes to the subscription plan will not modify the data presented in this report.

<Image align="center" border={true} width="700px" src="https://files.readme.io/44283c5c36e7729c49fe994b1a6fa794e99137ef2435e9ba8facddbd0ce263e3-image.png" className="border" />

## Subscriber retention by plan active volume

Illustrates the count of active subscribers, grouped by their sign-up periods and chosen plans.

<Image align="center" border={true} width="700px" src="https://files.readme.io/ab607870c447bf5f627eff7d16d4af25d41e6472f67433b424c107a663befff5-image.png" className="border" />

## Subscriber retention by plan churned volume

Reveals the number of subscribers who churned within the selected timeframes and plans.

<Image align="center" border={true} width="700px" src="https://files.readme.io/9842a1c2acfc7a0183df9381d5dc73b29d38c813a9fbf62c907a03edfd79d1af-image.png" className="border" />

<br />
