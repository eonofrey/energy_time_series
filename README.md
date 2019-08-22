# energy_time_series

The below is a quick predictive analysis I did using Facebook's Prophet module. Prophet is a procedure for forecasting time series data that fits non-linear trends to data with yearly, weekly, and daily seasonality; it will even handle holiday effects. On top of all of this it has outlier handeling and is robust to missing data and trend shifts. 


## Exploration 

Starting with a quick look at the raw data, you see it's a time series of megawatt consumption in the northeast region of the United States. The data is recorded hourly and spans from 2002 to 2018 with no missing values. 


A pairplot looking at the hour, week_of_year, and year varaibles shows some trends in energy consumption, especially strong in hour and week. 



Plotting the average energy consumption by month one sees a very clear increase in the summer (air conditioning) and winter (shorter days and heating). Plotting the avg. energy consumption by day of the year shows a similar, more preceise view. 


