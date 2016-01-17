# Update worksheetprotectionoptions

Update the properties of worksheetprotectionoptions object.
### Prerequisites
The following **scopes** are required to execute this API: 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
PATCH /workbook/worksheets(<id|name>)/protection/options
```
### Optional request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| X-Sample-Header  | string  | Sample HTTP header. Update accordingly or remove if not needed|

### Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|allowAutoFilter|boolean|Represents the worksheet protection option of allowing using auto filter feature.|
|allowDeleteColumns|boolean|Represents the worksheet protection option of allowing deleting columns.|
|allowDeleteRows|boolean|Represents the worksheet protection option of allowing deleting rows.|
|allowFormatCells|boolean|Represents the worksheet protection option of allowing formatting cells.|
|allowFormatColumns|boolean|Represents the worksheet protection option of allowing formatting columns.|
|allowFormatRows|boolean|Represents the worksheet protection option of allowing formatting rows.|
|allowInsertColumns|boolean|Represents the worksheet protection option of allowing inserting columns.|
|allowInsertHyperlinks|boolean|Represents the worksheet protection option of allowing inserting hyperlinks.|
|allowInsertRows|boolean|Represents the worksheet protection option of allowing inserting rows.|
|allowPivotTables|boolean|Represents the worksheet protection option of allowing using pivot table feature.|
|allowSort|boolean|Represents the worksheet protection option of allowing using sort feature.|

### Response
If successful, this method returns a `200 OK` response code and updated [WorksheetProtectionOptions](../resources/worksheetprotectionoptions.md) object in the response body.
### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_worksheetprotectionoptions"
}-->
```http
PATCH https://graph.microsoft.com/beta/workbook/worksheets(<id|name>)/protection/options
Content-type: application/json
Content-length: 177

{
  "allowFormatCells": true,
  "allowFormatColumns": true,
  "allowFormatRows": true,
  "allowInsertColumns": true,
  "allowInsertRows": true,
  "allowInsertHyperlinks": true
}
```
##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.worksheetprotectionoptions"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 177

{
  "allowFormatCells": true,
  "allowFormatColumns": true,
  "allowFormatRows": true,
  "allowInsertColumns": true,
  "allowInsertRows": true,
  "allowInsertHyperlinks": true
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update worksheetprotectionoptions",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->