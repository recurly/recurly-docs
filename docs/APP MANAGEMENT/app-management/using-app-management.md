---
title: Using App Management
excerpt: >-
  After you have connected your mobile apps and configured App Management, this
  page details out how to use App Management to get visibility into your app
  subscriptions
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: Enjoy App Management, and reach out if you need anything
---
# Viewing app subscriptions

Recurly makes it easy to see a complete picture of all your mobile app subscriptions, and allows you to drill into any customer account or subscription for more detail. In the example below, you can see that Brady has subscribed to the "US 1 Month Pro" plan via the Apple app.


<Image src="https://files.readme.io/be753a6-subDetails.png" align="center" width="75% " border={true} />


For more detail about the associated subscription activities, you can find a list right below the above customer account details. In the example below, a customer subscribed in April, and their monthly subscription renewed two times.


<Image src="https://files.readme.io/1c32a02-activities.png" align="center" width="75% " border={true} />


To understand the revenue associated with a customer account, or all of your customers, you can view the corresponding invoices. In the example below, you can see a snippet from a list of all Google and Apple invoices. When viewing a specific customer account, you will only see invoices specific to that account.


<Image src="https://files.readme.io/892704d-invoices.png" align="center" width="75% " border={true} />


Those are some of the ways you can find more information regarding your customer subscriptions. If you are interested in more metrics and data around your overall subscription health, read more below about the available dashboards, exports, and additional features.

# Dashboards

