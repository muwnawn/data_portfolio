---
title: "App Data Analysis by Python"
date: 2022-11-20
last_modified_at: 2022-11-20T11:59:26-04:00
tags: 
  - data_analysis
  - data_visualisation
  - python
header:
  image: "/images/DA_img_5.png"
  teaser: "/images/DA_img_5.png"
excerpt: "Data Analysis, Data Visualisation, Python"
classes: wide
mathjax: "true"
---
# Description
**What** - Profitable App Profiles for the App Store and Google Play Markets. This project's aim is to find mobile app profiles that are profitable for the App Store and Google Play markets. 

**Who** - Team of developers use this report to understand what kinds of apps are likely to attract more users and make data-driven decisions with respect to the kind of apps they build.

**How** - There are 2 main steps which are describe more detail in "Output" part below
- Step 1: Data Cleaning (Deleting Wrong Data, Removing Duplicate Entries, Removing Inappropriate Records)
- Step 2: Data Analysis (Most Common Apps by Genre, Most Popular Apps by Genre)

# Input
A data set containing data about approximately ten thousand Android apps from Google Play. You can find more details and download the data set from this [kaggle link](https://www.kaggle.com/datasets/lava18/google-play-store-apps).

A data set containing data about approximately seven thousand iOS apps from the App Store. You can find more details and download the data set from this [kaggle link](https://www.kaggle.com/datasets/ramamet4/app-store-apple-data-set-10k-apps).

# Output
## Step 1: Data Cleaning
### 1.1. Initial Data Checks
- **Colunm and Row Count**
- **Unique Case Identifier Variable**
  - Print a few duplicate rows to confirm.
- **Inappropriate Records**
  - Removing Non-English Apps: The company develops English apps therefore only the apps that are designed for an English-speaking audience are analyzed.
  - Isolating Free Apps: The company only build apps that are free to download and install, and main source of revenue consists of in-app ads.


### 1.2. Inspect Variable Types
- **Undesirable Column Types**

### 1.3. Specify Missing Values
- **Presence of missing values**
- **Variables with many missing values**

## Step 2: Data Analysis
### 2.1. Most Common Apps by Genre
### 2.2. Most Popular Apps by Genre
