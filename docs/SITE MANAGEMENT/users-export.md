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
# Overview

# Definition

The user export feature in Recurly allows administrators to easily download a comprehensive report containing information about every site user who has access to their Recurly site. This report includes the user's name, email address, their access permissions within Recurly, and the date each user was created.

> 👍 About users exports
>
> To capture the most precise history of user access, we advise setting up regular exports. This approach is crucial because our exports include users who had and continue to have access during the selected export dates, but we do not provide past access information. Regular exports will provide a more accurate snapshot of user access at any given point.

# How to access User Export?

1. Go to the **Admin** section of Recurly.
2. In the left-side panel, navigate to the "**Admin Exports**" option.
3. Select "**Users**" from the list of available exports.

<Image align="center" width="50% " src="https://files.readme.io/c68c593-image.png" />

# Requesting User exports

After selecting the "Users" option, you can set the desired time range for the report. This allows you to specify the period from which you want to obtain information about your active site users. Once you have set the time range, click on the "Request Export" button.

> **Recommendation:** To capture the most precise history of user access, we advise setting up regular, automated exports with shorter time frame intervals. This approach is crucial because our exports include users who had and continue to have access during the selected export dates, but we do not provide past access information. Regular, shorter interval exports will provide a more accurate snapshot of user access at any given point.

<Image align="center" width="80% " src="https://files.readme.io/94251c2-image.png" />

## Downloading the User export

Once the export file is ready, you will see it listed in the "Export History" table. To download the file, hover over the ellipses next to the export entry and click on the "Download" option. The exported data will be in CSV format, which can be easily opened and analyzed using spreadsheet software.

<Image align="center" width="75% " src="https://files.readme.io/db43603-image.png" />

# Available filters

The exported CSV file provides columns under your export based on specific criteria.

●	**Email Address:** Filter users by their email addresses.\
●	**Name:** Filter users by their first and last names.
●	 **User Access:** View the list of permissions assigned to each user.
●	**Date Added:** Filter users based on the date they accepted their invitation to the Recurly site.
●	 **User Role:** Filter users based on the role they are assigned to within your site.

# Exports table

| Id                                         | Example                                         | Description                                                                                                                          |
| :----------------------------------------- | :---------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------- |
| <span id="email">email</span>              | [john.doe@email.com](mailto:john.doe@email.com) | The unique email address associated with each user. Used for login and communication purposes.                                       |
| <span id="first_name">first\_name</span>   | John                                            | The first name of the user. Useful for personalized communication and record management.                                             |
| <span id="last_name">last\_name</span>     | Doe                                             | The last name or surname of the user. Paired with the first name for complete identification.                                        |
| <span id="user_access">user\_access</span> | Full Access                                     | Defines the permissions and capabilities a user has within the system. Can range from "Full Access" to "Read-Only".                  |
| <span id="date_added">date\_added</span>   | 2023-01-05                                      | The date when the user was added to the system. This helps track user history and tenure.                                            |
| <span id="user_role">user\_role</span>     | Administrator                                   | The role assigned to the user, dictating their responsibilities and tasks within the platform. Examples: Administrator, User, Guest. |