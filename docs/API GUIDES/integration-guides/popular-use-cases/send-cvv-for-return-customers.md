---
title: Send CVV for Return Customers
excerpt: >-
  Mastercard and certain gateways mandate CVV on all customer initiated
  transactions. Recurly offers several options to comply with these
  requirements.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This guide shows you how to use the [Purchase endpoint](https://developers.recurly.com/api/latest/#tag/purchase) to create new transactions using a stored card number while also passing the CVV code to Recurly. CVV code, even for stored payments is a high-value fraud reduction value, and some gateways require CVV on all customer-initiated transactions, even if it is a return customer revisiting your site.

### Prerequisites & limitations

- Familiarity with Recurly’s API
- Familiarity with Recurly's Recurly.js product (if you want to avoid handling the CVV directly)
- [Completed the Quickstart Guide](https://docs.recurly.com/recurly-subscriptions/docs/quick-start-guide#/)

***

# Definition

**Creating Purchases** refers to the process of generating new customer accounts alongside subscriptions in a single, consolidated call to the Recurly Purchase endpoint. This streamlines checkout experiences by bundling all required resources into one request.

**CVV** refers to the 3 or 4 digit code on the back of a credit card that customers can enter when making purchases or signing up for subscriptions.

**Return Customer / Stored Card&#x20;**&#x72;efers to a customer whose credit card is already on file within Recurly's systems. They do not need to re-enter their card, but they will need to provide their CVV code in certain cases.

**PCI Compliance** refers to the data-compliance industry standards around card and PII storage. Recurly takes card-data storage very seriously, and storing the customer's CVV code is against PCI compliance. This is why the customer must re-enter it in certain cases.

***

# CVV Collection Options

- You may pass the CVV code in the clear via the `cvv` field via the V3 API when making a purchase or creating a new subscription with an existing account code or billing info ID.&#x20;
- You may tokenize the CVV field by using the stand-alone Recurly.js CVV element and passing us a token ID alongside the existing account code. This method assumes the billing info on file is the sole card or is the primary when using Wallet.
  - If you are using Wallet and want to specify a non-Primary billing info ID, you will need to tokenize the billing info ID and CVV together using Recurly.js.
- You may use the CVV Verification endpoint to verify customer data prior to making non-transaction changes, such as re-enabling a subscription after a deactivation or pause.

<br />

# Creating Purchases and Subscriptions&#x20;

##

<br />

<br />
