# SortField resource type

Represents a condition in a sorting operation.


### Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Get SortField](../api/sortfield_get.md) | [SortField](sortfield.md) |Read properties and relationships of sortField object.|
|[Update](../api/sortfield_update.md) | [SortField](sortfield.md)	|Update SortField object. |

### Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|ascending|boolean|Represents whether the sorting is done in an ascending fashion.|
|color|string|Represents the color that is the target of the condition if the sorting is on font or cell color.|
|key|int|Represents the column (or row, depending on the sort orientation) that the condition is on. Represented as an offset from the first column (or row).|

### Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|dataOption|[SortDataOption](sortdataoption.md)|Represents additional sorting options for this field.|
|icon|[Icon](icon.md)|Represents the icon that is the target of the condition if the sorting is on the cell's icon.|
|sortOn|[SortOn](sorton.md)|Represents the type of sorting of this condition.|

### JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.sortfield"
}-->

```json
{
  "ascending": true,
  "color": "string",
  "key": 1024
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "SortField resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->