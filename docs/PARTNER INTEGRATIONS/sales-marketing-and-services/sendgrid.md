---
title: SendGrid
excerpt: >-
  Enhance your email efficiency with Recurly’s SendGrid integration—seamlessly
  manage customer communications with superior deliverability and analytics.
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

### Required Plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Additional Cost

Although Recurly doesn’t charge extra for this integration, there are associated costs from SendGrid which are determined by their pricing and policies.

### Managed Integration

For those who prefer not to use this self-service integration detailed below and are on the Elite plan, Recurly offers a Professional Services integration. There are additional costs associated with this service. For more information on this, reach out to Recurly account manager or [support@recurly.com](<>) for more details.

# Definition

Recurly's SendGrid integration is a feature that allows users to connect their merchant account to SendGrid using their own service and API key. This integration facilitates the management of customer communications by utilizing SendGrid’s SMTP server relays. It provides improved email deliverability and access to detailed analytics, ensuring that emails are delivered efficiently and reach the intended recipients accurately.

# SendGrid implementation guide

1. Having a SendGrid account with [Domain Authentication](https://docs.sendgrid.com/ui/account-and-settings/how-to-set-up-domain-authentication#what-is-domain-authentication) configured is a prerequisite for utilizing this integration.  You can sign up for a SendGrid account [here](https://sendgrid.com/en-us/pricing).
2. Ensure that you have site administration privileges for your Recurly account, allowing you to make the necessary configuration changes.
3. Connect Recurly to your SendGrid account by utilizing an  existing SendGrid API key or easily [create a new one](https://docs.sendgrid.com/ui/account-and-settings/api-keys#creating-an-api-key). The API Key will require “Mail Send” permissions.
4. Assign your SendGrid API key to your Recurly Site within the [Site Settings](https://app.recurly.com/go/configuration/edit) section. This step establishes the connection between Recurly and SendGrid, enabling seamless integration.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d3730ed-image.png",
        null,
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


Please **note** that any emails queued for dispatch prior to setting your SendGrid API Key will be sent as originally scheduled. However, once you have successfully set your SendGrid API Key, all subsequent queued emails will be sent using your SendGrid account. Allow some time for the system to process the active queue and ensure a smooth transition to the SendGrid integration.

# FAQs

**Q: Am I required to make this change?**  
**A:** No, the SendGrid integration is optional and available for those who want to leverage their own SendGrid account to gain visibility into email statistics and have more control over email deliverability.

**Q: Will Recurly continue to send emails for me if I don't use this SendGrid integration?**  
**A: **Yes, absolutely. The SendGrid integration is not mandatory, and Recurly will continue sending emails on your behalf if you choose not to set up a SendGrid account.

**Q: How soon after adding my API key will emails be sent from my SendGrid account?**  
**A:** Please allow some time for the system to process the active email queue. Once you've added your SendGrid API key, the transition to sending emails from your SendGrid account may take a short period before you start seeing them being sent.

**Q: Is there a charge for setting this up?**  
**A:** Recurly does not impose any additional charges to utilize this integration. However, please note that any applicable charges from SendGrid will be determined by their pricing and policies.

**Q: I logged into my site, but I don't see the SendGrid API field. Do I need to enable something else?**  
**A: **To update your SendGrid API key, a site admin needs to log in to your Recurly account. Once the API key is set, its value will always be masked for security purposes.