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
We can see that among the free English apps, more than a half (58.14%) are games. Entertainment apps are close to 8%, followed by photo and video apps, which are close to 5%. Below 0.2% of the apps are designed for navigation, medical or catalog.

The general impression is that App Store (at least the part containing free English apps) is dominated by apps that are designed for fun (games, entertainment, photo and video, social networking, sports, music, etc.), while apps with practical purposes (education, shopping, utilities, productivity, lifestyle, etc.) are more rare. However, the fact that fun apps are the most numerous doesn't also imply that they also have the greatest number of users — the demand might not be the same as the offer.

<img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/top3_common_apple.png">
<img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/bottom3_common_apple.png">

### On Google Play
While the App Store is dominated by apps designed for fun, while Google Play shows a more balanced landscape of both practical and for-fun apps. On Google Play, there are not that many apps designed for fun, and it seems that a good number of apps are designed for practical purposes (family, tools, business, lifestyle, productivity, etc.). However, if we investigate this further, we can see that the family category (which accounts for almost 19% of the apps) means mostly games for kids.

<img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/top3_common_google.png">
<img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/bottom3_common_google.png">

## Most popular genre
### On App Store
Now we'd like to get an idea about the kind of apps that have most users. 

On average, navigation apps have the highest number of user reviews, but this figure is heavily influenced by Waze and Google Maps, which have close to half a million user reviews together. The same pattern applies to social networking apps, where the average number is heavily influenced by a few giants like Facebook, Pinterest, Skype, etc. Same applies to music apps, where a few big players like Pandora, Spotify, and Shazam heavily influence the average number.

Our aim is to find popular genres, but navigation, social networking or music apps might seem more popular than they really are. The average number of ratings seem to be skewed by very few apps which have hundreds of thousands of user ratings, while the other apps may struggle to get past the 10,000 threshold. We could get a better picture by removing these extremely popular apps for each genre and then rework the averages, but we'll leave this level of detail for later.

Other genres that seem popular include weather, book, food and drink, or finance. The book genre seem to overlap a bit with the app idea we described above, but the other genres don't seem too interesting to us:

- Weather apps — people generally don't spend too much time in-app, and the chances of making profit from in-app adds are low. Also, getting reliable live weather data may require us to connect our apps to non-free APIs.

- Food and drink — examples here include Starbucks, Dunkin' Donuts, McDonald's, etc. So making a popular food and drink app requires actual cooking and a delivery service, which is outside the scope of our company.

- Finance apps — these apps involve banking, paying bills, money transfer, etc. Building a finance app requires domain knowledge, and we don't want to hire a finance expert just to build an app.
<img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/popular_apple.png">

### On Google Play
On average, communication apps have the most installs: 38,456,119. This number is heavily skewed up by a few apps that have over one billion installs (WhatsApp, Facebook Messenger, Skype, Google Chrome, Gmail, and Hangouts), and a few others with over 100 and 500 million installs.

We see the same pattern for the video players category, which is the runner-up with 24,727,872 installs. The market is dominated by apps like Youtube, Google Play Movies & TV, or MX Player. The pattern is repeated for social apps (where we have giants like Facebook, Instagram, Google+, etc.), photography apps (Google Photos and other popular photo editors), or productivity apps (Microsoft Word, Dropbox, Google Calendar, Evernote, etc.).

Again, the main concern is that these app genres might seem more popular than they really are. Moreover, these niches seem to be dominated by a few giants who are hard to compete against.

The game genre seems pretty popular, but previously we found out this part of the market seems a bit saturated, so we'd like to come up with a different app recommendation if possible.

The books and reference genre looks fairly popular as well, with an average number of installs of 8,767,811. It's interesting to explore this in more depth, since we found this genre has some potential to work well on the App Store, and our aim is to recommend an app genre that shows potential for being profitable on both the App Store and Google Play.

<img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/popular_apple.png">

## Conclusions
In this project, we analyzed data about the App Store and Google Play mobile apps with the goal of recommending an app profile that can be profitable for both markets.

