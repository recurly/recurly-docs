---
title: Gorgias integration
deprecated: false
hidden: true
metadata:
  robots: index
---
Gorgias provides you with the ability to view subscriptions alongside customer support tickets and perform basic operations.

# Available Prive Properties

### Subscriber Properties

Below is a list of Prive Subscriber properties that are available in Gorgias Widgets. The subscriber card is the first card and displays general attributes of the user.

| Prive Subscriber Property  | Description                                       |
| -------------------------- | ------------------------------------------------- |
| Customer Since             | Earliest date the customer was a subscriber since |
| Email                      | Subscriber Email                                  |
| First Name                 | Subscriber first name                             |
| Id                         | Subscriber id                                     |
| last name                  | subscriber last name                              |
| last order                 | last order date                                   |
| next order                 | next order date                                   |
| phone                      | phone number                                      |
| total active subscriptions | total active subscriptions                        |
| total orders               | total orders shopper has ever placed              |

![Screen Shot 2023-12-11 at 2.52.01 PM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1ea57b89-63cb-4329-92c7-218cfd9586fe/96e2a3d6-744d-4d91-8c5a-57380697fbad/Screen_Shot_2023-12-11_at_2.52.01_PM.png)

***example subscriber data card***

### Subscription Properties

Below is a list of Prive subscription contract properties that are available in Gorgias Widgets. The subscription card represents a distinct subscription contract and displays all the items in the contract.

| Prive Subscription Contract Property | Description                             |
| ------------------------------------ | --------------------------------------- |
| Contract id                          | subscription contract unique identifier |
| product title                        | the items produdct title                |
| Status                               | ACTIVE, PAUSED, CANCELLED               |
| Updated at                           | last time contract was updated          |
| order interval frequency             | order frequency number                  |
| order interval unit                  | DAY, WEEK, MONTH                        |
| Next Order Date                      | Next order date                         |
| Cancellation reason                  | if theres a cancellation reason         |

***example subscription data card***

![Screen Shot 2023-12-11 at 2.32.45 PM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1ea57b89-63cb-4329-92c7-218cfd9586fe/18e017e3-88be-437e-80c0-79d1eabbd610/Screen_Shot_2023-12-11_at_2.32.45_PM.png)

### Subscription Actions

| Prive Subscription Contract Action | Description                                                                            |
| ---------------------------------- | -------------------------------------------------------------------------------------- |
| Skip Subscription                  | Skips the next order                                                                   |
| Change Delivery Date               | changes the next delivery date                                                         |
| Manage Subscription                | Links to the subscription in prive. User must be logged in through the shopify portal. |

![Screen Shot 2023-12-11 at 2.53.36 PM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1ea57b89-63cb-4329-92c7-218cfd9586fe/6db408ad-16b8-45e6-9a1a-6d8153b879af/Screen_Shot_2023-12-11_at_2.53.36_PM.png)

## Data Refresh

Data is refreshed in the tickets for all of your subscription customers, including migrated customers.  The refresh on the ticket occurs ***on ticket update***. Unfortunately, gorgias does not define this as the page simply loading - it requires an action like a message sent or I’ve found adding and then quickly removing a tag does the trick and constitutes an update which loads the sidebar.

# Setup

You can setup the connection between Prive and Gorgias at [https://admin.tryprive.com/integrations/gorgias](https://admin.tryprive.com/integrations/gorgias)

![Screen Shot 2023-12-11 at 2.56.18 PM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1ea57b89-63cb-4329-92c7-218cfd9586fe/15a5ce06-22c2-4a70-8824-f9ff096d2df4/Screen_Shot_2023-12-11_at_2.56.18_PM.png)

[]()

The necessary api url and passwords to input can be found in the gorgias admin properties. Input the values into prive and click connect and it’ll be done.

![Screen Shot 2023-12-11 at 2.57.52 PM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1ea57b89-63cb-4329-92c7-218cfd9586fe/890d5d0c-0729-423a-aebc-b5c87f8a1bae/Screen_Shot_2023-12-11_at_2.57.52_PM.png)

# Video

View the video below to see the Gorgias X Prive Integration in action.

[https://www.loom.com/share/1f8b9b9e05584c87bf8665fa4f42e47d](https://www.loom.com/share/1f8b9b9e05584c87bf8665fa4f42e47d)

# Chat with us

If you have any questions, please chat with us live from within the Prive Subscriptions App or via email at [support@tryprive.com](mailto:support@tryprive.com).