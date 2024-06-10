## Retrieve Data

This section outlines the various GET APIs available for fetching data from different tables. Each API provides the capability to retrieve specific data based on provided parameters. Pagination support is available for managing large datasets effectively.The user can pass the set of parameters of same or different filter options at once .

### 1. Attribute Type Table 

This section outlines the process of retrieving data from the Attribute Type table using the dedicated API endpoint. The endpoint facilitates the retrieval of all data from the Attribute Type table or enables the selection of specific information by including Attribute Ids and Attribute Types. Additionally, the Attribute Type endpoint supports pagination to effectively manage larger datasets.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/attributetype' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/attributetype");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 3,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 1346,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
            "attributeTypeId": "number",
            "attributeType": "string",
            "dataTypeId": "number",
            "dataTypeSize": "number",
            "dataTypePrecision": "number",
            "dataTypeFilter": "string",
            "readonlyInd": "string",
            "searchableInd": "string",
            "remoteInd": "string",
            "defaultValue": "string",
            "alwaysEvaluateDefaultInd": "string",
            "displayCondition": "string",
            "disabledCondition": "string",
            "validationCondition": "string",
            "validationErrorText": "string",
            "viewColumnName": "string",
            "activeDate": "2011-01-01T00:00:00",
            "inactiveDate": "2011-01-01T00:00:00",
            "lastModifiedDate": "2020-10-08T13:35:31",
            "externalIdentifier": "string",
            "comments": "string",
            "refId": "string"
        }
	]
}
```

**API Endpoints**

`GET` /api/v1/attributetype

**Query parameters**

Attribute | Type | Description 
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch. 
PageSize | int | The number of results per page
attributeTypeIds | int | Attribute ID is one of the filter parameter is a integer data type
attributeTypes | string | Attribute Types is for the project detail type

### 2. Compound Table

This section guides you through the process of fetching data from the Compound table using the dedicated API endpoint. The endpoint offers the flexibility to retrieve all data from the Compound table or selectively acquire information by including Compound Ids, Compound Type Ids, Compound Status Ids, Compound Names, External Identifiers, or CAS Numbers. Additionally, the Compound endpoint is equipped with pagination capabilities to facilitate efficient management of substantial datasets.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/compound' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/compound");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 3,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 1346,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
            "compoundId": "number",
            "compoundName": "string",
            "compoundTypeId": "number",
            "compoundStatusId": "number",
            "activeDate": "2011-07-04T17:42:43",
            "description": "string",
            "alternateNames": "string",
            "cas": "string",
            "formula": "string",
            "molecularWeight": "number",
            "vpMolecularWeight": "number",
            "vp40": "number",
            "vp50": "number",
            "vp60": "number",
            "vp70": "number",
            "vp80": "number",
            "vp90": "number",
            "vp100": "number",
            "vpCoefA": "number",
            "vpCoefB": "number",
            "vpCoefC": "number",
            "vp2A": "number",
            "vp2B": "number",
            "reid": "number",
            "astmSlope": "number",
            "vpA": "number",
            "vpB": "number",
            "vpXMin": "number",
            "vpXMax": "number",
            "density": "number",
            "specificGravity": "number",
            "supplier": "string",
            "manufacturerId": "number",
            "epaTanksCategory": "string",
            "epaTanksId": "number",
            "inactiveDate": "string",
            "sortOrder": "number",
            "lastModifiedDate": "2020-09-10T10:01:19",
            "externalIdentifier": "string",
            "comments": "string",
            "refId": "string"
        }
	]	
}
```

**API Endpoints**

`GET` /api/v1/compound

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
compoundIds | int | Compound ID is one of the unique identifier for this compound record 
compoundTypeIds | int | Compound Type Ids is the associated compound type and is a second filter parameter option
compoundstatusIds | int | Compound Status Ids is associated with compound status
compoundNames | string | Compound Names The name of the compound which is a string type data and is one among the parameter for filter option
externalIdentifier | int | External Identifiers is a unique identifier for this record to an external data system
cas | string | CAS Number is a Chemical Abstract Service number for the compound 

