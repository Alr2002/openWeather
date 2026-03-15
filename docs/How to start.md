# How to start
## Prerequisites
To start working with the One Call API 3.0, register and log in to your account. Then select your subscription plan and receive your API key.

!!! info "Note"

    One Call API 3.0 is included in the "One Call by Call" subscription **only**.     
    Select the type of data you want to receive from One Call API 3.0:  
         - Current and forecast weather data  
         - Weather overview

## Current and forecast weather data

This endpoint is used to get access to current weather, minute forecast fo 1 hour, hourly forecast for 48 hours, daily forecast for 8 days and government weather alerts.

## How to make an API call

### API call
```
https://api.openweathermap.org/data/3.0/onecall?lat={lat}&lon={lon}&exclude={part}&appid={API key}
```

**Method** - GET

|Parameter|Required/Optional|Description|
-----------|:-------:|-----------|
`lat`        |required|Latitude, decimal (-90; 90). If you need the geocoder to automatic convert city names and zip-codes to geo coordinates and the other way around, please use our [Geocoding API](https://openweathermap.org/api/geocoding-api)
`lon`|required|Longitude, decimal (-180; 180). If you need the geocoder to automatic convert city names and zip-codes to geo coordinates and the other way around, please use our [Geocoding API](https://openweathermap.org/api/geocoding-api)
`appid`|required|Your unique API key (you can always find it on your account page under the "API key" tab)
`exclude`|optional|By using this parameter you can exclude some parts of the weather data from the API response. It should be a comma-delimited list (without spaces). Available values: `current` `minutely` `hourly` `daily` `alerts`
`units`|optional|Units of measurement `standard`,`metric` and `imperial` units are available. If you do not use the `units` parameter, `standard` units will be applied by default.
`lang`|optional|You can use the `lang` parameter to get the output in your language. 

### Example of API Request
**GET** https://api.openweathermap.org/data/3.0/onecall?lat=46.47747&lon=30.73262&exclude=hourly,daily,minutely&units=metric&appid={API key}

### Example of API Response
```
{
    "lat": 46.4775,
    "lon": 30.7326,
    "timezone": "Europe/Kyiv",
    "timezone_offset": 7200,
    "current": {
        "dt": 1772996948,
        "sunrise": 1772943848,
        "sunset": 1772985119,
        "temp": 6.04,
        "feels_like": 6.04,
        "pressure": 1033,
        "humidity": 66,
        "dew_point": 0.18,
        "uvi": 0,
        "clouds": 2,
        "visibility": 10000,
        "wind_speed": 0.76,
        "wind_deg": 328,
        "wind_gust": 1.34,
        "weather": [
            {
                "id": 800,
                "main": "Clear",
                "description": "clear sky",
                "icon": "01n"
            }
        ]
    }
}
```

### Fields in API response
> :information_source: &#8505; If you do not see some of the parameters in your API response it means that these weather phenomena are just not happened for the time of measurement for the city or location chosen. Only really measured or calculated data is displayed in API response.

- `lat` Latitude of the location, decimal (−90; 90)
- `lon` Longitude of the location, decimal (-180; 180)
- `timezone` Timezone name for the requested location
- `timezone_offset` Shift in seconds from UTC
- `current` **Current weather data API response**
  - `current.dt` Current time, Unix, UTC
  - `current.sunrise` Sunrise time, Unix, UTC. For polar areas in midnight sun and polar night periods this parameter is not returned in the response
  - `current.sunset` Sunset time, Unix, UTC. For polar areas in midnight sun and polar night periods this parameter is not returned in the response
  - `current.temp` Temperature. Units - default: kelvin, metric: Celsius, imperial: Fahrenheit. **How to change units used**
  - `current.feels_like` Temperature. This temperature parameter accounts for the human perception of weather. Units – default: kelvin, metric: Celsius, imperial: Fahrenheit.
  - `current.pressure` Atmospheric pressure on the sea level, hPa
  - `current.humidity` Humidity, %
  - `current.dew_point` Atmospheric temperature (varying according to pressure and humidity) below which water droplets begin to condense and dew can form. Units – default: kelvin, metric: Celsius, imperial: Fahrenheit
  - `current.clouds` Cloudiness, %
  - `current.uvi` Current UV index.
  - `current.visibility` Average visibility, metres. The maximum value of the visibility is 10 km
  - `current.wind_speed` Wind speed. Wind speed. Units – default: metre/sec, metric: metre/sec, imperial: miles/hour. **How to change units used**
  - `current.wind_gust` (where available) Wind gust. Units – default: metre/sec, metric: metre/sec, imperial: miles/hour. **How to change units used**
  - `current.wind_deg` Wind direction, degrees (meteorological)
  - `current.rain`
    - `current.rain.1h` (where available) Precipitation, mm/h. Please note that only mm/h as units of measurement are available for this parameter
  - `current.snow`
    - `current.snow.1h` (where available) Precipitation, mm/h. Please note that only mm/h as units of measurement are available for this parameter
  - `current.weather`
    - `current.weather.id` **Weather condition id**
    - `current.weather.main` Group of weather parameters (Rain, Snow etc.)
    - `current.weather.description` Weather condition within the group (**full list of weather conditions**). Get the output in your language
    - `current.weather.icon` Weather icon id. **How to get icons**
- `minutely` Minute forecast weather data API response
  - `minutely.dt` Time of the forecasted data, unix, UTC
  - `minutely.precipitation` Precipitation, mm/h. Please note that only mm/h as units of measurement are available for this parameter
- `hourly` Hourly forecast weather data API response
  - `hourly.dt` Time of the forecasted data, Unix, UTC
  - `hourly.temp` Temperature. Units – default: kelvin, metric: Celsius, imperial: Fahrenheit. **How to change units used**
  - `hourly.feels_like` Temperature. This accounts for the human perception of weather. Units – default: kelvin, metric: Celsius, imperial: Fahrenheit.
  - `hourly.pressure` Atmospheric pressure on the sea level, hPa
  - `hourly.humidity` Humidity, %
  - `hourly.dew_point` Atmospheric temperature (varying according to pressure and humidity) below which water droplets begin to condense and dew can form. Units – default: kelvin, metric: Celsius, imperial: Fahrenheit.
  - `hourly.uvi` UV index
  - `hourly.clouds` Cloudiness, %
  - `hourly.visibility` Average visibility, metres. The maximum value of the visibility is 10 km
  - `hourly.wind_speed` Wind speed. Units – default: metre/sec, metric: metre/sec, imperial: miles/hour. **How to change units used**
  - `hourly.wind_gust` (where available) Wind gust. Units – default: metre/sec, metric: metre/sec, imperial: miles/hour. **How to change units used**
  - `hourly.wind_deg` Wind direction, degrees (meteorological)
  - `hourly.pop` Probability of precipitation. The values of the parameter vary between 0 and 1, where 0 is equal to 0%, 1 is equal to 100%
  - `hourly.rain`
    - `hourly.rain.1h` (where available) Precipitation, mm/h. Please note that only mm/h as units of measurement are available for this parameter
  - `hourly.snow`
    - `hourly.snow.1h` (where available) Precipitation, mm/h. Please note that only mm/h as units of measurement are available for this parameter
  - `hourly.weather`
    - `hourly.weather.id` Weather condition id
    - `hourly.weather.main` Group of weather parameters (Rain, Snow etc.)
    - `hourly.weather.description` Weather condition within the group (full list of weather conditions). Get the output in your language
    - `hourly.weather.icon` Weather icon id. **How to get icons**

