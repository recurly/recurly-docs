---
title: European Union VAT
excerpt: >-
  This feature or setting is available to all customers on any Recurly
  subscription plan.
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

* Business Entity address with a specified country and postal code.
* An active Recurly account with plans and charges set up.
* If using Recurly.js for tax details during signup, ensure it's at least version v3.
* Knowledge of whether your digital services are being offered in EU countries where you're not VAT registered.
* If using Avalara AvaTax Pro, ensure it's connected to your Recurly site.

### Limitations

* At present, Recurly only supports a single merchant address per site, which is collected on the Business Entity page. This address is utilized for all invoice generation and tax calculations. If your operations demand multiple merchant addresses for invoices or tax calculations, Recurly currently cannot cater to this requirement.

# Definition

Recurly's EU VAT feature is a comprehensive tool designed to facilitate the automatic taxation of digital services within the European Union. It provides businesses with the ability to configure tax plans, identify digital services, and ensure accurate tax collection based on the customer's location, all while adhering to EU VAT regulations.

# Key benefits

* **Automated tax calculation**: Streamline the process of determining and applying the correct VAT rates based on customer location.
* **Compliance assurance**: Stay compliant with EU VAT regulations, especially for digital services, reducing legal risks.
* **Flexible configuration**: Easily turn taxes on or off for specific plans or charges, and identify products as digital or physical.
* **Enhanced customer experience**: Offer tax-inclusive pricing and provide accurate VAT previews during the checkout process.
* **Integrated tools**: Utilize additional features like invoice localization, country-specific invoice sequences, and location validation for a holistic VAT management experience.

# European Union VAT with Recurly

Recurly provides comprehensive support for VAT collection and validation across all 27 EU member states. For merchants offering digital products, an automated Location Validation feature is available to accommodate the 2015 digital rate amendments.

## EU countries and territories

### EU VAT countries

The following countries are part of the EU VAT system:

* Austria (AT)
* Belgium (BE)
* Bulgaria (BG)
* Croatia (HR)
* Cyprus (CY)
* Czech Republic (CZ)
* Denmark (DK)
* Estonia (EE)
* Finland (FI)
* France (FR)
* Germany (DE)
* Hungary (HU)
* Ireland (IE)
* Italy (IT)
* Latvia (LV)
* Lithuania (LT)
* Luxembourg (LU)
* Malta (MT)
* Netherlands (NL)
* Northern Ireland (XI)
* Poland (PL)
* Portugal (PT)
* Romania (RO)
* Slovakia (SK)
* Slovenia (SI)
* Spain (ES) - inclusive of the Canary Islands
* Sweden (SE)

### EU VAT territories

