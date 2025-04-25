# Impacts of Wind Direction and Speed on Fuel Consumption in Commercial Flights
## Motivation
 This project aims to  understand the effects of wind direction and wind speed on fuel consumption in commercial flights. With this undderstanding we can have a better view of commercial flights' impacts on the environment since we know that fuel consumption has an impact on the environment. 
  
## Objective
 During this project, how fuel consumption in commercial flights is affected by wind direction and wind speed between United States and Europe will be analyzed to find a way to make commercial flights more sustainable for our environment.  
   
## Data That Will Be Used
**Flight Data:** Data of commercial flights between United States and Europe.  
  
-Distance flown (km).  
-Flight duration(h).  
-Speed (km/h).  
-Altitude (ft).  
-Route.  
-Aircraft model.  
  
**Wind Data:** Wind path and wind speed along the flight path.  
  
-Wind speed (km/h) in different altitudes.  
-Wind direction in different altitudes.  
-Jet streams(Headwind, Tailwind, Crosswind) and turbulence regions.  
  
**Fuel Consumption Data:** Fuel usage statistics for flights. For every tonne of fuel reduced, an equivalent amount of 3.15t of CO2 is avoided.  
  
-Fuel burned (kg). 
  
## Data Source
**Wind data:** ECMWF (European Centre for Medium-Range Weather Forecasts).  
Offers wind data which includes wind speed, direction, and patterns over the Atlantic Ocean (between United States and Europe).  
  
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

**H₀:** Wind speed and direction have no impact on fuel consumption in commercial flights.  
  
**H₁:** Wind speed and direction have a significant impact on fuel consumption in commercial flights.  

**4) Trend Analysis:**  

 I will try to understand if jet streams have an impact on fuel consumption. If yes, I will look into each jet stream's (headwinds, tailwinds, and crosswinds) impact on this fuel consumption.  
 I will also investigate peaks and plateaus of fuel consumption related to wind conditions.
  
   
  
  
  

