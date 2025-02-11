---
title: Ramp pricing implementation guide
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
## Overview

This guide will provide detailed instructions on how to implement Ramp Pricing via API with your site. There are a few key actions to be sure to take, as well things to avoid. This guide will walk you through the following actions:

* Creating plans via API 
* Getting plan details via API
* Editing plans via API 
* Creating subscriptions via API
* Editing Subscriptions via API 
* Changing a Subscriptions' Plan via API

Also reference the [Ramp Pricing documentation](https://docs.recurly.com/docs/ramp-pricing). 

## Ramp Pricing: Supported API Versions

Ramp Pricing will be supported in the following API versions: 

* API V3 v2021-02-25
* API V3 v2019-10-10
* API V2 v2.29

#### Documentation

View API developer documentation on ramp pricing:\
[https://developers.recurly.com/api/v2021-02-25/index.html](https://developers.recurly.com/api/v2021-02-25/index.html)\
[https://developers.recurly.com/api/v2019-10-10/index.html](https://developers.recurly.com/api/v2019-10-10/index.html)\
[https://developers.recurly.com/api-v2/v2.29/index.html](https://developers.recurly.com/api-v2/v2.29/index.html)

## Managing Ramp Priced Plans via API

#### Step 1

Use POST /plans to create a plan with ramp pricing

* Include pricing\_model	as "ramp"
* Include the ramp\_intervals object to set the ramp pricing schedule
* Include the existing currencies object, and omit the base unit\_amount, as this is included within the ramp\_intervals object for ramp priced plans

```json Create Ramp Priced Plan
"pricing_model": "ramp",
"ramp_intervals": [
    {
      "starting_billing_cycle": 1,
      "currencies": [
        {
          "currency": "str",
          "unit_amount": 0
        }
      ]
    }
],
"currencies": [
		{
			"currency": "str",
			"setup_fee": 0,
			"tax_inclusive": false
		}
]
```

#### Step 2

Use GET /plans or GET /plans/\{plan\_id} to retrieve plan information including the ramp pricing schedule

* The ramp\_intervals object will be returned on a single plan or all applicable plans that represent the ramp pricing schedule for the plan

#### Step 3

Use PUT /plans/\{plan\_id} to update information regarding a plans ramp pricing schedule

* Include the updated ramp pricing schedule in the ramp\_intervals object 
* Include the full ramp pricing schedule that you would like to publish on the plan
* The new ramp pricing schedule will override any previous ramp pricing schedule

## Creating Subscriptions to Ramp Priced Plans via API

#### Step 1

Use POST /purchases or POST /subscriptions to create a subscription to a ramp priced plan

* If you would like to use the ramp pricing schedule from the plan, do not send in the ramp\_intervals object, and do not send in the previously existing unit\_amount value. Simply pass in the plan\_code for the desired plan.
* If you would like to create a unique ramp pricing schedule for the subscription, send the ramp\_intervals object to specify the ramp pricing schedule for the subscription. Do not send in the previously existing unit\_amount value.

```json POST /purchases or /subscriptions REQUEST to create subscription with unique ramp intervals from the plan
{
  "subscriptions": [
    {
      "plan_code": "string",
      "quantity": 1,
			"currency": "str",
      "ramp_intervals": [
        {
          "starting_billing_cycle": 1,
          "unit_amount": 2.99
        },
        {
          "starting_billing_cycle": 4,
          "unit_amount": 9.99
        },
        {
          "starting_billing_cycle": 7,
          "unit_amount": 14.99
        }
      ],
      "starts_at": "2019-08-24T14:15:22Z",
      "next_bill_date": "2019-08-24T14:15:22Z",
      "total_billing_cycles": 1,
      "renewal_billing_cycles": 0,
      "auto_renew": true
    }
  ]
}
```

#### Step 2

Use GET /subscriptions/\{subscription\_id} to retrieve the ramp pricing information for a subscription, or GET /subscriptions/ will include the ramp pricing information for all applicable subscriptions

* The ramp\_intervals object will be returned for the subscription 
* The first non-zero amount of remaining\_billing\_cycles is the current ramp interval.

```json GET /subscriptions/{subscription_id} RESPONSE to view ramp interval schedule on a subscription
{
  "id": "string",
  "object": "string",
  "uuid": "string",
  "account": {
    "id": "string",
    "object": "string",
    "code": "string",
    "email": "user@example.com",
    "first_name": "string",
    "last_name": "string",
    "company": "string",
    "parent_account_id": "string",
    "bill_to": "string",
    "dunning_campaign_id": "string"
  },
  "plan": {
    "id": "string",
    "object": "string",
    "code": "string",
    "name": "string"
  },
  "unit_amount": 0,
  "quantity": 0,
  "ramp_intervals": [
    {
      "starting_billing_cycle": 1,
      "remaining_billing_cycles": 3,
      "unit_amount": 2.99,
      "starting_on": "2023-07-14T16:57:17Z",
      "ending_on": "2023-08-14T16:57:17Z"
    },
    },
    {
      "starting_billing_cycle": 4,
      "remaining_billing_cycles": 2,
      "unit_amount": 9.99,
      "starting_on": "2023-07-14T16:57:17Z",
      "ending_on": "2023-08-14T16:57:17Z"
    },
    {
      "starting_billing_cycle": 7,
      "remaining_billing_cycles": 0,
      "unit_amount": 14.99,
      "starting_on": "2023-08-14T16:57:17Z",
      "ending_on": null
    }
  ]
}
```

#### Step 3

To modify a ramp priced subscription use POST v3/subscriptions/\{subscription\_id}/change

* Editing the ramp pricing schedule is only available as an Immediate Change, where "timeframe": "now"
* You can add additional price changes or modify the price and duration of any upcoming price change. You can also edit the price of the current billing period. This is accomplished by sending in a set of ramp intervals, that takes into account the current ramp interval and future ramp intervals. Do not send in past billing cycles.

```json POST /subscription/{subscription_id}/change REQUEST to modify ramp intervals
{
  "timeframe": "now",
  "ramp_intervals": [
    {
      "starting_billing_cycle": 1,
      "unit_amount": 2.99
    },
    {
      "starting_billing_cycle": 12,
      "unit_amount": 14.99
    },
    {
      "starting_billing_cycle": 18,
      "unit_amount": 19.99
    }
  ]
}
```

## Notes When Editing a Subscriptions Ramp Intervals

* You must send in the entire set of ramp intervals, and do so in a way that you do not change the price of any past billing cycle (already elapsed).  
* In order to change pricing you may often need to split out the past billing cycles of the current ramp into their own ramp, then create a new ramp with the price change for current/future billing cycles.

**Example**\
Sub ramps, subscription in 5th billing cycle, you wish to change the current and future pricing on the subscription.\
\{starting\_billing\_cycle: 1, unit\_amount: 1.00}\
\{starting\_billing\_cycle: 4, unit\_amount: 2.00}

**Correct payload**\
\{starting\_billing\_cycle: 1, unit\_amount: 1.00}\
\{starting\_billing\_cycle: 4, unit\_amount: 2.00}\
\{starting\_billing\_cycle: 5, unit\_amount: 3.00}

**Prohibited payload** (does not account for billing cycle 4 already billed at $2)\
\{starting\_billing\_cycle: 1, unit\_amount: 1.00}\
\{starting\_billing\_cycle: 4, unit\_amount: 3.00}

**Error Response**\
past\_billing\_cycles: cannot make changes to billing cycles that occurred prior to the current billing cycle

To have this feature enabled, please reach out to your Account Manager or Account Executive.
