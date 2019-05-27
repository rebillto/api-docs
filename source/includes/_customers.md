#Customers

A customer is each paying individual, this object is created on each successful checkout automatically.

##Get All Customers

```shell
curl --request GET \
  --url 'https://api.surcoseguros.com.ar/v1/customers/all' \
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
    "customers",
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

url = URI("https://api.surcoseguros.com.ar/v1/customers/all")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/customers/all"

headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/customers/all",
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

	url := "https://api.surcoseguros.com.ar/v1/customers/all"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

This endpoint retrieves all your customers.

### HTTP Request

`GET https://api.surcoseguros.com.ar/v1/customers/all`

Headers | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM

## Get Customer by Email

```shell
curl --request GET \
  --url 'https://api.surcoseguros.com.ar/v1/customers/you@domain.com' \
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
    "customers",
    "you@domain.com"
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

url = URI("https://api.surcoseguros.com.ar/v1/customers/you@domain.com")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/customers/you@domain.com"

headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/customers/you@domain.com",
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

	url := "https://api.surcoseguros.com.ar/v1/customers/you@domain.com"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

This endpoint retrieves a specific Customer's Data using its email as Primary Key.

### HTTP Request

`GET https://api.surcoseguros.com.ar/v1/customers/:email`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc

### URL Parameters

Parameter | Description
--------- | -----------
:email | you@domain.com

## New Customer

```shell
curl --request POST \
  --url 'https://api.surcoseguros.com.ar/v1/customers/new' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc' \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --data 'firstName=Nahuel&lastName=Sample_client_lastName&email=nahuel%40nahuel.xyz&password=your-passw0rd&role=2&enabled=1&company_name=sample_Some%20Company&address_street=sample_address_street3&address_number=00000&address_floor=1&address_apt=A&address_city=Buenos%20Aires&address_province=Buenos%20Aires&zipcode=0000'
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
    "customers",
    "new"
  ],
  "headers": {
    "Content-Type": "application/x-www-form-urlencoded",
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

req.write(qs.stringify({ firstName: 'Nahuel',
  lastName: 'Sample_client_lastName',
  email: 'you@domain.com',
  password: 'your-passw0rd',
  role: '2',
  enabled: '1',
  company_name: 'sample_Some Company',
  address_street: 'sample_address_street3',
  address_number: '00000',
  address_floor: '1',
  address_apt: 'A',
  address_city: 'Buenos Aires',
  address_province: 'Buenos Aires',
  zipcode: '0000' }));
req.end();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://api.surcoseguros.com.ar/v1/customers/new")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["Content-Type"] = 'application/x-www-form-urlencoded'
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc'
request.body = "firstName=Nahuel&lastName=Sample_client_lastName&email=nahuel%40nahuel.xyz&password=your-passw0rd&role=2&enabled=1&company_name=sample_Some%20Company&address_street=sample_address_street3&address_number=00000&address_floor=1&address_apt=A&address_city=Buenos%20Aires&address_province=Buenos%20Aires&zipcode=0000"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/customers/new"

payload = "firstName=Nahuel&lastName=Sample_client_lastName&email=nahuel%40nahuel.xyz&password=your-passw0rd&role=2&enabled=1&company_name=sample_Some%20Company&address_street=sample_address_street3&address_number=00000&address_floor=1&address_apt=A&address_city=Buenos%20Aires&address_province=Buenos%20Aires&zipcode=0000"
headers = {
    'Content-Type': "application/x-www-form-urlencoded",
    'Authorization': "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/customers/new",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "firstName=Nahuel&lastName=Sample_client_lastName&email=nahuel%40nahuel.xyz&password=your-passw0rd&role=2&enabled=1&company_name=sample_Some%20Company&address_street=sample_address_street3&address_number=00000&address_floor=1&address_apt=A&address_city=Buenos%20Aires&address_province=Buenos%20Aires&zipcode=0000",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc",
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

	url := "https://api.surcoseguros.com.ar/v1/customers/new"

	payload := strings.NewReader("firstName=Nahuel&lastName=Sample_client_lastName&email=nahuel%40nahuel.xyz&password=your-passw0rd&role=2&enabled=1&company_name=sample_Some%20Company&address_street=sample_address_street3&address_number=00000&address_floor=1&address_apt=A&address_city=Buenos%20Aires&address_province=Buenos%20Aires&zipcode=0000")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("Content-Type", "application/x-www-form-urlencoded")
	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

This endpoint creates or updates a customer using its `email` as Primary Key.

### HTTP Request

`POST https://api.surcoseguros.com.ar/v1/customers/new/`

