---
title: Sales taxes
excerpt: >-
  Navigate the complexities of global sales tax with Recurly's comprehensive
  guide. From the U.S. to the EU, understand rates, rules, and best practices
  for seamless tax collection.
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

- Familiarity with your business's tax obligations in the regions you operate.

### Limitations

- Recurly's out-of-the-box tax calculations are based on Avalara's AvaTax. For advanced tax rules and rate mappings, integration with Avalara AvaTax Pro or Vertex is required.
- Custom credit adjustments in Recurly do not support tax calculations.
- In sandbox mode, Avalara's Address Validation cannot be tested, and minor variations in applied tax rates might be observed.

# Introduction to sales tax

Recurly is a leading subscription billing platform. We collaborate with Avalara and Vertex to facilitate sales tax billing and collection worldwide.

This page outlines our fundamental taxation feature, Recurly Taxes, which is powered by Avalara. Recurly Taxes provides essential sales tax compliance for specific use cases and regions. 

- Recurly’s in the box tax solution does not support tax calculation for regions aside from those included on this page.  For wider global sales tax support, consider our [Direct Integration with Avalara AvaTax](https://docs.recurly.com/docs/avalara). 
- Recurly Taxes supports tax-inclusive pricing through Avalara AvaTax, Vertex, and Recurly's own In-The-Box taxes. Learn more about [Tax Inclusive Pricing](https://docs.recurly.com/docs/tax-inclusive-pricing).
- Recurly Taxes do not handle communications taxes and surcharges. For these needs, explore our [Avalara for Communications](https://docs.recurly.com/docs/afc) integration.

Recurly is not a tax expert. Our tools are designed to help merchants comply with local sales tax and VAT laws, but we do not guarantee tax compliance. 

For advice on laws applicable to your business, consult a sales tax professional. They can provide guidance on local laws in your service areas. If you need a referral to a tax professional, contact our support team, and we'll connect you with a firm that can assist.

> 👍 For more advanced options, connect your own Avalara AvaTax Pro or Vertex account:
> 
> - Access to many more taxable regions
> - Detailed product taxability rules
> - Advanced tax reporting
> - Tax filing services
> 
> Discover more about <a href="https://docs.recurly.com/docs/avalara">Avalara AvaTax Pro</a> and <a href="https://docs.recurly.com/docs/vertex">Vertex</a>.

# Go live with taxes checklist

To start tax collection with Recurly, follow these steps. We recommend testing your tax configurations in sandbox mode before applying them to your production Recurly site.

1. Activate the[ tax countries and/or state/provinces](https://docs.recurly.com/docs/tax#section-taxable-regions) where you plan to collect tax. This step will make tax options visible on your plan and account pages.
2. Decide [which customer address to tax](https://docs.recurly.com/docs/tax#customer-taxable-address) where applicable: the Billing address or Account address. 
3. Ensure your <a href="#section-which-address-fields-to-collect">existing and new customer addresses</a> are accurate, enabling correct tax calculations upon going live.
4. Verify that your <a href="#section-your-merchant-address">merchant address(es)</a> meets the requirements for tax calculations.
5. Set the [taxable addresses](https://docs.recurly.com/docs/tax#determining-taxable-addresses) you prefer to use for each of your business entities directly on the business entity. This allows you to control which taxable addresses associated with an invoice to send the service as the Origin Address and Destination Address for tax calculation.
6. Identify <a href="#section-exempt-customers">tax-exempt customers</a> and mark their accounts accordingly.
7. <a href="#section-taxable-plans-and-adjustments">Modify all relevant plans</a> to enable "Tax Collected." _This action will initiate tax collection on invoices for both new and existing subscribers to the plan. However, it will not apply taxes to invoices that have already been generated, only new ones created after tax collection was applied to the corresponding plan._
8. Update your checkout pages to include <a href="#section-tax-previews-at-checkout">tax previews</a>.



# Determining Taxable Addresses

With every invoice that is generated, there are two (2) types of addresses passed to your site’s tax service that the tax service uses for tax calculation. The first type of address is the “Origin Address,” which is intended to represent the seller’s (your) business address, and the second type of address is the “Destination Address,” which is intended to represent the buyer’s (customer) location where the goods or services are used or fulfilled. Once the appropriate taxable addresses are sent to your tax service provider, the tax service will assess the Origin and Destination address values and use those locations to identify the appropriate tax rate to apply to the invoice. Once the tax service applies the necessary tax rate, tax is calculated, and the tax location, rate, and amount are added and displayed on the invoice. 

There are two (2) address types that can be applied to the Origin and/or Destination addresses. These are known as the invoice’s “taxable addresses”. The taxable address options from the invoice represent the merchant’s taxable address and the customer’s taxable address.  

## Merchant Taxable Address

The merchant’s taxable address will always reflect the appropriate business entity tax address. On the business entity configuration page(s), you can decide whether to use the same address for both invoice display as well as taxation, or you can set one address for invoice display and a separate one for taxation. However you want to set up your business entity addresses is completely up to you and your needs. You can use the same addresses across some or all of your entities, or you can have unique addresses set for each of your business entities. In all scenarios, the entity address used for taxation will always be used as your merchant taxable address on invoice.

**Business Entity where the same address is used for both invoice display and taxation.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9490870-Screenshot_2024-06-06_at_9.44.56_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]




**Business Entity where a different address is used for invoice display versus taxation**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3508a11-Screenshot_2024-06-06_at_9.43.52_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]




## Customer Taxable Address

The customer’s taxable address will always reflect the appropriate customer address to be used for taxation based on the type of invoice, your site’s Tax Settings, and which customer addresses are present on a given invoice. 

There are **three (3) types of customer addresses** that can be used as the customer’s “taxable” address.

- Account Information address
- Billing Information address
- Shipping Information address 

The **Account Information address** is always used as the customer’s taxable address on **manual invoices**, **unless there is a customer shipping address on the invoice**. You also have the option to enable using the customer Account Info address as the customer taxable address for all invoices generated across your site on the Tax Settings page. This will also ensure that the Account address of your customer is always used as the “Bill To” address presented on the invoice.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1b1e2d0-Screenshot_2024-06-11_at_2.25.27_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


To enable or disable using the Account address as the customer taxable address for all invoices, visit the "Tax Settings" page. This option is disabled out-of-the-box.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6e7280d-Screenshot_2024-06-11_at_12.44.48_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


The **Billing Information address** is always used as the customer’s taxable address on all **automatic invoices, unless there is a shipping address present on the invoice,** or if the Tax Settings option to use the Account Info address for the taxable address on all invoices is enabled.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dd6b481-Screenshot_2024-06-11_at_8.04.03_PM.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "300px",
      "border": true
    }
  ]
}
[/block]


