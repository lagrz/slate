## POST /token

> Code samples

```shell
# You can also use wget
curl -X post https://api.wirecash.com/sandbox/token \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -d '{"username":"YOUR USERNAME","access_token":"YOUR ACCESS TOKEN", "refresh_token": "YOUR REFRESH TOKEN"}'
```

```http
POST https://api.wirecash.com/sandbox/token HTTP/1.1
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

fetch('https://api.wirecash.com/sandbox/token',
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

result = RestClient.post 'https://api.wirecash.com/sandbox/token',
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

r = requests.post('https://api.wirecash.com/sandbox/token', params={
  'access_token': 'YOUR ACCESS TOKEN',
  'refresh_token': 'YOUR REFRESH TOKEN',
  'username': 'YOUR USERNAME'
}, headers = headers)

print r.json()
```

```java
Response<AuthenticateResponse> response = client.service().refreshToken(
    new RefreshTokenRequest()
        .withUsername("USERNAME")
        .withRefresh_token("REFRESH_TOKEN")
        .withAccess_token("ACCESS_TOKEN")
).execute();
if (response.isSuccessful()) {
    //do something
}
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
