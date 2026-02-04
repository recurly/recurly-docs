---
title: Level 2 and Level 3 / CEDP guide
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This guide shows you how to use the [Purchase endpoint](https://developers.recurly.com/api/latest/#tag/purchase) to create new subscriptions or purchases using Cards that includes Level 2 data, or Level 3 data, and some best practices for qualifying for the Visa CEDP program.

### Prerequisites & limitations

* Familiarity with Recurly’s V3 API, and basic REST concepts
* Familiarity with Recurly's line item catalog, shipping addresses, and shipping fees behavior.
* Familiarity with Recurly's taxation offerings:
  * [Avalara](https://docs.recurly.com/recurly-subscriptions/docs/avalara)
  * [Vertex](https://docs.recurly.com/recurly-subscriptions/docs/vertex)
  * [Recurly Tax Settings](https://docs.recurly.com/recurly-subscriptions/docs/taxes)
* [Completed the Quickstart Guide](https://docs.recurly.com/recurly-subscriptions/docs/quick-start-guide#/)
* [Completed the Coupons and discounts guide](https://docs.recurly.com/recurly-subscriptions/docs/coupons-and-discounts-guide)
* A supported gateway account. Check your individual gateway for L2/3 Support.

# &#x20;Definition

**Creating Purchases** refers to the process of generating new customer accounts alongside subscriptions in a single, consolidated call to the Recurly Purchase endpoint. This streamlines checkout experiences by bundling all required resources into one request.

**Creating Subscriptions** refers to the process of generating new customer accounts and subscriptions using the `subscriptions` endpoint in Recurly's V3 API. This endpoint cannot be used for one-time transactions, but also supports the relevant fields.

# Level 2 Requirements

<Callout icon="📘" theme="info">
  Level 2 Interchange program is sunsetting in April of 2026 for Visa Cards, and the CEDP program will be preferred. Level 3 data will be desired after that point. For Visa cards, see Level 3 requirements and speak to your gateway about qualification.
</Callout>

Level 2 Data generally consists of Tax Information and a Purchase Order Number (PO Number) in addition to baseline Level 1 Data which consists of the consumer's billing information at the very minimum. To ensure your transactions are not getting downgraded, ensure you're passing AVS data (Address Data) for all of your transactions.

Recurly supports passing tax information and a PO Number on all of our supported gateways. To pass tax information, you can use a supported tax integration, or setup taxes inside your Recurly site. To pass a PO number in either purchases or subscriptions, include the `po_number` field in your payloads when creating subscriptions and purchases.

Since Level 2 requires a minimum percentage of taxation, and as such, tax exempt businesses generally do not qualify for Level 2 Interchange programs. Minimum / Maximum taxation require to qualify falls between 0.1 percent and 31 percent of the total amount.

<br />

```json
{
  "currency": "USD",
  "account": {
    "code": "{{customer-account-code}}" // Account with Billing Information + Card on File
  },
  "line_items": [ // You may also supply Recurly item codes
    {
      "unit_amount": "10.00",
      "quantity": 2,
      "description": "Custom 4x4 Art Print",
      "type": "charge",
      "tax_code": "physical",
      "product_code": "100B",
      "tax_exempt": false,
    }
  ],
  "po_number": "123456", // Purchase Order Number 
  "gateway_code": "{{gateway-code}}"
}
```

# Level 3 Requirements

Level 3 Data consists of Level 1 + 2 data, plus a lot more, including line items and shipping information at a high level.  You will want to ensure you are passing Level 1 data (Name, Address information), Level 2 data (taxes or tax exempt status, and PO Number), in addition to the below data:

* **Line Items**: you will want to ensure you are sending quality line item data, and not generic information. Visa will be looking for quality of data, not just quantity of data. Read more about CEDP specifics in our [LIne Item](https://docs.recurly.com/recurly-subscriptions/docs/line-items) documentation. You may pass line items by setting up your catalog within your Recurly site, or passing in the data dynamically via API.
  * You will need to specify the product code, description, quantity, and if necessary, the HS/Commodity Code value. **You may not pass all zeroes**, and it is recommended to use the HS/Commodity Code values from one of our Tax Integrations such as Avalara or Vertex, or use the HS/Commodity Code lists available online.
  * HS Codes are supported on line item add-ons, and Plans:
    * [Add-Ons](https://docs.recurly.com/recurly-subscriptions/docs/add-ons)
    * [Plans](https://docs.recurly.com/recurly-subscriptions/docs/plans)
* **Shipping Costs**: See our documentation on how to pass shipping costs in our dedicated [Shipping Fees ](https://docs.recurly.com/recurly-subscriptions/docs/shipping)documentation.
* **Shipping Address** for the Consumer: See our documentation on how to pass shipping addresses in our dedicated [Shipping Addresses ](<* https://docs.recurly.com/recurly-subscriptions/docs/shipping-addresses>)documentation.
* All other required data is derived from your Recurly account or line item catalog setup.

**Example Here**
