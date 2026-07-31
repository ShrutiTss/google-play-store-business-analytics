# Data Dictionary

## Overview

This document describes the columns available in the Google Play Store dataset used in this project. It explains the business meaning of each field, its data type, analytical importance, and whether any preprocessing is expected before analysis.

**Dataset Version:** Google Play Store Apps (Gautham Prakash)

**Total Rows:** 2,312,944

**Total Columns:** 24


| Column                | Description                                            | Data Type | Business Category      | Cleaning Required?                | Keep?    | Notes                                           |
| --------------------- | ------------------------------------------------------ | --------- | ---------------------- | --------------------------------- | -------- | ----------------------------------------------- |
| **App Name**          | Name of the application displayed on Google Play       | String    | Identifier             | No                                | ✅        | Mainly for display and reference                |
| **App Id**            | Unique package identifier of the app                   | String    | Primary Identifier     | Check duplicates                  | ✅        | Primary key for identifying apps                |
| **Category**          | Category assigned to the app                           | String    | Business Dimension     | Check missing/inconsistent values | ✅        | One of the most important analytical dimensions |
| **Rating**            | Average user rating (0–5)                              | Float     | Performance Metric     | Validate range (0–5)              | ✅        | Measures user satisfaction                      |
| **Rating Count**      | Number of users who rated the app                      | Float     | Performance Metric     | Check anomalies                   | ✅        | Indicates confidence in ratings                 |
| **Installs**          | Install range displayed on Google Play (e.g., 1,000+)  | String    | Performance Metric     | **Yes**                           | ✅        | Needs conversion to numeric format              |
| **Minimum Installs**  | Minimum estimated install count                        | Float     | Performance Metric     | Validate values                   | ✅        | Better metric than Install Range for analysis   |
| **Maximum Installs**  | Maximum estimated install count                        | Integer   | Performance Metric     | Validate values                   | ✅        | Useful for upper-bound analysis                 |
| **Free**              | Indicates whether the app is free                      | Boolean   | Monetization           | No                                | ✅        | Useful for Free vs Paid analysis                |
| **Price**             | Price of the application                               | Float     | Monetization           | Check negatives/outliers          | ✅        | Applicable mainly to paid apps                  |
| **Currency**          | Currency used for pricing                              | String    | Monetization           | Check consistency                 | ✅        | Most values expected to be USD                  |
| **Size**              | Application size                                       | String    | Technical Metric       | **Yes**                           | ✅        | Requires conversion to numeric units            |
| **Minimum Android**   | Minimum Android version required                       | String    | Platform Compatibility | Standardize versions              | ✅        | Useful for developer recommendations            |
| **Developer Id**      | Unique identifier for the developer                    | String    | Developer Information  | Check duplicates                  | ✅        | Used for developer-level analysis               |
| **Developer Website** | Developer's official website                           | String    | Metadata               | Handle missing values             | ⚠️ Maybe | May not be useful for business analytics        |
| **Developer Email**   | Contact email of the developer                         | String    | Metadata               | Handle missing values             | ⚠️ Maybe | Usually not required for analysis               |
| **Released**          | Original release date of the application               | String    | Time Dimension         | Convert to Date                   | ✅        | Enables launch timeline analysis                |
| **Last Updated**      | Date when the app was last updated                     | String    | Time Dimension         | Convert to Date                   | ✅        | Useful for maintenance analysis                 |
| **Content Rating**    | Target audience (Everyone, Teen, etc.)                 | String    | Business Dimension     | Check consistency                 | ✅        | Useful for audience segmentation                |
| **Privacy Policy**    | Privacy policy URL                                     | String    | Metadata               | Handle missing values             | ⚠️ Maybe | Unlikely to be used in analytics                |
| **Ad Supported**      | Indicates whether the app contains ads                 | Boolean   | Monetization           | No                                | ✅        | Helps analyze monetization strategies           |
| **In App Purchases**  | Indicates whether the app offers in-app purchases      | Boolean   | Monetization           | No                                | ✅        | Important monetization feature                  |
| **Editors Choice**    | Indicates whether the app is marked as Editor's Choice | Boolean   | Quality Indicator      | No                                | ✅        | Useful for premium app comparisons              |
| **Scraped Time**      | Date and time when the dataset was collected           | String    | Metadata               | Convert to DateTime               | ✅        | Important for understanding data freshness      |
