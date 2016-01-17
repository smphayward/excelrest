# Update sortfield

Update the properties of sortfield object.
### Prerequisites
The following **scopes** are required to execute this API: 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
PATCH /workbook/tables(<id|name>)/sort/fields
PATCH /workbook/bindings(<id>)/table/sort/fields
PATCH /workbook/worksheets(<id|name>)/tables(<id|name>)/sort/fields
```
### Optional request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  | string  | Bearer <code>|

### Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|ascending|boolean|Represents whether the sorting is done in an ascending fashion.|
|color|string|Represents the color that is the target of the condition if the sorting is on font or cell color.|
|dataOption|string|Represents additional sorting options for this field. Possible values are: `Normal`, `TextAsNumber`.|
|icon|Icon|Represents the icon that is the target of the condition if the sorting is on the cell's icon.|
|key|int|Represents the column (or row, depending on the sort orientation) that the condition is on. Represented as an offset from the first column (or row).|
|sortOn|string|Represents the type of sorting of this condition. Possible values are: `Value`, `CellColor`, `FontColor`, `Icon`.|

### Response
If successful, this method returns a `200 OK` response code and updated [SortField](../resources/sortfield.md) object in the response body.
### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_sortfield"
}-->
```http
PATCH https://graph.microsoft.com/beta/workbook/tables(<id|name>)/sort/fields
Content-type: application/json
Content-length: 126

{
  "key": 99,
  "sortOn": "sortOn-value",
  "ascending": true,
  "color": "color-value",
  "dataOption": "dataOption-value"
}
```
##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.sortfield"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 126

{
  "key": 99,
  "sortOn": "sortOn-value",
  "ascending": true,
  "color": "color-value",
  "dataOption": "dataOption-value"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update sortfield",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->