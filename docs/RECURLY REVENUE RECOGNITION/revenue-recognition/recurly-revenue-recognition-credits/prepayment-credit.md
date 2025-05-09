---
title: Prepayment credit
excerpt: >-
  Prepayment credit in Recurly allows customers to pay in advance for purchases,
  streamlining the subscription process and enhancing financial flexibility.
  This feature allows businesses to pull balance credits information, enhancing
  their revenue recognition experience.
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

* Cancellation and refund policy that supports prepayment crediting.

### Limitations

* Prepayment credits can only be used for purchases and cannot be refunded.
* Specific configurations may restrict the use of prepayment credits for certain plans or products.

# Definition

Prepayment credit refers to an advance payment made by a customer for purchases or subscriptions with a business. This credit is stored in the customer's account and automatically applied to invoices as they are generated, simplifying the payment process.

# Key benefits

* **Streamlined revenue recognition**: Incorporating prepayment credits into revenue reports enhances financial accuracy by reflecting real-time customer balances and potential sales.
* **Enhanced financial reporting**: Prepayment credits contribute to a more comprehensive view of financial health, allowing for precise revenue tracking and forecasting in revenue recognition reports.
* **Increased operational efficiency**: The management of prepayment credits through automated systems simplifies the reconciliation process, ensuring that credits are accurately reported in financial statements, improving overall financial transparency and compliance.

# Key details

Customers are encouraged to make advance payments, known as prepayment credits, which are then applied to purchases. This process involves the issuance of two invoices in Recurly: one acknowledging the payment and the other representing the credit.

**Payment invoice**

<Image align="center" className="border" width="80% " border={true} src="https://files.readme.io/41591a7-image.png" />

**Credit Invoice**

<Image align="center" className="border" width="80% " border={true} src="https://files.readme.io/9ed19d1-image.png" />

Prepayment credits are integrated into the Revenue Recognition (RevRec) system as a single Sales Order (SO) line, accompanied by two invoices. Adjustments to the credit are recorded as new lines, identifiable by their origin and plan code.

| Origin       | Activity                   | Plan Code                  |
| ------------ | -------------------------- | -------------------------- |
| credit-event | prepayment credit issued   | credit-prepayment          |
| credit-event | prepayment credit redeemed | credit-prepayment redeemed |
| credit-event | Prepayment credit voided   | credit-prepayment-voided   |

<Image align="center" className="border" border={true} src="https://files.readme.io/00ce3ca-image.png" />

Customers can view their total credit balance in Recurly, which is equal to the total sell price of the credit lines. This balance is visible in the customer information section.

<Image align="center" className="border" width="45% " border={true} src="https://files.readme.io/0a9446b-image.png" />

Through prepayment credits, Recurly provides a flexible and efficient way for businesses and customers to recognize and manage advance payments, offering benefits such as improved cash flow, convenience, and simplified billing processes.