### 3. Emission Category Table

This section elaborates on how to obtain data from the Emission Category table using the designated API endpoint. The endpoint allows you to retrieve all data from the Emission Category table or selectively acquire information by providing the Emission Category ID. Moreover, the Emission Category endpoint features pagination to facilitate efficient management of substantial datasets.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/emissioncategory' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/emissioncategory");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 3,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 1346,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
		   {
            "emissionCategoryId": "number",
            "emissionCategory": "string",
            "sortOrder": "number",
            "lastModifiedDate": "2022-11-22T08:03:51",
            "externalIdentifier": "string",
            "comments": "string",
            "refId": "string"
        }
	]
}
```

**API Endpoints**

`GET` /api/v1/emissioncategory

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
emissionCategoryIds | int | Emission Category ID is one of the unique identifier for this emission category record and is one of the filter option provided for Emission Category
emissionCategoryTypes | string | Emission Category Types is for the project to emission category detail types

### 4. Emission Factor Table

This section elaborates on how to obtain data from the Emission Factor table using the designated API endpoint. The endpoint allows you to retrieve all data from the Emission Factor table or You can optionally fetch specific data by including the emission factor Ids, emission factor names, emission type Ids, emission category Ids, unit Ids, compound Ids, equipment Ids, last modified start date and last modified end date. The Emission Factor endpoint supports pagination.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/emissionfactor' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/emissionfactor");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 1,
    "currentPageSize": 10,
    "maxAPIPageSize": 500,
    "totalCount": 1,
    "hasPrevious": false,
    "hasNext": false,
    "data": [
        {
            "emissionFactorId": "number",
            "emissionFactor": "number",
            "equipmentId": "number",
            "emissionTypeId": "number",
            "emissionCategoryId": "number",
            "compoundId": "number",
            "emissionFactorName": "string",
            "unitId": "number",
            "lastModifiedDate": "2018-08-22T15:33:44",
            "externalIdentifier": "string",
            "comments": "string",
            "activeDate": "2014-01-01T00:00:00",
            "inactiveDate": "2014-01-01T00:00:00",
            "primaryInd": "string",
            "reportableInd": "string",
            "readOnlyInd": "string",
            "dataLockTypeId": "number"
        }
    ]
}
```

**API Endpoints**

`GET` /api/v1/emissionfactor

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
emissionFactorIDs | int | Emission Factor Ids are unique identifier for this Emission Factor record
emissionFactorNames | string | Emission Factor Names are one of the filter option and the parameter is for the names of the Emission Factors
emissionTypeIds | int | The unique identifier of the associated emission type
emissionCategoryIds | int | The unique identifier of the associated emission category
unitIds | int | The unique identifier of the associated unit
compoundIds | int | Compound ID is one of the unique identifier for this compound record  
equipmentIds | int | The unique identifier of the associated equipment
lastModifiedStartDate | string | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"
lastModifiedEndDate | string | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"

### 5. Emission Type Table

