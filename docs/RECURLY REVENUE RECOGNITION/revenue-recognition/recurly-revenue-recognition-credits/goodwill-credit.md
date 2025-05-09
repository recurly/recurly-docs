---
title: Goodwill credit
excerpt: >-
  Boost purchases by recognizing goodwill credits with Recurly Revenue
  Recognition. This feature allows businesses to bring credit information
  directly into revenue recognition.
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

* Goodwill credits are non-transferable and must be used within the issuing account.
* Credits may have expiration dates or usage conditions, depending on the business policy.

# Definition

Goodwill credit is a complimentary credit balance given to customers as a gesture of goodwill. This credit can be applied toward purchases, facilitating payment adjustments and enhancing customer loyalty. Importantly, this system allows for seamless integration into the customer's Enterprise Resource Planning (ERP) system or revenue recognition ecosystem, streamlining reporting and financial tracking.

# Key benefits

* **Streamlined revenue recognition**: Incorporating goodwill credits into revenue reports enhances financial accuracy by reflecting real-time customer balances and potential sales.
* **Enhanced financial reporting**: Goodwill credits contribute to a more comprehensive view of financial health, allowing for precise revenue tracking and forecasting in revenue recognition reports.
* **Increased operational efficiency**: The management of goodwill credits through automated systems simplifies the reconciliation process, ensuring that credits are accurately reported in financial statements, improving overall financial transparency and compliance.

# Key details

To support business growth and enhance customer satisfaction, companies can issue goodwill credits. These credits serve as a balance in the customer's account, applicable towards purchases. 

When goodwill credit is allocated, Recurly generates a credit invoice, reflecting the credit balance which can be adjusted against subsequent payments. This process not only simplifies account management but also ensures transparency in financial transactions.

<Image align="center" className="border" width="80% " border={true} src="https://files.readme.io/82c8766-Screenshot_1_2024-03-04_at_4.45.08_PM.png" />

The issuing and redemption of goodwill credits are accurately documented, facilitating seamless financial reporting. Credits are recorded as a single line in revenue recognition reports, with redemptions detailed separately. This clear delineation helps businesses track credit usage and its impact on financial health.

The following table outlines the identifiers for goodwill credit transactions:

| Origin       | Activity          | Plan Code                |
| ------------ | ----------------- | ------------------------ |
| credit-event | Goodwill issued   | credit-goodwill          |
| credit-event | Goodwill redeemed | credit-goodwill-redeemed |
| credit-event | Goodwill voided   | credit-goodwill-voided   |

<Image align="center" className="border" border={true} src="https://files.readme.io/19cd870-image.png" />

In instances where goodwill credit is issued erroneously or remains unused, it can be voided, removing the balance from the customer's account. This action, along with all other credit transactions, is recorded in Revenue Recogntion, ensuring comprehensive financial oversight.

<Image align="center" className="border" border={true} src="https://files.readme.io/efb1208-image.png" />
