---
title: Copy of Add-ons
excerpt: >-
  Elevate your subscription model with Recurly's versatile Add-ons. Tailor
  pricing, design unique add-ons or reuse items across plans, and enjoy flexible
  billing options. Streamline your product setup and enhance your offerings
  effortlessly.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

Add-ons are additional charges billed each billing period alongside a subscription's base charge. With the ability to associate one or more add-ons with each plan, Recurly offers customization, versatility, and granular control over your product & packaging. Add-ons can be unique to a plan or created from an Item in your Item Catalog for re-use across multiple plans, streamlining your product set-up.

# Key benefits

1. **Versatility**: Design your own add-on from scratch, or derive an add-on  from an Item in your Item Catalog to use across various plans.
2. **Customization**: Define your add-ons with properties such as type, name, code, accounting code, pricing model, price, tiers, taxes and options for opting out or editable quantity.
3. **Flexible billing options:** Tailor your billing approach with the option to bill up front or in arrears using usage-based billing.
4. **Enhanced pricing models**: Select from four pricing models: Fixed Price, Tiered, Volume, and Stairstep, offering the flexibility to meet diverse business needs.
5. **Items on subscriptions**: Configure item-based add-ons directly on customer subscriptions for even more streamlined operations.

# Creating an add-on

1. Navigate to your plan settings. This can be done either through the Recurly Admin Console or via the Plans or Add-ons API endpoints.

2. Choose to create an add-on that is unique to the plan, or create an add-on from a saved item in your catalog.

<Image align="center" border={true} width="75% " src="https://files.readme.io/5916c04-Screenshot_2023-12-05_at_1.58.47_PM.png" className="border" />

3. Define the add-on’s properties. This includes type, name, code, accounting code, HS Code, pricing model, price, tiers, taxes, and options for opting out or editable quantity. Some properties will auto-populate if you're creating an item-based add-on.

* **Accounting Code**: Select a unique code to identify plans in your internal invoice exports. This code should be configured based on your specific tax settings and compliance requirements. Limit to 25 lowercase alphanumeric characters.
* **HS code/Commodity code**:  Enter a Harmonized System (HS) code or Commodity Code to meet invoice compliance requirements for traded products. Generally, HS Code consists of at least six digits, with countries adding more digits for further national or regional classification. Recurly limits to 25 lowercase alphanumeric characters.

<Image align="center" border={false} width="75% " src="https://files.readme.io/8c21c4e0ebd874c93570696c830ee4b1e68664d47d108291d1fc23ff910077c1-image.png" />

4. Save your changes.

# Configuring item add-ons directly on subscriptions

1. Follow the instructions in our Item <a href="https://docs.recurly.com/docs/catalog" target="_blank">Catalog documentation</a>.
2. **Note:** You don't need to configure the availability of the add-on on the plan first.

Understanding and utilizing the add-on feature in Recurly can significantly enhance your subscription billing operations, providing the flexibility and customization necessary for diverse business models.