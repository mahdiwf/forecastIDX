# forecastIDX
Forecasting using regression (SARIMAX) <br>
To predict the Indonesian stock market (IDX/JKSE) at the first part of 2023: bullish or bear?
# Annotations and Samplings
IDX closing prices
![image](https://github.com/mahdiwf/forecastIDX/assets/163992115/e70a7fcd-0ea1-4d26-bce8-5bdaae1c7fbc)

Observation:
1) The stock price from 2018 to 2020 was sideways in the range of 5500 - 6500 after trending up in 2017
2) There were huge dips in the stock prices in March 2020(due to the Pandemic).
3) The stock prices increased from 2020 (after the new normal) to early 2023
4) The stock price was sideways from mid 2022 to end 2022
So, what will happen in 2023 semester 1?

Decompose
![image](https://github.com/mahdiwf/forecastIDX/assets/163992115/f732e230-c2e5-40eb-b1aa-85a4950cfea1)

Observation:
1) Trend: downward trend followed by the mostly linear upward trend
2) Seasonality: Interestingly, it seems there is seasonality every 2.5-3 years
 * end of 2017 to 2020 (3+12+12 = 27 months)
 * early 2020 to mid 2022 (9+12+6 = 27 months)
3) Residuals: the index price is susceptible to random shocks and noise. Of course, this is the stock market.

Model diagnostics
![image](https://github.com/mahdiwf/forecastIDX/assets/163992115/ebaf8e06-95d1-42a5-b95e-a6b4e7a6bdcf)

It is not perfect, however, our model diagnostics suggest that the model residuals are nearly normally distributed.
Points on the Normal Q-Q Plot indicate the univariate normality of the dataset. If the data is not normally distributed, the points will deviate from the reference line.

IDX close price - Actual vs Forecast
![image](https://github.com/mahdiwf/forecastIDX/assets/163992115/9b92942c-e84b-4dc0-9b08-51cd2e5f246f)

The line plot shows the observed values compared to the rolling forecast predictions. Overall, this forecast aligns with the actual values very well, showing an upward trend starting from the beginning of the year.

IDX close price - six months forecast
![image](https://github.com/mahdiwf/forecastIDX/assets/163992115/29c8047f-21de-4cb1-9792-5a62c920c5d8)

Based on this forecast, the earlier part of 2023 will be neither bullish nor bearish. It will be in the sideways trading range between 6500 to 7000.
Let's confirm with the actual.

IDX close price - six months actual vs forecast
![image](https://github.com/mahdiwf/forecastIDX/assets/163992115/4e8315d8-3208-4180-b455-359c8252dc79)

Even though they are not very close, it confirms that in the first semester of 2023, the IDX/JKSE will be in sideways/swing in the range of 6500 to 7000.<be>
In the future, to improve the performance, I will add more predictors/technical indicators.

Reference:<br>
https://www.statsmodels.org/stable/generated/statsmodels.tsa.statespace.sarimax.SARIMAX.html <br>
https://www.digitalocean.com/community/tutorials/a-guide-to-time-series-forecasting-with-arima-in-python-3 <br>
