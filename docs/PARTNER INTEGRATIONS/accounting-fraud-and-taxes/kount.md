---
title: Kount (fraud) integration
excerpt: >-
  Integrate with Kount for advanced fraud protection, ensuring safer
  transactions and a more secure customer experience.
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

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Prerequisites

* You must have a Kount 360 account. Please reach out to Recurly Support or your CSM/TAM if you are not already using this service.
* You must be able to utilize Recurly.js and invoke the risk related data-collector of that integration method.

### Limitations

* Risk inquiries are only performed on new billing info verifications (sign-ups and billing info updates) for the following payment methods:
  * Cards (including ApplePay and GooglePay)
  * All APMs available on the Recurly Platform. If you are not using Recurly.js for APMs (some do not offer this support) then Kount DDC / Session Information will be excluded.
* Existing accounts with a billing info (card or otherwise) on file will not undergo risk inquiries unless they update their billing information. 

### Recommendations 

* Use Recurly.js for all supported payment methods if you are not already doing so. This will ensure that the data collector creates a session ID which supports proper fraud detection with Kount and reduces false positives.
* For APMs that are not supported with Recurly.js, we will support a session ID bypass option. There are no integration changes you need to make for APMs not supported with Recurly.js -- continue to use them as documented. 
* Properly set up your webhooks if your Kount Account has rules for 'Review' flows, and ensure your integration is properly listening for Kount Fraud Update webhooks from Recurly. See **Enabling Kount Review Webhooks** on this page for more information.

# Definition

Kount is a leading fraud management platform that specializes in ensuring secure online transactions. Through its integration with Recurly, businesses can benefit from enhanced fraud detection and prevention mechanisms, ensuring a safer and more seamless transaction experience for their customers.

Recurly recognizes the importance of safeguarding businesses from potential threats. In our commitment to support and protect our customers, we've partnered with [Kount](http://www.kount.com/), a frontrunner in fraud management. This collaboration equips you with top-tier fraud prevention capabilities right within your Recurly platform.

Recurly's integration uses Kount's updated **Kount 360** platform.

# Key benefits

* **Reduced fraudulent orders**: Minimize the risk of accepting deceptive orders to safeguard your business.
* **Decreased chargebacks**: Lower the incidence of chargebacks, preserving both time and financial resources.
* **Enhanced customer experience**: Offer a secure transaction environment, elevating customer confidence and satisfaction.
* **Cost efficiency**: Curtail operational expenses tied to fraud detection and management, promoting a healthier bottom line.
* **Retention boost**: Foster a secure transaction milieu, aiding in reducing customer churn and enhancing loyalty.

<Image align="center" border={true} width="60% " src="https://files.readme.io/82814e8-d063eb2-image_7.png" className="border" />

Once Kount’s Fraud Service is activated, Recurly initiates risk assessments for new card verifications, including sign-ups and billing info updates. Accounts with existing credit or debit cards will only be assessed if their billing information is updated.

# Kount Enterprise

For businesses seeking a robust and customizable fraud management solution, Kount Enterprise is the ideal choice. It offers the foundational fraud prevention technology of Kount Basic, enhanced with direct access to your Kount Control Center and a dedicated Kount Customer Success Manager. With Kount Enterprise, you can:

* Create custom rules based on observed fraud trends and specific business policies.
* Access Kount’s business intelligence tools for comprehensive analysis.
* Conduct manual reviews for transactions.
* Leverage Kount's advanced artificial intelligence scoring for improved fraud detection.

## How does it work?

Upon activation, for every new card transaction, Recurly communicates with Kount’s Fraud Service, sharing essential transaction details like IP address, email address, shipping address, card details or apple pay tokens, billing info, and more.

Kount processes this data using its proprietary AI, applies your custom rules, and returns a risk decision. Recurly respects this decision: if Kount advises declining the transaction, Recurly halts the process, avoiding the payment gateway. If approved, Recurly continues with the transaction, forwarding details to the payment gateway.

Kount has additional layers of fraud protection in Kount Enterprise. Contact Kount to learn more about this offering and then, to integrate Kount Enterprise with Recurly, reach out to Recurly's [onboarding team](mailto:onboarding-team@recurly.com).

### Using custom fields

When using Custom Fields (formerly referred to as UDFs or 'User Defined Fields'), the label was not case-sensitive. In Kount 360, the label you send to Recurly will need to match the label you set in Kount. Example:

* If your Kount Rule is set up with a custom field label of '**Velocity**', then you must send '**Velocity**' to Recurly, and not '**velocity**', '**VeLoCiTy**' or '**VELOCITY**' as the rule will not trigger.

### Enabling Kount Review Webhooks

If you are utilizing the 'Review' flows in Kount, you will need to configure an endpoint in your Kount 360 Dashboard so that Recurly receives updates on your orders when Review states move to Approved or Declined.

While you should have had your webhooks configured when you set up your account, merchants who have migrated from Kount Command to Kount 360 may not have this enabled.

**Kount Webhook Endpoint**: `https://callbacks.recurly.com/kount/your-subdomain` where `your-subdomain` will be your Recurly site subdomain.

Kount only supports a single endpoint at this time, so if you are sharing your Kount credentials across multiple Recurly sites, you will not be able to use Review flows on all of them, and you must choose. For this, it is recommended to have a specific website ID (Kount site) that has Review flows.

You can configure your Kount site settings in your Fraud Management settings within Recurly. Simply enter a value for the 'Website ID' in configuration, and set up your Review rules to look at that value in Kount.

For a quick guide on best practices when ingesting Review webhooks, see our <Anchor label="integration guide on Ingesting Kount Status Webhooks" target="_blank" href="https://docs.recurly.com/recurly-subscriptions/docs/kount-360-review-webhook-guide">integration guide on Ingesting Kount Status Webhooks</Anchor> and next steps.

<br />
