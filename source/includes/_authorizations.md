#Authorizations

Each user is attached to a Role, and a Role is defined by its permissions. Each endpoint has a one-to-one relation to a permission id and description.

In order to enable a user to access a set of permissions, it shall be related to a Role ID. For adding more than one permission to a Role, use the role/permissions endpoints.

Note that this feature is for Administrators only.

## Get All Roles

```shell
curl --request GET \
  --url 'https://api.surcoseguros.com.ar/v1/roles/all' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'
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
    "roles",
    "all"
  ],
  "headers": {
    "Authorization": "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

url = URI("https://api.surcoseguros.com.ar/v1/roles/all")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/roles/all"

headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/roles/all",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

	url := "https://api.surcoseguros.com.ar/v1/roles/all"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
```json
//JSON Sample Response
{
    "response": [
        {
            "id": 1,
            "name": "Administrador",
            "description": null,
            "updatedAt": null,
            "createdAt": null
        },
        {
            "id": 2,
            "name": "Productor",
            "description": null,
            "updatedAt": null,
            "createdAt": null
        }
    ]
}
```

### HTTP Request

`GET https://api.surcoseguros.com.ar/v1/roles/all`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM
Content-type | application/json

### Body Parameters

Parameter | Description
--------- | -----------
name | Name of the new role.
description | Description of the new role.

## Get All Role Permissions

```shell
curl --request GET \
  --url 'https://api.surcoseguros.com.ar/v1/roles/permissions' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'
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
    "roles",
    "permissions"
  ],
  "headers": {
    "Authorization": "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

url = URI("https://api.surcoseguros.com.ar/v1/roles/permissions")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/roles/permissions"

headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/roles/permissions",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

	url := "https://api.surcoseguros.com.ar/v1/roles/permissions"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
```json
//JSON Sample Response
{
    "response": [
        {
            "id": 1,
            "name": "VIEW_MY_COMPANIES"
        },
        {
            "id": 2,
            "name": "VIEW_ALL_COMPANIES"
        }
    ]
}
```
### HTTP Request

`GET https://api.surcoseguros.com.ar/v1/roles/permissions`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM
Content-type | application/json

### URL Parameters

Parameter | Description
--------- | -----------
:type | Retrieve the Plan by `planID` or `mpPlanID`.
:id | ID of the Plan to Retrieve.

## Get Permissions by Role ID

```shell
curl --request GET \
  --url 'https://api.surcoseguros.com.ar/v1/roles/1' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'
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
    "roles",
    "1"
  ],
  "headers": {
    "Authorization": "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

url = URI("https://api.surcoseguros.com.ar/v1/roles/1")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/roles/1"

headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/roles/1",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

	url := "https://api.surcoseguros.com.ar/v1/roles/1"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

### HTTP Request

`GET https://api.surcoseguros.com.ar/v1/roles/:id`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM
Content-type | application/json

### URL Parameters

Parameter | Description
--------- | -----------
:type | Retrieve the Plan by `planID` or `mpPlanID`.
:id | ID of the Plan to Retrieve.

## New Role

```shell
curl --request PUT \
  --url 'https://api.surcoseguros.com.ar/v1/roles/new' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78' \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --data 'name=test&description=descriptiontest'
```

```javascript
var qs = require("querystring");
var http = require("http");

var options = {
  "method": "PUT",
  "hostname": [
    "https://api.surcoseguros.com.ar"
  ],
  "path": [
    "v1",
    "roles",
    "new"
  ],
  "headers": {
    "Content-Type": "application/x-www-form-urlencoded",
    "Authorization": "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

req.write(qs.stringify({ name: 'test', description: 'descriptiontest' }));
req.end();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://api.surcoseguros.com.ar/v1/roles/new")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["Content-Type"] = 'application/x-www-form-urlencoded'
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'
request.body = "name=test&description=descriptiontest"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/roles/new"

payload = "name=test&description=descriptiontest"
headers = {
    'Content-Type': "application/x-www-form-urlencoded",
    'Authorization': "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
    }

response = requests.request("PUT", url, data=payload, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/roles/new",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "PUT",
  CURLOPT_POSTFIELDS => "name=test&description=descriptiontest",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78",
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

	url := "https://api.surcoseguros.com.ar/v1/roles/new"

	payload := strings.NewReader("name=test&description=descriptiontest")

	req, _ := http.NewRequest("PUT", url, payload)

	req.Header.Add("Content-Type", "application/x-www-form-urlencoded")
	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

### HTTP Request

`PUT https://api.surcoseguros.com.ar/v1/roles/new`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM
Content-type | application/json

