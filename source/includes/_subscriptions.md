#Subscriptions

## Get All Subscriptions

```shell
curl --request GET \
  --url 'https://api.rebill.to/v1/subscriptions/all' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc'
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
    "subscriptions",
    "subscriptionid",
    "3"
  ],
  "headers": {
    "Authorization": "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM"
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

url = URI("https://api.rebill.to/v1/subscriptions/all")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.rebill.to/v1/subscriptions/all"

headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.rebill.to/v1/subscriptions/all",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc"
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

	url := "https://api.rebill.to/v1/subscriptions/all"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

### HTTP Request

`GET https://api.rebill.to/v1/subscriptions/all`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc
Content-type | application/json


## Get a specific Subscription

```shell
curl --request GET \
  --url 'https://api.rebill.to/v1/subscriptions/subscriptionid/3' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'
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
    "subscriptions",
    "subscriptionid",
    "3"
  ],
  "headers": {
    "Authorization": "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM"
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

url = URI("https://api.rebill.to/v1/subscriptions/subscriptionid/3")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.rebill.to/v1/subscriptions/subscriptionid/3"

headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.rebill.to/v1/subscriptions/subscriptionid/3",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM"
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

	url := "https://api.rebill.to/v1/subscriptions/subscriptionid/3"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

### HTTP Request

`GET https://api.rebill.to/v1/subscriptions/:type/;id`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc
Content-type | application/json

### URL Parameters

Parameter | Description
--------- | -----------
:type | Use `preapprovalid` (referencing to the mercadopago preapprovalid) or `subscriptionID`.
ID | The ID of the subscription to retrieve.

<div class="divider"></div>