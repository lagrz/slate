## QuoteRequest

<a name="schemaquoterequest"></a>

```json
{
  "service_id": 4,
  "currency_symbol": "BRL",
  "amount": 200.0,
  "payer_id": 34
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
service_id|number|true|Service id
currency_symbol|string|true|The 3 letter currency code 
amount|number|true|An amount between the bounds of the limits provided by the service `min_limit` and `max_limit`. The general minimum send amount must be $25 USD or above.
payer_id|number|true|The username provided for API use.
