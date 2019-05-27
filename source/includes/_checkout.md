#Checkout

##Basic Checkout

```shell
curl --request POST \
  --url 'https://api.surcoseguros.com.ar/v1/checkout/basic' \
  --header 'Authorization: JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc' \
  --header 'Content-Type: application/json' \
  --data '{
	"callbackURL":"http://www.surcoseguros.com.ar",
	"planID":3,
	"start_date":"1/04/2018",
	"customerData": {
		"email":"you@domain.com"
	},
	"extra": {
		"phone_brand": "samsung",
		"phone_model": "s8",
		"phone_IMEI": "1298319230198209487378377",
		"phone_POS": "sample_location"
	}
}'
```

```javascript
var http = require("http");

var options = {
  "method": "POST",
  "hostname": [
    "https://api.surcoseguros.com.ar"
  ],
  "path": [
    "v1",
    "checkout",
    "basic"
  ],
  "headers": {
    "Authorization": "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc",
    "Content-Type": "application/json"
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

req.write(JSON.stringify({ callbackURL: 'http://www.surcoseguros.com.ar',
  planID: 3,
  start_date: '1/04/2018',
  customerData: { email: 'you@domain.com' },
  extra:
   { phone_brand: 'samsung',
     phone_model: 's8',
     phone_IMEI: '1298319230198209487378377',
     phone_POS: 'sample_location' } }));
req.end();
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://api.surcoseguros.com.ar/v1/checkout/basic")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["Authorization"] = 'JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc'
request["Content-Type"] = 'application/json'
request.body = "{\n\t\"callbackURL\":\"http://www.surcoseguros.com.ar\",\n\t\"planID\":3,\n\t\"start_date\":\"1/04/2018\",\n\t\"customerData\": {\n\t\t\"email\":\"you@domain.com\"\n\t},\n\t\"extra\": {\n\t\t\"phone_brand\": \"samsung\",\n\t\t\"phone_model\": \"s8\",\n\t\t\"phone_IMEI\": \"1298319230198209487378377\",\n\t\t\"phone_POS\": \"sample_location\"\n\t}\n}"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://api.surcoseguros.com.ar/v1/checkout/basic"

payload = "{\n\t\"callbackURL\":\"http://www.surcoseguros.com.ar\",\n\t\"planID\":3,\n\t\"start_date\":\"1/04/2018\",\n\t\"customerData\": {\n\t\t\"email\":\"you@domain.com\"\n\t},\n\t\"extra\": {\n\t\t\"phone_brand\": \"samsung\",\n\t\t\"phone_model\": \"s8\",\n\t\t\"phone_IMEI\": \"1298319230198209487378377\",\n\t\t\"phone_POS\": \"sample_location\"\n\t}\n}"
headers = {
    'Authorization': "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc",
    'Content-Type': "application/json"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.surcoseguros.com.ar/v1/checkout/basic",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\n\t\"callbackURL\":\"http://www.surcoseguros.com.ar\",\n\t\"planID\":3,\n\t\"start_date\":\"1/04/2018\",\n\t\"customerData\": {\n\t\t\"email\":\"you@domain.com\"\n\t},\n\t\"extra\": {\n\t\t\"phone_brand\": \"samsung\",\n\t\t\"phone_model\": \"s8\",\n\t\t\"phone_IMEI\": \"1298319230198209487378377\",\n\t\t\"phone_POS\": \"sample_location\"\n\t}\n}",
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
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.surcoseguros.com.ar/v1/checkout/basic"

	payload := strings.NewReader("{\n\t\"callbackURL\":\"http://www.surcoseguros.com.ar\",\n\t\"planID\":3,\n\t\"start_date\":\"1/04/2018\",\n\t\"customerData\": {\n\t\t\"email\":\"you@domain.com\"\n\t},\n\t\"extra\": {\n\t\t\"phone_brand\": \"samsung\",\n\t\t\"phone_model\": \"s8\",\n\t\t\"phone_IMEI\": \"1298319230198209487378377\",\n\t\t\"phone_POS\": \"sample_location\"\n\t}\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("Authorization", "JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc")
	req.Header.Add("Content-Type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```json
{
	"callbackURL":"http://www.surcoseguros.com.ar",
	"planID":3,
	"start_date":"1/04/2018",
	"customerData": {
		"email":"you@domain.com"
	},
	"extra": {
		"phone_brand": "samsung",
		"phone_model": "s8",
		"phone_IMEI": "1298319230198209487378377",
		"phone_POS": "sample_location"
	}
}
```
Basic Checkout uses MercadoPago to process the payment. After sending the required JSON as stated, you will get a response with the init_point that shall be used to process the payment.
After the payment is processed, the customer will be returned to the `callbackURL` defined before. You can customize the `callbackURL` to redirect to any Thank You page in your system.

### HTTP Request

`POST https://api.surcoseguros.com.ar/v1/checkout/basic`

The request shall be sent in JSON Format.

Header | Content
--------- | -----------
Authorization | JWT eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwicGFzc3dvcmQiOiIkMmEkMTAkUzBCUk5TcWdBUTVDODVwa1cuSVpQZVZQeW95dWUxbDNQeko4MjVjcGRkVjMuOWxrT052ajYifQ.rD9kYRH6Q7VKYAuvxl0VL0b1JQwLMaDHArntRoVugrc
Content-type | application/json

### URL Parameters

Parameter | Description
--------- | -----------
callbackURL | The URL to return after the successful payment in Mercadopago.
planID | The Plan ID provided (to know more about the different plans available please write us).
start_date | The date of the first charge.
customerData | Object containing all the customer's data. The following information shall be contained as in the sample JSON provided: `firstName`, `lastName`, `email`, `phone`, `birthday`, `vat_type` (your responsability to AFIP, As Known As 'Responsable Inscripto, Excento'), `vatID_number` (or CUIT), `personalID_type` (passport, or DNI), `personalID_number`, `address_street`, `address_number`, `address_floor`, `address_apt` (apartment), `zipcode`, `city`, `province`, `description` (optional).
extra | Depending of the plan, you shall include the extra information inside this Object in JSON format. E.g. for Mobile Protection the following fields are required: `phone_brand`, `phone_model`, `phone_IMEI`, `phone_POS`
