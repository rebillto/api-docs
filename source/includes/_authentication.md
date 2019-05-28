# Authentication

> To authorize, use this code:

```shell
curl --request GET \
  --url 'https://api.rebill.to/v1/getToken' \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --header 'email: you@domain.com' \
  --header 'password: your-passw0rd'
```

```javascript
var http = require("http");

var options = {
  "method": "GET",
  "hostname": [
    "https://api.rebill.to"
  ],
  "path": [
    "v1",
    "getToken"
  ],
  "headers": {
    "Content-Type": "application/x-www-form-urlencoded",
    "email": "you@domain.com",
    "password": "your-passw0rd"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://api.rebill.to/v1/getToken")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["Content-Type"] = 'application/x-www-form-urlencoded'
request["email"] = 'you@domain.com'
request["password"] = 'your-passw0rd'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.rebill.to/v1/getToken"

headers = {
    'Content-Type': "application/x-www-form-urlencoded",
    'email': "you@domain.com",
    'password': "your-passw0rd"
    }

response = requests.request("GET", url, headers=headers)

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
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Content-Type: application/x-www-form-urlencoded",
    "email: you@domain.com",
    "password: your-passw0rd"
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.rebill.to/v1/getToken"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("Content-Type", "application/x-www-form-urlencoded")
	req.Header.Add("email", "you@domain.com")
	req.Header.Add("password", "your-passw0rd")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

First ask for an access token, using your login credentials. A TOKEN will be returned and shall be included in the HEADER of all your request as `Authorization`.

HTTP Request:

`GET https://api.rebill.to/v1/getToken`

Headers | Content
--------- | -----------
Content-Type | application/x-www-form-urlencoded
username | youremail@domain.com
password | your-password
