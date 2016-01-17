# Update filterdatetime

Update the properties of filterdatetime object.
### Prerequisites
The following **scopes** are required to execute this API: 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http

```
### Optional request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  | string  | Bearer <code>|

### Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|date|string|The date in ISO8601 format used to filter data.|
|specificity|string|How specific the date should be used to keep data. For example, if the date is 2005-04-02 and the specifity is set to "month", the filter operation will keep all rows with a date in the month of april 2009. Possible values are: `Year`, `Monday`, `Day`, `Hour`, `Minute`, `Second`.|

### Response
If successful, this method returns a `200 OK` response code and updated [FilterDatetime](../resources/filterdatetime.md) object in the response body.
### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_filterdatetime"
}-->
```http

Content-type: application/json
Content-length: 64

{
  "date": "date-value",
  "specificity": "specificity-value"
}
```
##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.filterdatetime"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 64

{
  "date": "date-value",
  "specificity": "specificity-value"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update filterdatetime",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->