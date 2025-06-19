---
title: Segment
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
#### Metadata description

Configuration guide for ingesting Segment.com events into Recurly Engage via AWS Lambda and using them as usage trackers.

# Overview

### Required plan (the same for all pages)

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations \[just add if any]

# Definition

# Key benefits

* **This is a key benefit**: This is a description (x3)

# Key details (the rest of the contents)

## Integrating with Segment.com

Recurly Engage allows you to ingest Segment.com events and target your users according to your existing Page (web), Screen (mobile), and Track calls. This article explains how to add us as a destination via Amazon Lambda.

1. Login to Segment
2. Go to the correct app workspace

![Settings→Integrations](https://files.readme.io/f5c742b-Segment_configure.png)

1. Add a new destination

![Settings→Integrations](https://files.readme.io/125929e-Segment_configure_2.png)

1. Type lambda in the search box and click the found tile

![Settings→Integrations](https://files.readme.io/cfe1f2f-Segment_configure_3.png)

1. Click "Configure Amazon Lambda"

![Settings→Integrations](https://files.readme.io/8baf8c6-Segment_configure_4.png)

1. Select your app and click "Confirm Source"

![Settings→Integrations](https://files.readme.io/ffd3c94-Segment_configure_5.png)

1. Now go to \[2] and locate the credentials to enter

![Settings→Integrations](https://files.readme.io/58f7707-Segment_Configure_6.png)

1. Copy over the `Region`, `Role Address` and `Lambda ARN` values. Make sure to provide the read-only `External ID` to your customer success manager as the final step. Note that `Client Context` and `Log Type` do not need any special configuration.

![Settings→Integrations](https://files.readme.io/a036acc-Segment_configure_7.png)
![Settings→Integrations](https://files.readme.io/a6f4a75-Segment_Configure_8.png)

Information from Segment can take up to one hour before it is available within Recurly Engage.

## Adding a new tracker

1. Go to **Settings > Usage Tracking > Segment > Add New Tracker**.

![Settings→Integrations](https://files.readme.io/47e233c-Segment_configure_9.png)

1. Select a Segment event

![Settings→Integrations](https://files.readme.io/0caf0ba-Segment_configure_10.png)

1. Click Submit

![Settings→Integrations](https://files.readme.io/8c96b24-Segment_Configure_11.png)
![Settings→Integrations](https://files.readme.io/f74c2d1-Segment_Configure_12.png)

1. Go to add a new segment

![Settings→Integrations](https://files.readme.io/8ec2610-Segment_Configure_13.png)

1. Now under the **Usage** tab you can see the newly added Segment trait you can target.

![Settings→Integrations](https://files.readme.io/0af69fd-Redfast_usage_4.png)