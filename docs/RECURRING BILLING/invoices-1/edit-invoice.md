---
title: Edit invoice
excerpt: >-
  Optimize your billing process by seamlessly editing and tailoring invoices as
  per your requirements with Recurly's Edit Invoice feature.
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

Recurly's Edit Invoice allows merchants to modify specific attributes of an invoice post its generation. From changing the 'Bill To' information, adding a PO number, adjusting the due date to attaching specific notes, ensure your invoices remain accurate and updated.

# Key benefits

- **Flexibility**: Adapt to changing business requirements or customer details with ease, ensuring invoices always stay relevant.
- **Compliance and accuracy**: Maintain precise and compliant billing records by editing invoice attributes as required.
- **Efficient process**: With integrated tools like activity logs, webhooks, and integration syncs, ensure that every edit is logged and synced, maintaining transparency.

# Key details

**Invoice Editing Capabilities:** Recurly's advanced billing system ensures that your invoices remain accurate and up-to-date, even after their creation. The platform's flexibility allows merchants to adjust vital invoice attributes such as the 'Bill To' details, PO numbers, due dates, and other specific annotations. One of the standout features is Recurly's in-built historical record system. With this, any modifications made to an account's details, like the name or company, won't inadvertently alter previously issued invoices. This separation preserves the authenticity of older invoices while offering the ability to tailor newer ones.

**Access Controls:** Ensuring the security and sanctity of financial records, Recurly has implemented a robust permission-based system for its Edit Invoice feature. Only administrators granted explicit edit permissions in the Customers section can make alterations to invoices. In contrast, those with read-only permissions can view the details but are restricted from making any changes, safeguarding against unintended edits.

**API Integration:** Beyond the manual adjustments within the Admin Console, tech-savvy users or those with integrated business systems can leverage the power of the Recurly API. This offers a programmatic method to edit invoices, facilitating seamless interactions with other digital platforms or automated workflows, further enhancing efficiency.

**Attribute Flexibility:** Every business is unique, and so are its billing requirements. Recognizing this, Recurly offers varying degrees of flexibility for different invoice attributes. From adjusting PO numbers, tailoring customer notes, setting terms and conditions, amending VAT reverse charge notes, to modifying 'Bill To' details, merchants have a wide range of editable fields. However, it's crucial to be aware of certain restrictions. For instance, if an invoice has undergone tax considerations, alterations to the 'Bill To' address may be limited to maintain tax accuracy.

**Communication:** Clear communication is pivotal in maintaining trust. Even though Recurly won't auto-send an email after an invoice edit, it provides merchants with the autonomy to inform their customers. By manually triggering a resend of the updated invoice information, businesses can ensure their clientele remains well-informed, nurturing transparency.

**Activity Transparency:** Accountability is paramount, especially in financial dealings. Recurly's commitment to transparency shines through its meticulous activity log feature. Each edit, no matter how minor, is recorded, detailing which invoice attributes were adjusted. This systematic logging fosters trust, as merchants can always trace back changes, ensuring a dependable audit trail.

**Webhook Notifications:** The digital ecosystem is vast, and staying informed becomes vital. Every time an invoice undergoes an edit, Recurly dispatches a webhook notification encapsulating the changes. The type of notification differs based on the nature of the edited invoice. This real-time information dispatch aids in keeping integrated systems or stakeholders in sync with the modifications.

**Integration with Other Platforms:** Recurly's adaptability is further highlighted by its interoperability with renowned platforms like Salesforce, QuickBooks, and NetSuite. Any edits performed within Recurly are synchronized during the regular update cycles of these platforms. Yet, it's crucial to note some exceptions. Platforms such as Xero necessitate manual adjustments for the changes to take effect, emphasizing the need to be aware of each platform's specific integration nuances.

# **Editing an Invoice in the Admin Console:**

1. Navigate to the "Customers" section in the Admin Console.
2. Find and select the invoice you want to edit.
3. Click on the "Invoice Actions" dropdown located at the top right of the Invoice Details page.
4. Choose "Edit Invoice".
5. This will redirect you to the edit page where you can make the necessary modifications.
6. After making all desired changes, click "Save Changes".

# **Editing Invoice via API:**

1. Refer to the Recurly API documentation for the `put_invoice` operation.
2. Ensure you have all necessary parameters and information for the API call.
3. Make the API request with the new changes.
4. On successful execution, the invoice will be updated with the modifications provided.

# **Resending Updated Invoice:**

1. Navigate to the "Invoice Details" page in the Admin Console for the edited invoice.
2. Opt to resend the last email for the invoice.
3. The email, pulling the latest invoice information, will be sent to the customer.

# FAQs

**Q:** Will editing the invoice trigger an email to the customer?

**A:** No, any modifications made to an invoice within Recurly will not automatically dispatch an email notification to the customer. This design choice ensures that merchants have full control over communication. If you deem it necessary to update your customer with the revised invoice details, you can manually initiate the resend of the latest invoice information from the Invoice Details page within the Admin Console. By doing so, you make sure your customers are kept in the loop with the most accurate and updated billing information.

**Q:** Why can't I edit the invoice's Bill To address?

**A:** The 'Bill To' address is closely tied to tax calculations. If your Recurly site has taxes enabled, or if the invoice was previously subjected to tax considerations when it was posted, you'll find that you can't modify the 'Bill To' address. This restriction is in place because changing the address could potentially alter the tax amount due to different tax regulations in various regions. Recurly prioritizes maintaining the accuracy of invoice amounts and prevents any changes that might inadvertently adjust them. Furthermore, even if an invoice doesn't currently have taxes applied, altering the address could place it in a taxable jurisdiction, leading to tax requirements.

**Q:** Why can't I edit the Ship To on the invoice?

**A:** The 'Ship To' address, typically indicating where goods are to be delivered, has multiple operational implications. For instance, changing this address could affect logistics, delivery timelines, and even costs. To ensure that there's no unintentional disruption, especially where physical goods are concerned, Recurly decided to omit the 'Ship To' editing feature from the initial release of the invoice editing capability. If you have a strong business case or specific requirement to adjust the 'Ship To' details, it's recommended to reach out to Recurly Support. They can provide guidance and discuss potential solutions tailored to your use case.

**Q:** I want to edit something you don't support.

**A:** Recurly is always striving to enhance its platform based on user feedback and business needs. If you find that a specific attribute or feature isn't available for editing, please don't hesitate to contact Recurly Support. Sharing your requirements and the underlying business rationale can be immensely valuable. Such feedback often guides future updates and feature rollouts, ensuring that the platform remains aligned with the evolving needs of its user base.