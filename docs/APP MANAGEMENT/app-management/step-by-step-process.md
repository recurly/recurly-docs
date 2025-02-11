---
title: App Management setup
excerpt: >-
  This page will guide you through the process to connect your Apple and Google
  apps, configure App Management, and initiate a migration
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Connect your mobile apps

In order for Recurly to provide you a complete view of the lifecycle of your app subscriptions, and provide insight into the associated subscription revenue, you need to direct the real time notifications from Apple and Google to Recurly and provide API access to retrieve key subscription related info. Follow the steps below one-time to connect your mobile app to Recurly.

**Before proceeding to connect Apple or Google**, be sure to read through the [App Management Key Details section](https://docs.recurly.com/docs/app-management#key-details). You may need to make slight modifications to the subscription purchasing workflow in your mobile apps.

## Apple App Store

### Prerequisites

Before configuring Recurly App Management, you need to create a new Apple App Store Connect API key with appropriate permissions. In order to complete the required steps in these prerequisites, you need to be either an "Account Holder" or “Admin” within Apple App Store Connect. If you run into permission issues, please reach out to one of your Apple App Store Connect Admins.

1. **Log into **Apple App Store Connect via <a href="https://appstoreconnect.apple.com/access/integrations/api" target="_blank">this link</a>. As shown below, you will be creating an **App Store Connect API key** (NOT an In-App Purchase key) for the Recurly connection.
   1. [block:image]{"images":[{"image":["https://files.readme.io/47f5ec5-createKeyv2.png","",""],"align":"center","sizing":"50% ","border":true}]}[/block]
2. **Create **an API key by clicking the + (plus) symbol near “Active”
   1. **Input **a name to uniquely identify the key
   2. For Access, **select **both "Developer", and "Sales and Reports" (see example).  
       
      1. [block:image]{"images":[{"image":["https://files.readme.io/6c000ec-image.png",null,""],"align":"center","sizing":"50% ","border":true}]}[/block]
   3. **Click **"Generate" to generate the API key.
3. Once the key is generated, you will see an option to download the key from the table of Active keys. Please **download **that **private key file** (.p8 file), and **save it** in a secure location. **You will only be able to download that file once, so be careful to securely store it.**
4. For that key, **save the “Key ID”**, which is found in the same row of information for the key you just created.
5. In addition, **save the “Issuer ID”**, which is found just above the list of Active keys.
6. While in Apple App Store Connect, **navigate **to “Reports”, which is found near the top center of your page. It can also be found from the App Store Connect page, by clicking on “Payments and Financial Reports”.
7. When viewing the Reports page, **save your “Vendor #”**, which is listed on the top left of the page.
8. You have now completed the prerequisites, and have all the information from Apple that you need to connect Recurly. There is one additional Apple App Store Connect step in the instructions below, so remain logged into Apple App Store Connect.

### Configuration

1. In Recurly, **navigate **to App Management → App Connector. Under "Apple App Store", click “Add Source”.
   1. If you are only replacing the API key, next to "Apple App Store", click "View Details".
2. This is where you will input all the information you noted earlier regarding the API key.
   1. For “Authentication Key”, **open** the private key p8 file you downloaded in a text editor, and **paste the entire contents** in the field. As seen in the example below, your copy and paste includes the hyphens and BEGIN PRIVATE KEY and END PRIVATE KEY.
   2. If you have already enabled the connection, and are coming back to replace the API key, you only need to replace the "Authentication Key" and "Key ID" fields. Once those are edited, the new API key is being used, and you can skip the remaining configuration skips listed below.
3. As shown in the example below, **ensure **you have all 4 fields populated. Your input should look similar to what is shown. Once all 4 fields look good, click “Enable connection”.  

   [block:image]{"images":[{"image":["https://files.readme.io/e58446c-image.png",null,""],"align":"center","sizing":"50% ","border":true}]}[/block]

   1. <br />
4. Once enabled, you now need to point the Apple App Store notifications to Recurly. While on that same page in Recurly, copy the “Production URL” shown to your clipboard.
   1. If you are **only** configuring Recurly App Management to push mobile app earnings revenue information into Recurly Revenue Recognition, you can skip this step and the remaining steps. Please note that if these steps are skipped, Recurly App Management will **not** provide any visibility into your mobile app subscription lifecycles and related events.
5. Back in Apple App Store Connect, **navigate **to your app. You can get to your app in “My Apps”, or from Apps on the top of your page.
6. While viewing your App in Apple App Store Connect, **navigate **to the “App Store Server Notifications” section under General → App Information.
7. Next to “Production Server URL”, **click **Edit, and **input** the copied URL from Recurly into the “Production Server URL” field. In that window, **ensure **“Version 2 Notifications” are selected, and then **click** Save.
   1. If you are testing and using a non-Production site, you will want to edit the “Sandbox Server URL” instead of Production.
8. Once the server URL for your Apple app is correctly pointing to Recurly, go back to your open page within Recurly and check the box to confirm that you have added the URL.
9. **Click **“Complete Configuration”.
10. You have now completed the steps necessary to connect Recurly with your Apple app.
    1. **Note**: The "Last Notification Received" date will remain blank until Recurly receives a valid notification from Apple. Test notifications sent directly from Apple App Store Connect to test the notification Server URL will not impact the "Last Notification Received" date.

## Google Play

### Prerequisites

Before configuring Recurly App Management, you need to create a new Google Cloud service account and API key with appropriate permissions. Given **it can take Google up to 36 hours** to propagate the service account access, we recommend completing these prerequisites early, and then ensuring at least 36 hours has passed. When configuring Recurly App Management, your API access is checked to ensure that your subscriptions are successfully tracked upon completing the configuration.

1. If not done already, **ensure** you have a Google Play Developer account and have set up a profile in Google Payments by following the steps below.
   1. Set up a Google Play Developer account (instructions <a href="https://support.google.com/googleplay/android-developer/answer/6112435" target="_blank">here</a>).
   2. Set up a profile in <a href="https://pay.google.com/" target="_blank">Google Payments Center</a>, and link that profile to your developer account (instructions <a href="https://support.google.com/googleplay/android-developer/answer/3092739" target="_blank">here</a>).
      1. **If your app is not yet live**, you can **skip** this step and come back to it before going live.
2. Following <a href="https://developers.google.com/android-publisher/getting_started" target="_blank">these Google instructions</a>, configure access to the Google Play Developer API through the Google Cloud Console and Google Play Console. When done following those instructions, you should have completed the following tasks. Please note that we have provided additional info below to the linked Google instructions.
   1. **Link **your developer account to a new or existing Google Cloud Project.
   2. **Enable** the Google Play Developer API for your linked Google Cloud Project.
   3. **Set up** a service account with appropriate Google Play Console permissions to access the Google Play Developer API.
      1. When you are creating the service account, **make sure** to add the “Pub/Sub Admin” and “Monitoring Viewer” roles, which give the service account necessary permissions to the Google Project.
      2. **Save the e-mail address** for the new service account.
   4. **Provide **the service account you created with access to your app within Google Play Console
      1. Within Google Play Console, **click **“Invite new users” from the “Users and Permissions” page.
      2. Within Permissions, **click **“Add app”, **select **your app from the list, and click **Apply**. When prompted to select Permissions for your app, click Apply.
      3. Once your app appears under App permissions, **click** "Account permissions" (to the right of App permissions) and select the below 3 permissions.
         1. View app information and download bulk reports (read-only)
         2. View financial data, orders, and cancellation survey responses
         3. Manage orders and subscriptions
      4. Click **Invite User** to invite the service account, and complete this step
3. Following <a href="https://developers.google.com/workspace/guides/create-credentials#create_credentials_for_a_service_account" target="_blank">these Google instructions</a>, **create** a new JSON key for your service account.
   1. **Given that you can never recover the private JSON key from Google, be sure to securely store the key**. You will need this key for an upcoming step within Recurly.
4. Referring to the section entitled “Find your Google Cloud Storage URI” of <a href="https://support.google.com/googleplay/android-developer/answer/6135870?hl=en" target="_blank">these Google instructions</a>, **save a link to the Google Storage URI** that points to the Earnings report.
5. You have now completed the prerequisites, and have all the information from Google that you need to connect Recurly. There are additional Google steps in the instructions below, so remain logged into Google Play and Google Cloud.

### Configuration

1. As noted in the prerequisites, ensure you have waited at least 36 hours since creating the JSON key for your new Google Cloud service account. Once that time has elapsed, proceed to the next step.
2. **Connect **your Google app to Recurly
   1. In Recurly, **navigate **to App Management -> App Connector, and click Add Source for Google Play Store.
   2. Using the example shown below, **input **your service account JSON key, Earnings report URI, and App package name.  
      1. For JSON key, copy the entire contents of the JSON key file and paste them into the field.
      2. For Google Earnings Report URI, paste in the entire URI that you saved earlier. The URI typically begins with gs:// and ends with earnings/.
      3. For App Package name, click into your app from Home within Google Play Console to access the Dashboard of your app. Copy the unique package name, which is found directly under the name of your app.
      4. [block:image]{"images":[{"image":["https://files.readme.io/1259949-GooogleConfig3.png","",""],"align":"center","sizing":"50% ","border":true}]}[/block]
   3. **Click **“Verify Credentials”
   4. Once enabled, a Production URL for App Management is created. Leave this page open, and **continue **to the next step.
3. **Follow **these steps to set up Google Pub/Sub, which is used by Recurly to receive notifications from Google regarding subscription activity.
   1. If you are **only** configuring Recurly App Management to push mobile app earnings revenue information into Recurly Revenue Recognition, you can skip this step and the remaining steps. Please note that if these steps are skipped, Recurly App Management will **not** provide any visibility into your mobile app subscription lifecycles and related events.
   2. Following <a href="https://cloud.google.com/pubsub/docs/publish-receive-messages-console#create_a_topic" target="_blank">these Google instructions</a>, **create** a topic. As shown in the example below, **uncheck** “Add a default subscription” (we will create one in the next step).
      1. [block:image]{"images":[{"image":["https://files.readme.io/e5db490-CreateTopic.png","",""],"align":"center","sizing":"50% ","border":true}]}[/block]
   3. While viewing the topic, **save **the “Topic ID” since you will need it later. This topic ID is the longer URI version (e.g., projects/{project_id}/topics/{topic_name}), and not just the name you provided when creating the topic.
   4. **Add **a subscription to that topic by clicking “Create Subscription” within the topic, and inputting the following information:
      1. Referencing the example below, **select **“Delivery type” of Push and paste the URL from Recurly App Management into “Endpoint URL”
         1. [block:image]{"images":[{"image":["https://files.readme.io/3201c7c-addSub.png","",""],"align":"center","sizing":"50% ","border":true}]}[/block]
      2. Referencing the example below, **change **Acknowledgement deadline from the default to 60 seconds.
         1. [block:image]{"images":[{"image":["https://files.readme.io/a280776-ackDeadline.png","",""],"align":"center","sizing":"50% ","border":true}]}[/block]
      3. Referencing the example below, **change **Retry policy to “Retry after exponential backoff delay”, with the default of 10 seconds for minimum backoff, and 600 seconds for maximum backoff.
         1. [block:image]{"images":[{"image":["https://files.readme.io/01414fb-retryPolicy.png","",""],"align":"center","sizing":"50% ","border":true}]}[/block]
      4. **Click ** "Create" to create the subscription.
   5. Following <a href="https://developer.android.com/google/play/billing/getting-ready#grant-rights" target="_blank">these Google instructions</a>, grant Google Play privileges to publish notifications to your topic. You can see an example of this step below.
      1. [block:image]{"images":[{"image":["https://files.readme.io/d683df6-addPrincipals.png","",""],"align":"center","sizing":"50% ","border":true}]}[/block]
4. Following <a href="https://developer.android.com/google/play/billing/getting-ready#enable-rtdn" target="_blank">these Google instructions</a>, enable real-time notifications for your app by inputting the topic name and sending a test message.
   1. This is where you will use the longer URI version of your topic that you saved in a previous step.
5. Once you have completed setting up Google Pub/Sub and real-time notifications for your Google app, **proceed back** to Recurly. Check the checkbox that confirms you have completed setting up the Google configuration, and then click Complete Configuration.
6. App Management within Recurly is now set up. You can now look forward to viewing your Google Play app information within Recurly!
   1. **Note**: The "Last Notification Received" date will remain blank until Recurly receives a valid notification from Google.

# Configure App Management

Once you have completed the required steps above to connect your mobile apps, follow these steps to complete the configuration.

## Creating external products

External products are created in order for Recurly to correctly associate your unique Apple and Google subscriptions to a single product within Recurly. This makes it easier for you to track one type of subscription, which may be available via web or your mobile apps. Follow these steps to create your external products. You only need to do this once per subscription that you have created in Apple or Google.

1. **Navigate **to App Management -> External Products in the left hand navigation
2. **Click **the New External Product button
3. **Give **the external product a name (e.g., Monthly Gold Plan).
4. **Select** the Recurly plan you want to map to this external product (e.g., Monthly Gold Plan - Web).
5. **Click **the Add Source button to map either your Apple or Google product, and follow the information below to enter the "External Reference Code"
   1. For Apple, **provide **the Apple "Product ID" of the product you want to map to this Recurly plan. 
      1. When logged into Apple App Store Connect, you can find the "Product ID" when viewing the details of a specific subscription.
   2. For Google Play, a subscription can have one or more plans associated with it. In order to properly reference a specific subscription, you need to provide both the Product ID and Base Plan ID. Using an example of "ACME" for Product ID and "Monthly_Pass" for Base Plan ID, you would enter "ACME+Monthly_Pass" for the External Reference code in Recurly.
      1. When logged into the Google Play Console, navigate to Monetize → Products → Subscriptions for your mobile app. You can find the "Product ID" when viewing the details of a specific subscription. In that same view, you can find a table of base plans under "Base plans and offers". The "Base Plan ID" is listed in the first column of that table.
6. **Repeat **the above step if you offer an identical subscription via the other app store (Google or Apple)
7. **Click **Create External Product to save your changes.

For each subscription offered via Apple or Google, you should have one external product reflected within Recurly. For example, if you offer a monthly subscription and yearly subscription, you should have two external products configured when done with this section. The below is an example of having three types of your subscription offerings identified within Recurly as external products.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/34ba932-external-products.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


## Entitlements

Our entitlements feature provides an easy way to both control and grant access to features within your mobile app. For more information on this feature, including how to create entitlements, see our [entitlements feature](https://docs.recurly.com/docs/entitlements) docs. When you create entitlements, you will see an option to assign an External Product. This is how you will include one of the external products you just created to an entitlement.

If you plan to use our entitlements feature, navigate to Configuration -> Entitlements, and follow the instructions linked in the above paragraph. The below is an example of having three entitlements configured.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8c29fe3-entitlements.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


**You have now completed the minimum requirements to get App Management working properly.** If you need to migrate historical subscription related activity, see the below section.

## Webhooks

Once Recurly has processed a real-time notification from Apple or Google and updated the subscription related data within Recurly, Recurly can send a webhook notification specific to the subscription event (e.g., subscriber canceled). If you would like to receive those webhooks, navigate to the <a href="https://docs.recurly.com/docs/api-support-and-webhooks#configuring-recurly-to-send-webhooks" target="_blank">next page</a> to learn more about how to configure and received those webhooks.

# Migration

Due to limitations with the Apple and Google App Stores, Recurly is unable to automatically ingest historical data from the App Stores on your behalf. This includes any App Store subscriptions that were created prior to your use of Recurly App Management. In order to reflect this data in Recurly, it is necessary to backfill our records with subscription and customer information stored on your side. Please contact our <a href="https://support.recurly.com/" target="_blank">support team</a>, as they will facilitate the historical import.