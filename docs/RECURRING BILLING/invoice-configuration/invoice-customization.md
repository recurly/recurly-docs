---
title: Invoice template customization
excerpt: >-
  Customize your invoices to reflect your brand and meet diverse business needs
  with Recurly’s Invoice Template Customization feature.
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

Recurly's invoice template customization empowers you to effortlessly craft and customize multiple invoice templates, catering to diverse business scenarios. Whether managing multiple entities within your organization or issuing distinct invoices featuring unique logos, company details, and specific rules, this feature offers unparalleled flexibility. It allows seamless adaptation to the evolving requirements of both your business and customers.

# Key benefits

* **Branding consistency:** Customize invoices with your company’s logo and details to ensure a uniform and professional presentation..
* **Flexibility and control:** Create multiple templates to cater to different business entities or customer segments, each with its own set of rules and parameters.
* **Efficiency and scalability:** Streamline your invoicing process as your business grows, without compromising on the quality or clarity of communication with your customers.

# Key details

## Create and assign invoice templates

#### Default template vs. alternate template

* **Default template:** This is the invoice template that will automatically be applied to all accounts unless you manually select an alternate option to assign to an Account. The default template is pre-configured with the company information displayed within Site Settings. However, it is not a rigid format; you can still leverage the customization features to modify the default template according to your needs.
* **Alternate template:** Our system offers a versatile approach to invoice templates, catering to diverse business needs. Initially, you will find a default template, pre-configured with your company's information as set in the Site Settings. This serves as an immediate solution for standard invoicing needs. Additionally, you have the flexibility to create multiple custom templates. These templates can incorporate any of the newly added features and are adaptable to various scenarios or customer segments. Once multiple templates are created, you can select one as your preferred default template. This flexibility is especially useful for businesses with different billing entities or those requiring varied invoice presentations for different customer groups.

## Custom header & footer images to your invoices

#### Features

* **Custom header image:** Personalize your invoices further by adding a unique header image to each invoice template. This could be your company’s logo or any other image that aligns with your brand. Each template can have its own distinct header image.
* **Custom footer image:** Similar to the header, you can also add a unique footer image to each invoice template. This could be used for additional branding, legal disclaimers, or other important information.

#### UI features

* **Create invoice templates:** This feature allows you to design and create one or more alternate invoice templates. This is especially useful if you have different business units or customer segments that require distinct invoicing formats.
* **Preview modifications:** Before saving, you can preview the changes made in invoice templates. This ensures that the invoices will appear exactly as you intend when they are sent to customers.
* **Assign templates to accounts:** Our system allows you to tailor the invoicing experience for each of your customers by assigning specific invoice templates to their accounts. This feature enables you to send invoices that are styled uniquely, reflecting the individual relationship you have with each customer. To assign these customized templates, you'll need to navigate to the Accounts page. Here, you can edit and set the desired template for each customer account, ensuring that each client receives an invoice that best suits the nature of your business interactions with them.
* **Hide line item dates:** For a cleaner look, you have the option to hide line item dates and zero-dollar line items on invoices, making the invoice easier to read and more focused on key information.
* **Navigation and sorting:** The “Invoice Templates” tab is easily accessible from the left-side navigation panel in the window. Within this tab, you can view all your templates.

#### API & UI features

* **Assign and reassign invoice templates to accounts:** Through both the API and UI, you can assign a specific invoice template to an account, change the assigned template, or revert to using the default template for an account. This gives you the flexibility to manage how individual customers are invoiced.
* **View template assignment:** For any given account, you can easily view which invoice template is currently assigned, ensuring clarity in your invoicing process.

#### API features

* **List accounts per template:** Through the API, you can retrieve a list of all customer accounts that are assigned to a specific invoice template. This is useful for auditing and managing your invoicing at scale.

## Merchant business address

#### Overriding company details

* This feature allows you to customize the company address that appears on a specific invoice template. By default, the address configured in your Site Settings will be used. However, if you need to display a different address on certain invoices (perhaps for different business units or legal entities), this feature provides that flexibility. It’s important to note that this overridden address is for display purposes on the invoice only and does not affect tax calculations, which continue to use the address in Site Settings.

Invoice Customization provides the ability to create and tailor multiple invoice templates to suit various business use cases that would require the information and formatting of an invoice sent to one account to be different to that sent to another. For example, if your organization has several entities within it, you can now send out varying invoices with unique logos, company information (e.g. address, entity name,) or rules and parameters around certain fields that are present within a given invoice. This new capability will help support your ability to scale and adapt to the changing needs of your business as well as your customers’. 

# Creating a new invoice template

1. **Navigate to Invoice Templates Tab**
   * Go to Configuration in your Recurly Admin Console.
   * Select the Invoice Templates tab (previously displayed as Invoice Settings).

2. **Create a New Template**
   * Click the “Create Invoice Template” button at the top-right hand of the window.

