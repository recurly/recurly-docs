---
title: OLD Setup Video
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Getting Started 
[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FpRXZ-gRcNr4%3Ffeature%3Doembed&url=http%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DpRXZ-gRcNr4&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FpRXZ-gRcNr4%2Fhqdefault.jpg&key=02466f963b9b4bb8845a05b53d3235d7&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" frameborder=\"0\" allowfullscreen></iframe>",
  "url": "https://www.youtube.com/watch?v=pRXZ-gRcNr4&feature=youtu.be",
  "title": "Recurly for Salesforce",
  "favicon": "https://s.ytimg.com/yts/img/favicon-vflz7uhzw.ico",
  "image": "https://i.ytimg.com/vi/pRXZ-gRcNr4/hqdefault.jpg"
}
[/block]
See above for a video on how to get started with the Recurly for Salesforce integration. You will also find detailed instructions below.

Setting up an integration with Salesforce can be complicated, especially if you have a significant amount of data in your system. Before getting started, please be sure to read through this entire page. If you have questions or are unsure of how the setup process functions, please [reach out to our team](https://support.recurly.com/) and we will be happy to assist you in setup.

### Initial Steps

1. If you don't already have a Salesforce account, you can [create a free developer account](https://developer.salesforce.com/signup) for evaluation. We highly recommend that you test the integration in a Recurly sandbox account before integrating your production account.

2. Install the Recurly for Salesforce package in your Salesforce organization. We recommend you install in a sandbox org first to test the integration with your business process. [**Click here**]( http://test.salesforce.com/packaging/installPackage.apexp?p0=04t1Q000001QhyN) for the sandbox Salesforce integration link. Once this feature is enabled on your production Recurly account, you'll receive a separate install link for the production integration.
 
3. Within your Salesforce instance, choose the roles you would like to assign Recurly permissions to.  It is important to do this before installing the package because you will assign the permission sets in the package to these profiles during package installation. If you would like to make new profiles, clone existing Salesforce profiles that you would like to have Recurly permission sets added to and label them "**Recurly ______ Profile**." e.g. "**Recurly Support Profile**." 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/21213b6-Screen_Shot_2016-09-01_at_12.56.33_PM.png",
        "Screen Shot 2016-09-01 at 12.56.33 PM.png",
        1860,
        874,
        "#b2d3e2"
      ]
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1bb405c-Screen_Shot_2016-09-22_at_1.49.46_PM.png",
        "Screen Shot 2016-09-22 at 1.49.46 PM.png",
        929,
        461,
        "#f6f6f7"
      ]
    }
  ]
}
[/block]
4. Click Install. Grant access to the Recurly API when prompted.

5. The install process will run. It may take a few minutes to complete.

6. We recommend you review your user profiles after the install process is complete to ensure that your profiles have been assigned to the user roles you would like to access Recurly data.

7. We STRONGLY recommend if you have state/country fields set up as pick lists, that you change them to be text fields. This will likely save you many hours of headaches in the integration process as pick lists are very challenging for all integrations, including ours.

## Configuring Your Recurly for Salesforce Integration

### Configure API Settings

After installing the app, navigate to the **API Settings** tab on the **Recurly Admin** page and follow these instructions to connect your Recurly site(s) to your Salesforce org:

1. Set the *Private API Key*: This is the field that will capture your API key to authenticate with Recurly. You can find this under "API Credentials" in Recurly. We recommend you create a new API key called "Salesforce".

2. Set *Public Key*: This field will accept your public API key on the "API Credentials" page in Recurly so that you can integrate with Recurly.js for payment information. If you do not want to sync information from SFDC back to Recurly, you do not need to include the Public Key.

3. Continue to set the Private and Public API keys for any other Recurly subdomains which you would like to have populate data in Salesforce. The integration supports a maximum of ten (10) subdomains syncing data from Recurly. This functionality is helpful if you have multiple business units or product lines using different Recurly sites.

### Configure Sync Settings

Once your API settings are configured, continue to the **Sync Settings** tab to set the rest of your automated data sync preferences:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/07dab88-Sync_Settings.png",
        "Sync_Settings.png",
        2366,
        1010,
        "#f4f4f4"
      ],
      "caption": "Sync Settings tab"
    }
  ]
}
[/block]
1. *Enable Outbound Sync*: Checking this box will enable the ability to sync records from Salesforce to Recurly. These new/edited records sync immediately. If this option is disabled, records updated in Salesforce will not sync to Recurly. Note that this functionality requires that the Public API Key be populated in step #2, above.