This section guides you through the process of fetching data from the Emission Type table using the dedicated API endpoint. The endpoint enables you to retrieve data from the entire Emission Type table or selectively obtain information by including Emission Type Ids. Additionally, the Emission Type endpoint is equipped with pagination capabilities to facilitate the handling of extensive datasets.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/emissiontype' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/emissiontype");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 3,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 1346,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
          {
            "emissionTypeId": "number",
            "emissionType": "string",
            "sortOrder": "number",
            "lastModifiedDate": "2022-11-22T08:03:41",
            "externalIdentifier": "string",
            "comments": "string",
            "refId": "string"
        }
	]
}
```

**API Endpoints**

`GET` /api/v1/emissiontype

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
emissionTypeIds | int | Emission Type ID is one of the type of emissions and is the one of the filter option provided for Emission Type
emissionTypes | string | Emission Types is for the project to emission detail types


### 6. Equipment Table

This section provides guidance on retrieving data from the Equipment table using the designated API endpoint. The endpoint allows you to retrieve all data from the Equipment table or specify specific data based on equipment Ids. Additionally, the Equipment endpoint offers pagination support to facilitate the handling of substantial datasets.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/equipment' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/equipment");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 3,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 1346,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
            "equipmentId": "number",
            "areaId": "number",
            "facilityId": "number",
            "equipmentTypeId": "number",
            "sourceName": "string",
            "equipmentStatusId": "number",
            "modelId": "number",
            "ownershipId": "number",
            "ownerId": "number",
            "serialNumber": "string",
            "manufactureDate": "2013-09-03T00:00:00",
            "internalName": "string",
            "alternateName": "string",
            "design": "string",
            "originalSurveyDate": "2022-12-12T15:43:07",
            "activeDate": "2013-09-03T00:00:00",
            "inactiveDate": "2022-12-12T15:43:07",
            "dataLockTypeId": "number",
            "lastModifiedDate": "2022-12-12T15:43:07",
            "externalIdentifier": "string",
            "comments": "string"
        }
	]
}

```

**API Endpoints**

`GET` /api/v1/equipment

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
equipmentIds | int | Equipment ID is one of the unique identifier for this equipment record
equipmentTypeIds | int | Equipment Type ID is one of the unique identifier for this equipment type record
equipmentStatusIds | int | Equipment Status ID is one of the unique identifier for this equipment status record
facilityIds | int | Facility ID is one of the unique identifier for this equipment status record
sourceNames | string | Source Names is one of the unique identifier for this equipment record
internalNames | string | Internal Names is one of the unique identifier for this equipment record
alternateNames | string | Alternate Names is one of the unique identifier for this equipment record
lastModifiedStartDate | string | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"
lastModifiedEndDate | string | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"


### 7. Equipment Attribute Table

All data from the Equipment Attribute table will be returned from the endpoint below. You can optionally fetch specific data by including the facility attribute Ids, facility names, emission type Ids, facility type Ids, unit Ids, equipment Ids, last modified start date and last modified end date. The facility attribute endpoint supports pagination.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/equipmentattribute' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/equipmentattribute");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 1,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 337,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
            "equipmentAttributeId": "number",
            "equipmentId": "number",
            "attributeTypeId": "number",
            "equipmentAttribute":"string",
            "dataLockTypeId": "number",
            "lastModifiedDate": "datetime",
            "externalIdentifier": "string",
            "comments":"string"
        }
	]
}

```

**API Endpoints**

`GET` /api/v1/equipmentattribute

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
equipmentAttributeIds | int | EquipmentAttributeId one of the unique identifier for this Equipment record.
equipmentIds | int |  EquipmentId must be numeric.
attributetypeIds | int | AttributeTypeId must be numeric.
equipmentattributes | string | Equipment Attribute is one of the filter option and the parameter is for the Equipment Attribute Type 
lastModifiedStartDate | string | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"
lastModifiedEndDate | string | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"


### 8. Equipment Status Table

All data from the Equipment Status table will be returned from the endpoint below. You can optionally fetch specific data by including the equipment status ID and equipment status value. The Equipment Status endpoint supports pagination.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/equipmentstatus' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/equipmentstatus");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 3,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 1346,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
		{
            "equipmentStatusId": "number",
            "equipmentStatus": "string",
            "colorId": "number",
            "sortOrder": "number",
            "lastModifiedDate": "2022-11-22T07:46:46",
            "externalIdentifier": "string",
            "comments": "string"
        }
	]
}
```

**API Endpoints**

`GET` /api/v1/equipmentstatus

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
equipmentStatusIds | int | Equipment Status ID is one of the unique identifier for this equipment status record
equipmentStatus | string | Equipment Status is one of the identifier for the status of the equipment



### 9. Equipment Type Table

