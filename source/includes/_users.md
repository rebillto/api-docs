#Title

```shell
CURL Request Example

```

```javascript
Node.JS Request Example

```

```ruby
Ruby Request Example

```

```php
PHP Request Example

```

```go
GO Request Example

```

```json
JSON Response Example

```

Some description here.

### Headers

`GET https://api.rebill.to/v1/getToken`

Header | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`
Authorization | Bearer {access_token} | Yes | Access token.

### Parameters

Name | Parameter | Type | Required | Description
--------- | --------- | ----------- | ----------- | -----------
something | QueryString | boolean | No | Something.
something | Path Parameter | boolean | No | Something.

### Body

Attribute | Content | Required | Description
--------- | ----------- | ----------- | -----------
Content-Type | application/json | Yes | Can also be sent as `application/x-www-form-urlencoded`
Authorization | `Basic base64_hash` | Yes | Your username and password in base64.

### Response

Attribute | Content | Always Present | Description
--------- | ----------- | ----------- | -----------
`success` | boolean | Yes | Returns `true` if the performed action was success, otherwise `false`.
`response` | object | Yes | Contains an object with the result of the performed action if success. If an error ocurred, the response object will not exist. Check the error response format.

<div class="divider"></div>