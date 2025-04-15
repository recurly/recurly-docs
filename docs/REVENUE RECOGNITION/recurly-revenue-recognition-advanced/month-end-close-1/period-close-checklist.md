---
title: Automatic month end close
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

This feature is part of our product, Recurly Revenue Recognition Advanced. \[<a href="https://docs.recurly.com/docs/recurly-revenue-recognition-advanced" target="_blank">Learn more here</a>].

# Definition

**Period Close Checklist** refers to a set of tasks—both system-defined and user-defined—required to finalize each open period in Recurly RevRec. This ensures that data is complete, journals are transferred, and balances are reconciled before closing a period.

# Key details

## Period Close Checklist in Recurly Revenue Recognition

Recurly Revenue Recognition includes a **Period Close Checklist** to ensure accurate and efficient period closures. The checklist begins with **four system-defined tasks** and can be expanded with your own custom tasks.

<Image align="center" className="border" border={true} width="40% " src="https://files.readme.io/e5684605bed5eeb29626cfb74bddd32d2305b6e5a007bde21a9ea74563147aec-4._System_Defined_Tasks.png" />

### System-Defined Tasks

1. **Data processed for the current open period**: Ensures all Recurly invoices, credits, and voids are transferred into RevRec, including data up to the period’s end date. *(This task cannot be skipped.)*

2. **Billing Pending Processing or Stuck in Stage**: Identifies transactions stuck in the **Order** or **Doc Stage** tables for the current open period, prompting investigation and resolution.

3. **Transfer Journals**: Ensures that all batches containing journals are approved and summarized for the current period. Batches without journals can remain open.

4. **Review the Accounted Reports**: Confirms the accuracy of journal entries and reconciles beginning and ending balances. Verifies that the **Liability Balance plus Asset Balance** matches the **Revenue Workflow** for the current open month.

### Creating Custom Tasks

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

## How to close the period

1. **Navigate to** **Import/Export → Period Close**.
2. You’ll see a list of **Open** tasks—both system-defined and any custom tasks you’ve created.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/9a3be1e42458d56d98f631b6ddecd3523a6c0fda123eaa791a4fdf667107f5a1-5._Period_Close_-_Step_1.png" />

3. **Review** and **update** each task:

* Click **Review Task** to open the task details.
* **Complete** the task when you’re finished, add **comments** or **attachments** for audit purposes.

<Image align="center" className="border" border={true} width="70% " src="https://files.readme.io/3044c605415d1bbda4afbba7b31ecaf13c31a498d0d5c398ad16b8de47c34042-6._Period_Close_-_Step_3.png" />

<br />

* **Optional tasks** may be set to **Skipped** if you do not need to complete them.

<Image align="center" className="border" border={true} width="70% " src="https://files.readme.io/5802364502736289fb780bb5f62e681e53e78a040c3d823d3d61080782258d8a-7._Perid_Close_-_Step_4.png" />

3. **Required tasks** must be marked as **Complete** before you can close the period.
4. Once all mandatory tasks are complete, the **Initiate period close** button becomes active.
5. Click **Initiate period close**, add final comments, then click **Close period**.
   * If any required tasks aren’t in **Complete** status, you’ll see an **internal server error** message.

With all tasks finalized, you’ll successfully close the period in Recurly RevRec, ensuring an accurate and compliant end-of-period process.