# Manitoba Weather API

## Description
This is a REST API that provides resources to help people in Manitoba with weather forecasts and plan their day to day events. 
Users will be allowed to pick the city and the unit of temperature they are looking to learn more about.
In addition, users will have the luxury of finding out the average temperature of the day and whether it is going to rain or snow. 

## Resources
### Forecast
Contains information about Winnipeg's weather forecast, including temperature, humidity, precipitation, and wind direction.

## Endpoints and parameters
### GET `/forecast/{date}`

Retrieves the weather forecast and the busyness status for a specified date and location.

**Parameters:**

-   `date` (required): The date to retrieve the forecast for in `YYYY-MM-DD` format.
-   `location` (required): The name of the city or town to retrieve weather forecast for.
-   `venue` (optional): The name of the venue to retrieve the busyness status for.

#### Sample request

`http://api.manitobaweather.com/forecast/2023-03-27`

#### Sample response

`{ "date":  "2023-03-27",
   "temperature":  "-1°C",
   "humidity":  "60%",  
   "precipitation":  "0.0 mm",  
   "wind_direction":  "NE",  
   "wind_speed":  "10 km/h"  }`

### GET `/forecast/average`

Retrieves the average value of a specified weather attribute for a range of dates.

**Parameters:**

-   `start_date` (required): The start date to retrieve the forecast for in `YYYY-MM-DD` format.
-   `end_date` (required): The end date to retrieve the forecast for in `YYYY-MM-DD` format.
-   `attribute` (required): The weather attribute for which to calculate the average (e.g., temperature, humidity, precipitation, wind_speed, wind_direction).
#### Sample request

`https://api.manitobaweather.com/forecast/average?start=2023-03-20&end=2023-03-27&attribute=temperature`

#### Sample response

`{ "start_date":  "2023-03-20",  
   "end_date":  "2023-03-27",  
   "attribute":  "temperature",  
   "average":  "0°C"  }`