### URL Parameters

Parameter | Description
--------- | -----------
:type | Retrieve the Plan by `planID` or `mpPlanID`.
:id | ID of the Plan to Retrieve.

## Update Role by ID

```shell
curl --request POST \
  --url 'https://api.surcoseguros.com.ar/v1/roles/update' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78' \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --data 'id=5&name=test1&description=descriptiontest1'
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
    "roles",
    "update"
  ],
  "headers": {
    "Content-Type": "application/x-www-form-urlencoded",
    "Authorization": "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

req.write(qs.stringify({ id: '5', name: 'test1', description: 'descriptiontest1' }));
req.end();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://api.surcoseguros.com.ar/v1/roles/update")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["Content-Type"] = 'application/x-www-form-urlencoded'
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'
request.body = "id=5&name=test1&description=descriptiontest1"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/roles/update"

payload = "id=5&name=test1&description=descriptiontest1"
headers = {
    'Content-Type': "application/x-www-form-urlencoded",
    'Authorization': "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/roles/update",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "id=5&name=test1&description=descriptiontest1",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78",
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

	url := "https://api.surcoseguros.com.ar/v1/roles/update"

	payload := strings.NewReader("id=5&name=test1&description=descriptiontest1")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("Content-Type", "application/x-www-form-urlencoded")
	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

### HTTP Request

`POST https://api.surcoseguros.com.ar/v1/roles/update`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM
Content-type | application/json

### URL Parameters

Parameter | Description
--------- | -----------
:type | Retrieve the Plan by `planID` or `mpPlanID`.
:id | ID of the Plan to Retrieve.

## Add Permission to Role

```shell
curl --request PUT \
  --url 'https://api.surcoseguros.com.ar/v1/roles/addpermission' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78' \
  --data 'role_id=2&permission_id=2000&description=test'
```

```javascript
var qs = require("querystring");
var http = require("http");

var options = {
  "method": "PUT",
  "hostname": [
    "https://api.surcoseguros.com.ar"
  ],
  "path": [
    "v1",
    "roles",
    "addpermission"
  ],
  "headers": {
    "Authorization": "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

req.write(qs.stringify({ role_id: '2', permission_id: '2000', description: 'test' }));
req.end();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://api.surcoseguros.com.ar/v1/roles/addpermission")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'
request.body = "role_id=2&permission_id=2000&description=test"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/roles/addpermission"

payload = "role_id=2&permission_id=2000&description=test"
headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'}

response = requests.request("PUT", url, data=payload, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/roles/addpermission",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "PUT",
  CURLOPT_POSTFIELDS => "role_id=2&permission_id=2000&description=test",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

	url := "https://api.surcoseguros.com.ar/v1/roles/addpermission"

	payload := strings.NewReader("role_id=2&permission_id=2000&description=test")

	req, _ := http.NewRequest("PUT", url, payload)

	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

### HTTP Request

`PUT https://api.surcoseguros.com.ar/v1/roles/addpermission`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM
Content-type | application/json

### URL Parameters

Parameter | Description
--------- | -----------
:type | Retrieve the Plan by `planID` or `mpPlanID`.
:id | ID of the Plan to Retrieve.

## Remove Permission to Role

