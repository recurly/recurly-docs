---
title: App Management - Recurly Revenue Recognition Advanced
excerpt: >-
  Efficiently manage and integrate app data from Apple Store and Google Play
  Store into Recurly Revenue Recognition with tailored grouping, performance
  obligations, and data rules.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Required plan

This feature is part of our product, Recurly Revenue Recognition Advanced. \[<a href="https://docs.recurly.com/docs/recurly-revenue-recognition-advanced" target="_blank">Learn more here</a>].

# Definition

Recurly Revenue Recognition Advanced has the capability to handle data from both the App Store and the Play Store data, whether it’s from Apple or Android. To manage App Management data, a few straightforward configurations must be done in Recurly Revenue Recognition Advanced.

# Key benefits

* **Streamlined data management:** Easily group App Management data based on subscription source, ensuring accurate and efficient data handling.
* **Flexible revenue recognition:** Define exclusive POBs for App Management data, allowing for revenue recognition on an overtime basis.
* **Enhanced data rules:** Copy Google fees to the "App Fees" attribute and assign distinct account numbers for both Apple and Google Store data.
* **Seamless integration:** With the App Management Integration, effortlessly flow App Management data into Recurly Revenue Recognition Advanced.

# Grouping configuration

Configure your system to group order lines based on the subscription's source (Apple Store or Google Play Store).

The App Management data is organized by subscription. Therefore, you need to create two separate grouping rules using the contract grouping feature in Recurly Revenue Recognition Advanced:

* **Apple Store Grouping Rule**: Set the grouping attribute to "Source = Apple Store."
* **Play Store Grouping Rule**: Set the grouping attribute to "Source = Play Store."

This setup ensures that order lines are accurately grouped by the subscription source.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/c12a5169c1ba7c997669e14fa3e4ffa32b6a7b9bb9744cec662251558ae07f88-1_Grouping_Config.png" />

# Performance obligation

We define an exclusive Performance Obligation (POB) for App Management data, where revenue is recognized over time.

This POB, known as **App Subscription**, is automatically assigned to any order line in a contract that meets the Recurly Revenue Recognition Advanced Rules for either "Play Store" or "Apple Store" data.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/e4b80b6217c0f05b40f6172ec21e405d0b1185473a5dcc1c5b23eee5e1f86555-2_POB.png" />

The POB rules are based on the source of the data, ensuring that all order lines with the specified source are grouped under the **App Subscription** POB.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/77f5d669bd2139deb12466c6119b28e9a3c272e9cc04094b0691334566d27e82-3_POB_Rules.png" />

The hierarchy of these rules is critical to guaranteeing the correct obligation is applied.

<br />

# Data rule configuration

To ensure accurate revenue recognition, you need to configure data rules that transform App Management data correctly. Specifically, you must copy the sell price from "Google Fees" lines to the "App Fees" attribute and assign proper account numbers for data originating from the Play Store and Apple Store.

We have defined four data rules:

### Data rule 1 - Copy Google fees to app fees

Copies the sell price from "Google Fees" lines into the "App Fees" attribute.

**Rule:**

| Application Attribute | Formula        |
| :-------------------- | :------------- |
| App Fees              | Line.SellPrice |

**Criteria:**

| Field | Operator | Value       |
| :---- | :------- | :---------- |
| Plan  | =        | Google Fees |

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/6ce5c2ecf7e0343039efd0c9cf37d3b8f1151eaa89492acb3b69bc867052e0d6-4_Data_Rule.png" />

<br />

### Data Rule 2 - Zero out Google fees

Sets the sell price of the Google Fees plan to zero to avoid duplicative charges.

**Rule:**

| Application Attribute | Formula |
| :-------------------- | :------ |
| App Fees              | 0       |

**Criteria:**

| Field | Operator | Value       |
| :---- | :------- | :---------- |
| Plan  | =        | Google Fees |

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/14ab1e62d857d59865b8ed09371367da4df6e629723f87c270bf4dd280cba05d-5_Data_Rule_2.png" />