---
title: November 10, 2026 - Recurly Subscription Management
author: Jenn Schnoes
hidden: false
metadata:
  robots: noindex
published_at: '2026-11-06T17:15:45.098Z'
---
An early November 5th fix addressed a high-priority EBANX issue where real-time transaction status updates were not being reflected in reporting — resolved automatically with no integration changes required. The November 10th release follows up with two additional EBANX and Vantiv bug fixes: auth codes now display correctly for EBANX card transactions, and Vantiv will handle errors more gracefully when non-Vantiv gateway tokens are routed to the platform via custom gateway routing.

On the new features side, Recurly now offers an Unprocessed Notifications export for App Management merchants, surfacing Apple and Google lifecycle notifications that couldn’t be processed along with the identifiers needed to resolve them — available exclusively to merchants with app store connections enabled. Revolv3 merchants will also see the target gateway used reflected in reporting, with no integration changes needed.

| Release Date | Feature         | Type        | Potential Impact | Description / Overview                                                                                                                                                                                                                                                                                                                                 |
| ------------ | --------------- | ----------- | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Nov 10       | Revolv3 Gateway | Enhancement | Low              | We'll be storing the target gateway used in Revolv3's orchestration to inform merchant reporting. No integration updates are necessary to receive this update.                                                                                                                                                                                         |
| Nov 10       | Exports         | Enhancement | New              | Recurly now offers an Unprocessed Notifications - External export that lists App Management external subscriptions with notifications from Apple and Google that couldn’t be processed, along with the identifiers needed to resolve them. This new export will only be available to merchants who have enabled the connections to app stores feature. |
| Nov 10       | Vantiv Gateway  | Bug fix     | Low              | We've updated handling of response format errors when non-Vantiv gateway tokens are sent to Vantiv via custom gateway routing. The response will not reflect invalid data, and no integration changes are necessary for integrators.                                                                                                                   |
| Nov 10       | Ebanx Gateway   | Bug fix     | Low              | A cosmetic issue was fixed that caused auth codes to not display for card transactions. No integration updates are necessary to receive this update.                                                                                                                                                                                                   |
| Nov 5        | Ebanx Gateway   | Bug fix     | High             | An issue with status updates has been released early, addressing an issue where realtime status updates were not being reflected in reporting. No integration updates are necessary to receive this update.                                                                                                                                            |

<br />

<br />