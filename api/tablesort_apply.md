# TableSort: apply

Perform a sort operation.
### Prerequisites
The following **scopes** are required to execute this API: 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /workbook/tables(<id|name>)/sort/apply
POST /workbook/bindings(<id>)/table/sort/apply
POST /workbook/worksheets(<id|name>)/tables(<id|name>)/sort/apply

```
### Request headers
| Name       | Type | Description|
|:---------------|:--------|:----------|
| X-Sample-Header  | string  | Sample HTTP header. Update accordingly or remove if not needed|

### Request body
In the request body, provide a JSON object with the following parameters.

| Parameter	   | Type	|Description|
|:---------------|:--------|:----------|
|fields|SortField[]|The list of conditions to sort on.|
|matchCase|boolean|Optional. Whether to have the casing impact string ordering.|
|method|SortMethod|Optional. The ordering method used for Chinese characters.|

### Response
If successful, this method returns `, ` response code. It does not return anything in the response body.

### Example
Here is an example of how to call this API.
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "tablesort_apply"
}-->
```http
POST https://graph.microsoft.com/beta/workbook/tables(<id|name>)/sort/apply
Content-type: application/json
Content-length: 61

{
  "fields": {
  },
  "matchCase": true,
  "method": {
  }
}
```

##### Response
Here is an example of the response. 
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.none"
} -->
```http
HTTP/1.1 200 OK
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "TableSort: apply",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->