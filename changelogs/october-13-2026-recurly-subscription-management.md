---
title: October 20, 2026 - Recurly Subscription Management
author: Jenn Schnoes
hidden: false
metadata:
  robots: noindex
published_at: '2026-10-08T19:32:27.374Z'
---
<br />

| Release Date | Feature             | Type        | Potential Impact | Description / Overview                                                                                                                                                                                                                                            |
| ------------ | ------------------- | ----------- | ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Oct 20       | Nuvei Gateway       | Enhancement | Low              | When onboarding Nuvei, merchants worldwide will be able to see and select the gateway in the Payment Gateways page.                                                                                                                                               |
| Oct 20       | Cybersource Gateway | Bug fix     | Med              | For migrated merchants, we have addressed a sandbox issue where 3DS was not reliably triggering, and partial authorizations were not being voided properly.                                                                                                       |
| Oct 20       | Invoice Templates   | Enhancement | Low              | Invoice templates now let you show or hide the merchant billing email address. This setting is on by default, so the email address continues to appear on invoices unless you turn it off.                                                                        |
| Oct 20       | Account Hierarchy   | Enhancement | Low              | Merchants using Account Hierarchy can now control whether and when a child account's billing target can<br />change. Requires Account Hierarchy to be<br />enabled; contact Recurly support to turn on this feature.                                              |
| Oct 20       | App Management      | Enhancement | Low              | Populating `/external_subscriptions.last_purchase` for Google Play managed subscriptions consistently when receiving lifecycle events.                                                                                                                            |
| Oct 20       | App Management      | Enhancement | Low              | Updated the v3 `/external_subscriptions` response to contain references to the `external_product` and `plan` if the merchant has linked a plan through the `/external_product_references`.                                                                        |
| Oct 20       | V3 API              | Enhancement | Low              | Added parity between the v3 `/subscriptions` and `/purchases` endpoints, with both supporting `vat_reverse_charge_notes`, `customer_notes`, `terms_and_conditions`, and `credit_application_policy` at the subscriptions\[] level to persist to the subscription. |