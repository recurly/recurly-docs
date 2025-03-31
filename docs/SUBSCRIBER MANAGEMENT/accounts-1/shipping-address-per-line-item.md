---
title: Shipping addresses per purchase
excerpt: >-
  Unlock advanced shipping address functionalities for each purchase, enhancing
  the billing process for multi-location and B2C operations.
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

This feature is only available on advanced plans. If you’re currently on Pro or Starter, you may need to upgrade your plan to access it. Please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) for more information.

### Prerequisites

Please contact [support@recurly.com](mailto:support@recurly.com) to have this feature enabled on your site.

If you are an existing customer, you ***must*** have "**Only Bill What Changed**" enabled on your site first. See <a href="https://docs.recurly.com/docs/change-subscription#section-only-bill-what-changed-release" target="_blank">here</a> for more information.

# Definition

The "Shipping Addresses per Purchase" feature in Recurly facilitates the assignment of distinct shipping addresses for individual purchases, including for separate line items within a single purchase. This functionality enables businesses to cater to specific B2C needs, such as customers desiring to send products to multiple destinations, or B2B requirements for multiple taxation based on distinct locations.

For businesses seeking to provide a seamless shopping experience to their customers by offering the flexibility of multiple shipping addresses for individual purchases, the "Shipping Addresses per Purchase" feature is a game-changer. With clear invoice displays, accurate taxation, and comprehensive export functionalities, Recurly ensures businesses can navigate the complexities of multi-address billing with ease.

# Key benefits

* **Individualized taxation:** Tax each line item based on its distinct shipping address, improving taxation accuracy.
* **Enhanced flexibility:** Assign various shipping addresses for each line item within a single purchase.
* **Improved customer experience:** Allow customers the flexibility to receive products at multiple destinations within a single purchase.
* **Efficient data management:** Avoid duplicity by ensuring that identical addresses aren't added to an account multiple times.
* **Clear invoicing:** Enhanced invoice displays clearly associate shipping addresses with their respective line items, eliminating confusion.

# Key details

The recent feature enhancement to Recurly offers businesses the capability to individually assign shipping addresses to both subscriptions and one-off charges within a purchase. Through the purchase endpoint in the API, businesses can specify unique shipping addresses for each line item. This advanced functionality is beneficial for B2C businesses selling physical goods, allowing customers to receive their products at various addresses. Moreover, B2B businesses can benefit from this feature by taxing their customers based on multiple operational locations.

**Using the API**: Through the purchase endpoint, businesses can:

* Designate a new shipping address for an entire purchase, which will be applicable to all line items.
* For multiple shipping addresses, the final one listed in the API request is applied to the purchase.
* Assign new or existing shipping addresses for individual line items.
* However, errors arise if both a shipping address ID and a new address are provided for the same charge or subscription.

**Invoice Display**: Invoices have been revamped to clearly showcase multiple shipping addresses, ensuring clarity about which address correlates with which line items.

**Tax Implications**: With this feature, an invoice can reflect diverse tax rates. Each line item will be taxed based on its associated shipping address. In instances where a line item doesn’t have a designated shipping address, it gets taxed according to the billing or account address.

**Exports**: Given that an invoice might have multiple shipping addresses associated with it, the Adjustments - Export can help in determining the specific address linked with a line item. Several new columns have been added for more detailed shipping address fields.

# Shipping Addresses per Purchase

