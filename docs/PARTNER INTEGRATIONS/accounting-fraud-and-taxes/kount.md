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

This feature is only available on advanced plans. If you’re currently on Pro or Starter, you may need to upgrade your plan to access it. Please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) for more information.

### Limitations

* Risk inquiries are only performed on new card verifications (sign-ups and billing info updates).
* Existing accounts with a credit or debit card on file will not undergo risk inquiries unless they update their billing information.

# Definition

Kount is a leading fraud management platform that specializes in ensuring secure online transactions. Through its integration with Recurly, businesses can benefit from enhanced fraud detection and prevention mechanisms, ensuring a safer and more seamless transaction experience for their customers.

Recurly recognizes the importance of safeguarding businesses from potential threats. In our commitment to support and protect our customers, we've partnered with [Kount](http://www.kount.com/), a frontrunner in fraud management. This collaboration equips you with top-tier fraud prevention capabilities right within your Recurly platform.

# Key benefits

* **Reduced fraudulent orders**: Minimize the risk of accepting deceptive orders to safeguard your business.
* **Decreased chargebacks**: Lower the incidence of chargebacks, preserving both time and financial resources.
* **Enhanced customer experience**: Offer a secure transaction environment, elevating customer confidence and satisfaction.
* **Cost efficiency**: Curtail operational expenses tied to fraud detection and management, promoting a healthier bottom line.
* **Retention boost**: Foster a secure transaction milieu, aiding in reducing customer churn and enhancing loyalty.

<Image align="center" className="border" width="60% " border={true} src="https://files.readme.io/82814e8-d063eb2-image_7.png" />

Once Kount’s Fraud Service is activated, Recurly initiates risk assessments for new card verifications, including sign-ups and billing info updates. Accounts with existing credit or debit cards will only be assessed if their billing information is updated.

# Kount Enterprise

For businesses seeking a robust and customizable fraud management solution, Kount Enterprise is the ideal choice. It offers the foundational fraud prevention technology of Kount Basic, enhanced with direct access to your Kount Control Center and a dedicated Kount Customer Success Manager. With Kount Enterprise, you can:

* Create custom rules based on observed fraud trends and specific business policies.
* Access Kount’s business intelligence tools for comprehensive analysis.
* Conduct manual reviews for transactions.
* Leverage Kount's advanced artificial intelligence scoring for improved fraud detection.

## How does it work?

Upon activation, for every new card transaction, Recurly communicates with Kount’s Fraud Service, sharing essential transaction details like IP address, email address, shipping address, card details, billing info, and more.

Kount processes this data using its proprietary AI, applies your custom rules, and returns a risk decision. Recurly respects this decision: if Kount advises declining the transaction, Recurly halts the process, avoiding the payment gateway. If approved, Recurly continues with the transaction, forwarding details to the payment gateway.

Kount has additional layers of fraud protection in Kount Enterprise. Contact Kount to learn more about this offering and then, to integrate Kount Enterprise with Recurly, reach out to Recurly's [onboarding team](mailto:onboarding-team@recurly.com).
