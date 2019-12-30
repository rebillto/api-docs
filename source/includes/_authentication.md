#Authentication

Microservice for authentication into the Rebill Platform.

##Get Token

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

##Recover Password

```shell
CURL Request Example

curl --location --request POST 'https://api.rebill.to/v1/users/password/recover' \
--header 'Content-Type: application/json' \
--data-raw '{
  "email": "nahuel@rebill.to"
}'
```

```javascript
Node.JS Request Example

var request = require("request");

var options = { method: 'POST',
  url: 'https://api.rebill.to/v1/users/password/recover',
  headers: 
   { 'cache-control': 'no-cache',
     Connection: 'keep-alive',
     'Content-Length': '33',
     'Accept-Encoding': 'gzip, deflate',
     Host: 'api.rebill.to',
     'Postman-Token': '6491d1e0-430d-4648-b91b-f78a0ce0ac3c,921deabc-aa3d-4f0e-9624-a50c521bb861',
     'Cache-Control': 'no-cache',
     Accept: '*/*',
     'User-Agent': 'PostmanRuntime/7.20.1',
     'Content-Type': 'application/json' },
  body: { email: 'nahuel@rebill.to' },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});

```

```ruby
Ruby Request Example

require 'uri'
require 'net/http'

url = URI("https://api.rebill.to/v1/users/password/recover")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["Content-Type"] = 'application/json'
request["User-Agent"] = 'PostmanRuntime/7.20.1'
request["Accept"] = '*/*'
request["Cache-Control"] = 'no-cache'
request["Postman-Token"] = '6491d1e0-430d-4648-b91b-f78a0ce0ac3c,345074b5-4e59-4d06-a180-ba3d5c8f6c5f'
request["Host"] = 'api.rebill.to'
request["Accept-Encoding"] = 'gzip, deflate'
request["Content-Length"] = '33'
request["Connection"] = 'keep-alive'
request["cache-control"] = 'no-cache'
request.body = "{\n  \"email\": \"nahuel@rebill.to\"\n}"

response = http.request(request)
puts response.read_body
```

```python
Python Request Example


import requests

url = "https://api.rebill.to/v1/users/password/recover"

payload = "{\n  \"email\": \"nahuel@rebill.to\"\n}"
headers = {
    'Content-Type': "application/json",
    'User-Agent': "PostmanRuntime/7.20.1",
    'Accept': "*/*",
    'Cache-Control': "no-cache",
    'Postman-Token': "6491d1e0-430d-4648-b91b-f78a0ce0ac3c,ff99166d-4c3f-4b1b-936b-942d54270692",
    'Host': "api.rebill.to",
    'Accept-Encoding': "gzip, deflate",
    'Content-Length': "33",
    'Connection': "keep-alive",
    'cache-control': "no-cache"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```php
