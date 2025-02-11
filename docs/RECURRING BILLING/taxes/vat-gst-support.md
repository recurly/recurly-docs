---
title: VAT & GST support
excerpt: >-
  Navigate the complexities of global taxation with ease. Recurly's VAT & GST
  support ensures compliance and accuracy, tailored for your business needs.
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

* Ensure you have access to the Business Entities configuration in your Recurly account.
* Familiarize yourself with the tax regulations of the countries you operate in.

### Limitations

* Tax rates are based on current regulations and may change. Always stay updated with local tax authorities.
* The system applies default tax rates for each country. Custom rates need manual configuration.

# Definition

VAT (Value Added Tax) & GST (Goods and Services Tax) are consumption taxes applied to the value added to goods and services. These taxes are levied at each stage of the production or distribution process, and the end consumer typically bears the final tax cost.

# Key benefits

* **Current regulation adherence**: Tax rates are based on current regulations and may change. Always stay updated with local tax authorities.
* **Default rate application**: The system applies default tax rates for each country. Custom rates need manual configuration.

# Tax registration numbers

Set up default VAT and Tax Registration Numbers in the Business Entities configuration to display on all your invoices. While these settings cater to your merchant business, separate fields are available to record your customers' Tax Registration Numbers on their account records.

### Country-specific tax registration numbers

For businesses registered in multiple countries, configure unique VAT Numbers and Tax Registration Numbers for specific customer invoices. For instance, if you're registered in Turkey, display both your Turkish VAT number and Tax Registration Number on invoices for Turkish customers. Access this feature via the Advanced Settings link or navigate to Configuration → Taxes → Tax Settings.

## Country-specific tax details

## Australia

Enabling tax collection in Australia will apply 10% GST to all taxable plan, add-on or adjustment line items for customers in Australia.

| Tax Region | Tax Type | Minimum Address Requirement |
| :--------- | :------- | :-------------------------- |
| AU         | GST      | Country                     |

### AU GST on digital services

On July 1, 2017, Australia started requiring non-resident businesses with digital services sales in Australia past a specific threshold to register and collect GST from Australian customers. This change includes exemption for Australian businesses with an active and GST registered ABN, and the collection of two pieces of location evidence from customers that are taxed.

## Canada

Enabling tax collection in Canada will apply 5% GST to all taxable plan, add-on or adjustment line items for customers in Canada. Additional province level taxes (PST, HST, or QST) will be applied if you enable the province as a taxable sub-region and the customer is located in that province. If you want to collect only GST from all provinces in Canada, enable Canada, but do not select a province.

| Tax Region | Tax Type                                | Minimum Address Requirement |
| :--------- | :-------------------------------------- | :-------------------------- |
| CA         | GST  \\nGST/PST  \\nGST/HST  \\nGST/QST | Postal Code and Country     |

## Chile

Enabling tax collection in Chile will apply 19% VAT to all taxable plan, add-on or adjustment line items for customers in Chile.

| Country | Tax Rate | Minimum Address Requirement |
| :------ | :------- | :-------------------------- |
| Chile   | 19%      | Country                     |

## Europe (no EU)

Enabling tax collection in a non-EU European country will apply that country's VAT rate to all taxable plan, add-on or adjustment line items for customers in the country.

All countries have a Tax Type of *VAT* and a Minimum Address Requirement of *Country*.

## European Union

The European Union VAT system has many rules and requirements, so we have created a separate page dedicated to EU VAT. Read the full details on our European Union VAT support [here](https://docs.recurly.com/eu-vat-2015).

## Mexico

Enabling tax collection in Mexico will apply 16% VAT to all taxable plan, add-on or adjustment line items for customers in Mexico.

| Tax Region | Tax Type | Minimum Address Requirement |
| :--------- | :------- | :-------------------------- |
| MX         | VAT      | Country                     |

## Indonesia

Enabling tax collection in Indonesia will apply 10% VAT to all taxable plan, add-on or adjustment line items for customers in Indonesia.

| Tax Region | Tax Type | Minimum Address Record |
| :--------- | :------- | :--------------------- |
| ID         | VAT      | Country                |

## Israel

Enabling tax collection in Israel will apply 17% VAT to all taxable plan, add-on or adjustment line items for customers in Israel.

| Tax Region | Tax Type | Minimum Address Requirement |
| :--------- | :------- | :-------------------------- |
| IL         | VAT      | Country                     |

## New Zealand

Enabling tax collection in New Zealand will apply 15% GST to all taxable plan, add-on or adjustment line items for customers in New Zealand.

| Tax Region | Tax Type | Minimum Address Requirement |
| :--------- | :------- | :-------------------------- |
| NZ         | GST      | Country                     |

## South Africa

Enabling tax collection in South Africa will apply 15% VAT to all taxable plan, add-on or adjustment line items for customers in South Africa.

| Tax Region | Tax Type | Minimum Address Requirement |
| :--------- | :------- | :-------------------------- |
| ZA         | VAT      | Country                     |

## Thailand

Enabling tax collection in Thailand will apply 7% VAT to all taxable plan, add-on or adjustment line items for customers in Thailand. VAT rate is scheduled to increase to 10% on Sept 30, 2019.

| Tax Region | Tax Type | Minimum Address Requirement |
| :--------- | :------- | :-------------------------- |
| TH         | VAT      | Country                     |

## United Kingdom

Enabling tax collection in the United Kingdom will apply 20% VAT to all taxable plan, add-on or adjustment line items for customers in the United Kingdom.

| Tax Region | Tax Type | Minimum Address Rec |
| :--------- | :------- | :------------------ |
| GB         | VAT      | Country             |

# Setting up VAT & GST in Recurly

### 1. **Accessing Business Entities Configuration**

* Log in to your Recurly account.
* Navigate to the main dashboard.
* On the left sidebar, click on Configuration.
* From the dropdown, select Business Entities.

### 2. **Setting up default tax registration numbers**

* Within the Business Entities section, locate the Tax Registration Numbers area.
* Enter your default VAT Number and Tax Registration Number in the respective fields.
* Click Save to apply changes.

### 3. **Configuring country-specific tax registration numbers**

* Still within the Business Entities section, find and click on the Advanced Settings link.
* Alternatively, navigate to Configuration > Taxes > Tax Settings.
* Here, you can specify different VAT and Tax Registration Numbers for each country you're registered in.
* Click Add Country, select the desired country from the dropdown, and input the respective VAT and Tax Registration Numbers.
* Repeat for all countries as necessary.
* Click Save to store these settings.

### 4. **Enabling tax collection for specific countries**

* Navigate to Configuration > Taxes.
* Here, you'll see a list of countries. Click on the country you wish to enable tax collection for.
* Toggle the Enable Tax Collection switch to the 'ON' position.
* The system will automatically apply the default tax rate for that country. If you wish to set a custom rate, input the desired percentage in the Tax Rate field.
* Ensure the correct Tax Type (VAT or GST) is selected from the dropdown.
* Click Save.

### 5. **Setting Up province or state-specific taxes (e.g., for Canada)**

* If you're enabling tax collection for a country with province or state-specific taxes, you'll see an additional section labeled Sub-regions.
* Click Add Sub-region, select the desired province or state, and input the respective tax rate.
* Click Save.

### 6. **Reviewing and testing**

* Once you've set up all desired tax settings, it's crucial to review and test them.
* Create a test invoice for a customer from one of the countries you've configured.
* Ensure the correct tax rate is applied and that the invoice displays the appropriate VAT or Tax Registration Number.
* If everything looks correct, your setup is complete. If not, revisit the previous steps to troubleshoot and correct any discrepancies.
