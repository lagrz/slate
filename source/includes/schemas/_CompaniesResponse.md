## CompaniesResponse

<a name="schemacompaniesresponse"></a>

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

### Properties

Name|Type|Required|Description
---|---|---|---|
companies|[[Company](#schemacompany)]|false|An array of Company Objects
