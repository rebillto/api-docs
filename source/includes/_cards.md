#Cards

## Get All Cards

```shell
curl --location --request GET 'https://api-staging.rebill.to/v1/cards' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag'
```

```javascript
var request = require('request');
var options = {
  'method': 'GET',
  'url': 'https://api-staging.rebill.to/v1/cards',
  'headers': {
    'Authorization': 'Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag'
  }
};
request(options, function (error, response) { 
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```ruby
require "uri"
require "net/http"

url = URI("https://api-staging.rebill.to/v1/cards")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Authorization"] = "Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag"

response = https.request(request)
puts response.read_body
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api-staging.rebill.to/v1/cards",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag"
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
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api-staging.rebill.to/v1/cards"
  method := "GET"

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, nil)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Authorization", "Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

  fmt.Println(string(body))
}
```

```json
{
    "success": true,
    "response": [
        {
            "id": 110,
            "customer_id": 9,
            "gateway_id": 1,
            "gateway_card_id": "787123123",
            "gateway_card_token": "48917823asdyh891273ijad91",
            "expiration_month": 10,
            "expiration_year": 2020,
            "first_six_digits": 445678,
            "last_four_digits": 6896,
            "payment_method_id": "visa",
            "payment_method_name": "Visa",
            "payment_method_type_id": "credit_card",
            "thumbnail": "http://img.mlstatic.com/org-img/MP3/API/logos/visa.gif",
            "secure_thumbnail": "https://www.mercadopago.com/org-img/MP3/API/logos/visa.gif",
            "security_code_length": 3,
            "security_code_location": "back",
            "issuer_id": 316,
            "issuer_name": "BBVA Frances",
            "cardholder_name": "xxxxxxx",
            "cardholder_identification_number": "12345678",
            "cardholder_identification_type": "DNI",
            "live_mode": true,
            "gateway_user_id": "473824949-6IY5jBHh3bsXjK",
            "organization_id": 0,
            "updatedAt": "2019-12-26",
            "createdAt": "2019-12-26",
            "deletedAt": null,
            "status": null
        },
        {
            "id": 111,
            "customer_id": 32,
            "gateway_id": 1,
            "gateway_card_id": "87109283981",
            "gateway_card_token": "LALISDJKLASHSD1123090909",
            "expiration_month": 10,
            "expiration_year": 2020,
            "first_six_digits": 556545,
            "last_four_digits": 3333,
            "payment_method_id": "visa",
            "payment_method_name": "Visa",
            "payment_method_type_id": "credit_card",
            "thumbnail": "http://img.mlstatic.com/org-img/MP3/API/logos/visa.gif",
            "secure_thumbnail": "https://www.mercadopago.com/org-img/MP3/API/logos/visa.gif",
            "security_code_length": 3,
            "security_code_location": "back",
            "issuer_id": 316,
            "issuer_name": "BBVA Frances",
            "cardholder_name": "XXXXX",
            "cardholder_identification_number": "1111111",
            "cardholder_identification_type": "DNI",
            "live_mode": true,
            "gateway_user_id": "XXXXXXX",
            "organization_id": 0,
            "updatedAt": "2019-12-27",
            "createdAt": "2019-12-27",
            "deletedAt": null,
            "status": null
        }
    ]
}
```

Use this endpoint to get an array of every card associated with an account. Access token is requiered

#### Headers

`GET https://api.rebill.to/v1/cards`