The **Shipping address is always used as the customer’s taxable address on any invoice where there is a Shipping address applied**. Regardless of whether the invoice is manual, automatic, or if you have the Account Info address overriding option enabled on Tax Settings, customer Shipping addresses will always be used for the customer taxable address if there is one available on the invoice.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/155b94a-Screenshot_2024-06-11_at_2.26.13_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


#### Multiple Shipping Addresses

Some invoices will have [multiple unique shipping addresses](https://docs.recurly.com/docs/shipping-address-per-line-item#shipping-addresses-per-purchase) on them. Since tax is calculated at the line-item level on an invoice, Recurly will send the unique tax shipping address for each line item to the tax service if "Customer tax address" is set for the Origin/Destination addresses based on the Business Entity applied to the given invoice. 

Common scenarios where this can occur are when [Account Hierarchy Invoice Rollup](https://docs.recurly.com/docs/ah-invoice-rollup) and/or [Calendar Billing](https://docs.recurly.com/docs/calendar-billing) are enabled on your site. 

If different tax rates are used for each line item based on the end-customer's shipping destination, "Tax" on the invoice will show a generic "Tax" label, with the final comprehensive tax amount accounting for the total dollar amount in taxes applied for all line items. There will also be a section on the invoice that will show each shipping address's state/country code, corresponding tax rate, and cumulative tax amount for each tax rate for your customer's reference. 

**Sample invoice displaying tax  behavior when multiple shipping addresses are present **

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/39e4e93-multi_shipping_address.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "75% ",
      "border": true
    }
  ]
}
[/block]


## Setting Taxable Addresses

Controlling which taxable addresses from invoices to send to your tax service is configurable at the Business Entity level. Each of your business entities has a “Tax Settings” section, where you can set the taxable address(s) to use for the Origin Address and Destination Address.

> 👍 Keep in mind
> 
> If a customer and/or plan is "tax exempt," no tax will be applied to the invoice and/or subscription.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b0a13d1-Screenshot_2024-06-06_at_9.47.06_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]




By default, **Recurly sets all entity taxable address configurations to use the Business Entity Tax Address as the Origin Tax Address and the Customer Tax Address as the Destination Tax Address**. Choosing to keep these default settings on an entity’s Taxable Address configuration  will ensure that all invoices where the given business entity is applied will send the merchant's entity tax address as the Origin Address to the tax service, and the customer’s taxable address from the invoice as the Destination Address to the tax service.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6876f6c-Screenshot_2024-06-06_at_9.31.37_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


**Sample invoice where Business Entity tax address is used for the origin address, and Customer tax address is used for the destination address. This is the default/standard behavior for all Business Entities unless overridden. **

Here, you see that the tax rate applied to the invoice is based off the customer's taxable address, which used the Denver, Colorado sales tax amount. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8463c4b-Screenshot_2024-06-11_at_3.11.17_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


However, you can override these settings if you wish to do so. Some merchants require that the merchant’s taxable address be used for both the Origin and Destination Addresses, and others may require that the customer’s taxable address be used for both the origin and destination addresses. Recurly supports merchants in controlling which taxable addresses to send their tax service for this reason.

> 🚧 Using the merchant’s taxable address for the Origin Address and the customer’s taxable address for the Destination Address is standard practice for most regions.
> 
> You should consult your accounting and/or compliance team to determine which taxable address configuration is best for you and your business entity/entities. By choosing to override these default settings, your invoices may ignore standard tax rules from the tax service, such as reverse VAT.

Since in the vast amount of cases, tax services use the Destination Address to calculate tax off of, if your business requires that all customers be taxed based off of your business entity’s tax address, you can try setting the Business Entity Tax Address to be used for both the Origin and Destination Addresses.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a4d250b-Screenshot_2024-06-06_at_10.02.15_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


**Sample invoice where Business Entity tax address is used for both origin and destination address values**

Here, you see that as both the origin and destination addresses used the Business Entity tax address for tax calculation, the resulting tax rate applied to the customer's invoice is based off of the GB VAT rate amount of 20%, since the merchant is located in the United Kingdom.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/46c9707-Screenshot_2024-06-11_at_3.05.09_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


**Sample invoice where Business Entity tax address is used for both origin and destination address values**

In this example, the Business Entity is located outside of the United States, and the Customer is located within the United States. The resulting tax rate applied to the customer's invoice is based off of the GB VAT rate amount of 20% since the merchant is located in the United Kingdom.

> 🚧 If you choose to make both the origin and destination address values use the Business Entity tax address, and the Business Entity tax address is outside of the United States, the VAT prefix shown on the invoice will show "USST" for United States Sales Tax instead of the local country code prefix. The correct tax rate will still apply to the invoice based on the Business Entity's taxable address location.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b9362c2-Screenshot_2024-06-11_at_2.47.18_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


Some US states require that a customer’s address be used for both the Origin and Destination address for particular goods, or if a merchant ships from a warehouse but does not maintain a taxable address at the warehouse location. In this case, you can try setting the Customer Tax Address to be used for both the Origin and Destination Addresses.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/88ae714-Screenshot_2024-06-06_at_10.04.49_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


**Sample invoice where Customer tax address is used for both origin and destination address values**

Here, you see that the tax rate applied to the invoice is based off of the customer's taxable address, which is out of Wyoming. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/927dd57-Screenshot_2024-06-11_at_2.41.58_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


Keep in mind that whichever taxable address configuration you set on your business entity will apply to all invoices associated with that entity. However, you can set unique taxable address configurations for each of your business entities. This allows merchants with different taxation requirements in varying global regions to successfully apply taxes to invoices based on the expected tax application behavior for each legal entity. 

