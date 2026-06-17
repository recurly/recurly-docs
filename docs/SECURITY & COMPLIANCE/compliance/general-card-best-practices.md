---
title: General Card Best Practices
excerpt: >-
  Ensure Card compliance effortlessly with Recurly. Take advantage of the below
  best practices with card processing to ensure the best approval rates and
  reduced fees from your associated processing partners.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

> **Note:** Please note that the information provided below is intended as a general guide, and may not apply to all specific business circumstances. Card Brand requirements can and will change, and we endeavor to update this information in a timely fashion when we are notified or learn of new information. Please refer back to this page for new updates, or inquire with our support team if you see something that does not make sense or has changed.

# Definition

Processing cards can be complicated, and ensuring you are supplying the correct information to ensure the highest possible auth rates is an important part of data collection from your consumers, and Recurly's integrations.&#x20;

# Key details

Recurly makes available a plethora of consumer data fields such as name fields, address fields for billing and shipping, and usage of Recurly.js and API fields for collecting consumer IP address information.&#x20;

Major Card processing Networks such as Visa and Mastercard have a host of fields they require for best auth rates.

## Visa

Visa best practices include providing the customers First and Last name, Billing Address, and at least one of the following:&#x20;

- Email Address
- Phone Number&#x20;
- IP Address&#x20;
- Browser Data (Only available when using Recurly.js, HPP, or Recurly Checkout)

Ensure you are making use of Recurly fields that allow for sending and storing this data for future purchases, and renewals. If you would like to qualify for additional interchange improvements, follow our CEDP Level 2/3 Guidelines. If you are not using the API, ensure you are filling out your subscription plan and line item catalog fields to the fullest extent.

- [Level 2/3 API Guide](https://docs.recurly.com/recurly-subscriptions/docs/level-2-and-level-3-cedp-guide)&#x20;

## MasterCard and Elo

MasterCard and Elo have similar guidelines to Visa, in that they have recently updated their best practices.&#x20;

For MasterCard and Elo, you must provide **at least one** of the following:

- Email
- Home/mobile/work phone number
- Cardholder name

Additionally, Mastercard also require either the **billing** or shipping address to be provided. The cardholder name should contain only English characters, without accents (especially in LATAM regions).

**&#x20;**

<br />
