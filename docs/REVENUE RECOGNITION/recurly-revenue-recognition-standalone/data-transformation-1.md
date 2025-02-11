---
title: Data transformation - Revenue Recognition Standalone
excerpt: >-
  Recurly's Revenue Recognition Standalone: Transforming data to enable
  businesses to transform data, manage product bundling, apply customized rules,
  and analyze data effectively.
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

* Familiarity with the organization's revenue recognition standards.
* Understanding of product bundling and data rule configurations.
* Knowledge of the desired attributes for data transformation.

### Limitations

* Dataset, product bundle and data rules cannot be deleted. They can only be inactivated or modified.

### Key benefits

* **Streamlined Data Management:** Efficiently manage product bundles, apply customized data rules, and analyze data for accurate revenue recognition.
* **Comprehensive Analysis:** Create datasets for in-depth data analysis, with daily automatic refreshes ensuring up-to-date information.
* **Customizable Configurations:** Tailor product bundles, data rules, and datasets to specific business requirements.
* **Consistent Reporting:** Datasets ensure uniformity in data analysis and reporting across different functionalities.

# Key details

## Data transformation

The Data Transformation section in Recurly revenue recognition Standalone enables efficient data management through features like product bundling for simplified sales, configurable data rules for customized revenue recognition, and datasets for comprehensive data analysis. It streamlines processes, ensures accuracy, and provides valuable insights for informed decision-making.

<Image align="center" className="border" border={true} src="https://files.readme.io/56719facd7bd21a7af3e2c9e90e183dd096b94761541b670b18c50b1e3b4475d-image.png" />

## Product bundle

Product Bundle allows grouping multiple individual products into a single unit for simplified sales. In Recurly revenue recognition Standalone, you can configure product bundles based on the Parent Identifier. When the sales order (SO) file is uploaded with the parent identifier, Recurly revenue recognition Standalone automatically separates it into child lines. The child lines inherit the Sell Price, List Price, and Cost Price based on the formulas specified in the Product Bundle configuration for each child line. This feature streamlines the management of bundled products and ensures accurate pricing and cost allocation.

### How to configure product bundles

1. **Navigate** to the Transformation section and select Product Bundle.

<Image align="center" className="border" width="40% " border={true} src="https://files.readme.io/5cc6c56b69ce025a1e01f6c4782cd18b8e426e1b80f2c497f4b6205831b99a10-image.png" />

2. **Click** on the New icon to create a new Product Bundle configuration.
3. **Provide** a unique name for the Product Bundle.
4. **Select** the Parent Identifier attribute from the attribute list. This will determine how the system segregates the Product Bundle into child lines.
5. **Toggle** the Revenue Recognition, Cost, and Commission Attribution options to activate if the Product Bundle is eligible for these features.
6. **Set** the status of the Product Bundle to active or inactive by toggling the active option.
7. **Specify** the effective start and end dates for the Product Bundle.
8. **Click** on the Save icon to save the configuration.
9. To edit a Product Bundle configuration, make the desired changes and click on the Save icon. 
10. To delete a configuration, click on the Delete icon. 

Please find below a screenshot illustrating the configuration of a TV Bundle in the Recurly's Revenue Recognition Standalone system based on the Parent Identifier. This TV Bundle is eligible for Revenue, Cost, and Commission Attribution.

<Image align="center" className="border" border={true} src="https://files.readme.io/cc893de43f50b031a7e2a24912628d8d016a9680dbb7fe51865d655b6b0b4017-image.png" />

1. **Go** to the Rule Set page by clicking on "Rule Set" at the top.
2. To add new lines, **click** on the "New" icon. This will allow you to define child lines under the Rule Set.
3. In the Rules section, under the Parent Identifier column, **enter** the Parent value corresponding to the selected attribute in the Product Bundle main screen.
4. For each child line, **enter** the Sales Price Formula, List Price Formula, and Cost Formula based on a percentage. The system will calculate the child line sales price, list price, and cost using the total values mentioned in the SO file for the Parent line.
5. If each child line has a different quantity regardless of the quantity mentioned in the SO file, **specify** the quantity in the Rule under the Quantity column for each child line.
6. **Click** on the "Save" icon to save the configuration.
7. If any lines in the Rules need to be edited, **make** the necessary changes and click on 'Save'.
8. To delete a line in the Product Bundle Rules, **select** the line and click on the 'Delete' icon.

**Example:**

In Recurly Revenue Recognition Standalone, let's consider the example of configuring a TV Bundle under the Rule Set of Product Bundle. To set it up, we add 5 child lines in the Rules section, specifying the Parent Identifier as "TV Bundle." For each child line, we define the Sales Price formula, List Price formula, and Cost Formula. We can also set the desired Quantity values for each child line, independent of the Quantity mentioned in the SO File. Once the configuration is finalized, we save it to apply the specified calculations and rules to the TV Bundle in Recurly Revenue Recognition Standalone.

