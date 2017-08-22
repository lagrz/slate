## QuoteResponse

<a name="schemaquoteresponse"></a>

```json
{
  "exchange_rate": 3.2373,
  "fee": 4.99,
  "recipient_receives": 323.73,
  "total": 104.99,
  "amount": 100.0,
  "id": 11559
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
exchange_rate|number|true|FX rate for the service
fee|number|true|Base fee
recipient_receives|number|true|The amount the recipient receives (Fx rate * amount)
total|number|true|The sender total (fee + send amount)
amount|number|true|The amount provided for the quote
id|number|number|Quote id
