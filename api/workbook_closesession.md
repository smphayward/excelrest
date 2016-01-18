# Workbook: CloseSession

Closes an existing session that is sent along in the HTTP header. 

## HTTP request
```http
POST /workbook/closesession
```

### Request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  |string | Oauth2 authorization code. Required.| 
| Workbook-Session-Id  |string |It is recommended to include the workbook session Id along with the request. Optional.|


## Response
If successful, this method returns a `204 No Content` response code and closes the workbook session.

## Example

### HTTP request
```http
POST /workbook/closesession
```

### Response

```http
HTTP/1.1 204 No Content
```