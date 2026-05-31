---
title: Payment processing
excerpt: >-
  Comprehensive view of payment success rates across all transaction types,
  payment methods, and gateways. Monitor success rates and decline patterns to
  optimize payment processing.
deprecated: false
hidden: false
metadata:
  title: Payment Processing
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

- Users must have analytics user role permission.
- To see splits in pie chart cards, your site must be processing more than one payment method, such as cards and ACH, or cards and Apple Pay.

# Definition

The Payment Analytics dashboard gives you a deep dive into the performance of your payment stack — covering everything from high-level success rates and trends over time, to granular breakdowns by payment method, gateway, and card BIN. Paired with visibility into top decline reasons, this dashboard equips you with the insights needed to pinpoint underperformance, understand its root cause, and take targeted action to improve authorization rates and protect revenue.

# Key benefits

- **Pinpoint underperformance quickly** — by breaking success rates down across gateways, payment methods, and card BINs, you can isolate exactly where failures are occurring rather than chasing broad trends.
- **Turn declines into recoverable revenue** — understanding your top decline reasons gives you a clear, actionable starting point for reducing preventable payment failures.
- **Optimize with confidence** — combining trend data with granular breakdowns means you can make informed decisions about your payment stack, whether that's switching gateways, prioritizing certain payment methods, or flagging underperforming card BINs.

# Key details

## General Filters (Top Left Corner)

- **Date Range:** Adjust the time interval for your data to track and analyze long-term trends. The default view is  30 days.

- **Country:** See data specific to your country, offering relevant insights and comparisons.

- **Gateway:** This filter allows you to segment and analyze data based on available payment processors. You can look at all payment gateways together or examine one at a time to understand where issues are happening.

- **Payment method:** If you want to see the breakdown of failed payments by the method your customers use, this filter lets you select specific payment options to analyze.

- **Initiated by:** This filter allows you to select between CIT (customer initiated) or MIT (merchant initiated) transactions.

- **Currency:** This filter allows you narrow your view to specific currency or currencies.

## Payment Success Rate

This card displays your overall Payment Success Rate as a single at-a-glance percentage — encompassing both customer- and merchant-initiated transactions for a fully holistic view of payment health — paired with a comparison to the previous time period, so you can immediately see whether performance is moving in the right direction.


<Image src="https://files.readme.io/fdab704983d618d07856b31c1c0f243a69b11af35427781d0dabdbc65fc851a1-image.png" align="center" border={true} />


## Payment Success Rate Over Time

Payment Success Rates over Time tracks your overall Payment Success Rate over the timeframe in view, giving you a more detailed view of how performance is trending.


<Image src="https://files.readme.io/990c9649897c4951cc72cadb8ac24f2499ae9adc2fb53f2fb4a49922b6cf2172-image.png" align="center" border={true} />


## Payment Method Distribution

The Payment method distribution chart breaks down every payment method accepted on your site, showing the relative distribution of transactions across each, giving you an instant read on how your customers prefer to pay.


<Image src="https://files.readme.io/5c8d9cf777870794051ad03ea1ea0a04b9234ac71a32074c1db32255a431eb40-image.png" align="center" width="600px" border={true} />


## Gateway Success Rates

The Gateway Success Rates graph breaks down payment success rates by gateway, giving you a side-by-side comparison of how each PSP is performing within your selected timeframe. Seeing performance isolated by gateway makes it easy to identify underperforming routing paths and validate the impact of gateway changes.


<Image src="https://files.readme.io/4fcc2f024b2b21e72fb0543368ce4cc67574cdb2f96408d0293671d13041ac05-image.png" align="center" border={true} />


## Payment Method Success Rates

The Payment Method Success Rates card breaks down payment success rates by payment method, giving you a side-by-side comparison of how each performs independent of the gateway processing it. Isolating success rates at the payment method level helps you identify which methods are underperforming and understand whether declines are method-specific.


<Image src="https://files.readme.io/85e30bc6549491443c6c0a1e68dc357b6c1525a3081f50772da5bdbdb097ee45-image.png" align="center" border={true} />


## Card BIN Success Rates

The Card BIN Success Rates card breaks down payment success rates by card BIN, surfacing the top performing and most common BINs transacting on your site within a given timeframe. Visibility at the BIN level allows you to identify whether specific card issuers or card types are experiencing higher decline rates, giving you the granularity needed to take targeted action — whether that's working with your gateway, or flagging patterns.


<Image src="https://files.readme.io/685d9bffaf3e06ae70999223c5e9a2ec59205752eb6e974f1a6bd88c7a9c907b-image.png" align="center" border={true} />


## Payment Decline Reasons

This table surfaces your top payment decline reasons, categorized by hard or soft decline type, and ranked by count, percentage, and associated dollar volume — giving you a comprehensive view of where and why payments are failing. Distinguishing between hard and soft declines is critical, as soft declines often represent recoverable revenue through retries or account updates, while hard declines signal issues that require a more targeted intervention such as routing changes or issuer outreach.


<Image src="https://files.readme.io/c83f911da5c3212387e1ddde43e38a4a5dff163baeb38dac2d65d2b5ece58f77-image.png" align="center" border={true} />


<br />
