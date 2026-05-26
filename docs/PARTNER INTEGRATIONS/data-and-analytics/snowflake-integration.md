---
title: Snowflake integration
excerpt: >-
  Elevate your data insights with Recurly's seamless integration with Snowflake,
  the leading cloud data platform.
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

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

# Definition

Recurly integrates with Snowflake to share merchant data directly. If you're a Recurly customer, contact our Account Management to enable this feature. The enablement of the Snowflake integration is managed by Recurly's Professional Services: a Recurly Solutions Manager will be assigned to gather your Snowflake credentials and configure the secure data share. With updates every hour or daily, you're assured up-to-date data. Together, Recurly and Snowflake provide a clear view of your business operations. For more details, refer to Recurly's official documentation.

# Key benefits

* **Seamless data integration**: Enjoy effortless data transition from Recurly to your Snowflake account, with Recurly managing all intricate ETL processes, eliminating manual intervention, coding, or server management.
* **Real-time insights**: Stay updated with fresh data through automatic hourly updates, ensuring your latest business metrics are always accessible.
* **Unified data experience**: Merge your Recurly data seamlessly with other datasets in Snowflake for a holistic data analysis, leveraging Snowflake's robust capabilities.
* **Enhanced reporting**: Utilize Snowflake's adaptability for custom reports and comprehensive analysis without any hassle.
* **Cost and time efficiency**: Bypass traditional ETL pipelines or third-party intermediaries to streamline processes, saving both time and resources.

# Dive into Snowflake

Snowflake is revolutionizing the way organizations harness the power of their data. With its state-of-the-art cloud data platform, businesses across the globe can seamlessly manage data warehousing, data lakes, data engineering, data science, data application development, and data sharing all within a single ecosystem. What truly sets Snowflake apart is its unmatched capability to offer near-unlimited scale, concurrency, and performance across multiple clouds and regions. Moreover, Snowflake is the backbone of the Data Cloud—a global network where data exploration, sharing, and maximizing its value is an integrated experience. Discover more about harnessing your data at Snowflake.com.

## The synergy of Snowflake and Recurly

Recurly's integration with Snowflake empowers businesses to seamlessly export their comprehensive Recurly data, as outlined in their export overview, directly into Snowflake with updates every hour. This integration allows businesses to achieve a more profound understanding of their performance by combining Recurly data with other datasets within Snowflake.

By mentioning the "comprehensive Recurly data," it provides a broader understanding that it's not limited to account-level data only.

### The edge of Recurly’s Snowflake integration

While Snowflake simplifies data-intensive report generation and application creation, importing data has always been a challenge. Traditionally, Recurly users had to either manually manage ETL pipelines or rely on third-party vendors. This integration eliminates these challenges, offering a hands-off data export experience. As Paul Snyder from The Daily Wire aptly puts it, "Having Recurly and Snowflake integrated automates our data pull process, enhancing efficiency and saving significant time."

# Integration guide

Recurly integrates with Snowflake to share merchant data directly. If you're a Recurly customer, contact our Account Management to enable this feature. With updates every hour or daily, you're assured up-to-date data. Together, Recurly and Snowflake provide a clear view of your business operations. For more details, refer to Recurly's official documentation.

# FAQs

**Q: Which tables are included in the exports?**

**A:** All <a href="https://docs.recurly.com/docs/export-overview" target="_blank">Recurly exports</a> are included, except for the deprecated exports **invoices** and **revenue recognition schedules**.

**Q: What is the schema for each table?**

**A:** The schema mirrors the <a href="https://docs.recurly.com/docs/export-overview" target="_blank">Recurly exports</a> with a few exceptions:

* All timestamps are in UTC.
* Custom fields appear as a JSON object in the `custom_fields` column instead of separate columns.
* Additional status columns on accounts and subscriptions mirror the export settings available in the UI.
* An `export_id` column ensures data integrity in the integration.

**Q: What data is included?**

**A:** All historical data is available. For instance, if there are 10 years of data in Recurly, then all 10 years will be available in the Snowflake share.

**Q: How are schema changes managed?**

**A:** New tables get added to the share, and new columns append to the end of existing tables. For any breaking changes, like a column drop, we'll communicate well in advance. During a schema change, the table might be momentarily unavailable. It's recommended to use retry logic for such scenarios.

**Q: How frequently does the data refresh?**

**A:** Data can refresh either daily or hourly.

**Q: When do daily refreshes take place, and can I adjust the timing?**

**A:** Daily refreshes start at 07:00 UTC but may take several hours to finish. At present, the refresh time isn't configurable.

**Q: Is there a guaranteed time for daily refreshes to finish?**

**A:** We don't guarantee a specific finish time for daily refreshes. If timing is critical, we suggest opting for hourly refreshes.

**Q: Can I change the time zone of the timestamps?**

**A:** All timestamps are in UTC, but they can be converted to any time zone for various analytics uses. We recommend using Snowflake's time zone conversion features for this purpose.
