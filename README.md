# Excel REST API

**Note:** _The Excel REST API reference is being made available to provide a preview to the upcoming release. These APIs are not yet released. We look forward to making them available as part of the Microsoft Graph /beta API set._

## Objects 

* [Worksheet](resources/worksheet.md): The Worksheet object is a member of the Worksheets collection. The Worksheets collection contains all the Worksheet objects in a workbook.
	* [Worksheet Collection](resources/worksheetcollection.md): A collection of all the Workbook objects that are part of the workbook. 
* [Range](resources/range.md): Range represents a cell, a row, a column, a selection of cells containing one or more contiguous blocks of cells.  
* [Table](resources/table.md): Represents collection of organized cells designed to make management of the data easy. 
	* [Table Collection](resources/tablecollection.md): A collection of Tables in a workbook or worksheet. 
	* [TableColumn Collection](resources/tablecolumncollection.md): A collection of all the columns in a Table. 
	* [TableRow Collection](resources/tablerowcollection.md): A collection of all the rows in a Table. 
* [Chart](resources/chart.md): Represents a chart object in a workbook, which is a visual representation of underlying data.  
	* [Chart Collection](resources/chartcollection.md): A collection of charts in a workbook or a worksheet	
* [NamedItem](resources/nameditem.md): Represents a defined name for a range of cells or a value. Names can be primitive named objects (as seen in the type below), range object, etc.
  * [NamedItem Collection](resources/nameditemcollection.md): a collection of named items of a workbook.
* [Create Session](api/createsession.md): Create Excel workbook sessions. It is a good practice to create workbook session and pass it along with the request as part of the request header as it allows the server to link the API request to an existing in-memory copy of the file on the server. If a session ID is not provided, the server dynamically creates a session behind the scene. However, this requires additional server side processing and could add to the latency of the response. Session ID has a life span which gets extended with each usage or regresh. Once a session ID has expired, a new session session ID needs to be created. If an expired or invalid session token is provided as part of the request, the API will return an error indicating that the session ID is not valid. 		

## Programming Notes

Following sections provide important programming details related to Excel APIs.