2. *Invoice Roll-Ups*: By enabling this option, Salesforce accounts that are linked to Recurly accounts will be populated with the overview and summarization fields listed in [our docs](https://docs.recurly.com/docs/salesforce#section-recurly-data-on-standard-salesforce-accounts), which can be used for reporting on Salesforce accounts.

3. *Most Recent Invoice*: By enabling this option, Salesforce accounts you have linked to Recurly accounts will be populated with "Recurly Most Recent Invoice Amount" which can be used for reporting on Salesforce accounts.

4. *Only Sync Accounts with Subscriptions*: Checking this box will only sync accounts that have active, pending, or expired subscriptions to Salesforce. Accounts without subscriptions will not be synced. This will limit the amount of data sent to Salesforce.
[block:callout]
{
  "type": "warning",
  "body": "DO NOT click **Activate Recurly Sync** yet. This will be the last step after more settings are enabled.",
  "title": "Warning"
}
[/block]
### Linking Recurly Accounts with Native Salesforce Accounts

The **Account Link Settings** enable you to link the Recurly Accounts custom object with the native Account object within Salesforce. By clicking this checkbox, when accounts are integrated from Recurly, the app will create a link between the Recurly Account record and a related Salesforce account record if a match exists.

_For example, if you link Recurly accounts and Salesforce accounts based on email address: If you have a Recurly account with email address "test@salesforce.com" and you enable the setting, the integration will look to see if there is a Salesforce account with the email address "test@salesforce.com". If a Salesforce account with this email exists, then it will be linked to the applicable Recurly account. If there is no account with this email address, the Recurly account will not be linked to any accounts in Salesforce._

This setting is not required, and we advise you to review the documentation below before enabling it or contact Recurly Support for assistance.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1b859a9-Account_Link_Settings.png",
        "Account_Link_Settings.png",
        2352,
        1106,
        "#f2f2f2"
      ],
      "caption": "Account Link Settings tab"
    }
  ]
}
[/block]
1. *Link Accounts Enabled*: Checking this box will enable the ability to link Recurly accounts to related Salesforce accounts that already exist in your organization.

2. Choose the desired fields on which to match accounts in the *Salesforce Account Link Field* and *Recurly Account Link Field*. Note that this is mandatory to enable account linking.
[block:callout]
{
  "type": "danger",
  "body": "Do not use a calculated field, a field that is not writable from external systems, or a field that is not visible to your Salesforce users. If you choose a field that fits this description, Recurly will not be able to create accounts in Salesforce and this functionality will not work.",
  "title": "Warning on Calculated Fields"
}
[/block]
3. *Create Accounts To Link To*: If account linking is configured, this setting enables Salesforce to create accounts in the native Accounts object for any Recurly accounts that don't match an existing Salesforce account. See below for more details.

#### Creating Salesforce Accounts from Recurly Accounts

If you choose to link Recurly accounts to standard Salesforce accounts, the integration gives you the additional option to create a Salesforce account if a Recurly account does not find a match within Salesforce. In the **Account Link Settings**, checking the *Create Accounts to Link to* box will cause Salesforce accounts to be created if a link is not found to associate a Recurly account to an existing Salesforce account.

_For example, if you link Recurly accounts and Salesforce accounts based on email address: If you have a Recurly account with email address "test@salesforce.com" and you enable the setting, the integration will look to see if there is a Salesforce account with email address "test@salesforce.com". If a Salesforce account with this email exists, then it will be linked to the applicable Recurly account. If there is no account with this email address, the integration will attempt to create a Salesforce account for it._

This feature is helpful for merchants who have an online channel that generates leads for their sales team. It will create Salesforce accounts that can be edited and owned by sales and service teams.
[block:callout]
{
  "type": "danger",
  "title": "Warning on Salesforce Account Creation",
  "body": "This setting is not required, and we advise you to review all documentation before enabling the setting as it may result in a significant number of accounts being created in your Salesforce instance."
}
[/block]
### Configure Product Sync Settings

