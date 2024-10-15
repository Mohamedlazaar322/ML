# Project: Solar Energy Forecasting
**Overview**
This project focuses on forecasting solar energy production using data from PVOutput in Sicily. The goal was to build multiple forecasting models and evaluate their performance, using a 30-minute aggregated dataset over a 30-day period. The initial data were at 5-minute intervals, but were resampled to 30-minute intervals due to computational constraints.

**Data**
Source: PVOutput (Sicily)
Time Interval: Originally 5-minute, resampled to 30-minute intervals.
Duration: 30 days.

**Models Used**
1. ARIMA (AutoRegressive Integrated Moving Average)
2. SARIMAX (Seasonal ARIMA with eXogenous variables)
3. Prophet
4. XGBoost
5. LSTM

**Results**

| Model   | MAE (kWh) | RMSE (kWh) |
|---------|-----------|------------|
| ARIMA   | 27.18     | 29.63      |
| SARIMAX | 11.73     | 13.79      |
| Prophet | 29.47     | 41.23      |
| XGBoost | 4.66      | 8.38       |
| LSTM    | 2.62      | 3.73       |

**ARIMA**: Performed poorly, likely due to its inability to handle the seasonality present in the data.

**SARIMAX**: Improved performance by accounting for seasonality, but still not optimal.

**Prophet**: Was one of the worst-performing models in this case, possibly due to overfitting or misalignment with the seasonal patterns of solar energy.

**XGBoost**: While LSTM performed the best, XGBoost stands out as a very strong contender, offering excellent predictive performance along with the added benefits of interpretability and potentially faster training times. Its performance suggests it's capturing the underlying patterns in your energy consumption data very effectively.

**LSTM**: Outperformed all other models, showing the best accuracy in both MAE and RMSE.

**Conclusion**
The LSTM and XGBoost clearly outperformed other models, the choice between them would depend on specific requirements such as interpretability needs, available computational resources, and the importance of squeezing out every last bit of predictive performance.
