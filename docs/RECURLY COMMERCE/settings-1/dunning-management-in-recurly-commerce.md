---
title: Dunning management in Recurly Commerce
deprecated: false
hidden: true
metadata:
  robots: index
---
# 💸 Managing payment failures and dunning

### What is dunning?

Dunning is an automated payment management process that allows a merchant to set up retries for failed payment methods on a specific frequency and send reminders about an outstanding due from a declined payment method.

### Dunning configuration

Recurly Commerce offers configuration of the Dunning process in the “Settings” tab of the Recurly Commerce portal. Merchants may choose from 3 Dunning options to implement for their subscribers and can choose whether contracts go into a paused or cancelled state once dunning is complete:

**Prive’s standard dunning setting**: Subscription contracts will be automatically canceled when they complete dunning with this setting. The subscriber’s payment method will be retried every 2 days for a maximum of 5 times.

![](https://files.readme.io/3bf5832600003bd3b17e282c64e971bfa1f39b855cec40f27f8e237e8810ca0a-image.png)

**Retry-after failed billing:** Merchants can choose the number of days and the number of retires a subscriber’s payment method will be retried **after** the expected renewal date. Merchants can also choose whether contracts will be paused or canceled once dunning is complete.

![](https://files.readme.io/af06f66ba65c9cbc0dcfd02450a5fa2edc05b99c51cdbda69a470a8f756f9046-image.png)

**Retry before failed billing:** Merchants can choose the number of days and the number of retires a subscriber’s payment method will be retried before the expected renewal date. Merchants can also choose whether contracts will be paused or canceled once dunning is complete.

![](https://files.readme.io/e42f13d781adc8e6abba25442334c698dc1c6ad63279f0b9700b9b85ab657d78-image.png)

### Payment failure notification

The “**Failed payment method”** communication is a highly recommended transactional notification that can be configured on in the notifications tab of the Recurly Commerce app. This comm notifies customers when their order could not be placed due to a payment failure and includes a link to their customer portal where the customer can login and reset their billing information.

![](https://files.readme.io/6b7f0ec80fa3dbde857f2708efc35c769674f6c576da4ea56bc51d44a037fc56-image.png)

### Reset billing information

As a merchant, while you cannot reset the billing information for the subscriber, you can navigate to the “customers” tab, select the subscriber in question, scroll down to the “Billing & Shipping” section of the subscription contract, and select the “send email to reset” button.

This action will send an email to the subscriber where they will click a link that redirects them to update their billing information with Shopify payments. This will automatically update in the Recurly Commerce system.

![](https://files.readme.io/b320e86d113266aa9acb2cfb4a106ac6ceb882de0f94865aa9b716080bd45f21-image.png)

### Process failed payment

Once the failed payment has been updated, as a merchant, you can select the “process now” button in the subscription contract of the subscriber in question. This will immediately charge their payment method and if the transaction is successful, the next order will renew immediately. Selecting “process now” will not interrupt the future renewal dates of the contract.

![](https://files.readme.io/fe4a69f7fba47c5ab1fdff5e35f3a3093106bb827a4b5dc0fc014303222eb956-image.png)