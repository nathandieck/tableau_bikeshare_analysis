# Citibike Usage Patterns

- The assignment involved analyzing use patterns for the Citibike bikeshare program in New York City and identifying key trends and phenomena that might be of interest to planners and other stakeholders.
- This analysis uses Tableau to identify and visualize these phenomena. 
- The tableau notebook is located on the [Tableau Public Server](https://public.tableau.com/profile/nathan.dieck#!/vizhome/Tableau_Challenge_Workbook/CitibikeUsePatterns?publish=yes).

## Overview
* Data from the first full week of April in 2016 and 2019 were compared.

Data on individual rides were downloaded from the Citibike website and cleaned and modified in preparation for analysis. Direct modification of the CSV was used to isolate only the two weeks under investigation (the first full week of April 2016, beginning 4/3, and the first full week of April 2019, beginning 4/7) and to address a discrepency between the ways that ride dates and times were reported in those two years. Python code was developed to further modify the data, splitting the date into its own column and calculating for each station in the sample whether the station was a net aggregator or a net disperser of bicycles. 

To control for an obvious confound in use patterns, namely the weather, a separate dataset was downloaded from the National Oceanic and Atmospheric Administration (NOAA) containing the daily weather for those two weeks. This dataset was usable as-is and was merged on the date while in Tableau. 

These data were then used to create a series of visualizations in Tableau on program growth and use patterns for the two time periods. 

## Phenomenon #1: Program growth
* Predictable program growth was observed. 

The program grew according to a variety of metrics and operational definitions. The number of stations in the system increased by 60% while the number of bikes in the system, the number of individual trips, and the overal distance traveled all roughly tripled. By these measures, the program has been very successful in achieving sustained growth over time. 

The first dashboard in the presentation shows the growth in terms of quantitative statistics and in terms of geographic footprint. We see that the physical footprint of the program has expanded over the three years, while traffic at stations which existed in 2016 usually had expanded by 2019. 

## Phenomenon #2: Difference in use between customers and subscribers
* Use patterns appear to remain largely consistent, with slight variations from year to year. However, subscribers use bikes differently than customers. 

The program breaks down their user base into "subscribers" and "customers" with "customers" presumed to be users who have no ongoing subscription. It is a consistent pattern in both April 2016 and April 2019 that "customers" account for a small percentage of the overall business in terms of trips taken and distance traveled. However, it is notable that customers take much longer trips on average than subscribers. However, from 2016 to 2019, the percentage of trips made by customers doubled (from 6% to 12% of total trips) while the total percentage of distance traveled increased from 21% to 29%. Average distance decreased from 3.30 km to 2.69. 

A separate observation is the way bikes are used differently on different days. The number of trips taken rise during the week and fall again during the weekend. However, curiously, the total number of seconds traveled increases considerably during the weekend, well exceeding travel times on any given weekday. 

Upon further investigation, this turns out to be a function of which users are using bikes on which days. As noted previously, subscribers take more trips, but for fewer average seconds, than customers do. An analysis of which users use bikes on which days explains the data trend: Customer use is largely limited to the weekends while subscriber use occurs more often during the week. Customers use the bikes on fewer, longer trips than subscribers do. 

This observation both answers and raises questions. It seems to suggest that subscribers are usually commuters and customers are usually on weekend excursions. Inversely it suggests that commuters see the economic benefits of subscribing vs. paying the presumably larger one-off fee. However, one question that remains unanswered by the data is why the discrepency exists. One possibility is that distances traveled vary - commuter/subscribers might simply use a bike to get from their train station or bus stop to their place of work while customer/excursionists are usually on more of a sojourn. Another possibility is fitness levels, with regular users being able to travel the same distance faster than infrequent users due to being accustomed to the bikes. 

## Phenomenon 3: Role of Weather
* Weather predicts bike usage and temperature is a greater predictor of use than precipitation over the two weeks examined.

The two weeks being surveyed showed variations in both preciptation levels and temperature levels, a fortunate occurance. We'd predict that both rain and cold temperatures would have an impact on bike use and we find that they both seem to. 

However, rainfall appears to have a limited impact on both the number of trips taken and the duraton of those trips. Both 2016 and 2019 featured days of fairly heavy rainfall and rainfall corresponds to dips in both the number of trips and their duration. This is not a surprise. However, even when the rain was heavy the dips were usually slight. 

More surprising is that both number of trips and trip duration match the curves for daily average temperature extremely tightly - that is, trips and durations go up as temperatures go up and drop again reliably when temperatures fall. 

One should note when considering these data that NOAA records total rainfall over the day. One possible explanation for the limited impact of rainfall is that it occurred at night, during off-peak hours. 

## Phenomenon 4: Geographic 
* Many of the most frequently used stations are roughly in the center of program area, in midtown Manhattan. Interestingly, many of these stations operate at a net loss in terms of bicycle inventory. 

The geographic data show that many of the stations from which trips are most frequently undertaken are also in the center of the city, in midtown Manhattan. This is predictable, both because of the density of Manhattan's business and residential communities and because it is in the geographic center of a program known for making many shorter trips rather than long hauls on bicycles. While the 'trips taken' visualization shows that any station in the system is used as a departure point for cross-system trips, it also shows that most trops are fairly local and are often between Manhattan and Manhattan or between Manhattan and another borough. 

What is more interesting is that many of the stations in midtown Manhattan disperse rather than aggregate bicycles. The color used on the map shows the extent to which each bicycle station disperses (red) or aggregates (green) bicycles. Many of the most used stations in midtown are net dispersers - they dispatch more bikes than they recieve. In two weeks, some stations 'lost' more than 200 bicycles, which presumably needed to be replaced by Citibike employees. Less-trafficked stations in lower and upper Manhattan tend to be aggregators, though with the exception of stations bordering Central Park few stations receive large amounts of traffic (remember that the size of the dots measure departures rather than arrivals, so it is actually possible as aggregators that the Central Park stations receive more traffic than the map suggests). 

One plausible conclusion for this pattern is that more commuters (subscribers) use the bikes to leave work than to arrive at work in the morning. Wikipedia describes Midtown as the center of New York's commercial district, so there is some evidence this may be true; moreover previously discussed data show that the busiest stations see most of their departures in the evening. As a former bicycle commuter, this makes sense: arriving to work in the morning leaves the commuter with problems of personal presentation and punctuality that are not concerns in the evening. 

## Conclusions

The data show the following patterns fairly clearly: 

- The program grew markedly over three years by most of the operational definitions that can be extracted by the data. This can be interpreted as a successful program. 
- There are two predominant classes of user: the subscriber who appears to be a daily commuter, and the customer who appears to be a weekend excursionist. The majority of travel is undertaken by subscribers and customer use spikes during the weekends. Customers use the bicycles longer than subscribers for reasons speculated on previously. 
- While heavy precipitation does deter bicycle use somewhat, changes in temperature are a stronger predictor of bicycle use.
- It is likely though not confirmed by the data that bicycle commuters are likely to employ their bicycles to commute home in the evening more often than to work in the morning. Central Park is a popular destination for bicycle users. 