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
# Description
**What** - Profitable App Profiles for the App Store and Google Play Markets. This project's aim is to find mobile app profiles that are profitable for the App Store and Google Play markets. 

**Who** - Team of developers use this report to understand what kinds of apps are likely to attract more users and make data-driven decisions with respect to the kind of apps they build.

**How** - There are 2 main steps which are describe more detail in "Detail steps" part below
- Step 1: Data Cleaning (Deleting Wrong Data, Removing Duplicate Entries, Removing Inappropriate Records)
- Step 2: Data Analysis (Most Common Apps by Genre, Most Popular Apps by Genre)

# Input
A data set containing data about approximately ten thousand Android apps from Google Play. You can find more details and download the data set from this [kaggle link](https://www.kaggle.com/datasets/lava18/google-play-store-apps).

A data set containing data about approximately seven thousand iOS apps from the App Store. You can find more details and download the data set from this [kaggle link](https://www.kaggle.com/datasets/ramamet4/app-store-apple-data-set-10k-apps).

# Output
## Most common genre
### On App Store
We can see that among the free English apps, more than a half (58.14%) are games. Entertainment apps are close to 8%, followed by photo and video apps, which are close to 5%. Only 3.66% of the apps are designed for education, followed by social networking apps which amount for 3.29% of the apps in our data set. 

The general impression is that App Store (at least the part containing free English apps) is dominated by apps that are designed for fun (games, entertainment, photo and video, social networking, sports, music, etc.), while apps with practical purposes (education, shopping, utilities, productivity, lifestyle, etc.) are more rare. 

<figure>
  <img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/top10_common_apple.png">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/bottom10_common_apple.png">
  <figcaption>Top 10 and bottom 10 most common genres on Apple Store.</figcaption>
</figure>


### On Google Play
While the App Store is dominated by apps designed for fun, while Google Play shows a more balanced landscape of both practical and for-fun apps. On Google Play, there are not that many apps designed for fun, and it seems that a good number of apps are designed for practical purposes (family, tools, business, lifestyle, productivity, etc.).

<figure>
  <img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/top10_common_google.png">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/bottom10_common_google.png">
  <figcaption>Top 10 and bottom 10  most common genres on Google Play Store.</figcaption>
</figure>

However, if we investigate this further, we can see that the family category (which accounts for almost 18% of the apps) means mostly games for kids.

<figure>
  <img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/top10_common_google_family.png">
  <figcaption>Top 10 most common categories of "Family" genre on Google Play Store.</figcaption>
</figure>

## Most popular genre
### On App Store
Now we'd like to get an idea about the kind of apps that have most users. 

On average, navigation apps have the highest number of user reviews, but this figure is heavily influenced by Waze and Google Maps, which have close to half a million user reviews together. The same pattern applies to social networking apps, where the average number is heavily influenced by a few giants like Facebook, Pinterest, Skype, etc. Same applies to music apps, where a few big players like Pandora, Spotify, and Shazam heavily influence the average number.

Our aim is to find popular genres, but navigation, social networking or music apps might seem more popular than they really are. The average number of ratings seem to be skewed by very few apps which have hundreds of thousands of user ratings, while the other apps may struggle to get past the 10,000 threshold. We could get a better picture by removing these extremely popular apps for each genre and then rework the averages, but we'll leave this level of detail for later.

Other genres that seem popular include weather, book, food and drink, or finance. The book genre seem to overlap a bit with the app idea we described above, but the other genres don't seem too interesting to us:

- Weather apps — people generally don't spend too much time in-app, and the chances of making profit from in-app adds are low. Also, getting reliable live weather data may require us to connect our apps to non-free APIs.

- Food and drink — examples here include Starbucks, Dunkin' Donuts, McDonald's, etc. So making a popular food and drink app requires actual cooking and a delivery service, which is outside the scope of our company.

- Finance apps — these apps involve banking, paying bills, money transfer, etc. Building a finance app requires domain knowledge, and we don't want to hire a finance expert just to build an app.

<figure>
  <img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/top10_popular_apple.png">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/bottom10_popular_apple.png">
  <figcaption>Top 10 and bottom 10 most popular genres on Apple Store.</figcaption>
</figure>

### On Google Play
On average, communication apps have the most installs: 38,456,119. This number is heavily skewed up by a few apps that have over one billion installs (WhatsApp, Facebook Messenger, Skype, Google Chrome, Gmail, and Hangouts), and a few others with over 100 and 500 million installs.

We see the same pattern for the video players category, which is the runner-up with 24,727,872 installs. The market is dominated by apps like Youtube, Google Play Movies & TV, or MX Player. The pattern is repeated for social apps (where we have giants like Facebook, Instagram, Google+, etc.), photography apps (Google Photos and other popular photo editors), or productivity apps (Microsoft Word, Dropbox, Google Calendar, Evernote, etc.).

Again, the main concern is that these app genres might seem more popular than they really are. Moreover, these niches seem to be dominated by a few giants who are hard to compete against.

The game genre seems pretty popular, but previously we found out this part of the market seems a bit saturated, so we'd like to come up with a different app recommendation if possible.

The books and reference genre looks fairly popular as well, with an average number of installs of 8,767,811. It's interesting to explore this in more depth, since we found this genre has some potential to work well on the App Store, and our aim is to recommend an app genre that shows potential for being profitable on both the App Store and Google Play.

<figure>
  <img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/top10_popular_googple.png">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/bottom10_popular_google.png">
  <figcaption>Top 10 and bottom 10 most popular genres on Apple Store.</figcaption>
</figure>

## Conclusions
In this project, we analyzed data about the App Store and Google Play mobile apps with the goal of recommending an app profile that can be profitable for both markets.

We concluded that taking a popular book (perhaps a more recent book) and turning it into an app could be profitable for both the Google Play and the App Store markets. The markets are already full of libraries, so we need to add some special features besides the raw version of the book. This might include daily quotes from the book, an audio version of the book, quizzes on the book, a forum where people can discuss the book, etc.

# Detail steps
[Google Colab link](https://colab.research.google.com/drive/1D5Cs3UDQY50va7-FgEzkN8pYuaPtCkO4?usp=sharing)
