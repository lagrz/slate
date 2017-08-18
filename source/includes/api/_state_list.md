## GET /state/list

> Code samples

```shell
# You can also use wget
curl -X get https://api.wirecash.com/state/list \
  -H 'Authorization: string' \
  -H 'Accept: application/json'
  -H 'Authorization: YOUR_ACCESS_TOKEN'
```

```http
GET https://api.wirecash.com/dev/state/list HTTP/1.1
Host: api.wirecash.com

Accept: application/json
Authorization: YOUR_ACCESS_TOKEN

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Authorization':'YOUR_ACCESS_TOKEN',
  'Accept':'application/json'
};

fetch('https://api.wirecash.com/dev/state/list',
{
  method: 'GET',

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
  'Authorization' => 'YOUR_ACCESS_TOKEN',
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.wirecash.com/dev/state/list',
  params: {}, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Authorization': 'YOUR_ACCESS_TOKEN',
  'Accept': 'application/json'
}

r = requests.get('https://api.wirecash.com/dev/state/list', params={

}, headers = headers)

print r.json()
```

```java
//Using Unirest http://unirest.io/java.html
Unirest.get("https://api.wirecash.com/dev/state/list")
  .header("Authorization", "YOUR_ACCESS_TOKEN")
  .asJson();
```

```csharp
//some code

```

Returns a list of state name and 2 letter code for every US state where services are available from.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
Authorization|header|string|true|access_token value


> Example responses

```json
{
  "states": [
    {
      "code": "string",
      "name": "string"
    }
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[StateListResponse](#schemastatelistresponse)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The access_token has exipred|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods: Authorization header `access_token`
</aside>
