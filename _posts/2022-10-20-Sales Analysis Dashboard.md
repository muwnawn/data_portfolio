---
title: "Sales Analysis Dashboard"
date: 2022-10-20
last_modified_at: 2022-11-15T11:59:26-04:00
tags: 
  - data_visualisation
  - powerbi
header:
  image: "/images/DA_img_5.png"
  teaser: "/images/DA_img_5.png"
excerpt: "Data Visualisation, Data Preparation, Power BI, Power Query, DAX"
classes: wide
mathjax: "true"
---

## Description
**What** - A monthly Sales Analysis dashboard focusing on sales, margins, volumes and conversions summarizes the sales performance for the month which helps to determine the effectiveness of the sales strategy. Usually, the first page of a dashboard contains the most important KPI’s and the others  show the trends and figures.

**Who** - Sales teams, mostly c-level executives, use these reports to find trends and insights to improve the quality of their products and services. 

**Why** - A month dashboard provides a broader feeling of how the sales reps are performing in the long run. It focuses on more long-term measurement of KPIs such as sales cycle length, conversion report, and monthly progress report, among many others.

**How** - This Dashboard was created by Power BI after data-cleansing step in Power Query. 

## Input
[Link Dataraw](https://github.com/muwnawn/home/blob/master/assets/Portfolio_Sales%20and%20Finance%20Analysis/Sales%20and%20Finance%20Data%20Raw.xlsm)

## Output
[Link Dashborad](https://github.com/muwnawn/home/blob/master/assets/Portfolio_Sales%20and%20Finance%20Analysis/Sales%20Analysis%20Dashboard.pbix)

### 1. Overview - 
Main metrics: 
- Total Sales
- Sales Revenue = Sales - Discount
- Total Profit
- Profit margin (%) = Profit/Sales
- Sales by Order Month (Time Series Analysis)
- Customer Growth Rate by Month (Time Series Analysis)
- Sales by Product Category
- Sales by Region

### 2. Products Report - which products are selling the best & which items are returned
Main metrics: 
- Total Orders
- Total Quantity
- Returned Orders
- Top 5 Products by Sales
- Bottom 5 Products by Sales
- Listing of most Returned Products

### 3. Customer Report - 
Main metric: 
- Total Customers
- Customer Growth Rate = Number of new customers/ Number of customers
- Customer Churn Rate = Number of lost customers/ Number of customers 
- Number of Customer by Ship Mode
- Number of Customer by Segment
- Retention Customer Rate by Last Twelve Months (Cohort Analysis)

### 4. Region/Sales Person Report - which region are selling the best - which product, when, where (city)
Main metrics: 
- Top 5 Cities by Sales
- Bottom 5 Cities by Sales
- Sales by Region
<!-- - Region/Sales Representatives Performance (Cohort Analysis) -->

## Preview
<img src="{{ site.url }}{{ site.baseurl }}/assets/Portfolio_Sales and Finance Analysis/SAD_Overview.png" alt="SAD_Overview Preview">
<img src="{{ site.url }}{{ site.baseurl }}/assets/Portfolio_Sales and Finance Analysis/SAD_Product.png" alt="SAD_Product Preview">
<img src="{{ site.url }}{{ site.baseurl }}/assets/Portfolio_Sales and Finance Analysis/SAD_Customer.png" alt="SAD_Customer Preview">
<img src="{{ site.url }}{{ site.baseurl }}/assets/Portfolio_Sales and Finance Analysis/SAD_Region.png" alt="SAD_Region Preview">
