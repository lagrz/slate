## GET /state/{state_code}/country/{country_code}

> Code samples

```shell
# You can also use wget
curl -X get https://api.wirecash.com/sandbox/state/CA/country/BR \  
  -H 'Accept: application/json' \
  -H 'Authorization: YOUR_ACCESS_TOKEN'
```

```http
GET https://api.wirecash.com/sandbox/state/CA/country/BR HTTP/1.1
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

fetch('https://api.wirecash.com/sandbox/state/CA/country/BR',
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

result = RestClient.get 'https://api.wirecash.com/sandbox/state/CA/country/BR',
  params: {}, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Authorization': 'YOUR_ACCESS_TOKEN',
  'Accept': 'application/json'
}

r = requests.get('https://api.wirecash.com/sandbox/state/CA/country/BR', params={

}, headers = headers)

print r.json()
```

```java
Response<CompaniesResponse> response = client.service()
    .getServicesByStateCountry(
        "CA","BR",
        authenticateResponse.getAccess_token())
    .execute();
if (response.isSuccessful()) {
    //do something
}
```

```csharp
//some code

```

Returns a list of Companies and services narrowed down by US State of origin, and Country sending to. All services are sorted by country.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
amount|query|string|false|Returns the results `fee` based on the given amount, defaults to $200
country_code|path|string|true|Country code to narrow search results by.
state_code|path|string|true|State code to narrow search results by.
Authorization|header|string|true|access_token value


> Example responses

```json
{
  "companies": [
    {
      "company_logo": "string",
      "company_name": "string",
      "description": "string",
      "id": 0,
      "rating": 0,
      "services": {
        "GH": [
          {
            "delivery_type": "string",
            "exchange_rate": [
              {
                "currency_id": 0,
                "currency_name": "string",
                "currency_symbol": "string",
                "exchange_rate": "string"
              }
            ],
            "fee": 0,
            "id": 0,
            "max_limit": 0,
            "min_limit": 0,
            "payers": [
              {
                "id": 0,
                "payer_logo": "string",
                "payer_name": "string"
              }
            ]
          }
        ],
        "MX": [
          {
            "delivery_type": "string",
            "exchange_rate": [
              {
                "currency_id": 0,
                "currency_name": "string",
                "currency_symbol": "string",
                "exchange_rate": "string"
              }
            ],
            "fee": 0,
            "id": 0,
            "max_limit": 0,
            "min_limit": 0,
            "payers": [
              {
                "id": 0,
                "payer_logo": "string",
                "payer_name": "string"
              }
            ]
          }
        ]
      }
    }
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[CompaniesResponse](#schemacompaniesresponse)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid data provided.|None
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The access_token has exipred|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods: Authorization header `access_token`
</aside>
