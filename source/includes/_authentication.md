#Authentication

```shell
CURL Request Example

curl --location --request GET "https://api.rebill.to/v1/getToken" \
--header "Content-Type: application/x-www-form-urlencoded"
```

```javascript
Node.JS Request Example

var request = require('request');
var options = {
  'method': 'GET',
  'url': 'https://api.rebill.to/v1/getToken',
  'headers': {
    'Content-Type': 'application/x-www-form-urlencoded'
  }
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```ruby
Ruby Request Example

require "uri"
require "net/http"

url = URI("https://api.rebill.to/v1/getToken")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Content-Type"] = "application/x-www-form-urlencoded"

response = https.request(request)
puts response.read_body
```

```python
Python Request Example


import requests

url = "https://api.rebill.to/v1/getToken"

payload = {}
headers = {
  'Content-Type': 'application/x-www-form-urlencoded'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))
```

```php
PHP Request Example

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.rebill.to/v1/getToken",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Content-Type: application/x-www-form-urlencoded"
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

```

```go
GO Request Example

package main

import (
  "fmt"
  "os"
  "path/filepath"
  "io"
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api.rebill.to/v1/getToken"
  method := "GET"

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, nil)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Content-Type", "application/x-www-form-urlencoded")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

  fmt.Println(string(body))
}
```

```json
JSON Response Example

{
    "success": true,
    "response": {
        "token": "eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJG1FZHNyMUFNaUJXdFlQVlVUdkxaa3VFNFNwbTRwRlIyMnE1R1dYRHRuL01Ba2dEUG9ibjIu.tbxALN3ni1Db0OMX3kBkj09WUnPJxRl8T4JxLTQXgnI",
        "created": "2019-12-16T02:21:58Z",
        "expires": "2019-12-16T14:21:58Z",
        "currentTime": "2019-12-16T10:38:35Z",
        "remains": "03:43:23",
        "status": "active"
    }
}
```


The authentication process is through a token Bearer. In order to obtain a token, you shall use your username (email) and password.
Note that the `username` and `password` shall be sent using `Basic Authentication`. This means that both components shall be sent in base64 format.
The token has a validity of 12 hours before expiration.

#### Headers

`GET https://api.rebill.to/v1/getToken`

Header | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`
Authorization | `Basic base64_hash` | Yes | Your username and password in base64.

#### Response

Attribute | Content | Always Present | Description
--------- | ----------- | ----------- | -----------
`success` | boolean | Yes | Returns `true` if the performed action was success, otherwise `false`.
`response` | object | Yes | Contains an object with the result of the performed action if success. If an error ocurred, the response object will not exist. Check the error response format.
