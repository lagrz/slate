## GET /country/list

> Code samples

```shell
# You can also use wget
curl -X get https://api.wirecash.com/sandbox/country/list \  
  -H 'Accept: application/json' \
  -H 'Authorization: YOUR_ACCESS_TOKEN'
```

```http
GET https://api.wirecash.com/sandbox/country/list HTTP/1.1
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

fetch('https://api.wirecash.com/sandbox/country/list',
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

result = RestClient.get 'https://api.wirecash.com/sandbox/country/list',
  params: {}, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Authorization': 'YOUR_ACCESS_TOKEN',
  'Accept': 'application/json'
}

r = requests.get('https://api.wirecash.com/sandbox/country/list', params={

}, headers = headers)

print r.json()
```

```java
Response<CountryListResponse> response = client.service()
    .getCountryList(authenticateResponse.getAccess_token()).execute();
if(response.isSuccessful()){
    //do something
}
```

```csharp
//some code

```

Gets a list of countries where services offered.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
Authorization|header|string|true|access_token value


> Example responses

```json
{
  "countries": [
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
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[CountryListResponse](#schemacountrylistresponse)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The access_token has exipred|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods: Authorization header `access_token`
</aside>
