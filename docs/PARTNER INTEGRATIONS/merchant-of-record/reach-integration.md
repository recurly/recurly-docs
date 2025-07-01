---
title: Reach integration
excerpt: >-
  A turnkey integration that lets you plug Reach’s global MoR capabilities—local
  gateways, tax, and fraud—directly into Recurly’s subscription management.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Required plan

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Prerequisites & limitations

* **Minimum annual volume:** Reach is best suited for merchants processing at least $10 million+ in annual revenue. This threshold allows Reach to negotiate and provision localized acquiring relationships with tier-1 processors on your behalf (<a href="https://www.chargebee.com/docs/payments/2.0/others/reach" target="_blank">chargebee.com</a>, <a href="https://www.withreach.com/who-we-help/digital-saas" target="_blank">withreach.com</a>).
* **Reach contract:** You must sign a master agreement directly with Reach to establish your merchant-of-record relationship. Once executed, Reach will generate the necessary credentials for:

  * One or more payment gateways (commonly Adyen, PayPal Complete, or Stripe)
  * Avalara for tax calculation and remittance
  * Kount for fraud screening (<a href="https://www.chargebee.com/docs/payments/2.0/others/reach" target="_blank">chargebee.com</a>, <a href="https://docs.recurly.com/docs/gateway-merchant-account-overview" target="_blank">docs.recurly.com</a>).

# Definition

Reach is a merchant-of-record (MoR) and payment orchestration platform designed to simplify global subscription and SaaS expansion by handling local payment processing, tax compliance, and fraud management. Through our partnership with Recurly, Reach provides merchants with a turnkey solution to plug in localized payment gateways (e.g., Adyen, PayPal Complete), tax engines (Avalara), and fraud tools (Kount) directly into Recurly’s subscription flow. By acting as the MoR, Reach assumes liability for compliance, tax remittance, and chargeback risk, while ensuring a seamless, localized checkout experience for end-customers (<a href="https://recurly.com/partner/expand-globally-with-recurly-reach/" target="_blank">recurly.com</a>, <a href="https://www.withreach.com/who-we-help/digital-saas" target="_blank">withreach.com</a>).

# Key benefits

* **Accelerate global expansion:** Eliminate the need to set up multiple international merchant accounts—Reach provides localized acquiring in 60+ markets, reducing time-to-market and operational overhead.
* **Simplified tax compliance:** Automated, real-time tax calculation and remittance through Avalara ensure you stay compliant in every jurisdiction Reach supports—without managing separate tax registrations or manual returns.
* **Advanced fraud protection:** Integration with Kount’s device fingerprinting and machine-learning models helps minimize fraud-related declines while approving legitimate orders, maintaining conversion rates and protecting revenue.

# Key details

## Obtaining Reach-issued credentials

1. **Payment gateway credentials**: After contract execution, Reach will provision and provide API keys (or equivalent credentials) for one or more local payment processors—typically Adyen or PayPal Complete (sometimes Stripe)—depending on your target markets and preferred payment rails. These credentials ensure that Recurly routes authorizations through Reach’s acquiring relationships in each region (<a href="https://www.chargebee.com/docs/payments/2.0/others/reach" target="_blank">chargebee.com</a>, <a href="https://recurly.com/partner/expand-globally-with-recurly-reach" target="_blank">recurly.com</a>).

2. **Tax engine credentials (Avalara)**: Reach will issue a set of Avalara API credentials (Account Number and License Key) scoped to your Reach account. These credentials enable Recurly to invoke Avalara’s rates-and-rules engine for accurate, real-time tax calculation and automated remittance across multiple jurisdictions (<a href="https://www.chargebee.com/docs/payments/2.0/others/reach" target="_blank">chargebee.com</a>, <a href="https://www.withreach.com/who-we-help/digital-saas" target="_blank">withreach.com</a>).

3. **Fraud management credentials (Kount)**: Reach configures a Kount profile on your behalf, providing API credentials that allow Recurly to send transaction data for risk screening. Kount’s device fingerprinting and behavior analytics help minimize declines and fraudulent transactions while preserving legitimate orders (<a href="https://recurly.com/partner/expand-globally-with-recurly-reach/" target="_blank">recurly.com</a>, <a href="https://www.withreach.com/who-we-help/digital-saas" target="_blank">withreach.com</a>).

## Configuring Recurly

Once you have your Reach-provided credentials, follow these steps within the Recurly admin console:

1. **Configure payment gateways**

   * Navigate to **Billing → Payment Gateways**.
   * Select the processor matching your Reach credentials (e.g., **Adyen** or **PayPal**).
   * Enter the API credentials supplied by Reach (e.g., API Key, Merchant Account, Client ID/Secret).
   * Enable any region-specific settings (currencies, settlement schedules) as instructed by Reach.
   * Save and verify that the gateway status is **Active** (<a href="https://docs.recurly.com/docs/gateway-merchant-account-overview" target="_blank">docs.recurly.com</a>, <a href="https://recurly.com/integrations" target="_blank">recurly.com</a>).

2. **Enable Avalara for tax calculation**

   * Go to **Billing → Taxes** in Recurly.
   * Choose **Avalara** as your tax engine.
   * Input the Avalara **Account Number** and **License Key** provided by Reach.
   * Configure any Nexus settings or tax jurisdictions if needed (Reach may pre-configure these based on your contract).
   * Click **Save**, then run a test invoice to confirm that Avalara returns correct tax amounts for various jurisdictions (<a href="https://docs.recurly.com/docs/gateway-merchant-account-overview" target="_blank">docs.recurly.com</a>, <a href="https://recurly.com/integrations" target="_blank">recurly.com</a>).

3. **Enable Kount for fraud screening**

   * Navigate to **Billing → Fraud Tools**.
   * Select **Kount** from the list of fraud management providers.
   * Enter the **Kount API Key** (Site ID and API Key) furnished by Reach.
   * Choose the risk threshold and review settings recommended by Reach’s implementation guide.
   * Save your settings.
   * Perform a staged transaction to verify that Kount logs appear in Recurly’s fraud dashboard, and that risk decisions (approve, review, decline) align with expectations (<a href="https://recurly.com/partner/expand-globally-with-recurly-reach" target="_blank">recurly.com</a>, <a href="https://recurly.com/integrations" target="_blank">recurly.com</a>).

## Testing and verification

1. **Test transactions**

   * Process a series of sandbox transactions across target regions (e.g., EU, APAC, LATAM) to confirm:

     * **Routing:** Payments route through Reach’s acquiring relationships (e.g., Adyen or PayPal) and settle in the correct local currency.
     * **Tax Calculation:** Avalara returns accurate sales tax, VAT, or GST for each jurisdiction.
     * **Fraud Screening:** Kount consistently flags test scenarios (synthetic cards, velocity anomalies) according to your risk rules.

2. **Review settlement reports**

   * In Recurly, verify that settled transactions appear with Reach’s acquiring entity (e.g., “Reach via Adyen”) in the **Billing → Transactions** report.
   * Check that settlement amounts and remittance schedules align with the terms negotiated by Reach.

3. **Monitor chargebacks and disputes**

   * Confirm that any test chargeback flows (e.g., a disputed payment) route through Reach’s dispute process. Reach assumes liability for chargebacks and will handle retrieval requests; these should not flow directly to your legal team unless escalated.