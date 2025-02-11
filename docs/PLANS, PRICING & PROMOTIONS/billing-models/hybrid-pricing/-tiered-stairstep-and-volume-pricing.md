---
title: Tiered, stairstep and volume pricing
excerpt: >-
  Unleash the power of Tiered, Stairstep and Volume Pricing models with Recurly.
  Optimize your sales volumes, attract more customers, and scale your business
  effortlessly by creating incentivizing cost structures.
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

**Tiered pricing **is a progressive cost model that changes the unit price based on specified thresholds or "tiers." This dynamic pricing model incentivizes customers to purchase more, driving up sales volumes while creating a personalized buying experience.

**Volume pricing **is a pricing model where the per-unit cost decreases as the quantity purchased increases, encouraging customers to buy in bulk. The price for all units is determined by the highest tier reached by the quantity, resulting in overall cost savings for the customer.

**Stairstep pricing** is a pricing model that charges a flat rate for a defined range of quantities, creating distinct pricing "steps''. Each step represents a tier of volume, with the price remaining the same within that tier, regardless of the exact quantity purchased.

# Key benefits

1. **Tiered pricing benefit: **Encourages customers to purchase more items to reach a lower price per unit, thereby potentially increasing overall sales volumes.

2. **Volume pricing benefit:** Offers incentives for bulk purchases, which can lead to economies of scale, benefiting both the business and the customer through better prices and operational efficiencies.

3. **Stairstep pricing benefit: **Provides clear and predictable pricing within defined quantity ranges, simplifying budget planning for customers and revenue forecasting for businesses.

# Key details

## Tiered pricing

Tiered Pricing offers a strategic approach to price your products or services. At its core, it involves varying the price per unit depending on the quantity purchased by the customer, creating a pricing ladder or "tiers". For instance, a business may charge $1 per unit for the first 100 units. But if a customer needs more, the cost per unit beyond the initial 100 drops to 50¢. Such a structure incentivizes customers to buy in larger quantities, boosting sales volumes and overall profitability.

In Recurly, the tiered pricing model can be easily implemented when creating a new plan or using an existing add-on. The pricing model is determined at the plan level, allowing you to define tiers and prices as per your requirements. Once the tiers are set, Recurly handles the total calculation based on the chosen pricing model and quantity. If you're using Recurly's Checkout or Hosted Payment Pages, enabling the "Editable Quantity" checkbox allows your subscribers to set a quantity when signing up, providing them with an interactive and flexible purchasing experience.

## Volume pricing

Volume Pricing is a savvy strategy that incentivizes customers to purchase larger quantities by offering a lower per-unit price as they reach specific volume thresholds. All units are priced based on the rate of the highest tier reached. For example, if a company sells seats and a customer buys more than 20 seats, the per-seat price drops from $10 to $9. This pricing model is optimal for bulk purchases, providing both businesses and customers with the benefits of economies of scale.

Recurly's Volume Pricing model is straightforward to set up. Whether creating a new plan or using an existing add-on, you can choose 'Volume Pricing' in the pricing model section. Next, you define the volume ranges and corresponding costs, with higher quantities being allocated lower costs. Once the quantities for the subscription add-ons are set to align with the tiers, Recurly handles the calculation of the correct total. When using Recurly's Checkout or Hosted Payment Pages, you can also allow your subscribers to select their desired quantity by enabling the "Editable Quantity" feature.

## Stairstep pricing

Stairstep Pricing is a unique pricing strategy that charges a consistent rate within certain quantity ranges or tiers. For instance, a SaaS provider might offer tiers based on the number of seats purchased: $50 for 1-10 seats, $100 for 11-20 seats, and $150 for 21+ seats. Whether a customer acquires 25, 50, or 100 seats, they will pay the fixed price of $150. This pricing model provides predictable revenue for businesses and simplifies budget planning for customers, making it an excellent choice when the costs of delivering services do not increase linearly with each additional unit.

# Guide to activate the tiered pricing model

1. **Plan creation:** Start by creating a new plan or using an existing add-on in your Recurly account.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e850bbb00f83aebde0b5d78c438e65fa23822353957f35b74c219822162ac5cd-Screenshot_2025-01-16_at_11.38.57_AM.png",
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


