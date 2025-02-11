---
title: Analytics Dashboard UI Comparison
fullscreen: false
hidden: true
metadata:
  title: ''
  description: ''
---
Recurly has updated the look and feel of the analytics dashboards into new, modern versions. While the Modern versions have formatting, dashboard layouts, and color palette changes, they still retains the Classic version's  functionality.  However, there are new features too. 

This document includes the following two sections: 

- **Dashboard UI Features At-A-Glance** provides a short description of the changed/new features
- **Dashboard UI Features in Detail** provides a detailed description and screenshots of the changed/new features


# Dashboard UI Features At-A-Glance

The rows in the following table briefly identify the new UI features available in the Modern Looker-enhanced versions of the Recurly Analytics dashboards. This table gives you a quick "look at-a-glance" at the features. These features greatly improve on those offered in the Classic versions and allow you to filter, organize, and access reliable details, pertinent to your business’s performance, faster and more efficiently.  An individual section that covers each of these UI features,  follows this table. Each topic provides details and screenshots that describe how to use each feature.

## Modern Analytics Dashboard UI/UX Changes


[block:parameters]
{
  "data": {
    "h-0": "UI Features",
    "h-1": "Modern Dashboards",
    "h-2": "Classic Dashboards",
    "0-0": "Actions",
    "0-1": "New Actions area has clear cache, refresh data, download data, and track completion time for refresh options",
    "0-2": "Actions area was not available in the Classic version.",
    "1-0": "Clear Cache",
    "1-1": "Request Clear Cache & Refresh:<ul>\n<li>Any time from Actions Area</li>\n<li>Any time from widget drop<br>\ndowns</li>\n</ul>",
    "1-2": "Clear Cache & Refresh was available in the Classic version from the upper right corner of those dashboards..",
    "2-0": "Currency Filters",
    "2-1": "Currency Filters always appear, even if only one currency option is available.",
    "2-2": "Currency Filters only displayed if more than one currency is available.",
    "3-0": "Date Range",
    "3-1": "Specify Date Range:<ul>\n<li>Default to the last 12 months</li>\n<li>Sophisticated searches</li>\n<li>Granular filtering</li>\n</ul>",
    "3-2": "Specify Date Range:<ul>\n<li>Default to the last 18 months</li>\n<li>Simplistic setting &#x26; choices</li>\n</ul>",
    "4-0": "Download Data",
    "4-1": "Download Data in multiple formats:  \nTXT, to Excel spreadsheet, CSV, JSON, HTML, Markdown, and PNG",
    "4-2": "Download Data in one format:  \nCSV",
    "5-0": "Dunning Campaigns",
    "5-1": "Dunning Effectiveness dashboard:<ul>\n<li>Select appropriate dunning version from views at the top of the dashboard.</li>\n<li>All Dunning Campaign views show summary of all campaign</li>\n<li>Individual Dunning Campaign views show details from individual campaigns</li>\n</ul>",
    "5-2": "Dunning Effectiveness dashboard: Dunning version selection was localized to the chart component to which it applied.  \nDoes not have campaigns",
    "6-0": "Ellipses",
    "6-1": "Ellipses in widgets provide drop down menu options, use:<ul>\n<li>Vertical Ellipses to Clear Cache and Refresh Data &#x26; to Download Data</li>\n<li>Horizontal Ellipses to drill into MRR Account Details</li>\n</ul>",
    "6-2": "Ellipses with dropdown menu choices are not available in the Classic version.",
    "7-0": "Filters",
    "7-1": "Filters are grouped at the top left area of all dashboards and multiple view dashboards.",
    "7-2": "Filters related to specific sections of the dashboards are found at that location.",
    "8-0": "Hover Text",
    "8-1": "Hover Text shows dates / totals in individual messages for each selected segment of bar or line charts.",
    "8-2": "Hover Text shows dates / totals in one message for all segments of bar or line charts.",
    "9-0": "KPIs",
    "9-1": "Key Performance Indicators (KIPs) show:<ul>\n<li>Active Totals</li>\n<li>Last Month</li>\n<li>Previous Month</li>\n<li>3 Months Ago</li>\n<li>1 Year Ago</li>\n</ul>",
    "9-2": "Key Performance Indicators (KIPs) show:<ul>\n<li>Active Totals</li>\n<li>Previous Month</li>\n<li>3 Months Ago</li>\n<li>1 Year Ago</li>\n</ul>",
    "10-0": "MRR Drill Down",
    "10-1": "Monthly Recurring Revenue (MRR) Drill Down option lets you view the MRR Accounts Drill report.",
    "10-2": "Monthly Recurring Revenue (MRR) Drill Down option is not available in the Classic version.",
    "11-0": "Multiple Daily Uploads",
    "11-1": "Automatic Data Uploads occur multiple times a day. In addition, request a Clear Cache & Refresh from the Actions Area to start an upload.",
    "11-2": "Data Uploads occurred once a day in the Classic version.",
    "12-0": "Select Plans",
    "12-1": "Ability to Select, contrast, compare more than 2 plans. Can compare up to 12 plans at a time.",
    "12-2": "Data Uploads occurred once a day in the Classic version.  \nAbility to Select and compare 2 Plan",
    "13-0": "Sort / Hide Data",
    "13-1": "Sort details in widgets:<ul>\n<li>Show/Hide details on bar, line, and pie charts using the widget’s color-coded legends</li>\n<li>Sort details on tables in ascending or descending order.</li>\n</ul>",
    "13-2": "Sort/Hide Data is not available in the Classic version."
  },
  "cols": 3,
  "rows": 14,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


# Dashboard UI Feature in Detail

The following topics describe in detail, the new and enhanced UI features available in the Modern Looker-enhanced versions of the Recurly Analytics dashboards. Each topic tell you exactly how to use the new features and  includes instructions and screenshots to help you located new areas on the dashboards.

## Actions

The Recurly Looker-enhanced dashboards provide you with a set of actions at the top right corner of the dashboards:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5357e17-analytics_hide_filters_option.png",
        "analytics hide filters  option.png",
        540,
        130,
        "#f4f6f8"
      ],
      "caption": "Actions Options Area"
    }
  ]
}
[/block]
The actions include the following features:

