# Energy Time Series Analysis 

The below is a quick predictive analysis I did using Facebook's Prophet module. Prophet is a procedure for forecasting time series data that fits non-linear trends to data with yearly, weekly, and daily seasonality; it will even handle holiday effects. On top of all of this it has outlier handeling and is robust to missing data and trend shifts. 


## Exploration 

The data is hourly energy consumption taken from PJM Interconnection LLC's website. PJM is part of the Eastern Interconnection grid operating an electric transmission system serving all or parts of Delaware, Illinois, Indiana, Kentucky, Maryland, Michigan, New Jersey, North Carolina, Ohio, Pennsylvania, Tennessee, Virginia, West Virginia, and the District of Columbia. The data has no missing values, spans from 2002 to 2018, and shows strong seasonality: 

<img width="997" alt="Screen Shot 2019-08-21 at 8 50 04 PM" src="https://user-images.githubusercontent.com/38504767/63557572-4a1f5d80-c517-11e9-9309-1f03d250316d.png">


A pairplot looking at the hour, week_of_year, and year varaibles shows some trends in energy consumption, especially strong in hour and week. 

<img width="1000" alt="Screen Shot 2019-08-21 at 8 49 20 PM" src="https://user-images.githubusercontent.com/38504767/63557578-573c4c80-c517-11e9-859c-1d896fb30dc6.png">

Plotting the average energy consumption by month one sees a very clear increase in the summer (air conditioning) and winter (shorter days and heating). Plotting the avg. energy consumption by day of the year shows a similar, more preceise view. 

<img width="536" alt="Screen Shot 2019-08-21 at 8 49 32 PM" src="https://user-images.githubusercontent.com/38504767/63557592-68855900-c517-11e9-976c-5e0b4b79c48f.png"> <img width="545" alt="Screen Shot 2019-08-21 at 9 23 38 PM" src="https://user-images.githubusercontent.com/38504767/63557597-6c18e000-c517-11e9-8c09-55a897d3ad56.png">

THe below charts show hourly energy consumption, but separate the trends by summer and winter. The summer trends make sense, as the day goes on and gets hotter, people'e AC units have to use more energy to keep their houses cool. In winter, however, there is a small dip in energy consumption around 3pm. My two theories for this are: 1) This is the hottest part of the day so it takes less energy to heat the house 2) Kids have not gotten home yet from school. When they get home the energy consumption spikes. 

<img width="923" alt="Screen Shot 2019-08-21 at 8 49 53 PM" src="https://user-images.githubusercontent.com/38504767/63557614-8357cd80-c517-11e9-93b8-65b820976c85.png">

## Prophet Model 

To use Facebook's Prophet procedure to model the data, the dataframe has to have 2 columns: The date (as type datetime) with column header 'ds', and the dependent variable one is predicting with column header 'y'.

<img width="222" alt="Screen Shot 2019-08-22 at 7 39 36 PM" src="https://user-images.githubusercontent.com/38504767/63557657-9e2a4200-c517-11e9-9355-ea6e82798115.png">

For this analysis I split the data at 8/3/2017 to predict the last year of energy consumption using Prophet. Below are the trend, weekly, yearly, and daily components as determined by the model. 
<img width="644" alt="Screen Shot 2019-08-21 at 8 52 44 PM" src="https://user-images.githubusercontent.com/38504767/63557670-a6827d00-c517-11e9-8e2b-49467997e54b.png">
<img width="646" alt="Screen Shot 2019-08-21 at 8 52 54 PM" src="https://user-images.githubusercontent.com/38504767/63557678-a7b3aa00-c517-11e9-8ddd-ba5adebfd16d.png">

It uses these components along with outlier handling to predict the last year of data (blue). Adding the actuals (red) one can see that the model generally captures the trend pretty well and ends up with a mean average error of 3785 megawatts.


<img width="993" alt="Screen Shot 2019-08-21 at 8 52 25 PM" src="https://user-images.githubusercontent.com/38504767/63557698-c154f180-c517-11e9-86c5-6bd2032de74a.png">




