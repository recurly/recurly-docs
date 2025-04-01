---
title: Entitlements
excerpt: >-
  Enable comprehensive access management across your digital ecosystem with
  Recurly's Cross-platform Entitlements. Create and manage customer access
  rights, establish effective paywalls, and leverage API functionality for
  detailed entitlement checks. Learn more in our comprehensive guide.
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

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

# Definition

Entitlements are granular features built and bundled to manage customer access rights across multiple platforms. These entitlements are often unlocked through subscription purchases across various app stores and the web. Managed through a simple UI, they define what functionalities or services a user can access.

# Key benefits

* **Controlled access:** Define and manage access to various features within your product environment, creating a customized user experience.
* **Cross-platform consistency:** Configure and apply entitlements across different platforms (web, mobile, and app stores), providing users with a seamless experience.
* **Efficiency:** With Recurly's API support, conduct entitlement checks effectively, streamlining your operations and saving time.
* **Enhanced monetization:** With the ability to create paywalls, drive revenue by gating premium features or content.
* **Flexibility:** An unlimited number of entitlements can be created, offering flexibility to meet changing business needs.

# Key details

Recurly's Cross-platform Entitlements enable you to build and manage specific features that determine customer access rights in a simple and unified interface. They allow you to control the extent of features your customers can access based on their subscription levels.

For example, if you run a digital magazine, you can create entitlements that allow basic subscribers to access standard content while premium subscribers have additional access to exclusive articles, special reports, or digital events.

Creating an entitlement in Recurly requires you to define specific attributes like Name, Code, Description, and Grantors. Once created, these entitlements can be updated in real-time and are reflected immediately in all subsequent API calls. Should you need to delete an entitlement, it is removed from the system instantly.

> **Note:**Retrieving these entitlements can be done through Recurly's API by requesting all active entitlements for a specific customer account. Entitlements are granted when a customer makes a recurring purchase (like a subscription) that is associated with the entitlement.

# Creating an entitlement

   a. **Log in** to your Recurly Admin UI.

   b. **Navigate** to the Entitlements section.

<Image align="center" className="border" border={true} src="https://files.readme.io/a27e3418d1c785fe38623167fbcb01816c93d3569a252f6faf9a2bbff59b35ee-image.png" />

   c. **Click on** "Create your first entitlement" to start creating a new entitlement.

<Image align="center" className="border" width="65% " border={true} src="https://files.readme.io/38e1b03-image.png" />

   d. **Define** the attributes - Name, Code, Description, and Grantors.

**Name**

The concise label for the entitlement, summarizing its primary function. It doesn't appear on subscriber invoices, Checkout, or Hosted Payment Pages and has a 255-character limit.

**Code**

The unique identifier for the entitlement within Recurly. It facilitates linking the entitlement to specific features or functionalities in your application, such as feature flags.

**Description**

A detailed explanation of the entitlement, offering customers insight into its associated feature or functionality.

**Grantors**

Recurring products, like Plans or Items, that provide the entitlement upon a customer's subscription purchase. An Entitlement can be linked to multiple products, and vice versa, a product can correspond to several Entitlements.

e. **Save** your changes by pressing "Create Entitlement".

# Assigning an entitlement

a. In your Recurly Admin UI, **navigate** to the Entitlements section.

b. **Select** the entitlement you want to assign. **Note**: You can complete this step when creating a new entitlement.

<Image align="center" className="border" width="65% " border={true} src="https://files.readme.io/5c40763-image.png" />

c. **Click** on “Edit Entitlement”.

<Image align="center" className="border" width="65% " border={true} src="https://files.readme.io/83ec1b0-image.png" />

d. **Click** on “Add Assignment” and **choose** between **Plan** or **Item**.

<Image align="center" className="border" width="65% " border={true} src="https://files.readme.io/23fac5a-image.png" />

<Image align="center" width="5px" src="https://files.readme.io/5121661-image.png" />

e. **Select** one from the list to add it.

<Image align="center" className="border" width="65% " border={true} src="https://files.readme.io/2886755-image.png" />

<Image align="center" className="border" width="65% " border={true} src="https://files.readme.io/3a4c308-image.png" />

f. **Save** changes.

# Updating an entitlement

   a. **Navigate** to the Entitlements section in your Recurly Admin UI.

   b. **Select** the entitlement you want to update.

   c. **Make** the necessary changes to the attributes or associations.

   d. **Save** your changes. 

> **Note:** All subsequent API calls will reflect these updates.

# Deleting an entitlement

   a. In your Recurly Admin UI, navigate to the Entitlements section.

   b. Select the entitlement you want to delete.

<Image align="center" className="border" width="65% " border={true} src="https://files.readme.io/5c40763-image.png" />

   c. Click on "Delete" and then “Confirm”. This will remove the entitlement instantly.

<Image align="center" className="border" width="65% " border={true} src="https://files.readme.io/83ec1b0-image.png" />
