# Manitoba Weather API

## Description
describe api

## Resources
### Forecast
Contains information about Winnipeg's weather forecast, including temperature, humidity, precipitation, and wind direction.

## Endpoints and parameters
### GET `/forecast/{date}`

describe endpoint

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

(uses a query parameter to say which attribute we want the average of)

describe endpoint

describe parameters

#### Sample request

`https://api.manitobaweather.com/forecast/average?start=2023-03-20&end=2023-03-27&attribute=temperature`

#### Sample response

`{ "start_date":  "2023-03-20",  
   "end_date":  "2023-03-27",  
   "attribute":  "temperature",  
   "average":  "0°C"  }`
