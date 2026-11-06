---
title: November 10, 2026 - Recurly Subscription Management
author: Jenn Schnoes
hidden: true
published_at: '2026-11-06T17:15:45.098Z'
---
<br />

| Release Date | Feature         | Type        | Potential Impact | Description / Overview                                                                                                                                                                                                               |
| ------------ | --------------- | ----------- | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Nov 10       | Revolv3 Gateway | Enhancement | Low              | We'll be storing the target gateway used in Revolv3's orchestration to inform merchant reporting. No integration updates are necessary to receive this update.                                                                       |
| Nov 10       | Ebanx Gateway   | Bug fix     | Low              | A cosmetic issue was fixed that caused auth codes to not display for card transactions. No integration updates are necessary to receive this update.                                                                                 |
| Nov 10       | Vantiv Gateway  | Bug fix     | Low              | We've updated handling of response format errors when non-Vantiv gateway tokens are sent to Vantiv via custom gateway routing. The response will not reflect invalid data, and no integration changes are necessary for integrators. |
| Nov 5        | Ebanx Gateway   | Bug fix     | High             | An issue with status updates has been released early, addressing an issue where realtime status updates were not being reflected in reporting. No integration updates are necessary to receive this update.                          |