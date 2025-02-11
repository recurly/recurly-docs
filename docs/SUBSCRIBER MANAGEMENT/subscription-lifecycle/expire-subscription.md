---
title: Expire/cancel subscription
excerpt: >-
  Ensure flexibility and customer satisfaction with our intuitive cancelation
  and expiration options.
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

<Embed url="https://www.youtube.com/watch?v=jJsmG-2a95Y" title="How to Cancel a Subscription" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/jJsmG-2a95Y/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=jJsmG-2a95Y" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FjJsmG-2a95Y%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DjJsmG-2a95Y%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FjJsmG-2a95Y%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

The "Expire/Cancel Subscription" feature in Recurly offers businesses the ability to manage the termination or conclusion of their customer's subscriptions. Whether it's an immediate cancellation, end-of-term expiration, or a customer-initiated change, our solution is crafted to provide flexibility without complexity.

# Definition

When a customer elects to end their subscription at the next bill date or term end, this is called **canceling** the subscription. If you decide to end the subscription early, mid-cycle, this is called **terminating** the subscription. Both result in the subscription **expiring**. Once a subscription is expired, it cannot be reactivated. Only a canceled subscription can be reactivated, which just means the customer changed their mind and decided to continue the subscription before the bill date where the subscription was set to expire. Subscriptions configured to expire at end of their term, will naturally expire at the end of their last billing period.

# Key benefits

* **Empowered customer experience**: Offer cancellation choice, fostering trust and a positive brand interaction.
* **Customizable subscription expiry**: Flexibility in setting subscription end dates—immediate, next bill, or term end.
* **Automated revenue recovery**: Streamline expiration actions based on payment outcomes for efficient dunning management.

# Key details

In the digital age, providing autonomy to users about their subscription choices is essential. Recurly's "Expire/Cancel Subscription" tool enables businesses to strike the right balance between flexibility and effective subscription management.

Subscriptions often run through various states during their lifecycle. They can be active, canceled, or expired based on various factors, including customer decisions, business needs, or externalities like payment failures.

When a subscription is **cancelled**, it remains active for the duration of the subscription period in a 'pre-expiry' state, which means the customer still has the liberty to reactivate it before it moves to the **expired** state and access to the service is terminated. Once a subscription is in the expired state, it cannot be reactivated; a new subscription has to be initiated. Here, the differentiation between 'canceling' and 'terminating' becomes crucial. While cancellation leads to an eventual expiration at a pre-set future date, termination results in an immediate expiration.

<Image title="2019-09-04_0922.png" alt={866} align="center" src="https://files.readme.io/9ebba7b-2019-09-04_0922.png">
  Subscriptions can be cancelled at three different timeframes: immediately, next bill date, or term renewal.
</Image>

# Cancel a Subscription

**a. Admin console:** 

* Navigate to the desired account.
* Click on the subscription name.
* From the **Subscription Actions** dropdown, choose **Cancel Subscription**.
* Decide the cancellation type: immediate, at the next billing cycle, or at the end of the term.

**b. Hosted account management:** 

* Navigate to the **Hosted Page Settings** under Configuration in the Admin Console.  
* Enable the **Cancel subscriptions** option under Customer Options.  
* The customer, upon accessing their Hosted Account, will have the option to cancel.

# Reactivate a subscription

> **Note**: The subscription can only be reactivated if it isn't expired or permanently canceled.

**a. Admin console:** 

* Go to the desired account.  
* Select the canceled subscription's name.  
* Use the **Subscription Actions** dropdown and opt for **Reactivate Subscription**.

**b. Hosted account management:** 

* If the cancellation option was provided to the customer, they'll see a reactivation option until the subscription expires.

# Terminate a subscription

**a. Admin console:** 

* Access the desired account.  
* Click on the subscription name.  
* From the **Subscription Actions** dropdown, opt for **Cancel Subscription**.  
* On the following page, select **Terminate Subscription**.

**b. API:**

Termination can also be initiated through API calls. Specific API documentation will provide the required parameters and endpoints.

# Dunning

Within <a href="https://docs.recurly.com/docs/dunning-management">Dunning Management</a> you can choose to automatically expire a subscription when an invoice for the subscription reaches the end of the dunning cycle without successful payment.

It is important to note that if a subscription expires outside of dunning, via canceling, terminating, or naturally expiring, any past due invoices on the account currently in dunning will not automatically be failed. Those past due invoices will stay open and in dunning until they are either paid or reach the end of their dunning cycle. If you have selected to leave invoices past due at the end of dunning, then the invoices will never automatically fail. If you would like to stop collection on the past due invoices, you will need to manually mark them as failed.
