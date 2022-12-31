---
title: "App Data Analysis by Python"
date: 2022-11-20
last_modified_at: 2022-11-20T11:59:26-04:00
tags: 
  - data_analysis
  - data_visualisation
  - python
header:
  image: "/images/Python Programming for Beginners.jpg"
  teaser: "/images/Python Programming for Beginners.jpg"
excerpt: "Data Analysis, Data Visualisation, Python"
classes: wide
mathjax: "true"
---
## DESCRIPTION
This project's aim is to find mobile app profiles that are profitable for the App Store and Google Play markets. 

This report helps developers understand what kinds of apps are likely to attract more users and make data-driven decisions to the kind of apps they would build. Note: only free English apps are analysed.

**How** - There are 3 main steps which are described in "Detail steps" part below

## INPUT
A data set containing data about approximately ten thousand Android apps from Google Play. You can find more details and download the data set from this [kaggle link](https://www.kaggle.com/datasets/lava18/google-play-store-apps).

A data set containing data about approximately seven thousand iOS apps from the App Store. You can find more details and download the data set from this [kaggle link](https://www.kaggle.com/datasets/ramamet4/app-store-apple-data-set-10k-apps).

## DETAIL STEPS
I represent in 2 ways: the first one working with python dataframe and libraries, the second one using python lists and built-in functions.**
Below are some main step without code, please click the [Google Colab link](https://colab.research.google.com/drive/1D5Cs3UDQY50va7-FgEzkN8pYuaPtCkO4?usp=sharing) to see full code and how it works. 
- Step 0: Understanding the data (Open file, Initial Data Checks by finding colunm, row count, duplicate records and missing values)
- Step 1: Data Cleaning (Delete Wrong Data, Removing Duplicate and Inappropriate Records)
- Step 2: Data Analysis (Find Most Common Apps by Genre, Most Popular Apps by Genre)
- Step 3: Data Visualization

## OUTPUT
### Most common genre
#### On App Store
The general impression is that **App Store is dominated by apps that are designed for fun** (mostly games - 58.14%, entertainment - 8%, photo and video - 5%, etc.), while apps with practical purposes (education	- 3.6%, others < 3% each) are more rare. 

<p align="center">
    <img src="https://drive.google.com/uc?export=view&id=156VtRfpw913jcXhmNRrc00OK6gfBHwMu">
    <br>
    <em>Top 5 and bottom 5 most common genres on Apple Store.</em>
</p>

#### On Google Play
While the App Store is dominated by apps designed for fun, **Google Play shows a more balanced landscape of both practical and for-fun apps**. On Google Play, it seems that a good number of apps are designed for practical purposes (family, tools, business, productivity, etc.).

<p align="center">
    <img src="https://drive.google.com/uc?export=view&id=1-3PgrEbdGN3hQk49YVMRFDUBfLtgjA6W">
    <br>
    <em>Top 5 and bottom 5 most common genres on Google Play Store.</em>
</p>

However, if we investigate this further, we can see that mostly apps in the family category (which accounts for almost 18% of the apps) are made with entertainment  purpose.

<p align="center">
    <img src="https://drive.google.com/uc?export=view&id=1HyS0GysD54p6OUAEzYcJJ9qs9Z0OvIBl">
    <br>
    <em>Most common categories of "Family" genre on Google Play Store.</em>
</p>

### Most popular genre
So, we found that most common apps in both store are for entertainment. Now we'd like to get an idea about the kind of apps that have most users. 

#### On App Store

<p align="center">
    <img src="https://drive.google.com/uc?export=view&id=1-23rgpJK2dnVFBDxk4uliOq0wKXpRqFr">
    <br>
    <em>Top 10 most popular genres on Apple Store.</em>
</p>

Most of the popular genres might seem more popular than they really are and be dominant by a few giants.
- On average, navigation apps have the highest number of user reviews (more than 86090 user reviews), but this figure is heavily influenced by Waze (account for 67% total reviews) and Google Maps (30%), which have close to half a million user reviews together. 
- The same pattern applies to 
  - Reference apps, where have the Bible (account for 73% total reviews) and Dictionary.com which skew up the average rating.
  - Social networking apps, where the average number is heavily influenced by a few giants like Facebook (39%), Pinterest (14%), Skype, etc. 
  - Music apps, where a few big players like Pandora (30%), Spotify (23%), and Shazam heavily influence the average number. 
  - Book apps, where also have big players like Kindle (45%), Audible (19%). 
  - Food and drink — examples here include Starbucks (35%), Domino's Pizza(30%), etc.
  - Travel - Google Earth	(40%), Yelp (20%),...
  - Photo & video apps - have Instagram (47%) which actually social networking apps. 
 
Other genres that seem popular include weather or finance:
- Weather apps — people generally don't spend too much time in-app, and the chances of making profit from in-app adds are low. Also, getting reliable live weather data may require us to connect our apps to non-free APIs.
- Finance apps — these apps involve banking, paying bills, money transfer, etc.

The average number of ratings seem to be skewed by very few apps which have hundreds of thousands of user ratings, while the other apps may struggle to get past the 10,000 threshold. 

<p align="center">
    <img src="https://drive.google.com/uc?export=view&id=1---pHKPyejHKcfWrp2DNMiVCWDo5G8Mb">
    <br>
    <em>Distribution of app users on Apple Store.</em>
</p>

After removing apps that have more than 10,000 reviews, we can see some new genres like Business, Shopping, Health & fitness and Productivity. Beside Shopping and Productivity, other genres share the same dominant pattern as describe above.

<p align="center">
    <img src="https://drive.google.com/uc?export=view&id=1-0qRkalA0QtwqT2bMJZK0fxVeOQizHvB">
    <br>
    <em>Top 10 most popular genres on Apple Store (below 10 thousands reviews).</em>
</p>

**To temperarily conclude, protential genre on Apple Store are Finance, Shopping and Productivity apps.**

#### On Google Play
On Google Play Store, communication, social and video players has most installs but again, the main concern is that these app genres might seem more popular than they really are. Moreover, these niches seem to be dominated by a few giants who are hard to compete against.
- On average, communication apps have the most installs: 71,452,385. This number is heavily skewed up by a few apps that have over one billion installs (WhatsApp, Facebook Messenger, Skype, Google Chrome, Gmail, and Hangouts), and a few others with over 100 and 500 million installs.
- We see the same pattern for the social category, which is the runner-up with 45,176,396 installs. The market is dominated by apps like Facebook, Instagram, Google+, etc.. 
- The pattern is repeated for video players apps (where we have giants like Youtube, Google Play Movies & TV, or MX Player), photography apps (Google Photos and other popular photo editors), or productivity apps (Microsoft Word, Dropbox, Google Calendar, Evernote, etc.).

<p align="center">
    <img src="https://drive.google.com/uc?export=view&id=1-2jaIzPC5Y4eRJ5x13hFUmyTBI8_tyaW">
    <br>
    <em>Top 10 most popular genres on Google Play Store.</em>
</p>

The average number of ratings seem to be skewed by very few apps which have milions of user installs, while the other apps may struggle to get past the 10,000,000 threshold. 

<p align="center">
    <img src="https://drive.google.com/uc?export=view&id=1-72rXpjraD1Hz3aZ6GJ1z2O0roAonrKW">
    <br>
    <em>Distribution of app users on Google Play Store.</em>
</p>

After removing apps that have more than 10,000,000 installs, most popular genres on Google Play Store are Entertainment, Education and Games.
- The game or entertainment genre seems pretty popular, but previously we found out this part of the market seems a bit saturated (most common genre), so we'd like to come up with a different app recommendation if possible.

<p align="center">
    <img src="https://drive.google.com/uc?export=view&id=1-FXc77A3wBIA9mmKoJyg7laB8qEUw1_t">
    <br>
    <em>Top 10 most popular genres on Google Play Store (below 10 milions installs).</em>
</p>

### Conclusions
In this project, we analyzed data about the App Store and Google Play mobile apps with the goal of recommending an app profile that can be profitable for both markets.

We concluded that taking a popular book (perhaps a more recent book) and turning it into an app could be profitable for both the Google Play and the App Store markets. The markets are already full of libraries, so we need to add some special features besides the raw version of the book. This might include daily quotes from the book, an audio version of the book, quizzes on the book, a forum where people can discuss the book, etc.

