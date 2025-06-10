---
title: How it works
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

When a customer submits your payment form, Recurly.js immediately encrypts and securely stores their payment information on our servers. It then returns an authorization key—commonly known as a *token*—that you use to complete the subscription process through our API.

With this token, you can perform any API operation that requires payment details. Because you never directly handle sensitive payment information, your PCI compliance scope is significantly reduced.