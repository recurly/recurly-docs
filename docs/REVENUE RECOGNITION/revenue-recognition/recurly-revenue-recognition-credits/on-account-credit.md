---
title: On-account credit
excerpt: >-
  Leverage your on-account credits with Recurly Revenue Recognition. This
  feature allows businesses to pull reports for the "on-account credit",
  encouraging loyalty programs implementation.
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

### Additional cost

To access this feature or setting, you must have an active subscription to either the Recurly Revenue Recognition Advanced or the Standard edition. For further information on pricing and how to enable this feature on your account, please contact your Recurly account manager directly, or reach out to us at [support@recurly.com](mailto:support@recurly.com).

### Prerequisites

* Cancellation and refund policy that supports account crediting.

### Limitations

* On-account credits are non-transferable between accounts.
* Credits may be subject to expiration as per the business's terms and conditions.

# Definition

On-account credit in Recurly refers to the balance credited to a customer's account instead of a direct refund. This occurs when a customer cancels a subscription plan and is eligible for a refund. Rather than returning the money to the original source, Recurly offers the option to credit the account, which can be applied towards purchases. This is accurately portrayed in the Recurly Revenue Recognition reports.

# Key benefits:

* **Streamlined revenue recognition**: Incorporating on-account credits into revenue reports enhances financial accuracy by reflecting real-time customer balances and potential sales.
* **Enhanced financial reporting**: On-account credits contribute to a more comprehensive view of financial health, allowing for precise revenue tracking and forecasting in revenue recognition reports.
* **Increased operational efficiency**: The management of on-account credits through automated systems simplifies the reconciliation process, ensuring that credits are accurately reported in financial statements, improving overall financial transparency and compliance.

# Key details

When a customer's subscription is canceled and a refund is issued, Recurly can credit the customer's account instead of providing a refund. This on-account credit can be utilized for any purchases within Recurly's platform.

Upon issuing on-account credit, Recurly generates a credit invoice, reflecting the credited amount and any subsequent redemptions. The invoice is updated to show the remaining balance of the credit, offering transparency and ease of tracking for both the customer and the business.

### Credit invoice example

The credits and their redemptions are recorded in Recurly Revenue Recognition as distinct entries, allowing for clear financial tracking and reporting. These entries are categorized based on their origin (credit-event) and specified by unique plan codes, enabling easy identification and reconciliation.

<Image align="center" className="border" width="80% " border={true} src="https://files.readme.io/8ed64f5-image.png" />

### Accounting table for on-account credits

| Origin       | Activity                   | Plan code                  |
| ------------ | -------------------------- | -------------------------- |
| credit-event | on-account credit Issued   | credit-on-account          |
| credit-event | on-account credit Redeemed | credit-on-account-redeemed |
| credit-event | on-account credit Voided   | credit-voided              |
| credit-event | on-account credit Refunded | credit-paid                |

<Image align="center" className="border" border={true} src="https://files.readme.io/ccb7b62-image.png" />

This feature not only enhances customer satisfaction by providing flexible refund options but also streamlines financial processes, making it a valuable tool for businesses looking to improve their subscription management and accounting practices.
