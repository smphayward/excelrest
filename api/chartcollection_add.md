# ChartCollection: add

Creates a new chart.
### Prerequisites
The following **scopes** are required to execute this API: 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /workbook/worksheets(<id|name>)/charts/add

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
|type|string|Represents the type of a chart.  Possible values are: `ColumnClustered`, `ColumnStacked`, `ColumnStacked100`, `BarClustered`, `BarStacked`, `BarStacked100`, `LineStacked`, `LineStacked100`, `LineMarkers`, `LineMarkersStacked`, `LineMarkersStacked100`, `PieOfPie`, `etc.`.|
|sourceData|string|The Range object corresponding to the source data.|
|seriesBy|string|Optional. Specifies the way columns or rows are used as data series on the chart.  Possible values are: `Auto`, `Columns`, `Rows`.|

### Response
If successful, this method returns `200, OK` response code and [Chart](../resources/chart.md) object in the response body.

### Example
Here is an example of how to call this API.
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "chartcollection_add"
}-->
```http
POST https://graph.microsoft.com/beta/me/drive/items/<id>/workbook/worksheets(<id|name>)/charts/add
Content-type: application/json
Content-length: 94

{
  "type": "type-value",
  "sourceData": "sourceData-value",
  "seriesBy": "seriesBy-value"
}
```

##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.chart"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 52

{
  "id": "id-value",
  "height": 99,
  "left": 99
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "ChartCollection: add",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->