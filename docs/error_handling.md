# Error handling

## Structure of API errors

In case of incorrect API call you will receive API error response. Error response payload returned for all types of errors with the structure below.

!!! warning "Example of error response"

    ```
    {
        "code": "400",
        "message": "Invalid date format",
        "parameters": [
            "date"
        ]
    }
    ```

## Fields in error response

|Parameter|Description|
|:-----------|:-----------|
| `code` | Code of error |
| `message` | Description of error |
| `parameters` | (optional) List of request parameters names that are related to this particular error |

## HTTP status code summary

Please find more detailed information about some popular errors below.

| Code of error | Status | Description |
|:-----------:|:---:|:--------|
| 200 | OK | Everything worked as expected |
| 400 | Bad Request | You can get error 400 error if either some mandatory parameters in the request are missing or some of request parameters have incorrect format or values out of allowed range. List of all parameters names that are missing or incorrect will be returned in `parameters`attribute of the `ErrorResponse` object.|
| 401 | Unauthorized | You can get 401 error if API token did not provide in the request or in case API token provided in the request does not grant access to this API. You must add API token with granted access to the product to the request before returning it.|
| 402 | Request Failed | The parameters were valid but the request failed. |
| 403 | Forbidden | The API key doesn't have permission to perform the request. |  
| 404 | Not Found | You can get 404 error if data with requested parameters (`lat`, `lon` and `date`) does not exist in service database. You must not retry the same request. |
| 409 | Conflict | The request conflicts  with another request (perhaps due to using the same idempotent key). |
| 424 | External Dependency Failed | The request couldn't be completed due to a failure in a dependency  external to OpenWeathermap. |
| 429 | Too Many Requests | You can get 429 error if key quota of requests for provided API to this API was exceeded. You may retry request after some time or after extending your key quota. |
| 5xx | Unexpected Error | You can get '5xx' error in case of other internal errors. Error Response code will be `5xx`. Please contact us and enclose an example of your API request that receives this error into your email to let us analyze it and find a solution for you promptly. You may retry the request which led to this error. |