3. **Fill in Template Information**
   * Enter the required field information and any other fields you would like to configure within your new template.

4. **Preview the Template**
   * Press “Preview Template” to see a sample of what the invoices will look like when sending out the selected invoice template to Accounts. This Preview will contain fake invoice data aside from the fields you configured for the template.

5. **Save the Template**
   * Select “Save Changes” to ensure the successful creation of the new invoice template.

# Associating an invoice template to an account

1. **Access Account Information**
   * Navigate to the Accounts section in your Recurly Admin Console.
   * Select the desired account.

2. **Edit Account Information**
   * Click Edit in the Account Information box.

3. **Select Invoice Template**
   * Scroll down to the “Invoice Template” section.
   * From the drop-down list, select the desired Invoice Template you would like to assign for that specific Account.

4. **Save Changes**
   * Click Save to apply the new template to the account.

# Hiding line item dates on an invoice template

1. **Navigate to Edit Template Screen**
   * Follow steps 1-3 from "Creating an Alternate Invoice Template" to navigate to the editing screen of an invoice template.

2. **Configure Line Item Dates**
   * Under the “Body Section,” select the box next to “Hide line item dates” to hide the line item dates on this specific invoice template.

3. **Save Changes**
   * Click Save to apply the changes to the template.

# Hiding Zero Dollar Line Items on an Invoice Template

1. **Navigate to Edit Template Screen**
   * Follow steps 1-3 from "Creating an Alternate Invoice Template" to navigate to the editing screen of an invoice template.

2. **Configure Zero Dollar Line Items**
   * Under the “Body Section,” select the box next to “Hide zero-charge line items” to hide the zero dollar charge line items on this specific template.

3. **Save Changes**
   * Click Save to apply the changes to the template.

# Upload custom header and footer images

1. **Navigate to Edit Template Screen**
   * Follow steps 1-3 from "Creating an Alternate Invoice Template" to navigate to the editing screen of an invoice template.

2. **Upload Header Image**
   * Within the “Header Section,” click to upload a logo. Acceptable file types are PNG, JPG, and GIF with a maximum size of 256 KB.

3. **Upload Footer Image**
   * Within the “Footer Section,” click to upload an image. Acceptable file types are PNG, JPG, and GIF with a maximum size of 256 KB.

4. **Save Changes**
   * Click Save to apply the new images to the template.

# Override merchant business address on an invoice template

1. **Navigate to Edit Template Screen**
   * Follow steps 1-3 from "Creating an Alternate Invoice Template" to navigate to the editing screen of an invoice template.

2. **Override Company Details**
   * Within the “Header Section,” select “Customize invoice display address,” fill in the required fields and any additional fields you would like to have included in the address.

3. **Save Changes**
   * Click Save to apply the new address to the template.

Please note that these step-by-step processes are designed to guide you through each feature of the Invoice Template Customization in Recurly, ensuring that you can effectively and efficiently tailor your invoices to meet your specific business needs.

# FAQ

* **Q: Who can leverage this feature?**\
  A: Anyone on the Pro or Elite plans can utilize this feature to customize your invoice templates.

* **Q: Is it an added cost?**\
  A: This feature will be included in Pro and Elite plans. To request to upgrade to either of these plans, please reach out to your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) for more details.

* **Q: Can Invoice Customization be leveraged via API?**\
  A: Invoice customization is supported on both versions of our API- V2, and V3. While configuration and setup of templates is not available via API, you are able to assign and reassign a custom template to each of your accounts.

* **Q: Is there a limit on the amount of templates I can create?**\
  A: Yes, currently you can create up to 10 alternate templates.

* **Q: Is there anything I need to do to turn this feature on and begin using it?**\
  A: No, this feature will be automatically enabled for the Recurly Admin profile on qualifying plans.

* **Q: Will I lose my current invoice settings if I change Recurly plans?**\
  A: No, the Invoice Settings page will still exist within invoice capabilities. The page will now be accessible through the Invoice Templates tab by clicking on “Invoice Settings” at the top-right of the screen. The pre-existing configurations will not be changed.

* **Q: Will customizations made on invoice templates also update email template content?**\
  A: No, you need to make any desired changes to the email content directly in the appropriate email template(s). The email will include the invoice reflecting your custom configurations as a PDF attachment.

* **Q: If I choose to override the business address from Site Settings on an invoice template, will taxes be adjusted to the new “Billed From” address?**\
  A: No, at this time if you choose to override the entity address on an invoice template, that change will only reflect on invoices sent out using that template. The business address that is configured for your site in Site Settings will be the address used for tax purposes.

* **Q: Does changing or assigning a new invoice template change existing invoices on an account?**\
  A: No, only invoices generated after an invoice template has been assigned to an account will use the newly assigned invoice template. Already existing invoices on the account will not be updated to the new template and will be left as-is for auditing purposes.
