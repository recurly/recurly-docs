---
title: TSYS
excerpt: >-
  Enhance your payment operations with the TSYS Gateway, designed to integrate
  seamlessly with Recurly, facilitating secure and efficient transactions for
  merchants in the US.
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

This payment gateway or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

- A TSYS Summit Merchant ID / V# and associated Configuration information

### Limitations

#### Limitations

- Available only for US-based merchants
- Supports transactions in US Dollars only
- Requires the merchant bank to share necessary credentials with Recurly
- TSYS Sierra (Terminal Settlement) Merchant IDs are not supported

# Definition

TSYS Gateway is a crucial intermediary that fosters connections between merchant banks and Recurly, thereby facilitating smooth and secure transaction processes for US-based merchants.

# Key details

| Feature                         | Description                                                    |
| ------------------------------- | -------------------------------------------------------------- |
| Services that work with Recurly | Purchases, Recurring Billing                                   |
| Supported operations            | Purchase, Refund, Void                                         |
| Supported payment types         | Credit Card transactions                                       |
| Supported card brands           | Visa, MasterCard, American Express, Discover, JCB, Diners Club |
| Gateway Specific 3DS2 Supported | No                                                             |
| Card on File Supported          | Yes                                                            |
| Regions                         | United States                                                  |
| Currencies                      | USD                                                            |

## Getting started

To initialize the connection between your TSYS Gateway and Recurly, begin with the establishment of a merchant profile using the Host Capture (Summit platform) for Recurly, version 1.0. Following its creation, you may log into your Recurly site and [enable the gateway](https://docs.recurly.com/docs/tsys#step-by-step-process-to-enable-tsys-gateway).

##### DBA Name Adjustments

Because TSYS requires at least five (5) characters sent in certain fields, if your site subdomain (subdomain.recurly.com) is less than five characters (example: abc.recurly.com), then you will need to add a site DBA name that is at least five characters.

You may consider adding a legal business type at the end of your DBA for example: Acme, Inc versus just Acme.  
The absence of this provision will default the system to the site name, triggering a failure in all transactions.

#### New Merchant Accounts

We’ve made it easy for those setting up new merchant accounts. After logging into your Recurly account, go to Configuration, Payment Gateways and click on TSYS. On the right you will see the Apply button. Click to apply for a new merchant account in TSYS.

#### Existing Merchant Accounts

Merchants with existing accounts should seek the creation of a TSYS Merchant Profile via the merchant bank using the Host Capture on the Summit platform.  
Post creation, you may enable TSYS directly within your Recurly Payment Gateway settings.

> **Note**: In the event of modifications in address or contact details, reach out to the merchant account provider to avoid any disruptions in service due to outdated merchant profiles.

##### Merchant Geography

Though confined to merchants with a US presence, TSYS extends its services globally, processing credit card transactions for customers worldwide.

##### Address and CVV Requirements

Emphasizing user-friendliness, TSYS abstains from imposing minimum requirements for address details and dispenses with the necessity for Card Security Code configurations, simplifying recurring billing processes.

# Step-by-step process to enable TSYS gateway

Follow this step-by-step process to enable the TSYS Gateway within your Recurly account:

1. **Merchant profile**: Reach out to your merchant bank to establish a TSYS Merchant Profile through the Host Capture (Summit platform) for Recurly, version 1.0.
   - **New Merchant Accounts**: If you're setting up a new merchant account, create or log in to your Recurly account and complete the payment gateway setup process to apply for a new merchant account. After you have obtained credentials, please move to Step 2.
   - **Existing Merchant Accounts**: For existing merchant accounts, collaborate with your merchant bank to initiate a TSYS Merchant Profile using the Host Capture on the Summit platform and continue to Step 2.
2. **Gather necessary details**: Accumulate vital details including your POS ID, Authentication Code, and zip code following the creation of the merchant profile. If you have a V#, please also provide it in your setup.
3. **DBA name**: Navigate to the site settings on your Recurly account and designate a DBA (Doing Business As) name with a minimum length of 5 characters IF your site subdomain is less than five (5) characters (example: abc.recurly.com is a 3 character subdomain, so would require this step). This step is pivotal to avoid transaction failures.
4. **Gateway configuration**: 

- Access your Recurly site and navigate to **Payment Gateways → Add a Payment Gateway** and choose TSYS. 
- Enter your TSYS credentials including the following: POS ID, Authentication Code, and Zip Code. Enter your V# (can start with a ‘7’) if you have it.
- If you do not want to use TSYS as a failover option, check the box labeled ‘Exclude from Gateway Failover’. 
- Select the card types you have set up at TSYS under ‘Accepted Credit Card Types’.
- Save your Payment Gateway Settings.

### Integration notes

- **Address and CVV Requirements**: TSYS is designed for recurring billing, eliminating the need for Card Security Code (CSC) configurations. Additionally, TSYS doesn't impose minimum address requirements.
- **Currency Support**: The TSYS integration is available for US merchants, supporting transactions solely in US Dollars. To accept additional currencies, integrate with other gateways.
- **Merchant Geography**: Although TSYS caters to US-based merchants, it facilitates the processing of credit cards globally, enhancing your business reach.
- **Update on changes**: In the case of any amendments in your address or contact details, notify your merchant account provider promptly to avoid service interruptions due to outdated merchant credentials.
- **Combination with other gateways**: To expand currency acceptance, TSYS can be coupled with other gateways, thereby facilitating a broader financial operation.

Keep these notes in mind to ensure a smooth and successful integration process with the TSYS Gateway through Recurly.