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

This feature may not be included in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Prerequisites

* A Recurly site with at least one configured business entity (the Site Default Entity is created automatically)
* Admin UI access to configure entities, invoice templates, and account settings

### Limitations

* Business entity assignment cannot take effect mid-billing period — changes apply at the start of the next billing cycle
* Changing a business entity on a subscription is not available for immediate subscription changes
* Subscription-level entity assignment is not available for purchase calls made on Recurly Checkout
* Each country can only be added to a single entity's Subscriber Locations at a time
* The Site Default Entity cannot be deleted
* Recurly supports only one Avalara account per site (multi-entity tax support is handled via sub-entity mapping)
* Merchants on Starter and Professional plans cannot configure invoice notes at the entity level

***

# Definition

Business Entities let you configure Recurly to reflect how your organization is actually structured. An entity can represent a legal entity, a distinct business unit or brand, a subsidiary, a geographic headquarters, or a warehouse distribution center.

By setting up multiple entities on a single Recurly site, you ensure every customer receives invoices, emails, and tax treatment that's accurate for the entity they're subscribed to — all without managing multiple sites. You can create as many entities as your business needs, and update, remove, or add them at any time.

<Image align="center" border={true} width="75%" src="https://files.readme.io/06cfb5f7a4340dea7a32921c5b7c54aa49ce8d897bda4eaa12b6001ff157dd6d-image.png" className="border" />

***

# Key benefits

* **Dynamic entity management:** Add, remove, and update entities as your business evolves — whether an entity means a brand, subsidiary, geographic location, or legal entity.
* **Consolidated customer accounts:** Keep a single customer account subscribed to one or more of your entities at a time, all within one Recurly site.
* **Tailored customer communications:** Send customized invoices and emails based on the entity a customer is subscribed to, improving brand clarity and customer experience.
* **Automated, accurate tax treatment:** Configure tax calculation, reporting, filing, and registration independently for each entity.
* **Entity performance analytics:** Use the Business Entity Overview dashboard to track and compare key metrics across entities, so you can make informed decisions for each of your markets.

***

# Key details

## Entity-specific merchant email addresses

The Billing Contact Email address is used as the "from" address on all transaction emails and appears on all invoices and receipts. Keeping this accurate for each entity ensures customers always see the right contact information.

