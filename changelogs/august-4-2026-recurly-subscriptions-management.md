---
title: August 4, 2026 - Recurly Subscriptions Management
author: Tammy Pippin
hidden: false
published_at: '2026-07-29T19:37:13.081Z'
type: improved
---
The August 4th release brings compliance updates to Recurly's retries and a bug fix. Recurly now retries soft-declined transactions up to 20 times per 30-day period, aligning with card network retry rules. Merchants may see improved payment recovery rates as Recurly now fully utilizes the retry window permitted by card network rules.

| Release Date | **Feature**               | Type        | **Potential Impact** | **Description / Overview**                                                                                                                                                                                                                                                                                      |
| :----------- | :------------------------ | ----------- | :------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Aug 4, 2026  | **Intelligent Retries**   | Enhancement | Medium               | Recurly now retries soft-declined transactions up to 20 times per 30-day period, aligning with card network retry rules. Merchants may see improved payment recovery rates as Recurly now fully utilizes the retry window permitted by card network rules.                                                      |
| Aug 4, 2026  | **Tax Inclusive Pricing** | Enhancement | Low                  | You can now configure tax-inclusive regions independently of your tax integration, so these settings stay intact even if the tax integration is disabled. This gives you granular control over which accounts and subscriptions are tax inclusive vs. exclusive. Find this under Taxes → Tax Inclusive Regions. |
| Aug 4, 2026  | **Braintree Gateway**     | Bug fix     | Low                  | We've fixed an issue where Braintree PayPal nonces were not exchanged for a token when using a PUT to replace billing info. No integration changes are needed by merchants.                                                                                                                                     |

<br />