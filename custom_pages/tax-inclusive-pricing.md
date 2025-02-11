---
title: Tax Inclusive Pricing
fullscreen: false
hidden: true
metadata:
  title: ''
  description: ''
---
[block:callout]
{
  "type": "info",
  "body": "Tax inclusive pricing is only available using the Vertex tax service."
}
[/block]

Recurly’s new tax inclusive pricing feature allows you to set your prices inclusive of any taxes that your customers may have. You can set prices inclusive or exclusive of taxes on Recurly subscriptions, items, set up fees, and add-ons. You can set prices inclusive or exclusive of taxes on Recurly items, plan fees, plan set up fees, and plan add-ons.



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a290666-Screen_Shot_2022-04-22_at_12.12.14_PM.png",
        "Screen Shot 2022-04-22 at 12.12.14 PM.png",
        2402,
        1214,
        "#f8f8f9"
      ]
    }
  ]
}
[/block]

This feature will allow you to configure your plans as usual and then set tax inclusivity at subscription creation via the UI and API. For example, let’s say you create a plan called “Gold” at $10.00. You subscribe one customer, Customer X,  to the plan selecting the “price includes tax” option, and subscribe another customer, Customer Y, to the plan selecting the “price does not include tax” option - both customers will have a tax rate of 10.025%. Customer X will end up paying just $10.00. Customer Y will end up paying $10.00 + $1.02 of tax.

When subscribing a customer, the setup fee and whatever add-ons you create will inherit the tax status selected. Please see below screenshots for more information. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7a7b275-Screen_Shot_2022-04-22_at_12.23.30_PM.png",
        "Screen Shot 2022-04-22 at 12.23.30 PM.png",
        1530,
        772,
        "#f7f7f7"
      ],
      "caption": "Tax inclusive subscription invoice with add-on and setup fee."
    }
  ]
}
[/block]




[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/55a1a22-Screen_Shot_2022-04-22_at_12.23.19_PM.png",
        "Screen Shot 2022-04-22 at 12.23.19 PM.png",
        1504,
        730,
        "#f7f7f7"
      ],
      "caption": "Tax exclusive subscription invoice with add-on and setup fee."
    }
  ]
}
[/block]

Additionally, any items created by themselves, outside of the plan page, will inherit the tax inclusive status of that subscription

You are also able to create a one time purchase inclusive of tax. Simply add a charge to an account and select the “price includes tax” option. 

Please note, you are unable to change the inclusivity status of a subscription once it has been created.


## Discounts

See below to see how discounts are applied to purchases that are inclusive of taxes:
Percentage Discount
Tax inclusive price: $300.00
Tax rate: 10.025%
Discount amount: 20%
Price after discount: $240.00
Tax service returns: $217.69 subtotal + $22.32 tax

Fixed Amount Discount
Tax inclusive price: $300.00
Tax rate: 10.025 %
Discount amount: $60.00
Price after discount: $240.00
Tax service returns: $217.69 subtotal + $22.32 tax