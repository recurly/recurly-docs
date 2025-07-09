---
title: Automatic month end close
excerpt: >-
  A succinct checklist to guide and streamline your period close process in
  Recurly RevRec, from system-defined tasks to custom, site-specific
  requirements.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Required plan

This feature is part of our product, Recurly Revenue Recognition Advanced. \[<a href="https://docs.recurly.com/docs/recurly-revenue-recognition-advanced" target="_blank">Learn more here</a>].

# Definition

**Period Close Checklist** refers to a set of tasks—both system-defined and user-defined—required to finalize each open period in Recurly RevRec. This ensures that data is complete, journals are transferred, and balances are reconciled before closing a period.

# Key details

## Period Close Checklist in Recurly Revenue Recognition

Recurly Revenue Recognition includes a **Period Close Checklist** to ensure accurate and efficient period closures. The checklist begins with **four system-defined tasks** and can be expanded with your own custom tasks.

<Image align="center" className="border" border={true} width="40% " src="https://files.readme.io/e5684605bed5eeb29626cfb74bddd32d2305b6e5a007bde21a9ea74563147aec-4._System_Defined_Tasks.png" />

### System-Defined Tasks

1. **Data processed for the current open period**: Ensures all Recurly invoices, credits, and voids are transferred into RevRec, including data up to the period’s end date. *(This task cannot be skipped.)*

2. **Billing Pending Processing or Stuck in Stage**: Identifies transactions stuck in the **Order** or **Doc Stage** tables for the current open period, which you must investigate and resolve.

3. **Transfer Journals**: Ensures that all batches containing journals are approved and summarized for the current period. Open batches without journals can remain open.

4. **Review the Accounted Reports**: Confirms the accuracy of journal entries and reconciles beginning and ending balances. Verifies that the **Liability Balance plus Asset Balance** matches the **Revenue Workflow** for the current open month.

### Creating User-Defined Tasks

You can create any number of user-defined tasks essential for period close:

1. Go to **Setup → Period Task**.

<Image align="center" className="border" border={true} width="30% " src="https://files.readme.io/d71ad5d26e258a599e71f5f7a2600a822edb5750c1e16c93c8f67036971c39b2-1._Period_Task.png" />

2. Click the **"+"** button.
3. Enter a **Task Name**.
4. Choose **Required** or **Optional**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/fcb1c2c356433e70d4af97013f4f31d943576d776ad01c5310f29725a44c8699-2._New_Task.png" />

5. Define the **Activation Period** (tasks activate in the subsequent period).
6. **Save** your changes.

If needed, reorder tasks by clicking the "**⋮**" icon on the bottom right.

<Image align="center" className="border" border={true} width="70% " src="https://files.readme.io/645c32df97dbf8e54bb01e00817febf42e64b46a152a7492df8b52b94bb3fdb0-3._Hierarchy_change.png" />

<br />

***

# How to close the period

1. **Navigate to** **Import/Export → Period Close**.
2. **Click “Initiate Period Close.”**
   * Perform this step only after the open period has concluded.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/ab01604cf77a9c63e0213c6478101aa15ed2a6829c18f39c628164369e3eb7fd-Screenshot_2025-06-27_at_9.08.42_AM.png" />

3. **Confirm period close**
   * A dialogue box will appear.
   * Enter any necessary message/comment.
   * Click **“Close Period”** to confirm and begin the automated close process.

<Image align="center" className="border" border={true} width="70% " src="https://files.readme.io/44a525a8455f53f840096291d8901fe552f8e3711a3cb1c71a3583e84545761b-6.Comments.png" />

<br />

4. **System Checks**

* The system runs a **“period close automated”** job to verify:
* All invoices from Recurly are transferred into RevRec.
* Data in contract stage, doc stage, and cost stage are fully processed.
* Transfer JEs are summarized.
* Accounted reports are reconciled with Revenue Recognition standards.
* Refer to the “Period Task” section for details on each automated check.

5. **Complete User-Defined Tasks**

* Review each user-defined task.
* Mark each task as **“Complete”** when finalized.
* Add comments or file attachments as an **audit trail** and for future reference.

6. **Optional tasks** may be set to **Skipped** if you do not need to complete them.

<Image align="center" className="border" border={true} width="70% " src="https://files.readme.io/5802364502736289fb780bb5f62e681e53e78a040c3d823d3d61080782258d8a-7._Perid_Close_-_Step_4.png" />

7. **Automatic Close & Next Period Open**
   * Once **all required tasks** are complete, the system automatically closes the **current period** and opens the **next one**.
   * The final screen will display the period as closed and all tasks as completed.

