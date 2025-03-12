---
title: Period close checklist
excerpt: >-
  A succinct checklist to guide and streamline your period close process in
  Recurly RevRec, from system-defined tasks to custom, site-specific
  requirements.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

**Period Close Checklist** refers to a set of tasks—both system-defined and user-defined—required to finalize each open period in Recurly RevRec. This ensures that data is complete, journals are transferred, and balances are reconciled before closing a period.

# Key details

## Period Close Checklist in Recurly Revenue Recognition

Recurly Revenue Recognition includes a **Period Close Checklist** to ensure accurate and efficient period closures. The checklist begins with **four system-defined tasks** and can be expanded with your own custom tasks.

### System-Defined Tasks

1. **Data processed for the current open period**: Ensures all Recurly invoices, credits, and voids are transferred into RevRec, including data up to the period’s end date. *(This task cannot be skipped.)*

2. **Billing Pending Processing or Stuck in Stage**: Identifies transactions stuck in the **Order** or **Doc Stage** tables for the current open period, prompting investigation and resolution.

3. **Transfer Journals**: Ensures that all batches containing journals are approved and summarized for the current period. Batches without journals can remain open.

4. **Review the Accounted Reports**: Confirms the accuracy of journal entries and reconciles beginning and ending balances. Verifies that the **Liability Balance plus Asset Balance** matches the **Revenue Workflow** for the current open month.

### Creating Custom Tasks

You can create any number of user-defined tasks essential for period close:

1. Go to **Setup → Period Task**.
2. Click the **"+"** button.
3. Enter a **Task Name**.
4. Choose **Required** or **Optional**.
5. Define the **Activation Period** (tasks activate in the subsequent period).
6. **Save** your changes.

If needed, reorder tasks by clicking the "**⋮**" icon on the bottom right.

***

## How to Close the Period

1. **Navigate to** **Import/Export → Period Close**.
2. You’ll see a list of **Open** tasks—both system-defined and any custom tasks you’ve created.
3. **Review** and **update** each task:
   * Click **Review Task** to open the task details.
   * **Complete** the task when you’re finished, add **comments** or **attachments** for audit purposes.
   * **Optional tasks** may be set to **Skipped** if you do not need to complete them.
4. **Required tasks** must be marked as **Complete** before you can close the period.
5. Once all mandatory tasks are complete, the **Initiate period close** button becomes active.
6. Click **Initiate period close**, add final comments, then click **Close period**.
   * If any required tasks aren’t in **Complete** status, you’ll see an **internal server error** message.

With all tasks finalized, you’ll successfully close the period in Recurly RevRec, ensuring an accurate and compliant end-of-period process.