All data from the Equipment Type table will be returned from the endpoint below. You can optionally fetch specific data by including the equipment type ID and equipment types value. The Equipment type endpoint supports pagination.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/equipmenttype' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/equipmenttype");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 3,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 1346,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
		        {
            "equipmentTypeId": "number",
            "equipmentType": "string",
            "visibleInd": "string",
            "equipmentAttributesInd": "string",
            "emissionCalculationsInd": "string",
            "containmentInd": "string",
            "geometryInd": "string",
            "emissionFactorsInd": "string",
            "sampleLocationsInd": "string",
            "equipmentAssociationsInd": "string",
            "facilityAssociationsInd": "string",
            "locationInformationInd": "string",
            "fuelUseInd": "string",
            "peopleAssociationsInd": "string",
            "serviceScheduleInd": "string",
            "serviceHistoryInd": "string",
            "operationalDataCollectnInd": "string",
            "pteOperationalDataInd": "string",
            "scheduleInd": "string",
            "correspondenceInd": "string",
            "requirementsInd": "string",
            "fileAttachmentsInd": "string",
            "viewName": "string",
            "sortOrder": "number",
            "lastModifiedDate": "2022-04-14T09:15:47",
            "externalIdentifier": "string",
            "comments": "string",
            "refId": "string"
        }
	]
}
```

**API Endpoints**

`GET` /api/v1/equipmenttype

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
equipmentTypeIds | int | Equipment Type ID is one of the unique identifier for this equipment type record
equipmentTypes | string | Equipment Types is one of the filter option and the parameter is for the type of the equipment


### 10. Facility Table

All data from the Facility table will be returned from the endpoint below. You can optionally fetch specific data by including the facility Ids, facility names, emission type Ids, facility type Ids, facility status Ids, county Ids, last modified start date and last modified end date. The facility endpoint supports pagination.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/facility' };
request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/facility");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 1,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 337,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
       {
            "facilityId": "number",
            "facilityName": "string",
            "areaId": "number",
            "facilityTypeId": "number",
            "facilityStatusId": "number",
            "sortOrder": "number",
            "facilityOwnershipId": "number",
            "facilityOwnerId": "number",
            "landOwnershipId": "number",
            "landOwnerId": "number",
            "operatorId": "number",
            "countryId": "number",
            "countyId": "number",
            "offshoreBlockId": "number",
            "meteorologicalId": "number",
            "businessEntityId": "number",
            "businessUnitId": "number",
            "alternateName": "string",
            "purchaseDate": "2023-06-25T04:00:00Z",
            "previousOwnerId": "number",
            "soldDate": "2023-06-25T04:00:00Z",
            "soldToId": "number",
            "activeDate": "2023-06-25T04:00:00Z",
            "inactiveDate": "2023-06-25T04:00:00Z",
            "dataLockTypeId": "number",
            "lastModifiedDate": "2023-06-25T04:00:00Z",
            "externalIdentifier": "string",
            "comments": "string"
        }
	]
}

```

**API Endpoints**

`GET` /api/v1/facility

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
facilityIds | int | Facility ID is one of the unique identifier for this Facility record
facilityTypeIds | int | Facility Type ID is one of the unique identifier for this Facility record
facilityStatusIds | int | Facility Status ID is one of the unique identifier for this Facility record
countyIds | int | County ID is one of the unique identifier for this Facility record
facilityNames | string | Facility Name is the unique identifier of the associated facility type
alternateNames | string | Alternate Name is the unique identifier of the associated facility 
externalidentifier | string | External Identifier a unique identifier for this record to an external data system
areaIds | int | Area ID is one of the unique identifier for this Facility record to determine the region 
lastModifiedStartDate | string | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"
lastModifiedEndDate | string | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"


### 11. Facility Attribute Table

