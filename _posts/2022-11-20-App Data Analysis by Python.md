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

**How** - There are 2 main steps which are describe more detail in "Detail steps" part below
- Step 1: Data Cleaning (Deleting Wrong Data, Removing Duplicate Entries, Removing Inappropriate Records)
- Step 2: Data Analysis (Most Common Apps by Genre, Most Popular Apps by Genre)

# Input
A data set containing data about approximately ten thousand Android apps from Google Play. You can find more details and download the data set from this [kaggle link](https://www.kaggle.com/datasets/lava18/google-play-store-apps).

A data set containing data about approximately seven thousand iOS apps from the App Store. You can find more details and download the data set from this [kaggle link](https://www.kaggle.com/datasets/ramamet4/app-store-apple-data-set-10k-apps).

# Output

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
### 2.1. Most Common Apps by Genre (have the most apps) 
To get a sense of the most common genres for each market, we'll build a frequency table for the prime_genre column of the App Store data set, and the Genres and Category columns of the Google Play data set.

### 2.2. Most Popular Apps by Genre (have the most users) 
One way to find out what genres are the most popular is to calculate the average number of installs for each app genre. For the Google Play data set, we can find this information in the Installs column, but for the App Store data set this information is missing. As a workaround, we'll take the total number of user ratings as a proxy, which we can find in the rating_count_tot app.