PHP Request Example

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.rebill.to/v1/users/password/recover",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\n  \"email\": \"nahuel@rebill.to\"\n}",
  CURLOPT_HTTPHEADER => array(
    "Accept: */*",
    "Accept-Encoding: gzip, deflate",
    "Cache-Control: no-cache",
    "Connection: keep-alive",
    "Content-Length: 33",
    "Content-Type: application/json",
    "Host: api.rebill.to",
    "Postman-Token: 6491d1e0-430d-4648-b91b-f78a0ce0ac3c,4f9b3613-2cba-4366-af40-542a54fedc72",
    "User-Agent: PostmanRuntime/7.20.1",
    "cache-control: no-cache"
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
GO Request Example

package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.rebill.to/v1/users/password/recover"

	payload := strings.NewReader("{\n  \"email\": \"nahuel@rebill.to\"\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("Content-Type", "application/json")
	req.Header.Add("User-Agent", "PostmanRuntime/7.20.1")
	req.Header.Add("Accept", "*/*")
	req.Header.Add("Cache-Control", "no-cache")
	req.Header.Add("Postman-Token", "6491d1e0-430d-4648-b91b-f78a0ce0ac3c,8dac3199-219d-469e-a0f6-c7b15c750974")
	req.Header.Add("Host", "api.rebill.to")
	req.Header.Add("Accept-Encoding", "gzip, deflate")
	req.Header.Add("Content-Length", "33")
	req.Header.Add("Connection", "keep-alive")
	req.Header.Add("cache-control", "no-cache")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```json
JSON Response Example

```

Use this endpoint in order to recover password from a User. It recives the user email , and send them an email with a unique link to change password.

#### Headers

`POST https://api.rebill.to/v1/users/password/recover`

Header | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`

#### Body
Parameter | Description
--------- | ----------- |
Email | Email in plain text

#### Response

Attribute | Content | Always Present | Description
--------- | ----------- | ----------- | -----------
`success` | boolean | Yes | Returns `true` if the performed action was success, otherwise `false`.
`response` | object | Yes | Contains an object with the result of the performed action if success. If an error ocurred, the response object will not exist. Check the error response format.

##Validate Email

```shell
CURL Request Example

curl --request POST \
  --url https://api.rebill.to/v1/users/validate/email \
  --header 'Accept: */*' \
  --header 'Accept-Encoding: gzip, deflate' \
  --header 'Cache-Control: no-cache' \
  --header 'Connection: keep-alive' \
  --header 'Content-Length: 162' \
  --header 'Content-Type: application/json' \
  --header 'Host: api.rebill.to' \
  --header 'Postman-Token: b6c7ba07-da1a-43d7-bfd2-8bfc9ca8de5a,513dac06-a837-43c1-ae20-a36fad97f913' \
  --header 'User-Agent: PostmanRuntime/7.20.1' \
  --header 'cache-control: no-cache' \
  --data '{\n  "token": "eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEtnU1ZJVVEzRkZIeXpJYlllUEJjRnVnRS9aL3QybFhuMXpUQUV3WEJlQi5RbVhwN3dIdVZX.3PT3XDsU4rl-QMBFY8ogQEqfP36JHxi0vrOL6aSNAgA"\n}'
```

```javascript
Node.JS Request Example

var request = require("request");

var options = { method: 'POST',
  url: 'https://api.rebill.to/v1/users/validate/email',
  headers: 
   { 'cache-control': 'no-cache',
     Connection: 'keep-alive',
     'Content-Length': '162',
     'Accept-Encoding': 'gzip, deflate',
     Host: 'api.rebill.to',
     'Postman-Token': 'b6c7ba07-da1a-43d7-bfd2-8bfc9ca8de5a,727523c3-a32f-4c57-bc7c-f823baa20107',
     'Cache-Control': 'no-cache',
     Accept: '*/*',
     'User-Agent': 'PostmanRuntime/7.20.1',
     'Content-Type': 'application/json' },
  body: { token: 'eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEtnU1ZJVVEzRkZIeXpJYlllUEJjRnVnRS9aL3QybFhuMXpUQUV3WEJlQi5RbVhwN3dIdVZX.3PT3XDsU4rl-QMBFY8ogQEqfP36JHxi0vrOL6aSNAgA' },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```ruby
Ruby Request Example

require 'uri'
require 'net/http'

url = URI("https://api.rebill.to/v1/users/validate/email")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["Content-Type"] = 'application/json'
request["User-Agent"] = 'PostmanRuntime/7.20.1'
request["Accept"] = '*/*'
request["Cache-Control"] = 'no-cache'
request["Postman-Token"] = 'b6c7ba07-da1a-43d7-bfd2-8bfc9ca8de5a,fb10682a-29eb-4b96-adf5-f60d12ea2a2b'
request["Host"] = 'api.rebill.to'
request["Accept-Encoding"] = 'gzip, deflate'
request["Content-Length"] = '162'
request["Connection"] = 'keep-alive'
request["cache-control"] = 'no-cache'
request.body = "{\n  \"token\": \"eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEtnU1ZJVVEzRkZIeXpJYlllUEJjRnVnRS9aL3QybFhuMXpUQUV3WEJlQi5RbVhwN3dIdVZX.3PT3XDsU4rl-QMBFY8ogQEqfP36JHxi0vrOL6aSNAgA\"\n}"

response = http.request(request)
puts response.read_body
```

```python
Python Request Example


import requests

url = "https://api.rebill.to/v1/users/validate/email"

payload = "{\n  \"token\": \"eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEtnU1ZJVVEzRkZIeXpJYlllUEJjRnVnRS9aL3QybFhuMXpUQUV3WEJlQi5RbVhwN3dIdVZX.3PT3XDsU4rl-QMBFY8ogQEqfP36JHxi0vrOL6aSNAgA\"\n}"
headers = {
    'Content-Type': "application/json",
    'User-Agent': "PostmanRuntime/7.20.1",
    'Accept': "*/*",
    'Cache-Control': "no-cache",
    'Postman-Token': "b6c7ba07-da1a-43d7-bfd2-8bfc9ca8de5a,e548fcbe-ca9f-4d59-8e8d-fe9903eb1288",
    'Host': "api.rebill.to",
    'Accept-Encoding': "gzip, deflate",
    'Content-Length': "162",
    'Connection': "keep-alive",
    'cache-control': "no-cache"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```php
PHP Request Example

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.rebill.to/v1/users/validate/email",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\n  \"token\": \"eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEtnU1ZJVVEzRkZIeXpJYlllUEJjRnVnRS9aL3QybFhuMXpUQUV3WEJlQi5RbVhwN3dIdVZX.3PT3XDsU4rl-QMBFY8ogQEqfP36JHxi0vrOL6aSNAgA\"\n}",
  CURLOPT_HTTPHEADER => array(
    "Accept: */*",
    "Accept-Encoding: gzip, deflate",
    "Cache-Control: no-cache",
    "Connection: keep-alive",
    "Content-Length: 162",
    "Content-Type: application/json",
    "Host: api.rebill.to",
    "Postman-Token: b6c7ba07-da1a-43d7-bfd2-8bfc9ca8de5a,7a85cd1c-beec-4b38-ada2-e23f8e6ddaf8",
    "User-Agent: PostmanRuntime/7.20.1",
    "cache-control: no-cache"
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
GO Request Example

package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.rebill.to/v1/users/validate/email"

	payload := strings.NewReader("{\n  \"token\": \"eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEtnU1ZJVVEzRkZIeXpJYlllUEJjRnVnRS9aL3QybFhuMXpUQUV3WEJlQi5RbVhwN3dIdVZX.3PT3XDsU4rl-QMBFY8ogQEqfP36JHxi0vrOL6aSNAgA\"\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("Content-Type", "application/json")
	req.Header.Add("User-Agent", "PostmanRuntime/7.20.1")
	req.Header.Add("Accept", "*/*")
	req.Header.Add("Cache-Control", "no-cache")
	req.Header.Add("Postman-Token", "b6c7ba07-da1a-43d7-bfd2-8bfc9ca8de5a,b3f90660-4e90-4bce-b781-c8f61b744cf0")
	req.Header.Add("Host", "api.rebill.to")
	req.Header.Add("Accept-Encoding", "gzip, deflate")
	req.Header.Add("Content-Length", "162")
	req.Header.Add("Connection", "keep-alive")
	req.Header.Add("cache-control", "no-cache")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```json
JSON Response Example

```


Use this endpoint in order to validate an email address.

#### Headers

`POST https://api.rebill.to/v1/users/validate/email`

Header | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`
Authorization | `Basic base64_hash` | Yes | Your username and password in base64.

#### Response

Attribute | Content | Always Present | Description
--------- | ----------- | ----------- | -----------
`success` | boolean | Yes | Returns `true` if the performed action was success, otherwise `false`.
`response` | object | Yes | Contains an object with the result of the performed action if success. If an error ocurred, the response object will not exist. Check the error response format.

##Sign Up

```shell
CURL Request Example

curl --request POST \
  --url https://api.rebill.to/v1/signup \
  --header 'Accept: */*' \
  --header 'Accept-Encoding: gzip, deflate' \
  --header 'Cache-Control: no-cache' \
  --header 'Connection: keep-alive' \
  --header 'Content-Length: 377' \
  --header 'Content-Type: application/json' \
  --header 'Host: api.rebill.to' \
  --header 'Postman-Token: 853270a7-ff28-4474-9762-46548e01d6b9,06e424dd-e9af-4d56-a8ea-ccf0901b196c' \
  --header 'User-Agent: PostmanRuntime/7.20.1' \
  --header 'cache-control: no-cache' \
  --data '{\n	"organization": {\n		"name":"Company Name",\n		"address_street":"sample_address_street",\n		"address_number":"00000",\n		"address_floor":"1",\n		"address_apt":"A",\n		"address_city":"Buenos Aires",\n		"address_province":"Buenos Aires",\n		"zipcode":"0000"\n	},\n	"user": {\n		"firstName": "Nahuel",\n		"lastName": "Candia",\n		"email": "support@rebill.to",\n		"password": "pepito123"\n	}\n}'
```

```javascript
Node.JS Request Example

var request = require("request");

var options = { method: 'POST',
  url: 'https://api.rebill.to/v1/signup',
  headers: 
   { 'Postman-Token': 'e155690a-4930-4078-9c04-d8815b3abda6',
     'cache-control': 'no-cache',
     'Content-Type': 'application/json' },
  body: 
   { organization: 
      { name: 'Company Name',
        address_street: 'sample_address_street',
        address_number: '00000',
        address_floor: '1',
        address_apt: 'A',
        address_city: 'Buenos Aires',
        address_province: 'Buenos Aires',
        zipcode: '0000' },
     user: 
      { firstName: 'Nahuel',
        lastName: 'Candia',
        email: 'support@rebill.to',
        password: 'pepito123' } },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});

```

```ruby
require 'uri'
require 'net/http'

url = URI("https://api.rebill.to/v1/signup")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["Content-Type"] = 'application/json'
request["cache-control"] = 'no-cache'
request["Postman-Token"] = '5fa8bc99-51ca-4430-b09b-5a6fa059058d'
request.body = "{\n\t\"organization\": {\n\t\t\"name\":\"Company Name\",\n\t\t\"address_street\":\"sample_address_street\",\n\t\t\"address_number\":\"00000\",\n\t\t\"address_floor\":\"1\",\n\t\t\"address_apt\":\"A\",\n\t\t\"address_city\":\"Buenos Aires\",\n\t\t\"address_province\":\"Buenos Aires\",\n\t\t\"zipcode\":\"0000\"\n\t},\n\t\"user\": {\n\t\t\"firstName\": \"Nahuel\",\n\t\t\"lastName\": \"Candia\",\n\t\t\"email\": \"support@rebill.to\",\n\t\t\"password\": \"pepito123\"\n\t}\n}"

response = http.request(request)
puts response.read_body
```

```python
Python Request Example

import requests

url = "https://api.rebill.to/v1/signup"

payload = "{\n\t\"organization\": {\n\t\t\"name\":\"Company Name\",\n\t\t\"address_street\":\"sample_address_street\",\n\t\t\"address_number\":\"00000\",\n\t\t\"address_floor\":\"1\",\n\t\t\"address_apt\":\"A\",\n\t\t\"address_city\":\"Buenos Aires\",\n\t\t\"address_province\":\"Buenos Aires\",\n\t\t\"zipcode\":\"0000\"\n\t},\n\t\"user\": {\n\t\t\"firstName\": \"Nahuel\",\n\t\t\"lastName\": \"Candia\",\n\t\t\"email\": \"support@rebill.to\",\n\t\t\"password\": \"pepito123\"\n\t}\n}"
headers = {
    'Content-Type': "application/json",
    'cache-control': "no-cache",
    'Postman-Token': "52ad227b-a4a6-4035-942c-f7d0ec6f72f7"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```php
PHP Request Example

<?php

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.rebill.to/v1/signup",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\n\t\"organization\": {\n\t\t\"name\":\"Company Name\",\n\t\t\"address_street\":\"sample_address_street\",\n\t\t\"address_number\":\"00000\",\n\t\t\"address_floor\":\"1\",\n\t\t\"address_apt\":\"A\",\n\t\t\"address_city\":\"Buenos Aires\",\n\t\t\"address_province\":\"Buenos Aires\",\n\t\t\"zipcode\":\"0000\"\n\t},\n\t\"user\": {\n\t\t\"firstName\": \"Nahuel\",\n\t\t\"lastName\": \"Candia\",\n\t\t\"email\": \"support@rebill.to\",\n\t\t\"password\": \"pepito123\"\n\t}\n}",
  CURLOPT_HTTPHEADER => array(
    "Content-Type: application/json",
    "Postman-Token: 9dc0a084-b585-4113-b00b-3b40e56d3d90",
    "cache-control: no-cache"
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
GO Request Example

package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.rebill.to/v1/signup"

	payload := strings.NewReader("{\n\t\"organization\": {\n\t\t\"name\":\"Company Name\",\n\t\t\"address_street\":\"sample_address_street\",\n\t\t\"address_number\":\"00000\",\n\t\t\"address_floor\":\"1\",\n\t\t\"address_apt\":\"A\",\n\t\t\"address_city\":\"Buenos Aires\",\n\t\t\"address_province\":\"Buenos Aires\",\n\t\t\"zipcode\":\"0000\"\n\t},\n\t\"user\": {\n\t\t\"firstName\": \"Nahuel\",\n\t\t\"lastName\": \"Candia\",\n\t\t\"email\": \"support@rebill.to\",\n\t\t\"password\": \"pepito123\"\n\t}\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("Content-Type", "application/json")
	req.Header.Add("cache-control", "no-cache")
	req.Header.Add("Postman-Token", "3f2c5786-072e-4d3b-844f-05c008482446")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```json
JSON Response Example

```

Use this endpoint in order to signup new orgnizations into the Rebill Platform.

#### Headers

`POST https://api.rebill.to/v1/signup`

Header | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`

#### Response

Attribute | Content | Always Present | Description
--------- | ----------- | ----------- | -----------
`success` | boolean | Yes | Returns `true` if the performed action was success, otherwise `false`.
`response` | object | Yes | Contains an object with the result of the performed action if success. If an error ocurred, the response object will not exist. Check the error response format.
