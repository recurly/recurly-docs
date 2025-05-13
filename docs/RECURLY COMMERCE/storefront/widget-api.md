---
title: Widget API
deprecated: false
hidden: true
metadata:
  robots: index
---
# 👩‍💻 Widget API Documentation

<br />

<br />

### Links

<br />

* [Shopify Subscription Documentation](https://shopify.dev/apps/subscriptions)
  * Selling Plan Fields: [https://shopify.dev/api/admin-graphql/2022-07/objects/sellingplan](https://shopify.dev/api/admin-graphql/2022-07/objects/sellingplan)
    <br />

### Liquid Objects

<br />

Recurly Commerce subscription related data is available in Shopify liquid template objects

* [Product](https://shopify.dev/api/liquid/objects#product)
  * [Selling Plan](https://shopify.dev/api/liquid/objects#selling_plan)
    <br />

### Product Details

<br />

Gets the product information for a given productId

<br />

```
```

<br />

#### Selling Plan Groups

Represents a selling method (for example, "Subscribe and save" or "Pre-paid").

| Field                   | Description                                                                    | Value                                                                                                                       |   |
| ----------------------- | ------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------- | - |
| productId               | Shopify Product ID                                                             |                                                                                                                             |   |
| hasVariantLevel         | boolean that indicates whether the product has any product variants available. |                                                                                                                             |   |
| requires\_selling\_plan | Whether the product has subscription offers available.                         |                                                                                                                             |   |
| variants                | Product variants                                                               |                                                                                                                             |   |
| type                    |                                                                                | “ONETIME\_AND\_SUBSCRIPTION\_AND\_PREPAID”, “ONETIME\_AND\_SUBSCRIPTION”,"PREPAID\_SUBSCRIPTION\_ONLY, “SUBSCRIPTION\_ONLY” |   |

#### Selling Plan

Represents how a product can be sold and purchased.

| Field                   | Description                                                                                                             | Value                                                                                                                                                                   |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| specialDiscountActive   | Whether the subscription has any discount available                                                                     | boolean                                                                                                                                                                 |
| specialDiscount         | Discount amount                                                                                                         | number                                                                                                                                                                  |
| discountType            | Description: By Quantity, By Orders or Free Shipping                                                                    | “ORDER”, “QUANTITY”                                                                                                                                                     |
| specialDiscountModifier | The unit of the special discount                                                                                        | “PERCENTAGE”, “AMOUNT”, “FIXED\_AMOUNT”                                                                                                                                 |
| numberOfOrders          | Number of orders of the selling plan                                                                                    | number                                                                                                                                                                  |
| shippingDiscount        | discount applied to the shipping (free shipping)                                                                        | \{ active: boolean; countries: \{ all: boolean; countries: null; }; requirements: \{ type: string; amount: number; }; numberOfOrders: null; }                           |
| specialDiscountType     | Type of the special discount                                                                                            | 'QUANTITY', 'SHIPPING', 'ORDER', 'NONE'                                                                                                                                 |
| discount                | Amount of the discount                                                                                                  | number                                                                                                                                                                  |
| discountModifier        | The unit of the discount                                                                                                | “PERCENTAGE”, “AMOUNT”, “FIXED\_AMOUNT”                                                                                                                                 |
| optionOrder             | The order of the selling plan relative to the other selling plans (in which position of the dropdown it should show up) | number                                                                                                                                                                  |
| deliveryCadenceCount    | Delivery frequency (if it’s delivered every 2 weeks, then it’s 2).                                                      | number                                                                                                                                                                  |
| deliveryCadenceUnit     | Delivery frequency unit (if it’s every 2 months, then it’s “MONTH”)                                                     | 'DAY', 'MONTH', 'WEEK', 'YEAR'                                                                                                                                          |
| billingCadenceCount     | Billing frequency (if it’s every 2 weeks, then it’s 2)                                                                  | number                                                                                                                                                                  |
| billingCadenceUnit      | Billing frequency unit (if it’s every 2 weeks, then it’s “WEEK”)                                                        | 'DAY', 'MONTH', 'WEEK', 'YEAR'                                                                                                                                          |
| name                    | The default name of the selling plan, displayed in the widget subscription offer options dropdown.                      | string                                                                                                                                                                  |
| nameOverride            | The custom name of the selling plan, displayed in the widget subscription offer options dropdown.                       | string                                                                                                                                                                  |
| visibility              |                                                                                                                         | Array ('MERCHANT\_CONTRACT', 'STOREFRONT', 'SHOPPER\_CONTRACT', 'OFFER')                                                                                                |
| isDefault               | Indicates whether the selling plan should be selected by default                                                        | boolean                                                                                                                                                                 |
| discountCode            | Discount code available for the selling plan.                                                                           | string                                                                                                                                                                  |
| type                    | The selling group type                                                                                                  | 'ONETIME\_AND\_SUBSCRIPTION', 'ONE\_TIME\_AND\_PREPAID\_SUBSCRIPTION', 'SUBSCRIPTION\_ONLY', 'PREPAID\_SUBSCRIPTION\_ONLY', 'ONETIME\_AND\_SUBSCRIPTION\_AND\_PREPAID', |
| optionType              | Type of the selling plan, Note: use when type is “ONETIME\_AND\_SUBSCRIPTION\_AND\_PREPAID”                             | 'ONETIME\_AND\_SUBSCRIPTION', 'ONE\_TIME\_AND\_PREPAID\_SUBSCRIPTION', 'SUBSCRIPTION\_ONLY', 'PREPAID\_SUBSCRIPTION\_ONLY', 'ONETIME\_AND\_SUBSCRIPTION\_AND\_PREPAID', |
| giftOptions             | Contains the maximum number of deliveries for the gift purchase option                                                  | \{ maxDeliveries: number }                                                                                                                                              |
| sellingPlanGroupId      | Selling plan id from shopify                                                                                            | string                                                                                                                                                                  |

#### Prepaid - Example

<br />

```
```

<br />

#### One-time, Subscribe & Save, Prepaid - Example

<br />

```
```

<br />

### Store Theme

<br />

```
```

\<https\://subs.api.tryprive.com/stores/>\<shopify store url>/settings?themeId=\<theme\_id>
&#x20;&#x20;
\`\`\`

\| currency             | The currency used for the store                                                                                               | string                                                               |
\| -------------------- | ----------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
\| money\\\_format        | The price format                                                                                                              | string                                                               |
\| multilocation        | You can set up multiple locations in your Shopify store so that you can track inventory and fulfill orders at your locations. | boolean                                                              |
\| oneTimeFirst         | Whether the One-Time purchase should show up first, relative to the other offer options position                              | boolean                                                              |
\| onetimeCopy          | The text for the One-Time Purchase option title                                                                               | string                                                               |
\| subscribeCopy        | The text for the Subscription Offer option title                                                                              | string                                                               |
\| prepaidCopy          | The text for the Prepaid Offer option title                                                                                   | string                                                               |
\| subOptionCopy        | ?                                                                                                                             | string                                                               |
\| bgColor              | The background color for the widget elements                                                                                  | string                                                               |
\| borders              | The border properties for the widget elements                                                                                 | \{ borderRadius: string; borderWeight: string; borderColor: string; } |
\| accentColor          | Radio button color                                                                                                            | string                                                               |
\| quantityStyle        | Style for the quantity selector                                                                                               | string                                                               |
\| bgColorOnSelection   | Color for the product variant selection box                                                                                   | string                                                               |
\| deliveryEveryStyle   | custom CSS for the delivery frequency options                                                                                 | CSS Object                                                           |
\| purchaseOptionsStyle | ?                                                                                                                             | CSS Object                                                           |
\| selectedOptionsStyle | Styles for the text area                                                                                                      | CSS Object                                                           |
\| rank                 | Order for the subscription offer options                                                                                      | defaults to: \{ one-time: 1 subscribe: 2 prepay: 3 }                  |

\`\`\`jsx
\{
&#x20;   "currency": "USD",
&#x20;   "money\_format": "$\{\{amount}} USD",
&#x20;   "multilocation": true,
&#x20;   "widget\_settings": \{
&#x20;       "elements": \{
&#x20;           "buttonPrice": "not-existing-tag"
&#x20;       },
&#x20;       "customCss": null,
&#x20;       "onetimeFirst": false,
&#x20;       "onetimeCopy": null,
&#x20;       "subscribeCopy": "Discount Subscription",
&#x20;       "prepaidCopy": "Prepaid Subscription",
&#x20;       "subOptionCopy": null,
&#x20;       "styling": \{
&#x20;           "bgColor": null,
&#x20;           "borders": null,
&#x20;           "accentColor": "#000000",
&#x20;           "quantityStyle": null,
&#x20;           "bgColorOnSelection": "#dbe4ff",
&#x20;           "deliveryEveryStyle": null,
&#x20;           "purchaseOptionsStyle": null,
&#x20;           "selectedOptionsStyle": \{
&#x20;               "color": "#000000",
&#x20;               "fontSize": "1",
&#x20;               "fontWeight": "bold"
&#x20;           }
&#x20;       },
&#x20;       "rank": null
&#x20;   }
}
\`\`\`