If you have enabled the integration to sync your Recurly offerings (plans, add-ons, and items) with the native Product object in Salesforce (via the Advanced Settings tab), these settings will allow you to tailor that sync.
[block:callout]
{
  "type": "info",
  "body": "This option **will not** be editable if product syncing is not enabled"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a392e94-Product_Sync_Settings.png",
        "Product_Sync_Settings.png",
        2400,
        1574,
        "#f6f6f6"
      ],
      "caption": "Product Sync Settings tab"
    }
  ]
}
[/block]
1. *Product Linking Enabled*: This setting defaults to disabled. Checking this box will cause the integration to link Recurly Plans, Recurly Add-Ons, and Recurly Items to related Salesforce products that already exist in your organization. If a matching Salesforce product does not exist, or if this setting is disabled, then a new product will be created and linked to each Recurly custom object.

_For example, if you link Recurly plans and Salesforce products based on Plan Code and Product Code: If you have a Recurly plan with plan code "test123" and you enable the setting, the integration will look to see if there is a Salesforce product with the product code "test123". If a Salesforce product with this product code exists, then it will be linked to the applicable Recurly plan. If there is no product with this product code, then a new product will be created and linked to the Recurly plan._

2. Choose the desired fields on which to match your Recurly offerings and your Salesforce products. Note that this is mandatory to enable product linking. If a 1:1 match can't be identified for any Recurly offering (e.g. multiple Recurly objects match to a single existing product), then the existing product will be untouched and new products will be created for each Recurly object.
[block:callout]
{
  "type": "danger",
  "title": "Warning on Calculated Fields",
  "body": "Do not use a calculated field, a field that is not writable from external systems, or a field that is not visible to your Salesforce users. If you choose a field that fits this description, Recurly will not be able to create accounts in Salesforce and this functionality will not work."
}
[/block]
3. *Product Pricing Sync Enabled*: This setting defaults to disabled. Checking this box will cause the integration to sync the price for each Recurly offering to a Standard Price Book entry for the related product. Only prices that match the default currency of your Salesforce organization will be synced.

4. *Convert Opportunities to Recurly Subscriptions*: This setting defaults to disabled. Checking this box will enable the ability to create subscriptions and accounts in Recurly from Closed Won opportunities in Salesforce.

### Configure Advanced Sync Settings

The majority of users should ignore this section. If you have complex needs, please read on.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/710efd3-Advanced_Settings.png",
        "Advanced_Settings.png",
        2370,
        1694,
        "#f5f5f5"
      ],
      "caption": "Advanced Settings tab"
    }
  ]
}
[/block]
1. *Sync Batch Frequency*: By default, Salesforce will query Recurly once every 5 minutes to get new data. This can put a lot of strain on your Salesforce system but it gets you near-real-time information. If you would like to increase this interval, you can use this selector to choose any time between 5 and 60 minutes as the interval between data syncs.

2. *Nightly Account Rollup Start Time*: If you have invoice roll-ups enabled in your Sync Settings, these fields on the Salesforce account will be calculated each night at the specified time.

3. *Use Person Accounts*: If you have person accounts enabled in your Salesforce org, you will see the option to associate Person Accounts with Recurly Accounts when setting up Advanced Settings. Enable it to use the account linking functionality to work with person accounts.

4. *Item Sync Enabled*: This setting defaults to enabled. If you uncheck this box, items from your Recurly item catalog will not be synced with Salesforce. The purpose of this option is to limit the amount of data that is sent to Salesforce and should be used when you have concerns about data limits in your Salesforce org. If you elect to remove this option, items sold as add-ons or one-time charges will still be visible within the Recurly Add Ons and Recurly Line Items objects.

5. *Transaction Sync Enabled*: This setting defaults to enabled. If you uncheck this box, transactions will not be synced with Salesforce. The purpose of this option is to limit the amount of data that is sent to Salesforce and should be used when you have concerns about data limits in your Salesforce org. If you elect to remove this option, you can use the payment fields on the Recurly Invoice object to report on transactions.

6. *Line Item Sync Enabled*: This setting defaults to enabled. If you uncheck this box, invoice line items will not be synced with Salesforce. The purpose of this option is to limit the amount of data that is sent to Salesforce and should be used when you have concerns about data limits in your Salesforce org. If you elect to remove this option, you can use the total fields on the Recurly Invoice object to report on amounts invoiced, but you may lose detail that is only held on line item records.

