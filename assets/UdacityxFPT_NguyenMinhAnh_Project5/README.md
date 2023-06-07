# Flight Exploration
## by Minh Anh Nguyen


## Dataset

> The dataset name is "Airline On-Time Performance Data". This dataset reports flights in the United States, including carriers, arrival and departure delays, and reasons for delays, from 1987 to 2008. The dataset description [here](https://www.transtats.bts.gov/DatabaseInfo.asp?QO_VQ=EFD&Yv0x=D). Download dataset [here](https://community.amstat.org/jointscsg-section/dataexpo/dataexpo2009).

> This project uses dataset in 1-year period of 2006.


## Summary of Findings

> 58% of the total of flights was delayed. Flights delayed both on departure and arrival had highest figure, accounted for 37%. Meanwhile, Arrival Delay and Departure Delay flights contributed 12% and 9% respectively.

> These values of Departure and Arrival delay time were similar. Max values of 2 figures was 1.752 minutes and 1.779 minutes respectively, both around 29 hours. 50th percentile of these features had the same value of 15, which means 50% of flights were delayed below 15 minutes. 

> Distribution of Departure Delay: 41% of flights were delayed less than 10 minutues. 86% of flights were delayed less than 60 minutues (an hours). 95% of flights were delayed less than 110 minutues (nearly 2 hours). 99% of flights were delayed less than 210 minutues (3 and a half hours).

> Distribution of Arrival Delay: 40% of flights were delayed less than 10 minutues. 86% of flights were delayed less than 60 minutues (an hours). 95% of flights were delayed less than 110 minutues (nearly 2 hours). 99% of flights were delayed less than 210 minutues (3 and a half hours).

> There is a positive correlation between arrival and departure delays in which both variables move in the same direction. This means when one departure delays increases as arrival delays also increases and vice versor.

> Flights tended to be delayed in the middle and end of the year, especially peak in July and December with 45% of total flights be delayed. However, June had max delay time of 33 minutues, followed by December with 32 minutes. There were not so much differences between days of weeks. However, in the middle of the week, there were more flights had been delayed with Thursday and Friday accounted for 42% and 45% of total flights respectively. These 2 days of week also had highest delay time which was 33 minutes.

> The Atlantic Southeast Airlines has the longest average delay time, which was 16,4 minutes. Mesa and ATA Airlines placed second and third with 14 and 12 minutes respecively. Delay time of other airlines belowed 11 minutes. Especially, Aloha and Hawaiian Airline seemed like not be delayed, even took off early than scheduale. 

> The Southwest Airlines has the highest number and percentage of delayed flights, which had nearly 518 thousands delayed flights and accounted for 47% total flights of this airlines. Though Atlantic Southeast Airlines had less flights than many other airlines, it delayed 46% (second-highest) of its flights.

> Chicago and Alanta has the highest number and percentage of delayed flights, which had more than 200 thousands delayed flights and accounted for 48 and 50% total flights took off respectively. Though Las Vegas had less delayed flights than many other airlines, it delayed 49% (second-highest) of its flights. Chicago, Alanta and Dallas-Fort Worth also top 3 highest number of delayed flights. This can be investigate further to find reason of delay.

> Both Arrival and Departure delay also have ~0.5 correlation with Carrier and Late Aircraft delay meaning that in case of Carrier and Late Aircraft delay, the flight has higher chance of departing/arriving late. There is negative correlation among Carrier, NAS, Security and Late Aircraft delay.

> Late Aircraft were main reasons of delayed flights, followed by NAS and Carrier. The NAS is the most common delay cause for most of the airlines and Security the least common. For some airlines such as AQ, HA, OO and YV, Carrier causes the most delay.

## Key Insights for Presentation

> Presentation of the delayed flights analysis. 

> Percentage of delayed flights: 58% of the total of flights was delayed

> Delay time distribution: Around 40% of flights were delayed less than 10 minutues. Nearly 90% of flights were delayed less than 60 minutues (an hours). Almost all flights were delayed less than 210 minutues (3 and a half hours).

> Worst time to book flights: in the middle and end of the year, especially in July and December with 45% of total flights be delayed and more than 30 minutues delay. In the middle of the week, there were more flights had been delayed with Thursday and Friday.

> Worst airline to book flights: The Atlantic Southeast Airlines has the longest average delay time, which was 16,4 minutes. The Southwest Airlines has the highest number and percentage of delayed flights, which had nearly 518 thousands delayed flights and accounted for 47% total flights of this airlines. Though Atlantic Southeast Airlines had less flights than many other airlines, it delayed 46% (second-highest) of its flights.

> Worst place to book flights: 
> - Worst place to take off: Chicago and Alanta has the highest number and percentage of delayed flights, which had more than 200 thousands delayed flights and accounted for 48 and 50% total flights took off respectively. Though Las Vegas had less delayed flights than many other airlines, it delayed 49% (second-highest) of its flights.
> - Worst place to land off: Chicago, Alanta and Dallas-Fort Worth also top 3 highest number of delayed flights.

> Main reason for delay flights: Late Aircraft were main reasons of delayed flights, followed by NAS and Carrier.