# Workbook: CreateSession

Create a new Excel workbook session token.
## HTTP request
```http
POST /workbook/createsession
```

### Request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  |string | Oauth2 authorization code. Required.| 

## Optional Request body

Provide JSON object with the following properties

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|saveChanges | Boolean | If `true`, the changes made to the document during the session is saved. If `false`, the changes are not perssited to the document. Default is `true`.|

## Response
If successful, this method returns a `200 OK` response code and a [SessionInfo](../resources/sessioninfo.md) is retruned in the response body.

## Example

### HTTP request
```http
POST /workbook/createsession
Content-type: application/json
Content-length: 22

{
  "saveChanges": true
}

```

### Response

```http
HTTP/1.1 201 Created
Content-type: application/json

{
  
  "id": "id-value",
  "persistChanges": true 
}
```