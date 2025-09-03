---
title: Users export
excerpt: >-
  Effortlessly download a report of your Recurly site users, apply filters, and
  gain valuable insights into your user base.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Definition

The user export feature in Recurly allows administrators to easily download a comprehensive report containing information about every site user who has access to their Recurly site. This report includes the user's name, email address, their access permissions within Recurly, and the date each user was created.

> 👍 About users exports
>
> To capture the most precise history of user access, we advise setting up regular exports. This approach is crucial because our exports include users who had and continue to have access during the selected export dates, but we do not provide past access information. Regular exports will provide a more accurate snapshot of user access at any given point.

# Accessing user exports

1. Go to the **Admin** section of Recurly.
2. In the left-side panel, navigate to the "**Admin Exports**" option.
3. Select "**Users**" from the list of available exports.

![](https://files.readme.io/bfc90de5f39f60baedca5b749ceb675ec5d6f30e59f1d57a52b50153cca2026d-image.png)

# Obtaining an user export

To obtain an Users Export, visit the Admin Exports page and select the List of users report. This comprehensive report offers a detailed overview of all users within your Recurly site including first and last name, email, user role, user access and date added.

<Image align="center" className="border" border={true} width="300% " src="https://files.readme.io/72a3dcb735d4b2da29b969959b869b0121d4f79d6fe52584508c868c74e144ac-image.png" />

## Filtering options in the users report

<br />

## Select additional filters

> <br />

<br />

## Choose a visualization

Tailor your data presentation to suit your preferences by selecting a visualization option that best represents your dataset. Whether it's a table, column chart, bar graph, scatterplot, line graph, pie chart, map, or single value visualization, Recurly provides a range of visualization options to enhance your understanding of the account activities data.

<Image align="left" className="border" border={true} width="500% " src="https://files.readme.io/c181fbd418869615b74310fccbbc6320e82eff3ad4cec6aeaccca85953147351-image.png" />

<br />

<br />

Table (Default)
Column Chart
Bar Graph
Scatterplot
Line Graph
Pie Chart
Map
Single Value


Additional options are available by clicking the ellipses button at the end of the options list where a dropdown list of several more visualization options are presented.

## Download and save your data

Once the export file is ready, you will see it listed in the "Export History" table. To download the file, hover over the ellipses next to the export entry and click on the "Download" option. The exported data will be in CSV format, which can be easily opened and analyzed using spreadsheet software.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/aa36af42bece0d160f15ed8b11ce82b7715d3026c8d98f6cc4ef2f102d86139b-image.png" />

# Available filters

The exported CSV file provides columns under your export based on specific criteria.

* **Email Address:** Filter users by their email addresses.
* **Name:** Filter users by their first and last names.
* **User Access:** View the list of permissions assigned to each user.
* **Date Added:** Filter users based on the date they accepted their invitation to the Recurly site.
* **User Role:** Filter users based on the role they are assigned to within your site.

# Exports table

| Id                                        | Example                                         | Description                                                                                                                          |
| :---------------------------------------- | :---------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------- |
| <span id="email">email</span>             | [john.doe@email.com](mailto:john.doe@email.com) | The unique email address associated with each user. Used for login and communication purposes.                                       |
| <span id="first_name">first_name</span>   | John                                            | The first name of the user. Useful for personalized communication and record management.                                             |
| <span id="last_name">last_name</span>     | Doe                                             | The last name or surname of the user. Paired with the first name for complete identification.                                        |
| <span id="user_access">user_access</span> | Full Access                                     | Defines the permissions and capabilities a user has within the system. Can range from "Full Access" to "Read-Only".                  |
| <span id="date_added">date_added</span>   | 2023-01-05                                      | The date when the user was added to the system. This helps track user history and tenure.                                            |
| <span id="user_role">user_role</span>     | Administrator                                   | The role assigned to the user, dictating their responsibilities and tasks within the platform. Examples: Administrator, User, Guest. |
