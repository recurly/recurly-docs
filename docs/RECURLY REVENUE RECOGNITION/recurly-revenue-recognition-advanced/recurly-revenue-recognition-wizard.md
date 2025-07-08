---
title: Recurly Revenue Recognition Wizard
deprecated: false
hidden: true
metadata:
  robots: index
---
# Key details

After the Revenue Recognition feature is enabled for your site, you’ll notice several updates to your navigation panel prior to activating the feature.

1. A notification will appear, informing you that Revenue Recognition can now be enabled. This link will remain visible until you complete the enablement process.
2. A new "Revenue Recognition" section has been added to your main navigation menu. Advanced merchants will have access to advanced console options within this section, while standard merchants will be able to view Revenue Settings and General Ledger Accounts.

### **Revenue settings page:**

1. **Navigate** to Revenue Recognition > Revenue Settings.
2. **Adjust** the following required settings:
   1. **Auto Period Close Delay:** Specifies the number of days the system should wait after the end of a period before automatically closing it for standard merchants. The recommended minimum is 2 days, meaning the system will begin closing the completed period at the end of the second day. Merchants can choose to auto-close the period at any time after 2 days, depending on their business process.
   2. **Default Revenue Recognition Rules:** Set default rules for each type of plan, item, add-on, charge, credit, shipping method, and any other variant displayed on the screen for charges created prior to enabling the revenue recognition feature. The default value will be applied only if the system cannot find a rule at the charge line or plan/item level.
   3. **Global Reporting Currency:** Select a global currency for reporting purposes. Please note, this is separate from your site's global currency in Recurly. The global currency setup here is only for the purpose of revenue recognition.
   4. **Credit Transaction Handling:** For merchants using Advanced Revenue Recognition, you can specify how credit transactions—including Goodwill, On Account, and Prepaid Credits—are handled. If you choose the ‘ignore credit transactions’ option, revenue recognition will exclude these credit transactions from processing. To learn more about the various types of credits supported in Revenue Recognition, please refer to the **[Recurly Revenue Recognition Credits Documentation](recurly-revenue-recognition-credits)**.\
      You can modify all these settings any time before activation. After activation, only the **Auto Period Close Delay** will remain editable.

### General ledger accounts

Recurly's Revenue Recognition feature provides flexible configuration for liability and revenue accounts at the charge, plan, or item level. This means you can designate specific liability accounts (such as Deferred Revenue) and revenue accounts for each product, plan, or charge, aligning them with the accounts you use in your General Ledger (GL) system:

1. **Click** on “New Accounting Code”.
2. **Fill in** the accounting code and select the account type as Revenue or Liability. Give the description if required.
3. **Click on** Create. Once all the required accounts are created, the screen looks like this.

# Onboarding Wizard

This onboarding wizard is designed to guide you through the process of self-enabling and activating the Revenue Recognition feature for both the Standard and RA Manage Advanced systems. The wizard will walk you through each step, explaining the purpose of each control and providing guidance on which values to select for your specific use case.

**What to expect in this wizard:**

* Each step provides a clear explanation of the control or setting involved.
* You will receive recommendations and best practices for selecting the appropriate values.
* The flow is structured to ensure compliance with revenue recognition standards and to help you avoid common pitfalls.

### Preparation

To ensure a smooth onboarding experience, please **complete** the following preparations before starting the wizard:

* **Gather your technical memos:** Have your internal documentation and technical memos on hand. These should outline your organization’s revenue recognition policies, processes, and any unique requirements.
* **Chart of accounts:** Understand which General Ledger (GL) accounts will be used for revenue and liabilities. You will need to associate the correct GL accounts to revenue and deferred revenue postings.
* **Performance obligations:** Identify the different revenue recognition performance obligation types that will be associated with each charge, plan, or item. Performance obligations are promises to deliver distinct goods or services to your customers and are central to accurate revenue recognition.
* **Contract review:** Review your customer contracts to ensure you have clearly identified all performance obligations and understand how each should be recognized.
* **Product catalog mapping:** Be prepared to map each product, plan, or item in your catalog to the appropriate revenue recognition rule and performance obligation type.

### Key concepts

* \*\*Revenue recognition: \*\*The process of recognizing revenue as it is earned, in compliance with accounting standards such as ASC 606 and IFRS 15.
* **Performance obligations:** Each distinct good or service (or bundle) you promise to deliver is a performance obligation. Proper identification is critical for compliance and accurate financial reporting.
* **GL accounts:** Revenue and liability accounts must be set up and mapped correctly to ensure transactions are posted accurately for accounting and reporting purposes.

### Next steps