Analytics dashboards are available to provide you with insights and a comparison of your business performance across the App Stores. Additionally, you are able to extract your App Store data from Recurly for further transformation and analysis by leveraging the [Exports](#exports) or <a href="https://docs.recurly.com/docs/api-support-and-webhooks#rest-api-endpoints" target="_blank">REST APIs</a>. Metrics are grouped in the categories shown below.

For all dashboards, you can either view the information in a visual chart, or in a tabular format.

## Subscriptions

The Subscription dashboards provides insights into your active and churned subscriptions across each App Store, or broken down by each subscription offering.


<Image src="https://files.readme.io/085b9a00afbc0b53bf58563de99f7268271ede2e34332ce4e0a2b90bdd0ffbcf-image.png" align="center" width="700px" border={true} />


![]()


<Image src="https://files.readme.io/7beb46c6c32f389d1fc57663ff3f95dd978bf22fe64cffdabcb832e068a27801-image.png" align="right" border={true} />


<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />


<Image src="https://files.readme.io/8a88134d0692c155495036284d7709147965b659db11b32d3aeb2d37ce008762-image.png" align="center" border={true} />


## Subscriber retention

The Subscriber Retention dashboard uses cohort analysis to evaluate paid subscriber retention and churn rates over a specified timeframe for each cohort. As shown in the below example, you gain insight into the number of months your customers are staying subscribed, and can see if that duration is impacted by the month they became a subscriber.


<Image src="https://files.readme.io/6469c57ac9e35e311d2359063e894fe4387220fcbfbf03d32c3c3a7001ed2996-image.png" align="center" border={true} />


<br />

## Billings

The Billings dashboard shows total gross revenue processed in the App Stores over a selected time period. Billings can be broken down by the App Store from which they originated, and by new revenue (successful first time payments) and renewing revenue.


<Image src="https://files.readme.io/5f15a6ae9a4b9bf6c3d804bf74fd68a082d688c7850b296352045f852f598ed9-image.png" align="center" border={true} />


## Monthly recurring revenue

The Monthly Recurring Revenue (MRR) dashboard shows total gross revenue processed in the App Stores **minus the App Store commission** (10-30%) over a selected time period.


<Image src="https://files.readme.io/53cd74c847bf04ce900ab42ea53575ff8bfa499f7798ede3490837e906dd58df-image.png" align="center" border={true} />


# Exports

If you would prefer information from Recurly in a tabular format to either view in another application or within a spreadsheet editor, Recurly makes it easy for you to export that information for any time range specified. Specific to App Management, the below exports are **always available by navigating to Analytics -> Exports**.

- [Subscriptions - External](https://docs.recurly.com/docs/subscriptions-external)
  - Provides detailed information about all of your mobile app subscriptions.
- [Invoices - External](https://docs.recurly.com/docs/invoices-external)
  - Provides detailed information for all invoices (e.g., $1.99 for a new subscription) related to your mobile app subscriptions.

These exports can be downloaded manually as a CSV file, or through our [Automated Export system](https://docs.recurly.com/docs/export-overview#automated-exports).

# Additional features

## Business process automation

Recurly can be used as a hub for identifying and taking action on subscription lifecycle events using the [webhooks](https://docs.recurly.com/docs/api-support-and-webhooks#webhooks) and [REST API](https://docs.recurly.com/docs/api-support-and-webhooks#rest-api-endpoints). Using an example of checking to see if a customer is entitled to a set of features within your mobile app, you have a couple of options to verify if they should have access.

- Utilize the [External Subscription endpoints](https://docs.recurly.com/docs/api-support-and-webhooks#external-subscriptions) to determine if the customer has an active subscription
- Utilize [Entitlements](https://docs.recurly.com/docs/step-by-step-process#entitlements) and associated [REST API endpoints](https://docs.recurly.com/docs/api-support-and-webhooks#entitlements).

## Unassigned purchases

If Recurly is notified of a purchase by Apple or Google for a subscription you have not already defined as an External Product within Recurly, that purchase will be designated as an Unassigned Purchase. To ensure your new subscriber is entitled to their newly purchased subscription, you can review the list of unassigned purchases and quickly resolve the issue by assigning them to a new or existing External product.

# Troubleshooting

### When looking at "Last Notification Received" for my Apple or Google connection, it is either blank or shows an old date. Why?

If this value is blank, Recurly has never received a real-time notification from Apple or Google. In most cases, this is because Apple or Google are not configured to send notifications to the Recurly URL provided in App Management. To verify, follow the Apple or Google setup instructions listed [here](https://docs.recurly.com/docs/step-by-step-process).

If this value is not current (e.g., 5 days old), Recurly has not received any recent subscription related activity from Apple or Google. This could be because you do not have new subscribers, nor any subscription activity (e.g., renewal) since that date. If that is not true, it is likely due to the same issue listed above when the value is blank.

In addition, test server notifications (i.e., "Request a Test Notification") do not impact the "Last Notification Received", given that activity does not indicate that Recurly is correctly receiving subscription lifecycle notifications.

### When trying to connect Apple or Google, you receive an error. Why?

To ensure Recurly App Management is able to successfully begin tracking all subscription lifecycle events for your mobile apps, we validate the information you provide during configuration. If any of those components are incorrect, we provide immediate feedback. Here are a couple of the issues we have seen, that could be causing an issue with the validation.

- The entire contents of the API key file were not pasted into the field. Be sure to copy the entire contents of the file, and paste that into the configuration page.
- The API key was input correctly, but the permissions required by Recurly were not applied correctly within Apple or Google. To verify the permissions are correctly set, review the steps listed under **Prerequisites** for the appropriate app store.

### If I need to troubleshoot a subscription with Apple or Google, how can I uniquely identify the subscription when working with them?

There a couple of ways to get this unique identifier. For context, Apple uses originalTransactionId and Google uses purchaseToken. You can find this identifier as "External ID" when viewing the table of external subscriptions found at Customers -> Subscriptions -> External. You can also find this "External ID" when viewing the details of an external subscription.

### If we need to test occasionally (e.g., test a new introductory offer) to ensure everything looks good within Recurly, how can we ensure that testing does not interfere with our real (Production) subscriptions?

We have made it easy to filter out this test related activity. Here are a couple examples of how we make this easy for you:

- When viewing the table of external subscriptions or the table of external invoices, you will see a column called Environment which will show either Test or Production. In addition, you can use the filters on the left side to only show Production.
- When viewing the details of an external subscription, you will see a Test tag in the upper left, and Test for any related invoices and activity.

### For the integration with our Apple App Store and subscription lifecycle events, do we have to use Apple StoreKit 2?

No, it is not required to use Apple StoreKit 2. In addition, Recurly does not require that you implement an SDK from Recurly to power the subscription purchasing experience.
