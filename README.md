# Ford GoBike Trip Data Exploration
## by Golden Chikaire Egbua


## Dataset

Ford GoBike is the Bay Area's bike share system, introduced in 2013 as a pilot program for the region, with 700 bikes and 70 stations across San Francisco and San Jose. Having the expectations that once expansion is complete, Ford GoBike will grow to 7,000 bikes across San Francisco, the East Bay and San Jose.

Ford GoBike, like other bike share systems, consists of a fleet of specially designed, sturdy and durable bikes that are locked into a network of docking stations throughout the city. The bikes can be unlocked from one station and returned to any other station in the system, making them ideal for one-way trips. People use bike share to commute to work or school, run errands, get to appointments or social engagements and more. It's a fun, convenient and affordable way to get around.

The bikes are available for use 24 hours/day, 7 days/week and riders have access to all bikes in the network when they become a member or purchase a pass.

The dataset originally had 183,412 entries and 16 columns that were mostly numeric variables. The following are the initial collumns:

* duration_sec
* start_time
* end_time
* start_station_id
* start_station_name
* start_station_latitude
* start_station_longitude
* end_station_id
* end_station_name
* end_station_latitude
* end_station_longitude
* bike_id
* user_type
* member_birth_year
* member_gender
* bike_share_for_all_trip

## Preliminary Wrangling
After some Visual and Programatic Assessments, the issues below were dicovered and cleaned using the define-code-test framework

### Issues

1. There are missing values in some of the columns ('start_station_id', 'start_station_name', 'end_station_id', 'end_station_name', 'member_birth_year' and 'member_gender').

2. Incorrect data formats(dtype):
    * The 'start_time' and 'end_time' columns should be in the datetime format instead of string format.
    * The 'start_station_id', 'bike_id', and the 'end_station_id' columns should be in object(string) format.
    * 'member_birth_year' column is in the float format instead of integer format.
    * 'bike_share_for_all_trip' column is in the string format instead of boolean format.

3. Create columns for the start day of the week and start hour.

4. Calculate the distance traveled using the latitude and longitude values in the dataset.

5. Calculate the speed of each trip using the distance traveled and the duration.

6. Calculate member_age from member_birth_year and create age groups.

> After the wrangling, the dataset now contained 18 columns and 174,952 entries of bicycle trips. I created six more columns and dropped four columns making the final dataset to have 18 columns as shown in the table below.

| SN | Column | Dtype |
| :- | :- | :- |
| 1 | duration_sec | int64 |
| 2 | start_time | datetime64[ns] |
| 3 | end_time | datetime64[ns] |
| 4 | start_station_id | object |
| 5 | start_station_name | object |
| 6 | end_station_id | object |
| 7 | end_station_name | object |
| 8 | bike_id | object |
| 9 | user_type | object |
| 10 | member_birth_year | int64 |
| 11 | member_gender | object |
| 12 | bike_share_for_all_trip | bool |
| 13 | start_day | object |
| 14 | start_hour | int64 |
| 15 | distance_km | float64 |
| 16 | speed | float64 |
| 17 | member_age | int64 |
| 18 | member_age_groups | int64 |


## Summary of Findings

>The main findings from the data exploration are:
> * The bikes are being used primarily by commuters to work or school.
> * Most riders use the bikes for short distance trips of distances less than 10[km].
> * most of the trips had their speed between 2[m/s] and 4[m/s]. The mean speed is 3.08[m/s] and 75% of the trips had speed of 3.71[m/s] and below.
> * 74.4% of the users of the bike share system are male, while 23.5% are female and 2.1% are other.
> * The majority of users of the Ford Go Bike System are Subscribers (i.e. users who subscribe to the monthly membership), representing 90.4% of the total users, while Customers represented 9.6%
> * the male users rode for lesser duration than the female and the other gender. The males also rode at higher speed than the females, while females and others rode for longer distance than the males.
> * The commuting distance for the subscribers is less than the average ride a customer takes.
> * Subscribers had far more rides per day in comparism with the Customers, and the saturday and sunday rides are the least.
> * subscriber riders move at higher speed than customers, this could be because they might be rushing to work or school, while customers are mostly tourists around the Bay Area.
> * Customer rode longer trips than subscriber. This explains the fact that subscribers are mainly commuters who take short trips to work/school rather than longer trips around the Bay Area.
> * Most Customer bike trips happen in hour 17, hour 18 and hour 8 during the weekdays with highest on Thursdays. In the weekend, the hour with the peak of bike trips is 13. The Subscriber user type uses the bike during the weekdays with the peak recorded in hours 8, 17, 18 and 9.
> * Subscribers who fall in the age group between 21-30 years old are the most common age group to use the bike sharing system. They also lead the spike which occurs across all age groups in Thursdays. Subscribers who fall in the 31-40 year old age group are the next most common age group to use the bike sharing system, and follow a similar trend as the 21-30 year olds on Thursdays. The youngest age group, the 10-20 years olds are the least common age group to use the bike sharing system followed by the oldest age group, the 51-60 years olds.
> * Customers who fall in the age group between 21-30 years old are the most common age group to use the bike sharing system on Mondays, saturdays and sundays. while the Customers who fall in the 31-40 year old age group are the most common age group to use the bike sharing system on every other day of the week. The youngest age group, the 10-20 years olds are the least common age group to use the bike sharing system except on sundays where they have more rides than the oldest age group, the 51-60 years olds.
> * The most bike trips duration for the male happen in hour 3 on wednesday and sunday and hour 2 on wednesday, the most bike trips duration for the female happen in hour 3 on sunday and hour 2 on saturday, while that of the other gender happen in hour 3 on Thursday and hour 7 on sunday.

>When we include a third variable, the insight became more complete. It essentially amplified the previous findings through different visuals and adding in more variables to compare to other variables.

>Finally, it was interesting to note that the users in the working class age range (21-40year) had very many rides as compared to the other age groups, both in the customer and subscriber categories. Which means that they were not only interested in the bikes for commuting purpose alone but also for vacations and tours.


## Key Insights for Presentation

> Which gender and User Type patronize the Ford GoBike System the most according to our data?

> Is there a relationship between the daily number of bike trips per user_type, and their age group?

> Is there a relationship between the number of Trips per Day, number of Trips per Hour and User type?

> What is the relationship between trip duration and user type and also their gender?

> Is there a relationship between the Trip Mean Duration per Day, the Trip Mean Duration per Hour and the Member Gender?


```python

```