- Time from the last requested clear cache/refresh data beginning from 1m ago up to four hours.
- Reload action will track time from the last time you refreshed your data. It then resets the counter. This tells you how current your data is from the last refresh.
- Hide Filter action shown as three vertical lines that hide the Filters area that displays in the top left corner of the dashboard.
- Dashboard actions allow you to either clear the cache and refresh the data, view a popup Download Dashboard from where you can select a download format, page size, or specify how to arrange downloaded data, or reset filters to their default settings.
- Open Folders action all

## Clear Cache and Refresh Data

In addition to the regular updates performed by Recurly, you can poll for updates from multiple places on the dashboard using the Clear Cache and Refresh Data feature. 

Clear cache and refresh from:

- Actions area ->Dashboard Actions (vertical ellipse) -> requests  new Clear cache and refresh data. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c82358e-download_from_actions.png",
        "download from actions.png",
        598,
        398,
        "#f2f3f4"
      ],
      "caption": "Clear Cache and Refresh from Actions Area"
    }
  ]
}
[/block]
   This action requests a full refresh of all data.

- Vertical ellipses in the top right corner of all widgets including charts, tables, and key performance indicators.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/623c09d-download_link_from_widgets.png",
        "download link from widgets.png",
        448,
        306,
        "#eff1f3"
      ],
      "caption": "Clear Cache and Refresh from a Widget"
    }
  ]
}
[/block]
    This action updates the widget with the most current information available from the last clear cache.

## Date Range

The Recurly Looker-enhanced dashboards provide a more sophisticated option for selecting your date range settings. You still have the option to set your date range within an 18-month timeframe. However, there are two new dropdown menus that include more granular options that will make it easier for you to refine the date range that you select.

From the Filters area, select Date Range -> “Is in the last 18 months” and choose an option from the "Is in the last” dropdown. Then choose an option from the “months” dropdown. The default is: **In the last 18 months**. Modify the default to meet your needs and set another date range.  

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8706534-analytics_comparison_date_range_.png",
        "analytics comparison date range .png",
        1606,
        1252,
        "#f7f8f9"
      ],
      "caption": "Modern Date Range Filters"
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
## Download Data

You can download data from the Modern (Looker-enhanced) versions of the Analytics dashboards in multiple formats:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/43fbcd1-analytics_dashboard_download_formats.png",
        "analytics dashboard download formats.png",
        1660,
        1332,
        "#f3f4f6"
      ],
      "caption": "Modern Dashboard Download Formats"
    }
  ]
}
[/block]
You can select a download format from all widgets on the dashboard including bar, line, or pie charts or Key Performance Indicators (KPI) widgets.

Note: Download data from the Classic (previous) versions of the Analytics dashboards were in CSV format only. These Download CSV links are still available and  located across from the dashboard’s section names.

## Dunning Campaigns

