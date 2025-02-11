---
title: Native Mobile SDKs
excerpt: >-
  Elevate your mobile app experience with seamless integration of recurrent
  payments.
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

### Limitations

The SDKs are platform-specific, meaning separate integrations are required for Android and iOS.

# Definition

Native Mobile SDKs are software libraries provided by Recurly, designed specifically for Android and iOS platforms. They enable swift integration of recurrent payment functionalities within mobile applications.

# Key benefits

- **Quick and easy integration**: Integrate swiftly into existing mobile applications.
- **Secure payment handling**: Manage sensitive payment information securely and reduce PCI compliance concerns.
- **Seamless user experience**: Enjoy native app integration for a smooth user interface.
- **Direct encryption and storage**: Safeguard payment details with direct encryption and storage through Recurly.
- **Enhanced functionalities**: Access Recurly's robust API for extended features.

# Introduction to Recurly's Native Mobile SDKs

Recurly's Native Mobile SDKs are designed to simplify the integration of recurrent payment systems within your mobile applications. Whether you're building a subscription-based service, a content platform, or any other mobile application requiring recurrent payments, our SDKs are tailored to meet your needs.

## How the SDKs work

Upon the customer's submission of the payment form within your app, the SDKs take over. They securely send the customer's payment information to Recurly, where it's encrypted and stored. In return, you receive an authorization key. This key, combined with our API, allows you to complete the subscription process, ensuring a smooth transaction without compromising security.

## Security and PCI compliance

One of the significant advantages of using Recurly's Native Mobile SDKs is the reduction in PCI scope. Since the sensitive payment information is directly sent from the customer's device to Recurly, your application doesn't handle or store this data. This direct transfer ensures that the payment details remain secure, and your app remains compliant with PCI requirements.

### Integration steps

1. **Integrate the SDK**: Depending on your platform (Android or iOS), download the respective SDK source code from Recurly's official repository.

> **Note: **For information on how to implement the SDKs, you can refer to the **<a href="https://recurly.com/developers/api/#mobile-sdks" target="_blank">Recurly API Documentation</a>**.

2. **Initialize the SDK**: Within your app, initialize the SDK using your Recurly account credentials.
3. **Implement the payment form**: Design and implement the payment form within your app, ensuring it captures all necessary details.
4. **Handle submissions**: Set up event listeners to handle form submissions. Upon submission, the SDK will send the payment details to Recurly.
5. **Receive authorization key**: Once the payment details are securely sent to Recurly, you'll receive an authorization key, or token, in return. Use this token in server-side calls to Recurly's API to complete the subscription process.

# Support and documentation

For a deeper understanding, detailed integration steps, and troubleshooting, refer to the comprehensive documentation provided with each SDK. Additionally, Recurly's support team is always available to assist with any challenges or queries you might have during the integration process.