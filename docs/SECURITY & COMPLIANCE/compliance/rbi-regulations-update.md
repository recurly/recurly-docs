---
title: RBI regulations
excerpt: >-
  Navigate the new RBI e-mandate guidelines for recurring transactions with
  ease, ensuring compliance and reducing payment failure rates.
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

The Reserve Bank of India's (RBI) new regulations on e-mandates for recurring transactions aim to enhance the security and control of cardholders over such transactions. With a focus on transparency, the guidelines demand pre-transaction notifications and limit e-mandate transactions to INR 15,000 (raised from 5,000 previously), among other mandates.

# Key benefits

* **Enhanced transparency:** The RBI's regulations require issuing banks to provide their credit card users with detailed pre-transaction notifications, enhancing customer awareness and control over their finances.
* **Increased security:** With a cap on e-mandate transactions, customers are safeguarded against high-value unauthorized transactions, necessitating additional authentication for transactions exceeding INR 15,000.
* **Ease of subscription cancellation:** The new guidelines allow customers to cancel subscriptions directly through their bank account, bypassing the need to engage with the merchant for this purpose.

# Key details

## RBI's new regulations on e-mandates for recurring transactions

As of October 1, 2021, all issuing banks in India are required to adhere to the Reserve Bank of India’s (RBI) new regulations concerning e-mandates for recurring transactions. Merchants who fail to comply may experience increased payment failure rates for these transactions.

**Key mandates under the RBI framework include:**

1. Issuing banks are required to send a notification of the upcoming recurring charge to their credit card holders 24 hours prior to the charge. These alerts, delivered via SMS or email at the customer's preference, need to inform the cardholder about the merchant's name, transaction amount, date and time of the charge, among other details.
2. E-mandate transactions are now capped at INR 15,000 (approximately 180 USD at the time of this writing). Transactions exceeding this amount will necessitate additional factors of authentication (AFA).
3. Customers now have the ability to cancel a subscription directly through their bank account, eliminating the need to contact the merchant.

## Affected transactions and implications of non-compliance

This new directive affects all recurring transactions on Indian-issued credit and debit cards, including OTT subscriptions, bill payments, and other subscription-based services. Businesses operating in INR may see increased transaction failure rates starting September 30, 2021, if they fail to comply with the new RBI guidelines.

Recurly is actively working with its gateway partners to align with these mandates and to prevent transaction declines. We're updating our gateway integrations to provide issuing banks with the necessary information to comply with the RBI’s guidelines.

## Recurly's response to the RBI's new guidelines

To minimize the impact of these changes on your business, we recommend ceasing standard recurring payments for customers in India due to the high risk of declines, and instead, utilize Recurly’s new dunning campaigns. These automated messages will inform your Indian customers about expected payment declines and guide them on how to activate customer-initiated transactions (CIT). Offering multi-month or annual subscriptions can also be an effective strategy to reduce monthly confirmations by customers. With Recurly’s prepaid account balance functionality, you can allow subscribers to add to their prepaid account balance, and then decrement subscribers’ account balances monthly.\
For any additional questions, feel free to contact us. Your success in navigating these new RBI regulations is our priority.
