# Common Errors Status Code

Our API libraries raise exceptions for many reasons, such as a failed charge, invalid parameters, authentication errors, and network unavailability. We recommend writing code that gracefully handles all possible API exceptions.

### JSON Error Response

Attribute | Content | Always Present | Description
--------- | ----------- | ----------- | -----------
`success` | boolean | Yes | Returns `false` as the action performed was not completed successfully.
`response` | object | Yes | Contains an object with the result of the performed action if success. If an error ocurred, the response object will not exist. Check the error response format.

### Error Status Codes

Error Code | Meaning
---------- | -------
400 | Bad Request
401 | Unauthorized -- Your API key is wrong.
403 | Forbidden -- The request is forbidden for your access level, contact the developer support.
404 | Not Found -- The request is not longer active, or does not exist.
405 | Method Not Allowed -- You tried to access a request with an invalid method.
406 | Not Acceptable -- You requested a format that isn't JSON.
410 | Gone -- The endpoint requested has been removed from our servers.
429 | Too Many Requests -- You're requesting too much information.
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.

### Error Codes

Code | Description
--------- | -----------
1001 | Invalid password.
