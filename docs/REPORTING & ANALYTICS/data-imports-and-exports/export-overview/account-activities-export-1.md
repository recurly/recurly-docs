---
title: Account activities - export
excerpt: >-
  Learn how the Account Activities export provides a detailed log of user
  actions and modifications made within customer accounts in Recurly.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The Account Activities export gives you a detailed log of every user action and modification made within your customer accounts. Use it to monitor account behavior, investigate specific interactions, and make informed decisions based on real activity patterns across your subscriber base.

<Image align="center" border={true} width="75%" src="https://files.readme.io/c10045b59667229a3134cfee35f747e47562e569f477e00fb17dcc6e481ec02e-image.png" className="border" />

### Required plan

This feature is available to all merchants on an Elite Recurly plan with an Admin and Integrations role, or a role that includes Admin and Integrations permissions. To enable this feature on your Elite site, create a support request or contact your CSM. This export is also available as an optional add-on for customers on Recurly's Starter and Professional plans — reach out to Support or your CSM for more information.

## Filters

Use these filters to narrow down the activities displayed in your export:

* **Versions**: Select the export version that best fits your needs. Versions are based on the changelog at the bottom of this page
* **Export on**: Defaults to the creation timestamp of each activity
* **Time range**: Defaults to yesterday, capturing all activities created on that day in your site's default time zone

# Exports table

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Download Button</title>
    <style>
        .download-button {
            display: inline-block;
            padding: 5px 10px;
            text-align: center;
            text-decoration: none;
            color: #1C2833FF;
            background-color: #F8F8F8FF;
            border-radius: 5px;
            font-weight: normal;
            transition: background-color 0.5s ease, transform 0.3s ease;
            transition: 0.4s !important;
            font-family: 'Proxima-nova', Arial, sans-serif;
            max-width: 100%;
        }

        .download-button:hover {
            background-color: #FFFFFFFF;
            transform: scale(1.02);
        }
        a:hover {
            color: #1C2833FF;
            text-decoration: underline !important;
        }
    </style>
</head>
<body>
    <a href="https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx" class="download-button">Download our complete export schema</a>
</body>
</html>
`}</HTMLBlock>

| Id                                          | Example                                                  | Description                                                                                                                                                                                                                                   | Data type |
| :------------------------------------------ | :------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------- |
| <span id="account_code">account_code</span> | 123456789, [janedoe@gmail.com](mailto:janedoe@gmail.com) | A unique identifier for your customers within Recurly. Defaults to the customer's email address if no specific value is provided. This unmodifiable code is Recurly's primary identifier and is used to link records across multiple exports. | string    |
| <span id="acted_id">acted_id</span>         | 6ee26cd0ad75ffe2311e3e4f00a2f990                         | The unique identifier for the object where the activity occurred, such as an invoice or a transaction.                                                                                                                                        | string    |
| <span id="acted_type">acted_type</span>     | subscription                                             | The type of entity associated with the activity, such as an invoice or a subscription.                                                                                                                                                        | string    |
| <span id="actor_name">actor_name</span>     | Default API Key                                          | The entity responsible for the activity. This may be the Recurly Background Bot, an API call, or a specific user on your site.                                                                                                                | string    |
| <span id="actor_type">actor_type</span>     | api_key                                                  | The type of actor who performed the activity. Accepted values: `user` or `api_key`.                                                                                                                                                           | string    |
| <span id="created_at">created_at</span>     | 2014-01-01 10:00:00 PST                                  | The date and time when the activity occurred.                                                                                                                                                                                                 | timestamp |
| <span id="verb">verb</span>                 | subscribed                                               | The action performed on the object, describing what changed and how.                                                                                                                                                                          | string    |
| <span id="metadata">metadata</span>         | `{"plan_name":"trial_plan"}`                             | A JSON string containing additional details about the activity.                                                                                                                                                                               | string    |

# Version changelog

* N/A