The modern Looker-enhanced version of the Dunning Effectiveness dashboard allows you to view a summary of invoice, revenue, or subscriptions data for either all dunning campaigns/plans by selecting from the widget on the left or for any individual dunning campaigns or a version of a campaign by selecting from the widget on the right as shown in the following screenshot. 

[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ef32113-analytics_comparison_of_all_and_individual_campaigns.png",
        "analytics comparison of all and individual campaigns.png",
        1724,
        214,
        "#f7f8f9"
      ],
      "caption": "Dunning Campaign Views"
    }
  ]
}
[/block]
Clicking any of the links shown at the top of the dashboard to display a new page with its own filters, widgets, and details specific to the selected campaign.

## Ellipses (Vertical/Horizontal)

You can use ellipses on the Recurly dashboards to access the following features:

**Vertical Ellipses** are shown in:

- Actions area to clear cache and refresh data, download data, and refresh filters
- Dashboard widgets to download data and clear cache and refresh data 
- Dashboard tables to download data, auto size all columns, resize all column widths, and clear cache and refresh data

The **Horizontal Ellipse** is shown in columns on the Monthly Recurring Revenue (MRR) dashboard. Use them to access the link to MRR Accounts Drill reports.

## Filters

In the modern version of the Looker-enabled dashboards, filters have moved from embedded within individual widgets to a unique Filter area in the top left corner of the dashboards. 

### Use Filters 

Filters specify the settings that will apply to the dashboard by clicking an option or using a dropdown menu, in the Filter area. For example, choosing Monthly as your Select Timeframe option and a Plans option from the Select Plans dropdown menu means that you want your Plans data to be calculated and display for each month in your specified timeframe. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/97a043c-analytics_compair_filter_with_dropdown.png",
        "analytics compair filter with dropdown.png",
        1516,
        564,
        "#f1f3f6"
      ],
      "caption": "Subscriptions Filtered by Plans"
    }
  ]
}
[/block]
### Hide Filters 

The Hide filter option removes the Filter area of the top left corner of the dashboard.

1.  View filters on the dashboard.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e864e53-analytics_comaptison_filters_.png",
        "analytics comaptison filters .png",
        1528,
        174,
        "#edf1f6"
      ],
      "caption": "Filter Area"
    }
  ]
}
[/block]
2.  If you do not want them to display, click the horizontal bar icon in the Actions area to select the Hide filters option.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f6f6642-analytics_hide_filters_option.png",
        "analytics hide filters  option.png",
        540,
        130,
        "#f4f6f8"
      ],
      "caption": "Action Area Shows Horizontal Bars"
    }
  ]
}
[/block]
3.  Once you select Hide Filters, the Filter area will no longer be visible from the dashboard.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cabf880-analytics_comaprison_hidden_filter_area.png",
        "analytics comaprison hidden filter area.png",
        1560,
        566,
        "#f8f9f9"
      ],
      "caption": "Filter Area Hidden"
    }
  ]
}
[/block]
### Reset Filters 

Use the Reset Filter option to return your filter choices to their default settings. To do this, go to the Actions area in the top right corner of the dashboard, click Download actions -> Reset Filters. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6c1d039-download_from_actions.png",
        "download from actions.png",
        598,
        398,
        "#f2f3f4"
      ],
      "caption": "Reset Filters Option"
    }
  ]
}
[/block]
## Hover Text

The Recurly Looker-enhanced Hover text shows details for individual segments or points on charts that you hover over with your mouse. This includes bar, line, and pie charts. For example, if you hover over a specific segment on a bar chart as shown in the following screenshot, the hover text will display details for that selected plan in that specific date range. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1a2895b-analytics_comparison_sorted_bar_chart.png",
        "analytics comparison sorted bar chart.png",
        2538,
        1124,
        "#bea5b4"
      ],
      "caption": "Segment of a Bar Chart with Hover Text"
    }
  ]
}
[/block]
### KPIs

The Key Performance Indicators (KPIs) are shown in a separate widget, usually at the top or side of the dashboard. This widget features values at a glance, for the current month to date compared to the last month, previous month, three months ago, up to one year ago. These values give you a better sense of how the indicators are trending. See following screenshot:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/33aa788-billings_totals_overview.png",
        "billings totals overview.png",
        2604,
        362,
        "#f5f6f6"
      ],
      "caption": "Modern Dashboard Key Performance Indicators"
    }
  ]
}
[/block]
## MRR Drill Down

The Monthly Recurring Revenue (MRR) drill down feature allows you to view additional details about your accounts from the MRR dashboard widgets. This dashboard tracks totals for Monthly Recurring Revenue and Monthly Recurring Revenue Growth. 

