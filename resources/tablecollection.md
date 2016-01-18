# TableCollection resource type

Represents a collection of all the tables that are part of the workbook.


### Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[List](../api/table_list.md) | [Table](table.md) collection |Get table object collection. |
|[Itemat](../api/tablecollection_itemat.md)|[Table](table.md)|Gets a table based on its position in the collection.|
|[Add](../api/tablecollection_add.md)|[Table](table.md)|Create a new table. The range source address determines the worksheet under which the table will be added. If the table cannot be added (e.g., because the address is invalid, or the table would overlap with another table), an error will be thrown.|

### Properties
None

### Relationships
None


<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "TableCollection resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->