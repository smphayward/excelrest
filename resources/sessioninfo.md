# SessionInfo resource type

Represents workbook session.

### Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|string|Session id. Read-only.|
|persistChanges|boolean|Determines if the changes made during the session gets persisted to the workbook. Read-only.|

### JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.sessionInfo"
}-->

```json
{
  "id": "string",
  "persistChanges": true
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": SessionInfo resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->