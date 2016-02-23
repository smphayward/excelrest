# TableColumnCollection: Item

Gets a column object by Name or ID.
### Prerequisites
The following **scopes** are required to execute this API: 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /workbook/tables(<id|name>)/columns/Item
POST /workbook/bindings(<id>)/table/columns/Item
POST /workbook/worksheets(<id|name>)/tables(<id|name>)/columns/Item

```
### Request headers
| Name       | Description|
|:---------------|:----------|
| Authorization  | Bearer <code>|
| Workbook-Session-Id  | Workbook session Id that determines if changes are persisted or not. Optional.|

### Request body
In the request body, provide a JSON object with the following parameters.

| Parameter	   | Type	|Description|
|:---------------|:--------|:----------|
|key|number or string| Column Name or ID.|

### Response
If successful, this method returns `200, OK` response code and [TableColumn](../resources/tablecolumn.md) object in the response body.

### Example
Here is an example of how to call this API.
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "tablecolumncollection_item"
}-->
```http
POST https://graph.microsoft.com/beta/me/drive/items/<id>/workbook/tables(<id|name>)/columns/Item
Content-type: application/json
Content-length: 18

{
  "key": {
  }
}
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
  "description": "TableColumnCollection: Item",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->