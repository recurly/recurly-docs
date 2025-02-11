---
title: Multiple gateway configuration
excerpt: ''
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

### Prerequisites

- An active Recurly account.
- Access to gateway providers as desired.
- Familiarity with your business's transaction routing needs.

### Limitations

- Transactions will be routed to the first gateway added by default, supporting its currency and card type unless custom routing or default settings are applied.
- The hierarchy should be thoroughly understood to ensure transactions are processed as intended.

# Definition

Multiple Gateway Configuration in Recurly allows merchants to set up various payment gateways. This functionality is essential for businesses looking to accept multiple payment types, process transactions in diverse currencies, or simply to have a backup in case a primary gateway faces downtime.

# Key benefits

- **Versatility**: Supports a wide range of payment methods and currencies.
- **Optimized transaction routing**: Prioritize which gateway processes specific transactions based on predefined criteria.
- **Business continuity**: Ensure uninterrupted transaction processing with Gateway Failover, rerouting payments if a primary gateway is unavailable.
- **Custom routing**: Tailor gateway use based on unique business needs.
- **Streamlined management**: Manage and view all gateway configurations from a centralized dashboard.

# Key details

## Gateway support

Merchants have the freedom to craft countless gateway combinations tailored to their business requisites. The typical approach involves selecting a blend of providers to facilitate support for an array of currencies and card types. Moreover, Recurly offers the capability to embrace various payment methods, ranging from credit cards, external gateway tokens, to Amazon Pay, PayPal, Apple Pay, ACH, and more.

## Gateway hierarchy

The order in which multiple gateways are added to Recurly matters. Initially, transactions will seek the first gateway on the list that can accommodate its specific card type and currency. Beyond this default behavior, Recurly has a strategic hierarchy for transaction routing:

### Hierarchy

1. Transactions with a gateway token (e.g., Vantiv Tokens, Braintree Token).
2. Transactions referencing a gateway_code (as seen in Custom Gateway Routing).
3. Non-credit card transactions like PayPal, Amazon Pay, Adyen HPP.
4. The default gateway for Credit Card transactions.
5. The non-default Credit Card gateway, prioritizing the one added earliest.

## Gateway setup

After zeroing in on the ideal providers and payment methods, follow [Recurly's comprehensive setup guide][5] to integrate additional gateways. It's vital to recognize that transactions, by default, get channeled to the earliest added gateway that is compatible with the given currency and card type. However, for businesses seeking finer control over this routing:

### Custom gateway routing

Recurly extends the facility to pinpoint precisely which gateway will handle a transaction, courtesy of our Custom Gateway Routing tool. Dive deeper into this feature and explore its nuances here.

### Setting a default gateway

Empower your business by setting a default gateway to handle credit card transactions. This takes precedence if the gateway is compatible with the transaction's card type and currency, and no specific gateway code has been assigned via Custom Gateway Routing.

1. Navigate to the Payment Gateways configuration page and pinpoint the "Default Gateways" section on the right.
2. Select "Edit Defaults."
3. Within the new window, choose the desired default gateway for each payment method displayed.
4. Confirm by clicking "Save."

## Gateway failover

To fortify your transaction processing against unforeseen issues, activate the Gateway Failover feature. This serves as a safety net, automatically rerouting transactions to a secondary gateway should the primary one face issues. The moment your primary gateway returns to full functionality, Recurly seamlessly shifts new traffic back to it, ensuring uninterrupted service.

# Setting up multiple gateways

### Accessing Your Account

- Log in to your Recurly account.
- From the Configuration section, navigate to the "Payment Gateways" section.

### Adding a new gateway

- Click on the “Payment Gateway Actions” dropdown and select “Add Payment Gateway”. 
- Choose your preferred payment gateway provider by selecting from the table of brand icons.
- Enter the necessary credentials or API keys related to the chosen provider.
- Confirm and save.

### Repeat for additional gateways

- To add more gateways, simply repeat the process by selecting different providers as needed.

## Setting a default gateway

### Navigate to Default Settings

- Within the "Payment Gateways" section, find the "Default Gateways" option in the sidebar.

### Edit defaults

- Click on "Edit Defaults."
- Assign a default gateway for each payment method listed in the new window.
- Confirm and save.

## Enabling gateway failover

### Access gateway failover settings

- Under the "Payment Gateways" section, find the "Gateway Failover" option in the sidebar.

### Gateway failover configuration

- On this page, you have the option to Enable or Disable gateway failover.
- Please note that directly setting Primary and Backup gateways through a dropdown list is not a feature available on this page.

## Review and test

### Transaction testing

- To ensure the correct functioning of all settings, initiate a few test transactions.
- Monitor how they get routed based on the configuration and hierarchy you've set up.

### Adjust as needed

- Based on your testing, you might need to adjust hierarchy, configuration, or default settings. Remember, you can revisit and modify these settings anytime to better suit your business needs.