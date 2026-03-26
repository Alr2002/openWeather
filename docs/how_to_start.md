# How to start

## Prerequisites

To start working with the One Call API 3.0, register and log in to your account. Then select your subscription plan and receive your API key.

!!! info "Note"

    One Call API 3.0 is included in the "One Call by Call" subscription **only**. Select the type of data you want to receive from One Call API 3.0:  
         - Current and forecast weather data  
         - Weather overview

## Authentication

One Call API 3.0 uses API key authentication. You can obtain your API key in your account on the tab `API keys`.
You can generate as many keys as needed for your subscription.

## How to make an API call

### Base URL

`https://api.openweathermap.org/data/3.0`

### Endpoint - Current and forecast weather data

`/onecall`

This endpoint is used to get access to current weather, minute forecast fo 1 hour, hourly forecast for 48 hours, daily forecast for 8 days and government weather alerts.

### API call

Method - **GET**
```
https://api.openweathermap.org/data/3.0/onecall?lat={lat}&lon={lon}&exclude={part}&appid={API_key}
```

### Required parameters

|Parameter|Required/Optional|Description|
-----------|:-------:|-----------|
|[`lat`][1]   | required | Latitude (from -90 to 90). If you need the geocoder to automatic convert city names and zip-codes to geo coordinates and the other way around, please use our [Geocoding API](https://openweathermap.org/api/geocoding-api) | 
|[`lon`][1] |required|Longitude (from -180 to 180). If you need the geocoder to automatic convert city names and zip-codes to geo coordinates and the other way around, please use our [Geocoding API](https://openweathermap.org/api/geocoding-api)
| [`appid`][1]|required|Your unique API key (you can always find it on your account page under the ["API key" tab](https://home/openweathermap.org/api_keys))
| [`exclude`][1] |optional|By using this parameter you can exclude some parts of the weather data from the API response. It should be a comma-delimited list (without spaces). Available values: `current` `minutely` `hourly` `daily` `alerts`
|[`units`][1] |optional|Units of measurement `standard`,`metric` and `imperial` units are available. If you do not use the `units` parameter, `standard` units will be applied by default. [Learn more](https://openweathermap.org/api/one-call-3?collection=one_call_api_3.0#data) |
| [`lang`][1] |optional|You can use the `lang` parameter to get the output in your language. [Learn more](https://openweathermap.org/api/one-call-3?collection=one_call_api_3.0#multi) |


[1]: https://     "string"


