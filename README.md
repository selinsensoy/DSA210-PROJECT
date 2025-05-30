# Impacts of Wind Speed on Fuel Consumption in Commercial Flights
## Motivation
 This project aims to  understand the effects of wind speed on fuel consumption in commercial flights. With this undderstanding we can have a better view of commercial flights' impacts on the environment since we know that fuel consumption has an impact on the environment. 
  
## Objective
 During this project, how fuel consumption in commercial flights is affected by wind speed at some cities in Germany will be analyzed to find a way to make commercial flights more sustainable for our environment.(I will be looking at Istanbul and Bursa since my wind data is from that region)  
   
## Data That Will Be Used
**Flight Data:** Data of commercial flights in Hungary.  
  
-Distance flown (km).  
-Flight duration(h).  
-Speed (km/h).  
-Altitude (ft).  
-Route.  
-Aircraft model.  
  
**Wind Data:** Wind path and wind speed along the flight path.  
  
-Wind speed (km/h).     
  
**Fuel Consumption Data:** Fuel usage statistics for flights. For every tonne of fuel reduced, an equivalent amount of 3.15t of CO2 is avoided.  
  
-CO2 emission (tonnes). 
  
## Data Source
**Wind data:** ECMWF (European Centre for Medium-Range Weather Forecasts).  
Offers wind data which includes wind speed, patterns over the Atlantic Ocean (between United States and Europe).  
  
**Flight Data:** Eurocontrol.  
Offers real-time and historical flight data to airlines, airports, and aviation authorities.  
  
**Fuel consumption Data:** Eurocontrol.  
Also provides data on fuel consumption and route efficiency.  

## Analysis Plan:
**1) Collecting Data**  
  
**Flight Data:** I will request access to Eurocontrol's aviation data. If my access request is denied, I will collect necessary data from open aviation databases or use flight tracking APIs.  
  
**Wind Data:** I will obtain weather data from ECMWF, using ECMWF’s API.  
  
**Fuel Consumption Data:** I will request access to Eurocontrol's aggregated fuel consumption data. If my access request is denied, I will obtain data that I need from airlines or aviation authorities.  

  *I will combine these data using numpy and pandas.*  
  
**2) Visualisation:**  
  
  I will be using scatter plots for fuel consumption-wind speed/direction relation, heatmap for  correlations between fuel Consumption and wind variables, time series plot to show fuel consumption over time with the help of matplotlib.  

**3) Hypothesis Testing:**  

**H₀:** Wind speed have no impact on fuel consumption in commercial flights.  
  
**H₁:** Wind speed have a significant impact on fuel consumption in commercial flights.  

**4) Trend Analysis:**  

 In this project, I will explore how wind speed affects fuel consumption and CO₂ emissions in commercial flights. The objective is to determine whether there is a measurable relationship between wind speed and fuel efficiency. I will analyze the data to identify trends, such as whether higher wind speeds lead to increased or decreased fuel use. I will try to predict fuel consumption based on wind speed.  
  
  
## Data Description  

 **Date:** Date of flight  

**Route:** Flight route identifier  

**Fuel Consumption (kg):** Fuel consumed during the flight  

**Wind Speed (km/h):** Average wind speed during the flight  

*The dataset was cleaned by removing entries with missing fuel consumption or wind speed values.*  

