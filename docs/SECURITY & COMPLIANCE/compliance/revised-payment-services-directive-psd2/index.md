---
title: PSD2 compliance
excerpt: >-
  Get ready for PSD2 Compliance with our comprehensive guide - strengthen your
  online security, enhance the customer experience, and reduce fraud with Strong
  Customer Authentication (SCA) and 3D Secure (3DS).
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

# Definition

PSD2 (Revised Payment Services Directive) is a European Union directive that came into effect on December 31, 2020, requiring financial institutions to provide stronger authentication for online transactions within the European Economic Area (EEA). Its main objectives are to enhance payment security, reduce fraud, and ensure customer data protection by mandating additional authentication steps during checkout.

# Embracing PSD2 compliance

As of December 31, 2020, the Revised Payment Services Directive (PSD2) came into force across Europe, with a later enforcement date of March 14, 2022, for the UK. This directive applies to all online transactions within the European Economic Area (EEA), from Austria to the UK.

## PSD2 preparedness with Recurly

Recurly helps you remain compliant by supporting Strong Customer Authentication (SCA) through **3D Secure (3DS)** for initial and one-time purchases. For subscription renewals, Recurly flags subsequent charges as **Merchant-Initiated Transactions (MITs)** whenever possible to minimize the need for repeated authentication — even for subscriptions started before December 31, 2020.

However, in some situations, SCA may still be required, and card issuers always have the final say on whether to challenge a transaction. In these cases, Recurly provides fallback options to help recover failed MIT charges.

For comprehensive guidance, we also offer a step-by-step readiness checklist to ensure your business is fully aligned with PSD2 requirements.

***

# Subscription reactivation and SCA

Under PSD2/SCA regulations, **resuming or reactivating a subscription** is a non-invoiced action, however the consumer should have their card re-verified to avoid compliance and fraudulent activity. These scenarios typically require **customer re-authentication** to comply with PSD2:

* **Resuming a paused subscription** → If a customer paused their subscription and later resumes it, SCA is required and the consumer should reverify their card on file prior to resuming the subscription.
* **Reactivating a canceled subscription** → If a customer cancels and later restarts their subscription, SCA is also required under PSD2.
* **Automatic retries after failed payments** → If a payment fails and is automatically retried without customer involvement, Recurly treats these as MITs. However, in some rare cases, issuers may still enforce SCA if they flag the transaction. In this case, utilize [3D Secure Dunning emails](https://docs.recurly.com/recurly-subscriptions/docs/dunning-configuration-for-3ds-2-declines#/) to help resolve these reauthentication requests from consumer banks.

> **Tip:** If you support subscription pauses or reactivation, make sure your integration supports 3D Secure challenges where needed to stay compliant.

You can find our implementation guide for verifying stored cards in our [API Guide for 3DS on Stored Billing Information](https://docs.recurly.com/recurly-subscriptions/v1.1/docs/using-3d-secure-with-stored-billing-information#/).

***

# “One Leg Out” scenarios

PSD2 applies only when **both** the merchant’s acquiring bank **and** the customer’s issuing bank are located in the European Economic Area (EEA) and the UK. If either party is outside the EEA or the UK, the transaction falls under a **“One Leg Out”** exemption:

* If the merchant is outside the EEA but the customer’s card issuer is within the EEA → PSD2 technically **does not apply**, but issuers **may still request SCA** at their discretion.
* If the merchant is inside the EEA but the customer’s card issuer is outside → The transaction is **out of PSD2 scope**, though issuers may still choose to enforce SCA.

Because card issuers have control over enforcement, and the industry is moving towards consumer driven authentication to reduce fraud and scams, Recurly recommends **supporting 3D Secure wherever possible** to avoid unnecessary declines and keep up with  wider industry trends.

***

# Steps towards PSD2 compliance with Recurly

Use this checklist to ensure full SCA support through Recurly:

1. **Engage with your gateway provider**
   Confirm your gateway supports 3D Secure 2.0 transactions and make any required updates. See our <Anchor label="Gateway-specific updates" target="_blank" href="https://docs.recurly.com/docs/gateway-specific-updates">Gateway-specific updates</Anchor>.

2. **Revise your Recurly setup**
   Enable SCA challenge flows during checkout. Use our <Anchor label="3DS2 implementation guide" target="_blank" href="https://docs.recurly.com/recurly-subscriptions/docs/3d-secure-20-integration-guide">3DS2 implementation guide</Anchor>.
   _Note: Hosted checkout pages automatically handle this step._

3. **Adjust your dunning flow**
   Configure your dunning settings and emails to manage SCA declines effectively. Learn more in our <Anchor label="dunning configuration guide" target="_blank" href="https://docs.recurly.com/docs/dunning-configuration-for-3ds-2-declines">dunning configuration guide</Anchor>.

4. **Test your integration**
   Review our <Anchor label="testing guide" target="_blank" href="https://developers.recurly.com/guides/3ds2.html">testing guide</Anchor> and use our <Anchor label="test cards" target="_blank" href="https://docs.recurly.com/docs/test">test cards</Anchor> to simulate 3DS2 flows.

***

# More resources

* [Adyen: PSD2 and SCA](https://www.adyen.com/blog/psd2-understanding-strong-customer-authentication)
* [Braintree: Preparing for PSD2](https://www.braintreepayments.com/blog/understanding-and-preparing-for-psd2-strong-customer-authentication/)
* [Stripe: SCA Guide](https://stripe.com/guides/strong-customer-authentication)
* [WorldPay: PSD2 Overview](https://www.worldpay.com/global/psd2)
* [Cybersource: 3D Secure and PSD2](https://www.cybersource.com/en-us/solutions/fraud-and-risk-management/3d-secure-and-psd2.html)

***

# FAQs

**Q: Do I need to worry about PSD2?**

**A:** If your business’ bank or payment provider is in the European Economic Area (EEA) and you have customers there too, then yes, you need to get ready for PSD2 and make sure you have Strong Customer Authentication (SCA) in place. If either you or your customers are outside the EEA, then you don't need to worry about SCA.

**Q: Where can I find more technical information on preparing for PSD2?**

A: You can find all the technical details you need in our integration guide <a href="https://dev.recurly.com/page/recurly-3d-secure-2-integration-guide" target="_blank">here</a>.

**Q: Will my checkout conversions change because of 3DS?****

**A:** The first version of 3DS could lead to a drop in checkout conversions between 3-15%. But don't worry, the second version aims to limit this to a maximum of 5%. Remember, these numbers can change depending on your country. (Statistics provided by WorldPay)

**Q: What's the effect of 3DS on authorization rates?**

**A:** If you're new to 3DS, you can expect your authorization rates to go up from about 84% to 92% with the first version. The second version aims to push this up to 95%. (Statistics provided by WorldPay)

**Q: Can 3DS help me reduce fraud?**

**A:** Yes, businesses not using 3DS reported fraud rates of about 0.29%. With the first version of 3DS, this went down to 0.12%. It's hoped the second version will reduce this even further to 0.05%. (Statistics provided by WorldPay).

**Q: Will 3DS slow down my transactions?**

**A:** Generally, using 3DS could add up to 10 seconds to your transaction time. If an exemption is rejected and SCA is enforced, this could add another 1-2 seconds. (Statistics provided by WorldPay)

**Q: Who can I turn to if I have more questions about PSD2, SCA, or 3DS?**

**A:** While we're always here to help, your payment gateway should be your go-to resource for these kinds of questions. They'll be up to speed on how PSD2 and SCA might affect you and your customers.

**Q: What about PayPal transactions?**

**A:** No extra work needed here! PayPal will take care of Strong Customer Authentication in their "Pay with PayPal" process. We will also make sure our integration can handle recurring PayPal payments.

**Q: Could 3DS be triggered on recurring payments that I initiate, especially if the value changes?**

**A:** Yes, it's possible. Card issuers can challenge a transaction for any reason. Because of this, we're developing a "3DS dunning flow" to help you manage transactions that fail due to SCA and need to be re-authenticated by your customer.

**Q: Will SCA be needed every time I re-bill a customer on a usage-based plan?**

**A:** As long as the transaction is flagged as being started by the merchant (that's you), most re-bills shouldn't need SCA, even if the amount varies. But remember, card issuers have the final say and can ask for SCA on any transaction.

**Q: I have a fixed subscription but the first month is prorated. Will the full charge in the second month need SCA?**

**A:** Ideally, you should authenticate the full subscription amount when the customer signs up, even if the first month is prorated. After that, re-bills should generally not need SCA, as long as they're flagged as merchant-initiated. We'll take care of this for you.

**Q: What if the original transaction happened before Sept 14, 2019? Will I need to authenticate all of these older transactions?**

**A:** For renewals, we'll try to exempt these transactions from SCA by marking them as "merchant-initiated". This includes subscriptions that started before September 14, 2019. Our goal is to treat these as merchant-initiated so they won't need SCA when they renew on or after September 14.
