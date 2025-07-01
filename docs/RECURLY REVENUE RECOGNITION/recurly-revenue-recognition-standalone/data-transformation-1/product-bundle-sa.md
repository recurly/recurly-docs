---
title: Product bundle - Revenue Recognition Standalone
excerpt: >-
  Create and manage complex product bundles with precise pricing and cost
  allocation using Recurly Revenue Recognition Standalone.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Product Bundle allows grouping multiple individual products into a single unit for simplified sales and automated line-item expansion.

# Definition

In Recurly Revenue Recognition Advanced, a **Product Bundle** is defined by a Parent Identifier. When you upload a sales order (SO) file containing that parent identifier, the system automatically splits it into configured child lines. Each child line inherits its Sell Price, List Price, and Cost Price according to formulas you specify in the Product Bundle configuration.

# Key benefits

* **Automated line-item expansion**: Upload one parent SKU and let the system generate all child lines automatically.
* **Flexible pricing formulas**: Apply percentage-based formulas for sales, list, and cost prices on each child line.
* **Accurate cost & commission attribution**: Ensure precise revenue recognition, cost allocation, and commission tracking per component.

# Key details

## Configuring Product Bundles

1. Navigate to the **Transformation** section and select **Product Bundle**.

<Image align="center" className="border" border={true} width="30% " src="https://files.readme.io/bb61372-image.png" />

2. **Click** the **New** icon to create a Product Bundle.
3. **Provide** a **unique name** for the bundle.
4. **Select** the **Parent Identifier** attribute—this drives how parent lines split into child lines.
5. **Toggle** **Revenue Recognition**, **Cost**, and **Commission Attribution** on if applicable.
6. **Set** the bundle **Status** (active/inactive).
7. **Specify** **Effective Start** and **End Dates**.
8. **Click** the **Save** icon.
9. To edit, modify fields and click **Save** again.
10. To delete a bundle configuration, click the **Delete** icon.

*Below: example configuration of a “TV Bundle”.*

![](https://files.readme.io/ea99384-image.png)

## Defining bundle rules

1. Go to **Rule Set** at the top of the page.
2. Click the **New** icon to add child-line rules.
3. Under **Parent Identifier**, enter the exact value used in your SO file.
4. For each child line, define:

   * **Sales Price Formula**
   * **List Price Formula**
   * **Cost Formula**
5. If needed, override quantity per child line under **Quantity**.
6. Click **Save** to persist your rules.
7. To edit an existing rule, update its fields and click **Save**.
8. To remove a rule, select its row and click **Delete**.

**Example:** Configuring a TV Bundle with five child lines. Each line uses percentage formulas to split the parent’s total sales, list, and cost values. Quantities can be set independently of the SO file’s quantity.

![](https://files.readme.io/17c008d-image.png)

## How it works

When you upload an SO file containing the Parent Identifier:

* Recurly Revenue Recognition Advanced detects the bundle.
* It applies your configured formulas to split the parent line into child lines.
* Each child line inherits calculated Sell Price, List Price, Cost, and Quantity.
* Revenue recognition, cost allocation, and commission tracking occur automatically at the child-line level.