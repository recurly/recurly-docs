---
title: Alternate Email Templates
excerpt: >-
  Tailor customer communication, branding, updates regarding local mandates, and
  more, to each of your customer segments based on the business entity(ies) they
  subscribe to, or their geographic location.
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

## Required plan

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Important callout

In order to be compliant with regulations and standards such as PCI-DSS, HIPAA, may we suggest not include any sensitive information (e.g. protected health information, credit card numbers) when using Recurly’s email templates.

> 📘 Alternate Email Template functionality is separate from Dunning Email Campaigns
>
> To learn more about how to create and manage multiple dunning campaign emails, read our [Dunning documentation](https://docs.recurly.com/docs/dunning-management#email-template-configuration).

# Definition

Default email templates in Recurly refer to predefined layouts and formats which businesses can use to send automated or scheduled emails to their customers. These templates are designed to maintain brand consistency, enhance communication efficiency, and ensure relevant information is communicated in a structured manner.

Alternate email templates, or the ability to create an alternate variant of a given email, empowers merchants to customize information sent via email for each of their unique customer segments. Each non-dunning email template can have up to 20 total variants, which includes the default template variant and 19 alternate email template variants. This means that you can have 20 different variations of each non-dunning email template.

# Key benefits

All the benefits our default email templates already brought you... and more!

* **Supports multi-brand organizations:** Ensure each customer email resonates with each of your organization's brands or legal entities
* **Send compliant emails:** Include local mandate-related communications to customers in specific regions to ensure your email outreach is compliant
* **Create customer segments to bolster automation and efficiency:** Add audience criteria to each email template variant to automate the process of sending the correct email content to the desired customer audience. Email content and branding is dynamic based on a given applicable invoice event, allowing customers subscribing to more than 1 of your brands at once to receive the right email from the right brand and the right time

# Creating an alternate email template

1. Navigate to Email Templates.
2. Identify the template you would like to create an alternate email template for, and select the "New Template" button.
3. A modal will appear. If you haven't created an alternate email template for the given email before, the only option to create a new template off of will be from that email's default email template. **This will copy over all of that default template's (or the specific alternate template you select if others have already been created) settings, subject line, description, body content, language translations, and invoice PDF attachment preferences for emails with invoices associated.**

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/07e5f5beab4218be9cd05ea9020a067cfb0325c41045cdcdd75b33624b4ffc05-Screenshot_2024-12-09_at_8.30.23_PM.png" />

1. Give the new alternate email template you would like to create a name, which will be internal and not customer-facing, and press "Create."
2. On the new email template variant page, make sure to fill out all required fields.
3. Add at least 1 piece of "Audience Criteria." Audience criteria can be any combination of Account Address Country, Billing Address Country, and/or Business Entity. Your template will remain in a "Disabled" state until you have at least 1 piece of Audience Criteria set, which is a requirement before changing it to an "Enabled" state. Press the "Enabled" button once you are ready for this variant to become active and start sending to customers that meet its Audience Criteria.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/a3d033e8d18f8445fe25d903e15dbe86f39167046b09984bb51bcb83476aa6c6-Screenshot_2024-12-09_at_8.35.47_PM.png" />

1. Press "Save Changes". If you do not save your changes and press "Cancel" or navigate away from the new template without saving, the new alternate template will not be saved nor created.

## Email Template Settings

Email template general settings live at the email template variant level. This means that each individual email template on your site has its own configurable settings that you must set and manage on each variant, including the default variant.

### General email settings available to all email templates are:

* The *"From" email address* (required field) and *"CC email address"* (optional field) you would like to use for the given template variant
* Whether or not to *append a PDF version of the customer's invoice* if there is an invoice associated with a given email template
* The option to *disable sending the HTML version* of your email content to customers
  * By default, Recurly sends both a plain-text and HTML email to your customers. Your user’s mail client will display the HTML version if it can, otherwise it will fall back to the text-only version.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/5a25851753d47bcf1c1c7f8a4313271a479cef3bfe2642aee78770d87a6c79a4-Screenshot_2024-12-09_at_8.38.12_PM.png" />

There are additional specialized email settings that apply to some emails.

For example, you can specify how many days before a renewal event occurs you want to send a renewal email to your customer. Recurly applies the industry-standard amount of days prior to an event to send a given renewal-reminder email to customers, however, you can change those settings by clicking "Options" next to an email template type, and then "Settings." The "Options" dropdown is only available on email templates that have applicable specialized settings.

### Email templates with specialized settings include:

* Payment Confirmation
* Trial Ending
* All Subscription Renewal Emails (Bill Date Reminder, Term Renewal Reminder, Annual Reminder, Mastercard Reminder, SEPA Renewal Reminder, Credit Card Expired, Ramp Price Change)

## Audience Criteria

A given email template variant can be sent to a customer based on their **plan(s)**, **billing or account country location**, or the **business entity(ies)** they subscribe to. These criteria are configurable under each email template variant's "Audience Criteria" section. Default email template variants do not have an Audience Criteria section, because they are used as the "fallback" email template to send to any customer who does not meet any attributes specified in an alternate template.

### Simple Example

A merchant has 1 business entity that supports subscribers worldwide. They have a default email template for all emails, but are going to create 1 additional variant for each of their emails on Recurly, which have an intended audience of European Union-based subscribers.

Let's use the "New Subscription" email template as an example. The merchant has a customer, Anne Smith, who lives in France. The merchant creates a separate email template variant for the "New Subscription" email template and sets the Account and Billing Country attributes to "France, Italy, Spain, and Germany."

Anne Smith previously received the default template variant for the New Subscription email, will she will now automatically receive the merchant's EU-focused email template variant instead, since she meets its Audience Criteria.

### Unique Audience Criteria

> 📘 Audience Criteria must be unique for email variants within the same email template type
>
> You can not use the same Audience Criteria in one variant within a given email template on another variant within the same email template. You can, however, repeat Audience Criteria in a template variant within a completely separate email template.

Let's use the "New Subscription" email template as an example. If you make three (3) email template variants for "New Subscription," and add your "ACME EU" Business Entity, "France" as an Account Country  and "Italy" as a Billing Country for attributes on the Audience Criteria for a New Subscription template variant, then you will not be able to reuse those specific attributes (ACME EU for Business Entity, and/or France for Account Country, and/or Italy for Billing Country) as criteria on any other template variant under the New Subscription email template type. This prevents conflicting logic in determining which email template variant to send your customers.

### Audience Criteria Hierarchy

The example above was a simplified way of demonstrating how a merchant would ensure the correct email template variant is sent to a customer. However, it is likely that more complex organizations will require more flexible support.

Depending on your business model, you may have customers that meet attributes that span more than one alternate email variant within any given email template. When this happens, there is a hierarchy that will take effect to send the appropriate email template to your customer. The hierarchy of choosing a template variant when a customer meets **more than one template variant's Audience Criteria** is the following:

1. **Plan**
   1. If a Plan is set as the email template variant's Audience Criteria, then the Plan will determine which of your customers will receive the email template variant regardless if any other Audience Criteria has been selected.
      1. If you choose ***not*** to use Plan in your Audience Criteria, plans will not be taken into consideration when determining which email variant to send a customer at a given point in time.  In this case, Business Entity, Billing Country, or Account Country, if chosen, will be used to determine which template variant to send.
2. **Business Entity**
   1. If there is an invoice associated with an email event, or if a customer account has an Overriding Business Entity applied, then the Business Entity will determine which email template variant your customer will receive.
      1. If you choose ***not*** to use Business Entity in your Audience Criteria, business entities will not be taken into consideration when determining which email variant to send a customer at a given point in time. In this case, Billing Country or Account Country will be used to determine which template variant to send.
3. **Billing Country**
   1. If there is no Business Entity attribute set in an email template variant's Audience Criteria, or a business entity is not able to be identified for an email because a customer does not have an Overriding Business Entity applied to their account ***and*** there is no invoice associated with the particular email template, then **Billing Country** will be used to determine which email variant to send a customer.
4. **Account Country**
   1. If there is no Business Entity attribute set in an email template variant's Audience Criteria, ***or*** a business entity is not able to be identified for an email because a customer does not have an Overriding Business Entity applied to their account ***and*** there is no invoice associated with the particular email template, ***or*** a Billing Country is not set on a customer's account, which is very common with manual subscriptions and invoices, then the customer's **Account Country** will be used to determine which email variant to send a customer.

### Complex Example

Let's put the hierarchy of Audience Criteria behavior into a few practical examples.

A merchant has one (1) plan and four (4) business entities that they maintain on their single Recurly site. Their plan is called Standard and their entities are ACME INC (which is their site default entity), ACME US, ACME EU, and ACME UK. They have a default email template for all emails, and have created four (4) additional template variants for each of their email templates on Recurly; three (3) reflecting their alternate business entities and one (1) reflecting the their plan. Let's use the New Subscription email template as an example. The Audience Criteria for each of their template variants for the New Subscription email template is as follows:

**New Subscription**

* **ACME INC-** No Audience Criteria because it is configured as the default template variant
* **ACME US-** Account Country and Billing Country = United States, Mexico, Business Entity= ACME US
* **ACME EU-** Account Country and Billing Country = France, Germany, Italy, Spain, Business Entity= ACME EU
* **ACME UK-** Account and Billing Country = United Kingdom, Business Entity= ACME UK
* **Standard Plan-** Plan = Standard

There are seven (7) customers we are going to focus on to showcase different scenarios of how the New Subscription template assignment will send to a given customer.

**Customer Accounts and Scenarios**

* **Anne Smith-** Account and Billing Country in the US, no business entity override on her account
  * Anne Smith will receive the ACME US email variant for the New Subscription email template

`This is because both of Anne's addresses are located in the United States, and she has no business entity account level override. `

<br />

* **Gary Johnson-** Account Country in United Kingdom, Billing Country in Germany, no business entity override on his account
  * Gary Johnson will receive the **ACME EU** email variant for the New Subscription email template

`Gary does not have an overriding business entity on his account, and he meets the criteria to receive both the ACME EU and ACME UK email variants given his account address in the UK and his billing address in the EU. When this happens, Recurly's attribute hierarchy will choose the Billing Country to determine which variant to send a customer. `

<br />

* **Pete Clark-** Account Country in Germany, Billing Country in United Kingdom, account level business entity override set to ACME INC
  * Pete Clark will receive the **ACME INC** email variant for the New Subscription email template

`Although Pete meets the criterion to receive both the ACME EU and ACME UK variants, his address locations are irrelevant in determining which variant he should receive, since he has an overriding business entity set on his account. Business Entity is at the top of the hierarchy in determining which variant to assign a customer. `

<br />

* **Mary Lee-** Account Country in France, no Billing Country, no business entity override on her account
  * Mary Lee will receive the **ACME EU** email variant for the New Subscription email template

`Since Mary does not have an overriding business entity set on her account, and does not have a Billing Country in a different location from her Account Country, she will receive the ACME EU email variant since she meets that variant's Account Country criteria. `

<br />

* **Stephanie Jones-** Account and Billing Country set to Australia, no business entity override on her account
  * Stephanie Jones will receive the **ACME INC** email variant for the New Subscription email template

`Stephanie lives in Australia, which is outside the geographic specifications of subscribers automatically assigned to any of the alternate business entities and email template variants. Because her account and billing addresses do not meet any of the criteria for receiving an alternate email variant, and there is no overriding business entity set on her account, she will receive the default email template variant. `

<br />

* **Calvin Charles-** Account Country and Billing Country in Australia, account level business entity override set to ACME UK
  * Calvin Charles will receive the **ACME UK** email variant for the New Subscription email template

`Charles does not have billing or account addresses that would meeting the location-based attributes of any of the alternate email variants, but he does have an overriding business entity assigned on his account. This means that he will always receive the email variants for the ACME UK entity, so long as the ACME UK entity is set as an attribute on one of the merchant's email variants. `

* **David Peterson-** Account Country in Germany, Billing Country in United Kingdom, account level business entity override set to ACME INC, Plan is set to 'Standard'
  * David Peterson will receive the **Plan** email variant for the New Subscription email template.

`Although David meets the criterion to receive other email variants, the Plan Acceptance Criteria is the first in the hierarchy and anything after that will not be used to determine which variant to send.`

<br />

## Header and Footer templates

Merchants can make up to 20 total header templates and 20 total footer templates. These templates are typically used to communicate organization information like company or subsidiary name, location, contact information, and logos.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/1bc450d16b284b544de39bd4864fc692fa03f3ee438636e456805f5ce478f81a-Screenshot_2024-12-09_at_8.43.18_PM.png" />

Header and Footer templates do not have Audience Criteria. You can apply header and footer templates directly on each email template variant. If you do not set specific header/footer configurations on an email template variant, the default header and footer templates will be automatically applied. You can change an email template's header/footer configurations at any time.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/84836ea3a8b5bb0f16b30b37556a894d242cd09338fb3bc16a1c9dc2d62a7361-Screenshot_2024-12-09_at_8.40.46_PM.png" />

If you delete an alternate header or footer template, the default header or footer template will be automatically applied to any email template variant that was using that deleted header and/or footer.

# Editing an alternate email template

To edit any email template variant within a given email template, including the default variant, hover over the ellipses in the row of the template variant want to edit. That will take you to the edit page for the given template variant. Make sure to press "Save Changes" before navigating away from the screen to ensure any changes you make are applied. All edits will take effect on forward-moving emails generated after your edits have been successfully saved.

# Deleting an alternate email template

Default template variants are not able to be deleted. Default templates and all of its variants can be disabled at any time, however. To delete an alternate email template, hover over the ellipses in the row of the email variant you would like to delete, press delete, and confirm that you would like to proceed. This action is irreversible. Once deleted, there is no way to recover that variant. You can also delete a template variant when editing the individual variant itself, on the bottom right side of the page.

If you decide to delete an alternate email template that is enabled and has Audience Criteria set, the customers who would have receive that template based on the Audience Criteria attributes they met will receive a different template variant whose criteria they meet, otherwise they will receive the default email variant.