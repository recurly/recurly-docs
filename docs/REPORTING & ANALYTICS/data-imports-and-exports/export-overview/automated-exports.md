---
title: Automated exports
excerpt: >-
  Discover the efficiency and ease of automating your Recurly data exports,
  allowing for streamlined data management and enhanced business operations.
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

### Prerequisites

* Necessary configurations set up in the "Integrations" section of the Recurly admin console.
* Users possessing the "Integrations" role to access the "Automated Exports" UI. A few admin level exports will also require both the "Admin" and "Integrations" roles.
* Familiarity with the Recurly API to retrieve the daily exports.

### Limitations

* Not available out of the sandbox mode.
* The service offers the complete data set only, without the option for partial data sets based on status filters available in the Exports UI.
* A newly available version of an export does not automatically update in your existing configuration; reconfiguration is required to access the latest version.
* A given automated export file will not be accessible via Recurly API, 60 days after its creation.

# Definition

Automated Exports is a Recurly feature that facilitates scheduled data exports, enabling businesses to automatically synchronize data between Recurly and their data warehouse. It offers a broader set of attributes for each object compared to what is available through individual API objects, enhancing data detail and availability for analysis.

# Key benefits

* **Automated process**: Schedule your data exports to run automatically, saving time and reducing manual effort.
* **Detailed data**: Gain access to a comprehensive set of attributes for each object, offering richer data for your analyses.
* **Smooth transition from sandbox to production**: Retain your export schedules configured in sandbox mode when you switch to a production environment, avoiding reconfiguration hassles.
* **Secure data retrieval**: Utilize secure, temporary URLs to safely access your exported data.
* **Historical data access**: Retain access to each export for a duration of 60 days, facilitating historical data analysis.

# Automated exports

Automated Exports is a crucial tool designed to align your data warehouse seamlessly with the data available from Recurly, without the necessity to log into the admin console frequently. This feature is well-suited for businesses aiming for an automated and efficient data management process. Below, we delve deeper into the aspects of availability, configuration, and accessing the rich data sets available through this service.

For a full list of available exports, see [here](https://docs.recurly.com/docs/export-overview#exports-overview).

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Download Button</title>
    <style>
        .download-button {
            display: inline-block;
            padding: 5px 10px;
            text-align: center;
            text-decoration: none;
            color: #1C2833FF; 
            background-color: #F8F8F8FF; 
            border-radius: 5px;
            font-weight: normal;
            transition: background-color 0.5s ease, transform 0.3s ease;
          	transition: 0.4s !important;
            font-family: 'Proxima-nova', Arial, sans-serif;
            max-width: 100%; 
        }

        .download-button:hover {
            background-color: #FFFFFFFF; 
            transform: scale(1.02); 
        }
      	a:hover {
          	color: #888888FF;
          	text-decoration: underline !important;
        }
      </style>
</head>
<body>
    <a href="https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx" class="download-button">Download our complete export schema</a>
</body>
</html>
`}</HTMLBlock>

## Configuration

Initiate the configuration of automated exports through the "Integrations" section, accessible only to users holding the "Integrations" role. Although the configurations can be set up and deleted via the admin console, the daily retrieval of exports necessitates usage of the Recurly API, securing a broader and detailed data set.

**Note:** Multiple versions of the same export are allowed.

## New versions

Stay updated by utilizing the newest versions available in the Automated Exports configuration. However, note that the update to the latest version is not automated and demands manual reconfiguration.

## Details about the data made available

Benefit from a service that runs nightly, encompassing the entire previous day's data from each chosen export, abiding by the set time-range filters. It is crucial to acknowledge the service's focus on offering the complete data set, thus not providing partial sets based on various status filters.

## Accessing the data

Retrieve your detailed data exports securely using a private API key to poll a specified endpoint on the Recurly API. The retrieval grants you a secure and temporary URL, active for 60 minutes, directing to the data export's secure storage location.

**Recommendation:** To ensure the data's readiness for download, initiate the poll approximately 2 hours post the export run. Keep in mind that the exports remain accessible for 60 days post-creation, allowing for an extensive analysis window.

For an efficient, secure, and automated data export process, leverage Recurly's Automated Exports feature, enhancing your business operations through streamlined data management.

# **Advanced automated exports guide**

### **Step 1: Verifying your subscription plan**

* **Objective:** Ensure that you are subscribed to a plan that grants access to the Automated Exports feature.
* **Action:** Verify your subscription to the Recurly Professional or Elite plan.
* **Tip:** Utilize the sandbox mode for a trial run of the feature.

### **Step 2: Setting up user roles**

* **Objective:** Set up appropriate user roles to manage access to the Automated Exports UI.
* **Action:** Assign the "Integrations" role to the necessary team members.
* **Tip:** Proper role assignment helps in managing user permissions efficiently.

### **Step 3: Navigating to the integration section**

* **Objective:** Learn to navigate to the integration section to access Automated Exports settings.
* **Action:** Open the admin console and select the "Integrations" section from the navigation panel.
* **Tip:** Familiarize yourself with the admin console to streamline the navigation process.

### **Step 4: Configuring automated exports**

* **Objective:** Set up and configure your automated exports.
* **Action:** In the "Integrations" section, set up your export configurations, including scheduling and attribute selections.
* **Tip:** Regularly update your configurations to match your current data requirements.

### **Step 5: Updating export versions**

* **Objective:** Keep your exports updated with the latest versions.
* **Action:** Delete outdated configurations and re-add them using the newest version available.
* **Tip:** Regular updates ensure you have access to the most recent and relevant features.

### **Step 6: Understanding the data available**

* **Objective:** Understand the data available through automated exports.
* **Action:** Explore the details of the data available, including time range filters and the data attributes accessible through this feature.
* **Tip:** Leveraging the right data attributes can offer deeper insights and facilitate data analysis.

### **Step 7: Accessing the data**

* **Objective:** Learn how to access the data efficiently.
* **Action:** Utilize your private API key to poll the endpoint on the Recurly API, generating a secure URL for data access.
* **Tip:** Ensure timely data retrieval within the 60-minute window of URL activation to maintain data security.

### **Step 8: Retrieving the exported data**

* **Objective:** Successfully retrieve the data exported through the service.
* **Action:** Poll the specified endpoints approximately 2 hours after the export runs to check the data readiness for download.
* **Tip:** Regular checks can prevent missing out on data due to the 404 response received when the data is not ready.

### **Step 9: Automating data retrieval**

* **Objective:** Streamline operations through data retrieval automation.
* **Action:** Learn to automate the data retrieval process to save time and reduce manual effort.
* **Tip:** Utilizing APIs for automation can bring in efficiency and speed in the data retrieval process.

### **Step 10: Maintenance and support**

* **Objective:** Understand how to maintain your automated export configurations and where to find support.
* **Action:** Learn the best practices for maintaining your configurations and accessing Recurly support for assistance.
* **Tip:** Regular maintenance ensures smooth operations and quick resolution of any issues.
