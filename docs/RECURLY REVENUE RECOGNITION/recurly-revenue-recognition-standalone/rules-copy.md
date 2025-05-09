---
title: Rules - Revenue Recognition Standalone
excerpt: >-
  Efficiently manage your revenue recognition process with Recurly's Revenue
  Recognition Standalone features and rules management, ensuring accuracy of
  your rules.
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

This feature is part of our product, Recurly Revenue Recognition Standalone. [<a href="https://docs.recurly.com/docs/recurly-revenue-recognition-standalone" target="_blank">Learn more here</a>].

### Required plan

The Standalone Revenue Recognition module is available to merchants who need a revenue tool to automate their ASC 606 / IFRS 15 accounting but do not, at this time, need the Recurly billing platform. 

### Cost

Please reach out to [support@recurly.com](mailto:support@recurly.com) for more pricing details.

### Prerequisites

* Familiarity with Recurly's Revenue Recognition basic functionalities.
* Access to Recurly Revenue Recognition Standalone module.
* Necessary permissions to configure rules and holds.

### Limitations

* Once a Contract Grouping Rule is created, it cannot be deleted but can be inactivated.
* Approved SSP data cannot be deleted.
* Holds, once applied, can only be released based on the set criteria or manually by authorized personnel.

# Key benefits

* Streamlined revenue recognition process with clear rules and functionalities.
* Flexibility to define contract groupings, performance obligations, and variable considerations.
* Automated calculations for costs and variable considerations, reducing manual errors.
* Enhanced control over revenue recognition with the Holds feature.
* Comprehensive insights with the SSP Analyzer tool.

# Rules functionalities

<Image align="center" className="border" width="25% " border={true} src="https://files.readme.io/d33a162-image.png" />

## Contract grouping

This essential feature allows you to define specific criteria for grouping transactions into contracts, ensuring accurate and efficient revenue recognition.

### How to configure contract grouping

1. **Navigate** to the Rules section and select "Contract Grouping."

2. **Click** on the “+” icon in the right menu to create a new grouping rule.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/73e91e0-image.png" />

3. **Provide** a name for the contract grouping and specify the active date.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/7609ae3-image.png" />

4. Under the 'Grouping' section, **click** on the gray "+" button to add grouping criteria.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/37d95e4-image.png" />

5. **Select** the required grouping attribute(s) to define how contracts should be grouped.
6. **Specify** the rolling date and the number of days for the grouping rule.

<Image align="center" className="border" border={true} src="https://files.readme.io/0aa6811-image.png" />

7. **Save** your configuration.

### How to inactivate Contract Grouping Rule

**Note:** Once a Contract Grouping Rule is created/configured, it cannot be deleted. However, you can choose to inactivate a grouping rule if needed.

To inactivate a grouping rule, follow these steps:

1. **Go** to the Contract Grouping section and select the grouping rule tab that you want to inactivate.

2. The current status of the grouping rule will be "active." **Change** the status to "inactive."

<Image align="center" className="border" border={true} src="https://files.readme.io/8c5328f-image.png" />

3. **Click** on the Save icon to save the changes.

**Points to Remember:**\
➔	Only the active grouping rules will be visible in the Contract Grouping section.\
➔	Once a grouping rule is made inactive, it will be moved to the inactive tab for reference.

## Performance obligation

In Recurly Revenue Recognition Standalone, the second step of ASC 606 / IFRS 15 compliance involves identifying and defining performance obligations. This process includes setting up recognition methods for each obligation and establishing rules for the items or transactions associated with them, ensuring accurate and consistent revenue recognition.

### Adding POBs

1. Navigate to Rules → POB.

   <Image align="center" className="border" border={true} src="https://files.readme.io/9e57f37-image.png" />

2. Click on the "+" button to add a new performance obligation.

   <Image align="center" className="border" border={true} src="https://files.readme.io/4fd4296-image.png" />

