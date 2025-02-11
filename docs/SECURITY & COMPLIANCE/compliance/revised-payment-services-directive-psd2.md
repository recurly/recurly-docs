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

PSD2 (Revised Payment Services Directive) is a European Union directive that came into effect on December 31, 2020, and requires financial institutions to provide more secure authentication procedures for online transactions within the European Economic Area (EEA). Its main objective is to enhance the security of online payments, reduce fraud and ensure user data protection, by mandating additional authentication steps during the checkout process.

# Embracing PSD2 compliance

As of December 31, 2020, the Revised Payment Services Directive (PSD2) came into force across Europe, setting a new standard for the online transactions industry. With a later deadline of March 14, 2022 for the UK, this directive covers all online transactions within the European Economic Area (EEA), extending from Austria to the UK.

## PSD2 preparedness with Recurly

Recurly is committed to helping you smoothly transition into the era of PSD2. With our assistance, businesses can comply with SCA and implement 3DS for initial and one-time purchases. For subsequent renewal transactions, Recurly aims to exempt these transactions from SCA by marking them as Merchant Initiated Transactions (MITs), even for subscriptions that started prior to December 31, 2020. Be aware that in certain circumstances, subsequent MIT purchases may still require SCA, with card issuers having the ultimate say on any transaction. In such cases, Recurly is preparing to provide backup options to help recover MIT transactions that fail due to SCA.

To fully embrace the changes brought by PSD2, we've prepared a step-by-step readiness checklist, detailing what needs to be done to support SCA through Recurly. From contacting your gateway to ensuring you're ready for 3D Secure 2.0 transactions, to configuring your dunning flow and performing comprehensive testing, our guide will lead you through the process.

# Steps towards PSD2 compliance with Recurly

This checklist provides a step-by-step guide on how to ensure your SCA support through Recurly:

1. **Engage with your gateway provider:** Make sure your setup supports 3D Secure 2.0 transactions along with any other required modifications. Find out the necessary changes in our <a href="https://docs.recurly.com/docs/gateway-specific-updates" target="_blank">Gateway-specific Updates</a>.
2. **Revise your Recurly setup:** Enable SCA challenge flows during checkout. <a href="https://dev.recurly.com/page/recurly-3d-secure-2-integration-guide" target="_blank">Our Implementation Guide</a> provides detailed instructions. *Note: If you use our hosted checkout pages, this step is not required.*
3. **Adjust your dunning flow:** Set up your dunning flow and associated emails. You can learn more about this hosted flow in <a href="https://docs.recurly.com/docs/dunning-configuration-for-3ds-2-declines" target="_blank">our Documentation</a>. For those preferring a custom solution, refer to the implementation guide mentioned in Step 2.
4. **Practice makes perfect – Test!:** Review our testing notes in our <a href="https://developers.recurly.com/guides/3ds2.html" target="_blank">PSD2 Integration Guide</a>. You can also find test cards for use with the hosted pages <a href="https://docs.recurly.com/docs/test" target="_blank">here</a>.

# More resources

* <a href="https://www.adyen.com/blog/psd2-understanding-strong-customer-authentication" target="_blank">Adyen</a>: Dive deeper into understanding PSD2 and its implications with Adyen.
* <a href="https://www.braintreepayments.com/blog/understanding-and-preparing-for-psd2-strong-customer-authentication/" target="_blank">Braintree</a>: Navigate your preparations for PSD2 with this comprehensive guide from Braintree.
* <a href="https://stripe.com/guides/strong-customer-authentication" target="_blank">Stripe</a>: Explore Stripe's detailed guide on Strong Customer Authentication under PSD2.
* <a href="https://www.worldpay.com/global/psd2" target="_blank">WorldPay</a>: WorldPay's resource on PSD2 provides a global perspective on this regulation.
* <a href="https://www.cybersource.com/en-us/solutions/fraud-and-risk-management/3d-secure-and-psd2.html" target="_blank">Cybersource</a>: Learn about the intersection of 3D Secure and PSD2 with Cybersource.

# FAQs

**Q: Do I need to worry about PSD2?**

**A:** If your business’ bank or payment provider is in the European Economic Area (EEA) and you have customers there too, then yes, you need to get ready for PSD2 and make sure you have Strong Customer Authentication (SCA) in place. If either you or your customers are outside the EEA, then you don't need to worry about SCA.

**Q: Where can I find more technical information on preparing for PSD2?**

A: You can find all the technical details you need in our integration guide <a href="https://dev.recurly.com/page/recurly-3d-secure-2-integration-guide" target="_blank">here</a>.

**Q: Will my checkout conversions change because of 3DS?\*\***

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
