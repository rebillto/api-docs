#Authentication

```shell
curl --location --request GET "https://api.rebill.to/v1/getToken" \
  --header "Content-Type: application/x-www-form-urlencoded"
```

```javascript
var https = require('https');

var options = {
  'method': 'GET',
  'hostname': 'https://api.rebill.to',
  'path': '/v1/getToken',
  'headers': {
    'Content-Type': 'application/x-www-form-urlencoded'
  }
};

var req = https.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function (chunk) {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });

  res.on("error", function (error) {
    console.error(error);
  });
});

req.end();
```

```ruby
require "uri"
require "net/http"

url = URI("https://api.rebill.to/v1/getToken")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["Content-Type"] = "application/x-www-form-urlencoded"

response = http.request(request)
puts response.read_body
```

```python
import requests
url = 'https://api.rebill.to/v1/getToken'
payload = {}
headers = {
  'Content-Type': 'application/x-www-form-urlencoded'
}
response = requests.request('GET', url, headers = headers, data = payload, allow_redirects=False, timeout=undefined, allow_redirects=false)
print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.rebill.to/v1/getToken",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => false,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Content-Type: application/x-www-form-urlencoded"
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
} ?>
```

```go
package main

import (
  "fmt"
  "os"
  "path/filepath"
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api.rebill.to/v1/getToken"
  method := "GET"

  client := &http.Client {
    CheckRedirect: func(req *http.Request, via []*http.Request) error {
      return http.ErrUseLastResponse
    },
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

Note that the `username` and `password` shall be sent using `Basic Authentication`. This means that both components shall be sent in base64 format.
Your e-mail is your username.

### HTTP Request

`GET https://api.rebill.to/v1/getToken`

### Headers

Header | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`
Authorization | `Basic base64_hash` | Yes | Your username and password in base64.