You can set a unique billing contact email for each alternate entity. If you don't, the address falls back to what's configured on the [Site Settings](https://docs.recurly.com/docs/site-settings#email-settings) page. The Site Default Entity always uses the Site Settings billing contact email. You can also override all of this at the individual [email template](https://docs.recurly.com/docs/site-settings#email-settings) level.

The billing contact email appears in the following places:

* The "from" address on emails sent to customers
* The email address shown on PDF invoice attachments
* Invoice renderings on hosted pages
* The cancel authorization copy on hosted invoice pages

<Image align="center" border={true} width="75%" src="https://files.readme.io/9f3208f21ddc550c979c27d904490950e1a23a21c07fc8e2d8e0fbb035d14718-image.png" className="border" />

To preview which email address will appear on an invoice, click **Invoice Preview** when creating or modifying a subscription or one-time purchase. You can also check which entity is assigned to a customer's account or subscription to determine which billing contact email they'll see.

> **Note:** Billing contact email addresses can only be configured in the Recurly Admin UI.

***

## Automatic assignment of entities by subscriber location

### How automatic assignment works

By default, Recurly automatically assigns a business entity to each invoice based on the customer's "BILL TO" address at the time of the transaction. If a customer has manual billing enabled, or if your site is configured to use the account address, that address is used instead.

### Subscriber locations

Subscriber Locations are an optional configuration on alternate entities that let you define which countries should trigger automatic assignment to that entity. Each country can only be added to one entity's Subscriber Locations at a time.

If no countries are added to any alternate entity's Subscriber Locations, all customers are automatically assigned to the Site Default Entity, which acts as the site-wide fallback.

Once Subscriber Locations are configured, affected customers will start receiving invoices from the corresponding entity at the start of their next billing period. This applies to both new and existing subscribers, unless their subscription or account has a specific entity already assigned.

### Example

Say you create an entity called "Acme Inc. Western Europe" and add Germany, Italy, France, Spain, Ireland, and England to its Subscriber Locations. Any customer with a "BILL TO" address in one of those countries will automatically receive invoices from that entity.

If you also create "Acme Inc. Eastern Europe" with Poland and Hungary in its Subscriber Locations, customers in those two countries will be assigned to that entity instead.

Your global headquarters can be set as the Site Default Entity — serving as the fallback for all customers not covered by any Subscriber Location.

### Viewing entity assignments

You can view entity assignments on individual invoices within a customer's account. You can also query the Invoice object via API to identify which entity was applied to a specific invoice.

***

## Entity-level invoice treatments

In addition to configuring company information (name, contact number, display and tax addresses, and Tax ID numbers), you can set the following invoice display options per entity:

* Entity prefix for invoice numbering
* EU country sequencing
* Header and footer logo images
* Notes to the customer
* Terms and conditions

These settings ensure each entity's contact information, legal language, and branding reach the right customers consistently.

### Invoice number settings: invoice sequencing

Each business entity can use either a unique invoice sequence or your site's shared sequence.

### Invoice number settings: entity prefix

An entity prefix is an alphanumeric string of four characters or fewer that's added before the sequential invoice number. When enabled, the sequence starts at 1,000 and increments by one.

> **Note:** Changes to invoice numbering can disrupt reconciliation and gateway processing. See [gateway-specific information for invoice numbers](https://docs.recurly.com/recurly-subscriptions/update/docs/gateway-specific-information-for-invoice-numbers) for details. Contact [support@recurly.com](mailto:support@recurly.com) to have an entity invoice prefix added to your account.

### Invoice number settings: country sequencing

By default, Recurly uses a single sequence across your site, in line with European Commission invoicing rules. However, certain EU member states require a unique sequence per country. The Country Sequencing feature lets you set up distinct sequences for each EU member state. Enable or disable this using the radio button in the entity settings.

<Image align="center" border={true} width="75%" src="https://files.readme.io/284ef27c97ca20a094f8d08fad6567c05d6bbecc95399afc7196dad3a314c322-image.png" className="border" />

### Entity invoice images

Header and footer images let you control which logos appear on invoices sent to your customers. Footer images are commonly used for secondary logos or custom messaging.

<Image align="center" border={true} width="75%" src="https://files.readme.io/9b8334250dba359821af19442ee02910a3dae837c27e9e31f0706b73cd75ed5a-image.png" className="border" />

### Entity charge invoice notes

You can use site-level invoice notes, or override them with entity-specific notes.

**Note to customer**

Use this field to include any invoice details or a personalized message for the customer (e.g., "Thanks for your business"). This section is also useful for local compliance notes, such as authorized dealer status, delivery note numbers, type of supply, intra-community supply details, or Israel-specific invoice fields.

This section only appears on an invoice if text is present and does not display a section title. Customer notes appear at the bottom of the invoice in a larger font than Terms and Conditions.

**Terms and conditions**

Use this field for payment or contract terms. This section only appears on an invoice if text is present.

<Image align="center" border={true} width="75%" src="https://files.readme.io/91182c3da5fd1b14818b1bc2fcd0582284d3e7a40c8bf805c74ba34787cc4270-image.png" className="border" />

### How entity invoice treatments work with existing invoice customization

If a customer has a custom invoice template assigned, any display addresses and header/footer images on that template still apply. To use entity-level settings instead, select the first radio button in the invoice template's edit page.

New invoice templates default to using entity-level addresses and images. You can change this at any time — updates only apply to invoices going forward.

> **Note:** Image version history is not supported at the entity level. If an invoice is edited after posting, the reissued invoice will display the image currently configured on the entity — including refund and credit invoices.

### How entity notes work with site-level invoice notes

Notes configured on your site's [Invoice Settings](https://docs.recurly.com/docs/invoice-settings#terms-and-conditions) page apply to all invoices site-wide by default. To use entity-specific notes instead, select the first radio button option on the relevant entity.

You can change this setting at any time. Updates only apply to invoices going forward.

<Image align="center" border={true} width="75%" src="https://files.readme.io/da58122d9ba062b736399d4d39ae44e64ccb2b6cad8c2f7af0e2bac57d213920-image.png" className="border" />

If you create a new alternate entity and there are no notes on the Invoice Settings page, entity-level notes will be selected automatically. You can switch to using Invoice Settings notes at any time.

<Image align="center" border={true} width="75%" src="https://files.readme.io/8f3ae52660374f16a2e30c3159dd0ae99c3554a09d7db48ed36e5c38c9eb66d6-image.png" className="border" />

> **Note:** Merchants on Starter and Professional plans can configure notes only on the Invoice Settings page — entity-level notes are not available on these plans.

***

## Applying an entity to a customer's subscription

If you have multiple brands, or customers who subscribe to more than one of your entities, you can assign a business entity directly to individual subscriptions. This allows for consolidated account management across subsidiaries and entities.

Entity assignment at the subscription level is supported in:

* Recurly Admin UI
* Recurly API [V3](https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_subscription) (initial creation and changes)

> **Note:** Subscription-level entity assignment is not available for purchase calls made through Recurly Checkout.

**To assign an entity in the Admin UI:** Open the subscription, select your desired **Override Business Entity**, and save.

**To change an entity on an existing subscription:** Changes can only take effect on the `next_bill_date` or `subscription_term`. Immediate subscription changes do not support entity changes.

**To assign or change an entity via API:** Set the `business_entity_id` on the subscription object at creation, or update it via a [subscription change](https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_subscription_change). The new entity will be applied at the next billing renewal.

> **Important:** Changing the business entity on a subscription is not available for immediate subscription changes.

<Image align="center" border={true} width="75%" src="https://files.readme.io/74aaa9417dfe9867d358e0561b462816435a71241c2a245a1912d562af8505e3-image.png" className="border" />

When scheduling subscription changes for the next bill date or next term renewal:

<Image align="center" border={true} width="75%" src="https://files.readme.io/51bbc96db492cbc66e85afdc376967c8ea4bd24682429c08fb394642ba7fad53-image.png" className="border" />

you're able to change the business entity on the subscription.

<Image align="center" border={true} width="75%" src="https://files.readme.io/3be9814f06915afe9e0a5cebd70a8a527d080cbfdcac1c1d2cde7bf609649d31-image.png" className="border" />

Entities assigned at the subscription level take precedence over location-based assignment and any account-level entity override.

***

## Applying an overriding entity to a customer's account

If you want a static entity assignment — where all subscriptions and purchases for a customer always use the same entity — you can apply an overriding entity at the account level.

> **Tip:** If you're integrated with NetSuite, Recurly recommends applying entities at the account level rather than relying on automatic assignment. This keeps entity mapping consistent between Recurly and NetSuite, since entities are mapped when a customer is first created in NetSuite.

You can apply an account-level override via the Admin UI or API (V2/V3).

**To apply an override in the Admin UI:**

1. Navigate to the customer's account
2. Go to **Edit Account Information**
3. Select an **Overriding Business Entity** from the dropdown
4. Save your changes

Once saved, all future transactions for that account will use the selected entity. This assignment persists until you change it or revert the account to automatic assignment. The new entity takes effect at the start of the next billing cycle — you can't switch entities mid-billing period.

### Viewing the overriding entity on an account

The assigned entity is visible on the customer's account page under **Account Information**. You can also query the Account object via API to see the assigned entity, or query the Invoice object to see which entity was applied to a specific invoice.

<Image align="center" width="30%" src="https://files.readme.io/82155ea952e61d3c4390d86ca48b6cb2a1b1f1201ece6abb81f20d6a6c3b567d-image.png" />

***

## Account hierarchy and entities

For customers in a parent/child account hierarchy, entity assignment depends on how billing is configured:

* **Bill all charges to child account:** Each child account receives its own invoices and follows standard entity assignment — automatic (by Subscriber Location), subscription-level, or account-level override.
* **Bill all charges to parent account:** Invoices generated from a child account's charges are assigned to whichever entity applies to the parent — subscription-level, account-level override, or automatic assignment based on the parent's "BILL TO" address.

***

## Refund invoices

When a refund is issued, the refund invoice always uses the entity, invoice display information, and tax address from the original transaction — even if the customer's entity assignment has changed since the original purchase. This ensures accurate tax calculation and invoice consistency.

***

## Deleting an entity

The Site Default Entity cannot be deleted — it's essential to the invoicing process and serves as the fallback for all customers. It can be edited at any time.

Any alternate entity can be deleted at any time. To delete one:

* From the entity list page, hover over the entity, click the ellipsis (…), and select **Delete**
* Or, from the entity's view page, select **Delete Entity** from the **Entity Actions** dropdown

<Image align="center" border={true} width="75%" src="https://files.readme.io/ad0103bc5853f6b97c915e6442b1a095701f9aeba65f35cc6cb180c06c606799-image.png" className="border" />

To confirm deletion, you'll be prompted to enter the entity's code. Once confirmed, the entity is permanently removed. However, any refunds tied to original transactions under that entity will still use its display and tax address information.

<Image align="center" border={true} width="75%" src="https://files.readme.io/a4a7e7dcadebe8753aaa09317abae29226a21d4efc7cdb4253ad6c1dd3ecd989-image.png" className="border" />

After deletion, customers who had that entity set as their account-level override will be reassigned to the Site Default Entity, unless one of the following applies:

* Their subscriptions are reassigned to a different entity
* Their "BILL TO" address matches a country in another entity's Subscriber Locations
* The deleted entity's Subscriber Location countries are moved to another entity
* They're manually reassigned to a specific entity at the account level

***

## Tax ID numbers

Tax ID Numbers (TINs) are configured per entity and appear as the last line of merchant information on invoices. When a Default TIN/VAT number is set on an entity, it displays on all invoices issued under that entity.

<Image align="center" border={true} width="75%" src="https://files.readme.io/b531d19695ab3ab54e4c5d6e63645e54b45f76fc8ad9b1c6f4ffdf98e2315b28-image.png" className="border" />

Country-specific TINs override the default when a customer's "BILL TO" address is in a country that has its own TIN configured on the entity.

For example: if an entity has a default VAT number and a separate country-specific VAT number for Portugal, customers with a Portuguese billing address will see the Portugal-specific VAT number. All other customers on that entity will see the default.

<Image align="center" border={true} width="75%" src="https://files.readme.io/93fb6eb5b4cad4a3a221de8a367f2df5b5206bef6c6f8f424dee933ed006af13-image.png" className="border" />

> **Note:** TIN/VAT numbers don't carry over between entities automatically. If you use the same TIN across multiple entities, you'll need to enter it on each one individually.

***

## Direct Avalara accounts

If you have a direct Avalara integration, you can map each Recurly entity to the corresponding company in your AvaTax account for independent tax reporting and filing per entity.

Recurly supports one Avalara account per site. Multi-entity tax support works by mapping your Recurly Site Default Entity to the Avalara main company, and each alternate entity to a sub-entity within that same Avalara account.

**To set up the mapping:**

1. In Avalara, locate the company or sub-company code you want to map
2. Copy the Company Code exactly as it appears
3. In Recurly, go to **Configuration → Taxes → Avalara AvaTax Settings**
4. Paste the code into the corresponding Company Code field for the appropriate entity

If you delete an entity in Recurly, that mapping to the corresponding Avalara sub-company will be removed. Keep mappings up to date as your entities change.

<Image align="center" width="75%" src="https://files.readme.io/cec7285c7f46551ba140881ea32401ff88b034cabb313ddc525ee405912f0095-image.png" />

***

## Paused subscriptions

When a paused subscription is resumed, or an immediate change is made to it, a new billing period is triggered. The next invoice will use whichever entity applies to the customer at that point — the account-level override, Subscriber Location assignment, or the Site Default Entity.

***

## Plan downgrades

If you downgrade from a Recurly Elite plan to a Starter or Professional plan, you'll lose the ability to maintain multiple entities once the downgrade takes effect. Historic invoices and refunds that used alternate entities will remain unchanged. All future invoices, subscriptions, and transactions will be assigned to your Site Default Entity.

If you re-upgrade to an Elite plan in the future, you'll need to recreate your alternate entities.

***

## Entity-specific email templates

Recurly supports up to 20 template variations per email template type. You can assign a specific variation to customers based on their geographic location or their subscription, account, or invoice's entity assignment. For more information, see the [Alternate Email Templates](https://docs.recurly.com/docs/alternate-email-templates) documentation.

***

# FAQs

**Can other Recurly objects, such as plans or coupons, be entity-specific?**

Objects like plans, items, and coupons aren't siloed by entity within Recurly. You can pass specific plan, item, or coupon codes to customers via API based on their entity, but you'll need to maintain those mappings and flows in your own integration.

**Can purchases made from a given entity be routed to a specific payment gateway?**

This isn't available through the Admin UI. However, you can set a specific payment gateway at both the subscription and account levels — so a subscription assigned to a particular entity can be routed to your preferred gateway.

**Can I file taxes by entity in Avalara or Vertex?**

Yes — this is supported for merchants with a direct Avalara or Vertex account. You'll need to configure the integration in your Recurly site by mapping entity and company/division codes appropriately to enable entity-specific filing in your tax system.

**Does this feature work with Recurly revenue recognition?**

Yes, multi-entity is compatible with Recurly revenue recognition. If you enable revenue recognition after creating entities, you'll need to create two GL codes for each entity on your site.

**Can I run entity-specific analytics in Recurly?**

Yes. Two dashboards include entity-specific data:

* [Business Entity Overview Dashboard](https://docs.recurly.com/docs/business-entities-overview)
* [Explore — Invoices Dashboard](https://docs.recurly.com/docs/business-entities-overview#explore-invoices-dashboard)

The Entity Code is also included in the Admin UI for the following exports: Invoices — Accounts Receivable, Adjustments, Adjustments — Taxes, and Invoices — Summary.