Header | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`
Authorization | Bearer {access_token} | Yes | Access token.

#### Response

Attribute | Content | Always Present | Description
--------- | ----------- | ----------- | -----------
`success` | boolean | Yes | Returns `true` if the performed action was success, otherwise `false`.
`response` | object | Yes | Contains an object with an array of all the available cards in the organizations' vault.
`id` | integer | Yes | The unique card id for Internal usage at Rebill platform.
`customer_id` | integer | Yes | The unique customer id for Internal usage at Rebill platform.
`gateway_id` | integer | Yes | The unique gateway id for Internal usage at Rebill platform.
`gateway_card_id` | integer | Yes | The unique gateway card id for Internal usage at Rebill platform.
`gateway_card_token` | string | Yes | The unique token of selected card
`expiration_month` | string | Yes | Two digits of the expiration month of the selected card.
`expiration_year` | string | Yes | Four digits of the expiration year of the selected card.
`first_six_digits` | string | Yes | Firs six digits of the selected card.
`last_four_digits` | string | Yes | Last four digits of the selected card.
`payment_method_id` | string | Yes | Payment ID of the selected card.
`payment_method_name` | string | Yes | Name of the card.
`payment_method_type_id` | string | Yes | Credit or debit card.
`thumbnail` | string | Yes | http url image of thumbnail for the payment method.
`secure_thumbnail` | string | Yes | https url image of thumbnail for the payment method.
`security_code_length` | integer | Yes | Length of the security code of the selected card.
`security_code_location` | string | Yes | Location of the security code in the selected card.
`issuer_id` | integer | Yes | Internal ID of the card issuer.
`issuer_name` | string | Yes | Name of the card issuer.
`cardholder_name` | string | Yes | Card holder name.
`cardholder_identification_number` | string | Yes | Card holder legal identification number.
`cardholder_identification_type` | string | Yes | Card holder legal identification type.
`live_mode` | boolean | Yes | Live mode.
`gateway_user_id` | string | Yes | Internal id of the user in the gateway.
`organization_id` | integer | Yes | Internal id of the user organization.
`updatedAt` | date | Yes | Updated date of the card.
`createdAt` | date | Yes | Created date of the card.
`deletedAt` | date | Yes | Deleted date of the card. (if any)
`status` | string | Yes | Status of the card.



## Get Cards by Customer Id

```shell
curl --location --request GET 'https://api-staging.rebill.to/v1/cards/customerid/9' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag'
```

```javascript
var request = require('request');
var options = {
  'method': 'GET',
  'url': 'https://api-staging.rebill.to/v1/cards/customerid/9',
  'headers': {
    'Authorization': 'Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag'
  }
};
request(options, function (error, response) { 
  if (error) throw new Error(error);
  console.log(response.body);
});

```

```ruby
require "uri"
require "net/http"

url = URI("https://api-staging.rebill.to/v1/cards/customerid/9")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Authorization"] = "Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag"

response = https.request(request)
puts response.read_body

```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api-staging.rebill.to/v1/cards/customerid/9",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag"
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
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api-staging.rebill.to/v1/cards/customerid/9"
  method := "GET"

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, nil)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Authorization", "Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

  fmt.Println(string(body))
}
```

```json
{
    "success": true,
    "response": [
        {
            "id": 110,
            "customer_id": 9,
            "gateway_id": 1,
            "gateway_card_id": "8797506460",
            "gateway_card_token": "4815dc4e712404c35640f0d367a866ab",
            "expiration_month": 10,
            "expiration_year": 2020,
            "first_six_digits": 454073,
            "last_four_digits": 6896,
            "payment_method_id": "visa",
            "payment_method_name": "Visa",
            "payment_method_type_id": "credit_card",
            "thumbnail": "http://img.mlstatic.com/org-img/MP3/API/logos/visa.gif",
            "secure_thumbnail": "https://www.mercadopago.com/org-img/MP3/API/logos/visa.gif",
            "security_code_length": 3,
            "security_code_location": "back",
            "issuer_id": 316,
            "issuer_name": "BBVA Frances",
            "cardholder_name": "Denis Nahuel Candia",
            "cardholder_identification_number": "38072739",
            "cardholder_identification_type": "DNI",
            "live_mode": true,
            "gateway_user_id": "473824949-6IY5jBHh3bsXjK",
            "organization_id": 0,
            "updatedAt": "2019-12-26",
            "createdAt": "2019-12-26",
            "deletedAt": null,
            "status": null
        }
    ]
}

```

Use this endpoint to retrieve all the cards associated to an customer.

#### Headers

`GET https://api.rebill.to/v1/customerid/`

