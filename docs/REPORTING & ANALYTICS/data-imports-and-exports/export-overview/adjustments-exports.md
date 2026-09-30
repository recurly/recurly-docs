---
title: Adjustments - export
excerpt: Unveil detailed insights with the Adjustments Export feature.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Contract grouping

Contract Grouping lets you define specific criteria for grouping transactions into contracts, so revenue recognition stays accurate and efficient. Set up grouping rules once, and Recurly RevRec applies them automatically as transactions come in.

Available as part of Recurly RevRec

# Configuring a Contract Grouping rule

1. #### Open Contract Grouping
   Navigate to the Rules section and select "Contract Grouping."

2. #### Start a new rule

   Select the "+" icon in the right menu to create a new grouping rule.

   ![](https://files.readme.io/73e91e0-image.png)

3. #### Name and date the rule

   Provide a name for the contract grouping rule and specify its active date.

   ![](https://files.readme.io/7609ae3-image.png)

4. #### Add grouping criteria

   Under the Grouping section, select the "+" button to add grouping criteria.

   ![](https://files.readme.io/37d95e4-image.png)

5. #### Select grouping attributes

   Select the grouping attribute or attributes that define how contracts should be grouped. Recurly RevRec groups transactions into the same contract only when they share the same value for every attribute you select here — for example, selecting **Account** and **Plan** groups all transactions for a given account on that plan into one contract, while transactions on a different plan for the same account form a separate contract.

   The attributes available here come from the fields enabled on the [Attribute labels](https://docs.recurly.com/recurly-revrec/docs/attribute-labels) page (Setup → Attribute Labels → Contracts tab) — the list reflects your site's own configuration rather than a fixed set. To add or change which attributes appear here, update them there first.

6. #### Set the rolling window

   Specify the rolling date and the number of days for the grouping rule.

   ![](https://files.readme.io/0aa6811-image.png)

7. #### Save
   Save your configuration.

# Inactivating a Contract Grouping rule

<Callout icon="📘" theme="info">
  ### Note

  Once a Contract Grouping rule is created, it can't be deleted. You can inactivate a grouping rule instead, if needed.
</Callout>

To inactivate a grouping rule:

1. #### Select the rule
   Go to the Contract Grouping section and select the grouping rule tab you want to inactivate.

2. #### Change the status

   The rule's current status is "active." Change it to "inactive."

   ![](https://files.readme.io/8c5328f-image.png)

3. #### Save
   Select the Save icon to save your changes.

* Only active grouping rules appear in the Contract Grouping section.
* Once a grouping rule is inactivated, it moves to the inactive tab for reference.
* An inactive grouping rule can't be made active again.
