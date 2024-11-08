# Project: Solar Energy Forecasting
**Overview**
This project focuses on forecasting multivariate time series solar energy production. the data were gathred from PVOutput in Sicily. The goal was to build multiple forecasting models and evaluate their performance, using a 30-minute aggregated dataset over a 30-day period. The initial data were at 5-minute intervals, but were resampled to 30-minute intervals due to computational constraints.

**Data**
Source: PVOutput (Sicily)
Time Interval: Originally 5-minute, resampled to 30-minute intervals.
Duration: 30 days.

**Models Used**
1. VAR
2. Prophet
3. XGBoost
4. LSTM

**Results**

| Model   | MAE (kWh) | RMSE (kWh) |
|---------|-----------|------------|
| Var     | 0.67      | 0.82       |
| Prophet | 0.24      | 0.31       |
| XGBoost | 4.65      | 6.55       |
| LSTM    | 2.14      | 3.27       |


**VAR**: The model performed relatively well but did not achieve the lowest errors overal.The VAR is useful for capturing relationships across multiple variables, 
          which may explain the solid performance here. However is limited in handling non-linearities or seasonal patterns, which could be essential for solar 
          energy forecasting. 

**Prophet**: Outperformed all other models, showing the best accuracy in both MAE and RMSE. Prophet is adept at capturing seasonality and holiday effects, which 
             might have helped it model solar irradiance and daily energy fluctuations effectively.

**XGBoost**: Was one of the worst-performing models in this case, possibly due to overfitting or misalignment with the seasonal patterns of solar energy.

**LSTM**: This model has performed reasonable well achiving,aciving a balance between accuracy and generalisation, but still not optimal.



## **Conclusion**
Prophet emerges as the most effective model for this dataset, achieving the lowest MAE and RMSE. This suggests that its ability to model seasonal patterns is well-suited for solar energy data. However, VAR and LSTM also showed promising results and could be revisited with further tuning or additional data. XGBoost's relatively high errors indicate it may be less suited for this task, potentially due to a lack of suitable feature engineering or the non-linear nature of solar energy patterns.