Header | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`
Authorization | Bearer {access_token} | Yes | Access token.

#### Parameters

Name | Parameter | Type | Required | Description
--------- | --------- | ----------- | ----------- | -----------
CustomerID | QueryString | integer | No | ID of the selected customer.

#### Response

Attribute | Content | Always Present | Description
--------- | ----------- | ----------- | -----------
`success` | boolean | Yes | Returns `true` if the performed action was success, otherwise `false`.
`response` | object | Yes | Contains an object with the result of the performed action if success. If an error ocurred, the response object will not exist. Check the error response format.
`id` | integer | Yes | The unique card id for Internal usage at Rebill platform.
`customer_id` | integer | Yes | The unique customer id for Internal usage at Rebill platform.
`gateway_id` | integer | Yes | The unique gateway id for Internal usage at Rebill platform.
`gateway_card_id` | integer | Yes | The unique gateway card id for Internal usage at Rebill platform.
`gateway_card_token` | string | Yes | The unique token of selected card
`expiration_month` | string | Yes | Two digits of the expiration month of the selected card.
`expiration_year` | string | Yes | Four digits of the expiration year of the selected card.
`first_six_digits` | string | Yes | Firs six digits of the selected card.
`last_four_digits` | string | Yes | Last four digits of the selected card.
`payment_method_id` | string | Yes | Payment ID of the selected card.
`payment_method_name` | string | Yes | Name of the card.
`payment_method_type_id` | string | Yes | Credit or debit card.
`thumbnail` | string | Yes | http url image of thumbnail for the payment method.
`secure_thumbnail` | string | Yes | https url image of thumbnail for the payment method.
`security_code_length` | integer | Yes | Length of the security code of the selected card.
`security_code_location` | string | Yes | Location of the security code in the selected card.
`issuer_id` | integer | Yes | Internal ID of the card issuer.
`issuer_name` | string | Yes | Name of the card issuer.
`cardholder_name` | string | Yes | Card holder name.
`cardholder_identification_number` | string | Yes | Card holder legal identification number.
`cardholder_identification_type` | string | Yes | Card holder legal identification type.
`live_mode` | boolean | Yes | Live mode.
`gateway_user_id` | string | Yes | Internal id of the user in the gateway.
`organization_id` | integer | Yes | Internal id of the user organization.
`updatedAt` | date | Yes | Updated date of the card.
`createdAt` | date | Yes | Created date of the card.
`deletedAt` | date | Yes | Deleted date of the card. (if any)
`status` | string | Yes | Status of the card.

## Get Card By Id

```shell
curl --location --request GET 'https://api-staging.rebill.to/v1/cards/id/24' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag'
```

```javascript
var request = require('request');
var options = {
  'method': 'GET',
  'url': 'https://api-staging.rebill.to/v1/cards/id/24',
  'headers': {
    'Authorization': 'Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag'
  }
};
request(options, function (error, response) { 
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```ruby
require "uri"
require "net/http"

url = URI("https://api-staging.rebill.to/v1/cards/id/24")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Authorization"] = "Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag"

response = https.request(request)
puts response.read_body
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api-staging.rebill.to/v1/cards/id/24",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag"
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
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api-staging.rebill.to/v1/cards/id/24"
  method := "GET"

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, nil)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Authorization", "Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag")

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
        "id": 110,
        "customer_id": 9,
        "gateway_id": 1,
        "gateway_card_id": "8797506460",
        "gateway_card_token": "4815dc4e712404c35640f0d367a866ab",
        "expiration_month": 10,
        "expiration_year": 2020,
        "first_six_digits": 454073,
        "last_four_digits": 6896,
        "payment_method_id": "visa",
        "payment_method_name": "Visa",
        "payment_method_type_id": "credit_card",
        "thumbnail": "http://img.mlstatic.com/org-img/MP3/API/logos/visa.gif",
        "secure_thumbnail": "https://www.mercadopago.com/org-img/MP3/API/logos/visa.gif",
        "security_code_length": 3,
        "security_code_location": "back",
        "issuer_id": 316,
        "issuer_name": "BBVA Frances",
        "cardholder_name": "Denis Nahuel Candia",
        "cardholder_identification_number": "38072739",
        "cardholder_identification_type": "DNI",
        "live_mode": true,
        "gateway_user_id": "473824949-6IY5jBHh3bsXjK",
        "organization_id": 0,
        "updatedAt": "2019-12-26",
        "createdAt": "2019-12-26",
        "deletedAt": null,
        "status": null
    }
}
```

This endpoint allows you to retrieve information about a particular card , using the internal ID of the card (listed in the GetAllCards endpoint)

#### Headers

`GET https://api.rebill.to/v1/cards/id/:id`

Header | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`
Authorization | Bearer {access_token} | Yes | Access token.

#### Parameters

Name | Parameter | Type | Required | Description
--------- | --------- | ----------- | ----------- | -----------
id | QueryString | integer | Yes | ID of the card.

#### Response

Attribute | Content | Always Present | Description
--------- | ----------- | ----------- | -----------
`success` | boolean | Yes | Returns `true` if the performed action was success, otherwise `false`.
`response` | object | Yes | Contains an object with the result of the performed action if success. If an error ocurred, the response object will not exist. Check the error response format.
`id` | integer | Yes | The unique card id for Internal usage at Rebill platform.
`customer_id` | integer | Yes | The unique customer id for Internal usage at Rebill platform.
`gateway_id` | integer | Yes | The unique gateway id for Internal usage at Rebill platform.
`gateway_card_id` | integer | Yes | The unique gateway card id for Internal usage at Rebill platform.
`gateway_card_token` | string | Yes | The unique token of selected card
`expiration_month` | string | Yes | Two digits of the expiration month of the selected card.
`expiration_year` | string | Yes | Four digits of the expiration year of the selected card.
`first_six_digits` | string | Yes | Firs six digits of the selected card.
`last_four_digits` | string | Yes | Last four digits of the selected card.
`payment_method_id` | string | Yes | Payment ID of the selected card.
`payment_method_name` | string | Yes | Name of the card.
`payment_method_type_id` | string | Yes | Credit or debit card.
`thumbnail` | string | Yes | http url image of thumbnail for the payment method.
`secure_thumbnail` | string | Yes | https url image of thumbnail for the payment method.
`security_code_length` | integer | Yes | Length of the security code of the selected card.
`security_code_location` | string | Yes | Location of the security code in the selected card.
`issuer_id` | integer | Yes | Internal ID of the card issuer.
`issuer_name` | string | Yes | Name of the card issuer.
`cardholder_name` | string | Yes | Card holder name.
`cardholder_identification_number` | string | Yes | Card holder legal identification number.
`cardholder_identification_type` | string | Yes | Card holder legal identification type.
`live_mode` | boolean | Yes | Live mode.
`gateway_user_id` | string | Yes | Internal id of the user in the gateway.
`organization_id` | integer | Yes | Internal id of the user organization.
`updatedAt` | date | Yes | Updated date of the card.
`createdAt` | date | Yes | Created date of the card.
`deletedAt` | date | Yes | Deleted date of the card. (if any)
`status` | string | Yes | Status of the card.


## Add Card to Customer

```shell
curl --location --request POST 'https://api-staging.rebill.to/v1/cards' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag' \
--data-raw '{
    "customer_id": 9,
    "card": {
        "card_number": "4509953566233704",
        "expiration_month": "04",
        "expiration_year": "2022",
        "security_code": "000",
        "cardholder": {
            "name": "Denis Nahuel Candia",
            "identification": {
                "number": "38072739",
                "type": "DNI"
            }
        }
    }
}'
```

```javascript
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://api-staging.rebill.to/v1/cards',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag'
  },
  body: "{\n    \"customer_id\": 9,\n    \"card\": {\n        \"card_number\": \"4509953566233704\",\n        \"expiration_month\": \"04\",\n        \"expiration_year\": \"2022\",\n        \"security_code\": \"000\",\n        \"cardholder\": {\n            \"name\": \"Denis Nahuel Candia\",\n            \"identification\": {\n                \"number\": \"38072739\",\n                \"type\": \"DNI\"\n            }\n        }\n    }\n}"

};
request(options, function (error, response) { 
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```ruby
require "uri"
require "net/http"

url = URI("https://api-staging.rebill.to/v1/cards")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Post.new(url)
request["Content-Type"] = "application/json"
request["Authorization"] = "Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag"
request.body = "{\n    \"customer_id\": 9,\n    \"card\": {\n        \"card_number\": \"4509953566233704\",\n        \"expiration_month\": \"04\",\n        \"expiration_year\": \"2022\",\n        \"security_code\": \"000\",\n        \"cardholder\": {\n            \"name\": \"Denis Nahuel Candia\",\n            \"identification\": {\n                \"number\": \"38072739\",\n                \"type\": \"DNI\"\n            }\n        }\n    }\n}"

response = https.request(request)
puts response.read_body
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api-staging.rebill.to/v1/cards",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS =>"{\n    \"customer_id\": 9,\n    \"card\": {\n        \"card_number\": \"4509953566233704\",\n        \"expiration_month\": \"04\",\n        \"expiration_year\": \"2022\",\n        \"security_code\": \"000\",\n        \"cardholder\": {\n            \"name\": \"Denis Nahuel Candia\",\n            \"identification\": {\n                \"number\": \"38072739\",\n                \"type\": \"DNI\"\n            }\n        }\n    }\n}",
  CURLOPT_HTTPHEADER => array(
    "Content-Type: application/json",
    "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag"
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

  url := "https://api-staging.rebill.to/v1/cards"
  method := "POST"

  payload := strings.NewReader("{\n    \"customer_id\": 9,\n    \"card\": {\n        \"card_number\": \"4509953566233704\",\n        \"expiration_month\": \"04\",\n        \"expiration_year\": \"2022\",\n        \"security_code\": \"000\",\n        \"cardholder\": {\n            \"name\": \"Denis Nahuel Candia\",\n            \"identification\": {\n                \"number\": \"38072739\",\n                \"type\": \"DNI\"\n            }\n        }\n    }\n}")

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, payload)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Content-Type", "application/json")
  req.Header.Add("Authorization", "Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

  fmt.Println(string(body))
}
```

```json
{
    "success": true,
    "response": {
        "cardLocal": {
            "id": 122,
            "customer_id": 9,
            "gateway_id": "1",
            "gateway_card_id": "8800286669",
            "gateway_card_token": "19e80a070ee54fc398ba63dc9e7353bd",
            "gateway_user_id": "473824949-6IY5jBHh3bsXjK",
            "first_six_digits": "450995",
            "last_four_digits": "3704",
            "payment_method_id": "visa",
            "payment_method_name": "Visa",
            "payment_method_type_id": "credit_card",
            "thumbnail": "http://img.mlstatic.com/org-img/MP3/API/logos/310.gif",
            "secure_thumbnail": "https://www.mercadopago.com/org-img/MP3/API/logos/310.gif",
            "expiration_month": 4,
            "expiration_year": 2022,
            "cardholder_name": "Denis Nahuel Candia",
            "cardholder_identification_number": "38072739",
            "cardholder_identification_type": "DNI",
            "status": null,
            "live_mode": true,
            "security_code_length": 3,
            "security_code_location": "back",
            "issuer_id": 310,
            "issuer_name": "Banco Santander",
            "organization_id": "0",
            "updatedAt": "2020-01-02T15:12:48.303Z",
            "createdAt": "2020-01-02T15:12:48.303Z"
        },
        "cardTokenized": {
            "id": "8800286669",
            "expiration_month": 4,
            "expiration_year": 2022,
            "first_six_digits": "450995",
            "last_four_digits": "3704",
            "payment_method": {
                "id": "visa",
                "name": "Visa",
                "payment_type_id": "credit_card",
                "thumbnail": "http://img.mlstatic.com/org-img/MP3/API/logos/310.gif",
                "secure_thumbnail": "https://www.mercadopago.com/org-img/MP3/API/logos/310.gif"
            },
            "security_code": {
                "length": 3,
                "card_location": "back"
            },
            "issuer": {
                "id": 310,
                "name": "Banco Santander"
            },
            "cardholder": {
                "name": "Denis Nahuel Candia",
                "identification": {
                    "number": "38072739",
                    "type": "DNI"
                }
            },
            "date_created": "2020-01-02T11:12:48.138-04:00",
            "date_last_updated": "2020-01-02T11:12:48.138-04:00",
            "customer_id": "473824949-6IY5jBHh3bsXjK",
            "user_id": "473824949",
            "live_mode": true
        },
        "cardAttachmentResult": {
            "id": "8800286669",
            "expiration_month": 4,
            "expiration_year": 2022,
            "first_six_digits": "450995",
            "last_four_digits": "3704",
            "payment_method": {
                "id": "visa",
                "name": "Visa",
                "payment_type_id": "credit_card",
                "thumbnail": "http://img.mlstatic.com/org-img/MP3/API/logos/310.gif",
                "secure_thumbnail": "https://www.mercadopago.com/org-img/MP3/API/logos/310.gif"
            },
            "security_code": {
                "length": 3,
                "card_location": "back"
            },
            "issuer": {
                "id": 310,
                "name": "Banco Santander"
            },
            "cardholder": {
                "name": "XXXXXX",
                "identification": {
                    "number": "XXXXX",
                    "type": "DNI"
                }
            },
            "date_created": "2020-01-02T11:12:48.138-04:00",
            "date_last_updated": "2020-01-02T11:12:48.138-04:00",
            "customer_id": "473824949-6IY5jBHh3bsXjK",
            "user_id": "473824949",
            "live_mode": true
        }
    }
}

```

Use this endpoint to add a card to an existent customer 

#### Headers

`POST https://api.rebill.to/v1/cards`

Header | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`
Authorization | Bearer {access_token} | Yes | Access token.

#### Body

`POST https://api.rebill.to/v1/cards`

Attribute | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`
customer_id | integer | yes | customer id you selected
card | object | yes | object containing all the properties of the card
card_number | string | yes | card number
expiration_month | string | yes | expiration number of the card
expiration_year | string | yes | expiration year of the card
security_code | string | yes | 3 or 4 digits of the security code
cardholder | object | yes | object with cardholder information
name | string | yes | cardholder name
identification | object | yes | object with number and type of legal identification of cardholder
number | string | yes | number of the legal identification of cardholder
type | string | yes | type of the legal identification of cardholder

#### Response

Attribute | Content | Always Present | Description
--------- | ----------- | ----------- | -----------
`success` | boolean | Yes | Returns `true` if the performed action was success, otherwise `false`.
`response` | object | Yes | Contains an object with the result of the performed action if success. If an error ocurred, the response object will not exist. Check the error response format.

## Update Card

```shell
curl --location --request PUT 'https://api-staging.rebill.to/v1/cards' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag' \
--data-raw '{
    "customer_id": 9,
    "card_id": 122,
    "card": {
        "card_number": "4509953566233704",
        "expiration_month": "10",
        "expiration_year": "2020",
        "security_code": "166",
        "cardholder": {
            "name": "DENIS NAHUEL CANDIA",
            "identification": {
                "number": "38072739",
                "type": "DNI"
            }
        }
    }
}'
```

```javascript
var request = require('request');
var options = {
  'method': 'PUT',
  'url': 'https://api-staging.rebill.to/v1/cards',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag'
  },
  body: "{\n    \"customer_id\": 9,\n    \"card_id\": 122,\n    \"card\": {\n        \"card_number\": \"4509953566233704\",\n        \"expiration_month\": \"10\",\n        \"expiration_year\": \"2020\",\n        \"security_code\": \"166\",\n        \"cardholder\": {\n            \"name\": \"DENIS NAHUEL CANDIA\",\n            \"identification\": {\n                \"number\": \"38072739\",\n                \"type\": \"DNI\"\n            }\n        }\n    }\n}"

};
request(options, function (error, response) { 
  if (error) throw new Error(error);
  console.log(response.body);
});

```

```ruby
require "uri"
require "net/http"

url = URI("https://api-staging.rebill.to/v1/cards")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Put.new(url)
request["Content-Type"] = "application/json"
request["Authorization"] = "Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag"
request.body = "{\n    \"customer_id\": 9,\n    \"card_id\": 122,\n    \"card\": {\n        \"card_number\": \"4509953566233704\",\n        \"expiration_month\": \"10\",\n        \"expiration_year\": \"2020\",\n        \"security_code\": \"166\",\n        \"cardholder\": {\n            \"name\": \"DENIS NAHUEL CANDIA\",\n            \"identification\": {\n                \"number\": \"38072739\",\n                \"type\": \"DNI\"\n            }\n        }\n    }\n}"

response = https.request(request)
puts response.read_body

```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api-staging.rebill.to/v1/cards",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "PUT",
  CURLOPT_POSTFIELDS =>"{\n    \"customer_id\": 9,\n    \"card_id\": 122,\n    \"card\": {\n        \"card_number\": \"4509953566233704\",\n        \"expiration_month\": \"10\",\n        \"expiration_year\": \"2020\",\n        \"security_code\": \"166\",\n        \"cardholder\": {\n            \"name\": \"DENIS NAHUEL CANDIA\",\n            \"identification\": {\n                \"number\": \"38072739\",\n                \"type\": \"DNI\"\n            }\n        }\n    }\n}",
  CURLOPT_HTTPHEADER => array(
    "Content-Type: application/json",
    "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag"
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

  url := "https://api-staging.rebill.to/v1/cards"
  method := "PUT"

  payload := strings.NewReader("{\n    \"customer_id\": 9,\n    \"card_id\": 122,\n    \"card\": {\n        \"card_number\": \"4509953566233704\",\n        \"expiration_month\": \"10\",\n        \"expiration_year\": \"2020\",\n        \"security_code\": \"166\",\n        \"cardholder\": {\n            \"name\": \"DENIS NAHUEL CANDIA\",\n            \"identification\": {\n                \"number\": \"38072739\",\n                \"type\": \"DNI\"\n            }\n        }\n    }\n}")

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, payload)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Content-Type", "application/json")
  req.Header.Add("Authorization", "Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

  fmt.Println(string(body))
}
```

```json
{
    "success": true,
    "response": {
        "cardLocal": {
            "id": 123,
            "customer_id": 9,
            "gateway_id": "1",
            "gateway_card_id": "8800286669",
            "gateway_card_token": "a4481df3fc81c4d90345b9e04fe894da",
            "gateway_user_id": "473824949-6IY5jBHh3bsXjK",
            "first_six_digits": "450995",
            "last_four_digits": "3704",
            "payment_method_id": "visa",
            "payment_method_name": "Visa",
            "payment_method_type_id": "credit_card",
            "thumbnail": "http://img.mlstatic.com/org-img/MP3/API/logos/310.gif",
            "secure_thumbnail": "https://www.mercadopago.com/org-img/MP3/API/logos/310.gif",
            "expiration_month": 10,
            "expiration_year": 2020,
            "cardholder_name": "DENIS NAHUEL CANDIA",
            "cardholder_identification_number": "38072739",
            "cardholder_identification_type": "DNI",
            "status": null,
            "live_mode": true,
            "security_code_length": 3,
            "security_code_location": "back",
            "issuer_id": 310,
            "issuer_name": "Banco Santander",
            "organization_id": "0",
            "updatedAt": "2020-01-02T15:34:15.604Z",
            "createdAt": "2020-01-02T15:34:15.604Z"
        },
        "cardTokenized": {
            "id": "8800286669",
            "expiration_month": 10,
            "expiration_year": 2020,
            "first_six_digits": "450995",
            "last_four_digits": "3704",
            "payment_method": {
                "id": "visa",
                "name": "Visa",
                "payment_type_id": "credit_card",
                "thumbnail": "http://img.mlstatic.com/org-img/MP3/API/logos/310.gif",
                "secure_thumbnail": "https://www.mercadopago.com/org-img/MP3/API/logos/310.gif"
            },
            "security_code": {
                "length": 3,
                "card_location": "back"
            },
            "issuer": {
                "id": 310,
                "name": "Banco Santander"
            },
            "cardholder": {
                "name": "DENIS NAHUEL CANDIA",
                "identification": {
                    "number": "38072739",
                    "type": "DNI"
                }
            },
            "date_created": "2020-01-02T11:12:48.000-04:00",
            "date_last_updated": "2020-01-02T11:34:15.483-04:00",
            "customer_id": "473824949-6IY5jBHh3bsXjK",
            "user_id": "473824949",
            "live_mode": true
        },
        "cardAttachmentResult": {
            "id": "8800286669",
            "expiration_month": 10,
            "expiration_year": 2020,
            "first_six_digits": "450995",
            "last_four_digits": "3704",
            "payment_method": {
                "id": "visa",
                "name": "Visa",
                "payment_type_id": "credit_card",
                "thumbnail": "http://img.mlstatic.com/org-img/MP3/API/logos/310.gif",
                "secure_thumbnail": "https://www.mercadopago.com/org-img/MP3/API/logos/310.gif"
            },
            "security_code": {
                "length": 3,
                "card_location": "back"
            },
            "issuer": {
                "id": 310,
                "name": "Banco Santander"
            },
            "cardholder": {
                "name": "DENIS NAHUEL CANDIA",
                "identification": {
                    "number": "38072739",
                    "type": "DNI"
                }
            },
            "date_created": "2020-01-02T11:12:48.000-04:00",
            "date_last_updated": "2020-01-02T11:34:15.483-04:00",
            "customer_id": "473824949-6IY5jBHh3bsXjK",
            "user_id": "473824949",
            "live_mode": true
        }
    }
}

```

Use this endpoint to update information about an existent card (Expiration month for example)

#### Headers

`PUT https://api.rebill.to/v1/cards`

Header | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`
Authorization | Bearer {access_token} | Yes | Access token.

#### Body

`PUT https://api.rebill.to/v1/cards`

Attribute | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`


#### Response

Attribute | Content | Always Present | Description
--------- | ----------- | ----------- | -----------
`success` | boolean | Yes | Returns `true` if the performed action was success, otherwise `false`.
`response` | object | Yes | Contains an object with the result of the performed action if success. If an error ocurred, the response object will not exist. Check the error response format.

## Delete Card

```shell
curl --location --request DELETE 'https://api-staging.rebill.to/v1/cards/id/123' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag'
```

```javascript
var request = require('request');
var options = {
  'method': 'DELETE',
  'url': 'https://api-staging.rebill.to/v1/cards/id/123',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag'
  }
};
request(options, function (error, response) { 
  if (error) throw new Error(error);
  console.log(response.body);
});

