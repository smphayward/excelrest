# Update filter

Update the properties of filter object.
### Prerequisites
The following **scopes** are required to execute this API: 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http

```
### Optional request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| X-Sample-Header  | string  | Sample HTTP header. Update accordingly or remove if not needed|

### Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|ascending|bool|Represents the current conditions used to last sort the table.|
|color|string|Represents the current conditions used to last sort the table.|
|dataOption|SortDataOption|Represents the current conditions used to last sort the table.|
|icon|Icon|Represents the current conditions used to last sort the table.|
|key|int|Represents the current conditions used to last sort the table.|
|sortOn|SortOn|Represents the current conditions used to last sort the table.|

### Response
If successful, this method returns a `200 OK` response code and updated [Filter](../resources/filter.md) object in the response body.
### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_filter"
}-->
```http

Content-type: application/json
Content-length: 62

{
  "key": 99,
  "ascending": true,
  "color": "color-value"
}
```
##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.filter"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 62

{
  "key": 99,
  "ascending": true,
  "color": "color-value"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update filter",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->