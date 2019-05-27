#Plans

## Get All Plans

```shell
curl --request GET \
  --url 'https://api.surcoseguros.com.ar/v1/plans/all' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'
```

```javascript
var http = require("http");

var options = {
  "method": "GET",
  "hostname": [
    "https://api.surcoseguros.com.ar"
  ],
  "path": [
    "v1",
    "plans",
    "all"
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

url = URI("https://api.surcoseguros.com.ar/v1/plans/all")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/plans/all"

headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/plans/all",
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

	url := "https://api.surcoseguros.com.ar/v1/plans/all"

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

`GET https://api.surcoseguros.com.ar/v1/plans/all`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM
Content-type | application/json

## Get a Specific Plan

```shell
curl --request GET \
  --url 'https://api.surcoseguros.com.ar/v1/plans/mpPlanID/43' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'
```

```javascript
var http = require("http");

var options = {
  "method": "GET",
  "hostname": [
    "https://api.surcoseguros.com.ar"
  ],
  "path": [
    "v1",
    "plans",
    "mpPlanID",
    "43"
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

url = URI("https://api.surcoseguros.com.ar/v1/plans/mpPlanID/43")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/plans/mpPlanID/43"

headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/plans/mpPlanID/43",
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

	url := "https://api.surcoseguros.com.ar/v1/plans/mpPlanID/43"

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

`GET https://api.surcoseguros.com.ar/v1/plans/:type/:id`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM
Content-type | application/json

### URL Parameters

Parameter | Description
--------- | -----------
:type | Retrieve the Plan by `planID` or `mpPlanID`.
:id | ID of the Plan to Retrieve.
