---
title: Contract modification
excerpt: >-
  Discover the intricacies of modifying contracts within Recurly's platform,
  ensuring seamless adjustments to price, term, and more.
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

This feature is part of our product, Recurly Revenue Recognition Advanced. [<a href="https://docs.recurly.com/docs/recurly-revenue-recognition-advanced" target="_blank">Learn more here</a>].

### Prerequisites

* A valid Recurly account with appropriate permissions.
* Basic understanding of Recurly's Revenue Recognition processes.
* Familiarity with contract terms and conditions.

### Limitations

* Modifications must be approved by both parties.
* Not all types of modifications may be supported under certain conditions.
* Manual modifications using revenue workbench may be treated differently.

# Definition

Contract modification in Recurly Revenue Recognition pertains to the approved alterations in the price, term, or both of a contract. These changes are mutually agreed upon by both the supplier and customer, either in writing or through established practices.

# Key benefits

* **Flexibility**: Easily adjust contract terms to accommodate changing business needs.
* **Automation**: System automatically selects sub-types based on the nature of the modification.
* **Clarity**: Clear categorization of modifications ensures accurate revenue recognition.
* **Efficiency**: Streamlined processes reduce manual intervention and errors.
* **Transparency**: All modifications are traceable and viewable within the Revenue Workbench.

<Image align="center" width="60% " src="https://files.readme.io/1c72453-image.png" />

# Types of modification supported in Recurly Revenue Recognition

Recurly Revenue Recognition supports six primary types of contract modifications. Each primary type encompasses various sub-types. Depending on the nature of the change during the set Contract Revision Level, specific actions are triggered:

1. **New Line/POB**: The system selects an appropriate sub-type under New Line/POB based on the modification.
2. **Price Change**: A sub-type under **Price Change** is chosen based on the nature of the price alteration.
3. **Quantity Change**: The system determines a sub-type under Quantity Change according to the modification.
4. **Term Change**: A sub-type under **Term Change** is selected based on the term adjustment.
5. **Cancellations / Returns**: This category is activated when a contract amendment results from a cancellation or return.
6. **All Others**: Any alterations made to the Contract using Manual Functions in the Revenue Workbench are treated as a Contract Modification.

The following screenshot illustrates the diverse contract modifications supported by Recurly Recurly Revenue Recognition:

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/1b83a1b-image.png" />

## Important terminology in contract modification

* **POB related Terminologies**: POBs are categorized as distinct or non-distinct based on term, quantity, or both.
* **SSP related Terminologies**: Terms such as "Within SSP Range" and "Outside SSP Range" are used to describe the sell price of a new line in relation to the SSP range.
* **Treatment related Terminologies**: Contract modifications can be treated in various ways, including "Cumulative Catchup," "Prospective Catchup," and "No Allocation."

## Setting revision levels in Recurly Revenue Recognition Advanced

In Recurly Recurly Revenue Recognition, users can define the Contract Revision Level to specify the duration for system recognition of the modification.

#### Setting the Contract Revision Level:

1. **Navigate** to: Setup → Profiles → Contract Revision Level option.

<Image align="center" className="border" border={true} src="https://files.readme.io/a008b06-image.png" />

2. In the value column of the Contract Revision Level option, select from the dropdown:
   * **All**: All changes to the contract are treated as modifications.
   * **Period**: Changes in the next and subsequent periods are recognized as modifications.
   * **Quarter**: Adjustments in the next and subsequent quarters are considered modifications.

## Changing treatment in modification rules

To tailor the treatment during contract modification, follow these steps:

1. **Navigate** to Setup → Contract Modification.
2. **Choose** the desired contract modification rule from the dropdown list.

<Image align="center" className="border" border={true} src="https://files.readme.io/c5aaee1-image.png" />

## Viewing modifications in the workbench

To inspect a Contract Modification:

1. **Access** the Revenue Workbench and select the modified contract.
2. Under the modifications tab of the contract, all changes and revision levels are displayed.

<Image align="center" className="border" border={true} src="https://files.readme.io/56a1b13-image.png" />

# FAQs

**Q:** What is a Contract Modification in Recurly Revenue Recognition Advanced?\
**A:** It's an approved change in the price, term, or both of a contract within Recurly's revenue recognition platform. Both the supplier and customer must agree on this modification.

**Q:** How many types of modifications does Recurly Revenue Recognition Advanced support?\
**A:** Recurly RevRec supports six primary types of modifications, each with its own sub-types. These include New Line/POB, Price Change, Quantity Change, Term Change, Cancellations/Returns, and All Others.

**Q:** Can I manually modify a contract in Recurly Revenue Recognition Advanced?\
**A:** Yes, you can make manual modifications using the Revenue Workbench. However, these changes are treated as a special "All Others" type of Contract Modification.

**Q:** How can I view the changes made to a contract?\
**A:** Navigate to the Revenue Workbench and select the modified contract. Under the modifications tab, you'll see all changes and revision levels.

**Q:** What's the difference between "Cumulative Catchup" and "Prospective Catchup" treatments?\
**A:** "Cumulative Catchup" considers the retrospective approach, recalculating amounts from the beginning of the contract. "Prospective Catchup" only considers changes from the moment they were made, excluding amounts posted in closed periods.

**Q:** How do I set the Contract Revision Level?\
**A:** Go to Setup → Profiles → Contract Revision Level option. From there, you can select the desired revision level from the dropdown, such as "All," "Period," or "Quarter."

**Q:** What happens if a new line's sell price falls outside the SSP range?\
**A:** It's termed as "Outside SSP Range." This terminology is used to describe the sell price of a new line in relation to the SSP range.

**Q:** Are all modifications treated the same way in Recurly Recurly Revenue Recognition Advanced?\
**A:** No, modifications can be treated in various ways, including "Cumulative Catchup," "Prospective Catchup," and "No Allocation," depending on the nature of the change and the settings you choose.