We concluded that taking a popular book (perhaps a more recent book) and turning it into an app could be profitable for both the Google Play and the App Store markets. The markets are already full of libraries, so we need to add some special features besides the raw version of the book. This might include daily quotes from the book, an audio version of the book, quizzes on the book, a forum where people can discuss the book, etc.

# Detail steps
## Step 1: Data Cleaning
### 1.1. Initial Data Checks
Let's start by opening the two data sets and then continue with exploring the data.

A function named **open_dataset()** that we can use repeatedly to open dataset.

```python
def open_dataset(file_path):
    opened_file = open(file_path)
    from csv import reader
    read_file = reader(opened_file)
    data = list(read_file)
    return data

apple = open_dataset('/content/AppleStore.csv')
google = open_dataset('/content/googleplaystore.csv')
```

A function named **explore_data()** that we can use repeatedly to explore rows in a more readable way. Other options for this function is **rows_and_columns** to show the number of rows and columns for any data set, **duplicate_records** to show number of distinct values that are recorded duplicately and **missing_value** to show the order of the row if there any missing value in that row.

```python
def explore_data(dataset, start=0, end=3, rows_and_columns=True, duplicate_records=True, missing_value=True):
    
    if start!=False and end!=False:
      dataset_slice = dataset[start:end]
      for row in dataset_slice:
          print(row)
          print('\n') # adds a new (empty) line after each row

    if rows_and_columns:
        print('Number of rows:', len(dataset),'\n')
        print('Number of columns:', len(dataset[0]),'\n')
    
    if duplicate_records:
      duplicate_record = []
      for row in dataset:
        if dataset.count(row) > 1:
          if row not in duplicate_record:
            duplicate_record.append(row)
      print('Number of duplicate values:', len(duplicate_record),'\n')

    if missing_value:
      for row in dataset:
        if len(row) != len(dataset[0]):
          missing_row = dataset.index(row)
          print('Missing Values at row:', missing_row)
```

#### 1.1.1. Explore data and Colunm, Row Count
- **Explore dataset Apple Store Apps**

```python
explore_data(apple)
```

['', 'id', 'track_name', 'size_bytes', 'currency', 'price', 'rating_count_tot', 'rating_count_ver', 'user_rating', 'user_rating_ver', 'ver', 'cont_rating', 'prime_genre', 'sup_devices.num', 'ipadSc_urls.num', 'lang.num', 'vpp_lic']


['1', '281656475', 'PAC-MAN Premium', '100788224', 'USD', '3.99', '21292', '26', '4', '4.5', '6.3.5', '4+', 'Games', '38', '5', '10', '1']


['2', '281796108', 'Evernote - stay organized', '158578688', 'USD', '0', '161065', '26', '4', '3.5', '8.2.2', '4+', 'Productivity', '37', '5', '23', '1']


Number of rows: 7198 

Number of columns: 17 

Number of duplicate values: 0

The Apple Store data set has 7197 apps and 17 columns, the columns that seem interesting are: 'track_name', 'currency', 'price', 'rating_count_tot', 'rating_count_ver', and 'prime_genre'. {: .notice--info}

- **Explore dataset Google PLay Store Apps**

```python
explore_data(google)
```

['App', 'Category', 'Rating', 'Reviews', 'Size', 'Installs', 'Type', 'Price', 'Content Rating', 'Genres', 'Last Updated', 'Current Ver', 'Android Ver']


['Photo Editor & Candy Camera & Grid & ScrapBook', 'ART_AND_DESIGN', '4.1', '159', '19M', '10,000+', 'Free', '0', 'Everyone', 'Art & Design', 'January 7, 2018', '1.0.0', '4.0.3 and up']


['Coloring book moana', 'ART_AND_DESIGN', '3.9', '967', '14M', '500,000+', 'Free', '0', 'Everyone', 'Art & Design;Pretend Play', 'January 15, 2018', '2.0.0', '4.0.3 and up']


Number of rows: 10842 

Number of columns: 13 