* [Null Input](#null-input)
* [Null Response](#null-response)
* [Blank Input-and-Output](#blank-input-and-output)
* [Unbounded Range](#unbounded-range)
* [Large Range](#large-range)
* [Single Input Copy](#single-input-copy)
* [Throttling](#throttling)
* [Error Messages](#error-messages)

### Null-Input

#### null input in 2-D Array

**`null` input inside 2 dimensional array (for values, number-format, formula) is ignored** in the update API. No update will take place to the intended target when `null` input is sent in values or number-format or formula grid of values.

Example: In order to only update specific parts of the Range such as some cell's Number Format and retain the existing Number Format on other parts of the Range, set desired Number Format where needed and send `null` for the other cells. 

In below set request, only some parts of the Range Number Format is set while retaining the existing Number Format on the remainig part (by passing nulls).

```http
PATCH /Range('Sheet2!$E3:E6')
Content-Type: application/json
Content-Length: <length>

{
  "values":  [
               ["Eurasia", "29.96", "0.25", "15-Feb" ]
           ],
  "numberFormat": [

               [null, null, null, "m/d/yyyy;@"]          
                  ]
}
```
#### null input for a property

**`null` is not a valid single input for the entire property.** e.g., following is not valid as the entire values cannot be set to null or ignored. 

```
 "values" : null, 
```

Following is not valid either as null is not a valid color value. 
```
 "color" : null,
```

### Null-Response

Representation of formatting properties that consists of non-uniform values would result in `null` value to be returned in the response. 

Example: A Range can consist of one of more cells. In cases where the individual cells contained in the Range specified doesn't have uniform formatting values, the range level representation will be undefined. 

```
  "size" : null,
  "color" : null,
```

### Blank-Input-and-Output

Blank values in update requests are treated as instruction to clear or reset the respective property. Blank value is represented by two double-quotes with no space in between. `""`

Example: 
* For `values`, the range value is cleared out. This is same as clearing the contents in the application.
* For `numberFormat`, the number format is set to `General`.
* For `formula` and `formulaLocale`, the formula values are clearned out. 

For read operations, expect to receive blank values if the contents of the cells are blanks.

Blank value is not a valid single input for the entire property. e.g., following is not valid as the entire values cannot be set to null or ignored. 

```
  "values" : "", 
```

For read operatoins, if the cell contains no data or value, then the API returns a blank value. Blank value is represented by two double-quotes with no space in between. `""`.

```
  "values" : [["", "some", "data", "in", "other", "cells", ""]]
```

```
  "formula": [["", "", "=Rand()"]]
```

### Unbounded-Range

#### Read

Unbounded range address contains only column or row identifiers and unspecified row identifier or column identifiers (respectively), such as:

* `C:C`, `A:F`, `A:XFD` (contains unspecified rows)
* `2:2`, `1:4`, `1:1048546` (contains unspecified columns)

When the API makes a request to retrieve an unbounded Range (e.g., `/Range/('C:C')` level properties, the response returned contains `null` for cell level properties such as `values`, `text`, `numberFormat`, `formula`, etc.. Other Range properties such as `address`, `cellCount`, etc. will reflect the unbounded range.

##### Example

Below example requests entire Colum-C. 

<!-- { "blockType": "request", "name": "get-range-unbounded" } -->
```
GET /Range('C:C')
```
##### Response

The API returns Range object that contains `null` for cell level properties. 

<!-- { "blockType": "response", "@odata.type": "Range" } -->
```http
HTTP/1.1 200 OK
Content-Type: application/json
Content-length: <length>

{
  "cellCount": 1048576,
  "columnIndex": 2,
  "rowIndex": 0,
  "values": null,
  "text":  null, 
  "numberFormat": null,
  "formulas":  null,             
  "formulaLocal": null, 
  "address": "$C:$C",
  "addressLocal": "$C:$C"
}
```

Note: Navigation properties `format`, `font`, etc. object will always represent the entire Range requested. 


##### Resquest

<!-- { "blockType": "request", "name": "get-range-background" } -->
```
GET /Range('C:D')/Format/Background
```

##### Response

<!-- { "blockType": "response", "@odata.type": "Background" } -->
```http
HTTP/1.1 200 OK
Content-Type: application/json
Content-length: <length>

{
  "color" : "#DDEFF7",
  "pattern": "None",
  "patternColor" : "#000000"
}
```

#### Write

Setting cell level properties (such as values, numberFormat, etc.) on unbounded Range is **not allowed** as the input request might be too large to handle. 

Example: following is not a valid update request as the requested range is unbounded one. 
```http
PATCH /Range('Sheet2!$A:$E')
Content-Type: application/json
Content-Length: <length>

{
  "values": [
                ...
            ]
}

```

When such a Range is update operation is attempted, the API returns the following an error: 

```http
HTTP/1.1 413 Request Entity Too Large
Content-Type: application/json
Content-length: <length>

{
  "error": {
    "code": "RequestTooLarge",
    "message": "The size of the requested operation exceeds the maximum limit."
  }
}
```

### Large-Range

Large Range implies a Range whose size is too large for a single API call. Many factors such as number of cells or values or number-formats, or formulas, etc. contained in the range can make the response large enough to be unsuitable for API interaction. 

The API makes best attempt to return or write-to the requested data. However, due to the large size involved, API might result in an error condition due to large resource utilization. 

In order to avoid such condition, it is recommended to read or write large Range in multiple smaller range sizes.

### Single-Input-Copy

To support updating a range with same values or number-format or applying same formula across a range, the following convention is used in the set API. In Excel, this behavior is similar to inputting values or formulas to a range in the CTRL+Enter mode. 

API will look for *single cell value* and if the target range dimension doesn't match the input range dimension it will apply the update to the entire range in the CTRL+Enter model with the value or formula provided in the request.

Example: Following request updates selected range with the a text of "Due Date". Note that Range has 20 cells whereas the provided input only has 1 cell value.

```http
PATCH /Range('Sheet2!$E2:E21')
Content-Type: application/json
Content-Length: <length>

{
  "values": [
                  ["Due Date"]          
           ]
}
```

Example: Following request updates selected range with date of 3/11/2015".  

```http
PATCH /Range('Sheet2!$F2:F21')
Content-Type: application/json
Content-Length: <length>

{
  "values": [
                  ["3/11/2015"]          
           ],
  "numberFormat": [
                  ["m/d/yyyy"]          
           ]           
}
```

Example: Following request updates selected range with a formula of that will be applied across in the CTRL+Enter mode.  

```http
PATCH /Range('Sheet2!$H2:H21')
Content-Type: application/json
Content-Length: <length>

{
  "formula": [
                  ["=DAYS(B15,42060)"]          
           ]     
}
```

### Throttling 

Excel uses throttling to maintain optimal performance and reliability of the service. Throttling limits the number of user actions or concurrent calls (by script or code) to prevent overuse of resources.

Though this is less common, certain pattern of API usage such as high frequency requests or high volume requests that increases CPU or memory utilization of the servers beyond limit would likely get you throttled.

When a user exceeds usage limits, Excel service throttles any further requests from that user account for a short period. All user actions are throttled while the throttle is in effect.

API requests while the throttle is in effect will result in below error condition:

```http
HTTP/1.1 429 Too Many Requests
Content-Type: application/json
Content-length: <length>

{
  "error": {
    "code": "ActivityLimitReached",
    "message": "Activity limit has been reached."
  }
}
```

## Error Messages

Errors are returned using an error object that consists of a code and a message. The following table provides a list of possible error conditions that can occur. 

|HTTP status|Error code | Error message |
|:----------|:----------|:--------------|
|400|InvalidArgument |The argument is invalid or missing or has an incorrect format.|
|400|InvalidRequest  |Cannot process the request.|
|400|InvalidReference|This reference is not valid for the current operation.|
|400|InvalidBinding  |This object binding is no longer valid due to previous updates.|
|400|InvalidSelection|The current selection is invalid for this operation.|
|400|UnsupportedOperation|The operation being attempted is not supported.|
|400|RequestAborted|The request was aborted during run time.|
|400|ApiNotAvailable|The requested API is not available.|
|400|InsertDeleteConflict|The insert or delete operation attempted resulted in conflict.|
|400|InvalidOperation|The operation attempted is invalid on the object.|
|401|Unauthenticated |Required authentication information is either missing or invalid.|
|403|AccessDenied |You cannot perform the requested operation.|
|404|ItemNotFound |The requested resource doesn't exist.|
|409|Conflict |Request could not be processed because of conflict.|
|409|ItemAlreadyExists|The resource being created already exists.|
|429|ActivityLimitReached|Activity limit has been reached.|
|500|GeneralException|There was an internal error while processing the request.|
|501|NotImplemented  |The requested feature isn't implemented.|
|503|ServiceNotAvailable|The service is unavailable.|