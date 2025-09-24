---
title: User roles and permissions
excerpt: >-
  Delve into Recurly's User Roles and Permissions to streamline access, enhance
  security, and optimize collaboration within your platform.
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

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

User Roles and Permissions in Recurly define the access rights and functionalities available to different users. By creating and assigning roles, you can ensure that each team member has the appropriate level of access, tailored to their responsibilities within the organization.

# Key benefits

* **Tailored access**: Customize roles to grant specific permissions, ensuring users only access relevant sections.
* **Enhanced security**: Limit access to sensitive data by assigning roles with restricted permissions.
* **Optimized collaboration**: Ensure team members have the tools they need by assigning roles that match their responsibilities.
* **Streamlined management**: Easily manage and modify roles from a centralized dashboard.
* **Flexibility**: Adapt roles as your organization grows or changes, ensuring continued alignment with business needs.

# Key details

## Role management

A role in Recurly refers to a defined set of permissions and access rights that determine what actions and features a user can perform or obtain access to within the Recurly App. You have the ability to tailor your customized roles  to match your organization's unique requirements and team structure. This allows you to grant appropriate access to specific sections and functionalities based on each user's role and responsibilities.

Take control of access management within your organization using User-Based Roles in Recurly. By creating and assigning roles, you can streamline user permissions, enhance data security, and optimize collaboration across your Recurly account. Experience greater control and flexibility in managing user access with user-based roles.

## Creating a new role

1. **Navigate** to the "Admin" section in the Recurly App.
2. **Click** on "Roles".

<Image align="center" border={false} src="https://files.readme.io/540ff370d0d48eb9193c1a5e2918625c2b34ea42312fa604cac05ed19d906404-image.png" />

3. On the top-right corner of the screen, **find** and **click** the "Create Role" button.

<Image align="center" border={true} src="https://files.readme.io/62a5f2d519f87321ed20db7a4775c7e2fe03641ef29179bad5b03a58d752ebd5-image.png" className="border" />

4. Give the new role a descriptive name that reflects its purpose.
5. Provide a brief description to help others understand the role's function and scope.
6. Customize the role's permissions by selecting the appropriate actions and functionalities that you want to grant to users with this role.

<Image border={false} src="https://files.readme.io/6ad62ba-image.png" />

### Site admin role

The Site Admin role is the most powerful role within the Recurly application, providing unrestricted access to all features and settings. It is essential to carefully manage who has this level of access due to the permissions that come with it. Here are key things to know about the Site Admin role:

* **Default Behavior**: By default, Recurly will assign the first user who is ever added to the site as the Site Admin. This is the user who typically sets up the Recurly account initially.
* **Unrestricted Access**: The Site Admin role provides full access to all permissions in the Recurly App. This includes billing information, account settings, user permissions, and more.
* **Mandatory Presence**: It is essential to assign at least one user as a Site Admin on every Recurly production site. This ensures that there is always at least one user with the ability to manage and configure the site as needed.
* **Indelibility**: The Site Admin role itself cannot be deleted or edited, except for the role description. This is designed to prevent a situation where no users have full access to manage the site.
* **Responsibility**: Given the extensive permissions that the Site Admin role carries, it should be assigned thoughtfully and typically only to trusted individuals within the organization, such as business owners or top-level managers.

> 👍 **Recommendation**
>
> Review your Site Admin assignments regularly and ensure that only necessary individuals have this level of access. Remove the Site Admin role from users who no longer require it to maintain the security and integrity of your Recurly account.

## Deleting a role

1. Navigate to the "Roles" page in the Admin section of Recurly.
2. From the Roles list page, find the role you want to delete.
3. Select the "Delete" option.

<Image align="center" border={true} src="https://files.readme.io/342cf78-image.png" className="border" />

4. If there are users assigned to the role, a prompt will appear asking you to reassign them to an alternative role. Choose the appropriate role for reassignment.

