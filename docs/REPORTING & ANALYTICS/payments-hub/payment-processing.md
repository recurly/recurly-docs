---
title: Payment Processing
excerpt: >-
  Comprehensive view of payment success rates across all transaction types,
  payment methods, and gateways. Monitor success rates and decline patterns to
  optimize payment processing.
deprecated: false
hidden: true
metadata:
  title: Payment Processing
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

* Users must have analytics user role permission.

# Definition

The Payment Analytics dashboard gives you a deep dive into the performance of your payment stack — covering everything from high-level success rates and trends over time, to granular breakdowns by payment method, gateway, and card BIN. Paired with visibility into top decline reasons, this dashboard equips you with the insights needed to pinpoint underperformance, understand its root cause, and take targeted action to improve authorization rates and protect revenue.

# Key benefits

* **Pinpoint underperformance quickly** — by breaking success rates down across gateways, payment methods, and BINs, you can isolate exactly where failures are occurring rather than chasing broad trends.
* **Turn declines into recoverable revenue** — understanding your top decline reasons gives you a clear, actionable starting point for reducing preventable payment failures.
* **Optimize with confidence** — combining trend data with granular breakdowns means you can make informed decisions about your payment stack, whether that's switching gateways, prioritizing certain payment methods, or flagging underperforming BINs.

## Payment Success Rate

This card displays your overall Payment Success Rate as a single at-a-glance percentage — encompassing both customer and merchant initiated transactions for a fully holistic view of payment health — paired with a month-over-month trend indicator so you can immediately see whether performance is moving in the right direction. 

[ image ] 

## Payment Success Rate Over Time

Payment Success Rates over Time tracks your overall Payment Success Rate over an extended timeframe, giving you a broader view of how performance has trended across the month rather than a point-in-time snapshot.

[ image ]

## Payment Method Distribution

The Payment method distribution chart breaks down every payment method accepted on your site, showing the relative distribution of transactions across each — giving you an instant read on how your customers prefer to pay.

[ image ]

## Gateway Success Rates

The Gateway Success Rates graph breaks down payment success rates by gateway, giving you a side-by-side comparison of how each PSP is performing within your selected timeframe. Seeing performance isolated by gateway makes it easy to identify underperforming routing paths and validate the impact of gateway changes.

[ image ] 

## Payment Method Success Rates

The Payment Method Success Rates card breaks down payment success rates by payment method, giving you a side-by-side comparison of how each performs independent of the gateway processing it. Isolating success rates at the payment method level helps you identify which methods are underperforming and understand whether declines are method-specific.

[ image ]

## Card BIN Success Rates

The Card BIN Success Rates card breaks down payment success rates by card BIN, surfacing the top performing and most common BINs transacting on your site within a given timeframe. Visibility at the BIN level allows you to identify whether specific card issuers or card types are experiencing higher decline rates, giving you the granularity needed to take targeted action — whether that's working with your gateway, or flagging patterns.

## Payment Decline Reasons

This table surfaces your top payment decline reasons, categorized by hard or soft decline type, and ranked by count, percentage, and associated dollar volume — giving you a comprehensive view of where and why payments are failing. Distinguishing between hard and soft declines is critical, as soft declines often represent recoverable revenue through retries or account updates, while hard declines signal issues that require a more targeted intervention such as routing changes or issuer outreach.
