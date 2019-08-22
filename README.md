# energy_time_series

The below is a quick predictive analysis I did using Facebook's Prophet module. Prophet is a procedure for forecasting time series data that fits non-linear trends to data with yearly, weekly, and daily seasonality; it will even handle holiday effects. On top of all of this it has outlier handeling and is robust to missing data and trend shifts. 


## Exploration 

The data is hourly energy consumption taken from PJM Interconnection LLC's website. PJM is part of the Eastern Interconnection grid operating an electric transmission system serving all or parts of Delaware, Illinois, Indiana, Kentucky, Maryland, Michigan, New Jersey, North Carolina, Ohio, Pennsylvania, Tennessee, Virginia, West Virginia, and the District of Columbia. The has no missing values and spans from 2002 to 2018.


A pairplot looking at the hour, week_of_year, and year varaibles shows some trends in energy consumption, especially strong in hour and week. 



Plotting the average energy consumption by month one sees a very clear increase in the summer (air conditioning) and winter (shorter days and heating). Plotting the avg. energy consumption by day of the year shows a similar, more preceise view. 

THe below charts show hourly energy consumption, but separate the trends by summer and winter. The summer trends make sense, as the day goes on and gets hotter, people'e AC units have to use more energy to keep their houses cool. In winter, however, there is a small dip in energy consumption around 3pm. My two theories for this are: 1) This is the hottest part of the day so it takes less energy to heat the house 2) Kids have not gotten home yet from school. When they get home the energy consumption spikes. 