Number of duplicate values: 410

Missing Values at row: 10473

The Google Play data set has 10841 apps and 13 columns. At a quick glance, the columns that might be useful for the purpose of our analysis are 'App', 'Category', 'Reviews', 'Installs', 'Type', 'Price', and 'Genres'. Besides, this dataset has duplicate and missing values which would need to be handle later. {: .notice--info}

#### 1.1.2. Remove Duplicate Records
As been explored, the Google PLay Store Apps dataset has 410 duplicate values. 

```python
def remove_dup(dataset):
  remove_dup = []
  for i in dataset:
      if i not in remove_dup:
          remove_dup.append(i)
  return remove_dup
```
```python
google_remove_dup = remove_dup(google)
explore_data(google_remove_dup,False,False)
```
Number of rows: 10359 

Number of columns: 13 

Number of duplicate values: 0

Missing Values at row: 9991

483 duplicate rows of 410 duplicate values has been removed. {: .notice--info}

#### 1.1.3. Remove Inappropriate Records
- **Removing Non-English Apps**: The company develops English apps therefore only the apps that are designed for an English-speaking audience are analyzed.
The names of the apps suggest they are not directed toward an English-speaking audience. Below, there are a couple of examples from both data sets:

```python
print(apple[71][2])
print(apple[211][2])

print(google[2539][0])
print(google[9118][0])
```

新浪新闻-阅读最新时事热门头条资讯视频

央视影音-海量央视内容高清直播

tökr

لعبة تقدر تربح DZ

These apps have name that contains a symbol that is not commonly used in English text — English text usually includes letters from the English alphabet, numbers composed of digits from 0 to 9, punctuation marks (., !, ?, ;, etc.), and other symbols (+, *, /, etc.).

All these characters that are specific to English texts are encoded using the ASCII standard. Each ASCII character has a corresponding number between 0 and 127 associated with it, and we can take advantage of that to build a function that checks an app name and tells us whether it contains non-ASCII characters.

To minimize the impact of data loss, we'll only remove an app if its name has more than three non-ASCII characters:

```python
def remove_noneng(dataset):
  try:
    index_row = dataset[0].index('track_name')
  except:
    index_row = dataset[0].index('App')
  eng_app = []
  eng_app.append(dataset[0])
  
  for row in dataset[1:]:
    name = row[index_row]

    count_char = 0
    for char in name:
      if ord(char) > 127:
        count_char += 1

    if count_char <= 3:
      eng_app.append(row)
  return eng_app
```

```python
apple_engapp = remove_noneng(apple)
explore_data(apple_engapp,False,False)
```

Number of rows: 6184 

Number of columns: 17 

Number of duplicate rows: 0


```python
google_engapp = remove_noneng(google_remove_dup)
explore_data(google_engapp,False,False)
```

Number of rows: 10314 

Number of columns: 13 

Number of duplicate rows: 0

Missing Values at row: 9947

- **Removing Paid Apps**: The company only build apps that are free to download and install, and main source of revenue consists of in-app ads.

```python
def remone_paid(dataset):
  try:
    index_row = dataset[0].index('price')
  except:  
    index_row = dataset[0].index('Price')
  free = []
  free.append(dataset[0])
  for row in dataset[1:]:
    if row[index_row] == '0':
      free.append(row)
  return free
```

```python
apple_free = remone_paid(apple_engapp)
explore_data(apple_free,False,False)
```

Number of rows: 3223 

Number of columns: 17 

Number of duplicate rows: 0


```python
google_free = remone_paid(google_engapp)
explore_data(google_free,False,False)
```

Number of rows: 9552 

Number of columns: 13 

Number of duplicate rows: 0

<!-- ### 1.2. Inspect Variable Types
- **Undesirable Column Types**
 -->
 
### 1.2. Specify Missing Values
As explored, the Google Play Store Apps dataset used to have missing values at row 9947. However, after removing Paid Apps, the missing value row has also been removed. Therefore, the dataset no longer have missing values and we have final dataset after cleaning steps.