<Image align="center" className="border" border={true} src="https://files.readme.io/d27624399376acf0cd8a8026d2f19a8d7a1c080bc953a79e5f16294dbeaee9c5-8._Point_6.png" />

## **Important note on data synchronization**

* The system requires **30–60 minutes** for data to synchronize.
* After making any corrections, please wait up to an hour before clicking “Retry” or contacting Support.

With all tasks finalized, you’ll successfully close the period in Recurly RevRec, ensuring an accurate and compliant end-of-period process.

# FAQs

***

## General period close errors

### What does the error in the system task "Data processed for the current open period" mean?

**Problem:** Recurly invoices for the current open period have not been successfully transferred into RevRec.\
**Solution:** Initiate the billing integration job to synchronize the missing invoices. After the integration completes successfully, click Retry. The system will not allow the period close to proceed until all invoices are synced.

### What does the error in the system task “Billing pending processing or Stuck in Stage” mean?

**Problem:** Billing data or other uploaded transaction data for the current or a previous open period is stuck in the staging area and has not been processed.

**Solution:**

* Generate Stage Reports by navigating to Reports → Stage to find the specific transactions that are stuck.
* Review and process the stuck data to resolve any underlying errors.
* Once the data flows correctly into RevRec, click Retry on the period close task to continue.

