---
title: Hybrid pricing
excerpt: >-
  Unlock ultimate flexibility in your pricing strategy with Recurly's Hybrid
  Pricing Model. Seamlessly combine recurring, quantity-based, usage-based, and
  one-time models to cater to your unique business needs.
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

The Hybrid Pricing Model allows for a combination of different pricing models such as recurring, quantity-based, usage-based, and one-time models. This strategy enables subscriptions and custom charges (non-recurring products) to be purchased together in a single transaction.

# Key benefits

- **Flexibility:** It accommodates a wide variety of business models and product offerings, accommodating both recurring subscriptions and one-time charges.
- **Single transaction:** Simplifies the purchasing process by allowing customers to purchase subscriptions and one-time products in a single transaction.
- **Tailored pricing:** Allows businesses to precisely tailor their pricing strategies to their unique product offerings and customer needs.
- **Improved customer experience:** By offering a seamless purchasing process, it enhances the overall customer experience.
- **Effective for diverse product offerings:** Perfect for businesses that offer a combination of digital goods, physical goods, SaaS, and more.

# Key details

The Hybrid Pricing Model by Recurly offers an adaptive solution for businesses requiring diverse pricing strategies. By combining recurring, quantity-based, usage-based, and one-time models, you can address a wide range of business needs. The Hybrid Model particularly excels at supporting subscriptions and custom charges (non-recurring products) purchased together in one transaction.

## Example

To better illustrate the functionality of Hybrid Pricing, we’ve provided a few examples across different industries:

| Industry        | Example                                                                                                            |
| :-------------- | :----------------------------------------------------------------------------------------------------------------- |
| SaaS            | A CRM software charges $50/month/user and charges for usage based on the number of leads generated or emails sent. |
| Streaming media | A streaming service charges $39.99/month and offers one-time products such as movies or TV show seasons.           |
| Consumer goods  | Pet supplies service charges $9.99/month subscriptions and tiered pricing for toy add-ons.                         |

# Guide to activate hybrid pricing

1. **Understand Hybrid Checkout:** Hybrid checkout introduces the concept of a 'purchase' that includes recurring and non-recurring products. It incorporates subscriptions with custom charges.
2. **API Integration:** To use the hybrid model, you'll need to integrate with Recurly's API. 
3. **Create a Purchase:** In the API request, submit a subscription with one or many add ons or adjustments on a new or existing account. The subscription and adjustments will appear as line items on a single invoice, which is collected immediately.
4. **Transaction Management:** A purchase transaction is a single transaction to the gateway. If successful, it will update or create an account in Recurly. If the transaction fails, the request will be rolled back.
5. **Reference Documentation:** For more information on setting up a Hybrid Checkout, visit the <a href="https://developers.recurly.com/api/latest.html#operation/create_purchase" target="_blank">Purchases</a> section in Recurly's API documentation.

The Hybrid Pricing Model offers businesses the ultimate flexibility in pricing, accommodating a wide array of product offerings and customer purchasing habits. With Recurly's support, setting up this pricing model is straightforward, enhancing your ability to serve your customers better.