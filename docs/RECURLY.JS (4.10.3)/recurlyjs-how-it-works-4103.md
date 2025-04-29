---
title: 'Recurly.js: How it works (4.10.3)'
excerpt: >-
  A concise overview of how Recurly.js securely processes payment details and
  returns an authorization token to simplify PCI compliance.
deprecated: false
hidden: false
metadata:
  robots: index
---
![](https://recurly.com/developers/images/recurly-js-logo.png)

# How it works

When a customer submits your payment form, Recurly.js sends customer payment information to be encrypted and stored at Recurly and gives you an authorization key to complete the subscription process using our API.

With this authorization key (or token), you can do anything with our API that requires payment information. Because you never handle any sensitive payment information, your PCI scope is drastically reduced.