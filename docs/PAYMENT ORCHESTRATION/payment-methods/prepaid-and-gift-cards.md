---
title: Prepaid and gift cards
excerpt: >-
  Recurly provides credit card processing solutions that support a variety of
  credit and debit card types, offering secure and efficient handling of
  recurring transactions through globally recognized gateways.
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

### Prerequisites & supported gateways

To accept prepaid cards on your Recurly site, just enable any payment gateway that processes credit or debit cards.

### Limitations

* Prepaid cards often don't pass address verification system (AVS) checks. This is because they're not linked to a specific bank account or the cardholder's current address, and few consumers register their prepaid cards with their addresses.

* Non-reloadable prepaid cards have a fixed amount of money available. When the balance is depleted, customers will need to use another payment method to keep their subscriptions active. Adding a card to Recurly or getting initial approval doesn't ensure it will always be approved in the future.

* Accepting prepaid cards can lead to an increase in free trial abuse. If this concerns you, some gateways might offer the option to block the use of prepaid cards on your site.

# Description

For Recurly-issued Gift Cards, see [Gift Cards](https://docs.recurly.com/docs/gift-cards). 

For information on Recurly-specific gift cards, visit our gift card documentation.

Prepaid cards, provided by major credit card companies, come in two forms: reloadable and non-reloadable. This means some cards let you add money to them and others don't. Unlike gift cards, prepaid cards aren't restricted to a particular store or brand. These cards will have the logo of the major network they belong to, indicating they can be used widely.

For instance, the Visa Vanilla Prepaid Card, a non-reloadable option, is widely available and preloaded with a set amount of money. Meanwhile, the Emerald Prepaid MasterCard, a reloadable option offered by H\&R Block, is popular for managing tax refunds in the U.S. Reloadable cards are particularly useful for people without traditional bank accounts, offering a way to shop or pay bills online and in stores.

# Use cases

Non-reloadable prepaid cards, often coming in the form of a Visa or Mastercard Debit flavor, are popular ways to gift money to family and friends in lieu of cash for birthdays and holidays. Customers can use these cards at retailers and online to purchase items or services for themselves using this gifted money.

Reloadable prepaid cards are also popular for paying bills or making online purchases. These types of cards are debit cards, but are not attached and do not require a US bank account to function. Consumers can add funds to the balance at a retailer using cash, and then use the card’s balance for card-based purchases, including subscriptions.

# Checkout flow

There is no specific checkout flow for using a prepaid card on Recurly. These types of cards will function just like a normal credit or debit card.

If you are looking for Recurly gift cards, see the Gift Card documentation linked below.

# Recurly settings

1. **Enabling Recurly Gift Cards**

See the [Recurly Gift Cards documentation](https://docs.recurly.com/docs/gift-cards) for more information. 

2. **Enable any gateway that supports cards**

Choose a gateway that supports processing credit or debit cards and ensure you do not have Prepaid blocking on at the gateway level (where supported.)

Find the list of supported credit and debit card gateways via the link provided.

# FAQs

**Q: Can I block prepaid cards if I don’t wish to accept them?**

Yes, if you prefer not to accept prepaid cards, there are a few strategies you can employ. The simplest method is to activate [Kount](https://docs.recurly.com/docs/fraud-management#kount-enterprise), a service that helps manage and prevent fraud on your site, including blocking prepaid cards. You can get in touch with Recurly customer support to set up Kount for your website.

Alternatively, if you'd rather not use Kount, you can consult with your payment gateway provider. They might have specific settings or options available to block prepaid cards by identifying and refusing cards issued by prepaid card BINs (Bank Identification Numbers).