3. Enter a unique name for the performance obligation.\
   ![](https://files.readme.io/b21625b-image.png)

4. Provide the active date for the new POB.\
   ![](https://files.readme.io/f281b16-image.png)

5. Select the appropriate waterfall type (WF Type) from the dropdown:\
   ![](https://files.readme.io/9c4764d-image.png)
   1. **PointInTime:** Performance obligations recognized at a point in time.
   2. **OverTime:** Performance obligations recognized over the contract period.
   3. **OverTime Slide:** Performance obligations recognized over the contract period, with a delayed release date extending revenue recognition.
   4. **OverTime Condense:** Performance obligations recognized based on the release date, with revenue recognition adjusted based on event timing.
   5. **Manual:** Revenue realized based on manual input.

6. Choose the accounting method for the new POB from the dropdown options:\
   ![](https://files.readme.io/2b6ede8-image.png)
   1. **Daily:** Revenue recognized daily, based on the number of days in the contract.
   2. **FixedMonthly:** Revenue calculated in fixed amounts based on the number of months in the contract, with adjustments for start date.
   3. **PartialMonthly:** Revenue calculated partially for the first and last months of the contract, with equal recognition for the remaining months.
   4. **Annually:** Revenue calculated annually.

7. Select the ratable method from the dropdown options:\
   ![](https://files.readme.io/0bd9e92-image.png)
   1. **Sales Order Ratable:** Revenue amortized on a prorated basis, with catch-up in the current open period.
   2. **Sales Order Dates:** Revenue scheduled based on the start and end dates of the sales order lines.
   3. **Billing Dates:** Revenue scheduled based on the start and end dates of billing/invoice.

After completing step 1 – 6, save your changes and then your POB could look like this.

![](https://files.readme.io/2a3d5ab-image.png)

1. In the POB configuration screen, locate the Revenue Release section.

2. Click on the "+" button in the Revenue Release section to add a new release event.
   1. Follow these sub-steps to configure the release event:
      1. Select the desired event from the dropdown menu.
      2. Enter the percentage of revenue release applicable for this event.

![](https://files.readme.io/aad214f-image.png)

Please note that these steps allow you to add multiple release events to a single POB, enabling accurate revenue recognition based on different events and their corresponding revenue release percentages.

10. Save all changes.

### Adding POB rules

To access POB Rules, there are three methods available:

**Method 1**

1. **Go** to the Rules section in the navigation menu.

2. **Click** on "Rules" under the Performance Obligation menu.

**Method 2**

1. **Open** the desired POB.

2. **Navigate** to the "Rules" tab located at the top.

**Method 3**

1. **Open** the desired POB.

2. **Scroll down** to the bottom of the page.

3. **Enter** the required information in the Rules section. Note that this method provides limited functionality compared to the other methods.

Once in the Rules section, follow these steps to add POB Rules:

1. Click on the "+" icon under the Rules section.\
   ![](https://files.readme.io/165cf0c-image.png)

2. Select the specific POB to which the rule should be assigned.\
   ![](https://files.readme.io/e247385-image.png)

3. Define the attribute value used for recognizing the POB. For example, select the "Item" attribute. If the desired value is not available, click on the window-shaped button and select the attribute from the window that appears, then click on "Save." In this case, we have chosen "Account Code" as the attribute for POB recognition.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/8698dfd-image.png" />

![](https://files.readme.io/79bb6b3-image.png)

4. Once the attribute is determined, enter the corresponding value that describes the POB and adjust the active date as necessary.

![](https://files.readme.io/31a59de-image.png)

5. Click on the "Save" icon to save the rule.

![](https://files.readme.io/7388d8a-image.png)

**Notes:**

* Avoid editing the default POBs, such as "Material right" and "manual journal."
* Multiple release events can be associated with a single POB, but the total release percentage must equal 100%.
* POBs require an assigned rule to function properly.
* You can change the hierarchy of POB rules by dragging and rearranging them using the drag icon.
* Remember to save any changes made to the rules or hierarchy.
* To delete a POB Rule, select the rule and click on the "Delete" icon. Click on the "Save" icon to confirm the deletion.

![](https://files.readme.io/d7091a2-image.png)

## Standalone selling price

Setting up the Stand-Alone Selling Price (SSP) involves a streamlined process consisting of three key steps. Firstly, you will create the SSP by defining values, specifying pricing attributes, and configuring adjustments or discounts. Secondly, you will set the SSP Analyzer rules, establishing criteria for identifying and analyzing SSP variances, and customizing them to align with your business requirements. Lastly, you will prepare and upload the necessary data into the SSP Analyzer tool, ensuring accurate processing and analysis. By following these steps diligently, you can establish a robust SSP framework tailored to your products or services, enabling precise determination of stand-alone selling prices.

### Creating the SSP

1. **Navigate** to the Rules section and click on **SSP Definition**.

<Image align="center" className="border" border={true} src="https://files.readme.io/7bdf656-image.png" />

2. **Click** on the "+" icon to create a new SSP.

<Image align="center" className="border" border={true} src="https://files.readme.io/50c8572-image.png" />

3. **Enter** a name for the SSP.
4. **Leave** the Range tab blank when uploading SSP data.
5. **Select** the **Type** of SSP as SSP or RSSP.

**Note:** Select SSP, if you want to define standalone selling price and select RSSP when you want to define Residual standalone selling price.

6. Under the Books tab, choose the relevant Book for the SSP.\
   ![](https://files.readme.io/ad342cf-image.png)
7. Select the appropriate SSP value from the drop-down menu.\
   ![](https://files.readme.io/0695b7d-image.png)
8. Specify the SSP statistics as Simple Median, Simple Average, Weighted Median, or Weighted Average.\
   ![](https://files.readme.io/886d8aa-image.png)
9. Determine the SSP base as Low, Median, High, or Follow SellPrice.\
   ![](https://files.readme.io/b2875c5-image.png)
10. Under the Grouping tab, select the attribute that will define the SSP. For example, if you choose "item" as the attribute, the SSP will be based on items.\
    ![](https://files.readme.io/e3e1791-image.png)
11. Save the SSP configuration. The newly created SSP card will appear on the left side under active SSPs.\
    ![](https://files.readme.io/bc6db73-image.png)
12. To delete any SSP configured in Recurly Revenue Recognition Standalone, click on the delete icon located on the black menu bar.\
    ![](https://files.readme.io/26004bd-image.png)

### Configuring the SSP Analyzer

1. Navigate to the Rules section and click on SSP Analyzer, or click on SSP Analyzer at the top of the SSP page. In case of multiple SSP definitions, go to the required SSP card and click on SSP Analyzer.

<Image align="center" className="border" border={true} src="https://files.readme.io/d108a7b-image.png" />

2. On the SSP Analyzer page, click on the “+” icon to create a new SSP Analyzer.

![](https://files.readme.io/dc0b6d1-image.png)

3. Provide a unique name for the SSP Analyzer.
4. Select the appropriate Analyzer Type: Rules or Analysis. Choose "Rules" if you are uploading SSP data.
5. Define the active dates, including the start and end date (if applicable), for the SSP data.
6. Once you have configured the SSP Analyzer, click the Save icon to save your changes.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/c58f0b0-image.png" />

7. The Flow Status will be displayed as "New" once the configuration is saved.

![](https://files.readme.io/d6a62ce-image.png)

### Preparing and uploading SSP data

1. Ensure that the information in the table corresponds to the selections made for the SSP configuration, maintaining consistency with the chosen value type (e.g., amount or percentage).\
   ![](https://files.readme.io/1ada774-image.png)

2. To upload the SSP data, click on the Upload icon.

3. In the SSP upload window, select the SSP file that needs to be uploaded and click Open.

4. After the SSP file is uploaded, click on the Save icon.

5. The uploaded SSP data will be displayed under the Rules section in SSP Analyzer.

6. To approve the uploaded SSP data, click on the Approve icon. Note that approved data cannot be deleted.

7. The flow status will change to Approved once the SSP data is approved.

8. The SSP data will appear on the SSP Analyzer screen as shown below:\
   ![](https://files.readme.io/c3025e9-image.png)

9. After the SSP data is approved, it can be downloaded by clicking on the Download icon.

**Notes:**

* If the SSP data needs to be deleted, it can only be done before approving it. Click on the Delete icon to remove the data. Once approved, the data cannot be deleted.
* If the approved SSP data will not be used, specify an end date so that the data will not be utilized beyond that date.
* Recurly Revenue Recognition Standalone allows you to provide validity for the uploaded SSP data by specifying the start and end dates for the approved data.

## Variable considerations

In Recurly Revenue Recognition Standalone, the setup for automatically applying variable consideration (VC) estimates to transaction lines is done on the Variable Considerations page. Variable considerations refer to charges associated with discounts, rebates, and refunds that are determined by factors unrelated to the cost of producing goods or services. These amounts can be estimated using historical data and various calculations.

### How to configure Variable Considerations

1. **Go** to Rules → Variable Considerations.

2. **Click** on the "+" button to create a new VC template.

3. **Name** the VC template.

4. **Specify** the VC type, which is used to group VC of similar types (e.g., favorable VC).

5. **Ensure** that the VC-related accounts in your ERP system are accurately reflected:

   1. **Accrual Account:** A liability account used for VC accrual.
   2. **Contra Account:** A revenue account for VC revenue.
   3. **Clearing Account:** A clearing account associated with VC.

      <Image align="center" className="border" border={true} src="https://files.readme.io/05b4de3-image.png" />

6. **Define** the timing for VC accrual.

7. **Enter** the active dates for the VC.

8. To inactivate a VC, **toggle** its status to "Inactive."

9. To activate a VC needed, **toggle** its status to "Active."

10. **Click** the "+" button in the rules section to assign VC rates or amounts to be applied on items.

11. For each VC rule, you can provide active dates for the VC items.

12. To remove VC rules or items, simply delete them.

**Below is an example of a VC template:**

<Image align="center" className="border" border={true} src="https://files.readme.io/bd5875c-image.png" />

### Uploading files to VC

When working with Variable Considerations (VC) in Recurly Revenue Recognition Standalone, there are two options for importing data:

1. **Integrating Invoices from Recurly:** If VC is applicable, you can integrate invoices from the Recurly platform into Recurly Revenue Recognition Standalone
2. **Loading a Sales Order File:** Alternatively, you can load a sales order file into the system for which VC is applicable.

Once the data is collected and available in the system, Recurly Revenue Recognition Standalone automatically calculates VC based on the configured rules. The calculated VC amounts will be visible in the system, as shown in the provided screenshot.

With Recurly Revenue Recognition Standalone, VC estimates are automatically applied to transactions based on the VC rules defined during the setup process, streamlining the calculation and application of VC amounts.

<Image align="center" className="border" border={true} src="https://files.readme.io/8f2de29-image.png" />

In the revenue workbench of Recurly Revenue Recognition Standalone, you have the flexibility to manually modify the application of variable consideration. To do this, simply right-click on the specific item you wish to change while in the VC tab. The options available for adjustment can be seen in the provided image.

Any changes made to the variable consideration will be accurately reflected in the Revenue Workbench. If there are any adjustments or updates needed for the variable consideration, they can be performed through VC true-up or by initiating clearance to release the updated information.

<Image align="center" className="border" border={true} src="https://files.readme.io/d52f106-image.png" />

**Notes:**

* The transaction price displayed in the Revenue Workbench reflects the price after the adjustments for variable consideration.
* The revenue to date shown in the Revenue Workbench is the cumulative sum of revenue, allocations, and favorable variable considerations scheduled for the respective period.
* The Revenue Workbench provides visibility into the waterfall analysis for variable consideration, showcasing the breakdown and impact of variable consideration on revenue recognition.
* The VC Accrual represents either the amount calculated by the system or the liability that will be cleared once the actuals are incorporated into the process.

## Cost

Recurly Revenue Recognition Standalone includes functionality to account for costs. There are two options for managing costs within the system: manual loading of costs or automated calculation based on predefined formulas. The Rules page, specifically the Cost section, is used to define the Cost Type and Cost Rules.

### How to configure a cost type

1. Navigate to Rules and select Cost from the menu.

<Image align="center" className="border" width="25% " border={true} src="https://files.readme.io/f03f8f4-image.png" />

2. Enter the 'Cost Type' to specify the type of cost you are defining.
3. Determine the cost treatment based on the following options:
   1. **Point in time:** Recognize the cost in the month it is incurred.
   2. **Follow Revenue:** Recognize the cost according to the revenue recognition pattern over the contract period.
4. Set the cost keys by clicking on the field and selecting the appropriate options from the pop-up menu. Note that selecting cost keys is optional.
5. If you need the Recurly Revenue Recognition Standalone tool to calculate the cost amount, use the "Formula on" feature. Type "Line.SellPrice" (case sensitive) to apply cost rules based on a percentage of the sell price.
6. Specify a unique account number for the debit account ('Dr account number') and the credit account ('Cr account number'). These account numbers will be compared with the Sales Order number.
7. If your incremental cost needs to be amortized and capitalized, activate the "Cost Capitalize" option.\
   ![](https://files.readme.io/b6ce8f1-image.png)
8. Finally, click on the Save icon to save your cost configuration.

To add rules to the cost configuration in order to apply the cost formula to specific contract lines, such as the item "Macbook," follow these steps:

1. Under the cost rules section, click on the "+" button to add a new cost rule.
2. Select the book for which the cost should be applied. This ensures that the cost rule is associated with the correct book.
3. In the "Item" column, enter the name "Macbook" to specify that this cost rule should be applied to contract lines related to the item "Macbook."
4. In the "Value" column, enter the percentage of the sell price that should be treated as cost for the specified item.
5. Click on the save button to save the cost rule.\
   ![](https://files.readme.io/c0e7dae-image.png)

**Note:** If your cost calculation is based on any other attribute other than “item”, go to the mapper and select the required fields.

### Calculation of cost using a cost file

1. Prepare a Cost file that includes the necessary columns reflecting the cost attributes defined in the system. Ensure that the cost type specified in the file matches the cost type already defined in the system.

2. Navigate to the Transactions page in Recurly Revenue Recognition Standalone.

3. Click on the "Upload" icon to upload the Cost file.

4. Choose the Cost file from your local system by clicking on "Browse" or "Choose File" and select the appropriate file.\
   ![](https://files.readme.io/43d3a70-image.png)

5. Once the file is selected, click on "Open" to initiate the upload process.

6. The system will process the uploaded Cost file and calculate the cost based on the configuration specified in the Cost Rules. It will apply the calculated cost to the respective contract lines, even if the cost is not explicitly assigned to the item or POB in the contract.

By utilizing the Cost file upload functionality, you can streamline the process of calculating costs based on predefined rules and attributes, enabling accurate cost allocation in your revenue recognition calculations.

## Holds

In Recurly Revenue Recognition Standalone, the Holds feature allows for holding revenue recognition based on specific conditions set by management. 

There are two types of holds available: Contract Level hold and Element Level hold.

**Contract Level Hold:**

* A Contract Level hold applies to the entire contract.
* It prevents revenue recognition for the contract until the hold condition is met.
* The hold condition could be a specific event, date, or any other criteria defined by the management.
* Once the hold condition is satisfied, revenue recognition for the contract can proceed.

**Element Level Hold:**

* An Element Level hold applies to individual revenue elements within a contract.
* It allows for holding revenue recognition for specific elements until the hold condition is met.
* Each revenue element can have its own hold condition.
* The hold condition could be based on the fulfillment of certain criteria or the occurrence of specific events.
* Once the hold condition for an element is satisfied, revenue recognition for that particular element can proceed.

The **Holds** feature in Recurly Revenue Recognition Standalone provides flexibility in managing revenue recognition by allowing for temporary holds based on defined conditions. It ensures that revenue recognition aligns with the requirements and policies set by management, providing accurate and compliant financial reporting.

### How to apply holds

1. Navigation: Go to Rules → Holds

<Image align="center" className="border" width="25% " border={true} src="https://files.readme.io/f03f8f4-image.png" />

2. **Name:** Enter a name for the hold, such as "Delivery Hold."
3. **Apply on:** Select whether the hold should be applied at the Contract level or Element level.
4. **Release on:** Select an event based on which the hold can be released. Note that this option is inactive for a contract level hold.
5. **Books:** Select the books to which the hold configuration should apply. You can select all or specific books.
6. **Expiry Date:** Choose the date on which the hold will expire and will no longer be applied.
7. **Days:** Enter the number of days after which the hold will no longer apply.
8. **Active Dates:** Specify the date or period during which you want the hold to be active.
9. **Release Hold:** Choose one of the following options:
   1. **Active:** When the release hold is active, revenue cannot be scheduled and revenue will not be transferred to the general ledger even if you try to release revenue manually.
   2. **Inactive:** When the release hold is inactive, you can schedule revenue and revenue will be transferred to the general ledger when you try to release revenue manually.\
      ![](https://files.readme.io/d644991-image.png)
10. **Criteria:** This section allows you to define criteria for applying the hold to a contract or element. It includes the following columns:
    1. **Field type:** Specify the field type, such as "All" or a specific field.
    2. **Field:** Choose the field on which the hold criteria will be based.
    3. **Operator:** Select the operator to define the comparison, such as "=", "\<", ">", etc.
    4. **Value:** Enter the value against which the field will be compared, such as "Damaged" (text) or a specific number.

### Applying and releasing holds (functional scenarios)

1. **Create** a hold at the contract level by filling in the mandatory fields and selecting a criteria based on which the hold will apply. For example, set the criteria as "quantity equal to greater than 5."\
   ![](https://files.readme.io/0eafa22-image.png)

2. **Upload** the sales order (SO) file that satisfies the hold criteria.

3. **Open** the contract in the revenue workbench.

4. **Go** to the "Hold" tab in the contract view.\
   ![](https://files.readme.io/d0b9ff7-image.png)

5. **Right-click** on each order line that needs to have the hold released.

6. A dialog box titled "Release Line Hold" will appear.\
   ![](https://files.readme.io/bea81c0-image.png)

7. **Click** on the dialog box to release the hold on the selected order line.

8. The released hold will be reflected in the waterfall view, showing the updated revenue recognition.\
   ![](https://files.readme.io/1be3a75-image.png)

9. It's also possible to configure holds at the element level, providing more flexibility in managing revenue recognition.\
   ![](https://files.readme.io/ab318a9-image.png)

10. If holds are configured at the element level, you can follow the same process to release them manually.

### Applying hold on element level manually

1. **Go** to the "Rules" function and click on "Hold."

2. **Select** "Element Level" from the drop-down list.

3. **Choose** "Apply on" as "Element Level" for Line Hold.

4. **Click** on the Save icon to save the configuration.

Now, to apply the hold on an element level manually:

1. **Upload** a contract that does not satisfy the element level hold criteria.

2. **Go** to the Revenue Workbench and open the contract.

3. **Navigate** to the "Hold" tab in the Revenue Workbench. At this point, no hold will be applied.

4. Once the hold screen appears, **right-click** on the order line that needs to have the hold applied.

5. A dialogue box titled "Apply Line Hold" will appear.\
   ![](https://files.readme.io/7481598-image.png)

6. **Click** on "Apply Line Hold," and another dialogue box will appear.\
   ![](https://files.readme.io/538007b-image.png)

7. **Choose** a predefined hold from the options and add comments explaining why the hold is being applied. Note that you can apply the hold even if it does not satisfy the criteria set for the hold.

8. **Click** on the appropriate buttons to confirm and save the applied hold.

**Notes:**

* In the "Hold" tab of the Revenue Workbench, you can see the information about when and who applied the line hold.
* Holds can also be applied to partial revenue. For example, if 50% of the revenue for a contract has been released, you can apply a hold on the remaining 50% and release it at a later time. The same process mentioned above can be used to apply holds on partial revenue in the Revenue Workbench manually.

## Additional journals

### How to apply additional journals

<Image align="center" className="border" border={true} src="https://files.readme.io/71b5c0604e8644d9d4252b83a59c3b09a8bb60a642b8ba8a9e41ba6794907506-image.png" />

Recurly's Revenue Recognition Standalone comes with a feature to generate journals for any special purpose requirement based on the billed amount, adjustment waterfall values and/or revenue waterfall values by using the feature Additional Journals.

1. **Go** to Rules → Additional Journals

<Image align="center" className="border" width="30% " border={true} src="https://files.readme.io/e0b70c66e6d6fd6289df33a903195f396cadb173a04374f19eda1e61976c2e27-image.png" />

<br />

### Additional Journals Based on Billing

1. **Name:** Enter a unique name for the additional journal.
2. **Books:** Choose the books in which the journal is to be posted - example; Primary, Secondary or All.
3. **JE Type:** Select the JE type as Document

If the user needs to create an additional Journal based on the billed amount, then choose “document” as value for the JE type. In addition to the billed amount, users may be able to create journals based on any calculated columns in the document/billing record.

4. **Select** the POB Type for which the additional journals are to be applied. This selection would bring in additional journals only if the subscription belongs to the selected POB type.  If, instead, the additional journals are required for Cost/Expenses, then the cost type must also be selected. 
5. In the Amount field **select** the data type for the amount required in the journal entry. This feature is available only when the additional journals JE type selected is Document. As you can see below, the drop down under amount will display all the data type amounts for the document’s attributes.

<Image align="center" className="border" width="50% " border={true} src="https://files.readme.io/69087afb25503ce1e19aece61588b7a7fee9675ab9e7b73c0312b9af56201ad0-image.png" />

6. **Enter** the debit and credit account information for the additional journals.
7. **Enter** the active date. Choose the beginning and ending date that the JE should be active.  You can leave the end date blank if you want the JE to be applied forever.
8. Auto Reverse is an option available to reverse the JE passed in the next period of the contract. It is available only when the JE type is Document.
9. Retirement is available when additional journals are configured for cost type. This will create additional journals at the end of the contract period.

> **Note:** The POB type and cost type are exclusive from each other and cannot be selected at the same time. 

### Additional Journals for revenue waterfall amount

1. **Name:** **Enter** a unique name for the additional journal.
2. **Books: Choose** the books in which the journal is to be posted - example; Primary, Secondary or All.
3. **JE Type: Select** the JE type as Revenue Waterfall:

If the JE type is Revenue waterfall, the JE will be posted in the contract for the amounts in the Revenue waterfall. This can be applied only based on POB type. If the additional journal to be applied for all the contracts, then please leave the POB type blank.

4. **Enter** the debit and credit account information for the additional journals.
5. **Enter** the active date. Choose the beginning and ending date that the JE should be active. You can leave the End date blank if you want to apply for the JE forever. 

<Image align="center" className="border" border={true} src="https://files.readme.io/4dff3811167ce087e8e44d51026e1c52cb01fce83455cb64f1cfad42a9a7bcd7-image.png" />

### Additional Journals for Adjustment waterfall amount

1. **Name:** Enter a unique name for the journal to be applied.
2. **Books:** Choose the books in which the journal is to be posted - example; Primary, Secondary or All.
3. **JE Type:** Select the JE type as Adjustment Waterfall:

If the JE type is Adjustment waterfall, the entries will be posted in the adjustment waterfall. Adjustment waterfall refers to the waterfall that arises due to the carve ins and carve outs at the time of allocation. Hence, this is applicable only when the merchant has allocations.

4. **Enter** the debit and credit account values for the additional configured journals.
5. **Enter** the active date. Choose the beginning and ending date that the JE should be active. You can leave the End date blank if you want to apply the JE forever.

<Image align="center" className="border" border={true} src="https://files.readme.io/4861fbd75f701ac1e98429c9c265f626c7925e23cc88d1c3b4be4e581b0ab25c-image.png" />

> **Note:** Adjustment waterfall additional journals do not get an option to choose POB type and they do not have an option for auto reverse.
