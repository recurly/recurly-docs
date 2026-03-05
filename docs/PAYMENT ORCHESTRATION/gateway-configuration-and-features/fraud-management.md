---
title: Fraud management
excerpt: >-
  Attract a larger audience and secure customer trust with superior fraud
  prevention mechanisms built right into your Recurly setup, courtesy of Kount's
  expertise.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<Callout icon="❗️">
  **Kount Command will be deprecated in favor of Kount 360**

  In April 2026, Recurly will be migrating all Kount merchants to Kount 360. There are no integration changes necessary, and no settings changes required for your account. Some settings are no longer supported in Kount 360, and will be marked as such below.
</Callout>

# Overview

### Required plan

This feature or setting is available to all customers on Professional and Elite subscription plans. To request to upgrade to this plan, please reach out to your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) for more details.

### Limitations

* New card verifications (both sign-ups and billing info updates) are subject to risk inquiries. Existing accounts with a credit/debit card on file are not scrutinized unless their billing information is updated.
* The efficacy of fraud detection might be influenced by the quality and completeness of the transaction and customer data provided.

# Definition

Recurly's Fraud Management is a comprehensive suite of tools designed to identify and counteract fraudulent activities in real-time. This page is about how we help merchants fight fraud.

# Key benefits

* **Real-time fraud detection:** Our system analyzes transactions as they happen, providing instant alerts on suspicious activities, helping you prevent fraudulent transactions before they occur.

* **Integrated with Kount:** Leveraging Kount, a leading fraud management integration partner, we ensure your transactions are secure and your business is protected against evolving fraud tactics.

* **Enhanced payment security:** Utilizing AVS (Address Verification Service) and CVV (Card Verification Value) checks to add an extra layer of security, reducing the likelihood of fraudulent transactions.

# Key details

## Fraud Management Functionality

### Kount

We use Kount as our main fraud management integration partner to maximize fraud protection. To know more about our Kount integration, please visit our dedicated page. [Kount Integration](https://docs.recurly.com/docs/kount)

### AVS and CVV Verification

We also utilize AVS and CVV responses from our gateway partners as part of our fraud prevention measures. To understand the details and the process to enable these features, please visit our payment settings page. [Payment Settings](https://docs.recurly.com/docs/payment-settings)

# Fraud Management Configuration

To configure the fraud management settings, navigate to Configuration → Fraud Management in your Recurly account. This area allows you to customize your fraud detection and prevention measures to fit your business needs, ensuring you're equipped to handle the challenges of online payment fraud.

On this initial page, you can find an overview of the fraud management settings, providing a snapshot of whether this critical feature is active and how it is configured. To view any fraudulent transactions, click on ‘View All’ if you have access to a dashboard (Enterprise only merchants). To tailor these settings to your needs, click on the ‘Configure Settings’ button located in the upper right corner.

## Enabling fraud management

Set the status to ‘Enable’ to activate real-time fraud management monitoring, ensuring your transactions are scanned for suspicious activities.

<Image align="center" border={true} src="https://files.readme.io/199fcaa-Screen_Shot_2024-06-21_at_12.42.32_PM.png" className="border" />

## Decline threshold rules

### High risk decline

<Callout icon="📘" theme="info">
  This configuration will be unavailable in Kount 360.
</Callout>

Utilizing Kount's extensive data and logic, this feature gives a detailed analysis of transactions, checking for connections to fraudulent activities outside of Recurly's network. Any transaction identified as High Risk by Kount will be automatically declined.

<Image align="center" border={true} src="https://files.readme.io/69df826-Screen_Shot_2024-06-21_at_12.42.52_PM.png" className="border" />

> **Note:** This setting is overridden if a risk score decline level of 75+ is chosen.

### Risk score decline threshold

This setting allows you to define the risk score threshold that, if exceeded by a transaction, will trigger an automatic decline. A higher Risk Score setting means a more lenient approach to risk, potentially reducing the number of declined transactions. Conversely, a lower Risk Score setting indicates a stricter risk threshold, leading to more declined transactions.

Adjust this threshold by selecting an option from the dropdown menu to align with your organization's risk tolerance.

<Image align="center" border={true} src="https://files.readme.io/d647cf4-Screen_Shot_2024-06-21_at_12.43.10_PM.png" className="border" />

## Fraud velocity rules

<Callout icon="📘" theme="info">
  This configuration will be unavailable in Kount 360.
</Callout>

These rules restrict the frequency of attempts made using the same credit/debit card, IP address, email, or device for entering or updating billing information.

<Image align="center" border={true} src="https://files.readme.io/3458bd2-vel_rules_edited.png" className="border" />

> **Note:** There is a default for all velocity rules which can be found in your Recurly fraud management settings. This number provides a balanced approach to fraud prevention, but you may change it at your discretion. Setting this value to 0 turns off the velocity rule entirely, removing the restriction on attempt frequency. While possible, this is not recommended.

### Velocity rules for credit cards

This rule restricts how often billing information can be updated using the same credit or debit card number within a single hour. It's designed to prevent excessive attempts that might indicate fraudulent activity.

### Velocity rules for IP addresses

Similar to credit cards, this rule limits the number of times billing information updates can occur from the same IP address within an hour, helping to identify and mitigate potential fraud.

### Velocity rules for email addresses

This rule sets a cap on the number of billing information updates that can be made with the same email address over a 24-hour period. It's a crucial step in controlling fraud linked to email-based manipulation.

### Velocity rules for devices

This regulation controls the frequency of billing updates initiated from the same device within an hour, offering an additional layer of security by monitoring device-specific activity.

## Blocked countries

<Callout icon="📘" theme="info">
  This configuration will be unavailable in Kount 360.
</Callout>

<Image align="center" border={true} width="80% " src="https://files.readme.io/4fce49a-Screen_Shot_2024-06-21_at_12.45.05_PM.png" className="border" />

You have the option to automatically reject transactions originating from countries you designate as high risk. This automatic decline activates when the customer's transaction BIN (Bank Identification Number) Country is a match with any selected on your deny list. This rule is specifically applied to credit card transactions, enhancing your fraud prevention measures by geography.

<br />
