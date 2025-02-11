---
title: Account acquisition data
excerpt: Unlock critical insights with the Account Acquisition Data export.
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

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

The **Account Acquisition Data** section in Recurly's user guide is dedicated to helping merchants capture and leverage key account acquisition details. It facilitates the combination of business acquisition costs data and stored revenue information, enabling merchants to measure customer acquisition costs and lifetime value, as well as gain insight into which marketing channels are the most effective.

### Introduction

Recurly introduces functionalities to meticulously record pivotal marketing and account acquisition details on the account record. The primary role of this is to amalgamate the business's customer acquisition costs and the revenue data housed in Recurly. This vision entails not just a presentation of the revenue data but a fusion of both cost and revenue details, empowering merchants with the knowledge to make judicious decisions.

### Acquisition Data

Broaden your understanding of customer accounts with Recurly by capturing the following vital details:

1. **Cost to Acquire a Customer**: The cumulative cost incurred through marketing activities to acquire the customer.
2. **CAC Currency**: Represented in a 3-letter ISO code for the respective currency.
3. **Acquisition Channel**: Identifying the medium through which the customer was acquired.
4. **Acquisition Sub-Channel**: A flexible field to further detail the acquisition channel.
5. **Campaign ID**: An exclusive identifier for the marketing campaigns attributed to account conversion. It generally originates from marketing automation systems, serving as a tool to gauge the campaign's success rate.

### Integrating Data

To exploit this feature to the fullest, merchants are advised to integrate data from their marketing automation systems into these delineated fields. 

Transmission of Account Acquisition data can be carried out <a href="https://developers.recurly.com/api-v2/v2.4/#operation/createAccountAcquisition" target="_blank">via the API</a> or entered manually in the UI. However, utilizing the API is advocated to avoid errors that are often encountered with UI data entry, besides saving time. 

On choosing to amend an account record in the UI, the following fields will appear:

<Image align="center" className="border" border={true} src="https://files.readme.io/904f1cd-Screen_Shot_2016-09-07_at_3.33.36_PM.png" />

Post the account information update with acquisition details, this data becomes visible on the account screen's right flank in Recurly. Hover over "Acquisition Data" to view the populated fields when data is available.

<Image align="center" className="border" border={true} src="https://files.readme.io/5085df9-Screen_Shot_2016-09-07_at_3.34.03_PM.png" />

# Exports

Account Acquisition Data is available via the accounts export from Recurly.

For more guidance, check out our <a href="https://docs.recurly.com/docs/accounts-export#account_acquisition_cost" target="_blank">account exports dedicated page</a>. It offers a comprehensive view on how to utilize the data in the exports table to manage your accounts effectively.
