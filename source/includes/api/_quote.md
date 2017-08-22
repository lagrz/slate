## GET /quote

> Code samples

```shell
# You can also use wget
curl -X get https://api.wirecash.com/quote \
  -H 'Authorization: string' \
  -H 'Accept: application/json'
  -H 'Authorization: YOUR_ACCESS_TOKEN'
  -d '{"amount":25.0,"currency_symbol":"BRL", "payer_id": 34, "service_id": 2541}'
```

```http
GET https://api.wirecash.com/sandbox/quote HTTP/1.1
Host: api.wirecash.com

Accept: application/json
Authorization: YOUR_ACCESS_TOKEN
{"amount":25.0,"currency_symbol":"BRL", "payer_id": 34, "service_id": 2541}
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{"amount":25.0,"currency_symbol":"BRL", "payer_id": 34, "service_id": 2541}';
const headers = {
  'Authorization':'YOUR_ACCESS_TOKEN',
  'Accept':'application/json'
};

fetch('https://api.wirecash.com/sandbox/quote',
{
  method: 'GET',
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
  'Authorization' => 'YOUR_ACCESS_TOKEN',
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.wirecash.com/sandbox/quote',
  params: {
      'amount' => 25,
      'currency_symbol' => 'BRL',
      'payer_id' => 34,
      'service_id' => 2541      
    }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Authorization': 'YOUR_ACCESS_TOKEN',
  'Accept': 'application/json'
}

r = requests.get('https://api.wirecash.com/sandbox/quote', params={
 'amount': 25.0,
 'currency_symbol': 'BRL',
 'payer_id': 34,
 'service_id': 2541
}, headers = headers)

print r.json()
```

```java
Response<QuoteRequest> response = client.service().getQuote(
    new QuoteRequest()
            .withServiceId(2451L)
            .withCurrencySymbol("BRL")
            .withAmount(250.0), 
    authenticateResponse.getAccess_token()
).execute();
if(response.isSuccessful()){
    //do something
}
```

```csharp
//some code

```

Returns a quote for the given service and amount.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
Authorization|header|string|true|access_token value
body|body|[QuoteRequest](#schemaquoterequest)|true|All fields are required except `payer_id` as some services don't provide it. If no payers are available send `0` for `payer_id`.

> Example responses

```json
{
  "exchange_rate": 3.2373,
  "fee": 4.99,
  "recipient_receives": 323.73,
  "total": 104.99,
  "amount": 100,
  "id": 11559
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[QuoteResponse](#schemaquoteresponse)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Failed validation|None
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The access_token has exipred|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods: Authorization header `access_token`
</aside>