7. *Product Sync Enabled*: This setting defaults to disabled. If you check this box, your plans, add-ons, and items from Recurly will be synced with the native Product object in Salesforce. The purpose of this option is the limit the amount of data that is sent to Salesforce and should be used when you have concerns about data limits in your Salesforce org. With this option disabled, your Recurly offerings will still sync with the custom Recurly objects in Salesforce but will not be available to sell on Opportunities. More details around configuring this functionality are [above](https://docs.recurly.com/docs/recurly-for-salesforce-set-up#section-configure-product-sync-settings).

8. *Plan Name Assigned to Account*: This setting will transfer the name of any subscriptions linked to the Recurly account to the linked Salesforce standard accounts. You will also need to add the "Recurly Plan" field to the Salesforce account layout. This is best used in Salesforce for reporting on accounts by plan type. Note that this option is only available if you elect to link Recurly accounts and Salesforce accounts.

9. *Past Due Account Notification*: If you enable this function, any Salesforce account with a linked Recurly account that is past due will have the "Recurly Past Due Invoice" field on the Salesforce account checked. This is best used in Salesforce for reporting on accounts that are past due. Note that this option is only available if you elect to link Recurly accounts and Salesforce accounts.

10. *Billing Address*: If you enable this setting, the billing address from the Recurly account will transfer to the Billing Address fields on the linked Salesforce account. Note that this option is only available if you elect to link Recurly accounts and Salesforce accounts.

11. *Active Subscriber*: If you enable this setting, when a Recurly account that is linked to a Salesforce account has an active subscription, then the "Recurly Active Subscriber" checkbox on the Salesforce account will be checked. This feature is best used in reporting to see which customers have active subscriptions. Note that this option is only available if you elect to link Recurly accounts and Salesforce accounts.

12. *In Trial*: If you enable this setting, any Salesforce account with a linked Recurly account that has a subscription in the trial stage will have the "Recurly In Trial" checkbox on the Salesforce account checked. 

## Editing Your Salesforce Layouts

To take full advantage of your integration between Salesforce and Recurly, a number of Recurly-specific fields can be added to your native account, product, and opportunity layouts in Salesforce for easy access by your team.

### Modifying the Salesforce Account Layout
[block:callout]
{
  "type": "info",
  "body": "If you are not linking Recurly accounts and Salesforce standard accounts, you can ignore this section."
}
[/block]
In order to view Recurly data alongside the sales data that you have on your linked Salesforce accounts, you will need to edit the layout of your Salesforce account page. To do this, navigate to a Salesforce account layout and click "Edit Layout." Note that you need to have appropriate permissions to edit and save these forms.

**Recurly Fields:** If you elected to enable the advanced settings during the setup process, the following fields will be populated on Salesforce accounts. These fields will be updated each time a Recurly account is updated, except where noted below.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bc0294a-Screen_Shot_2016-11-04_at_4.26.53_PM.png",
        "Screen Shot 2016-11-04 at 4.26.53 PM.png",
        1003,
        216,
        "#e5e7e8"
      ]
    }
  ]
}
[/block]
1. *Recurly Active Subscriber*: If there are linked accounts with an active subscription, this will be True.
2. *Recurly Average Last 3 Invoices*: Average of the last 3 invoices issued in Recurly (updated overnight).
3. *Recurly Most Recent Invoice Amount*: The amount of the most recent invoice issued to this customer.
4. *Recurly Past Due Invoice*: If the account has a past due invoice in Recurly, this will be True.
5. *Recurly Plan Name*: If the account has an active subscription, the name of the plan will be populated here.
6. *Recurly Total Invoice Amount*: The sum of the total amount of invoices issued to this customer (updated overnight).
7. *Recurly Total Payment Amount*: The sum of the total amount of payments this customer has paid (updated overnight).

You can choose to drag any of these fields onto your account layout. An example layout is below:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9ef09ca-Screen_Shot_2016-11-04_at_4.30.59_PM.png",
        "Screen Shot 2016-11-04 at 4.30.59 PM.png",
        973,
        303,
        "#c2dbe4"
      ]
    }
  ]
}
[/block]
**Related Lists:** You can also add Related Lists for Recurly objects to your Salesforce account. This allows your sales reps and support reps to see billing information on the account object and is available for:

* Recurly Accounts
* Recurly Subscriptions
* Recurly Invoices
* Recurly Transactions
* Recurly Line Items

Below is our recommended account layout if you use all of the Recurly sync features:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/77d3945-Screen_Shot_2016-11-04_at_4.36.23_PM.png",
        "Screen Shot 2016-11-04 at 4.36.23 PM.png",
        882,
        1002,
        "#f6f5f4"
      ]
    }
  ]
}
[/block]
### Modifying the Salesforce Product Layout
[block:callout]
{
  "type": "info",
  "body": "If you are not syncing Recurly offerings to Salesforce products, you can ignore this section."
}
[/block]
In order to easily transition between your Salesforce products and their linked Recurly offerings, you can edit the layout of your Salesforce product page. To do this, navigate to a Salesforce product layout and click "Edit Layout." Note that you need to have appropriate permissions to edit and save these forms.