All data from the Facility Attribute table will be returned from the endpoint below. You can optionally fetch specific data by including the facility attribute Ids, facility names, emission type Ids, facility type Ids, facility attribute and last modified end date. The facility attribute endpoint supports pagination.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/facilityattribute' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/facilityattribute");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 1,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 337,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
          "facilityAttributeId": "number",
          "facilityId": "number",
          "attributeTypeId": "number",
          "facilityAttribute":"string",
          "dataLockTypeId": "number",
          "lastModifiedDate": "2023-03-30T07:27:06.295Z",
          "externalIdentifier": "string",
          "comments":"string"
        }
	]
}

```

**API Endpoints**

`GET` /api/v1/facilityattribute

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
facilityAttributeIds | int | Facility ID is one of the unique identifier for this Facility record
facilityIds | int | Facility Name is the unique identifier of the associated facility type
attributetypeIds | int | Attribute Type ID is the unique identifier of the associated attribute type
facilityattributes | string | Facility Attribute is one of the filter option and the parameter is for the Facility Attribute Type 
datalocktypeIds | int | Data Lock Type ID the unique identifier of the associated data lock type
lastModifiedStartDate | string | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"
lastModifiedEndDate | string | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"
externalidentifier | string | External Identifier a unique identifier for this record to an external data system
comments | string | Comments any comments associated with this record


### 12. Operation Table

All data from the Operation table will be returned from the endpoint below. You can optionally fetch specific data by including the operation Ids, operation type Ids, emission type Ids, emission category Ids, unit Ids, equipment Ids, last modified start date and last modified end date. The Operation endpoint supports pagination.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/operation' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/operation");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
	  "currentPage": 1,
    "totalPages": 1,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 337,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
            "operationId": "number",
            "equipmentId": "number",
            "emissionTypeId": "number",
            "emissionCategoryId": "number",
            "operationTypeId": "number",
            "activeDate": "2023-06-25T04:00:00Z",
            "unitId": "number",
            "controlledInd": "string 1 Byte Y or N",
            "estimatedInd": "string 1 Byte Y or N",
            "invalidInd": "string 1 Byte Y or N",
            "calculateEmissionsInd": "string 1 Byte Y or N",
            "collectionDate": "2023-06-25T04:00:00Z",
            "fieldEventId": "number",
            "inactiveDate": "2023-06-25T04:00:00Z",
            "dataLockTypeId": "number",
            "lastModifiedDate": "2023-06-25T04:00:00Z",
            "externalIdentifier": "string",
            "comments": "string",
            "badDataFlag": "number(0,1)",
            "operationAmount": "number"
        }
	]
}
```

**API Endpoints**

`GET` /api/v1/operation

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
operationIds | int | Operation Ids are unique identifier for this operation type record
operationTypeIds | string | Operation Type Ids is one of the filter option and the parameter is for the type of the Operation Type
emissionTypeIds | int | The unique identifier of the associated emission type
emissionCategoryIds | int | The unique identifier of the associated emission category
unitIds | int | The unique identifier of the associated unit 
equipmentIds | int | The unique identifier of the associated equipment
lastModifiedStartDate | string | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"
lastModifiedEndDate | string | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"


### 13. Operation Type Table

All data from the Operation Type table will be returned from the endpoint below. You can optionally fetch specific data by including the operation type ids, operation types . The Operation Type endpoint supports pagination.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/operationtype' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/operationtype");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 1,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 337,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
            "operationTypeId": "number",
            "operationType": "string",
            "parentOperationTypeId": "number",
            "compoundId": "number",
            "applicabilityFormula": "string",
            "sortOrder": "number",
            "lastModifiedDate": "2020-09-01T15:55:25",
            "externalIdentifier": "number",
            "comments": "number",
            "refId": "number"
        }
	]
}

