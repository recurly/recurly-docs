---
title: Cancellation Flows
excerpt: Proprietary & Confidential
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
> 👍 Merchant Benefit
> 
> Cancellation Flows is a feature to assist in preventing voluntary churn. The initial phases are designed to collect data to gain insights into why your customers are leaving. Future phases will enable linking cancel reasons to retention offers such as discounts, plan changes, or subscription pauses.

> 🚧 Cancellation Flows
> 
> This initiative is under development, with an iterative roll out process to merchants in early access. 
> 
> To participate in early access, please reach out to your Account Manager or Account Executive.

## Implementation

Implementing a cancel flow is a two step process (1) configuration via the admin UI to select the responses presented to the customer and (2) API integration to present the survey and capture your customers response.

### Configuration

1. **Access**: With a user who has the permission of _Configuration - Allow Access and Editing_ upon logging in to the Recurly Admin UI, navigate to _Configuration - Cancellation Flow_

[block:image]{"images":[{"image":["https://files.readme.io/ec79936-image.png",null,null],"align":"center","border":true}]}[/block]

2. **Select**: From the Available Responses section you can access the available responses in several ways
   1. Selecting the down carat shows all 16 default responses.
   2. Typing letters into the search box displays Responses that contain the characters entered.
   3. Typing numbers into the search box displays Responses containing the numbers entered.
3. **Move**: An Available Response is moved to the Selected Responses box by left clicking with your mouse or highlighting and pressing enter. 
   1. As Responses are 'moved' to Selected Responses, in the Available Responses drop down they are a lighter shade of grey to indicate they've been selected. 
4. **Publish**: If you do not yet have a published (saved) survey, as soon as a response is moved the Publish Changes button will become enabled. The button will also become enabled if you have a published survey and make any changes to Selected Responses.

[block:image]{"images":[{"image":["https://files.readme.io/15f1fa7-image.png",null,null],"align":"center","border":true}]}[/block]

The image below shows a successful Publish with two Selected Responses.

[block:image]{"images":[{"image":["https://files.readme.io/7b0cb93-image.png",null,null],"align":"center","border":true}]}[/block]

**Additional information**:

**Remove a Selected Response**: If you would like to remove a Response from Selected Responses simply single click on it. You will also notice in the Available Responses dropdown the text color is returned to normal. If you want to remove all Responses simply click on the Remove all(#) link and then Publish Changes.

**Order:** On the Cancellation Flow page the responses will initially show in the order you added them. If you refresh the page, or when you navigate away and return, they will be displayed in numerical order by their reference ID (001...016). When the API call is made to present them to your customer they will be in a random order. 

### Moving to production

As with other features within Recurly, to prevent test data from being in production, when you are ready to promote your sandbox to a production environment all Cancellation Flow user data and configurations will be cleaned and you will need to reconfigure your survey.

### API integration

Once you have your survey configured, the next step is to have the survey presented to your customer's and capture their results. Below is information about the API calls supporting Cancellation Flows.

- **GET List the site's published survey** as implied, this will only return the survey once it's in a published (aka saved) state. Published is defined as having one more response choices associated.
- **POST Create a new survey session** This is the call to generate a session for your customer. Ideally, anytime your customer clicks to indicate they wish to cancel, you would make a call to this endpoint to create a session. The response will include, among other things, the survey question and, in random order, the responses. This session will also be available in the Cancellation Flows export; available as an automated or manual export. 
- **POST Update a survey session** This call is used to update the session state and create a survey_response record with the customer's selection. The corresponding record in the export will also now display customer's  response and the position.
- **GET Fetch a survey session** If you ever need to retrieve a customers existing session, possibly something unexpected happened during the completion of the survey and the session state information was lost, use this call to retrieve the last known update to the survey session.  For better analytics reports, metrics housekeeping and to capture user behavior, we recommend beginning a new survey session when a user does not complete their survey in their initially assigned session (e.g. timed out or left the page).

Full details (path parameters, request and response schemas, and request and response samples) for our API calls can be found [here for v3 API](https://recurly.com/developers/api/v2999-01-01/index.html#operation/list_surveys) and [here for v2 API](https://recurly.com/developers/api-v2/v2.99/#operation/list_surveys). 

### Analyzing survey results

A Cancellation Flows export is available for configuration as a manual and automated export. The export provides data to enable you to gain an understanding as to why your customers are canceling, monitor trends such as if the position order of the response makes a difference, and provides insights into cancel behavior. An entry is created each time the _Create a new survey session_ API call is made and is updated each time the _Update a survey session_ API is called. Complete details on the export can be found [here](https://docs.recurly.com/docs/cancellation-flows-export).