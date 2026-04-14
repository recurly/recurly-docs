---
title: Multiple business entities
excerpt: >-
  Managing all of your organizations’ business entities from one Recurly site
  simplifies tax calculation and reporting, ensures customers receive invoices
  from the correct business entity, and allows businesses to scale with
  efficiency and flexibility.
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    Managing all of your organizations’ business entities from one Recurly site
    simplifies tax calculation and reporting, ensures customers receive invoices
    from the correct business entity, and allows businesses to scale with
    efficiency and flexibility.
  robots: index
next:
  description: ''
---
# Overview

### Required plan

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

# Definition

Business Entities can be configured on Recurly to reflect what an entity means for your specific organization. An entity on Recurly can reflect a legal entity, distinct business unit, brand or subsidiary, geographic location or headquarters, or warehouse distribution center. By setting up your business entities on one Recurly site, you can guarantee that all of your customers receive the appropriate communications and subscriptions from your company and its entities at any given time. This setup not only makes scaling your business more efficient and compliant, but also simplifies maintenance. You can create as many entities on your Recurly site as needed, updating, removing, and adding entities as your business needs change.

<Image align="center" border={true} width="80% " src="https://files.readme.io/06cfb5f7a4340dea7a32921c5b7c54aa49ce8d897bda4eaa12b6001ff157dd6d-image.png" className="border" />

# Key benefits

* **Dynamic entity management:** Enjoy the flexibility to add, remove, and update business entities as your business evolves. Define business entities as they are applicable to your business, whether an entity means a distinct brand, subsidiary, geographic location, or legal entity.
* **Consolidate customer accounts:** Maintain singular customer accounts subscribed to one or more of your business entities at a time, all within one Recurly site.
* **Tailored customer communications:** Cater to different customer segments with customized invoices and emails based on the Business Entity they are subscribed to, enhancing customer satisfaction and brand transparency.
* **Automated, accurate tax treatment:** Ensure tax calculation, tax reporting and filing, and tax registration information is configured appropriately for each unique business entity on your single Recurly site.
* **Analyze entity performance:** Use the Business Entity Overview dashboard to track and compare key performance metrics across each of your entities, empowering you to make informed decisions to grow your business in each of your markets.

# Key details

## Entity-specific merchant email addresses

