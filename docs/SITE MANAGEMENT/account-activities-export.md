---
title: Account activities export
excerpt: >-
  Dive deep into account interactions with Recurly's Account Activities Report,
  offering a comprehensive view of user actions and changes.
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    Dive into Recurly's Custom Fields to personalize your data, enhancing
    account, charge, item, plan, and subscription details for a tailored
    experience.
  robots: index
next:
  description: ''
---
# Definition

The Account Activities Report in Recurly provides a detailed log of user actions and modifications made within customer accounts. It serves as a powerful tool to monitor, analyze, and understand specific interactions, enabling businesses to make informed decisions based on user behavior and account activity patterns.

# Accessing account activities

Account activities can be viewed at both the account level, for individual customer accounts, and at the site level within the Admin section of the Recurly App (UI). By navigating to the "Admin Exports" page, you can conveniently access and explore the account-level activity log.

<Image align="center" border={true} width="80% " src="https://files.readme.io/2ede107c5f42b2c1f59b5cde5991d8278042fc5307e7038bf87727dc1a506f26-image.png" className="border" />

# Obtaining an account activities export

To obtain an Account Activities Export, visit the Admin Exports page and select the List of activities report. This comprehensive report offers a detailed overview of all account-level activities performed within your Recurly site. Whether you prefer a list of activities or a count of activities, you can choose the desired visualization option to meet your reporting needs.

<Image align="center" border={true} src="https://files.readme.io/09564797b2b3a7d1e6c5f282885b06d9c5e61a901cdf28a9cb5d49d0ec3de58d-image.png" className="border" />

# Filtering options in the account activities report

The Account Activities report provides various filtering options to refine and narrow down your search criteria. You can filter activities based on account code, acted upon object ID, acted type, actor name, actor type, created at time/date, verb, and metadata. Customizing the fields displayed in your report is made easy with the ability to select or exclude specific fields on the Explore screen.

![](https://files.readme.io/d2e40d3-image.png)

* **<span id="Account_Code">Account Code</span>:** The unique numerical identifier for the corresponding customer account associated with the activity.
* **<span id="Acted_Upon_Object_ID">Acted Upon Object ID</span>:** The unique numerical identifier for the specific object where the activity occurred, such as an invoice or a transaction.
  * **Tip:** You can click on any "Acted ID" within the table to quickly open the corresponding object in a new tab and view the related activity. For example, clicking on an Acted ID linked to a subscription change allows you to instantly see that specific subscription in a new tab by selecting "Open in Recurly App."
* **<span id="Acted_Type">Acted Type</span>:** Indicates the location within RA where the activity took place, such as an invoice or a subscription.
* **<span id="Actor_Name">Actor Name</span>:** Represents the entity or user on your RA site responsible for the activity. This could be the Recurly Background Bot, an API call, or a unique user.
* **<span id="Actor_Type">Actor Type</span>:** Specifies the type of actor who performed the activity, such as a user.
* **<span id="Created_at_Time_Date">Created at Time/Date</span>:** Records the timestamp or date when the activity occurred. You have the option to choose either the time or date representation.
* **<span id="Verb">Verb</span>:** Describes the action performed on an object and how it was changed. For instance, it could be "<span id="sent_email">sent_email</span>," "<span id="renewed">renewed</span>," or "<span id="marked_past_due">marked_past_due</span>."
* **<span id="Metadata">Metadata</span>:** Provides specific details about the activity, such as the name of the plan assigned to a customer or the invoice ID number sent to a customer.

## Select additional filters

To further refine your search, the Account Activities report offers additional filters such as "Search Entire Dataset," "Account Activities Acted Type," and "Account Activities Created At Date." These filters allow you to search for specific keywords, focus on particular acted types or objects, and define a specific date range for the activities you want to analyze.

![](https://files.readme.io/164484f-Screen_Shot_2022-08-09_at_2.27.44_PM.png "Screen Shot 2022-08-09 at 2.27.44 PM.png")

## Choose a visualization

Tailor your data presentation to suit your preferences by selecting a visualization option that best represents your dataset. Whether it's a table, column chart, bar graph, scatterplot, line graph, pie chart, map, or single value visualization, Recurly provides a range of visualization options to enhance your understanding of the account activities data.

![](https://files.readme.io/74b5576-image.png)

* Table (Default)
* Column Chart
* Bar Graph
* Scatterplot
* Line Graph
* Pie Chart
* Map
* Single Value

Additional options are available by clicking the ellipses button at the end of the options list where a dropdown list of several more visualization options are presented.

![](https://files.readme.io/932fc01-Screen_Shot_2022-08-16_at_4.25.15_PM.png "Screen Shot 2022-08-16 at 4.25.15 PM.png")

## Download and save your data

Once you have explored and customized your dataset, you can easily download it for further analysis or record-keeping. Simply click the gear icon on the top-right side of the Explore screen and select "Download" to choose from a variety of file format options. For larger datasets exceeding the table visualization limit of 5,000 rows, downloading the file ensures that you can access the complete dataset and analyze all results.

![](https://files.readme.io/286fce9-Screen_Shot_2022-08-09_at_2.50.19_PM.png "Screen Shot 2022-08-09 at 2.50.19 PM.png")

![](https://files.readme.io/30eb6af-Screen_Shot_2022-08-09_at_2.51.45_PM.png "Screen Shot 2022-08-09 at 2.51.45 PM.png")

Uncover valuable insights and track user actions with the Account Activities Report in Recurly. Gain a deeper understanding of account-level activities, identify trends, and make data-driven decisions to optimize your subscription business.
