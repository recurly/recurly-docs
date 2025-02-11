---
title: Analytics Dashboard Revamp - Changelog
fullscreen: false
hidden: true
metadata:
  title: ''
  description: ''
---
## Global Changes

This section covers changes that span all of the analytics dashboards. 

### Feature Enhancements


| Modern                                                                                                                                                                   | Classic                                                                  |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------- |
| <ul> <li>Data updates every hour for all dashboards except Subscribers and MRR (still daily)</li> </ul>                                                                  | <ul> <li>Data updates daily based on configured site timezone</li> </ul> |
| <ul> <li>Ability to download dashboard components (e.g. charts, tables) in | Modern                                                                                                                                       | Classic                                                                                                      |
| :------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------- |
| <ul> <li>All filters are at top of the dashboard.</li> </ul>                                                                                 | <ul> <li>Filters that pertain to specific sections of the dashboards are placed at that location.</li> </ul> |
| <ul> <li>Changing dashboard filters requires user to click ‘reload’ button in top right hand corner to refresh the dashboard data</li> </ul> | <ul> <li>Changing any filter immediately causes the dashboard data to refresh</li> </ul>                     |
| <ul> <li>Currency filters always appear (even if only one option)</li> </ul>                                                                 | <ul> <li>Currency filters only appeared if more than one currency available.</li> </ul>                      |
| <ul> <li>Date ranges default to last 12 months</li> </ul>                                                                                    | <ul> <li>Date ranges default to last 18 months</li> </ul>                                                    |                                                                          | <ul> <li>Classic look and feel</li> </ul>                                |

### UI / UX Modifications


[block:parameters]
{
  "data": {
    "h-0": "Modern",
    "h-1": "Classic",
    "1-0": "* Changing dashboard filters requires user to click ‘reload’ button in top right hand corner to refresh the dashboard data",
    "1-1": "* Changing any filter immediately causes the dashboard data to refresh",
    "2-0": "* Currency filters always appear (even if only one option)",
    "2-1": "* Currency filters only appeared if more than one currency available.",
    "3-0": "* Date ranges default to last 12 months",
    "0-0": "* All filters are at top of the dashboard.",
    "0-1": "* Filters that pertain to specific sections of the dashboards are placed at that location.",
    "3-1": "* Date ranges default to last 18 months"
  },
  "cols": 2,
  "rows": 4
}
[/block]




[block:callout]
| Modern                                                                            | Classic |
| :-------------------------------------------------------------------------------- | :------ |
| <ul> <li>Percent change and dates not available on the KPI cards</li> </ul>       |         |
| <ul> <li>Total Subscriptions compo| Modern                                                                                                                                                    | Classic                                                                                                                           |
| :--------------------------------------------------------------------------------------------------------------------------------------------------| Modern                                                                                                                                    | Classic                                                                  |
| :---------------------------------------------------------------------------------------------------------------------------------------- | :----------------------| Modern                                                                                                                                                                                                      | Classic                                       |
| :---------------------------------------------------------------------------------------------------------------------------------------------| Modern                                                                                 | Classic                                                                  |
| :------------------------------------------------------------------------------------- | :---------------------------------------------------------------| Modern                                                                                                     | Classic                                                                        |
| :--------------------------------------------------------------------------------------------------------- | :-------------------| Modern                                                                                                  | Classic                                                                                                |
| :------------------------------------------------------------------------------------------------------ | :----------------------| Modern                                                                                    | Classic                                                                                                              |
| :---------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------- |
| <ul> <li>Removed ability to filter Subscriptions and Dunning Lifecycle by Plan</li> </ul> | <ul> <li>Filter provided to select a plan on the 'Subscriptions Saved' and 'Dunning Lifecycle' components</li> </ul> |
| <ul> <li>Removed dunning version configuration settings</li> </ul>                        | <ul> <li>Displayed configuration information for the selected dunning version</li> </ul>                             |xperiences. To switch back to Classic, simply remove the '_v3' from the URL and refresh the page. \n\n**Example**\nIf viewing the 'Monthly Recurring Revenue' dashboard and the URL is 'http://subdomain.recurly.com/analytics_v3/mrr', change the URL to 'http://subdomain.recurly.com/analytics/mrr' to view the Classic version of the dashboard"
}
[/block]




