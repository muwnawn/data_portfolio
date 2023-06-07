---
title: "Flights Analysis by Python"
date: 2023-06-06
last_modified_at: 2023-06-06T11:59:26-04:00
tags: 
  - data_analysis
  - data_visualization
  - python
header:
  image: "https://e3.365dm.com/22/09/768x432/skynews-flights-half-term_5912915.jpg?20220928020714"
  teaser: "https://e3.365dm.com/22/09/768x432/skynews-flights-half-term_5912915.jpg?20220928020714"
excerpt: "Data Analysis, Data Visualization, Python"
classes: wide
mathjax: "true"
---
## DESCRIPTION
This flight data project analysis delay flights and investigate its reasons. The dataset containes flights in the United States with the reasons for delays, in 2006.

## DATASET
### Source
This project is a part of Udacity's Data Analyst Nanodegree and all the datasets are provided by Udacity.

The dataset name is "Airline On-Time Performance Data". This dataset reports flights in the United States, including carriers, arrival and departure delays, and reasons for delays, from 1987 to 2008. The dataset description [here](https://www.transtats.bts.gov/DatabaseInfo.asp?QO_VQ=EFD&Yv0x=D). Download dataset [here](https://community.amstat.org/jointscsg-section/dataexpo/dataexpo2009).

### Overview
The dataset has 7,141,922 flight details with 29 features in year of 2006.
The variables in the dataset contains information about flights' origin, departure, date and time, duration, cancellation status, delay (and cause of delay), etc.
Also, a flight is considered delayed when its arrival delay is longer than 15 minutes.

## KEY FINDINGS
### Percentage of delayed flights: 
- 58% of the total of flights was delayed.
- Flights delayed both on departure and arrival had highest figure, accounted for 37%. 
- Arrival Delay and Departure Delay flights contributed 12% and 9% respectively.

### Delay time distribution: 
- Around 40% of flights were delayed less than 10 minutues. 
- Nearly 90% of flights were delayed less than 60 minutues (an hours). 
- About 95% of flights were delayed less than 110 minutues (nearly 2 hours). 
- Almost all flights were delayed less than 210 minutues (3 and a half hours).

### Worst time to book flights
- Flights tended to be delayed in the middle and end of the year, especially peak in July and December with 45% of total flights be delayed and more than 30 minutues delay. 
- In the middle of the week, there were more flights had been delayed with Thursday and Friday.

### Worst airline to book flights
- The Atlantic Southeast Airlines has the longest average delay time, which was 16,4 minutes. Mesa and ATA Airlines placed second and third with 14 and 12 minutes respecively. 
- The Southwest Airlines has the highest number and percentage of delayed flights, which had nearly 518 thousands delayed flights and accounted for 47% total flights of this airlines. Though Atlantic Southeast Airlines had less flights than many other airlines, it delayed 46% (second-highest) of its flights.

### Worst place to book flights
- Original place to take off: Chicago and Alanta has the highest number and percentage of delayed flights, which had more than 200 thousands delayed flights and accounted for 48 and 50% total flights took off respectively. Though Las Vegas had less delayed flights than many other airlines, it delayed 49% (second-highest) of its flights. 
- Destination place to land off: Chicago, Alanta and Dallas-Fort Worth also top 3 highest number of delayed flights.

### Main reason for delay flights
- Both Arrival and Departure delay also have ~0.5 correlation with Carrier and Late Aircraft delay meaning that in case of Carrier and Late Aircraft delay, the flight has higher chance of departing/arriving late.
- Late Aircraft were main reasons of delayed flights, followed by NAS and Carrier.

## MATERIALS
- [Exploration file]("assets/UdacityxFPT_NguyenMinhAnh_Project5/Flight_Part_I_exploration.html")
- [Presentation file (slide desk)]("assets/UdacityxFPT_NguyenMinhAnh_Project5/Flight_Part_II_slide_deck.slides.html")