```

**API Endpoints**

`GET` /api/v1/operationtype

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
operationTypeIDs | int | The unique identifier for this operation type record
operationTypes | int | The type of operational data

### 14. Query Results

The QueryResults API end point will allow the user to run the views saved in Query view tables and returns the dynamic results based on the specific query view id value. The QueryResults endpoint supports pagination.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/queryresults',
  headers: { 'content-type': 'application/json' },
  body:
   { 
    "queryViewId": "number"
      },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/queryresults");
var request = new RestRequest(Method.GET);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n    \"queryViewId\": \"number\"\r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 51,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 25052,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
            "equipment_id": "number",
            "area_id": "number",
            "facility_id": "number",
            "equipment_type_id": "number",
            "source_name": "string",
            "equipment_status_id": "number",
            "model_id": "number",
            "ownership_id": "number",
            "owner_id": "number",
            "serial_number": "string",
            "manufacture_date": "2023-03-30T07:27:06",
            "internal_name": "string",
            "alternate_name": "string",
            "design": "string",
            "original_survey_date": "2023-03-30T07:27:06",
            "active_date": "2018-10-16T06:19:21",
            "inactive_date": "2023-03-30T07:27:06",
            "data_lock_type_id": "number",
            "last_modified_date": "2023-03-30T04:07:57",
            "external_identifier": "string",
            "comments": "string"
        }
	]
}

```

**API Endpoints**

`GET` /api/v1/queryresults

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
queryViewId | int | The unique identifier for this query view record


### 15. Unit Table

This section outlines how to retrieve data from the Unit table using the provided endpoint. You have the flexibility to fetch specific data by including unit Ids, unit type Ids, and units. The Unit type endpoint also supports pagination for managing large datasets effectively.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/unit' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/unit");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 1,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 337,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
            "unitId": "number",
            "unit": "string",
            "unitTypeId": 0,
            "description": "string",
            "alternateNames": "string",
            "sortOrder": "number",
            "lastModifiedDate": "2017-02-13T22:15:30.203Z",
            "externalIdentifier": "string",
            "comments": "string",
            "refId": "string"
        }
	]
}

```

**API Endpoints**

`GET` /api/v1/unit

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
unitIds | int | Unit ID is one of the unique identifier for this Unit record
unitTypeIds | int | Unit Type Ids is the unique identifier of the associated unit type
units | string | Units is one of the filter option and the parameter is for the Name of the Unit

### 16. Workflow Table

This section outlines how to retrieve data from the Workflow table using the provided endpoint. You have the flexibility to fetch specific data by including workflow Ids, workflow type Ids, workflow date for both start date and end date along with the last modified date. The workflow endpoint also supports pagination for managing large datasets effectively.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/workflow' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/workflow");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 1,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 337,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
            "workflowId": "number",
            "workflowTypeId": "number",
            "workflowDate": "2017-02-13T22:15:30.203Z",
            "dataLockTypeId": "1",
            "lastModifiedDate": "2017-02-13T22:15:30.203Z",
            "externalIdentifier": "string",
            "comments": "string"
        }
	]
}

```

**API Endpoints**

`GET` /api/v1/workflow

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
workflowIds | int | Workflow IDs are the unique identifier for workflows.
workflowTypeIds | int | Workflow Type IDs are the unique identifier for a workflow type.
workflowStartDate | dateTime | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"
workflowEndDate | dateTime | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"
lastModifiedStartDate | dateTime | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"
lastModifiedEndDate | dateTime | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"

### 17. Workflow Answer Table

This section outlines how to retrieve data from the Workflow Answer table using the provided endpoint. You have the flexibility to fetch specific data by including workflow Answer Ids, workflow Ids, workflow question Ids, category Answer Index, category Revision Index, question Answer Index, question Revision Index, workflow Answer, lastModifiedStartDate and lastModifiedEndDate. The Workflow Answer endpoint also supports pagination for managing large datasets effectively.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/workflowanswer' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/workflowanswer");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 1,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 337,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
            "workflowAnswerId": "number",
            "workflowId": "number",
            "workflowQuestionId": "number",
            "categoryAnswerIndex": "number",
            "categoryRevisionIndex": "number",
            "questionAnswerIndex": "number",
            "questionRevisionIndex": "number",
            "workflowAnswer": "2016-03-23",
            "dataLockTypeId": "number",
            "personId": "number",
            "lastModifiedDate": "2017-02-13T22:15:30.203Z",
            "externalIdentifier": "string",
            "comments": "string"
        }
	]
}

