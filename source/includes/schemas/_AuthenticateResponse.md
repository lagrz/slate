## AuthenticateResponse

<a name="schemaauthenticateresponse"></a>

```json
{
  "access_token": "string",
  "expires_in": 0,
  "refresh_token": "string",
  "token_type": "string"
}
```

### Properties

Name|Type|Required|Description
---|---|---|---|
access_token|string|true|The access token used in the `Authorization` header for every call in the API
expires_in|integer|true|The time the access_token will expire in seconds.
refresh_token|string|true|Refresh token used by the /token to obtain a new access_token.
token_type|string|true|Token type.
