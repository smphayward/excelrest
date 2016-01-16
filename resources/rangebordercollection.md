# RangeBorderCollection resource type

Represents the border objects that make up range border.


### Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[List](../api/rangeborder_list.md) | [RangeBorder](rangeborder.md) collection |Get rangeBorder object collection. |
|[Item](../api/rangebordercollection_item.md)|[RangeBorder](rangeborder.md)|Gets a border object using its name|
|[Itemat](../api/rangebordercollection_itemat.md)|[RangeBorder](rangeborder.md)|Gets a border object using its index|

### Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|count|int|Number of border objects in the collection. Read-only.|
|items|[RangeBorder[]](rangeborder[].md) collection|A collection of rangeBorder objects. Read-only.|

### Relationships
None


### JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.rangebordercollection"
}-->

```json
{
  "count": 1024,
  "items": [{"@odata.type": "microsoft.graph.RangeBorder[]"}]
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "RangeBorderCollection resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->