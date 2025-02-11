---
title: Audience segmentations
excerpt: >-
  Enhance your customer communications with Recurly's Audience Segmentations.
  Create bespoke email templates tailored to specific customer groups based on
  their billing or account country codes, ensuring precision in your messaging.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

### Required plan

This feature or setting requires an **Elite plan** and enablement by Recurly Support. 

# Definition

Recurly's Audience Segmentation lets merchants craft alternate versions of the Payment Confirmation and New Subscription email templates. This function ensures that tailored email content reaches specific subsets of customers, defined by their billing or account country codes.

# Key benefits

* **Targeted messaging**: Deliver content tailored to your customers by segmenting your audience based on their billing or account country codes.  
* **Stay compliant**: Seamlessly communicate any country or region-specific regulatory requirements, ensuring alignment with compliance mandates.  
* **Enhanced engagement**: Personalized emails often result in higher open rates, fostering better engagement with your audience.  
* **Streamlined process**: With in-built multi-locale support, establish your segment once and watch as Recurly sends locale-specific templates to the right audience.  
* **Adaptable tools**: Modify, delete, or add to your templates with ease, providing an agile communication toolkit for your business.

# Key details

## Why create an audience segment on an alternate email template?

Messages tailored to individual audiences often see better engagement. For scenarios like conveying region-specific regulatory requirements, it's essential that the correct group of customers receives the necessary information. An alternate email template with a defined audience segment ensures that the right customers get the tailored messaging, while others continue to receive your standard content.

## Creating alternate email templates

Recurly's Audience Segmentation feature is integrated with two primary email templates: New Subscription and Payment Confirmation. Each has a default version, but merchants can design an alternate version targeting a specific audience. When designing:

* Remember, only the New Subscription and Payment Confirmation templates support audience segments.
* Define criteria in the "Audience" section. If a customer meets just one criterion, they receive the alternate version.
* Customers outside the defined audience segment criteria will get the default email template.

## Audience criteria

* Define at least one criterion in the Audience section.
* The segment builder operates on "OR" logic – if a customer meets one criterion, they receive the alternate template.

## Locale Support

The audience segment of an alternate template supports all locales. After setting up your segment:

1. Customize the content per locale.
2. For example, if targeting the UK, Italy, and Sweden, first modify the content for the UK audience in English. Then, use locale support for Italian and Swedish translations.
3. The alternate template reaches customers in the defined countries, with the message in the set language for that region.

## Adding a PDF Attachment

Attach a PDF to your alternate email templates. For every locale on the alternate template, Recurly supports a unique PDF attachment, ensuring your message is consistent across languages.

## Your new alternate email template

After creation, your new template appears under the Email Templates section. From there, options include previewing the HTML, editing, renaming, or deleting the template.

<Image align="center" className="border" border={true} src="https://files.readme.io/a922248-Screen_Shot_2022-12-05_at_3.58.28_PM.png" />

## Renaming templates

Hover over the ellipsis next to the desired alternate template and select "Rename". Remember to save your changes.

<Image align="center" className="border" width="65% " border={true} src="https://files.readme.io/c0e4aa6-Screen_Shot_2022-12-05_at_9.07.12_PM.png" />

# How to create an alternate template

1. Navigate to the headers of the Payment Confirmation and New Subscription email templates.
2. Click on the "Options" button, then select "New Email Template".
3. Assign a unique name to your alternate template and save.
4. Start customizing the template. This includes the subject line, email body, and audience criteria.
5. For activation, ensure at least one criterion is defined in the Audience section.

# How to add audience criteria

1. Click "Add Attribute" located near the screen's bottom.
2. Choose the desired attributes.
3. Define your country criteria and save.\
   Once saved, your segment is active, and the alternate template is ready for deployment.

# How to upload a PDF attachment

1. In the PDF section, click "Choose File".
2. Upload your document (max 512 KB).
3. On activation, the attached PDF will accompany emails sent to customers.