```

```ruby
require "uri"
require "net/http"

url = URI("https://api-staging.rebill.to/v1/cards/id/123")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Delete.new(url)
request["Content-Type"] = "application/json"
request["Authorization"] = "Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag"

response = https.request(request)
puts response.read_body
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api-staging.rebill.to/v1/cards/id/123",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "DELETE",
  CURLOPT_HTTPHEADER => array(
    "Content-Type: application/json",
    "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag"
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
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api-staging.rebill.to/v1/cards/id/123"
  method := "DELETE"

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, nil)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Content-Type", "application/json")
  req.Header.Add("Authorization", "Bearer eyJhbGciOiJIUzI1NiJ9.JDJhJDEwJEt5YTJFeFdkMGU1TjJwbWc0aUY1ci5oc1ZwdzNNSDlndlMzN0c0ZFVYa0guZnBLN1RXdFdh.aG9_wxZA24j3n8qZw8r6B4UqY3jPpEZp49Z3yLBoJag")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

  fmt.Println(string(body))
}
```

```json
{
    "success": true,
    "response": {
        "unlinkMPResult": {
            "id": "8800286669",
            "expiration_month": 10,
            "expiration_year": 2020,
            "first_six_digits": "450995",
            "last_four_digits": "3704",
            "payment_method": {
                "id": "visa",
                "name": "Visa",
                "payment_type_id": "credit_card",
                "thumbnail": "http://img.mlstatic.com/org-img/MP3/API/logos/310.gif",
                "secure_thumbnail": "https://www.mercadopago.com/org-img/MP3/API/logos/310.gif"
            },
            "security_code": {
                "length": 3,
                "card_location": "back"
            },
            "issuer": {
                "id": 310,
                "name": "Banco Santander"
            },
            "cardholder": {
                "name": "DENIS NAHUEL CANDIA",
                "identification": {
                    "number": "38072739",
                    "type": "DNI"
                }
            },
            "date_created": "2020-01-02T11:12:48.000-04:00",
            "date_last_updated": "2020-01-02T11:37:06.903-04:00",
            "customer_id": "473824949-6IY5jBHh3bsXjK",
            "user_id": "473824949",
            "live_mode": true
        },
        "deleteLocalResult": 1
    }
}
```

This endpoint allows you to unlink a card to a customer.

#### Headers

`DEL https://api.rebill.to/v1/cards/id/:id`

Header | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`
Authorization | Bearer {access_token} | Yes | Access token.

#### Parameters

Name | Parameter | Type | Required | Description
--------- | --------- | ----------- | ----------- | -----------
id | QueryString | integer | yes | card id

#### Response

Attribute | Content | Always Present | Description
--------- | ----------- | ----------- | -----------
`success` | boolean | Yes | Returns `true` if the performed action was success, otherwise `false`.
`response` | object | Yes | Contains an object with the result of the performed action if success. If an error ocurred, the response object will not exist. Check the error response format.