We recently launched the ability to assign a shipping address to a purchase (which can include subscriptions and one time charges). Additionally, when using the purchase endpoint in our API, you can also specify different shipping addresses per line item. For example,  if you have the [multiple subscriptions](https://docs.recurly.com/v1.0/docs/multiple-subscriptions) feature enabled, you can specify different shipping addresses for each subscription and/or custom charge(s)

It's a great feature for B2C physical goods businesses that allow customers to ship their products to more than one address (e.g customer wants to send products to friends). It can also be useful for B2B businesses who have customers that need to be taxed based on multiple locations.

# Step-by-step process

1. **Enable the Feature**: Contact [support@recurly.com](mailto:support@recurly.com) to activate "Shipping Address(es) per Purchase" for your site.
2. **Check settings**: Ensure you have the "**Only Bill What Changed**" feature activated.
3. **API Integration**:
   * Use the v2/purchases endpoint in the API.
   * For assigning a new shipping address to the entire purchase, provide the address details.
   * To assign shipping addresses to individual line items, specify the address or address ID for each line item.
   * Avoid providing both a shipping address ID and a new address for the same item.
4. **Check Invoice Display**: After making a purchase with multiple shipping addresses, review the invoice display to ensure clarity in address-line item associations.
5. **Handle Taxes**: Ensure your site's tax settings are adjusted to tax each line item based on its shipping address.
6. **Review Exports**: Regularly check the Adjustments - Export to keep track of shipping addresses associated with each line item.

<Image align="center" className="border" border={true} src="https://files.readme.io/369dd28-Screenshot_2018-02-18_15.06.55.png" />

## Using the API

The purchase endpoint in our API supports the following shipping address functionality:

* Apply a new shipping address for a purchase
* This top level address will apply to all line items (subscriptions and one time charges) in a purchase  
* If multiple new shipping addresses are provided, the last address in the API request will be applied to the purchase
* any subscriptions in the purchase will be associated with the shipping address applied 
  * Apply a new or existing shipping addresses per line item 
* A new shipping address or existing shipping address ID can be specified per line item (subscription or charge)
* If both a shipping address ID and new shipping address are provided for the same subscription or charge, an error will be returned. 

> 🚧 Duplicate shipping addresses
>
> If a new address is specified either at the purchase level or line-item level, and the exact address already exists on the account, Recurly will ensure that the duplicate address will not be added to  the account. It is also suggested that you reference the shipping\_id if the shipping address already exists.

## Invoice Display

We've updated the invoice display in order to handle invoices with multiple shipping addresses so that it is clear to the customer of which shipping address is associated with which line item(s).

#### Example

Lisa purchases three monthly Kale Krate subscriptions. One box is for her sister Sarah, the second box is for her mother Shirley, and the third box is for herself. She also decides to purchase a blender (a one-time product) for her friend, Bill. All four of the family members live in different states. With the new shipping address functionality, the invoice will contain multiple shipping addresses associated with their correlated subscriptions and charge(s) adjustments The Kale Krate and the blender will be shipped to their respective person's address.

**Enhancements**

* Address at the top of line item table for each shipping address and its associated line items
* if a line item(s) does not have a shipping address and inherits the billing address as its taxable address, this billing address will be specified at the top of the table with the associated line-items
  * Shipped To section will include special note (the Shipping Address Count will not include billing or account addresses)

<Image title="Screenshot 2018-02-18 15.06.55.png" alt={1260} align="center" border={true} src="https://files.readme.io/369dd28-Screenshot_2018-02-18_15.06.55.png">
  This is the invoice display for a multiple shipping address purchase example, outlined above.
</Image>

> 📘 Is there a limit on shipping addresses allowed on an account?
>
> Yes. We will still enforce the existing rule of 20 allowed shipping addresses per customer account. This applies to shipping addresses created in the API (via purchase endpoint or shipping address endpoints) and the Admin UI. Also keep in mind that Recurly can only render up to 500 line items in an invoice.

# Taxes

If taxes are enabled on your site, with this feature, an invoice can have more than one tax rate. We will tax each line item based on it's associated shipping address. If a line item does **not** have a shipping address specified, it will be taxed based on the billing address or the account address if your tax settings are configured as such. If you are using manual collection for your invoices, the subscription charge and/or one time charge adjustment will be taxed based on account address.

Please see [Tax Invoices](https://docs.recurly.com/v1.0/docs/tax#section-tax-invoices) for more information. 

> 🚧 Multiple Tax Rate Invoice and Open Amount Refunds
>
> Until you have the Credit Invoices feature enabled on your site, open amount refunds will not succeed on invoices where there are multiple tax rates. This is due to existing behavior, where a line-item specific tax rate can't be applied. Credit Invoices resolves this issue, and thus must be enabled on your site.

# Exports

With this feature, an invoice can have more than one shipping address associated with it since each subscription(s) charge and/or one time charge(s) adjustment could have different addresses. We recommend that you reference the Adjustments - Export to determine the shipping address associated with a line item. 

**Adjustments Export**\
We have added new columns for expanded shipping\_address fields. This will be useful in determining the shipping address associated with each subscription and/or one time charge adjustment. 

* ship\_address\_name
* ship\_address\_line1
* ship\_address\_line2
* ship\_address\_city
* ship\_address\_state
* ship\_address\_zip
* ship\_address\_country
* ship\_address\_phone

**Invoice - Summary Export**\
For shipping addresses created using the purchase endpoint, there will be a new shipping\_address\_count field. This is a count of the number of shipping addresses created on an invoice. The shipping\_address field will never be set for invoices created in the purchase endpoint, as there can be more than one shipping address per invoice. This shipping\_address field will only be populated for invoices created using the subscriptions endpoint. You can reference the shipping\_address\_count field to determine if there is more than 1 address and use the **Line Items** export to identify each shipping address.