If you decide to change your business entity’s taxable address configuration settings at any point, no historic invoices will be impacted. All invoices generated after updating the taxable address settings will assume the new behavior.

## Taxable Addresses for one-time-charges

Recurly supports taxable address settings for one-time-charges via UI and both API versions for merchants on Recurly's Elite plan. 

The taxable address settings for charges will assume the settings from the business entity that will be applied to the invoice by default. However, you can choose to override this default behavior in the event that you require separate tax calculation behavior for one-time-charges than you do for standard subscription purchases.

The screenshot below shows an example of a merchant creating a new charge on a customer account. To ensure tax is applied to the invoice, the customer must not be tax-exempt, and the checkbox must be enabled under "Tax Collection." 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d5b7a87-Screenshot_2024-07-02_at_4.12.49_PM.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "70% ",
      "border": true
    }
  ]
}
[/block]


Once "Tax Collection" is enabled, you will see a new section on the charge expand to provide you the ability to override the Business Entity taxable address configurations for the given charge. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cc827b9-Screenshot_2024-07-02_at_4.15.32_PM.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "70% ",
      "border": true
    }
  ]
}
[/block]


At this point, if you decide to create the charge without enabling the option to "Override taxable address settings from business entity," the taxable addresses used for the charge will leverage the Origin and Destination addresses from the invoice based on the configurations set on the specific business entity that is applied to that charge invoice. In other words, the charge will follow the same taxable address behavior as [subscriptions](https://docs.recurly.com/docs/tax#setting-taxable-addresses) do.  

Alternatively, you can enable the "Override taxable address settings from business entity" checkbox, and set your desired values for the Origin and Destination addresses for the given charge. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b702ee9-Screenshot_2024-07-02_at_4.26.14_PM.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "70% ",
      "border": true
    }
  ]
}
[/block]


The tax calculated for the invoice will reflect the overriding taxable address settings applied to the charge. 

If there are multiple charges on a single invoice, you can set distinct taxable address settings for each charge/line item. Tax will be applied for each line item on the charge invoice based on each line item's individual taxable address settings. 

## Which address fields to collect

To accurately calculate tax, you need specific minimum address fields in the customer's taxable address (as detailed above). Invoices lacking these minimum address fields in the customer address will be posted without tax.

### Minimum address requirements

