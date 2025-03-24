---
title: Shopify migration
excerpt: >-
  Migrating to Shopify-Recurly Integration: A comprehensive guide for merchants
  transitioning from other services to a unified Shopify-Recurly subscription
  platform.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Prerequisites

* Merchant is currently using another Shopify subscription service.
* Shopify powers the checkout with supported payment methods (currently, credit cards via Shopify Checkout).
* A non-Production Recurly site is set up and configured.
* The Recurly Shopify app is installed in the merchant’s Shopify store.

### Limitations

* **Inactive Subscriptions**: Inactive (expired) subscriptions are not imported by default. Recurly Professional Services can assist with importing these.
* **Historical Data**: Past data is not migrated; it must be preserved externally.
* **Payment Methods**: Google Pay, Apple Pay, PayPal, and ShopPay are not yet supported.
* **Pre-paid Subscriptions**: Subscriptions with billing models such as “bill annually, deliver monthly” are not supported.
* **Discounts**: Certain Shopify discounts (e.g., “Buy X get Y”, “Free Shipping”) and specific discount requirements are not migrated.
* **Valid Payment Method Requirement**: Active subscriptions without a valid payment method will fail to import and need manual intervention.

# Key benefits

* **Seamless Transition**: Migrate active subscriptions with minimal downtime and disruption.
* **Unified Management**: Centralize subscription management under the Shopify-Recurly platform.
* **Enhanced Customer Experience**: Communicate changes clearly and provide customers with an updated, robust portal for managing their subscriptions.

# Definition

This guide outlines the process for migrating active subscriptions from a legacy Shopify subscription app to the Shopify-Recurly integration. The migration is coordinated by Recurly Professional Services, ensuring accurate mapping of customer and subscription data while maintaining subscription start dates and status.

# Key details

## Required before migration

1. **Develop a Communication Strategy**: Inform active customers about the migration, disable automatic email notifications from the previous subscription app to avoid confusion, and clearly communicate that the customer portal URL will change.
2. **Schedule the Migration**: Plan the migration during a low-activity period to minimize discrepancies between data export and the migration process.
3. **Ensure Customer Data Compliance**: Verify that Shopify Checkout requires both first and last names, as this is mandatory for new subscriptions and the migration.
4. **Prepare the Recurly Site**: [Set up and configure](https://docs.recurly.com/docs/shopify-early-access#/)  your non-Production Recurly site with the necessary custom fields, currencies, coupon settings, and site configurations. (
5. **Install and Configure the Recurly Shopify App**: Install the app in your Shopify store and create equivalent Recurly plans for every active subscription to ensure proper associations during migration.

## Migration process

1. **Export Subscription Data**: Export essential subscription data from your current service for at least seven test subscriptions, including key fields such as the Shopify customer ID and payment method ID.
2. **Submit Data for Migration**: Provide the exported data to Recurly Professional Services to initiate the migration process.
3. **Import Subscriptions**: Recurly will import the subscriptions by creating new customer accounts with active subscriptions, preserving the original start dates.
4. **Review Import Results**: Examine the import report for any subscriptions that failed to import due to issues (like missing valid payment methods) and address these manually.
5. **Verify Subscription Status**: Confirm that subscriptions marked as paused in the export remain paused after the import.

## Post migration considerations

1. **Cancel Legacy Subscriptions**: Once test migrations are verified, cancel the corresponding subscriptions in the previous app to avoid duplicate communications.
2. **Archive Historical Data**: Preserve any necessary historical data before uninstalling the legacy migration app.
3. **Update the Customer Portal Link**: Modify your Shopify theme to include a link to the new Recurly customer portal.
4. **Communicate Changes to Customers**: Clearly inform your customers about the new customer portal URL and any related changes.
5. **Complete the Production Migration**: After successful test migrations, repeat the process for all active subscriptions on your Recurly Production site, following your established communication strategy and timeline.