# Example of API request

## Example of API request current and forecast weather data

Method - **GET**

```
https://api.openweathermap.org/data/3.0/onecall?lat=46.47747&lon=30.73262&exclude=hourly,daily,minutely&units=metric&appid={API_key}
```

If you do not need to exclude any of the weather data from the API response please use API call like in the example below:

```
https://api.openweathermap.org/data/3.0/onecall?lat=46.47747&lon=30.73262&units=metric&appid={API_key}
```

## Test parameters for the query

|Parameter|Value|Description|
-----------|:-------:|-----------|
`lat`        |46.4775|Latitude
`lon`|30.7326|Longitude
`appid`|API_key| Your API key
`exclude`|hourly,daily,minutely| Exclude hourly, daily, minutely  parts of the weather data from the API response. 
`units`|metric|Units of measurement are metric
 


!!! example "Examples of API requests for various languages"
    === "Curl"

        ```
        curl --location 'https://api.openweathermap.org/data/3.0/onecall?lat=46.47747&lon=30.73262&exclude=hourly%2Cdaily%2Cminutely&appid={API_key}&units=metric'
        ```

    === "Python"

        ```py
        import requests
        url = "https://api.openweathermap.org/data/3.0/onecall?lat=46.47747&lon=30.73262&exclude=hourly,daily,minutely&appid={API_key}a&units=metric"
        payload = {}
        headers = {}
        response = requests.request("GET", url, headers=headers, data=payload)
        print(response.text)
        ```

    === "Java"


        ```java
        OkHttpClient client = new OkHttpClient().newBuilder()
        .build();
        MediaType mediaType = MediaType.parse("text/plain");
        RequestBody body = RequestBody.create(mediaType, "");
        Request request = new Request.Builder()
        .url("https://api.openweathermap.org/data/3.0/onecall?lat=46.47747&lon=30.73262&exclude=hourly,daily,minutely&appid={API_key}&units=metric")
        .method("GET", body)
        .build();
        Response response = client.newCall(request).execute();
        ```

    === "Ruby"

        ```ruby
        require "uri"
        require "net/http"
        url = URI("https://api.openweathermap.org/data/3.0/onecall?lat=46.47747&lon=30.73262&exclude=hourly,daily,minutely&appid={API_key}&units=metric")
        https = Net::HTTP.new(url.host, url.port)   
        https.use_ssl = true
        request = Net::HTTP::Get.new(url)
        response = https.request(request)
        puts response.read_body
        ```
    === "Java Script"

        ```javascript
        var settings = {
        "url": "https://api.openweathermap.org/data/3.0/onecall?lat=46.47747&lon=30.73262&exclude=hourly,daily,minutely&appid={API_key}&units=metric",
        "method": "GET",
        "timeout": 0,
        };
        $.ajax(settings).done(function (response) {
        console.log(response);
        });
        ```