![](https://files.readme.io/867fe40b3c6673da7aef8584d2ef15ab0114c60ccc11f00b7530d5c5c9f196cf-image.png)

Once the above setup is configured in Recurly Revenue Recognition Standalone, when an SO file is uploaded to the system and contains the correct Parent Identifier, the system automatically splits the transaction into child lines based on the configured rules and criteria. This segmentation applies the specified formulas and quantities to calculate the sales price, list price, and cost for each child line, ensuring precise tracking and management of revenue and costs associated with the bundled products.

## Data rules

Recurly Revenue Recognition Standalone allows for the configuration of data rules to apply specific criteria and formulas to transactions during the upload of sales orders, ensuring accurate revenue recognition, contract management, and cost allocation.

### How to configure data rules

1. **Navigate** to the Transformation section and select Data Rules.

<Image align="center" className="border" width="40% " border={true} src="https://files.readme.io/5cc6c56b69ce025a1e01f6c4782cd18b8e426e1b80f2c497f4b6205831b99a10-image.png" />

2. **Enter** a unique name for the data rule in the "Rule Name" field.
3. **Select** the desired object from the drop-down list (Contract, Order Line, Doc Line, or Cost) to determine at which level the rule should be applied.
4. **Choose** the appropriate book from the drop-down list for which the data rule configurations should apply.
5. **Specify** the active dates for the data rule by entering the start date and end date.

![](https://files.readme.io/72fbb53186e73732e825e154e006a54bf505c77fb54cc0b2c8f45eefeb1989ac-image.png)

6. **Click** on the Save icon to save the data rule.

> **Notes:**
>
> * Once configured, Data Rules in Recurly revenue recognition cannot be deleted but can be set to an inactive status.
> * To change the status of a Data Rule, click on the option under the Status column and switch it from Active to Inactive. Remember to save the changes by clicking on the Save icon.
> * If you need to make edits to a Data Rule configuration, you can modify the necessary fields and save the changes using the Save icon.
> * While deletion is not possible, you have the flexibility to update and adjust Data Rules to suit your business requirements as needed.

### How to configure the Rules section under the data rules

1. In the Data Rule you want to edit, **click** on the Add icon to add a new rule under the Rules tab.
2. **Select** the Application attribute from the dropdown menu based on your object selection. For example, if you selected Contract or Order Line, choose from the Contract attribute list.
3. **Specify** a formula or value under the Formula column to calculate or display the value for the Application attribute.
4. To add a Sub Criteria for any of your rules, **click** on the Add icon. **Select** the field, operator, and enter the desired value under the Sub Criteria section.
5. **Click** on the Save icon to save the configuration.
6. Multiple rules and sub-criteria can be added as needed.
7. To delete a configuration, select the line and click on the Delete icon in the Rules tab. To delete only the Sub Criteria, select the specific line and click on the Delete icon next to it.
8. Make any necessary changes to the Rules or Sub Criteria, and then save the changes using the Save icon.

### How to configure the criteria under the data rules

1. **Click** on the Add icon to add a new row in the Criteria section.
2. **Select** the field from the dropdown menu based on your object selection.
3. **Choose** the appropriate operator from the dropdown list under the Operator field.
4. **Enter** the value corresponding to the data mentioned under the Field column.
5. Multiple criteria can be added by repeating the above steps.

If any of the criteria need to be edited, make the necessary changes and click on the Save icon.\
To delete a criteria, click on the Delete icon next to it.

## Datasets

Datasets in Recurly revenue recognition Standalone are essential data tables used for analysis purposes. They serve as the foundation for all data analysis activities. With datasets, you can create comprehensive tables that incorporate fields from various attributes such as item, liability account, revenue account, region, country, customer, and more.

Once a dataset is created, it automatically refreshes on a daily basis, ensuring that you have the most up-to-date information for your analysis. It provides you with valuable insights and enables you to perform in-depth analysis and reporting.

It's important to note that once a dataset is created, it cannot be deleted. However, if needed, you can inactivate a dataset to prevent it from being used in further analysis. This maintains data integrity and allows you to manage your datasets effectively.

### How to create a dataset

1. **Navigate** to the Transformation section and select Datasets.

<Image align="center" className="border" width="40% " border={true} src="https://files.readme.io/5cc6c56b69ce025a1e01f6c4782cd18b8e426e1b80f2c497f4b6205831b99a10-image.png" />

2. **Enter** a name for the dataset in the provided field.
3. **Select** the appropriate books for which you want to apply this dataset.
4. **Choose** the desired attributes from the available options and mark the primary attribute(s) for the dataset.
5. **Click** on Save to save the dataset configuration.

Once you have configured the datasets and uploaded the sales order file with the appropriate identifiers, Recurly revenue recognition will display the details in the Revenue Workbench according to the dataset configurations. This means that the data from the sales order file will be analyzed and processed based on the rules and attributes defined in the datasets, providing you with accurate and meaningful insights.

Furthermore, the datasets will be reflected in all reports generated in Recurly revenue recognition. This ensures that the data analysis and reporting are consistent across different functionalities and allows you to leverage the dataset configurations for comprehensive and consistent reporting throughout the system.