**Please note:** Refer to the [stage data error FAQs](https://docs.recurly.com/docs/period-close-checklist#contract-stage-errors) below for understanding how to resolve the stage data errors.

### What does the error in the system task “Transfer Journals” mean?

**Problem:** Transfer Journal Cards for the primary book have not been approved or summarized.

**Solution:**

* Go to Import/Export → Transfer JE to locate the journals that are still open.
* Approve and summarize all open journals.
* Click Retry. This step ensures all journal entries are properly accounted for before closing the period.

### What does the error in the system task “Review the Accounted Reports” mean?

**Problem:** There are summarization issues or balance discrepancies in key financial reports.

**Solution:**

* Review the roll-forward reports (like Liability and Asset Balances) and verify that all unaccounted columns show zero.
* Confirm that the beginning balances for the current period match the ending balances from the previous period.
* Check that the revenue waterfall aligns with the scheduled balances.
* If you cannot identify the specific report causing the issue, please contact Recurly Support for assistance.

### Is it possible to reopen a closed period?

**Answer:** No, a period that has been closed cannot be reopened.

**Workaround:** Any transactions that belong to a closed period can be loaded into the current open period.

### Will the new period close process allow closing the period if invoices haven't been integrated?

**Answer:** No, the new period close process has a built-in check that prevents the period from being closed until all relevant invoices have been integrated.

### The data in the stage area is not needed, but the system is preventing the period close. What can be done?

**Problem:** The system will not allow the period to be closed while there is still data in the staging area, even if that data is unnecessary.

**Solution:** If the data in the staging area is not required, you must manually delete it (see directions [here](https://docs.recurly.com/docs/imports-exports#how-to-view-and-delete-data-in-the-stage-area)). The period close process will only continue once the stage is empty.

### What does the system check during the validation step?

**Answer:** The system task checks for the following alignments in the reports:

* The unaccounted column must be zero in the liability balance and asset balance reports.
* The beginning balance of the current period must match the ending balance of the previous period in the liability and asset balance reports.
* The total of the revenue waterfall report should match the scheduled balances.

### Can I skip a user-created task?

**Answer:** A user-created task can only be skipped if it was marked as optional during its creation. Mandatory tasks cannot be skipped.

### Can I add a new user task for the current period?

**Answer:** No. A user task added during the current period will only become visible and active in the period close process starting from the next period. You cannot add a new task for a period that is already in progress.

### Can I delete a user task in the current period?

**Answer:** Yes, you can delete a user task. However, the deletion will only take effect from the following period. The task will remain part of the period close checklist for the current period.

### Can I close a future period?

**Answer:** No. The new period close process will only allow you to close periods previous to the current calendar month. You cannot close the current month or any future months in advance.

### Why if I made my corrections, can I not close the period?

**Answer:** The system requires **30–60 minutes** for data to synchronize.

***

## Contract stage errors

These errors occur during the initial contract processing stage.

### What does the "Debit Account is Blank" or "Credit Account is Blank" error mean?

**Reason:** This error indicates that a transaction line is missing its assigned debit or credit account.

**Solution:** Please review the system configurations and assign the correct debit and credit accounts to the relevant lines to resolve the issue.

### Why am I seeing the error "Updated SO Amount is in a different sign than previous Billed Amount"?

**Reason:** This happens when an update to a Sales Order (SO) has an amount with a different sign (positive/negative) than the original SO. For example, a positive SO amount cannot be updated with a negative amount.

**Solution:** Ensure that the updated SO amount maintains the same sign as the original.

### What causes the "Error Processing So update"?

**Reason:** This error can occur in the case of a Credit Memo Request (CMR) when the updated Sales Order (SO) amount is less than the amount that has already been billed.

**Solution:** Verify the SO update amount and ensure it is not less than the billed amount.

### What does "Updated SO Amount is less than Billed Amount" mean?

**Reason:** This error indicates that the total billed amount for a line has exceeded the total amount specified in the Sales Order (SO).

**Solution:** To proceed, you must either increase the SO amount to match or exceed the billed amount.

### Why am I getting the "Bundle child updates are not allowed" error?

**Reason:** The revenue recognition module does not permit direct updates to the child lines of a bundle.

**Solution:** Updates should be made to the parent bundle line, not the individual child components.

### How do I fix "Pob Rule setup is missing in the book" or "Pob setup missing for some lines in this contract in book"?

**Reason:** These errors mean that one or more lines in the contract do not have a Price Obligation (POB) rule configured. The system requires POB rules to correctly recognize revenue.

**Solution:** Navigate to the POB rules section for the contract and configure the appropriate POB rules for all lines that are missing them.

**Please note:** If one line in the contract has no POB assigned, all the other lines will also be stuck in the stage area.

***

## Doc stage errors

These errors typically occur when processing documents like invoices and credit memos.

### What should I do about an "Invalid References on INV" error?

**Reason:** The reference invoice number or reference invoice line number provided is incorrect.

**Solution:** Please check and correct the reference invoice details.

### Why did I get the error "Invalid INV. INV belongs to Material Right Contract"?

**Reason:** The system does not allow an invoice to be associated with a material right contract line. Invoices linked to material rights cannot be collected.

**Solution:** Remove the invoice information from the material right line.

### How do I resolve a "Bill Amount is incorrect" error?

**Reason:** The amount on the bill is not correct.

**Solution:** Please check and validate that the bill amount is accurate.

### What does "Original Credit Memo does not exist or already Cancelled" mean?

**Reason:** This error occurs when you try to cancel a credit memo, but the reference details provided do not correspond to an existing, active credit memo in the system.

**Solution:** Re-upload the cancellation file with the correct reference invoice details.

### How do I fix "Original Invoice does not exist or already Cancelled" or "Original Invoice does not exist"?

**Reason:** This error appears when a credit memo is uploaded with reference details for an invoice that does not exist or has already been cancelled.

**Solution:** Correct the reference invoice details in your upload file and re-process it.

### Why am I seeing "Invalid INV. SO not present in System"?

**Reason:** This error occurs when an invoice is loaded with a reference to a Sales Order (SO) that is not in the system.

**Solution:** Please re-process the file with a valid and existing SO number.

### What should I do for an "Error Loading SO Line"?

**Reason:** The associated Sales Order (SO) line has not been successfully processed from the contract stage into the system.

**Solution:** Check the contract stage for the relevant SO and ensure it is processed successfully before you proceed with the invoice.

### How do I resolve "CM cannot be processed as INV is in error"?

**Reason:** You are trying to process a Credit Memo (CM) against an invoice that is currently in an error state in the stage area.

**Solution:** First, review and resolve the error associated with the original invoice. Once the invoice is processed successfully, you can process the credit memo.

### What causes the "Cumulative bill amount is over sell price" error?

**Reason:** This error occurs when the total value of invoices for a subscription exceeds the sell price, and the system is not configured to allow over-billing.

**Solution:** To resolve this, navigate to Profiles → Overage and enable the overage setting.

***

## Cost stage errors

These errors occur during the processing of cost-related data.

### What does "Invalid Cost,  SO not present in System" mean?

**Reason:** The Sales Order (SO) number referenced in the cost file is incorrect or does not exist in the system.

**Solution:** Please verify the SO number in your cost file is accurate and re-upload the file.

### Why am I seeing "Bundle child updates are not allowed" in the Cost Stage?

**Reason:** The revenue recognition module does not permit direct updates to the child lines of a bundle, and this rule applies to cost updates as well.

**Solution:** Updates must be made at the parent bundle level.

### How do I fix "Invalid Cost Type, Cost Type Setup is missing"?

**Reason:** The cost type specified is not valid because it has not been configured in the system.

**Solution:** Please revisit your configuration to ensure the cost type setup is correct. Refer to the user manual for more details on this setup.

### What does "Allocated Commission lines cannot be updated" mean?

**Reason:** Once commission has been allocated to a line, the revenue recognition module does not allow that line to be updated.

**Solution:** Avoid attempting to update lines where commission has already been allocated. Any changes may require a new transaction or reversal.