```python
apple_final = apple_free
google_final = google_free
```

## Step 2: Data Analysis
This project's aim is to determine the kinds of apps that are likely to attract more users because the revenue is highly influenced by the number of users. Therefore, the analysis would find out the most common and the most popular genres for both the App Store and Google Play market.

To get a sense of the most common genres for each market, we'll build a frequency table for the "prime_genre" column of the App Store data set, and the Genres and "Category" columns of the Google Play data set. 

One way to find out what genres are the most popular is to calculate the average number of installs for each app genre. For the Google Play data set, we can find this information in the "Installs" column, but for the App Store data set this information is missing. As a workaround, we'll take the total number of user ratings as a proxy or "rating_count_tot app".

### 2.1. Most Common Apps by Genre (have the most apps) 
The **popular_table** function return a tuple with 2 part, the first is a dictionary of average number of users per app and the second is number of apps both by genre.

```python
def popular_table(dataset):
  try:
    index_genre = dataset[0].index('prime_genre')
  except:
    index_genre = dataset[0].index('Category')

  try:
    index_user = dataset[0].index('rating_count_tot')
  except:
    index_user = dataset[0].index('Installs')

  popular_table = {}
  freq_table = {}

  for row in dataset[1:]:
    genre = row[index_genre]
    
    if genre in popular_table:
        popular_table[genre] += int(row[index_user].replace('+','').replace(',',''))
    else:
        popular_table[genre] = int(row[index_user].replace('+','').replace(',',''))

  for row in dataset[1:]:
    genre = row[index_genre]
    
    if genre in freq_table:
        freq_table[genre] +=1
    else:
        freq_table[genre] = 1

  for genre in popular_table:
    popular_table[genre] = round(popular_table[genre]/freq_table[genre],2)
  
  return popular_table, freq_table
```

Then I'll create frequency table using pandas library 
```python
freq_google = list(popular_table(google_final))[1]
freq_apple = list(popular_table(apple_final))[2]
```

```python
import pandas as pd
freq_dict = {'Genre':"","Percentage (%)":""}
freq_genre = list(freq_apple)
freq_value = list(freq_apple.values())
freq_dict['Genre'] = freq_genre
freq_dict['Percentage (%)'] = freq_value
  
df = pd.DataFrame.from_dict(freq_dict)
df.style #.background_gradient()
df.sort_values(by=['Percentage (%)'],ascending=False)
```
<img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/common_apple.png">

```python
import pandas as pd
freq_dict = {'Genre':"","Percentage (%)":""}
freq_genre = list(freq_google)
freq_value = list(freq_google.values())
freq_dict['Genre'] = freq_genre
freq_dict['Percentage (%)'] = freq_value
  
df = pd.DataFrame.from_dict(freq_dict)
df.style #.background_gradient()
df.sort_values(by=['Percentage (%)'],ascending=False)
```
<img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/common_google.png">

### 2.2. Most Popular Apps by Genre (have the most users) 
Similarly, I create popular table using pandas library.
```python
popular_google = list(popular_table(google_final))[0]
popular_apple = list(popular_table(apple_final))[0]
```
```python
popular_dict = {'Genre':"","Average Users":""}
popular_genre = list(popular_apple)
popular_value = list(popular_apple.values())
popular_dict['Genre'] = popular_genre
popular_dict['Average Users'] = popular_value
  
df = pd.DataFrame.from_dict(popular_dict)
df.style #.background_gradient()
df.sort_values(by=['Average Users'],ascending=False)
```
<img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/popular_apple.png">

```python
popular_dict = {'Genre':"","Average Users":""}
popular_genre = list(popular_google)
popular_value = list(popular_google.values())
popular_dict['Genre'] = popular_genre
popular_dict['Average Users'] = popular_value
  
df = pd.DataFrame.from_dict(popular_dict)
df.style #.background_gradient()
df.sort_values(by=['Average Users'],ascending=False)
```
<img src="{{ site.url }}{{ site.baseurl }}/assets/appdata/popular_apple.png">
