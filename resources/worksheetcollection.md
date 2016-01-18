# WorksheetCollection resource type

Represents a collection of worksheet objects that are part of the workbook.


### Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[List](../api/worksheet_list.md) | [Worksheet](worksheet.md) collection |Get worksheet object collection. |
|[Activeworksheet](../api/worksheetcollection_activeworksheet.md)|[Worksheet](worksheet.md)|Gets the currently active worksheet in the workbook.|
|[Add](../api/worksheetcollection_add.md)|[Worksheet](worksheet.md)|Adds a new worksheet to the workbook. The worksheet will be added at the end of existing worksheets. If you wish to activate the newly added worksheet, call ".activate() on it.|

### Properties
None

### Relationships
None


<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "WorksheetCollection resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->