**Recurly Fields:** The following Visualforce page/field will be available on Salesforce products. This field will be updated any time the linked Recurly offering is updated.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a625ef4-Product_Layout.png",
        "Product_Layout.png",
        1982,
        412,
        "#d1d5da"
      ]
    }
  ]
}
[/block]
*Linked Recurly Object*: If there is a linked plan, add-on, or item for this product, the name and link will be provided here. The field name is dynamic and will indicate the object type for this linked object.

### Modifying the Salesforce Opportunity Layout
[block:callout]
{
  "type": "info",
  "title": "",
  "body": "If you are not creating Recurly subscriptions from Salesforce opportunities, you can ignore this section."
}
[/block]
In order to create Recurly subscriptions directly from Closed Won opportunities in Salesforce, you need to edit the layout of your Salesforce opportunity page. To do this, navigate to a Salesforce opportunity layout and click "Edit Layout." Note that you need to have appropriate permissions to edit and save these forms.

**Recurly Fields:** The following Visualforce page/field will be available on Salesforce opportunities.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e326103-Opportunity_Layout.png",
        "Opportunity_Layout.png",
        2022,
        414,
        "#d1d5da"
      ]
    }
  ]
}
[/block]
*Recurly Subscription Button*: If the opportunity includes one or more Recurly-based products and is in a Closed Won status, this button will appear on the page to trigger the process of subscription (and account) creation in Recurly. Once a subscription has been created for an opportunity, this button will no longer be displayed. If you want to control access to this subscription creation capability, consider restricting the visibility of this button to specific user profiles.

**Related Lists:** You can also add Related Lists for Recurly subscriptions to your Salesforce opportunity. This allows your sales reps and support reps to see the final Recurly subscription that was created from an opportunity.

## Begin Syncing Data

Once you've completed the setup above, we recommend that you ensure your settings are complete and accurate. If you feel unsure of your setup, please [get in touch](https://support.recurly.com)! We are happy to work with you ensure you have the appropriate setup for your business and org.

When you are ready, click the Activate Recurly Sync button on the **Sync Settings** tab in order to sync data from Recurly to Salesforce. Note that the user who clicks the "Activate Recurly Sync" button will be the owner of the Recurly custom objects, as well as the Salesforce Account, Product, and Price Book Entry objects created in your instance.
[block:callout]
{
  "type": "warning",
  "body": "The first sync process will likely take longer than your future syncs due to your historical Recurly data syncing to Salesforce"
}
[/block]
**After the initial sync:**

* Records will be queried from Recurly into Salesforce every 5 minutes (or other cadence specified in your [Advanced Sync Settings](https://docs.recurly.com/docs/recurly-for-salesforce-set-up#section-configure-advanced-sync-settings)

* Updates made to these records within Salesforce will be sent back to Recurly immediately (if you have the Outbound Sync setting enabled).

* If you would like to retry a sync process, you can change the date/time in the Last Sync Time field on the Sync Settings tab to trigger a fresh sync

* If you would like to stop Salesforce from querying Recurly, click the "Deactivate Recurly Sync" button on the Sync Settings tab

## Uninstalling Recurly for Salesforce

If you need to uninstall a previous version of the package (version 1.5 is incompatible with version 2.0) or would simply like to uninstall the package, follow these instructions.

1. Click on the Sync Settings tab
2. Click on the "Deactivate Sync" button to turn off the automatic sync from Recurly
3. Click Setup in the upper right corner of the screen (note: if you are not an administrator in your Salesforce org, you may not have access to the below steps)
4. Click on Build > Installed Packages
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d6f758b-Screen_Shot_2016-09-02_at_12.16.24_PM.png",
        "Screen Shot 2016-09-02 at 12.16.24 PM.png",
        2422,
        778,
        "#e3e9ed"
      ]
    }
  ]
}
[/block]
5. Click "Uninstall" next to Recurly for Salesforce
6. You will be asked whether or not you would like to keep your data in your org or delete it

Should you run into issues with processes currently running, you can review your background jobs and stop them from running. If you have any other problems or questions, feel free to [contact us](https://support.recurly.com).