1.  Click the desired bar to select the See accounts option and then click “See accounts” to view that account’s MRR Accounts Drill
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4835115-analytics_comparison_mrr_drill_down_bar_chart.png",
        "analytics comparison mrr drill down bar chart.png",
        2444,
        804,
        "#dbdbd7"
      ],
      "caption": "MRR Accounts Drill Down Option"
    }
  ]
}
[/block]
2.  Click the horizontal ellipse, in the desired table cell, to display the See accounts option and then click “See accounts” to view that account’s MRR Accounts Drill.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/72499fd-analytics_comparison_mrr_drill_down_table.png",
        "analytics comparison mrr drill down table.png",
        608,
        370,
        "#edeff0"
      ],
      "caption": "Horizontal Ellipse in Far right Column"
    }
  ]
}
[/block]
    The MRR Accounts Drill displays account-level details such as: buckets, account codes, email addresses, date accounts were created, names, and either the Total MRR or Delta MRR.

## Multiple Uploads per Day

Recurly automatically updates your data during regular intervals, each day. Check the widget at the bottom of the dashboards to see the last time an update occurred.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/75ecb3a-billings_dat_update_widget.png",
        "billings dat update widget.png",
        642,
        130,
        "#f9fafa"
      ],
      "caption": "Widget Showing Latest Completed Upload"
    }
  ]
}
[/block]
Also, you can poll for an update clicking the Clear Cache and Refresh Data option from the Actions area ->Dashboard Actions dropdown in the top right corner of the dashboard. 

## Select Plans

Although you select/set up plans when you create your account, you can specify which plans you want to track in the dashboards by using the Select Plans filter.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/53ee4e6-analytics_compair_filter_with_dropdown.png",
        "analytics compair filter with dropdown.png",
        1516,
        564,
        "#f1f3f6"
      ],
      "caption": "Select Top 5 Plans from Filter"
    }
  ]
}
[/block]
Making your choice in the Select Plans filter narrows the filter options available in the Plans filter. In the Plans filter dropdown menu, you can check the box for any plans in the preset plans list. For example, if you choose the Top 5 Plans option from the Select Plans dropdown menu, those five plans will be listed in the Plans filter dropdown menu as shown in the following screenshot:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2a3a94c-analytics_comparison_plans_filter.png",
        "analytics comparison plans filter.png",
        1330,
        590,
        "#f4f5f7"
      ],
      "caption": "Filtered Plans from Select Plans List"
    }
  ]
}
[/block]
You can then check the box next to the desired plans and Recurly will calculate the latest details. You can use these statistics to compare plans. You can either select two plans, a set of plans, or all plans. Recurly will provide comparison data for up to twelve plans. 

## Sort/Hide Data

The Recurly Looker-enhanced version of the Analytics dashboards provides two different ways for you to sort your data from within the dashboards. 

### Sort Data in Charts

Use the color-coded legend on the bar, pie, or line chart to hide or reveal data. For example, in the following screenshot you see a bar chart with corresponding colors for each bar segment in the legend at the bottom of the widget.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1d11c32-analytics_comparison_unsorted_bar_chart.png",
        "analytics comparison unsorted bar chart.png",
        2532,
        1116,
        "#c7bdbc"
      ],
      "caption": "Bar Chart with Color-Coded Segments and Legends"
    }
  ]
}
[/block]
This bar chart shows the five top five plans that you selected in the Select Plans filter. You can compare or view any combination of these selected plans. For example, clicking the corresponding color in the legend will gray out that color in the legend and remove the color’s corresponding segment from the bar chart. In the following screenshot, three colors have been clicked and their corresponding data hidden, so you will only see the data for the two remaining colors (plans).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/913170f-analytics_comparison_sorted_bar_chart.png",
        "analytics comparison sorted bar chart.png",
        2538,
        1124,
        "#bea5b4"
      ],
      "caption": "Grayed out Colors in Legend Hidden in Chart"
    }
  ]
}
[/block]
You need only reselect the colors to cause the data to reappear. This feature works the same way in line and pie charts.

### Sort Data in Tables

Use  arrow in the top right column of Details (tables) to view the data in a table in either the ascending or descending order. Click the up arrow over the right  column of the table to change the order.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c83eeb2-analytics_comparison_sort_on_a_table.png",
        "analytics comparison sort on a table.png",
        730,
        486,
        "#f0f1f1"
      ],
      "caption": "Changing the Ascending/Descending Order in Tables"
    }
  ]
}
[/block]