Header | Content
--------- | -----------
Content-Type | application/x-www-form-urlencoded
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc


### BODY Parameters

Parameter | Description
--------- | -----------
firstName | Nahuel
lastName | Sample_client_lastName
email | you@domain.com
password | your-passw0rd
enabled | 1
company_name | sample_Some Company
address_street | sample_address_street3
address_number | 00000
address_floor | 1
address_apt | A
address_city | Buenos Aires
address_province | Buenos Aires
zipcode | 0000

## Update a Customer

```shell
curl --request POST \
  --url 'https://api.surcoseguros.com.ar/v1/customers/update' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MTYsInBhc3N3b3JkIjoiJDJhJDEwJFMwQlJOU3FnQVE1Qzg1cGtXLklaUGVWUHlveXVlMWwzUHpKODI1Y3BkZFYzLjlsa09Odmo2In0.qUMvsLxxt3reYBcvpTJkWWyenBXOGSUXO1AG3MxBttI' \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --data 'id=24&firstName=Test&lastName=changed1&email=sample_email3%40domain.com&password=your-passw0rd&role=1&enabled=1&company_name=Changed&address_street=Changed&address_number=00001Changed&address_floor=1Changed&address_apt=AChanged&address_city=Buenos%20AiresChanged&address_province=Buenos%20AiresChanged&zipcode=0000Changed'
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
    "customers",
    "update"
  ],
  "headers": {
    "Content-Type": "application/x-www-form-urlencoded",
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

req.write(qs.stringify({ firstName: 'Nahuel',
  lastName: 'Sample_client_lastName',
  email: 'you@domain.com',
  password: 'your-passw0rd',
  role: '2',
  enabled: '1',
  company_name: 'sample_Some Company',
  address_street: 'sample_address_street3',
  address_number: '00000',
  address_floor: '1',
  address_apt: 'A',
  address_city: 'Buenos Aires',
  address_province: 'Buenos Aires',
  zipcode: '0000' }));
req.end();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://api.surcoseguros.com.ar/v1/customers/update")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MTYsInBhc3N3b3JkIjoiJDJhJDEwJFMwQlJOU3FnQVE1Qzg1cGtXLklaUGVWUHlveXVlMWwzUHpKODI1Y3BkZFYzLjlsa09Odmo2In0.qUMvsLxxt3reYBcvpTJkWWyenBXOGSUXO1AG3MxBttI'
request["Content-Type"] = 'application/x-www-form-urlencoded'
request.body = "id=24&firstName=Test&lastName=changed1&email=sample_email3%40domain.com&password=your-passw0rd&role=1&enabled=1&company_name=Changed&address_street=Changed&address_number=00001Changed&address_floor=1Changed&address_apt=AChanged&address_city=Buenos%20AiresChanged&address_province=Buenos%20AiresChanged&zipcode=0000Changed"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/customers/update"

payload = "id=24&firstName=Test&lastName=changed1&email=sample_email3%40domain.com&password=your-passw0rd&role=1&enabled=1&company_name=Changed&address_street=Changed&address_number=00001Changed&address_floor=1Changed&address_apt=AChanged&address_city=Buenos%20AiresChanged&address_province=Buenos%20AiresChanged&zipcode=0000Changed"
headers = {
    'Authorization': "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MTYsInBhc3N3b3JkIjoiJDJhJDEwJFMwQlJOU3FnQVE1Qzg1cGtXLklaUGVWUHlveXVlMWwzUHpKODI1Y3BkZFYzLjlsa09Odmo2In0.qUMvsLxxt3reYBcvpTJkWWyenBXOGSUXO1AG3MxBttI",
    'Content-Type': "application/x-www-form-urlencoded"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/customers/update",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "id=24&firstName=Test&lastName=changed1&email=sample_email3%40domain.com&password=your-passw0rd&role=1&enabled=1&company_name=Changed&address_street=Changed&address_number=00001Changed&address_floor=1Changed&address_apt=AChanged&address_city=Buenos%20AiresChanged&address_province=Buenos%20AiresChanged&zipcode=0000Changed",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MTYsInBhc3N3b3JkIjoiJDJhJDEwJFMwQlJOU3FnQVE1Qzg1cGtXLklaUGVWUHlveXVlMWwzUHpKODI1Y3BkZFYzLjlsa09Odmo2In0.qUMvsLxxt3reYBcvpTJkWWyenBXOGSUXO1AG3MxBttI",
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

	url := "https://api.surcoseguros.com.ar/v1/customers/update"

	payload := strings.NewReader("id=24&firstName=Test&lastName=changed1&email=sample_email3%40domain.com&password=your-passw0rd&role=1&enabled=1&company_name=Changed&address_street=Changed&address_number=00001Changed&address_floor=1Changed&address_apt=AChanged&address_city=Buenos%20AiresChanged&address_province=Buenos%20AiresChanged&zipcode=0000Changed")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MTYsInBhc3N3b3JkIjoiJDJhJDEwJFMwQlJOU3FnQVE1Qzg1cGtXLklaUGVWUHlveXVlMWwzUHpKODI1Y3BkZFYzLjlsa09Odmo2In0.qUMvsLxxt3reYBcvpTJkWWyenBXOGSUXO1AG3MxBttI")
	req.Header.Add("Content-Type", "application/x-www-form-urlencoded")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

This endpoint creates or updates a customer using its `email` as Primary Key.

### HTTP Request

`POST https://api.surcoseguros.com.ar/v1/customers/update/`