Certain territories within the EU require VAT collection but aren't directly supported by Recurly's basic tax functionalities. For merchants with customers in these regions, connecting with AvaTax or Vertex is recommended. More details on integrating with [AvaTax](https://docs.recurly.com/docs/avalara) and [Vertex](https://docs.recurly.com/docs/vertex) can be found in the provided links.

#### France

* Monaco (MC)

#### United Kingdom

* Isle of Man (IM)

### EU special VAT rate territories

Some territories within the EU have unique VAT rates. To handle these special rates, merchants can connect with AvaTax or Vertex. More on [AvaTax](https://docs.recurly.com/docs/avalara) and [Vertex](https://docs.recurly.com/docs/vertex) integrations can be found in the linked documentation.

#### Portugal

* Azores
* Madeira

#### Greece

* Specific islands in the Aegean Sea

#### France

* Corsica

### EU Territories exempted from VAT

As per the [European Commission](https://ec.europa.eu/taxation_customs/business/vat/eu-vat-rules-topic/territorial-status-eu-countries-certain-territories_en), the following territories are exempt from VAT collection in Recurly:

#### Austria

* Jungholz
* Mittelberg

#### Denmark

* Greenland (GL)
* Faroe Islands (FO)

#### Finland

* Åland islands (AX)

#### France

* Guadelupe (GP)
* Guyana (GY)
* Martinique (MQ)
* Réunion (RE)
* Mayotte (YT)

#### Germany

* Island of Helgoland
* Busingen territory

#### Greece

* Mount Athos

#### Italy

* Livigno
* Campione d'Italia
* Waters of Lake Lugano within Italy

#### Spain

* Ceuta (EA)
* Melilla (EA)

#### United Kingdom

* Channel Islands - Use either Jersey or Guernsey's code
  * Jersey (JE)
  * Guernsey (GG)
  * Gibraltar (GI)

## Your tax identity

Recurly's EU VAT feature is available to all merchants, regardless of their business's geographical location. To leverage this feature effectively, it is imperative that you verify the accuracy of your tax identity beforehand. Tax calculations on all invoices will be based on the specific address of the business entity associated with each invoice, serving as the origin address for tax purposes. Although VAT rates are determined at the country level, it is crucial to provide your postal code as well, ensuring the precision of tax rate calculations.

On the Business Entities page, you can input your VAT Number, which will be displayed on all invoices unless your business is outside the EU. Ensure the accuracy of this number as Recurly doesn't validate merchant VAT Numbers.

<Image align="center" className="border" border={true} src="https://files.readme.io/b9418da-Screenshot_2023-04-19_at_10.54.11_AM.png" />

## Who is taxed

The taxation criteria depend on your business location. If your Business Entity is in the EU, VAT will be applied to invoices with a customer located in the EU, unless they provide a valid VAT registration number.

For non-EU Business Entities, VAT is applied only to invoices where the customer is located in a country where you're registered to collect VAT.

To determine who gets taxed, collecting the customer's country information is crucial. This is typically sourced from the Billing Info Country field.

### VAT registered countries

For the EU VAT feature to function, merchants must specify the EU countries where they're registered to collect VAT. At least one country must be selected to activate the feature. If your business is located in the EU, ensure your Business Entity's country is among the "VAT Registered Countries" to get accurate VAT rates.

### EU VAT registered customers

Customers providing a valid EU VAT registration number are recognized as EU businesses. If such a customer resides in the same country as your Business Entity, VAT will be applied. If they're from a different country, a "Reverse Charge" mechanism is applied, and VAT isn't charged. In this case, a note titled "VAT Reverse Charge Notes" will appear on the invoice, indicating the customer's responsibility for VAT fees.

Merchants can customize this note on the Tax Settings page. This default note will be displayed on all reverse charge invoices. However, you can modify the notes for a specific invoice before posting it.

<Image align="center" className="border" border={true} src="https://files.readme.io/6de21d3-tax-settings-2.png" />

For details on Recurly's VAT number validation, please refer to our [dedicated documentation](/docs/vat-number-validation).

#### Sample error responses for invalid VAT number

For those transitioning from sandbox to production mode, it's useful to understand the response generated by Recurly for invalid VAT numbers. Below is a sample XML error response for creating an account with an invalid VAT number:

```xml
<errors>
  <error field="account.vat_number" symbol="invalid">is invalid</error>
</errors>
```

### Brexit implications

With the Brexit transitionary period ending on 12/31/2020, Recurly will apply GB tax code rules instead of the EU tax code for sites with a UK address or customers with a UK destination address.

For B2C merchants:

1. If your Business Entity country is set to the UK and your customer is located in an EU member region, and that member region is not enabled in your tax configuration settings, no tax will be applied to the invoice.  Previously, GB VAT would be applied.  If you need to apply tax in this scenario, enable all the EU regions you are doing business in your tax configuration settings.  Doing so will ensure the appropriate destination VAT is applied.

2. If your Business Entity country is set to an EU member region and your customer is located in the UK, and the UK is not enabled in your tax configuration settings, no tax will be applied to the invoice.  Previously, your EU member region VAT rate would be applied.  If you need to apply tax in this scenario, enable the UK as a region in which you are doing business in your tax configuration settings.  Doing so will ensure the appropriate UK VAT rate is applied.

3. If your Business Entity country is set to a country outside of the UK or EU, and the UK is not enabled in your tax configuration settings, no tax will be applied to the invoice.  If you need to apply tax in this scenario, enable the UK as a region in which you are doing business in your tax configuration settings.  Doing so will ensure the appropriate UK VAT rate is applied.

> **Note:** For scenarios 2 and 3 above, some considerations if you sell physical goods. Starting 1/1/2021, all imported goods purchased will be subject to value-added tax (VAT). This will end the current £15 (about $20) VAT exemption thresholds known as low value consignment stock relief.  Foreign sellers must begin collecting U.K. VAT at the time of checkout on consignments not exceeding £135 ($180). Non-U.K. based businesses will need to register in the U.K. so they can make proper customs clearance declarations before shipments will be allowed into the country.  If you are supplying physical goods to the UK above £135, additional rules may apply.  Please consult a tax professional to determine which  Recurly configurations are appropriate for you.

For B2B merchants:

1. If you are not currently capturing VAT numbers from your UK based customers, no reverse VAT charge notes will be included on your customers' invoices.  If you need to include reverse VAT charges, enable the UK as a region in which you are doing business in your tax configuration settings and begin collecting VAT numbers from your business customers.

For Merchants located and/or doing business in Northern Ireland:

If you are located in Northern Ireland, to properly calculate VAT, you may need to update your Site Address Country to Northern Ireland.   If you are doing business in Northern Ireland, to properly calculate VAT, you may need to enable Northern Ireland as a Taxable Region within the EU on your site's Tax Settings and ensure your customers located in Northern Ireland specify Northern Ireland as their billing/account address country.  Please consult a tax professional to determine which Recurly configurations are appropriate for you.

### Exempt customers

Recurly's EU VAT feature allows merchants to mark a customer's account as exempt. This is useful for entities like governments or non-profits that might be exempt from VAT but don't have a VAT Number. If an account is marked as exempt, no VAT will be charged on their invoices. If special notes about the exemption are required, merchants can use the "Terms and Conditions" or "Customer Notes" sections on the invoice.

## Configuring taxation: plans and charges

The EU VAT feature is designed to tax all transactions by default. However, it offers flexibility by allowing users to disable taxes for specific plans or charges. Upon activation, all your existing plans will have the tax feature enabled. For any new plan or charge you create, the "Collect Sales Tax" option will be pre-selected. If you're issuing a charge (adjustment) via the API, ensure you indicate that the charge isn't tax-exempt on every API call to facilitate tax collection for that particular charge.

## Taxation criteria: identify digital services

For accurate taxation, it's essential to categorize digital services such as telecommunications, broadcasting, and electronic services at the product level. This ensures that EU consumers are taxed based on their respective country rates, especially for cross-border sales. With Recurly Taxes activated, you can configure plans, add-ons, and one-time charges to have a Tax Type of either "Digital Product", "Physical Product", or "Unknown". By default, all items are set to "Unknown". Both "Unknown" and "Physical Product" are treated as Tangible Personal Property (TPP) in Avalara during tax computation. In the Admin Console, this field is labeled as Tax Type, while in the API and Recurly.js, it's referred to as tax\_code.

<Image align="center" alt={1348} border={false} caption="Ensure the plan is set to &#x22;Collect Tax&#x22; to view the Tax Type." title="Screen Shot 2018-11-06 at 1.52.34 PM.png" src="https://files.readme.io/0bae8b0-Screen_Shot_2018-11-06_at_1.52.34_PM.png" />

<Image align="center" alt={1348} border={false} caption="Configuring the Tax Type for Add-Ons." title="Screen Shot 2018-11-06 at 1.53.53 PM.png" src="https://files.readme.io/735a9c8-Screen_Shot_2018-11-06_at_1.53.53_PM.png" />

If you categorize plans, add-ons, or charges as a Digital Product, ensure you're VAT registered across all 27 EU countries and have selected all these countries on the EU VAT Configuration page. If you're not VAT registered in an EU country where the digital item is being billed, the invoice will be halted.

### Understanding VAT rates

**For Merchants with Business Entities in the EU and registered for VAT:**

<HTMLBlock>{`
<table class="table table-bordered table-striped">
<tr>
<td><strong>Scenario</strong></td>
<td><strong>VAT Rate Country</strong></td>
</tr>
<tr>
<td>Customer is outside the EU</td>
<td>No VAT</td>
</tr>
<tr>
<td>EU customer has a VAT number and resides in the same country as the merchant</td>
<td>Merchant's Country</td>
</tr>
<tr>
<td>EU customer possesses a VAT number but is in a different country than the merchant</td>
<td>No VAT</td>
</tr>
<tr>
<td>Item has a Tax Type of "Digital Product" (2014)*</td>
<td>Merchant's Country</td>
</tr>
<tr>
<td>Item has a Tax Type of "Digital Product" (2015 onwards)*</td>
<td>Customer's Country</td>
</tr>
<tr>
<td>Item has a Tax Type of "Unknown" or "Physical Product" and the EU customer is in a VAT registered country</td>
<td>Customer's Country</td>
</tr>
<tr>
<td>Item has a Tax Type of "Unknown" or "Physical Product" and the EU customer is NOT in a VAT registered country</td>
<td>Merchant's Country</td>
</tr>
</table>
`}</HTMLBlock>

**For Merchants with Business Entities outside the EU:**

<HTMLBlock>{`
<table class="table table-bordered table-striped">
<tr>
<td><strong>Scenario</strong></td>
<td><strong>VAT Rate Country</strong></td>
</tr>
<tr>
<td>Customer is outside the EU</td>
<td>No VAT</td>
</tr>
<tr>
<td>EU customer is not in a VAT registered country</td>
<td>No VAT</td>
</tr>
<tr>
<td>EU customer possesses a VAT number</td>
<td>No VAT</td>
</tr>
<tr>
<td>EU customer is in a VAT registered country, and the item has a Tax Type of "Unknown", "Physical Product", or "Digital Product"</td>
<td>Customer's Country</td>
</tr>
</table>
`}</HTMLBlock>

## Taxation timing: Mandating dual location evidence

For merchants offering digital services to non-business EU customers, VAT regulations necessitate the collection of two non-conflicting pieces of evidence to determine the customer's country of residence. To enforce this, utilize Recurly's Tax Location Validation feature.

### Enable location validation

1. Navigate to Configuration > Taxes. Then, click on the "Tax Settings" button located at the top right corner of the Taxes page.
2. Scroll to find and activate "VAT Location Validation" within the "European Union VAT Settings" section. Don't forget to "Save Changes" at the page's end.

<Image align="center" width="80%" src="https://files.readme.io/72abb4a-vat-location-validation.png" />

Upon enabling VAT Location Validation, Recurly will assess all your existing EU accounts without a VAT number but with an active subscription. You'll receive an email notification for each account that doesn't comply with VAT regulations. Additionally, you can export the Accounts data to identify non-compliant accounts under the "tax\_location\_valid" column. Search for the value "FALSE", indicating non-compliance.

For each notification received or for each "FALSE" account in the Accounts export, access that account in Recurly. Check the Activity event to understand the evidence the customer has provided. Reach out to the customer to gather more evidence to prevent subscription cancellation upon renewal. Once you've updated the evidence for the non-compliant customer, ensure the account's non-compliant banner is removed. A successful Activity will be recorded on the account.

[Discover more about Tax Location Validation.](https://docs.recurly.com/docs/tax-location-validation)

## Invoice sequencing by country

By default, Recurly uses a single sequence for invoice numbers across your site, adhering to the European Commission's invoicing rules. However, certain EU member states mandate a unique sequence for their country. To cater to this, we offer the Country Invoice Sequencing feature. This allows merchants to establish distinct sequences for each EU member state. Once activated, all new EU invoices will have a number that progresses based on that country's sequence. Each sequence commences at 1000 and is prefixed with the respective two-letter country code (e.g., FR1000 for France). This country-specific sequencing is exclusive to the 27 EU member states. Invoices for customers outside the EU will follow the site-level sequence.

## VAT currency conversion

EU VAT rules require invoices to show VAT amounts in the customer’s local currency. When issuing invoices in Europe, display both the VAT and subtotal in the country’s official currency according to the corresponding ISO code. This ensures customers see accurate tax calculations aligned with local regulations. These guidelines apply to countries using the euro (EU member states) as well as the UK (GBP).

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/5d26619ac0b078da14bc655cb4c19c191f46beb7fc9bab2925c9c31024bb9558-VATCurrencyConversionInvoice.png" />

### Alternative solutions

Merchants have the option to either generate their invoices or programmatically input VAT currency conversion details into one of the two notes sections on an invoice before its creation. These sections are "Customer Notes" and "Terms and Conditions".

This alternative approach demands the modification of notes prior to each subscription renewal. You'll need to track subscription renewals on your end and initiate the Update Subscription API call before the renewal.

#### Suggested notes editing flow

1. Preview the subscription or adjustment invoice via the API and look for `<tax_type>vat</tax_type>`.
2. If `<tax_type>vat</tax_type>`, grab the `<tax_in_cents>`, `<currency>`, and `<country>` under `<address>`.
3. Run your own currency conversion.
4. Post the invoice or create the subscription via the API and store your currency conversion notes in either `<terms_and_conditions>` or `<customer_notes>` in the call.
5. If this is a subscription, you will need to store the renewal date or query for renewals on your side and then trigger an Update Subscription Notes call with the notes before the renewal creates the invoice.

### Using Avalara AvaTax Pro

Merchants with an AvaTax Pro account can ensure compliance with EU VAT regulations using Recurly's supplementary EU VAT features. These include invoice messaging, country invoice sequencing, and location validation for digital services customers.

#### Connecting to AvaTax Pro Account

Begin by connecting your AvaTax Pro account by entering your credentials. For detailed configuration instructions, refer to our [AvaTax Pro support article](/avalara).

#### Categorizing a digital service

If any of your plans, add-ons, or charges qualify as a Digital Service, you'll need to use Avalara's Tax Codes for accurate categorization. Once your AvaTax Pro account is linked, the Edit Plan page will display the plan Tax Code option beneath the "Collect Sales Tax" checkbox. Additional Tax Code options are available next to the add-ons on this page and on the Create a Charge page.

Consult with our Avalara representative to determine the appropriate tax codes for your products to ensure accurate EU VAT Digital Services categorization. A fundamental Digital Services tax code that is universally applicable is D0000000.

#### Accessing other EU VAT features

AvaTax Pro users can utilize **Location Validation** to meet Digital Services evidence requirements and **Country Invoice Sequencing** if a distinct invoice sequence for each EU country is needed. Both features are accessible from the "Tax Settings" page, found at the top right corner of the Taxes page. Additionally, AvaTax Pro

users automatically benefit from VAT Number validation and will observe new Reverse Charge notes on invoices that contain customer VAT Numbers.

### Implementing Recurly.js

For those using Recurly.js to showcase tax details during the signup process, it's essential to have at least Recurly.js v3 to utilize the EU VAT feature. If an update to your Recurly.js version is needed for tax support, we advise transitioning to the latest Recurly.js v4. The older Recurly.js v2 won't support tax previews once the feature is activated. Merchants offering digital services should update their tax previews to [specify a tax\_code of "digital"](https://docs.recurly.com/js/#pricing.attach) to ensure accurate VAT previews. An example can be found [here](https://github.com/recurly/recurly-js-examples/blob/master/public/advanced-tax/index.html).

To display the country code of the VAT rate in your tax previews, the "tax\_region" attribute can be utilized. Although we don't currently support tax\_rate in Recurly.js, a method to determine the rate is documented in [Github Issue #163](https://github.com/recurly/recurly-js/issues/163). For more details, explore our [Recurly.js documentation](https://docs.recurly.com/js/).

#### Integrating PayPal

For those using Recurly.js to facilitate PayPal sign-ups, modifications to your calls are necessary to ensure the customer's country is stored before subscription creation. Since PayPal tokens don't retain an address in the Billing Info, this information must be stored separately. Typically, Recurly.js is used to obtain a PayPal token, which is then stored in the Billing Info during the same API call that initiates the subscription. For VAT purposes, the Billing Info must first be created, then updated with the country before the subscription is finalized. Here's a recommended procedure:

1. Incorporate a country field in your checkout form.
2. Preview the pricing for the customer using Recurly.js. This preview will reflect the correct tax, considering the country provided in the form.
3. Once the customer confirms their preference for PayPal, use Recurly.js to obtain a PayPal token.
4. Subsequently, use the API to establish the [account](https://dev.recurly.com/docs/create-an-account) and [billing info](https://dev.recurly.com/docs/create-an-accounts-billing-info-token).
5. Update the billing info again using the API, inputting the address collected from the Recurly.js form. Exclude the token in this step, focusing only on the new address details.
6. Finalize the subscription using the [Create Subscription API](https://dev.recurly.com/docs/create-subscription) call.
7. In case of sign-up failure, an account for that customer will still be present in Recurly. You can either retain it or utilize the API to [Close the Account](https://dev.recurly.com/docs/close-account).

For those utilizing Recurly's Checkout or Hosted Payment Pages for PayPal sign-ups, it's worth noting that we do receive a country from PayPal with the billing agreement. This country is stored in the Billing Info before the subscription is initiated.

# Activating country invoice sequencing

1. Navigate to Configuration > Taxes. Then, click on the "Tax Settings" button located at the top right corner of the Taxes page.
2. Scroll to find and activate "Country Invoice Sequencing" within the "European Union VAT Settings" section. Ensure you "Save Changes" at the page's end.

<Image align="center" width="80%" src="https://files.readme.io/2c4e11d-country-invoices.png" />

# Enabling tax collection

## Using Recurly taxes

1. Ensure your Business Entity address includes both a country and a postal code.
2. In the Recurly Admin Console, navigate to Configuration > Taxes and click "Configure" adjacent to "European Union (VAT)" at the page's bottom.

<Image align="center" width="80%" src="https://files.readme.io/e86877c-eu-vat-enable.png" />

3. On the subsequent page, select "Enabled" to reveal the list of countries. At least one country must be selected. For EU merchants, the country that corresponds with your Business Entity country must be included. For non-EU merchants selling digital services, all countries must be enabled; otherwise, sales will be restricted in non-enabled countries.

<Image align="center" width="80%" src="https://files.readme.io/c448138-Screen_Shot_2019-03-07_at_1.50.44_PM.png" />

4. After clicking "Save Changes", a modal will appear, informing you that Avalara is used for tax calculations and seeking your agreement to our terms.
5. Post EU VAT activation, the relevant section will be highlighted in green on the Taxes page. You can revisit the Configure page to deactivate specific countries or the entire feature if adjustments are needed.

<Image align="center" width="80%" src="https://files.readme.io/9d6e22d-enabled.png" />

6. Now, proceed to Configuration > Plans. Here, set each plan as taxable and determine the Tax Type for every plan and add-on, choosing between "Physical Product" or "Digital Product". The default setting is "Unknown", which adheres to standard physical product tax regulations.

# FAQs

**Q:** Can the EU VAT feature accommodate "tax-inclusive" pricing?\
**A:** Absolutely, for more details, refer to our documentation [here](https://docs.recurly.com/docs/tax-inclusive-pricing).

**Q:** What are the implications if I don't upgrade to at least Recurly.js v3 and activate the EU VAT feature?\
**A:** If you're operating with Recurly.js v2 and activate the EU VAT feature, your VAT preview amounts might not align with the final invoices. However, the actual invoices will remain unaffected and accurate.

**Q:** What if I'm not gathering billing or shipping details during checkout?\
**A:** If you're not collecting country information during checkout and storing it in either Billing Info or Account Info, tax calculation becomes impossible. Accurate tax calculation mandates knowledge of the customer's location. While VAT is a country-level tax requiring only the country for accurate rate determination, it's not advisable to store IP addresses in Billing Info, as it might not be the most accurate location indicator. A customer might be traveling or using IP spoofing. Although we use IP addresses for location evidence for digital services, it serves as a secondary piece of evidence. The primary address evidence always stems from the billing address or the account address (shipping address).

**Q:** What if I'm offering digital services in the EU but am not registered in all countries?\
**A:** By not registering in an EU country, you're essentially forgoing the opportunity to sell digital services in that region. Recurly will restrict digital sales to countries where you're not VAT registered, unless the customer provides a valid VAT number.

**Q:** Does Recurly facilitate VAT registration?\
**A:** While Recurly doesn't directly offer VAT registration, our tax partner, Avalara, does. They can assist with VAT registration, MOSS, and tax filing and reporting. These services are integrated into the AvaTax Pro feature, where you can link your AvaTax account to your Recurly site. To engage with our partners at Avalara, please reach out to [support@recurly.com](mailto:support@recurly.com).

**Q:** As a non-EU digital services provider, am I obligated to collect VAT?\
**A:** Yes, if you're catering to any non-VAT registered consumers within the EU. All digital services providers selling to the EU must collect VAT on sales to consumers, based on the customer's country rate. There's no minimum sales threshold; even a single sale mandates VAT collection and registration. We strongly advise all merchants, whether currently collecting taxes or contemplating it, to consult with a tax advisor. If you lack one, we can introduce you to tax experts at Avalara or Vertex for guidance. For introductions to Avalara or Vertex, please contact [support@recurly.com](mailto:support@recurly.com).

**Q:** If my clientele consists solely of VAT-registered businesses, can I ensure that cross-border sales remain VAT-free if the customer omits a VAT number during purchase?\
**A:** No. If the customer resides in an EU country, you've activated EU taxes, and the customer fails to provide a valid VAT number, Recurly will automatically add VAT to their purchase. If you wish to avoid all VAT collections outside your home country, it's advisable to mandate a VAT number from all EU customers.