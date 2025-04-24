---
title: Setup for Revenue Recognition Advanced
excerpt: >-
  Recurly Revenue Recognition Advanced: Streamlining Revenue Recognition and
  Financial Reporting.
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

This feature is part of our product, Recurly Revenue Recognition Advanced. \[<a href="https://docs.recurly.com/docs/recurly-revenue-recognition-advanced" target="_blank">Learn more here</a>].

### Prerequisites

* Familiarity with the organization's revenue recognition standards (e.g., IFRS-15 or ASC-606).
* At least one primary book must be configured in Recurly Revenue Recognition Advanced to process revenue transactions.
* Attributes must be defined in the Attribute Labels section for data collection.

### Limitations

* Only one Primary book is allowed in the system.
* Once a book is deactivated, it cannot be reactivated.
* Pipeline features are exclusive to Secondary books.

# Definition

Recurly Revenue Recognition Advanced is a comprehensive tool designed to guide and automate the revenue treatment of transactions. It offers a structured approach to setting up books, profiles, attribute labels, segments, and business events, ensuring accurate and efficient financial reporting.

# Key benefits

* **Versatility:** Allows for the establishment of multiple books, catering to varied revenue recognition treatments.
* **Precision:** Offers detailed attribute labels, ensuring accurate data representation and transfer.
* **Flexibility:** Supports both standard and custom business events, catering to diverse business requirements.
* **Efficiency:** Automated processes reduce manual errors and streamline financial reporting.
* **Integration:** Seamless integration with ERP systems, ensuring consistent and accurate data transfer.

# Key details

## Books

In Recurly Revenue Recognition Advanced, books are instrumental in determining the revenue treatment for transactions. Users can establish multiple books, allowing for diverse revenue recognition treatments based on each book's rules. Organizations can choose their Primary Book (either IFRS-15 or ASC-606) based on their country of origin or the currency of their accounts. To process revenue transactions in Recurly Revenue Recognition Advanced, at least one primary book must be configured.

**Creating Books:**

1. **Navigate to:** Set Up → Books

<Image align="center" className="border" border="true" src="https://files.readme.io/69476ad-image.png" />

2. \*\*Click \*\*on the “+” to initiate book creation. Ensure the following fields are completed:
   * **Name:** Must be unique (e.g., Revenue subledger book).
   * **Compliance:** Choose the relevant accounting standard (e.g., ASC 606 or IFRS 15).
   * **Type of Transactions:** Opt for either booking or pipeline transactions.
   * **Primary:** Mark if this is the main book. Only one Primary book is allowed. Unmarked books will be secondary, and multiple secondary books are permissible.
   * **Status:** Mark as Active if the book is in use. Once deactivated, a book cannot be reactivated.
   * **System controls:** Choose among Allocation, forecasting, cost, posting. Note: Primary books must always have posting active.

<Image align="center" className="border" border="true" src="https://files.readme.io/3a64df9-image.png" />

3. After setting up the book(s),\*\* click the Save icon\*\*.
4. Once books are established, the Revenue workbench offers options to view contracts under each book individually or collectively. Reports are tailored based on the created books.

> **Note:** Secondary books exclusively use the pipeline features for forecasting, resembling orders booked via opportunities rather than sales orders.

## Profiles

Profiles in Recurly Revenue Recognition Advanced are designed to set application-level controls.

**Configuring Profiles:**

1. **Navigate** to: Set Up → Profiles

<Image align="center" className="border" border="true" src="https://files.readme.io/8ea6717-image.png" />

2. **Profile Options:**
   * **Account separator:** Specifies the value for account separation.
   * **Commission only:** Indicates if only commission data is present.
   * **Global currency:** Designate the primary currency for financial reporting.
   * **Overage allowed:** Enable if invoicing above the transaction amount is allowed.
   * **Contract revision level:** Determine when a contract alteration is considered a Contract Modification.
   * **Revenue Duration:** Differentiate between short-term (within a year) and long-term (beyond a year) revenue for GAAP and IFRS disclosure.
   * **SSP DATE:** Recurly Revenue Recognition Advanced sets the SSP date for all transaction lines to the earliest sales order book date when configured in PROFILE.

3. After finalizing the profile settings, **click the Save icon**.

## Attribute labels

Attribute labels bridge the gap between Recurly attribute names and their counterparts in Recurly Revenue Recognition Advanced. They also dictate display preferences in various areas.

**Main Tabs under Attribute Labels:**

1. **Contracts:** Pertains to contracts/sales orders.
2. **Documents:** Relates to documents/invoices.
3. **Cost:** Concerns cost/expenses/commissions.
4. **Outbound Attributes:** Defines how data is relayed to the ERP system.

**Configuring Labels for Contracts, Documents, and Cost:**

