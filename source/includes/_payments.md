#Payments

## Get All Payments


```shell
curl --request GET \
  --url 'https://api.surcoseguros.com.ar/v1/payments/all' \
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
    "payments",
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

url = URI("https://api.surcoseguros.com.ar/v1/payments/all")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/payments/all"

headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/payments/all",
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

	url := "https://api.surcoseguros.com.ar/v1/payments/all"

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

`GET https://api.surcoseguros.com.ar/v1/payments/all`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Customer to retrieve

## Get a Specific Payment


```shell
curl --request GET \
  --url 'https://api.surcoseguros.com.ar/v1/payments/subscriptionID/34' \
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
    "payments",
    "subscriptionID",
    "34"
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

url = URI("https://api.surcoseguros.com.ar/v1/payments/subscriptionID/34")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/payments/subscriptionID/34"

headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/payments/subscriptionID/34",
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

	url := "https://api.surcoseguros.com.ar/v1/payments/subscriptionID/34"

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

`GET https://api.surcoseguros.com.ar/v1/payments/:type/:id`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM

### URL Parameters

Parameter | Description
--------- | -----------
:type | Find by `paymentID` or `subscriptionID`.
:id | ID of the payment to retrieve.

## New Payment


```shell
curl --request POST \
  --url 'https://api.surcoseguros.com.ar/v1/payments/new' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM' \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --data 'planID=4312&subscriptionID=34&creation=01%2F03%2F2018&debit_date=03%2F01%2F2020&amount=20&setup_fee=30&currencyID=ARS'
```

```javascript
var qs = require("querystring");
var http = require("http");

var options = {
  "method": "POST",
  "hostname": [
    "https://api.surcoseguros.com.ar"
  ],
  "path": [
    "v1",
    "payments",
    "new"
  ],
  "headers": {
    "Content-Type": "application/x-www-form-urlencoded",
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

req.write(qs.stringify({ planID: '4312',
  subscriptionID: '34',
  creation: '01/03/2018',
  debit_date: '03/01/2020',
  amount: '20',
  setup_fee: '30',
  currencyID: 'ARS' }));
req.end();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://api.surcoseguros.com.ar/v1/payments/new")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["Content-Type"] = 'application/x-www-form-urlencoded'
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'
request.body = "planID=4312&subscriptionID=34&creation=01%2F03%2F2018&debit_date=03%2F01%2F2020&amount=20&setup_fee=30&currencyID=ARS"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/payments/new"

payload = "planID=4312&subscriptionID=34&creation=01%2F03%2F2018&debit_date=03%2F01%2F2020&amount=20&setup_fee=30&currencyID=ARS"
headers = {
    'Content-Type': "application/x-www-form-urlencoded",
    'Authorization': "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/payments/new",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "planID=4312&subscriptionID=34&creation=01%2F03%2F2018&debit_date=03%2F01%2F2020&amount=20&setup_fee=30&currencyID=ARS",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM",
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
}
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.surcoseguros.com.ar/v1/payments/new"

	payload := strings.NewReader("planID=4312&subscriptionID=34&creation=01%2F03%2F2018&debit_date=03%2F01%2F2020&amount=20&setup_fee=30&currencyID=ARS")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("Content-Type", "application/x-www-form-urlencoded")
	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

### HTTP Request

`POST https://api.surcoseguros.com.ar/v1/payments/new`

Header | Content
--------- | -----------
Content-Type | application/x-www-form-urlencoded
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM

### URL Parameters
Header | Content
--------- | -----------
planID | Plan ID related to this payment.
subscriptionID | Subscription ID related to this payment.
creation | Creation TIMESTAMP of this payment.
debit_date | First debit date (TIMESTAMP) of this payment.
amount | Amount charged.
currencyID | `ARS` corresponding to Argentine Pesos.
setup_fee | 30

## Update Payment


```shell
curl --request POST \
  --url 'https://api.surcoseguros.com.ar/v1/payments/update' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM' \
  --data 'id=4&planID=431123123&subscriptionID=34123123&creation=01%2F03%2F2018&debit_date=03%2F01%2F2020&amount=20&setup_fee=300&currencyID=ARS'
```

```javascript
var qs = require("querystring");
var http = require("http");

var options = {
  "method": "POST",
  "hostname": [
    "https://api.surcoseguros.com.ar"
  ],
  "path": [
    "v1",
    "payments",
    "update"
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

req.write(qs.stringify({ id: '4',
  planID: '431123123',
  subscriptionID: '34123123',
  creation: '01/03/2018',
  debit_date: '03/01/2020',
  amount: '20',
  setup_fee: '300',
  currencyID: 'ARS' }));
req.end();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://api.surcoseguros.com.ar/v1/payments/update")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'
request.body = "id=4&planID=431123123&subscriptionID=34123123&creation=01%2F03%2F2018&debit_date=03%2F01%2F2020&amount=20&setup_fee=300&currencyID=ARS"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/payments/update"

payload = "id=4&planID=431123123&subscriptionID=34123123&creation=01%2F03%2F2018&debit_date=03%2F01%2F2020&amount=20&setup_fee=300&currencyID=ARS"
headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'}

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/payments/update",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "id=4&planID=431123123&subscriptionID=34123123&creation=01%2F03%2F2018&debit_date=03%2F01%2F2020&amount=20&setup_fee=300&currencyID=ARS",
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
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.surcoseguros.com.ar/v1/payments/update"

	payload := strings.NewReader("id=4&planID=431123123&subscriptionID=34123123&creation=01%2F03%2F2018&debit_date=03%2F01%2F2020&amount=20&setup_fee=300&currencyID=ARS")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

### HTTP Request

`POST https://api.surcoseguros.com.ar/v1/payments/update`

Header | Content
--------- | -----------
Content-Type | application/x-www-form-urlencoded
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM

### BODY Parameters
Header | Content
--------- | -----------
planID | Plan ID related to this payment.
subscriptionID | Subscription ID related to this payment.
creation | Creation TIMESTAMP of this payment.
debit_date | First debit date (TIMESTAMP) of this payment.
amount | Amount charged.
currencyID | `ARS` corresponding to Argentine Pesos.
setup_fee | 30

## Delete Payment


```shell
curl --request DELETE \
  --url 'https://api.surcoseguros.com.ar/v1/payments/delete/subscriptionID/34' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc' \
  --header 'Content-Type: application/json'
```

```javascript
var http = require("http");

var options = {
  "method": "DELETE",
  "hostname": [
    "https://api.surcoseguros.com.ar"
  ],
  "path": [
    "v1",
    "payments",
    "delete",
    "subscriptionID",
    "34"
  ],
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc"
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

url = URI("https://api.surcoseguros.com.ar/v1/payments/delete/subscriptionID/34")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Delete.new(url)
request["Content-Type"] = 'application/json'
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/payments/delete/subscriptionID/34"

headers = {
    'Content-Type': "application/json",
    'Authorization': "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc"
    }

response = requests.request("DELETE", url, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/payments/delete/subscriptionID/34",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "DELETE",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc",
    "Content-Type: application/json"
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

	url := "https://api.surcoseguros.com.ar/v1/payments/delete/subscriptionID/34"

	req, _ := http.NewRequest("DELETE", url, nil)

	req.Header.Add("Content-Type", "application/json")
	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

### HTTP Request

`DELETE https://api.surcoseguros.com.ar/v1/payments/delete/:type/:id`

Header | Content
--------- | -----------
Content-Type | application/json
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM

### BODY Parameters
Header | Content
--------- | -----------
:type | Find by `paymentID` or `subscriptionID`.
:id | ID of the payment to retrieve.
