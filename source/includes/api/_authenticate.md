## POST /authenticate

> Code samples

```shell
# You can also use wget
curl -X post https://api.wirecash.com/sandbox/authenticate \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -d '{"username":"YOUR USERNAME","password":"YOUR PASSWORD"}'
```

```http
POST https://api.wirecash.com/sandbox/authenticate HTTP/1.1
Host: api.wirecash.com
Content-Type: application/json
Accept: application/json
{"username":"YOUR USERNAME","password":"YOUR PASSWORD"}
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "password": "YOUR USERNAME",
  "username": "YOUR PASSWORD"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('https://api.wirecash.com/sandbox/authenticate',
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

result = RestClient.post 'https://api.wirecash.com/sandbox/authenticate',
  params: {
    'username' => 'YOUR USERNAME',
    'password' => 'YOUR PASSWORD'
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://api.wirecash.com/sandbox/authenticate', params={
  'username': 'YOUR USERNAME',
  'password': 'YOUR PASSWORD'
}, headers = headers)

print r.json()
```

```java
//create the client
WirecashClient client = WirecashClient.newBuilder()
    .developmentBaseUrl().build();
//make an authenticate request with the server
Response<AuthenticateResponse> response = client.service().authenticate(
    new AuthenticateRequest()
            .withUsername("YOUR_USERNAME")
            .withPassword("YOUR_PASSOWRD")).execute();
//verify request was a success first
if(response.isSuccessful()){
    System.out.println(response.body().getAccess_token());
}
```

```csharp
//some code

```

Obtains tokens related to given username and password. The AuthenticateRequest must be in the body of the request in JSON format.

> Body parameter

```json
{
  "password": "string",
  "username": "string"
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[AuthenticateRequest](#schemaauthenticaterequest)|true|Requires the **username** and **password**


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
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid username or password provided.|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None