Maintaining an accurate [Billing Contact Email](https://docs.recurly.com/docs/site-settings#email-settings) address is crucial as this is the email address used for display on all Recurly invoices/receipts and acts as the 'from' address for all transaction-related customer communications. By correctly specifying this email address for each of your entities, you are ensuring a seamless, prompt, and professional correspondence with your customers, further enhancing their trust and experience with your business.

You can set a unique billing contact email address for each alternate entity if you wish based on your organization’s needs. This will ensure that customers will always see the correct merchant email address based on the appropriate business entity applied to their invoice or account. If you do not set unique email addresses on any of your alternate entities, the billing contact email address used will fall back to the one entered on the [Site Settings](https://docs.recurly.com/docs/site-settings#email-settings) page. Your Site Default Entity will always use the billing contact email address configured on the Site Settings page. You can also set a billing contact email address on individual [email templates](https://docs.recurly.com/docs/site-settings#email-settings), which will override any site or business entity settings.

The billing contact email address is used for customer-facing materials including:

* The sender “from” email address on emails sent to customers
* The email address displayed on the PDF invoice attachment customers receive within emails
* Invoice renderings on hosted pages
* Hosted invoice page's cancel authorization copy

<Image align="center" border={true} width="80% " src="https://files.readme.io/9f3208f21ddc550c979c27d904490950e1a23a21c07fc8e2d8e0fbb035d14718-image.png" className="border" />

You can preview the email address that will be used on an invoice by clicking the “Invoice Preview” button when creating/modifying a subscription or one time purchase. Another way to know which billing address will be used for an invoice or email sent to a customer when you have multiple entities configured is to check the entity a customer has assigned to their account, or subscription(s). If there is no business entity override set on a given account or assigned to a subscription, you can check the customer’s billing or account address depending on your site configurations, to see which entity they would receive on an invoice via automatic entity assignment.

Billing contact email addresses are only configurable via the Recurly Admin UI.

## Automatic assignment of entities by Subscriber Location

### Behavior

Automatic assignment is the default method of entity application to invoices for all customers at the time of their next billing event. This assignment is based on the billing address of the customer's account at the time the transaction takes place. If a customer has manual billing set up, or if your site is configured to use the account address for all invoices, then the account address will be used as the "BILL TO" address on the invoice.

## Subscriber Locations

The logic behind the automatic assignment of entities from the "BILL TO" address of a customer is based on the entity's configured subscriber locations. These locations are an optional configuration setting on alternate business entities. You can add specific countries to the entity to create rules for automatic assignment. Each unique country can only be added to a single Subscriber Location/entity at a time. You can adjust the countries within your Subscriber Locations at any time, but changes will reconfigure the entity assigned on any transaction if a customer's country location matches a country that has been moved to a new entity.

If you choose not to add any regions to any or all of your alternate entities' Subscriber Locations, all customers will be "automatically" assigned to the Site Default Entity, which serves as the site's fallback entity for assignment.

After subscriber locations are set, customers meeting location criteria will begin to receive invoices from the corresponding business entity at the start of their next billing period. This applies to new _and_ existing subscribers, unless their subscription(s) are assigned to a specific business entity, or their account has an overriding business entity assigned.

### How does it work?

For example, if you create an entity called "Acme Inc. Western Europe" and add Germany, Italy, France, Spain, Ireland, and England to its Subscriber Locations, customers whose "BILL TO" address is in one of those countries will receive the "Acme Inc. Western Europe" entity's invoice address settings and origin tax address.

If you set up another entity called "Acme Inc. Eastern Europe" with Poland and Hungary in its Subscriber Locations, customers with a billing address in these two countries will automatically have the "Acme Inc. Eastern Europe" entity applied to their invoices.

If your headquarters serves customers globally, you can set it up as your Site Default Business Entity on Recurly, which will serve as the fallback entity for customers who are not covered by a subscriber location within another entity.

### How can I see what entities are applied to invoices when using automatic assignment?

You can view this information on the individual invoices on a customer's account. This view will display the corresponding entity on each transaction associated with their billing address at a given point in time. You can also use an API query on the Invoice object to identify which entity was associated with a specific invoice.

## Entity-level invoice treatments

In addition to setting your entity's company information such as company name and contact number, invoice display and tax addresses, and tax ID numbers, you can also set entity-level invoice display settings for entity prefix, EU country sequencing, header and footer logo images, notes to the customer, and terms and conditions.

Setting specific invoice treatments for each of your entities helps in ensuring each business entity's contact information, logo presentation, desired notes for respective subscriber pools, and entity-specific legal communications and mandate information are sent to the right customers at the right time.

#### Invoice Number Settings: Invoice Sequencing

Merchants can choose to create a unique invoice sequence or use the shared sequence for each business entity.

#### Invoice Number Settings: Entity Prefix

Merchants will be able to choose whether or not to enable entity-specific invoice sequencing directly on each of their business entities.

* An entity prefix is an alphanumeric of 4 characters or less that is prepended to the sequential number.
* When adding an entity prefix, the sequence will start at 1000 and increment by 1.

Note: Changes to invoice numbering can potentially disrupt reconciliation and gateway processing. For more detailed information, visit [gateway specific information for invoice numbers](https://docs.recurly.com/recurly-subscriptions/update/docs/gateway-specific-information-for-invoice-numbers).

Contact [support](mailto:support@recurly.com) to have entity invoice prefix added to your account.

#### Invoice Number Settings: Country Sequencing

By default, Recurly uses a single sequence for invoice numbers across your site, adhering to the European Commission's invoicing rules. However, certain EU member states mandate a unique sequence for their country. To cater to this, we offer the Country Sequencing feature. This allows merchants to establish distinct sequences for each EU member state.  Merchants can enable or disable this feature by clicking the appropriate radio button.

<Image align="center" border={true} src="https://files.readme.io/a95b40221baa014f79f0dcd3c382557331e6cbae1c3643c0b7495d4d42a9e321-AltBizEntityMessage.png" className="border" />

#### Entity invoice images

Images for the invoice’s header and footer allows merchants to determine what logos are displayed on an invoice sent to their customers. Footer images are often used to display other custom communications to customers, or secondary logos.

<Image align="center" border={true} width="80% " src="https://files.readme.io/9b8334250dba359821af19442ee02910a3dae837c27e9e31f0706b73cd75ed5a-image.png" className="border" />

#### Entity charge invoice notes

You can use the Invoice Settings notes or you may select to override those notes and have invoice notes specific to the Business Entity.

**Note to Customer**

Customer Notes is another notes section available to you for any details you would like to add. This section is ideal for notes on invoice details or including a special message for the customer, like "thanks for your business".  Invoice notes provide flexibility to allow you to add relevant information to the invoice that may be specific to local invoice compliance needs. Notes such as Authorized Dealer, delivery note number, type of supply, intra-community supply, goods status, Israel invoice model, and Israel special note.

This section will only show on an invoice if there is text in the field and does not display a section title. Customer Notes are displayed at the bottom of the invoice in larger font than the Terms and Conditions.

**Terms and Conditions**

Terms and Conditions is a notes section available to you for any details you would like to add. The section is ideal for notes about payment or contract terms. The section will only show on an invoice if there is text in the field. While Recurly provides the ability to set notes for invoices at the entity level, you can opt to leverage general notes to be displayed on invoices sent to customers by choosing to use the "Invoice Settings" page notes.

<Image align="center" border={true} width="80% " src="https://files.readme.io/91182c3da5fd1b14818b1bc2fcd0582284d3e7a40c8bf805c74ba34787cc4270-image.png" className="border" />

#### How do Entity-specific invoice treatments work with Recurly’s existing Invoice Customization feature?

On your site’s [Invoice Templates](https://docs.recurly.com/docs/invoice-customization#instructions-for-use), any custom invoice display addresses, and header/footer images applied to a given template will still be applied to invoices sent to accounts with a customized invoice template assigned. If you decide you would like to use the invoice treatments applied at the entity level instead, you can select the first radio button option in the invoice template “edit” page, where you can choose to use the address/images applied on the entity level, rather than apply the custom invoice settings on the invoice template object. You can change this behavior whenever you want and as frequently as you want. Any updated settings will only be applied to forward-moving invoices.

New invoice templates created on your site will have the options for using the entity-level invoice addresses, and header and footer images selected automatically. Again, you can change these settings at any point in time.
Note: At this point in time, we do not support version history for images at the entity level. This means that if an invoice is posted, and you decide at a later time to edit that invoice for any reason, the newly-generated invoice will be re-sent to the customer with the image that is currently applied on the entity level. This also applies to refund/credit invoices.

#### How do Entity-specific Notes to Customers and Terms and Conditions work with Recurly's existing invoice notes set on the Invoice Settings page?

On your site’s [Invoice Settings](https://docs.recurly.com/docs/invoice-settings#terms-and-conditions) page, any custom invoice communications including the “Notes to Customer” and “Terms and Conditions” will still be applied to all invoices sent to all customers across your site, unless you decide to select the first radio button option on any of your business entities to use the entity’s charge invoice settings instead. You can change this behavior whenever you want and as frequently as you want. Any updated settings will only be applied to forward-moving invoices.

<Image align="center" border={true} width="80% " src="https://files.readme.io/da58122d9ba062b736399d4d39ae44e64ccb2b6cad8c2f7af0e2bac57d213920-image.png" className="border" />

If you decide to create a new alternate entity (a non-Site Default Entity) and there are no notes to the customer or terms and conditions added on your Invoice Settings page, the option to use the entity-level notes and terms and conditions will be selected automatically. You can choose to use the notes from Invoice Settings instead at any given point in time.

<Image align="center" border={true} width="75% " src="https://files.readme.io/2b954e8-Screenshot_2023-10-25_at_11.37.24_AM.png" className="border" />

Merchants on Recurly’s Starter and Professional plans will continue to have notes to the customer and terms and conditions supported on the Invoice Settings page, and not at the entity level, as multiple entities are not supported on these plans.

## Apply an entity to a customer’s subscription

If you have multiple brands, or customers that subscribe to more than one of your business entities at a time, you should leverage assigning business entities to individual subscriptions within an account. This allows for consolidated customer account management across each of your subsidiaries/business entities.

Currently, Recurly supports assigning entities on the subscription object within Recurly's Admin UI, and via Recurly’s API [V3](https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_subscription). Assignment for the initial purchase call on a subscription is only supported via API. Subscription level entity assignment is not available for purchase calls made on Recurly Checkout.

To assign a business entity to a subscription upon creation in the Recurly Admin UI, select your desired "Override Business Entity" on the subscription itself, and press save. If you wish to change a business entity on an existing subscription, you may do so, however changes to Business Entities on the Subscription object can only take place on "Next_Bill_Date" or "Subscription_term". To assign a subscription upon [creation via API](https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_subscription), set the subscription's business_entity_id. To [change a subscription's assigned entity via API,](https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_subscription_change) change the subscription's business_entity_id, and the new entity will be applied upon the next billing renewal event.

**Changing the Business Entity on the subscription is not available for immediate subscription changes.**

<Image align="center" border={true} width="75% " src="https://files.readme.io/055d80c92324ec381d8c0f07e9e7118bc7357d6b86aa69583e6e05ca077a5dad-Screenshot_2025-03-12_at_4.44.52_PM.png" className="border" />

**When scheduling subscription changes for the next bill date, or the next term renewal, however, you are able to change the Business Entity on the subscription.**

<Image align="center" border={true} width="75% " src="https://files.readme.io/bd3a9f1e3793369725930fd3f4c05a283806f930fd83dbee6cd94fa48af46e27-Screenshot_2025-03-12_at_4.45.15_PM.png" className="border" />

<Image align="center" border={true} width="75% " src="https://files.readme.io/d06d479f1fd7879eb4a38b65321d5d9efa98e94f9a2c6400d2926bb5391dd833-Screenshot_2025-03-12_at_4.45.34_PM.png" className="border" />

Entities assigned to subscriptions takes precedence over location-based subscription assignment and business entity overrides applied to a customer's Account.

## Apply an overriding entity to a customer's account

If you prefer static entity assignments on customer ACCOUNTS, where all subscriptions and purchases for a customer will always be assigned to a specific entity, you can opt to apply an overriding entity to a customer's account(s).

> **Tip:** If you are integrated with NetSuite, Recurly recommends applying entities at the ACCOUNT level rather than relying on automatic assignment. This approach ensures that entity mapping for customer accounts remains consistent between Recurly and NetSuite, as entities are mapped at the time a customer is created on NetSuite.

You can apply an overriding entity at the ACCOUNT level either via the admin console or API V2/V3.

To apply an overriding entity via the Recurly user interface, navigate to a specific customer account, go to the Edit Account Information page, and select an "Overriding Business Entity" from the dropdown menu provided in the field.

<Image align="center" border={true} width="75% " src="https://files.readme.io/e74cd0e-image.png" className="border" />

Once you save the changes made to the selected customer account with an overriding business entity, all future transactions of that account will be assigned to the corresponding business entity. This assignment persists until you either change the overriding entity or revert that account back to automatic assignment logic applied at the invoice level. Remember, the assigned overriding business entity will be applied at the start of the next billing cycle once your changes have been applied to the account. You cannot switch a customer’s business entity mid-billing period.

### View the overriding entity assigned to an account

You can see the business entity assigned at the account level for customers with an overriding business entity applied directly on their account page, under "Account Information". You can also do an API query on the Account object to identify which entity is associated with an account, or, for accounts using automatic assignment, an API query on the Invoice object to see which entity was applied to a specific invoice.

<Image align="center" width="75% " src="https://files.readme.io/74b18a2-image.png" />

## Account hierarchy and entities

If you have customers with a parent/child account hierarchy, the application of business entities for transactions depends on the billing preferences of the parent/child relationship.

* If the "Bill all charges to Child Account" option is selected for an account, each child account in a given hierarchy will receive its own invoices. They will thus follow the same entity assignment behavior explained above—either automatic assignment based on Subscriber Location at the invoice level, assignment applied to a given subscription, or an account-level overriding entity applied so all transactions for that customer occur under the overriding entity.
* If the "Bill all charges to Parent Account" option is selected for an account, invoices from a child account's charges sent to the given parent account will be assigned to whichever entity is assigned to the parent at the subscription level, account level if an overriding entity is set, or will assume the entity from automatic assignment based on the parent account's "BILL TO" address.

## Refund invoices

Refunds are inevitable. Whether a customer's entity is assigned at the invoice level using automatic assignment, or at the account level with an applied entity override, refunds work the same way.

When a customer makes a purchase, the entity assigned at the time of the transaction is considered the original entity. If a customer requests a refund and the entity assigned to their transactions or account has changed since the original purchase, the refund invoice will use the original entity's invoice display information and tax address, as well as the customer's taxable address that was  applied to the original invoice that the refund stemmed from. This process ensures the correct tax calculation for the refund and maintains invoice consistency with the original entity name and address.

## Deleting an entity from your site

You cannot delete your Site Default Entity from your Recurly site. The Site Default Entity is critical in communicating your company's customer-facing information during the invoicing process. While the SDE cannot be deleted, it can be edited.

However, you can delete any alternate entity set up on your site at any time. You can delete an alternate entity from the main list page when hovering over the ellipses for the entity of choice and selecting “Delete”, or by selecting "Delete Entity" from the "Entity Actions" dropdown on the view-page of a specific alternate entity.

<Image align="center" border={true} width="75% " src="https://files.readme.io/3d4668a-image.png" className="border" />

<Image align="center" border={true} width="75% " src="https://files.readme.io/38af1bd-image.png" className="border" />

When confirming to delete an alternate entity, you will be prompted to enter the entity code of the one you are attempting to delete. Once you enter the code successfully, that entity will be permanently deleted from your site. However, if a return is initiated, the refund invoice will still leverage the display and tax address information from the original transaction.

<Image align="center" border={true} width="75% " src="https://files.readme.io/ad195f0-image.png" className="border" />

Once you delete an alternate entity, all customers previously assigned to that specific entity as an overriding entity on their account will have their invoices assigned to the Site Default Entity moving forward, unless:

* The customer's subscriptions are reassigned to a different business entity.
* The customer's "BILL TO" address is changed to match a country included within the Subscriber Location on another alternate entity.
* The countries included in the deleted entity's Subscriber Locations are added to another alternate entity.
* The customer is manually reassigned to a specific entity at the account level (overriding business entity).

## Tax ID numbers

Tax ID Numbers (TINs) are entity-specific and used to display a business's tax registration number on invoices sent to customers. When a Default TIN/VAT number is entered on an entity, that number will appear as the last line in the merchant information shown on the invoice.

<Image align="center" width="75% " src="https://files.readme.io/258a8e1-image.png" />

Country-specific TINs replace the Default TIN/VAT number on the invoice when a customer's BILL TO address is located within a country that has a country-specific TIN configured on the given entity.

For example, if a merchant has a Default VAT number set on an entity and also has a country-specific VAT number configured for Portugal on that entity, then all customers with BILL TO addresses in Portugal will see the French merchant VAT number on their invoices instead of the merchant’s Default VAT number. Alternatively, if there are no other country-specific VAT numbers added to that entity, all customers leveraging that entity with BILL TO addresses in any country OTHER than Portugal will see the merchant’s Default VAT number on their invoices.

<Image align="center" width="75% " src="https://files.readme.io/29a94f5-image.png" />

TIN/VAT numbers will not automatically be applied across entities on Recurly. If you use the same TIN/VAT numbers across multiple entities, you need to ensure that you fill out those fields with the appropriate tax registration numbers for each entity.

## Direct Avalara accounts

If you have an integration to a direct Avalara account, you can map each of your entities from Recurly to your direct AvaTax account to report and file taxes independently for each unique entity. While Recurly only supports one unique Avalara account on a single Recurly site at a time, we provide multi-entity tax support by allowing you to map your Recurly Site Default Entity to your Avalara main company, and each alternate entity on Recurly to the corresponding sub-entities configured on your single Avalara account.

On your Avalara site, from your home page, you will see the list of companies/sub-companies within your account. Copy the unique Company Code exactly as it appears on your Avalara site, and paste it into the appropriate Company Code field in the Recurly App on the "Avalara AvaTax Settings" page to create a direct mapping for each Recurly entity to each Avalara company you manage.

If you delete an entity on Recurly, that mapping will no longer exist for the corresponding sub-company in Avalara. Maintain the mapping relationship between the two sites to ensure entity mappings are up-to-date if your entities change.

<Image align="center" border={true} width="75% " src="https://files.readme.io/ce9381d-image.png" className="border" />

## Paused subscriptions

If a customer's subscription is paused, resuming the subscription or an immediate change made to the subscription will trigger a new billing period. The subscription will no longer be paused, and the next invoice will be assigned to the entity assigned to the customer's account if an overriding entity has been applied. Otherwise, the invoice will receive the entity based on the subscriber location or the Site Default Entity if using automatic assignment logic.

## Downgrades

If you started on a Recurly Elite plan and then decide to move to a Recurly Starter or Professional plan, you will lose the ability to maintain multiple business entities on your site once your downgrade takes effect. Historic invoices leveraging various entities will remain unchanged, and refunds for invoices leveraging previously maintained alternate entities will still reflect the original entities applied. However, all invoices, subscriptions and transactions moving forward will be assigned to your Site Default Entity. All renewal, manual, immediate change, and one-time-charge invoices moving forward will receive the SDE assignment and treatments.

Should you decide to re-upgrade to an Elite plan at a future date, you will need to recreate alternate entities.

## Entity-Specific Email Templates

Recurly allows you to create up to 20 total template variations per email template type. You can ensure customers are assigned a certain variation of a given email template based on either their geographic location, or their subscription or account or invoice's applied business entity. To learn more about support for alternate email templates, view our dedicated [documentation](https://docs.recurly.com/docs/alternate-email-templates) page.

# FAQ

**Q: Can other Recurly objects, such as plans or coupons, be entity-specific?**

**A:** Objects such as plans, items and coupons can be assigned in a way that allows you to pass certain plan/item/coupon codes via API to certain customers based on specific entities. However, these objects are not limited or siloed by any specific entity in Recurly itself, you must maintain these mappings and flows in your integration.

**Q: Can purchases made from a given entity be routed to a specific payment gateway?**

**A:** This is not available through the UI. However, you can set a specific payment gateway at both the Subscription and Account levels, and thus route a given subscription assigned to a particular entity to the preferred gateway.

**Q: Can I file my taxes within Avalara or Vertex by the specific entity I have set up on my Recurly site?**

**A:** Yes, this is possible for merchants with a direct Avalara or Vertex account set up. You will need to configure the integration within your Recurly site to ensure entity/company/division codes are mapped appropriately, allowing for entity-specific filing in your tax system.

**Q: Does this feature work with Recurly revenue recognition?**

**A:** Yes, the multi-entity feature is compatible with Recurly revenue recognition. Please note that if you enable Recurly revenue recognition on your site after you've created entities, you will need to create 2 GL codes for each entity on your site.

**Q: Can I conduct entity-specific analytics within Recurly?**

**A:** Yes, there are two (2) dashboards available with entity-specific data.

* [Business Entity Overview Dashboard](https://docs.recurly.com/docs/business-entities-overview)
* [Explore- Invoices Dashboard](https://docs.recurly.com/docs/business-entities-overview#explore-invoices-dashboard)

Additionally, the Entity Code is included within the Admin UI for the Invoices - Accounts Receivable, Adjustments, Adjustments - Taxes, and Invoices - Summary exports.
