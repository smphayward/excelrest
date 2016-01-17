# Icon resource type

Represents a cell icon.


### Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Get Icon](../api/icon_get.md) | [Icon](icon.md) |Read properties and relationships of icon object.|
|[Update](../api/icon_update.md) | [Icon](icon.md)	|Update Icon object. |

### Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|index|int|Represents the index of the icon in the given set.|

### Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|set|[IconSet](iconset.md)|Represents the set that the icon is part of.|

### JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.icon"
}-->

```json
{
  "index": 1024
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Icon resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->