#  Visualisation   
   ### Daily Average Wind Speed by City:  
   ![image](https://github.com/user-attachments/assets/da1312f6-52c2-4bcd-91ca-340b58487f64)  
  

- The line chart plots **daily average wind speed** for:
  - **Berlin** (blue line)
  - **Dortmund** (orange line)
- **X-axis**: Dates from 2019-01 to 2021-01
- **Y-axis**: Wind speed values (unit unspecified – likely m/s or km/h)
- Wind speeds fluctuate significantly over time, with Berlin generally experiencing **higher peak values** than Dortmund.
- **Spikes** in wind speed may represent storms or seasonal wind patterns.


  ### Daily Total Fuel Consumption by City:  
  ![image](https://github.com/user-attachments/assets/155926a8-7866-45f3-ac67-6b7679242dfd)  


- The line chart plots **total daily fuel consumption** in kilograms for:
  - **Berlin** (blue line)
  - **Dortmund** (orange line)
- **X-axis**: Time range from January 2019 to January 2021
- **Y-axis**: Fuel consumption in **kilograms (kg)**
- **Berlin consistently consumes more fuel** than Dortmund across the entire period.
- Both cities show a **regular pattern** suggesting weekly or seasonal trends.
- Drops and spikes may represent weekends, holidays, or unusual activity levels.  
  ### Fuel Consumption vs. Wind Speed (with regression):   
  ![image](https://github.com/user-attachments/assets/225056dc-ed11-48d8-99b1-7d4ed0274f37)
  

- A **scatter plot** of daily data points for:
  - **X-axis**: Wind Speed
  - **Y-axis**: Fuel Consumption (kg)
  - Color-coded by city:
    - Berlin (blue)
    - Dortmund (orange)
- A **linear regression line** is plotted to show the overall trend.
- The plot suggests a **positive correlation** — as wind speed increases, fuel consumption tends to increase slightly.  

  ### Jointplot (scatter + histograms + regression) for overall data:  
  ![image](https://github.com/user-attachments/assets/0f80ccf6-bf61-4abb-b69a-9982ffb9986b)  


- **Most data points are clustered** in the lower range of wind speed (0–150) and fuel consumption (4500–5500 kg).
- The **regression line** suggests a weak upward trend — higher wind speeds may slightly increase fuel consumption.
- **Distribution plots** reveal:
  - Wind speed has a **right-skewed** distribution.
  - Fuel consumption is more **normally distributed** around 5000–5200 kg.  

  # Hypotheses Testing  
  The following hypothesis was tested:  

  **H₀:** Wind speed has no impact on fuel consumption in commercial flights.  

  **H₁:** Wind speed has a significant impact on fuel consumption in commercial flights.  
  ![image](https://github.com/user-attachments/assets/77a01331-1a96-4e61-9bfe-2475eef2d71d)  
  | Parameter | Value    |
| --------- | -------- |
| Slope     | 1.0094   |
| Intercept | 4775.57  |
| R-squared | 0.0441   |
| P-value   | < 0.0001 |
  
-The p-value is effectively zero, which is less than the significance level α = 0.05, so we reject the null hypothesis (H₀).  

-The positive slope (1.0094) indicates that fuel consumption tends to increase as wind speed increases.  

-However, the low R-squared value (0.0441) suggests that wind speed explains only a small portion (~4.4%) of the variance in fuel consumption, meaning other factors also play a significant role.  
**Conclusion:**  
 Based on the analysis, wind speed has a statistically significant impact on fuel consumption in commercial flights, although it is not the sole influencing factor.  

# Machine Learning Analysis:  
To further explore the relationship between wind speed and fuel consumption, two regression models were trained and evaluated:  

**Linear Regression:** A simple, interpretable model assuming a linear relationship.  

**Random Forest Regression:** A more complex ensemble model capable of capturing non-linear relationships.  
## Linear Regression Model  
![image](https://github.com/user-attachments/assets/53713675-47bb-4eb2-aa3e-f79912278dba)  

| Metric   | Linear Regression | 
| -------- | ----------------- | 
| **RMSE** | 544.43 kg         | 
| **MAE**  | 442.01 kg         | 
| **R²**   | 0.0096            |   


-The low R² value (close to 0) indicates that the Linear Regression model does not explain much of the variance in fuel consumption based on wind speed alone.  

-This suggests the relationship between wind speed and fuel consumption might not be simply linear, or other factors influence fuel consumption significantly.  
## Random Forest Model  
![image](https://github.com/user-attachments/assets/f6eafd35-fd7b-4f21-87b4-a71f883d280d)  


| Metric   | Random Forest |
| -------- | ------------- |
| **RMSE** | 471.01 kg     |
| **MAE**  | 370.16 kg     |
| **R²**   | 0.2587        |  


-The Random Forest model shows better performance across all metrics compared to Linear Regression. 


-The higher R² value (~0.26) indicates it explains about 26% of the variance in fuel consumption, capturing more complex and non-linear relationships.  
## Conclusion  


| Metric   | Linear Regression | Random Forest |
| -------- | ----------------- | ------------- |
| **RMSE** | 544.43 kg         | 471.01 kg     |
| **MAE**  | 442.01 kg         | 370.16 kg     |
| **R²**   | 0.0096            | 0.2587        |  



The Random Forest model significantly outperforms the Linear Regression model in predicting fuel consumption from wind speed. This suggests that the impact of wind speed on fuel consumption is likely non-linear and influenced by other interacting factors that Random Forest can capture better. Therefore, for predicting fuel consumption based on wind speed and related variables, advanced machine learning models like Random Forest should be preferred over simple linear models.  

# Future Outlook

While this study demonstrates that wind speed significantly impacts fuel consumption in commercial flights, there are several opportunities to enhance and expand this research:

1. **Incorporate Additional Meteorological Factors:**  
   Future work could include wind direction, turbulence, temperature, and atmospheric pressure to capture more complex weather effects on fuel efficiency.

2. **Expand Geographical Scope:**  
   Extending the analysis beyond Istanbul and Bursa to include other airports or regions would improve the generalizability of the findings.

3. **Use More Advanced Machine Learning Models:**  
   Exploring other algorithms such as Gradient Boosting Machines, Neural Networks, or ensemble methods could potentially improve prediction accuracy and reveal deeper insights.

4. **Integrate Real-Time Data:**  
   Leveraging live flight and weather data streams could enable dynamic fuel consumption predictions, supporting real-time flight planning and optimization.

5. **Environmental Impact Assessment:**  
   Coupling fuel consumption models with CO₂ emission calculations can provide actionable insights for reducing aviation’s environmental footprint.

6. **Policy and Operational Recommendations:**  
   Ultimately, this research can inform airline operational strategies and policy-making aimed at reducing fuel use and emissions under varying wind conditions.

By pursuing these avenues, future research can contribute to making commercial aviation more sustainable and environmentally responsible.















  
  
  

