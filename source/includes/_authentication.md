#Authentication

Microservice for authentication into the Rebill Platform.

## Get Token

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

## Recover Password

```shell
CURL Request Example

curl --location --request POST 'https://api.rebill.to/v1/users/password/recover' \
--header 'Content-Type: application/json' \
--data-raw '{
  "email": "nahuel@rebill.to"
}'
```

```javascript
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://api-staging.rebill.to/v1/users/password/recover',
  'headers': {
    'Content-Type': 'application/json'
  },
  body: "{\n  \"email\": \"nahuel@rebill.to\"\n}"

};
request(options, function (error, response) { 
  if (error) throw new Error(error);
  console.log(response.body);
});

```

```ruby
require "uri"
require "net/http"

url = URI("https://api-staging.rebill.to/v1/users/password/recover")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Post.new(url)
request["Content-Type"] = "application/json"
request.body = "{\n  \"email\": \"nahuel@rebill.to\"\n}"

response = https.request(request)
puts response.read_body
```

```python
import requests

url = "https://api-staging.rebill.to/v1/users/password/recover"

payload = "{\n  \"email\": \"nahuel@rebill.to\"\n}"
headers = {
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api-staging.rebill.to/v1/users/password/recover",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS =>"{\n  \"email\": \"nahuel@rebill.to\"\n}",
  CURLOPT_HTTPHEADER => array(
    "Content-Type: application/json"
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

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

  url := "https://api-staging.rebill.to/v1/users/password/recover"
  method := "POST"

  payload := strings.NewReader("{\n  \"email\": \"nahuel@rebill.to\"\n}")

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, payload)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Content-Type", "application/json")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

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
Attribute | Content | Required | Description
--------- | ----------- | ----------- | -----------
email | String | Yes | Email in plain text

#### Response

Attribute | Content | Always Present | Description
--------- | ----------- | ----------- | -----------
`success` | boolean | Yes | Returns `true` if the performed action was success, otherwise `false`.
`response` | object | Yes | Contains an object with the result of the performed action if success. If an error ocurred, the response object will not exist. Check the error response format.

## Validate Email

```shell
curl --location --request POST 'https://api-staging.rebill.to/v1/users/validate/email' \
--header 'Content-Type: application/json' \
--data-raw '{
  "token": "eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEtnU1ZJVVEzRkZIeXpJYlllUEJjRnVnRS9aL3QybFhuMXpUQUV3WEJlQi5RbVhwN3dIdVZX.3PT3XDsU4rl-QMBFY8ogQEqfP36JHxi0vrOL6aSNAgA"
}'
```

```javascript
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://api-staging.rebill.to/v1/users/validate/email',
  'headers': {
    'Content-Type': 'application/json'
  },
  body: "{\n  \"token\": \"eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEtnU1ZJVVEzRkZIeXpJYlllUEJjRnVnRS9aL3QybFhuMXpUQUV3WEJlQi5RbVhwN3dIdVZX.3PT3XDsU4rl-QMBFY8ogQEqfP36JHxi0vrOL6aSNAgA\"\n}"

};
request(options, function (error, response) { 
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```ruby
require "uri"
require "net/http"

url = URI("https://api-staging.rebill.to/v1/users/validate/email")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Post.new(url)
request["Content-Type"] = "application/json"
request.body = "{\n  \"token\": \"eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEtnU1ZJVVEzRkZIeXpJYlllUEJjRnVnRS9aL3QybFhuMXpUQUV3WEJlQi5RbVhwN3dIdVZX.3PT3XDsU4rl-QMBFY8ogQEqfP36JHxi0vrOL6aSNAgA\"\n}"

response = https.request(request)
puts response.read_body
```

```python
import requests

url = "https://api-staging.rebill.to/v1/users/validate/email"

payload = "{\n  \"token\": \"eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEtnU1ZJVVEzRkZIeXpJYlllUEJjRnVnRS9aL3QybFhuMXpUQUV3WEJlQi5RbVhwN3dIdVZX.3PT3XDsU4rl-QMBFY8ogQEqfP36JHxi0vrOL6aSNAgA\"\n}"
headers = {
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api-staging.rebill.to/v1/users/validate/email",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS =>"{\n  \"token\": \"eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEtnU1ZJVVEzRkZIeXpJYlllUEJjRnVnRS9aL3QybFhuMXpUQUV3WEJlQi5RbVhwN3dIdVZX.3PT3XDsU4rl-QMBFY8ogQEqfP36JHxi0vrOL6aSNAgA\"\n}",
  CURLOPT_HTTPHEADER => array(
    "Content-Type: application/json"
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

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

  url := "https://api-staging.rebill.to/v1/users/validate/email"
  method := "POST"

  payload := strings.NewReader("{\n  \"token\": \"eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEtnU1ZJVVEzRkZIeXpJYlllUEJjRnVnRS9aL3QybFhuMXpUQUV3WEJlQi5RbVhwN3dIdVZX.3PT3XDsU4rl-QMBFY8ogQEqfP36JHxi0vrOL6aSNAgA\"\n}")

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, payload)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Content-Type", "application/json")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

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
curl --location --request POST 'https://api-staging.rebill.to/v1/signup' \
--header 'Content-Type: application/json' \
--data-raw '{
	"organization": {
		"name":"Company Name",
		"address_street":"sample_address_street",
		"address_number":"00000",
		"address_floor":"1",
		"address_apt":"A",
		"address_city":"Buenos Aires",
		"address_province":"Buenos Aires",
		"zipcode":"0000"
	},
	"user": {
		"firstName": "Nahuel",
		"lastName": "Candia",
		"email": "support@rebill.to",
		"password": "pepito123"
	}
}'
```

```javascript
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://api-staging.rebill.to/v1/signup',
  'headers': {
    'Content-Type': 'application/json'
  },
  body: "{\n\t\"organization\": {\n\t\t\"name\":\"Company Name\",\n\t\t\"address_street\":\"sample_address_street\",\n\t\t\"address_number\":\"00000\",\n\t\t\"address_floor\":\"1\",\n\t\t\"address_apt\":\"A\",\n\t\t\"address_city\":\"Buenos Aires\",\n\t\t\"address_province\":\"Buenos Aires\",\n\t\t\"zipcode\":\"0000\"\n\t},\n\t\"user\": {\n\t\t\"firstName\": \"Nahuel\",\n\t\t\"lastName\": \"Candia\",\n\t\t\"email\": \"support@rebill.to\",\n\t\t\"password\": \"pepito123\"\n\t}\n}"

};
request(options, function (error, response) { 
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```ruby
require "uri"
require "net/http"

url = URI("https://api-staging.rebill.to/v1/signup")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Post.new(url)
request["Content-Type"] = "application/json"
request.body = "{\n\t\"organization\": {\n\t\t\"name\":\"Company Name\",\n\t\t\"address_street\":\"sample_address_street\",\n\t\t\"address_number\":\"00000\",\n\t\t\"address_floor\":\"1\",\n\t\t\"address_apt\":\"A\",\n\t\t\"address_city\":\"Buenos Aires\",\n\t\t\"address_province\":\"Buenos Aires\",\n\t\t\"zipcode\":\"0000\"\n\t},\n\t\"user\": {\n\t\t\"firstName\": \"Nahuel\",\n\t\t\"lastName\": \"Candia\",\n\t\t\"email\": \"support@rebill.to\",\n\t\t\"password\": \"pepito123\"\n\t}\n}"

response = https.request(request)
puts response.read_body
```

```python
import requests

url = "https://api-staging.rebill.to/v1/signup"

payload = "{\n\t\"organization\": {\n\t\t\"name\":\"Company Name\",\n\t\t\"address_street\":\"sample_address_street\",\n\t\t\"address_number\":\"00000\",\n\t\t\"address_floor\":\"1\",\n\t\t\"address_apt\":\"A\",\n\t\t\"address_city\":\"Buenos Aires\",\n\t\t\"address_province\":\"Buenos Aires\",\n\t\t\"zipcode\":\"0000\"\n\t},\n\t\"user\": {\n\t\t\"firstName\": \"Nahuel\",\n\t\t\"lastName\": \"Candia\",\n\t\t\"email\": \"support@rebill.to\",\n\t\t\"password\": \"pepito123\"\n\t}\n}"
headers = {
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api-staging.rebill.to/v1/signup",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS =>"{\n\t\"organization\": {\n\t\t\"name\":\"Company Name\",\n\t\t\"address_street\":\"sample_address_street\",\n\t\t\"address_number\":\"00000\",\n\t\t\"address_floor\":\"1\",\n\t\t\"address_apt\":\"A\",\n\t\t\"address_city\":\"Buenos Aires\",\n\t\t\"address_province\":\"Buenos Aires\",\n\t\t\"zipcode\":\"0000\"\n\t},\n\t\"user\": {\n\t\t\"firstName\": \"Nahuel\",\n\t\t\"lastName\": \"Candia\",\n\t\t\"email\": \"support@rebill.to\",\n\t\t\"password\": \"pepito123\"\n\t}\n}",
  CURLOPT_HTTPHEADER => array(
    "Content-Type: application/json"
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

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

  url := "https://api-staging.rebill.to/v1/signup"
  method := "POST"

  payload := strings.NewReader("{\n	\"organization\": {\n		\"name\":\"Company Name\",\n		\"address_street\":\"sample_address_street\",\n		\"address_number\":\"00000\",\n		\"address_floor\":\"1\",\n		\"address_apt\":\"A\",\n		\"address_city\":\"Buenos Aires\",\n		\"address_province\":\"Buenos Aires\",\n		\"zipcode\":\"0000\"\n	},\n	\"user\": {\n		\"firstName\": \"Nahuel\",\n		\"lastName\": \"Candia\",\n		\"email\": \"support@rebill.to\",\n		\"password\": \"pepito123\"\n	}\n}")

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, payload)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Content-Type", "application/json")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

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

#### Body

`POST https://api.rebill.to/v1/signup`

Attribute | Content | Required | Description
--------- | ----------- | ----------- | -----------
`organization` | object | yes | object with all properties of the organization
`name` | String | Yes | Name of the organization
`address_street` | String | No | Adress name
`address_number` | String | No | Adress number
`address_floor` | String | No | Adress floor
`address_apt` | String | No | Adress apartment
`address_city` | String | No | Name of the city
`address_province` | String | No | Name of the Province / State
`address_zipcode` | String | Yes | Zip Code 
`user` | object | yes | properties of the user to add
`firstName` | String | Yes | Name of the user
`lastName` | String | Yes | Lastname of the user
`email` | String | Yes | Email of the user (Must be a valid one - Use validate email endpoint if needed)
`password` | String | Yes | Password of the user


#### Response

Attribute | Content | Always Present | Description
--------- | ----------- | ----------- | -----------
`success` | boolean | Yes | Returns `true` if the performed action was success, otherwise `false`.
`response` | object | Yes | Contains an object with the result of the performed action if success. If an error ocurred, the response object will not exist. Check the error response format.
