## Service

<a name="schemaservice"></a>

```json
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
```

### Properties

Name|Type|Required|Description
---|---|---|---|
delivery_type|string|false|Type of delivery method this service provides
fee|integer|false|Base fee for this particular service.
id|integer|false|Id of service.
max_limit|integer|false|The maximum amount the user can send with this service.
min_limit|integer|false|The minimum amount the user needs to send with this service..
exchange_rate|[[ExchangeRate](#schemaexchangerate)]|false|ExchangeRate Object
payers|[[Payer](#schemapayer)]|false|Payer Object