[block:callout]
{
  "type": "danger",
  "title": "Current Known Issues",
  "body": "* Some dashboard drop-down filters (Currency, Dunning Versions) have some latency before displaying values.\n* Selecting the 'Any Value' option on the Currency filters will return erroneous data. This option is not needed and will be removed in a later iteration.\n* Recovered Revenue  dashboard exhibits long load times on KPIs and data table"
}
[/block]




## Changes by Dashboard

## Overview Dashboard
### Functionality Removed


[block:parameters]
{
  "data": {
    "h-0": "Modern",
    "h-1": "Classic",
    "0-0": "* Percent change and dates not available on the KPI cards",
    "1-0": "* Total Subscriptions components doesn't show 'All other' plans",
    "0-1": "",
    "1-1": ""
  },
  "cols": 2,
  "rows": 2
}
[/block]

### Feature Enhancements


[block:parameters]
{
  "data": {
    "h-0": "Modern",
    "h-1": "Classic",
    "0-0": "* KPIs now all feature values for the current month to date compared to the previous month to give a better sense how KPIs are trending",
    "0-1": "* Some KPIs focused on month to date but others provided data for the previous month compared to two months ago"
  },
  "cols": 2,
  "rows": 1
}
[/block]

## Churn Analysis
### UI / UX Modifications


[block:parameters]
{
  "data": {
    "h-0": "Modern",
    "h-1": "Classic",
    "0-0": "* Subscription Churn Reasons chart shows percentage and absolute side by side without the need to toggle back and forth",
    "0-1": "* Must toggle percentage vs absolute to see either one"
  },
  "cols": 2,
  "rows": 1
}
[/block]

## Monthly Recurring Revenue (MRR)
### Feature Enhancements


[block:parameters]
{
  "data": {
    "h-0": "Modern",
    "h-1": "Classic",
    "0-0": "* Uses new business logic to provide a better reflection of MRR Totals and Growth. See [here](https://docs.recurly.com/docs/monthly-recurring-revenue-modern-beta) for details",
    "0-1": "* Uses older business logic"
  },
  "cols": 2,
  "rows": 1
}
[/block]

## Subscriber Retention
### Functionality Removed


[block:parameters]
{
  "data": {
    "h-0": "Modern",
    "h-1": "Classic",
    "0-0": "* No longer able to view retention metrics at plan level granularity",
    "0-1": "* Filter is provided to view retention metrics by plan"
  },
  "cols": 2,
  "rows": 1
}
[/block]

## Dunning Effectiveness
### Feature Enhancements


[block:parameters]
{
  "data": {
    "h-0": "Modern",
    "h-1": "Classic",
    "0-0": "* Added additional visualizations to depict the dunning lifecycle: Funnel and Water-rise",
    "0-1": "* Only provides dunning lifecycle visualization as bar chart"
  },
  "cols": 2,
  "rows": 1
}
[/block]

### UI / UX Modifications


[block:parameters]
{
  "data": {
    "0-0": "* Dunning version selection is now at the top of the dashboard with all other filters",
    "0-1": "* Dunning version selection was localized to the chart component to which it applied",
    "h-0": "Modern",
    "h-1": "Classic"
  },
  "cols": 2,
  "rows": 1
}
[/block]

### Functionality Removed


[block:parameters]
{
  "data": {
    "h-0": "Modern",
    "h-1": "Classic",
    "0-0": "* Removed ability to filter Subscriptions and Dunning Lifecycle by Plan",
    "0-1": "* Filter provided to select a plan on the 'Subscriptions Saved' and 'Dunning Lifecycle' components",
    "1-0": "* Removed dunning version configuration settings",
    "1-1": "* Displayed configuration information for the selected dunning version"
  },
  "cols": 2,
  "rows": 2
}
[/block]


## Recovered Revenue
No changes aside from those noted in  [global](page:analytics-dashboard-revamp-changelog#section-global-changes)

## Billings
No changes aside from those noted in  [global](page:analytics-dashboard-revamp-changelog#section-global-changes)

## Subscribers
No changes aside from those noted in  [global](page:analytics-dashboard-revamp-changelog#section-global-changes)

## Trial Performance
No changes aside from those noted in  [global](page:analytics-dashboard-revamp-changelog#section-global-changes)

## Plans
Revamped dashboard will be added to early access at a subsequent date. Current experience remains as Classic

## Plan Performance
Ability to compare and contrast more than two plans. Classic only allows comparison of two.