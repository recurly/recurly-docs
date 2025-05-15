---
title: Gorgias integration
deprecated: false
hidden: true
metadata:
  robots: index
---
Gorgias provides you with the ability to view subscriptions alongside customer support tickets and perform basic operations.

# Available Recurly Commerce properties

### Subscriber Properties

Below is a list of Recurly Commerce Subscriber properties that are available in Gorgias Widgets. The subscriber card is the first card and displays general attributes of the user.

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

### Subscription properties

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

![](https://files.readme.io/3cff9280d25a1f28c54899c0b247017e74bb1bcddb960513889e66a43ed848be-image.png)

### Subscription actions

| Recurly Commerce Subscription Contract Action | Description                                                                            |
| --------------------------------------------- | -------------------------------------------------------------------------------------- |
| Skip Subscription                             | Skips the next order                                                                   |
| Change Delivery Date                          | changes the next delivery date                                                         |
| Manage Subscription                           | Links to the subscription in prive. User must be logged in through the shopify portal. |

![](https://files.readme.io/d9a02f6815a530855942f406237f87d47d05843c94c926ebffe9ec08eb36c4d3-image.png)

## Data refresh

Data is refreshed in the tickets for all of your subscription customers, including migrated customers.  The refresh on the ticket occurs ***on ticket update***. Unfortunately, gorgias does not define this as the page simply loading - it requires an action like a message sent or I’ve found adding and then quickly removing a tag does the trick and constitutes an update which loads the sidebar.

# Setup

You can setup the connection between Prive and Gorgias at [https://admin.tryprive.com/integrations/gorgias](https://admin.tryprive.com/integrations/gorgias)

<br />

![](https://files.readme.io/ae0f23457f5e288ec934e5f953cec169ad6444d58105216bbc1ae2c80b819d38-image.png)

<br />

The necessary api url and passwords to input can be found in the gorgias admin properties. Input the values into prive and click connect and it’ll be done.

![](https://files.readme.io/8d153beb5939badb4a0f59ac4e8fc3a18235482f7cef28a736a6ccb4b55e3755-image.png)

# Video

<Embed typeOfEmbed="iframe" url="https://www.loom.com/embed/1f8b9b9e05584c87bf8665fa4f42e47d" html="false" iframe="true" href="https://www.loom.com/embed/1f8b9b9e05584c87bf8665fa4f42e47d" />