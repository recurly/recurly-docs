---
title: PayPal on Adyen
excerpt: Streamline PayPal acceptance through your existing Adyen Gateway with Recurly.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

### Required plan

This feature or setting is only available to Recurly merchants who’ve been specifically approved by Adyen and PayPal directly.

### Prerequisites

- Active PayPal and Adyen account.
- Integration with Adyen gateways.

### Limitations

- This integration uses Adyen tokens so cannot be easily migrated or moved to direct Paypal integrations such as PayPal Business or Complete.
- Recurly does not have access to the PayPal BAID or Vault ID.
- PayPal does not allow transaction amount requests between .01 and .48 cents. It's best practice to send transaction amounts of .50 cents and above when not offering free trials.

# Definition

PayPal via Adyen enables aggregated reporting at the Gateway level. It requires Adyen tokens, and permissions set at PayPal specifically to authorize Adyen, not Recurly, to process on behalf of you and your customers.

If you’d like to learn more about PayPal payments or Adyen, find it in our new and improved Recurly docs here:

- [PayPal Payment Method](https://docs.recurly.com/docs/paypal-payments)
- [Adyen Gateway](https://docs.recurly.com/docs/adyen)

# Key benefits

- **Consolidated reporting**: Merchants no longer need to reference PayPal and Adyen reporting separately.
- **Trusted brand**: Merchants can be certain their payments are processed accurately by both Adyen and PayPal.
- **Consolidated gateways**: Have less gateways in your Recurly site! Less is sometimes more.

# Key Details

You will need your Adyen gateway already set up for PayPal payments, as well as an active business PayPal account, ready for connection. 

Giving Adyen permissions to your PayPal account will occur outside of Recurly, and you can follow those [instructions](https://docs.adyen.com/payment-methods/paypal/setup-paypal-direct-merchants/).

# Implementation guide

## Setting up PayPal on Adyen

### Giving Adyen permissions

To give Adyen permissions to your PayPal account (live or test), ensure you are following all of the steps outlined on [Adyen’s documentation](https://docs.adyen.com/payment-methods/paypal/setup-paypal-direct-merchants/#permission).

**Note**: PayPal’s sandbox site does not produce email activation emails. You will need to navigate within your PayPal sandbox account to find the email and verify your paypal email within your PayPal sandbox site.

If you are struggling with enabling PayPal on your Adyen site, please reach out to Adyen’s support team directly for assistance as there is an alternative method that remains undocumented.

### Enabling the service on Recurly

1. To activate PayPal on Adyen within Recurly, merchants need to first request the Feature Flag be enabled for their account. Keep in mind, this integration needs explicit permission from both Adyen and PayPal to enable. Proof of such will be requested.

2. After the feature flag is enabled, merchants can navigate to their Payment Gateway settings within the Recurly platform. You will find a checkbox within your Adyen gateway settings to enable PayPal as an Alternative Payment Method. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/10a6f1b-image.png",
        null,
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


## Enabling PayPal on Adyen via Recurly.js

### Alternative Payment Methods via Recurly.js

1. Follow the Alternative Payment Methods [documentation](https://recurly.com/developers/reference/recurly-js/#alternative-payment-methods) for Recurly.js. At this moment, using the Purchase route (rather than Billing Info Update) is supported. Using Billing Info Update will result in poor user experience.

2. Ensure you are capturing the consumer’s email address. This is required for processing PayPal transactions via the Adyen gateway. 

3. If you are receiving permission issues when testing or processing, please reach out to Adyen and/or PayPal directly. Recurly support has no access to these settings from our system.

# FAQs

### Will PayPal on Adyen support one-time and recurring payments?

Yes! Integrators using PayPal with Adyen will be able to take advantage of customer initiated one-time transactions as well as set up recurring payments.

### If I am using PayPal on Adyen, can I migrate to a different PayPal gateway on Recurly?

No. Since PayPal on Adyen uses gateway-specific tokens, Recurly does not have access to the underlying payment instrument or PayPal billing agreement ID / Vault ID, and so migrations will involve customers having to resign up for subscriptions.

### Can I use a PayPal direct integration alongside PayPal on Adyen?

Yes! You are able to use any other gateway integration alongside Adyen, no matter the payment method in use. However, keep in mind that PayPal on Adyen is not compatible with other PayPal offerings on Recurly.

### Which currencies can I use with PayPal on Adyen?

PayPal supports less currencies than Adyen does, but Recurly has made certain that all PayPal currencies are accepted within our system. You should be able to use the following currencies with your PayPal implementation through Adyen: [PayPal Supported Currencies](https://developer.paypal.com/docs/reports/reference/paypal-supported-currencies/)