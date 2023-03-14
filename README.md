# USA Airline Delay Cause Analysis

## Overview
- Cleaned the data of USA airline delay cause (data source: [Federal Aviation Administration](https://www.faa.gov/data_research)). Handled missing values, merged date time, and delimited geographic information in python.

- Analyzed and visualized the data from multiple perspectives and generated insights on time series features, delay cause, and geographic information.

- Used Holt-Winters model and forecasted Austin Airport performance in 2023. Optimized the models and increased the accuracy by 5% on average. Created and deployed the performance [dashboard](https://austin-ariport-delay-cause-dashboard.onrender.com) (click to see).

- In Oct 2022, I presented insights on choosing the least-likely-delayed airlines at Austin Airport during the 2022 Thanksgiving holiday in class. After holiday, my classmates gave me some positive feedback about the accuracy of the models according to their holiday travel experience.

![alt text](https://github.com/Doravado/usa_airline_delay_cause/blob/main/image/head.png)

## Code and Resources Used
- Tools: Jupyter Notebook, PyCharm<br>

- Packages: pandas, numpy, matplotlib, seaborn, plotly, statsmodels, dash

## Data Processing
- Replaced missing value on all columns with 0, considering the characteristics and application of feature data.

- Merged the 'year' and 'month' and created a new column, 'date,' which will be used to analyze time-series data.

- Delimited the 'airport_name' and created new columns, 'city' and 'state,' and cleaned the space in the text.

## Time Series Analysis
- Visualized delay minutes and the number of arriving flights to observe data trends and seasonality.

- Testified if data are stationary via ADF test to support data visualization insights.

- Key Insights:
  - From 2003 to 2017, the number of arriving flights goes down for the overall trend. However, it has skyrocketed since 2018 and peaked in 2019. The data plunge in 2020, expectedly. In 2022, flight traffic will return to the pre-pandemic level while still much lower than in 2019. On average, the number of arriving flights is highest in August and lowest in February.

  - From 2003 to 2022, the total delay minutes fluctuate severely since the variance magnitude of delay minutes is much bigger than that of arriving flights. However, on average, the delay minutes reach the highest point in July and lowest in September.

  - There is an asymmetry between the seasonality of the number of arriving flights and delay minutes. For example, June and July are the peak months for severe thunderstorms. Therefore, delay minutes hit the peak during the period, though flight traffic does not peak until August.

![alt text](https://github.com/Doravado/usa_airline_delay_cause/blob/main/image/delay%20minutes%20over%20years.png)

## Delay Cause Analysis
- Plotted each delay cause over the whole period and analyzed delay cause distribution.

- Created a specific table to display the delay cause distribution of each airline. Visualized and compared the delay cause of selected airlines.

- Key Insights:
  - 'Late_aircraft_delay' generate the most delay minutes every month.

  - Delay minutes hit the peak during Jun and Jul, though flight traffic does not reach the highest point until August. In June, both 'carrier_delay' and 'weather_delay' percentage increase. According to meteorological records, June and July, in particular, are the peak months for severe thunderstorms with high winds.
  
  -  In August, the percentages of 'carrier_delay' and 'nas_delay' jump up, which may be attributed to high flights this month.
  
  -  Delay cause of American Airlines and United Airlines are close to the benchmark. Due to old airplanes, Delta Airlines' percentage of its 'carrier_delay' is much higher than the benchmark. Southwest Airlines' percentage of its 'late_aircraft_delay' is much higher than the other three and the benchmark. According to my search, Southwest Airlines provides high-frequency flights for customers because of its supply chain strategy.

![alt text](https://github.com/Doravado/usa_airline_delay_cause/blob/main/image/delay%20cause%20over%20years.png)

## Geographic Information Analysis
- Created animated choropleth maps to show delay minutes and the number of arriving flights over the years.

- Key Insights:
  - California and Texas rank at the top regarding the number of arriving flights and delay minutes due to their large population. Florida is climbing to a higher rank as more people want to go to warm-weather destinations.

![alt text](https://github.com/Doravado/usa_airline_delay_cause/blob/main/image/animated_map.gif)

## Austin Airport Performance Forecast
- Used Holt-Winters model (based on trend and seasonality) and forecasted Austin airport performance (number of arriving flights and delay minutes) in 2023.

- Created and deployed the performance [report](https://austin-ariport-delay-cause-dashboard.onrender.com) (click to see the dashboard) via plotly.dash, including each airline's delay cause at Austin Airport since 2003.

- Key Insights:
  - Total delay minutes of Austin airport increases over time. Bad news for passengers.
  
  - There is an evident seasonality of delay minutes. It reaches a peak in August and then goes down in the rest of the months in the year. However, it goes up a little bit in Oct and Dec.
 
  - Based on the Holt-Winters model forecast, Nov is the lowest point in the last three months of a year; it decreases by 18% compared with Oct 2022. So Nov may be an excellent time to travel by flight.
  
  - Nov is the lowest point for most airlines, same as the total delay minutes of Austin airport. Southwest may be the best-performing airline during Nov 2022.

![alt text](https://github.com/Doravado/usa_airline_delay_cause/blob/main/image/dashboard2.png)

