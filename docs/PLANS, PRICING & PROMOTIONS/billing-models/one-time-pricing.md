---
title: One-time pricing
excerpt: ''
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

# Definition

The One-Time Billing Model from Recurly is designed for businesses that need to charge a one-time setup fee or sell non-recurring items in addition to their regular subscription charges. This model is perfect for a variety of scenarios, such as a gym membership that includes an initial equipment fee, IoT companies that sell devices bundled with an annual service fee, web stores that offer exclusive items to their subscribers, or SaaS companies that levy flat fees for professional services or unique events.

Additionally, this pricing structure empowers merchants to sell products to their customers as standalone purchases, not tied to a subscription. Examples include a single purchase of a physical good, a Pay-Per-View event, or an educational course. This flexibility allows merchants to introduce additional revenue streams through one-time sales, enhancing their overall business model.

# Key benefits

- **Increased revenue streams:** Charging a one-time fee or selling additional items can significantly augment your revenue.
- **Versatility:** It supports a broad spectrum of business types, from IoT to gyms, web stores, and SaaS companies.
- **Ease of management:** The Catalog feature simplifies the management of one-time purchases.
- **Customer engagement:** Offering additional one-time purchases can boost customer engagement and satisfaction.

# Key details

The One-Time Billing Model leverages Recurly's Catalog feature for ease of recording and managing one-time purchases. With a default price setting and options to record commonly used attributes like SKU, accounting code, and tax information, the Catalog feature makes it straightforward to sell items via the Recurly API or the User Interface. This model is designed to give businesses more freedom and flexibility in how they charge their customers, enabling them to generate additional revenue from one-time purchases or setup fees.

## Example

| Industry  | Example                                                                                                     |
| :-------- | :---------------------------------------------------------------------------------------------------------- |
| Web Store | Rocksbox service offers members the option to purchase a broader selection of jewelry from their web store. |
| SaaS      | TheHealthyBack charges a flat fee for professional services or one-time events.                             |

# Set up one-time billing model

1. **Incorporate a Setup Fee:** Each plan can have one set-up fee. This is ideal for businesses that require an initial investment from the customer, such as gyms, SaaS, or IoT companies.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d9b94cc-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "50% ",
      "border": true
    }
  ]
}
[/block]


2. **Use the item catalog feature:** If your business sells one-time items, use Recurly's <a href="https://docs.recurly.com/docs/catalog" target="_blank">catalog</a>. feature to detail what you sell. This feature helps to record one-time purchases and set a default price. Additionally, it lets you document commonly used attributes such as SKU, accounting code, and tax information, making it easy to sell items via Recurly API or UI.
3. **Implement one-time purchases:** In your checkout flow, create an adjustment on the account for the product through the Purchases endpoint. This endpoint allows for billing both recurring and one-time purchases together.