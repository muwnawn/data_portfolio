---
title: "A note about Statistics"
date: 2022-12-26
last_modified_at: 2022-12-26T11:59:26-04:00
author_profile: true
header:
  image: "/images/STATS.jpg"
  teaser: "/images/STATS.jpg"
excerpt: ""
classes: wide
toc: true
toc_icon: "heart"
published: false
---

## 1. FOUNDATION
### 1.1. Populations and Parameters
<img align = "right" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQJCMXUDZGeezz8p7LF9OO18EVC0P0_tsKP9w&usqp=CAU">

- Population is any large collection of objects or individuals.
- Parameters is any summary number, like an average or percentage, that describes the entire population.

### 1.2. Samples and Statistics
- Samples is a representative group drawn from the population.
- Statistics is any summary number, like an average or percentage, that describes the sample.

### 1.3. Statistics Techniques
- Descriptive statistics:	describe data in ways to capture the essence of the information in the data
- Inferential statistics:	draw conclusions from data about the population

### 1.4. Measures of Central Tendency
- Mean: the average of data - easily affected by extreme values (Outliers)
- Median: middle value of the ordered data
- Mode: the value that occurs most often - may be more than one mode

### 1.5. Measures of Position
- Percentile: If you have a 95th percentile score then you are at or above 95% of all test takers. 
- Quartiles

### 1.6. Measures of Variability
- Range
- Variance: measures how far each number in the set is from the mean (average)
- Standard Deviation: approximately the average distance the values of a data set are from the mean - the square root of the variance

## 2. DISTRIBUTIONS
<!-- PROBABILITY -->
### 2.1. Probability Distributions
- Mean: the average of data - easily affected by extreme values (Outliers)
- Median: middle value of the ordered data
- Mode: the value that occurs most often - may be more than one mode
<!-- - Z-score: distance from mean = (datapoint - mean)/SD
- Empirical rule -->

### 2.2. Sampling Distributions
- Sampling Distribution of the Sample Mean



- Sampling Distribution of the Sample Proportion

## 3. HYPOTHESIS TESTING FOR ONE SAMPLE
### 3.1. Some term
- Confidence Intervals:
<p align = 'center'>
  <img src = "https://conversionsciences.com/wp-content/uploads/2016/09/confidence-interval-example.webp">
<p/>
- Margin of Errors:
<p align = 'center'>
  <img src = "https://conversionsciences.com/wp-content/uploads/2016/09/confidence-interval-example.webp">
<p/>
- Regression toward the mean is “the phenomenon that if a variable is extreme on its first measurement, it will tend to be closer to the average on its second measurement.” This ensures that as we continue increasing the sample size and the length of observation, the mean of our observations will get closer and closer to the true mean of the population.
- Null Hypothesis (Ho): a baseline assumption that there is no relationship between two data sets. When a statistical hypothesis test is run, the results either disprove the null hypothesis or they fail to disprove the null hypothesis.
    - Example: When taking AB test, we automatically assume Variation B is NOT a meaningful improvement over Variation A. That is our null hypothesis. Either we disprove it by showing that Variation B’s conversion rate is a statistically significant improvement over Variation A, or we fail to disprove it.
- Statistical Significance: when the p-value < the significance level
    - p-value is the probability of obtaining at least as extreme results given that the null hypothesis is true.
    - significance level (alpha) is the probability of rejecting the null hypothesis given that it is true.
     
### 3.2. Steps
- Step 1. Set up the hypotheses and check conditions
    - Hypothesis Test for One-Sample Proportion
    - Hypothesis Testing for One-Sample Mean
- Step 2. Decide on the significance level, alpha
- Step 3. Calculate the test statistic
Hypothesis Test for One-Sample Proportion
Hypothesis Testing for One-Sample Mean
- Step 4. Calculate probability value (p-value)
    - Hypothesis Test for One-Sample Proportion
    - Hypothesis Testing for One-Sample Mean
Z-table for Proportion
T-table for Mean
- Step 5. Make a decision about the null hypothesis

## 3. SOURCES
1. [STAT 500: Applied Statistics](https://online.stat.psu.edu/stat500/)
2. [A/B Testing Statistics](https://conversionsciences.com/ab-testing-statistics/#:~:text=An%20AB%20test%20is%20an,statistically%20significant%20relationship%20or%20not)
