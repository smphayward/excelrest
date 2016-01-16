# ChartCollection resource type

A collection of all the chart objects on a worksheet.


### Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[List](../api/chart_list.md) | [Chart](chart.md) collection |Get chart object collection. |
|[Item](../api/chartcollection_item.md)|[Chart](chart.md)|Gets a chart using its name. If there are multiple charts with the same name, the first one will be returned.|
|[Itemat](../api/chartcollection_itemat.md)|[Chart](chart.md)|Gets a chart based on its position in the collection.|
|[Add](../api/chartcollection_add.md)|[Chart](chart.md)|Creates a new chart.|

### Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|count|int|Returns the number of charts in the worksheet. Read-only.|
|items|[Chart[]](chart[].md) collection|A collection of chart objects. Read-only.|

### Relationships
None


### JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.chartcollection"
}-->

```json
{
  "count": 1024,
  "items": [{"@odata.type": "microsoft.graph.Chart[]"}]
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "ChartCollection resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->