- [Australia](#section-australia): Country
- [Canada](#section-canada): Country and postal code
- [Chile](#section-chile): Country
- [Europe (Non-EU)](#section-europe-non-eu-): Country
- [European Union](#section-european-union): Country
- [Indonesia](#section-indonesia): Country
- [Israel](#section-israel): Country
- [New Zealand](#section-new-zealand): Country
- [South Africa](#section-south-africa): Country
- [Thailand](#section-thailand): Country
- [United Kingdom](#section-united-kingdom): Country
- [United States](#section-united-states): Country and postal code (full street address recommended)

### Recurly's address requirements

Upon activating a tax region, Recurly automatically requires a country for all new or updated customer billing addresses, in line with your Site Settings Address Requirement.

However, this Site Settings Address Requirement doesn't extend to the Account Information address. If you're taxing based on the Account Information address, it's crucial to collect and store the necessary fields in Recurly for accurate tax calculation.

### Recurly Taxes address requirements

Recurly Taxes sets a maximum character limit for each address field, affecting invoices taxed through Recurly Taxes and Avalara AvaTax Pro. Exceeding these limits in Recurly can lead to inaccurate taxation or the absence of tax application.

| Field Name        | Max Character Length                                                                                                  | Example         |
| :---------------- | :-------------------------------------------------------------------------------------------------------------------- | :-------------- |
| street address    | 50                                                                                                                    | 200 Main Street |
| address 2         | 100                                                                                                                   |                 |
| city              | 50                                                                                                                    | Irvine          |
| state / province  | [See Recurly's ISO alpha-2 Codes](https://docs.recurly.com/countries-provinces-and-states) for accepted region codes  | CA              |
| country           | [See Recurly's ISO alpha-2 Codes](https://docs.recurly.com/countries-provinces-and-states) for accepted country codes | US              |
| zip / postal code | 11                                                                                                                    | 92614           |

### Countries, provinces, and states

Recurly uses [ISO alpha-2 country codes](https://docs.recurly.com/countries-provinces-and-states) on all forms. For instance, the United Kingdom is "GB," not "UK". Only the United States (US), Canada (CA), Italy (IT), and the Netherlands (NL) require a state/province field if it's mandated in your Site Settings Address Requirement. [See Recurly's ISO alpha-2 Codes](https://docs.recurly.com/countries-provinces-and-states).

## Existing customer addresses

Before initiating tax collection, ensure your existing customers' addresses meet the minimum requirements for your taxable regions.

### Audit existing addresses

It's advisable to audit your billing and account addresses, updating postal code and country for all customers or at least those in your taxable regions who will be subject to tax on future invoices. You can perform this audit using the "Accounts" and "Billing Info" exports in the Reports section of your Admin Console.

### Inform your customers

Activating tax collection means existing customers in taxable regions will see taxes on their next invoice. This could surprise customers and lead to complaints. Proactively informing your customers about the upcoming tax collection in their area can help mitigate this issue.

If you start tax collection and an existing customer makes an immediate subscription change before their first taxed renewal, the subscription change invoice will include taxes on new charges but not on the returned credit. This happens because the original charge, which the credit represents, was invoiced before tax collection commenced and did not include tax, making it inaccurate to return taxes.

## Address validation

Recurly employs Avalara’s address validation tools to verify the validity of addresses used on your taxed invoices. Before generating an invoice, Recurly sends the address information to Avalara for validation.

### Error messages for new sign-ups

When using Recurly Taxes, if the address is deemed invalid or the customer's tax region (tax jurisdiction) can't be determined due to insufficient address information, the sign-up will be blocked, meaning neither a subscription nor an invoice will be created. One of the following errors will be returned:

- _"The address provided is invalid, could not determine taxing jurisdictions"_: This error occurs when either the customer's address or the merchant/site's address is invalid or lacks sufficient information for tax jurisdiction determination.

- _"The state/province provided is invalid, could not apply tax"_: This error is returned when the state/province in either the customer's or the merchant/site's address is invalid.

- "The city provided is invalid, could not apply tax": This is returned when the city in either the customer's or the merchant/site's address is invalid for the specified country.

### For future subscriptions and renewals

Addresses are still sent to Avalara for validation for ongoing subscriptions and renewals. However, unlike new sign-ups, an invalid address won't block the invoice creation; it will be generated without tax. Tax will be charged correctly once a valid address is provided on the account. The blocking of invoices due to invalid or insufficient addresses is exclusive to new sign-ups.

### When Avalara address validation is used

For merchants utilizing Recurly Taxes, only addresses within your taxable regions are sent to Avalara for validation. If insufficient information is available to identify the taxable region, the address won't be sent to Avalara. For merchants with their own Avalara AvaTax Pro account, all addresses undergo Avalara validation. If an account lacks an address, its invoices are created without tax and don't undergo Avalara's address validation.

### Military addresses

For customers with military addresses, add "General Delivery" or "GD" to an extra street address line in the customer's address for proper validation.

### Disabling Recurly Taxes address validation for new sign-ups

You can disable Recurly Taxes’ address validation for initial purchases in Configuration > Taxes > Tax Settings > Tax Service Settings. Choose to disable "Require valid address for initial purchases". With this setting off, addresses for new sign-ups are still sent to Avalara for tax jurisdiction determination, but if an address fails validation, the invoice will still be created (without tax).

![](https://files.readme.io/006ad47-Tax_Settings__Recurly.png "Tax_Settings_—_Recurly.png")

## Exempt customers

To mark a customer account as tax-exempt, navigate to the customer's account page in the Admin Console and edit the Account Information. Check the "Tax Exempt?" box. Once this is checked, all future invoices for the account will be created without tax calculation.

# Your merchant address

Before activating a taxable region, ensure your merchant address meets the minimum requirements for tax calculations. This address, used on customer invoices and for tax calculations with Avalara, is located in the Admin Console under Configuration → Business Entities. For accurate tax calculations, a postal code and country are essential. Lacking these details will result in an error when attempting to enable a taxable region.

## Tax registration numbers

In the Business Entities section, you can specify a default VAT Number and Tax Registration Number. These numbers will appear on all invoices you issue. This information pertains to your merchant business. For recording customer-specific Tax Registration Numbers (VAT numbers or Tax IDs),   a separate field is available on the customer's account record as well.

### Country-specific tax registration numbers

To display different VAT Numbers and Tax Registration Numbers on invoices for customers in specific countries (for example, if you're registered in Turkey and want to show both your Turkish VAT number and Tax **Registration** Number on invoices to customers in Turkey), you can configure this when adding or updating a Business Entity. 

## Enable a taxable region

Activating a taxable region unveils tax collection settings on plan and account pages. This allows for the configuration of product taxability and customer exemptions. Once a region is enabled, any taxable products and customers will generate tax invoices.

To enable a tax region:

1. Navigate to Configurations → Taxes.
2. Click "Configure" for the desired country.
3. On the country-specific page, choose the "Enabled" option.
4. If the country includes state or province sub-regions, they will be displayed for selection.
5. Click "Save Changes".
6. A pop-up will confirm that Recurly is using Avalara for tax rate calculations. Click "I agree to the above terms" and then "Enable".

Note: While Recurly supports tax calculations for listed regions, invoice compliance for each region is not guaranteed.

> 🚧 Enable tax regions and taxable plans at the start of the day UTC
> 
> Avalara's taxable region start and end dates do not include times. Therefore, enabling taxes in a region mid-day UTC might result in customers invoiced earlier without tax. If a refund is needed, Avalara may calculate taxes on the refund, potentially leading to a larger refund amount than the original transaction. This discrepancy can cause an error and block the refund.
> 
> To prevent this, try to enable new taxable regions and relevant plans around the start of the day UTC. If this issue arises, contact Recurly Support.

### Supported regions

| Regions              |                                    |                      |
| -------------------- | ---------------------------------- | -------------------- |
| land Islands         | Democratic Republic of the Congo   | Macedonia (FYROM)    |
| Albania              | Dominican Republic                 | Martinique           |
| Algeria              | Ecuador                            | Mexico               |
| Angola               | Egypt                              | Moldova              |
| Australia            | Georgia                            | New Zealand          |
| Barbados             | Europe (non-EU: all 22  countries) | Norway               |
| Belarus              | European Union (all 28 countries)  | Russia               |
| Benin                | Iceland                            | Serbia               |
| Bosnia & Herzegovina | Indonesia                          | South Africa         |
| Burkina Faso         | Israel                             | Switzerland          |
| Canada               | Japan                              | Taiwan               |
| Canary Islands       | Kazakhstan                         | Thailand             |
| Chile                | Kenya                              | Togo                 |
| China                | Republic of Korea (South)          | Turkey               |
| Colombia             | Kosovo                             | Ukraine              |
| Costa Rica           | Kyrgyzstan                         | United Arab Emirates |
| Côte d'Ivoire        | Lebanon                            | United Kingdom       |
|                      |                                    | United States        |
|                      |                                    | Vietnam              |

## Supported tax regions and their rates

Tax regions are organized by continent in the tables below. 

### Africa

| Country                          | Tax Region | Tax Rate | Tax Type |
| :------------------------------- | :--------- | :------- | :------- |
| Algeria                          | DZ         | 19%      | VAT      |
| Angola                           | AO         | 14%      | VAT      |
| Burkina Faso                     | BF         | 18%      | VAT      |
| Burundi                          | BI         | 18%      | GST      |
| Benin                            | BJ         | 18%      | VAT      |
| Botswana                         | BW         | 12%      | GST      |
| Cameroon                         | CM         | 19.25%   | GST      |
| Canary Islands                   | IC         | 7%       | VAT      |
| Cape Verde                       | CV         | 15%      | GST      |
| Democratic Republic of the Congo | CD         | 16%      | VAT      |
| Côte D'Ivoire                    | CI         | 18%      | VAT      |
| Egypt                            | EG         | 14%      | VAT      |
| Ethiopia                         | ET         | 15%      | GST      |
| Ghana                            | GH         | 15%      | GST      |
| Kenya                            | KE         | 16%      | VAT      |
| Lesotho                          | LS         | 15%      | GST      |
| Madagascar                       | MG         | 20%      | GST      |
| Mauritania                       | MR         | 16%      | GST      |
| Mozambique                       | MZ         | 16%      | GST      |
| Namibia                          | NA         | 15%      | GST      |
| Nigeria                          | NG         | 15%      | GST      |
| Rwanda                           | RW         | 18%      | GST      |
| Senegal                          | SN         | 18%      | GST      |
| South Africa                     | ZA         | 15%      | VAT      |
| Tanzania                         | TZ         | 18%      | GST      |
| Togo                             | TG         | 18%      | VAT      |
| Uganda                           | UG         | 18%      | GST      |
| Zambia                           | ZM         | 16%      | GST      |
| Zimbabwe                         | ZW         | 14.5%    | GST      |

### Asia

| Country                      | Tax Region | Tax Rate | Tax Type |
| :--------------------------- | :--------- | :------- | :------- |
| Armenia                      | AM         | 20%      | VAT      |
| United Arab Emirates         | AE         | 5%       | VAT      |
| China                        | CN         | 13%      | VAT      |
| Hong Kong                    | HK         | 0%       | GST      |
| Indonesia                    | ID         | 11%      | VAT      |
| Israel                       | IL         | 17%      | VAT      |
| Iran                         | IR         | 9%       | GST      |
| Japan                        | JP         | 10%      | VAT      |
| Jordan                       | JO         | 16%      | GST      |
| Kazakhstan                   | KZ         | 12%      | VAT      |
| Kyrgyzstan                   | KG         | 12%      | VAT      |
| Republic of Korea (South)    | KR         | 10%      | VAT      |
| Lebanon                      | LB         | 11%      | VAT      |
| Maldives                     | MV         | 8%       | GST      |
| Malaysia                     | MY         | 10%      | GST      |
| Nepal                        | NP         | 13%      | GST      |
| Pakistan                     | PK         | 17%      | GST      |
| Palestine Occupied Territory | PS         | 16%      | GST      |
| Philippines                  | PH         | 12%      | GST      |
| Singapore                    | SG         | 8%       | GST      |
| Sri Lanka                    | LK         | 15%      | GST      |
| Taiwan                       | TW         | 5%       | GST      |
| Thailand                     | TH         | 7%       | GST      |
| Vietnam                      | VN         | 8%       | VA       |

### Australia

Enabling tax collection in Australia will apply 10% GST to all taxable plan, add-on or adjustment line items for customers in Australia.

| Tax Region | Tax Type | Tax Rate | Minimum Address Requirement |
| :--------- | :------- | :------- | :-------------------------- |
| AU         | GST      | 10%      | Country                     |

#### ABN and ACN

Recurly supports the handling and verification of Australian Business Numbers (ABN) and Australian Company Numbers (ACN). When the customer's country is set to Australia, the VAT number field on the invoice, Checkout, Hosted Pages, and in the Admin Console will be labeled "ABN / ACN." Any number entered in this field for Australia will undergo validation to confirm it is either 9 or 11 digits, and will be saved and displayed in the formats "000 000 000" or "00 000 000 000," respectively.

> 📘 Enable ABN validation with Australian Business Register
> 
> For identifying customers with an active and GST-registered ABN, thereby exempting them from Australian GST, reach out to [Recurly Support](https://support.recurly.com/). Request the activation of **ABN validation through the Australian Business Register** on your Recurly site. More information on this feature is available in the **AU GST on Digital Services** section below.

#### AU GST on digital services

Effective July 1, 2017, Australia began requiring non-resident businesses selling digital services in Australia over a certain threshold to register and collect GST from Australian customers. This legislation includes exemptions for Australian businesses that have an active and GST-registered ABN, along with the requirement to collect two pieces of location evidence from customers being taxed.

##### Cross-border exemption

To identify customers with an active and GST-registered ABN for exemption from Australian GST, contact [Recurly Support](https://support.recurly.com/) to enable **ABN validation through the Australian Business Register** on your Recurly site. Once activated, an 11-digit number submitted in the VAT number field (ABN/ACN) for Australia will be checked against the Australian Business Register's API. Invalid ABNs will be rejected. Valid ABNs will be saved, and Recurly will record whether they qualify for a tax exemption. An ABN qualifies for a tax exemption if it is both active and GST-registered. However, Recurly does not display whether an ABN is marked as qualifying for a tax exemption.

For invoices to Australian customers, if they possess a qualifying ABN and your Site Settings country is outside Australia (cross-border sale), GST will not be applied by Recurly. However, a valid ABN or ACN that doesn't qualify for a tax exemption will still appear on the invoice, but GST will be charged.

Recurly revalidates ABNs with the Australian Business Register every six months. If a revalidation during renewal (after six months) finds the number no longer qualifies, GST will be applied to the invoice.

ABN validation with the Australian Business Register is only active in production mode on your Recurly site. In sandbox mode, you can simulate responses with these test ABNs:

- 10 120 000 004: Treated as a real, GST-registered ABN, exempt from tax.
- 10 000 000 000: Treated as a real ABN not registered for GST, and will be taxed.
- 51 824 753 555: Not recognized as a real ABN and will not be saved.

##### Location Validation

To require two pieces of matching location evidence from taxable Australian customers, enable Recurly's <a href="https://docs.recurly.com/docs/tax-location-validation">Tax Location Validation for Australia</a>.

### Europe

#### Non-european union

Enabling tax collection in a non-EU European country will apply that country's VAT rate to all taxable plan, add-on or adjustment line items for customers in the country.

All countries have a Tax Type of _VAT_ and a Minimum Address Requirement of _Country_.

Here are all the supported non-EU European countries and their rates:

| Country                                 | Tax Region | Tax Rate | Tax Type |
| :-------------------------------------- | :--------- | :------- | :------- |
| Albania                                 | AL         | 20%      | VAT      |
| land Islands                            | AX         | 24%      | VAT      |
| Andorra                                 | AD         | 4.5%     | GST      |
| Belarus                                 | BY         | 20%      | VAT      |
| Bosnia and Herzegovina                  | BA         | 17%      | VAT      |
| Georgia                                 | GE         | 18%      | VAT      |
| Iceland                                 | IS         | 24%      | VAT      |
| Isle of Man                             | IM         | 0%       | GST      |
| Kosovo                                  | XK         | 18%      | VAT      |
| Latvia                                  | LV         | 21%      | VAT      |
| Liechtenstein                           | LI         | 7.7%     | VAT      |
| Macedonia, The Former Yugoslav Republic | MK         | 18%      | VAT      |
| Moldova                                 | MD         | 20%      | VAT      |
| Monaco                                  | MC         | 20%      | GST      |
| Montenegro                              | ME         | 19%      | GST      |
| Northern Ireland                        | XI         | 20%      | VAT      |
| Norway                                  | NO         | 25%      | VAT      |
| Russia                                  | RU         | 20%      | VAT      |
| Serbia                                  | RS         | 20%      | VAT      |
| Switzerland                             | CH         | 7.7%     | VAT      |
| Turkey                                  | TR         | 18%      | VAT      |
| Ukraine                                 | UA         | 20%      | VAT      |

#### Russia

If you need to collect a State Registration Number instead of a VAT Number, you can contact <a href="https://support.recurly.com/" target="_blank">Recurly Support</a> and we will change your site to display the VAT Number field as "SRN / SRNIE" when the associated address country is Russia. This display will show on the invoice, in the Admin Console, Checkout, and on the Hosted Pages. Additionally, this feature will validate any value saved in the SRN / SRNIE field to be 13 or 15 digits.

#### European union

The European Union VAT system has many rules and requirements, so we have created a separate page dedicated to EU VAT. Read the full details on our European Union VAT support <a href="https://docs.recurly.com/eu-vat-2015">here</a>.

| Location       | Tax Region | Tax Rate | Tax Type | Minimum Address Requirement |
| :------------- | :--------- | :------- | :------- | :-------------------------- |
| United Kingdom | GB         | 20%      | VAT      | Country                     |

### Oceania

Enabling tax collection in New Zealand will apply 15% GST to all taxable plan, add-on or adjustment line items for customers in New Zealand.

| Country     | Tax Region | Tax Rate | Tax Type | Minimum Address Requirement |
| :---------- | :--------- | :------- | :------- | :-------------------------- |
| New Zealand | NZ         | 15%      | GST      | Country                     |

#### NZ GST on Digital Services

Starting from October 1, 2016, New Zealand mandated non-resident digital services businesses to collect GST from non-business customers in New Zealand. Additionally, these businesses must collect two matching pieces of evidence proving the customer's location in New Zealand. To enforce the collection of two matching location evidence pieces from non-business New Zealand customers, activate Recurly's [Tax Location Validation for New Zealand](https://docs.recurly.com/docs/tax-location-validation).

With Recurly, you can collect GST Numbers from New Zealand business customers and ensure invoices are not taxed when a valid New Zealand GST Number is provided.

- Input the GST Number in the VAT Number field of the customer's address in Recurly.
- For addresses with New Zealand as the country, Recurly requires the GST Number to be either 8 or 9 digits.
- On invoices, Recurly will label the field as "GST Number" instead of "VAT Number" for New Zealand customers to correctly identify the provided information.
- If you have enabled New Zealand taxes and your Site Settings country is not New Zealand, Recurly will not apply tax on invoices where the customer is in New Zealand and has a valid GST Number in the VAT Number field.

### North America

#### Canada

Activating tax collection in Canada results in a 5% GST being applied to all taxable plan, add-on, or adjustment line items for customers in Canada. Additional provincial level taxes (PST, HST, or QST) are applied if you enable the specific province as a taxable sub-region and the customer is located in that province. To collect only GST across all provinces in Canada, enable Canada as a taxable region, but refrain from selecting any specific province.

[block:parameters]
{
  "data": {
    "h-0": "Tax Region",
    "h-1": "Tax Type",
    "h-2": "Minimum Address Requirement",
    "0-0": "CA",
    "0-1": "GST  \nGST/PST  \nGST/HST  \nGST/QST",
    "0-2": "Postal Code and Country"
  },
  "cols": 3,
  "rows": 1,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


When managing tax collection in Canada using Recurly, it's important to understand the different tax types applicable in each province. Here's a breakdown of the Canadian provinces, indicating whether they charge a provincial level tax and the name of this tax:

| Province Name               | Tax Type |
| :-------------------------- | :------- |
| Alberta                     | GST      |
| British Columbia\*          | GST/PST  |
| Manitoba\*                  | GST/PST  |
| New Brunswick\*             | GST/HST  |
| Newfoundland and Labrador\* | GST/HST  |
| Northwest Territories       | GST      |
| Nova Scotia\*               | GST/HST  |
| Nunavut                     | GST      |
| Ontario\*                   | GST/HST  |
| Prince Edward Island\*      | GST/HST  |
| Quebec\*                    | GST/QST  |
| Saskatchewan\*              | GST/PST  |
| Yukon                       | GST      |

- For customers located in a province different from the one you have enabled in your Canada tax settings, they will only be charged GST.

Note: Some Canadian cities have unique exemption rules. For instance, the city of Lloydminster spans both Alberta and Saskatchewan and is exempt from PST due to its unique location. Recurly Taxes takes these city-specific rules into account. However, Recurly's tax calculations in sandbox mode and for production previews are at the provincial level and may not reflect these city-level exceptions.

#### United States

Enabling tax collection in the United States will apply Sales Tax to all taxable plan, add-on or adjustment line items for customers in the states you enable. Sales Tax applies state, county, local and special taxes depending on the customer's invoice address.

The Tax Region for U.S. Sales Tax is always the two letter state code of the tax being applied. This is shown on the invoice next to the combined tax rate.

The Minimum Address Requirement for U.S. Sales Tax is _Postal Code_ and _Country_.

> 📘 Collect full street address for more accurate rate calculations
> 
> U.S. Sales Tax has complex tax jurisdiction dividing lines that go down to the street address. The house across the street from you can be in the same postal code, but be in a different tax jurisdiction. While a postal code and country are the minimum address requirement for taxes to be calculated, we strongly suggest merchants collect the full street address in order to calculate more accurate tax rates through Recurly Taxes.

| Country            | Tax Region | Tax Rate | Tax Type |
| :----------------- | :--------- | :------- | :------- |
| Barbados           | BB         | 17.5%    | VAT      |
| Belize             | BZ         | 12.5%    | GST      |
| Costa Rica         | CR         | 13%      | VAT      |
| Cuba               | CU         | 10%      | GST      |
| Dominican Republic | DO         | 18%      | VAT      |
| Guadeloupe         | GP         | 8.5%     | GST      |
| Guatemala          | GT         | 12%      | GST      |
| Honduras           | HN         | 15%      | GST      |
| Jamaica            | JM         | 15%      | GST      |
| Martinique         | MQ         | 8.5%     | VAT      |
| Mexico             | MX         | 16%      | GST      |
| Nicaragua          | NI         | 15%      | GST      |
| Panama             | PA         | 7%       | GST      |
| El Salvador        | SV         | 13%      | GST      |

### South America

| Country             | Tax Region | Tax Rate | Tax Type |
| :------------------ | :--------- | :------- | :------- |
| Argentina           | AR         | 21%      | GST      |
| Bolivia             | BO         | 13%      | GST      |
| Chile               | CL         | 19%      | VAT      |
| Colombia            | CO         | 19%      | VAT      |
| Curacao             | CW         | 6%       | GST      |
| Ecuador             | EC         | 12%      | VAT      |
| Falkland Islands    | FK         | 0%       | GST      |
| Guyana              | GY         | 14%      | GST      |
| Peru                | PE         | 18%      | GST      |
| Paraguay            | PY         | 10%      | GST      |
| Suriname            | SR         | 10%      | GST      |
| Trinidad And Tobago | TT         | 12.5%    | GST      |
| Uruguay             | UY         | 22%      | GST      |
| Venezuela           | VE         | 16%      | GST      |

- Recurly does not support RUT number validation, format validation, or IP address validation in Chile. 

# Taxable plans and adjustments

## Plans

Once you enable a taxable region, you can configure your plans to collect taxes. All existing plans will default to tax exempt. You will need to edit each individual plan that you want to tax to enable the "Collect Tax" option. All new plans created will default to collecting tax. If a plan has "Collect Tax" enabled, any included add-ons will also be taxed.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/I4jdxgmIRjq5DT9kW6vE_tax-on-plan.png",
        "tax-on-plan.png",
        "1699"
      ],
      "align": "center",
      "caption": "How to enable a plan to collect tax"
    }
  ]
}
[/block]


## One-time charges

Once you enable a taxable region, you can create custom charge adjustments that collect tax. The Create Charge page in the Admin Console for an account will default to collecting tax on charges. Recurly does not support tax calculations on custom credit adjustments.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/LHEDJwmZRAu5dYDWRxOx_tax-on-charge.png",
        "tax-on-charge.png",
        "1694"
      ],
      "align": "center",
      "border": true,
      "caption": "How to create a charge with tax"
    }
  ]
}
[/block]


## Tax product type

Recurly's in-the-box tax calculations, leveraging AvaTax by Avalara, treats each line item (plan, add-on, adjustment) as "Tangible Personal Property" (TPP), typically considered physical goods. In many regions, tax rules for physical and digital goods, as well as services, align with those for TPP. You should ensure that the basic rates calculated meet your taxation needs. You can also choose to enter a specific tax code for a given product, if you have a particular tax code(s) your business requires for the products/services being sold. Recurly recommends consulting with your tax and accounting experts before applying a specific tax code to products within the application. 

You can find a list of <a href="https://taxcode.avatax.avalara.com/" target="_blank">suggested tax codes</a> on Avalara’s website. Click into the category of products you are selling to see the tax codes.

For more advanced product distinctions and tax rules, upgrading to your own <a href="https://docs.recurly.com/docs/avalara" target="_blank">AvaTax account</a> or <a href="https://docs.recurly.com/docs/vertex" target="_blank">Vertex account</a> is recommended for access to rate/rule mappings.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a0b212d-Screenshot_2024-07-09_at_1.48.10_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


# Tax previews at checkout

Recurly provides tax estimate previews based on internal rate tables, while final invoices use Avalara for tax calculation. These previews are available on Checkout, Hosted Payment Pages, through the API for Subscriptions and Invoices, and via Recurly.js for subscription sign-ups.

# Tax invoices

Invoices that include tax will feature:

- A "Tax" column next to Subtotal, displaying the tax rate for each line item. If tax is not applicable, it will show as 0.00%.
- A "Total" column after the Tax column, showing the combined amount of the subtotal and tax for each line item.
- An invoice-level total tax row, detailing the tax region, rate, and total tax amount for the invoice, equaling the sum of the tax amounts from all line items.

#### Tax invoices with multiple tax rates

An invoice may contain more than one tax rate, depending on the tax treatment of the item type or if there are multiple shipping addresses with different tax rates (see [Shipping Address per Line Item](doc:shipping-address-per-line-item)).

In such cases, the invoice will also include:

- A Tax Details card that outlines each tax rate, the associated subtotal amount, and the tax amount.
- An invoice-level total tax row that shows only the total tax amount for the invoice, as the Tax Details card provides detailed information about rates and subtotal amounts.

## Tax amount rounding

In sandbox mode, tax amount estimates and production mode previews are always rounded up to two decimal points. This approach accommodates the varying rounding rules across different regions and jurisdictions. Actual invoices in production mode, calculated through Avalara, apply region- and jurisdiction-specific rounding at the line item level. Generally, amounts below five are rounded down, and those five or higher are rounded up.

### Example

_Given Scenario:_

- Invoice rate is HU VAT 27% (Hungary VAT)
- First line item costs $5.79 (raw tax = $1.5633)
- Second line item costs $5.81 (raw tax = $1.5687)

_Sandbox Mode and Production Previews:_

- Tax for the first line item = $1.57
- Tax for the second line item = $1.57
- Total tax = $3.14

_Production Actual Invoice:_

- Tax for the first line item = $1.56
- Tax for the second line item = $1.57
- Total tax = $3.13

## Tax on credits

When refunding tax, the entire tax amount should be itemized and documented on a credit memo issued to the customer. When this credit is used for a new invoice, the tax amount doesn't need to be itemized again, as the credit acts as payment. Below is how Recurly handles tax returns on credit in different scenarios.

### Refunds

Refunds in Recurly generate a refund invoice, acting as a credit memo. The refund method influences the tax calculation approach.

_Line Item Refunds:_  
Recurly calculates tax on the selected refund line items. These refunds maintain the product identity, ensuring the correct tax amount is linked with the refunded credit on both the refund invoice and your "Adjustments" export.

_Open Amount Refunds:_  
Also known as Specific Amount Refunds, Recurly calculates the tax to be returned so that the net refund to the customer matches the requested amount. If the invoice being refunded has multiple line items, the returned tax isn't linked to any specific item. As Open Amount Refunds are at the invoice level, specific line item associations are lost. Hence, Line Item Refunds are recommended unless a custom refund amount is necessary.

> 🚧 Rounding Issues with Multiple Partial Refunds
> 
> Partial refunds that include tax might lead to rounding issues, where the final refund amount's tax is slightly higher than the original transaction amount. This can block the refund with an error. If this occurs, contact Recurly Support.

### Immediate upgrades and downgrades

Immediate subscription changes generate an invoice with prorated billing for the new subscription and credits for the unused portion of the old subscription. Ideally, this would involve a credit memo for the refund and a separate invoice for the new charges. However, Recurly combines both on the same invoice, showing positive tax on new charges and negative tax on credits. The invoice's total tax is the net of these amounts. Including the credit as a line item also reduces the overall subtotal, so the subtotal and total tax might not directly correlate.

Despite this discrepancy, the correct tax is collected and returned at the line item level. Tax reporting at this level through the "Adjustments" export should enable accurate tax amount reporting.

### Custom credit adjustments

Recurly does not calculate tax on custom credit adjustments. To credit a customer and refund tax, a refund should be issued rather than creating a custom credit adjustment.

# Tax exports

Recurly offers detailed tax reporting at the line item level through the ["Adjustments" export](https://docs.recurly.com/docs/adjustments-exports). This export itemizes state, county, local, and special tax rates and amounts as calculated by Avalara.

However, specialized reports or exports for taxes are not directly provided by Recurly. These features are available when you upgrade to your own Avalara AvaTax Pro or Vertex account.

## Disable a taxable region

Disabling a taxable region will stop tax collection on future invoices from customers in that location. If a refund is later processed on a taxed invoice from that disabled region, tax will be refunded appropriately because we track the date range where you collected tax in the region.

> ❗️ Do not disable and re-enable a Tax Region in Production Mode
> 
> We allow merchants to disable tax regions because they may no longer have a tax obligation in that area. Be careful about mistakenly disabling a tax region because re-enabling it will reset the date range tracked for the region and past invoices will not refund tax correctly. If you get yourself in this situation, please contact Recurly Support.

# Sandbox testing

Most of Recurly's standard tax functionalities can be tested on any site in sandbox mode. In this mode, both preview and final invoices use Recurly's internal rate tables. In production mode, Avalara is used for final invoice tax calculations, while Recurly's internal rate tables are reserved for checkout previews. Thus, in sandbox mode, Avalara's Address Validation can't be tested, and you may notice minor differences in the tax rates applied.

# Avalara downtime

When an invoice is generated and a Recurly site is set up to collect tax in the customer's location, Recurly sends a request to Avalara for tax calculation. If Recurly can't receive a successful response from Avalara, or if the internal Recurly tax service that interfaces with Avalara is unresponsive, the response varies based on the type of invoice.

To check Avalara's operational status, visit [Avalara's status page](http://status.avalara.com/) and view the Avalara AvaTax section under "Tax Calculation Service".

## For new sign-ups and purchases

In cases where Recurly can't obtain a successful response from Avalara, or if the internal tax service is unresponsive, new sign-ups or purchases will be blocked (preventing the creation of a subscription or invoice). This measure ensures that no invoice is generated for a customer in a taxable location without accounting for tax. The error message provided will be:

- "Tax service currently unavailable, please try again later"

### Disable tax response requirement for initial purchases

If you prefer to allow new sign-ups and purchases to proceed even when tax can't be calculated, you can modify your site's default settings. Go to Configuration > Taxes > Tax Settings > Tax Service Settings and disable the option "Require successful tax response for initial purchases".

![](https://files.readme.io/8dac00c-Tax_Settings__Recurly.png "Tax_Settings_—_Recurly.png")

If you opt to disable the tax response requirement, invoices will be issued without tax in situations where either Avalara or Recurly's internal tax service is unresponsive, or if the tax service returns an error other than an invalid address. It's crucial to note that Recurly does not provide direct notifications for invoices created without tax consideration. To monitor such invoices, you should utilize the Invoices - Summary export or the Invoices API to identify invoices created in taxable locations where no tax was applied.

It's important to understand that once an invoice is generated, it's not feasible to charge the customer solely for the missing tax. The only method to collect the omitted tax is to refund the original invoice and then issue a new custom charge invoice. However, this custom charge invoice, although linked to the account, will not be associated with the subscription or the underlying plan. **Therefore, it's advised that merchants who disable the tax response requirement should be prepared to absorb the missing tax fees themselves, rather than attempting to collect them from the customer.**

## For future subscriptions and renewals

If Recurly is unable to receive a response from Avalara or if the internal Recurly tax service is unresponsive, Recurly will not activate a future subscription or renew an existing one. Instead, it will attempt to activate or renew the subscription every hour until a response is received from Avalara. This ensures that no invoice is created for a customer in a taxable location without considering tax. Although the renewal might occur an hour later, the original subscription billing cycle dates will be honored. Unlike sign-ups and purchases, this functionality is not configurable.

If Avalara or Recurly's internal tax service encounters an error during a renewal, the renewal will proceed, resulting in the creation of an invoice without tax.

### Notes

There are several ways to determine if the tax service was used for an invoice:

- In the API and exports, there is a boolean field called `used_tax_service` indicating whether the tax service was utilized.
- In the Recurly user interface, there will be a note on the invoice specifying whether the tax service was used.