2. **Pricing model selection:** In the pricing model section, choose 'Tiered Pricing'.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5e9aa7392e822d34d0daee0240098ae9fb192cac2ae433b05e15f7a0f84d9b67-Screenshot_2025-01-16_at_11.32.58_AM.png",
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


3. **Tier and price definition:** Since 'Tiered Pricing' is selected, you can now set up different tiers and respective prices at the plan level.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/77da2e9-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% ",
      "border": true
    }
  ]
}
[/block]


4. **Quantity assignment:** Input the quantity for the subscription add-on in line with the different tiers you've defined.
5. **Calculation management:** Recurly will automatically calculate the correct total based on the pricing model and quantity input.
6. **Editable quantity configuration:** If you're utilizing Recurly's Checkout or Hosted Payment Pages, check the "Editable Quantity" box. This enables your subscribers to choose their desired quantity when signing up.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dd26624-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% ",
      "border": true
    }
  ]
}
[/block]


By implementing Tiered Pricing, you can maximize your sales volumes, provide your customers with compelling incentives, and scale your business with ease and efficiency.

# Guide to activate volume pricing

1. **Plan Creation:** Begin by creating a new plan or using an existing add-on in your Recurly account.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/004922a55d36ae8e15474590e1bd1f78fbc016ec9ca92736c3d9532bc3452abd-Screenshot_2025-01-16_at_11.38.57_AM.png",
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


2. **Pricing Model Selection:** In the pricing model section, select 'Volume Pricing'.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/50fedf7bf0859eea6dd2c1c9e5acc7f142f91f9e3fec6bb1049d151cca5fcd50-Screenshot_2025-01-16_at_11.34.57_AM.png",
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


3. **Range and cost configuration:** Define the ranges based on the volume of the products. The larger the volume, the lower the costs.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/85273ad-image.png",
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


4. **Quantity assignment:** Enter the quantity for the subscription add-on, keeping in mind the different tiers you've defined.
5. **Calculation management:** Recurly will automatically calculate the correct total based on the pricing model and quantity input.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/57e6827-image.png",
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


6. **Editable quantity configuration:** If you're using Recurly's Checkout or Hosted Payment Pages, enable the "Editable Quantity" checkbox, allowing your subscribers to select their desired quantity during sign-up.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f2f99db-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% ",
      "border": true
    }
  ]
}
[/block]


Volume pricing presents a win-win scenario for both businesses and customers, creating a compelling incentive for larger purchases while promoting economies of scale. Recurly makes implementing this pricing strategy a seamless process, providing an efficient way to drive your revenue growth.

# Guide to activate stairstep pricing

1. **Plan Creation:** Initiate by creating a new plan or employing an existing add-on in your Recurly account.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/004922a55d36ae8e15474590e1bd1f78fbc016ec9ca92736c3d9532bc3452abd-Screenshot_2025-01-16_at_11.38.57_AM.png",
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


1. **Pricing model selection:** In the pricing model section, opt for 'Stairstep Pricing'.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c997473503d6a04046f5bc0df17ba02c179f3b7bf47860faed273b86863abdc5-Screenshot_2025-01-16_at_11.36.23_AM.png",
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


1. **Define range and cost:** Define the range for the stairstep pricing by selecting the starting and ending quantities and assigning the corresponding flat rate for that range. The rate remains consistent within this range.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7b3c437-image.png",
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


1. **Add "stairs":** Incorporate as many "stairs" (or tiers) as needed, adjusting the cost accordingly for each tier.

2. **Calculation management:** Recurly will take care of calculating the appropriate total, factoring in the chosen pricing model and quantity.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/de697fe-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% ",
      "border": true
    }
  ]
}
[/block]


1. **Editable quantity configuration:** If you're using Recurly's Checkout or Hosted Payment Pages, tick the "Editable Quantity" box, enabling your subscribers to specify their quantity when signing up.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eddbaf2-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% ",
      "border": true
    }
  ]
}
[/block]


Through the implementation of Stairstep Pricing, you can create a predictable revenue stream while offering an adaptable pricing model that caters to your customers' diverse needs.