```

**API Endpoints**

`GET` /api/v1/workflowanswer

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
workflowAnswerIds | int | Workflow Answer IDs are the unique identifiers for the answers in the workflow. Answer IDs are associated with a unique Question ID.
workflowIds | int | Workflow IDs are the unique identifier for workflows (the named form or workflow type+date completed).
workflowQuestionIds | int | Workflow Question IDs are the unique identifiers for questions in the workflow. Question IDs are associated with a unique Workflow ID.
categoryAnswerIndex | int | Category Answer Index is the index for answers in the category.
categoryRevisionIndex | int | Category Revision Index is the list of category revisions. If the workflow itself is updated a new category revision ID is assigned.
questionAnswerIndex | int | Question Answer Index is the index for answers to a question. Answer IDs are associated with a unique Question ID.
questionRevisionIndex | int | Question Revision Index is the index for questions with revisions. If the question itself is updated a question revision ID is assigned.
workflowAnswer | string | Wokflow Answer is the answer to the question..
lastModifiedStartDate | dateTime | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"
lastModifiedEndDate | dateTime | Date time format "yyyy/mm/dd T hours:min:secZ - Ex : 2017-02-13T22:15:30Z"

### 18. Workflow Equipment Table

This section outlines how to retrieve data from the Workflow Equipment table using the provided endpoint. Equipment workflows are typically labeled Inspection. You have the flexibility to fetch specific data by including workflow Equipment Ids, workflow Ids, and Equipment Ids. The Workflow Equipment endpoint also supports pagination for managing large datasets effectively.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/workflowEquipment' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/workflowEquipment");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 1,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 337,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
            "workflowEquipmentId": "number",
            "workflowId": "number",
            "equipmentId": "number",
            "workflowQuestionId": "number",
            "lastModifiedDate": "2017-02-13T22:15:30.203Z",
            "externalIdentifier": "string",
            "comments": "string"
        }
	]
}

```

**API Endpoints**

`GET` /api/v1/workflowEquipment

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
workflowEquipmentIds | int | Workflow Equipment ID is the unique identifier for the associated equipment within the workflow.
workflowIds | int | Workflow Ids is the unique identifier of the associated workflow.
equipmentIds | string | Equipment IDs are the unique identifier of the associated equipment.

### 19. Workflow Facility Table

This section outlines how to retrieve data from the Workflow Facility table using the provided endpoint. Facility workflows are typically labeled Inspection. You have the flexibility to fetch specific data by including workflow Facility Ids, workflow Ids and facility Ids. The Workflow Facility endpoint also supports pagination for managing large datasets effectively.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/workflowfacility' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/workflowfacility");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 1,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 337,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
            "workflowFacilityId": "number",
            "workflowId": "number",
            "facilityId": "number",
            "workflowQuestionId": "number",
            "lastModifiedDate": "2017-02-13T22:15:30.203Z",
            "externalIdentifier": "string",
            "comments": "string"
        }
	]
}

```

**API Endpoints**

`GET` /api/v1/workflowfacility

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
workflowFacilityIds | int | Workflow Facility IDs are the unique identifier for the associated facility within the workflow.
workflowIds | int | Workflow IDs are the unique identifier for workflows (the named form or workflow type+date completed).
facilityIds | int | Facility IDs are the unique identifier for the associated facility.



### 20. Workflow Person Table

This section outlines how to retrieve data from the Workflow Person table using the provided endpoint. You have the flexibility to fetch specific data by including workflow person Ids, workflow Ids and person Ids. The Unit type endpoint also supports pagination for managing large datasets effectively.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/workflowperson' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/workflowperson");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 1,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 337,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
            "workflowPersonId": "number",
            "workflowId": "number",
            "personId": "number",
            "workflowQuestionId": "number",
            "lastModifiedDate": "2017-02-13T22:15:30.203Z",
            "externalIdentifier": "string",
            "comments": "string"
        }
	]
}

```

