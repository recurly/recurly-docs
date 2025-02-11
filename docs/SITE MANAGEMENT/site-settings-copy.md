---
title: Site Settings (Legacy)
excerpt: >-
  [Your Recurly site settings](https://app.recurly.com/go/configuration/edit)
  are core to your business. These settings help define your address and
  currency requirements, set your company contact information, and establish
  payment gateway support for your business location.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Clear Test Data

To remove all test data from your Recurly sandbox site, simply utilize the **Clear Test Data** button. This action will delete all test [accounts][2], along with their associated [subscriptions][3] and [transactions][4], ensuring a clean slate for further testing and experimentation.

![](https://files.readme.io/82abc75-Screenshot_1.png)

It's important to note that this action will not affect any configuration elements like [subscription plans][5], [coupons][6], or email templates. However, it will remove third-party integrations such as Xero and QuickBooks Online, as well as any configured webhook endpoints. It's crucial to exercise caution when using this irreversible action.

## Site Subdomain

To update the name shown on your customer bank statements, please contact your merchant bank and request an update to your DBA.

Site subdomain is used on hosted pages and within your API credentials, so changes to site subdomain will also require an update to your API authentication. You may need to log out and log back in to see subdomain changes take effect.

> 📘 Company DBA Name
> 
> For certain gateways, you may need to configure your company's DBA (doing business as) name as this will be included in the transaction request. This will be configured under your Site Settings. Note, if this field is left blank, then Recurly will use the Site Name populated on your Site Settings page.

## Address Requirements

This sets the minimum fields required for billing address from your customers. Please make sure this matches the address requirements for [your gateway][7]'s **Address Validation Service** requirements. Most gateways require **Street Address** and **Postal Code**, while [PayPal][7] requires a full address, and [Beanstream][7] asks for full address and phone number.

_Recurly recommends collecting postal code at a minimum._

### Taxes

If you are collecting taxes, make sure you are collecting enough address information for an accurate tax rate. When taxes are enabled, Country is automatically required for all Billing Information addresses on your site. Site Settings address requirements do not work with the Account Information address. If you are taxing based on the Account Information address, make sure you collect and save in Recurly the details you will need for an accurate tax rate. 

Here are our recommendations:

- United States - Full Address (Postal Code and Country is required at a minimum for U.S. Sales Tax to be calculated.)
- Canada - Country and State/Province
- Australia, New Zealand, Israel, European Union, Non-EU Europe - Country

### Countries, Provinces and States

Recurly uses <a href="https://docs.recurly.com/countries-provinces-and-states">ISO alpha-2 country codes</a> on all forms.  For example, United Kingdom is "GB", not "UK". Only the United States (US), Canada (CA), Italy (IT) and the Netherlands (NL) will require a state/province if that field is required in your Site Settings address requirements. <a href="https://docs.recurly.com/countries-provinces-and-states">See Recurly's ISO alpha-2 Codes.</a>

[7]: /docs/payment-gateways

## Accepted Currencies

Merchants with [our Multiple Currency add-on][8] are able to define multiple currencies in their Recurly account, which is set here. Once you start processing transactions in one currency, _you will not be able to change your site to another currency_.

[8]: /docs/currencies

## Billing & Technical Contact

Recurly will communicate directly with **Billing Contact Email** for any Recurly receipts. This email address is also your site's default **From** email address, but this can be reconfigured in your [Email Templates][9]. The **Technical Contact Email** and **Phone Number** will be used for any major technical issues related to your site. Since many of these messages are directly actionable, please do not use role-based email addresses (e.g. sales@, info@, or admin@) for either of these contacts.  

[9]: /docs/email-templates

## Company Details

These fields define your company information for display on your customer invoices. Setting your country will also determine the [Payment Gateways][7] available to your business.

## Tax Information

In September 2020, Recurly introduced the ability to set Tax Identification Numbers per country and display only the relevant country's information on each invoice. More information below. To configure these settings, please refer to your Site Settings page.

Setting country-specific VAT numbers in **Tax Settings** will allow you to configure tax identification information and include it on customer invoices on a country-by-country basis. For example, if you are registered to sell in Singapore and Turkey, you can enter your tax registration numbers for those countries. A Turkish customer would only see your Turkish ID, and a Singaporean customer your Singaporean tax ID.

## IP Address Range Allowlist

This feature allows merchants to specify a public IP address or range that represents your computers and bypasses Recurly's fraud checks. This feature is especially useful for merchants who manually process transactions on behalf of their customers.

IP Addresses can be given in the following formats:

**Single IP**: 192.168.0.1

**IP Range**: 192.168.12.0/24 (Range must be narrower than /24).

## Invoice Prefixing

Merchants who have multiple billing systems funneling into one gateway account can define an **Order Number Prefix** inside of Recurly. This will help you uniquely identify Recurly transactions inside your payment gateway virtual terminal. Please note that this is on the backend only and will not show up on the invoice.

**_Paypal Payment Gateways does not support invoice prefixing._**