# Manitoba Weather API

## Description
This is a REST API that provides resources to help people in Manitoba with weather forecasts and plan their day to day events.

Users will be able to pick a city and a date, then find out the average temperature of the day and whether it is going to rain or snow. They may also specify a venue or business to check how occupied it will be on that day.

## Resources
### Forecast
Contains information about Winnipeg's weather forecast, including temperature, humidity, precipitation, and wind direction.

## Endpoints and parameters
### GET `/forecast/{date}`

Retrieves the weather forecast for a specified date and location. Optionally specifying a venue will retrieve that venue's predicted popularity for the day.

**Parameters**

| Name | Type | Required? | Description|
|---|---|---|---|
|`date`| string | Yes | The date to retrieve the forecast for in `YYYY-MM-DD` format. |
|`location`| string| Yes | The name of the city or town to retrieve the weather forecast for. |
|`venue`| string | No | The name of the venue to retrieve the popularity for. |

#### Sample request

`curl -X GET "http://api.manitobaweather.com/forecast/2023-03-27?location=Winnipeg"`

#### Sample response

```
{
   "date":  "2023-03-27",
   "temperature":  "-1°C",
   "humidity":  "60%",  
   "precipitation":  "0.0 mm",  
   "wind_direction":  "NE",  
   "wind_speed":  "10 km/h"
}
```

### GET `/forecast/average`

Retrieves the average value of a specified weather attribute for a range of dates.

**Parameters**

| Name | Type | Required? | Description|
|---|---|---|---|
|`start_date`| string | Yes | The start of the date range to retrieve the forecast for in `YYYY-MM-DD` format. |
|`end_date` | string | Yes | The end of the date range to retrieve the forecast for in `YYYY-MM-DD` format. |
|`location`| string| Yes | The name of the city or town to retrieve the weather forecast for. |
|`attribute`| string | Yes | The weather attribute for which to calculate the average. Must be one of: `"temperature"`, `"humidity"`, `"precipitation"`, `"wind_speed"`, `"wind_direction"`.|

#### Sample request

`curl -X GET "https://api.manitobaweather.com/forecast/average?start=2023-03-20&end=2023-03-27&location=Winnipeg&attribute=temperature"`

#### Sample response

```
{
   "start_date":  "2023-03-20",  
   "end_date":  "2023-03-27",
   "location": "Winnipeg",
   "attribute":  "temperature",  
   "average":  "0°C"
}
```