**API Endpoints**

`GET` /api/v1/workflowperson

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
workflowPersonIds | int | Workflow Person ID is the unique identifier for the associated person within the workflow.
workflowIds | int | Workflow IDs are the unique identifier for workflows (the named form or workflow type+date completed).
personIds | int | Person IDs are the assigned values for associated person(s) and can be used as a filter.

### 21. Workflow Question Table

This section outlines how to retrieve data from the Workflow Question table using the provided endpoint. You have the flexibility to fetch specific data by including workflow Question Ids, workflow question categoy Ids, data type Ids, required Inds and questions. The Workflow Question endpoint also supports pagination for managing large datasets effectively.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/workflowquestion' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/workflowquestion");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 1,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 337,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
            "workflowQuestionId": "number",
            "workflowQuestionCategoryId": "number",
            "question": "string",
            "dataTypeId": "number",
            "dataTypeSize": "number",
            "dataTypePrecision": "number",
            "dataTypeFilter": "string",
            "workflowAnswerListId": "number",
            "workflowAnswerList": "string",
            "defaultValue": "string",
            "alwaysEvaluateDefaultInd": "string",
            "displayInd": "string",
            "displayCondition": "string",
            "disabledInd": "string",
            "disabledCondition": "string",
            "requiredInd": "string",
            "validationCondition": "string",
            "validationErrorText": "string",
            "repeatInd": "string",
            "repeatDeleteInd": "string",
            "repeatDeleteConfirmInd": "string",
            "reviseInd": "string",
            "associateEntityInd": "string",
            "allowCopyInd": "string",
            "workflowTypeId": "number",
            "viewColumnName": "string",
            "sensitiveDataInd": "string",
            "xmlDescription": "string",
            "sortOrder": "number",
            "lastModifiedDate": "2017-02-13T22:15:30.203Z",
            "externalIdentifier": "string",
            "comments": "string",
            "refId": "string"
        }
	]
}

```

**API Endpoints**

`GET` /api/v1/workflowquestion

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
workflowQuestionIds | int | Workflow Question ID are the unique identifiers for the workflow question record.
workflowQuestionCategoryIds | int | Workflow Question Category Ids are the unique identifiers for the associated workflow question category.
dataTypeIds | int | Data Type IDs are the unique identifiers for the associated data type.
requiredInds | string | Required Inds is the value if an answer is required before saving the form.
questions | string | Questions are the question content values included on the form.

### 22. Workflow Type Table

This section outlines how to retrieve data from the Workflow Type table using the provided endpoint. You have the flexibility to fetch specific data by including workflow Ids, workflow type Ids, and workflows. The Unit type endpoint also supports pagination for managing large datasets effectively.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://[tenant].actsapi.intelex.com/v1/workflowtype' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/workflowtype");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Response Schema

```json
{
    "currentPage": 1,
    "totalPages": 1,
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": 337,
    "hasPrevious": false,
    "hasNext": true,
    "data": [
        {
           "workflowTypeId": "number",
            "workflowType": "string",
            "workflowCategoryId": "number",
            "remoteInd": "string",
            "addCondition": "string",
            "openCondition": "string",
            "workflowAssociationsInd": "string",
            "fileAttachmentsInd": "string",
            "allowCopyInd": "string",
            "viewName": "string",
            "xmlDescription": "string",
            "sortOrder": "number",
            "lastModifiedDate": "2017-02-13T22:15:30.203Z",
            "externalIdentifier": "string",
            "comments": "string",
            "refId": "string"
        }
	]
}

```

**API Endpoints**

`GET` /api/v1/workflowtype

**Query parameters**

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
workflowTypeIds | int | Workflow Type IDs are the unique identifier for a workflow type.
workflowCategoryIds | int | Workflow Category IDs are the unique identifier for the associated workflow category.
workflowTypes | string | Workflow Types are the assigned values for the type of workflow and can be used as a filter.



