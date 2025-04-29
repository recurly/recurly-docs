---
title: Upgrading (4.10.3)
excerpt: Learn how to upgrade your Recurly.js features.
deprecated: false
hidden: false
metadata:
  robots: index
---
## Upgrading

Upgrading from a previous version of Recurly.js.

***

### Upgrading from v3

Recurly.js v4 introduced the concept of hosted fields. These are a more secure method of capturing customer card data, ensuring that their payment information is never exposed to your payment form. This is a huge benefit for security and reduced PCI compliance exposure.

First, you will need to update your payment form. The credit card fields `number`, `month`, `year`, and `cvv` will need to be removed and replaced with a container element in the form `<div data-recurly="card"></div>`. We recommend using the card field since it includes a handful of validation and UX improvements, but it is also possible to use separate fields for the number, month, year, and cvv. This is explained more completely in the [Getting Started](https://docs.recurly.com/v1.2/docs/getting-started-4103#/) section.

Your `recurly.token` call may also need to be updated. It is now necessary to pass a reference to your checkout `<form>` that contains the hosted fields. Your callback function requires no modification. More info is available in the [Getting a Token](#getting-a-token) section.

You'll notice that the hosted fields won't look like the rest of your payment form inputs. That is because they are in fact iframes, and will need to be styled in order to get them to look right. We provide a stylesheet that works as a good baseline for styling the hosted fields to your needs (See the [Getting Started](https://docs.recurly.com/v1.2/docs/getting-started-4103#/) section). To tweak styles further, and to cover styles for when the field is invalid, etc, see the [Styling Card Fields](https://docs.recurly.com/v1.2/docs/styling-card-fields#/) section.

We are happy to assist further in your upgrade path. Feel free to reach out to us for [Support](#support).

### Upgrading from versions prior to v3

Since version 3, Recurly.js shifted to credit card tokenization as its method of billing info capture. Given the significant changes, upgrading from an earlier version of Recurly.js will require a full rewrite of your integration. Please see the [Getting Started](https://docs.recurly.com/v1.2/docs/getting-started-4103#/) section to begin.