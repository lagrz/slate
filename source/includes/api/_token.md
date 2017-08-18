## POST /token

> Code samples

```shell
# You can also use wget
curl -X post https://api.wirecash.com/dev/token \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'
  -d '{"username":"YOUR USERNAME","access_token":"YOUR ACCESS TOKEN", "refresh_token": "YOUR REFRESH TOKEN"}'
```

```http
POST https://api.wirecash.com/dev/token HTTP/1.1
Host: api.wirecash.com
Content-Type: application/json
Accept: application/json
{"username":"YOUR USERNAME","access_token":"YOUR ACCESS TOKEN", "refresh_token": "YOUR REFRESH TOKEN"}
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "access_token": "YOUR ACCESS TOKEN",
  "refresh_token": "YOUR REFRESH TOKEN",
  "username": "YOUR USERNAME"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('https://api.wirecash.com/dev/token',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://api.wirecash.com/dev/token',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://api.wirecash.com/dev/token', params={
  'access_token': 'YOUR ACCESS TOKEN',
  'refresh_token': 'YOUR REFRESH TOKEN',
  'username': 'YOUR USERNAME'
}, headers = headers)

print r.json()
```

```java
//Using Unirest http://unirest.io/java.html
HashMap<String, String> requestBody = new HashMap<>();
requestBody.put("username", "YOUR USERNAME");
requestBody.put("refresh_token", "YOUR REFRESH TOKEN");
requestBody.put("access_token", "YOUR ACCESS TOKEN");

Unirest.post("https://api.wirecash.com/dev/authenticate")
  .header("accept", "application/json")        
  .body(requestBody)
  .asJson();
```

```csharp
//some code

```

Used to refresh the `access_token`. The request must be placed in the body in JSON format.

> Body parameter

```json
{
  "access_token": "string",
  "refresh_token": "string",
  "username": "string"
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[RefreshTokenRequest](#schemarefreshtokenrequest)|true|RefreshTokenRequest object in json format


> Example responses

```json
{
  "access_token": "string",
  "expires_in": 0,
  "refresh_token": "string",
  "token_type": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[AuthenticateResponse](#schemaauthenticateresponse)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid data provided|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None