```shell
curl --request POST \
  --url 'https://api.surcoseguros.com.ar/v1/roles/removepermission/' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78' \
  --data 'role_id=2&permission_id=2000'
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
    "roles",
    "removepermission",
    ""
  ],
  "headers": {
    "Authorization": "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

req.write(qs.stringify({ role_id: '2', permission_id: '2000' }));
req.end();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://api.surcoseguros.com.ar/v1/roles/removepermission/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'
request.body = "role_id=2&permission_id=2000"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/roles/removepermission/"

payload = "role_id=2&permission_id=2000"
headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'}

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/roles/removepermission/",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "role_id=2&permission_id=2000",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

	url := "https://api.surcoseguros.com.ar/v1/roles/removepermission/"

	payload := strings.NewReader("role_id=2&permission_id=2000")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

### HTTP Request

`POST https://api.surcoseguros.com.ar/v1/roles/removepermission/`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM
Content-type | application/json

### URL Parameters

Parameter | Description
--------- | -----------
:type | Retrieve the Plan by `planID` or `mpPlanID`.
:id | ID of the Plan to Retrieve.

## Set or Update Role to User

```shell
curl --request PUT \
  --url 'https://api.surcoseguros.com.ar/v1/roles/settouser' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78' \
  --data 'user_id=11&role_id=13'
```

```javascript
var qs = require("querystring");
var http = require("http");

var options = {
  "method": "PUT",
  "hostname": [
    "https://api.surcoseguros.com.ar"
  ],
  "path": [
    "v1",
    "roles",
    "settouser"
  ],
  "headers": {
    "Authorization": "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

req.write(qs.stringify({ user_id: '11', role_id: '13' }));
req.end();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://api.surcoseguros.com.ar/v1/roles/settouser")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'
request.body = "user_id=11&role_id=13"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/roles/settouser"

payload = "user_id=11&role_id=13"
headers = {'Authorization': 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'}

response = requests.request("PUT", url, data=payload, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/roles/settouser",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "PUT",
  CURLOPT_POSTFIELDS => "user_id=11&role_id=13",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

	url := "https://api.surcoseguros.com.ar/v1/roles/settouser"

	payload := strings.NewReader("user_id=11&role_id=13")

	req, _ := http.NewRequest("PUT", url, payload)

	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

### HTTP Request

`PUT https://api.surcoseguros.com.ar/v1/roles/settouser`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM
Content-type | application/json

### URL Parameters

Parameter | Description
--------- | -----------
:type | Retrieve the Plan by `planID` or `mpPlanID`.
:id | ID of the Plan to Retrieve.

## Delete Role

```shell
curl --request DELETE \
  --url 'https://api.surcoseguros.com.ar/v1/roles/delete/5' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78' \
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
    "roles",
    "delete",
    "5"
  ],
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
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

url = URI("https://api.surcoseguros.com.ar/v1/roles/delete/5")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Delete.new(url)
request["Content-Type"] = 'application/json'
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/roles/delete/5"

headers = {
    'Content-Type': "application/json",
    'Authorization': "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78"
    }

response = requests.request("DELETE", url, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/roles/delete/5",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "DELETE",
  CURLOPT_HTTPHEADER => array(
    "Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78",
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

	url := "https://api.surcoseguros.com.ar/v1/roles/delete/5"

	req, _ := http.NewRequest("DELETE", url, nil)

	req.Header.Add("Content-Type", "application/json")
	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkRGJXY2FtMW9HcEVhZUtHemt0NE5iZW5JUVM5dkMwRXVtaWlxc2J4ejFmek84ekFSNW1WUW0ifQ.DD1Wk4qBmEL1xOu8CaJv4WzJLcNPR-OqCZ6jg114P78")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

### HTTP Request

`DELETE https://api.surcoseguros.com.ar/v1/roles/delete/:id`

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6OSwicGFzc3dvcmQiOiIkMmEkMTAkcjdGQXlFNGZicnc1MEtWTkw0elJ4ZWxjaFdlREVwSDBYaUxNeFlPLlhDODR6RGkvWk9mcUsifQ.WJ_ijzdSYqPU8XqXRlDiR2YlSVhpijIPCU6aQFGSBOM
Content-type | application/json

### URL Parameters

Parameter | Description
--------- | -----------
:type | Retrieve the Plan by `planID` or `mpPlanID`.
:id | ID of the Plan to Retrieve.