<Image align="center" border={true} src="https://files.readme.io/176cfc0-image.png" className="border" />

5. If none of the existing roles fit the users you need to reassign, you can create a new role at this point.
6. Confirm the deletion by following the prompts or clicking the appropriate button.
7. Once the role is successfully deleted, the assigned users will assume the permissions of their newly designated role.

> Remember, it's important to carefully consider the implications of deleting a role and ensure that users are appropriately reassigned to maintain access and functionality within the Recurly system.

### Reassigning and removing a site admin

1. Access the user's profile directly.
2. Select the desired alternative role from the User Role selection field.

<Image align="center" border={true} src="https://files.readme.io/6fe5b06-image.png" className="border" />

If the user is the only active site user assigned to the Site Admin role, designate an alternative site user to be assigned as the Site Admin before reassigning the user. It is necessary to have at least one site user assigned to this role at all times.

### Out-of-the-box roles for pre-existing merchants

If your site was live in production prior to migrating to the roles-based user management system, Recurly provides a set of "out-of-the-box" roles to ensure a seamless transition:

* The out-of-the-box roles match the permission sets that were assigned to individual site users before the migration.
* These roles reflect the unique permission combinations assigned to each site's users.
* You can create your own custom roles and rename or delete the “out-of-the-box” provided roles as needed, except for the "Site Admin" role.
* The "Site Admin" role is essential and must have at least one site user assigned to it at all times. Recurly will create the Site Admin role for all sites.

## User permissions

There are two options for providing access to the Customers section of the application: Read Only and Can Edit.

<Image align="center" border={true} width="50% " src="https://files.readme.io/ea6bf4e-image.png" className="border" />

* **Read Only:** Users with this access level can view accounts, invoices, transactions, and subscriptions. They are also able to add account notes and view customer information. However, they do not have access to the links for hosted account management or the ability to update billing information.
* **Can Edit:** Users with this access level have the ability to view and edit accounts, subscriptions, invoices, and transactions. In addition to the permissions of the Read Only level, they can make changes to customer records.

However, they are not able to edit, delete, or add to plans, transactions, coupons, items, or gift card redemptions from the Customers section, unless they also have edit access to the Configuration section of Recurly.

### Analytics

Users with this access level can view and export all data under the Analytics section. They have comprehensive visibility into analytics-related information.

<Image align="center" border={true} src="https://files.readme.io/270b250-image.png" className="border" />

### Revenue Recognition

Users in this category have either Read-Only or Admin access to Recurly's Revenue Recognition platform. The "Allow Access" checkmark enables or disables general access to Recurly's revenue recognition in a role, and it can always be edited. However, the ability to set whether a role has "Read-Only" or "Admin" access within the revenue recognition platform is only available during the initial configuration of the role. After the role has been configured and saved, granular access control within the revenue recognition platform itself is the only way to configure access.
Please note that the Revenue Recognition section and corresponding permission set will only appear on Recurly sites that have the Revenue Recognition feature flag enabled.

### Configuration

Users with Configuration access can view and edit Site Settings, Business Entities, Email Templates, Payment Gateways, Custom Fields, Hosted Payment Pages, Dunning Management, Measured Units, Tax Settings, Currencies, Fraud Management, Shipping Information, Network Tokens, Apple Pay, Entitlements, Payment Settings, Gift Card Settings, and Analytics Settings. They also have the ability to create, edit, and view Plans, Items, and Coupons.

<Image align="center" border={true} src="https://files.readme.io/56e2aa4-image.png" className="border" />

### Integrations

Users with Integrations access can view and edit Webhooks, API keys, and Recurly Integrations to QuickBooks Online, Xero, Mailchimp, Salesforce, and Zendesk. They have control over the integrations between Recurly and these external platforms.

### Admin

Users with Admin access have full control over their company's billing information, account settings, and Users/Roles/Admin Exports/SSO Settings. They have the highest level of access and authority within the Recurly system.
