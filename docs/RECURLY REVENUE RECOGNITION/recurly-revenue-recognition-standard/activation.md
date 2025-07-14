---
title: Validation and activation for Revenue Recognition Standard
excerpt: >-
  Learn how to enable and validate Recurly Revenue Recognition Standard Edition
  for accurate and error-free revenue recognition.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Definition

Recurly Revenue Recognition Standard Edition validation and activation protocol must be followed to ensure accurate rule application and reduce errors. This involves selecting the Performance Obligation (POB) and General Ledger (GL) Accounts at the Product level within the Recurly UI.

* **Increased flexibility:** Simplifies the configuration of Recurly Revenue Recognition rules, providing a consistent method for choosing rules.
* **Simplified maintenance:** Allows for the maintenance of all rules through a single method.
* **Prevents premature activation:** Ensures rules are applied accurately by preventing premature activation.

# Key details

## Enabling Recurly Revenue Recognition Standard Edition

**Recurly Revenue Recognition Standard validation process:** Users must select the POB and GL Accounts when creating new plans, setup fees, add-ons, items, shipping, and gift cards. Additionally, users can define default POB and GL Accounts at the Business Entity level, which will auto-default to all plans and charges.

**Recurly Revenue Recognition Standard activation process:** Once validation is complete, the Enablement Manager can activate the integration on the chosen date.

> **Note:** Recurly Billing acts as the source of truth for Recurly Revenue Recognition Rules. The integration will not be active until the Recurly Revenue Recognition Standard is validated and activated. 

## Prevalidation

Before starting the validation process, complete these steps:

* **Assign** a POB and GL Account Code to all products, including existing plans, setup fees, add-ons, items, shipping, and gift cards.

<Image align="center" className="border" width="80% " border={true} src="https://files.readme.io/e99a298-image.png" />

* **Navigate** to Configuration → General Ledger Accounts.
* **Click** 'New accounting code' and add at least one revenue and one liability account.
* **Navigate** to Configuration → Business Entities.
* For each business entity, **click** 'Edit' and set the default Liability and Revenue Accounting codes.

<Image align="center" className="border" width="80% " border={true} src="https://files.readme.io/598eef9-image.png" />

> **Note:** The validation process cannot be completed until these configurations are set.

## Validation steps

1. **Click** 'Get Started' in the information box on the left.

<Image align="center" className="border" width="20% " border={true} src="https://files.readme.io/0c16c94-image.png" />

2. **Click** 'Validate Configuration'. The system will check that all required configurations are in place.

<Image align="center" className="border" width="40% " border={true} src="https://files.readme.io/52f550b-image.png" />

3. If the Business Entities default account codes are missing, you will receive an error message. **Set up** the default account codes to proceed (see pre-validation directions).
4. If the Business Entities default account codes are set up, **you will see a confirmation screen**.

<Image align="center" className="border" width="40% " border={true} src="https://files.readme.io/a1c4fd2-image.png" />

5. **Select** the default POB and GL account codes for each product type. These defaults will apply to new products and any products that are missing the POB rules. 

> **Note:** You will need to determine the default rule for plans, set up fees, add-ons, items, shipping, gift cards, custom credits, and custom charges. This will be the default option when creating a new product. Once set, **defaults** cannot be changed; however, you will be able to modify the POB selection and GL account codes for individual products at any time.

6. **Click** 'Apply to confirm'.
7. If you require historical data, your **Enablement Manager** will assist in setting the correct performance obligations and GL accounts.
8. Upon successful validation, a confirmation screen will appear.

<Image align="center" className="border" width="50% " border={true} src="https://files.readme.io/209d6d3-image.png" />

## Activation

Once validation is successful, Enablement Managers will revalidate the configurations and set the activation date according to your needs. If necessary, the activation date can be rescheduled.

<Image align="center" className="border" width="20% " border={true} src="https://files.readme.io/b648a43-image.png" />

At the time of activation, the validation flow will trigger again to check for any missing Recurly Revenue Recognition elements in new plans/items. If no errors are found, the activation will be completed. If errors are found, activation can be rescheduled until the errors are resolved.