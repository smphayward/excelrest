# Get TableColumn

Retrieve the properties and relationships of tablecolumn object.
### Prerequisites
The following **scopes** are required to execute this API: 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /workbook/tables(<id|name>)/columns(<id|name>)
GET /workbook/bindings(<id>)/table/columns(<id|name>)
GET /workbook/worksheets(<id|name>)/tables(<id|name>)/columns(<id|name>)
```
### Optional query parameters
|Name|Value|Description|
|:---------------|:--------|:-------|
|$count|none|The count of related entities can be requested by specifying the $count query option.|
|$expand|string|Comma-separated list of relationships to expand and include in the response. See relationships table of [TableColumn](../resources/tablecolumn.md) object for supported names. |
|$select|string|Comma-separated list of properties to include in the response.|

### Request headers
| Name      |Description|
|:----------|:----------|
| Authorization  | Bearer <code>|
| Workbook-Session-Id  | Workbook session Id that determines if changes are persisted or not. Optional.|

### Request body
Do not supply a request body for this method.
### Response
If successful, this method returns a `200 OK` response code and [TableColumn](../resources/tablecolumn.md) object in the response body.
### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "get_tablecolumn"
}-->
```http
GET https://graph.microsoft.com/beta/me/drive/items/<id>/workbook/tables(<id|name>)/columns(<id|name>)
```
##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.tablecolumn"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 81

{
  "id": 99,
  "name": "name-value",
  "index": 99,
  "values": "values-value"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Get TableColumn",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->