Header | Content
--------- | -----------
Content-Type | application/x-www-form-urlencoded
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc


### BODY Parameters

Parameter | Description
--------- | -----------
firstName | Nahuel
lastName | Sample_client_lastName
email | you@domain.com
password | your-passw0rd
enabled | 1
company_name | sample_Some Company
address_street | sample_address_street3
address_number | 00000
address_floor | 1
address_apt | A
address_city | Buenos Aires
address_province | Buenos Aires
zipcode | 0000

##Delete a Customer

```shell
curl --request DELETE \
  --url 'https://api.surcoseguros.com.ar/v1/customers/delete/you@domain.com' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM' \
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
    "customers",
    "delete",
    "you@domain.com"
  ],
  "headers": {
    "Content-Type": "application/json",
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

url = URI("https://api.surcoseguros.com.ar/v1/customers/delete/you@domain.com")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Delete.new(url)
request["Content-Type"] = 'application/json'
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/customers/delete/you@domain.com"

headers = {
    'Content-Type': "application/json",
    'Authorization': "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM"
    }

response = requests.request("DELETE", url, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/customers/delete/you@domain.com",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "DELETE",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM",
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

	url := "https://api.surcoseguros.com.ar/v1/customers/delete/you@domain.com"

	req, _ := http.NewRequest("DELETE", url, nil)

	req.Header.Add("Content-Type", "application/json")
	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

This endpoint deletes a Customer, using its email as Primary Key. Only administrators can delete a customer.

### HTTP Request

`DELETE https://api.surcoseguros.com.ar/v1/customers/delete/:email`

Header | Content
--------- | -----------
Content-Type | application/json
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM

### URL Parameters

Parameter | Description
--------- | -----------
:email | Email of the customer to delete.