Once you have gathered the necessary information and documentation, proceed with the wizard. Each step will guide you through configuration, offering explanations and context to help you make informed decisions.

**Click** the "Get Started" button to open the onboarding wizard. This will appear as a side dialog, guiding you through the remaining setup tasks. You must complete every item in the task list to activate Revenue Recognition, but you can finish them in any order.

**Please note**, you can safely exit the wizard at any time. Your progress will be saved, allowing you to return and continue later. Anyone on your team with the necessary permissions can view and contribute to the process.

There will be several steps to be completed before we activate the Revenue Recognition. These steps can be completed in any order. The steps to be completed are as under:

* Assigning business entity defaults
* Review settings of All Products
* Configure Default Rules
* Set Global Currency
* Set Auto Period Close Delay
* Configure Credit Handling (Available **only** to Advanced Revenue Recognition merchants)
* Configure Revenue Recognition Start

## Step 1: Assigning GL accounts to business entities

Assigning General Ledger (GL) Accounts to business entities enables users to set default values for GL accounts at the plan, item, and charge levels during product and charge creation.

* **Default value assignment:** When merchants use one or two GL accounts across multiple charges, attaching GL accounts to business entities allows these accounts to be automatically used as default values when defining products and charges.
* **Streamlined setup:** This approach simplifies the configuration process, especially for merchants with straightforward accounting structures, by reducing repetitive data entry and ensuring consistency.
* Automatic application for historical Data: The system will use these default GL account values for inactive plans that still have active subscriptions requiring revenue recognition processing.

#### Guidance

* **For simple account structures:** If your business uses the same GL accounts for most or all charges, assign these accounts at the business entity level to streamline product and charge setup.
* **For complex account structures:** If different products or charges require different GL accounts, you can override the default values at the plan, item, or charge level as needed.

This feature ensures that both new and historical transactions are processed with the correct accounting mappings, supporting accurate revenue recognition and financial reporting.

### Assigning business entity defaults

One of the required tasks is to assign default accounting codes for your business entities.

1. Within the wizard's task list, **locate** the step for business entities.
2. Instead of editing each business entity directly through configuration, you can enter your preferred accounting codes into the fields presented in the card and click on create.
3. **Click** "Apply" to save your changes. The system will validate this step.
4. Once completed, **click** "Next" to move to the following step.

## Step 2: Reviewing settings of all products

To ensure compliance with best accounting practices, you must review each plan  individually to apply the correct revenue recognition rules and accounting codes.

Out of the box, the system provides several Revenue Performance Obligations (POBs) that can be attached at the Setup, Plan, and Add-On levels. Users must select the correct values for each section to ensure the system generates accurate accounting entries.

### `PointInTime` recognition

* **Definition:** Revenue is recognized at a specific point in time, typically the month the billing is issued.
* **Setup:** **Attach** the "PointInTime" POB to the relevant plan or item.
* **Example table:**

| Invoice Created Month | Invoice Amount | Start Date | End Date   | Recognized Period | Recognized Amount |
| --------------------- | -------------- | ---------- | ---------- | ----------------- | ----------------- |
| JAN 2025              | $129.00        | 01/21/2025 | 07/20/2025 | JAN 2025          | $129.00           |
| FEB 2025              | $120.00        | 02/02/2025 |            | FEB 2025          | $120.00           |

### `OverTime` (daily) recognition

* **Definition:** Revenue is recognized evenly over the contract period, calculated daily.
* **Setup:** **Select** "OverTime (Daily)" POB for the plan or item.
* **Amortization example:**

| Period | Number of Days | Amortized Amount |
| ------ | -------------- | ---------------- |
| Jan    | 11             | $7.84            |
| Feb    | 28             | $19.96           |
| Mar    | 31             | $22.09           |
| Apr    | 30             | $21.38           |
| May    | 31             | $22.09           |
| Jun    | 30             | $21.38           |
| July   | 20             | $14.25           |

* **Calculation:**
  * **Number of days:** 181
  * **Per day rate:** $129.00 / 181 = $0.713

### `OverTime` (partial monthly) recognition

* **Definition:** Revenue is recognized over the contract period, with partial recognition in the first and last months, and equal amounts in the remaining months.
* **Setup:** Assign "OverTime (Partial Monthly)" POB as required.
* **Amortization example:**

| Period | Number of Days | Amortized Amount |
| ------ | -------------- | ---------------- |
| Jan    | 11             | $7.84            |
| Feb    | 28             | $21.38           |
| Mar    | 31             | $21.38           |
| Apr    | 30             | $21.38           |
| May    | 31             | $21.38           |
| Jun    | 30             | $21.38           |
| July   | 20             | $14.26           |