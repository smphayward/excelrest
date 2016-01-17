# FilterCriteria resource type

Represents the filtering criteria applied to a column.


### Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Get FilterCriteria](../api/filtercriteria_get.md) | [FilterCriteria](filtercriteria.md) |Read properties and relationships of filterCriteria object.|
|[Update](../api/filtercriteria_update.md) | [FilterCriteria](filtercriteria.md)	|Update FilterCriteria object. |

### Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|color|string|The HTML color string used to filter cells. Used with "cellColor" and "fontColor" filtering.|
|criterion1|string|The first criterion used to filter data. Used as an operator in the case of "custom" filtering.|
|criterion2|string|The second criterion used to filter data. Only used as an operator in the case of "custom" filtering.|
|values|[object[]](object[].md)|The set of values to be used as part of "values" filtering.|

### Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|dynamicCriteria|[DynamicFilterCriteria](dynamicfiltercriteria.md)|The dynamic criteria from the Excel.DynamicFilterCriteria set to apply on this column. Used with "dynamic" filtering.|
|filterOn|[FilterOn](filteron.md)|The property used by the filter to determine whether the values should stay visible.|
|icon|[Icon](icon.md)|The icon used to filter cells. Used with "icon" filtering.|
|operator|[FilterOperator](filteroperator.md)|The operator used to combine criterion 1 and 2 when using "custom" filtering.|

### JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.filtercriteria"
}-->

```json
{
  "color": "string",
  "criterion1": "string",
  "criterion2": "string",
  "values": {"@odata.type": "microsoft.graph.object[]"}
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "FilterCriteria resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->