1. For each tab, **set labels** to determine display preferences and order.
2. **Drag** items to rearrange their display order.

**Setting up Attribute Labels:**

1. **Navigate to** Setup → Attribute Labels.

<Image align="center" className="border" border="true" src="https://files.readme.io/735ad0b-image.png" />

2. **Adjust** and add attribute labels as required.
3. \*\*Click \*\*the Save icon after configuration.

**Notes:**\
Attributes must be defined here for Recurly Revenue Recognition Advanced to gather data.

## Segments

Segments help define a company's accounting structure, typically based on reporting needs or business processes.

**Defining Segments:**

1. **Navigate** to setup.
2. **Select** “Segment”.
3. \*\*Click \*\*“+” to add new segments and mark the natural segment containing the account.

<Image align="center" className="border" border="true" src="https://files.readme.io/3c26ee3-image.png" />

### Segment mapper

This tool allows users to input values for defined segments, either linking them to contract attributes or assigning a static value. For instance, segments like Company and Revenue Code might use contract attribute values, while others like cost center have a fixed code. The segment account pulls the “account number” from its respective contracts.

## Business events

In Recurly Revenue Recognition Advanced, business events are either custom or standard triggers that initiate various actions for revenue and cost. After setting up an event, users can upload an event file, and RevRec Advanced will process the uploaded events.

### Standard events / default events

Standard events are built-in business triggers in Recurly Revenue Recognition Advanced that aid in releasing POB. Examples include:

1. \*\*Upon Billing: \*\*Events occur upon billing for sales orders.
2. \*\*Upon Booking: \*\*Events occur upon sales order loading.
3. **Expiration:** An event triggers upon expiration.

### Custom Event

Users can create custom events in Recurly Revenue Recognition Advanced, such as:

1. **Revenue:** Associated with a POB template to release revenue.
2. **Holds:** Linked to holds or approvals to release revenue or transfer revenue placed on a Contract, POB, or line Hold.

**Configuring Events:**

1. **Navigate** to Set up → Events

<Image align="center" className="border" border="true" src="https://files.readme.io/9648676-image.png" />

2. \*\*Fill in \*\*the necessary fields and select options as needed.
3. After setting up the event, **click the Save icon**.

**Associating an Event with POB:**

Before uploading an event file to Recurly Revenue Recognition Advanced, it's essential to link the business event with a POB.

1. **Navigate** to the desired POB. Within the revenue release tab, click on the "+" icon. From the dropdown, choose the event and specify the percentage of revenue release based on the chosen event (set to 100 if it's the only one).

<Image align="center" border="true" caption="POB Association" src="https://files.readme.io/a76fa5f-image.png" />

2. Multiple events can be linked in Recurly Revenue Recognition Advanced. Additionally, you have the flexibility to edit or delete revenue release events.

3. Once done, **click on the Save icon**.

**Event File Template**\
Your event file template should resemble the table below:

| Attribute 1 (from event mapper) | Attribute 2 (from event mapper) | Event Action | Start Date | End Date | Release Date | Effective Date | Expiry Date |
| :------------------------------ | :------------------------------ | :----------- | :--------- | :------- | :----------- | :------------- | :---------- |
|                                 |                                 |              |            |          |              |                |             |

**Template Components**

* **Event Code**: Every uploaded event file must include an event code. Recurly revenue recognition supports various event codes, as outlined in the table below:

  | Event Type                  | Event Action |
  | :-------------------------- | :----------- |
  | EventActionRemoveHold       | 1            |
  | EventActionRecognize        | 2            |
  | EventActionDefer            | 3            |
  | EventActionExpiryDate       | 4            |
  | EventActionDeferFuture      | 5            |
  | EventActionAccelerate       | 6            |
  | EventActionDeferReRecognize | 7            |

* **Start & End Date**: These dates, while optional, determine the revenue recognition period. They will override any dates specified in the contract.

* **Release Date**: This date allows you to input data for the current period as if the event is scheduled for a future date. For instance, you can input an event file on May-23 for July-23, aiding in waterfall catchup.

* **Effective Date**: Governs future events. For example, if events dated Jul-23 are loaded in May-23, the system won't process them until Jul-23 is active. Thus, the effective date manages future events.

* **Expiry Date**: Applicable for events with a set expiration. It can be utilized to update an event's expiration date.

## Currencies

Recurly Revenue Recognition Advanced predefines all currencies as ISO Codes, each with its corresponding precision, listed on the Currencies page.

**Editing Currencies Configuration:**

1. **Navigate** to Setup → Currencies\
   ![](https://files.readme.io/4ae93a3-image.png)
2. All currencies are predefined in Recurly Revenue Recognition Advanced. To edit:
   * **Double-click** on the desired currency or precision field.
   * **Make** the necessary changes.
   * **Click** the Save icon.