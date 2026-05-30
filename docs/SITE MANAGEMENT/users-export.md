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

### Prerequisites & limitations

- The **Users report** will only include users who had and continue to have access during the selected dates. Deleted users will be excluded from the users report.
- To capture the most precise history of user access, it's recommended to running this report regularly to provide a more accurate snapshot of user access at any given point in time.

# Definition

The user export feature in Recurly allows administrators to easily download a comprehensive report containing information about every site user who has access to their Recurly site. This report includes the user's name, email address, their access permissions within Recurly, and the date each user was created.

# Accessing user exports

1. **Go** to the **Admin** section of Recurly.
2. In the left-side panel, **navigate** to the "**Admin Exports**" option.

3) **Select** "**Users**" from the list of available exports.


<Image src="https://files.readme.io/cf686844ae85d399335ac290c89bbdbcb4689628b53de0ead7ea74367f7a7eb7-image.png" align="left" width="600px" border={true} />


<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

\#

<br />

## Explore interface

The Explorer is divided into three areas:

| Interface Area              | Description                                                                                                                                                                                                                  |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Left panel -Workbook        | Agent Ask natural-language questions about your invoice data. The agent suggests fields and runs queries on your behalf.                                                                                                     |
| Center panel - Field picker | Browse and search the full field catalog. Fields are grouped by topic. Click any field to add it to your active query. Use the In-use filter to see only selected fields.                                                    |
| Right panel - results area  | Toggle between Results (table view), Chart (visualization), or Both. Use the Options tab to configure axes, grouping, and chart type. Click Preview to run a sample query and verify your field selection before committing. |


<Image src="https://files.readme.io/b14849b0185ddbdd34596936d16adf5a7d73a6fb11baae37a842dc3c7616288f-image.png" border={true} />


<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

### Pre-built sample queries

- **List of users (v1**) - a comprehensive report of all users within your Recurly site including first name, last name, email, user access and date added time.&#x20;
- **List of users (v2)** - the same report as v1 but also includes the user role field.


<Image src="https://files.readme.io/3ceeaf7681e6988fc9e83a9f517a887d40a1df14b0809ae1f829e6367cf86ae0-image.png" align="left" width="500px" border={true} />


### Using the Workbook Agent

The Workbook Agent is the fastest way to start an analysis. Type a question in the text box at the bottom of the left panel and press Enter (or click the send icon).

**Example prompts:**

- "How many admins have each role type? Give me a breakdown"
- "Which users have admin access but no MFA enabled?"
- "Show me all users with billing permissions"

## Available Fields

- **Email:** Filter users by their email addresses.
- **Name:** Filter users by their first and last names.
- **User Access:** View the list of permissions assigned to each user.
- **Date Added Time:** Filter users based on the date they accepted their invitation to the Recurly site.
- **User Role:** Filter users based on the role they are assigned to within your site.

### Creating a new report

1. Browse and search the full field catalog. Fields are grouped by data topic.&#x20;
2. Click any field to add it to your active query. Use the In-use filter to see only selected fields.
3. Toggle between Results (table view), Chart (visualization), or both.&#x20;
4. Use the Options tab to configure axes, grouping, and chart type.&#x20;

### Filtering your data

1. **Standard Filters:** Drag and drop any field into the Filters section of the query builder, or click the drop-down/actions menu next to the field header in your data view and select Filter.
2. **Filtered Measures:** To create a measure that is specifically tied to one dimension (e.g., Acted Type by Actor Name), create a pivot table with your target metric and the dimension. Right-click the measure under a specific pivot value and select Create filtered measure.&#x20;


<Image src="https://files.readme.io/1ba5f548916b68fb496637523d03fa69b0884d6f4777b8dd4a1cc5a136e9e363-image.png" align="center" width="700px" border={true} />


### Downloading your data

To download your activity data, from the menu, select **Tab** - **Download**. You can choose from several file format options including CSV, Excel and JSON.


<Image src="https://files.readme.io/bbf4a79f307a7e268318352d2b6046a6a297587b4729e4a0147a74220c6bd7b3-image.png" align="left" border={true} />


<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />


<Image src="https://files.readme.io/9727ad37879c86cdf6a7f77e9689f41e48e0d5a9a80c6443c1c337f11a68da86-image.png" align="left" width="400px" border={true} />


<br />
