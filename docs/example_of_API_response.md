# Example of API response

## Example of API response

??? note "JSON"

    ``` json linenums="1"
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

## Fields in API response

!!! info "Note"

    If you do not see some of the parameters in your API response it means that these weather phenomena are just not happened for the time of measurement for the city or location chosen. Only really measured or calculated data is displayed in API response.

|Parameter|Description|
|:-----------|:-----------|
|lat|Latitude of the location, decimal (−90; 90)|
|lon|Longitude of the location, decimal (-180; 180)|
|timezone|Timezone name for the requested location|
|timezone_offset|Shift in seconds from UTC|
|**current**|**Current weather data API response**|
 |<ul><li> current.dt </li>|Current time, Unix, UTC|
 |<ul><li> current.sunrise </li> | Sunrise time, Unix, UTC. For polar areas in midnight sun and polar night periods this parameter is not returned in the response |
 |<ul><li> current.sunset </li>| Sunset time, Unix, UTC. For polar areas in midnight sun and polar night periods this parameter is not returned in the response |
 |<ul><li> current.temp </li>| Temperature. Units - default: kelvin, metric: Celsius, imperial: Fahrenheit. |
 |<ul><li> current.feels_like </li>| Temperature. This temperature parameter accounts for the human perception of weather. Units – default: kelvin, metric: Celsius, imperial: Fahrenheit. |
 |<ul><li> current.pressure </li> | Atmospheric pressure on the sea level, hPa |
 |<ul><li> current.humidity </li> | Humidity, % |
 |<ul><li> current.dew_point </li> | Atmospheric temperature (varying according to pressure and humidity) below which water droplets begin to condense and dew can form. Units – default: kelvin, metric: Celsius, imperial: Fahrenheit |
|<ul><li> current.clouds </li> | Cloudiness, % |
|<ul><li> current.uvi </li> | Current UV index. |
|<ul><li> current.visibility </li> | Average visibility, metres. The maximum value of the visibility is 10 km |
|<ul><li> current.wind_speed </li> | Wind speed. Wind speed. Units – default: metre/sec, metric: metre/sec, imperial: miles/hour. |
|<ul><li> current.wind_gust </li> | (Where available) Wind gust. Units – default: metre/sec, metric: metre/sec, imperial: miles/hour. |
|<ul><li> current.wind_deg </li> | Wind direction, degrees (meteorological) |
|<ul><li> **current.rain** </li> | |
 |&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; current.rain.1h | (Where available) Precipitation, mm/h. Please note that only mm/h as units of measurement are available for this parameter |
 |<ul><li> **current.snow** </li> ||
 |&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; current.snow.1h | (Where available) Precipitation, mm/h. Please note that only mm/h as units of measurement are available for this parameter |
 |<ul><li> **current.weather** </li> ||
 |&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; current.weather.id | [Weather condition id](https://openweathermap.org/weather-conditions#Weather-Condition-Codes-2) |
 | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; current.weather.main | Group of weather parameters (Rain, Snow etc.) |
 | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; current.weather.description | Weather condition within the group. Get the output in your language
 | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;current.weather.icon | Weather icon id. [How to get icons](https://openweathermap.org/weather-conditions#How-to-get-icon-URL) |
| minutely | Minute forecast weather data API response |
| <ul><li> minutely.dt </li> | Time of the forecasted data, unix, UTC |
 |<ul><li> minutely.precipitation </li> | Precipitation, mm/h. Please note that only mm/h as units of measurement are available for this parameter |
 | hourly | Hourly forecast weather data API response |
 |<ul><li> hourly.dt </li> | Time of the forecasted data, Unix, UTC |
 |<ul><li> hourly.temp </li> | Temperature. Units – default: kelvin, metric: Celsius, imperial: Fahrenheit. |
 |<ul><li>hourly.feels_like </li> | Temperature. This accounts for the human perception of weather. Units – default: kelvin, metric: Celsius, imperial: Fahrenheit. |
 |<ul><li> hourly.pressure | Atmospheric pressure on the sea level, hPa |
 |<ul><li> hourly.humidity </li> | Humidity, % |
 |<ul><li> hourly.dew_point </li> | Atmospheric temperature (varying according to pressure and humidity) below which water droplets begin to condense and dew can form. Units – default: kelvin, metric: Celsius, imperial: Fahrenheit. |
 |<ul><li> hourly.uvi </li> | UV index |
 |<ul><li> hourly.clouds </li> | Cloudiness, %
 |<ul><li> hourly.visibility </li> | Average visibility, metres. The maximum value of the visibility is 10 km |
 |<ul><li> hourly.wind_speed </li> | Wind speed. Units – default: metre/sec, metric: metre/sec, imperial: miles hour. |
 |<ul><li> hourly.wind_gust </li> | (Where available) Wind gust. Units – default: metre/sec, metric: metre/sec, imperial: miles hour. |
 |<ul><li> hourly.wind_deg </li> | Wind direction, degrees (meteorological) |
 |<ul><li> hourly.pop </li> | Probability of precipitation. The values of the parameter vary between 0 and 1, where 0 is equal to 0%, 1 is equal to 100% |
 |<ul><li>  **hourly.rain** </li> ||
 |&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; hourly.rain.1h | (Where available) Precipitation, mm/h. Please note that only mm/h as units of measurement are available for this parameter |
 |<ul><li> **hourly.snow** </li> 
 |&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  hourly.snow.1h | (Where available) Precipitation, mm/h. Please note that only mm/h as units of measurement are available for this parameter |
 |<ul><li> **hourly.weather** </li> 
 |&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; hourly.weather.id | [Weather condition id](https://openweathermap.org/weather-conditions#Weather-Condition-Codes-2)|
 |&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; hourly.weather.main | Group of weather parameters (Rain, Snow etc.) |
 | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; hourly.weather.description | Weather condition within the group. Get the output in your language |
 |&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; hourly.weather.icon | Weather icon id. [How to get icons](https://openweathermap.org/weather-conditions#How-to-get-icon-URL) |
