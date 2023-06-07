---
title: "A/B Test Results Statistics Analysis by Python"
date: 2023-04-20
last_modified_at: 2023-04-20T11:59:26-04:00
tags: 
  - data_analysis
  - python
header:
  image: "https://www.travelpayouts.com/blog/wp-content/uploads/2018/11/ab-testing.jpg"
  teaser: "https://www.travelpayouts.com/blog/wp-content/uploads/2018/11/ab-testing.jpg"
excerpt: "Data Analysis, Statistics, Python"
classes: wide
mathjax: "true"
---
## DESCRIPTION
This project analyse the results of an A/B test run by an e-commerce website. The company has developed a new web page in order to try and increase the number of users who "convert," meaning the number of users who decide to pay for the company's product. The project's goal is to help the company understand if they should implement this new page, keep the old page, or perhaps run the experiment longer to make their decision.

### Dataset
This project is a part of Udacity's Data Analyst Nanodegree and all the datasets are provided by Udacity.
[Supporting Materials](https://video.udacity-data.com/topher/2017/December/5a32c9a0_analyzeabtestresults-2/analyzeabtestresults-2.zip).

### Summary
This notebook is organized into the following sections:
#### Introduction
- The company arrange their website users into 2 groups using new page and old page.
- The control group users are served with old_page; and treatment group users are matched with the new_page.
#### Part I: Probability
- The dataset contains 290.584 unique users, seperated pretty fairly into 2 groups.
- Conversion rate regardless of the page they receive is 11.96%. Conversion rate of treatment and control group is 11.88% and 12.04%, respectively.
- Conversion rate of control group higher than Conversion rate of treatment group by 0.16%, which can indicate quickly that old page is better than new page.
#### Part II: A/B Test
If the company want to assume that the old page is better, hypothesis test need to be performed with:
- Null hypotheses (H0): pold >= pnew
- Alternative hypotheses (H1): pold < pnew
with pold and pnew, which are the "converted" probability (or rate) for the old and new pages respectively.
By comparing p-value to type I error threshold (α = 0.05), decision about which hypothesis is true or there is a difference between the new and old pages or not can be made. The p-value = 0.09 > 0.05 (type I error rate), the null hypothesis is failed to reject.

#### Part III: Regression approach
Since each row in the dataset is either a conversion or no conversion, logistic regression is used to predict the probability of the occurrence of a binary event based on one or more predictor variables.
The p-value of ab_page is 0.1897 > 0.05 differing from p-value found in Part II (0.09) due to the type of test (part III is a two-sided and Part II is a one-sided)
However, this p-value is still larger then Type I error rate (0.19 > 0.05) which means the null hypothesis is also failed to reject.

**The company should keep the old page.**

## MATERIALS
[The folder]("assets/UdacityxFPT_NguyenMinhAnh_Project3") contains dataset, ipynb file and html file explain all the steps and findings in the summary part above.
