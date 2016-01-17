# RangeReference resource type

Represents a string reference of the form SheetName!A1:B5, or a global or local named range


### Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Get RangeReference](../api/rangereference_get.md) | [RangeReference](rangereference.md) |Read properties and relationships of rangeReference object.|
|[Update](../api/rangereference_update.md) | [RangeReference](rangereference.md)	|Update RangeReference object. |

### Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|address|string|The worksheet containing the current range.|

### Relationships
None


### JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.rangereference"
}-->

```json
{
  "address": "string"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "RangeReference resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->