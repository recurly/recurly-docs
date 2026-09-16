---
title: September 01, 2026 - Recurly Subscription Management
author: Jenn Schnoes
hidden: false
published_at: '2026-08-28T21:20:12.732Z'
---
This release introduces opt-in support for Adyen’s Checkout API v72, allowing merchants to meet compliance mandates and unlock new features, and resolves an issue for Cybersource merchants using Recurly HPP or Checkout by eliminating errors from unexpected 3DS attempts when 3DS isn't enabled. User experience enhancements to Compass Assistant.

| Release Date | Feature             | Type        | Potential Impact | Description / Overview                                                                                                                                                                                                                                               |
| ------------ | ------------------- | ----------- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Sep 1        | **Adyen Gateway**   | Enhancement | Medium           | Recurly now supports Adyen’s Checkout API v72. This update is strictly opt-in and will not impact your live traffic without coordination. If you need v72 for compliance requirements or to unlock new features, please contact Support to enable the configuration. |
| Sep 1        | Cybersource Gateway | Bug fix     | Low              | We've addressed an issue causing unexpected 3DS attempt errors for Cybersource merchants using Recurly HPP or Checkout without 3DS enabled.                                                                                                                          |
| Sep 1        | Compass             | Enhancement | Low              | User experience enhancements to Compass Assistant including full screen mode, streaming responses and chat history tweaks.                                                                                                                                           |