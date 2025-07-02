---
title: '- Derive exchange rate for external data - Revenue Recognition Standalone'
excerpt: >-
  Automatically fetch and apply historical exchange rates for imported
  multi-currency subscriptions and invoices—no manual rates needed.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Recurly Revenue Recognition Advanced can derive the correct exchange rate for any contract or invoice created outside Recurly, based on its creation date. This removes the burden of supplying manual rates when importing or reconciling multi-currency subscription data.

# Definition

The **Derive ExRate** feature automatically retrieves the appropriate currency exchange rate—by contract date for subscriptions and invoice date for invoices, so merchants don’t need to upload rates manually for external data feeds.

# Key benefits

* **Automated accuracy**: Ensures each line uses the historical rate in effect on its creation date for precise revenue recognition.
* **Streamlined imports**: Eliminate extra columns and manual effort—just flag “Derive ExRate” and let the system handle the rest.
* **Consistent reporting**: Keeps multi-currency analytics in sync without rate discrepancies or human error.

# Key details

## Guide

### Deriving exchange rates in Recurly Revenue Recognition Advanced

Recurly Revenue Recognition Advanced offers a convenient **Derive ExRate** attribute you can enable either in your upload files or via a Data Rule. Once enabled, the system auto-populates exchange rates for every line you flag—no additional rate data required.

**Navigation**: **Setup → Attribute labels**

<Image align="center" className="border" border={true} src="https://files.readme.io/d16237a7e65513909fb2023b3fcf6f100ba183876684236f262a37d7f8b65281-1_Screenshot_.png" />

You can enable this feature using one of two methods:

#### Method 1: Using the “Derive ExRate” attribute in your upload file

1. **Include** the **Derive ExRate** column in your sales order or subscription upload.
2. **Enter** `Yes` or `Y` for any line you want the system to derive the rate.
3. **Omit** exchange rate columns—those lines will automatically pull the correct rate.

#### Method 2: Configuring a data rule

1. **Navigate** to **Transformation → Data Rules**.
2. **Create** a new rule:

   * **Name** your rule.
   * **Select** **Order Line** as the object.
3. Under **Application Attributes**, choose **Derive ExRate** and set **Value** to `Yes`.
4. **Save** the Data Rule.

<Image align="center" className="border" border={true} src="https://files.readme.io/9c6b8a88518e4be2b7d7a990132723e42e06472348b28522b36da7b8c4333e2f-image.png" />

Once saved, every uploaded line will default to **Derive ExRate = Y**, and you no longer need to supply exchange rates manually. Lines without a `Y` will assume **N** (No) by default.