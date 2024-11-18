## Add or Modify Data

This section outlines the available POST APIs designed for modifying ACTS data. These APIs let you update existing records and insert new records. POSTs should be formatted in JSON. 

* To insert new records, set the primary key to 0
* To update existing records, use the primary key of the record. 

<aside class="notice">
For efficient handling of larger data inserts, it is recommended to perform batch POSTs containing up to 500 rows each. 

Note that excessively large batch POSTs may encounter throttling or failure, depending on system resources.
</aside>

In the following release, the POST APIs End points are provided to add or update following: 

* Analysis
* Analysis Compound
* Emission Factor
* Equipment
* Equipment Analysis
* Equipment Attribute
* Emissions Recalculate By Equipment
* Emissions Recalculate By Operation 
* Facility
* Facility Attribute
* Operation
* Workflow
* Workflow Answer
* Workflow Equipment
* Workflow Facility
* Workflow Person
 
POST requests to these endpoints should be formatted in JSON.

### 1. Analysis Table 

This section guides you through the process of modifying existing Analysis records or adding new entries to the Analysis table using the designated API endpoint. For inserting a new record, please pass the primary key field AnalysisId as 0 in the request body.

**Analysis POST endpoint**

`POST` api/v1/analysis

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/analysis',
  headers: { 'content-type': 'application/json' },
  body:
    [
{
  "analysisId": "number",
  "analysisName": "string",
  "analysisDate": "2024-11-01T12:58:49Z",
  "analysisTypeId": "number",
  "analysisStatusId": "number",
  "alternateName": "string",
  "vendorId": "number",
  "vendorAnalysisNumber": "number",
  "vendorJobNumber": "string",
  "vendorId2": "number",
  "vendorAnalysisNumber2": "string",
  "vendorJobNumber2": "string",
  "reviewedById": "number",
  "reviewedDate": "2024-11-01T12:58:49Z",
  "submitDate": "2024-11-01T12:58:49Z",
  "dataLockTypeId": "number",
  "externalIdentifier": "string",
  "comments": "string"
}
],
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/analysis");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "[  {\r\n  \"analysisId\": \"number\",\r\n  \"analysisName\": \"string\",\r\n
  \"analysisDate\": \"2024-11-01T12:58:49Z\",\r\n  \"analysisTypeId\": \"number\",\r\n  \"analysisStatusId\": \"number\",\r\n
  \"alternateName\": \"string\",\r\n  \"vendorId\": \"number\",\r\n  \"vendorAnalysisNumber\": \"number\",\r\n  \"vendorJobNumber\": \"string\",\r\n  \"vendorId2\": \"number\",\r\n  \"vendorAnalysisNumber2\": \"string\",\r\n  \"vendorJobNumber2\": \"string\",\r\n
  \"reviewedById\": \"number\",\r\n  \"reviewedDate\": \"2024-11-01T12:58:49Z\",\r\n  \"submitDate\": \"2024-11-01T12:58:49Z\",\r\n
  \"dataLockTypeId\": \"number\",\r\n  \"externalIdentifier\": \"string\",\r\n  \"comments\": \"string\"}\r\n]",
   ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body

```json
[
  {
  "analysisId": "number",
  "analysisName": "string",
  "analysisDate": "2024-11-01T12:58:49Z",
  "analysisTypeId": "number",
  "analysisStatusId": "number",
  "alternateName": "string",
  "vendorId": "number",
  "vendorAnalysisNumber": "number",
  "vendorJobNumber": "string",
  "vendorId2": "number",
  "vendorAnalysisNumber2": "string",
  "vendorJobNumber2": "string",
  "reviewedById": "number",
  "reviewedDate": "2024-11-01T12:58:49Z",
  "submitDate": "2024-11-01T12:58:49Z",
  "dataLockTypeId": "number",
  "externalIdentifier": "string",
  "comments": "string"
}
]
```
> Example Response

```json
{
	"insertedRowCount" : 0 , 
	"updatedRowCount" : 1 ,
	"deletedRowCount" : 0 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update due to invalid analysisId

```json
{
	"insertedRowCount" : 0 , 
	"updatedRowCount" : 0 ,	
  "deletedRowCount" : 0 ,
	"failureCount" : 1 ,
	"errorMessage" : [
	 "External Identifier : , Error: An error occurred while saving the entity changes. See the inner exception for details. "
	]
}

```

### 2. Analysis Compound Table 

This section guides you through the process of modifying existing Analysis Compound records or adding new entries to the Analysis Compound table using the designated API endpoint. For inserting a new record, please pass the primary key field AnalysisCompoundId as 0 in the request body.

**Analysis Compound POST endpoint**

`POST` api/v1/analysiscompound

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/analysiscompound',
  headers: { 'content-type': 'application/json' },
  body:
    [
{
	"analysisCompoundId": "number",
	"analysisValue": "number",
	"analysisId": "number",
	"analysisDate": "2011-07-19T00:00:00z",
	"compoundId": "number",
	"comments": "string",
	"dilutionFactor": "number",
	"dataLockTypeId": "number",
	"externalIdentifier": "string",
	"operator": "string",
	"resultText": "string",
	"reportableInd": "string",
	"reportingLimit": "number",
	"method": "string",
	"methodDetectionLimit": "number",
	"qualifier": "string",
	"sortOrder": "number",
	"unitId": "number"
 }
],
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/analysiscompound");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "[  {\r\n  \"analysisCompoundId\": \"number\",\r\n	\"analysisValue\": \"number\",\r\n
	\"analysisId\": \"number\",\r\n	\"analysisDate\": \"2011-07-19T00:00:00z\",\r\n	\"compoundId\": \"number\",\r\n	\"comments\": \"string\",\r\n	\"dilutionFactor\": \"number\",\r\n	\"dataLockTypeId\": \"number\",\r\n	\"externalIdentifier\": \"string\",\r\n
	\"operator\": \"string\",\r\n	\"resultText\": \"string\",\r\n	\"reportableInd\": \"string\",\r\n	\"reportingLimit\": \"number\",\r\n
	\"method\": \"string\",\r\n	\"methodDetectionLimit\": \"number\",\r\n	\"qualifier\": \"string\",\r\n	\"sortOrder\": \"number\",\r\n
	\"unitId\": \"number\"}\r\n]",   ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body

```json
[
{
	"analysisCompoundId": "number",
	"analysisValue": "number",
	"analysisId": "number",
	"analysisDate": "2011-07-19T00:00:00z",
	"compoundId": "number",
	"comments": "string",
	"dilutionFactor": "number",
	"dataLockTypeId": "number",
	"externalIdentifier": "string",
	"operator": "string",
	"resultText": "string",
	"reportableInd": "string",
	"reportingLimit": "number",
	"method": "string",
	"methodDetectionLimit": "number",
	"qualifier": "string",
	"sortOrder": "number",
	"unitId": "number"
 }
]
```
> Example Response

```json
{
	"insertedRowCount" : 0 , 
	"updatedRowCount" : 1 ,
	"deletedRowCount" : 0 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update due to invalid analysisCompoundId

```json
{
	"insertedRowCount" : 0 , 
	"updatedRowCount" : 0 ,	
  "deletedRowCount" : 0 ,
	"failureCount" : 1 ,
	"errorMessage" : [
	 "External Identifier : , Error: An error occurred while saving the entity changes. See the inner exception for details. "
	]
}

```


### 3. Emission Factor Table 

This section guides you through the process of modifying existing Emission Factor records or adding new entries to the Emission Factor table using the designated API endpoint. For inserting a new record, please pass the primary key field emissionFactorId as 0 in the request body.

**Emission Factor POST endpoint**

`POST` api/v1/emissionfactor

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/emissionfactor',
  headers: { 'content-type': 'application/json' },
  body:
    [
  {
    "emissionFactorId": "number",
    "equipmentId": "number",
    "emissionTypeId": "number",
    "emissionCategoryId": "number",
    "compoundId": "number",
    "emissionFactorName": "string",
    "activeDate": "2023-06-25T04:00:00Z",
    "emissionFactor": "number",
    "unitId": "number",
    "viewColumnName": "string",
    "inactiveDate": "2023-06-25T04:00:00Z",
    "dataLockTypeId": "number",
    "lastModifiedDate": "2023-06-25T04:00:00Z",
    "externalIdentifier": "string",
    "comments": "string"
  }
],
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/emissionfactor");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "[  {\r\n    \"emissionFactorId\": \"number\",\r\n    \"equipmentId\": \"number\",\r\n    \"emissionTypeId\": \"number\",\r\n    \"emissionCategoryId\": \"number\",\r\n    \"compoundId\": \"number\",\r\n    \"emissionFactorName\": \"string\",\r\n    \"activeDate\": \"2023-06-25T04:00:00Z\",\r\n    \"emissionFactor\": \"number\",\r\n    \"unitId\": \"number\",\r\n    \"viewColumnName\": \"string\",\r\n    \"inactiveDate\": \"2023-06-25T04:00:00Z\",\r\n    \"dataLockTypeId\": \"number\",\r\n    \"lastModifiedDate\": \"2023-06-25T04:00:00Z\",\r\n    \"externalIdentifier\": \"string\",\r\n    \"comments\": \"string\"\r\n  }\r\n]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body

```json
[
  {
    "emissionFactorId": "number",
    "equipmentId": "number",
    "emissionTypeId": "number",
    "emissionCategoryId": "number",
    "compoundId": "number",
    "emissionFactorName": "string",
    "activeDate": "2023-06-25T04:00:00Z",
    "emissionFactor": "number",
    "unitId": "number",
    "viewColumnName": "string",
    "inactiveDate": "2023-06-25T04:00:00Z",
    "dataLockTypeId": "number",
    "lastModifiedDate": "2023-06-25T04:00:00Z",
    "externalIdentifier": "string",
    "comments": "string"
  }
]
```
> Example Response

```json
{
	"insertedRowCount" : 0 , 
	"updatedRowCount" : 1 ,
	"deletedRowCount" : 0 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update due to invalid EmissionFactorId

```json
{
	"insertedRowCount" : 0 , 
	"updatedRowCount" : 0 ,	
  "deletedRowCount" : 0 ,
	"failureCount" : 1 ,
	"errorMessage" : [
	 "External Identifier : , Error: An error occurred while saving the entity changes. See the inner exception for details. "
	]
}

```


### 4. Equipment Table 

This section guides you through the process of modifying existing equipment records or adding new entries to the Equipment table using the designated API endpoint.

**Equipment POST endpoint**

`POST` api/v1/equipment

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/equipment',
  headers: { 'content-type': 'application/json' },
  body:
    [  {
    "equipmentId": "number",
    "areaId": "number",
    "facilityId": "number",
    "equipmentTypeId": "number",
    "sourceName": "string ",
    "equipmentStatusId": "number",
    "modelId": "number",
    "ownershipId": "number",
    "ownerId": "number",
    "serialNumber": "number",
    "manufactureDate": "2023-06-25T04:00:00Z",
    "internalName": "string",
    "alternateName": "string",
    "design": "string",
    "originalSurveyDate": "2023-06-25T04:00:00Z",
    "activeDate": "2023-06-25T04:00:00Z",
    "inactiveDate": "2023-06-25T04:00:00Z",
	  "dataLockTypeId": "number",
    "lastModifiedDate": "2023-06-25T04:00:00Z",
    "externalIdentifier": "string",
    "comments": "string"
	}],
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/equipment");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", " [ {\r\n    \"equipmentId\": \"number\",\r\n    \"areaId\": \"number\",\r\n    \"facilityId\": \"number\",\r\n    \"equipmentTypeId\": \"number\",\r\n    \"sourceName\": \"string \",\r\n    \"equipmentStatusId\": \"number\",\r\n    \"modelId\": \"number\",\r\n    \"ownershipId\": \"number\",\r\n    \"ownerId\": \"number\",\r\n    \"serialNumber\": \"number\",\r\n    \"manufactureDate\": \"2023-06-25T04:00:00Z\",\r\n    \"internalName\": \"string\",\r\n    \"alternateName\": \"string\",\r\n    \"design\": \"string\",\r\n    \"originalSurveyDate\": \"2023-06-25T04:00:00Z\",\r\n    \"activeDate\": \"2023-06-25T04:00:00Z\",\r\n    \"inactiveDate\": \"2023-06-25T04:00:00Z\",\r\n\t  \"dataLockTypeId\": \"number\",\r\n    \"lastModifiedDate\": \"2023-06-25T04:00:00Z\",\r\n    \"externalIdentifier\": \"string\",\r\n    \"comments\": \"string\"\r\n }\r\n]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body

```json
[
  {
    "equipmentId": "number",
    "areaId": "number",
    "facilityId": "number",
    "equipmentTypeId": "number",
    "sourceName": "string ",
    "equipmentStatusId": "number",
    "modelId": "number",
    "ownershipId": "number",
    "ownerId": "number",
    "serialNumber": "number",
    "manufactureDate": "2023-06-25T04:00:00Z",
    "internalName": "string",
    "alternateName": "string",
    "design": "string",
    "originalSurveyDate": "2023-06-25T04:00:00Z",
    "activeDate": "2023-06-25T04:00:00Z",
    "inactiveDate": "2023-06-25T04:00:00Z",
	  "dataLockTypeId": "number",
    "lastModifiedDate": "2023-06-25T04:00:00Z",
    "externalIdentifier": "string",
    "comments": "string"
	}
]
```
> Example Response

```json
{
	"insertedRowCount" : 2 , 
	"updatedRowCount" : 3 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update

```json
{
	"insertedRowCount" : 0 , 
	"updatedRowCount" : 1 ,
	"failureCount" : 1 ,
	"errorMessage" : [
	 "Equipment ID : 0, Error: An error occurred while saving the entity changes. See the inner exception for details "
	]
}

```

### 5. Equipment Analysis Table 

This section outlines the process of adding new entries or modifying existing records within the Equipment Analysis table using the dedicated API endpoint.

**Equipment Analysis POST Endpoint**

`POST` api/v1/equipmentanalysis

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/equipmentanalysis',
  headers: { 'content-type': 'application/json' },
  body:

       [
  {
    "equipmentAnalysisId": "number",
    "equipmentId": "number",
    "analysisId": "number",
    "analysisAssociationTypeId": "number",
    "activeDate": "2014-04-01T00:00:00z",
    "inactiveDate": "2025-04-01T00:00:00z",
    "dataLockTypeId": "number",
    "lastModifiedDate": "2014-04-01T13:37:16z",
    "externalIdentifier": "string",
    "comments": "string"
  }
],
          json: true };


request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/equipmentanalysis");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", " [\r\n  { \r\n\ "equipmentAnalysisId\": \"number\",\r\n    \"equipmentId\": \"number\",\r\n
    \"analysisId\": \"number\",\r\n    \"analysisAssociationTypeId\": \"number\",\r\n    \"activeDate\": \"2014-04-01T00:00:00z\",\r\n
    \"inactiveDate\": \"2025-04-01T00:00:00z\",\r\n    \"dataLockTypeId\": \"number\",\r\n    \"lastModifiedDate\": \"2014-04-01T13:37:16z\",\r\n    \"externalIdentifier\": \"string\",\r\n    \"comments\": \"string\" \r\n  }\r\n]", 
    ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body 

```json
 [
  {
    "equipmentAnalysisId": "number",
    "equipmentId": "number",
    "analysisId": "number",
    "analysisAssociationTypeId": "number",
    "activeDate": "2014-04-01T00:00:00z",
    "inactiveDate": "2025-04-01T00:00:00z",
    "dataLockTypeId": "number",
    "lastModifiedDate": "2014-04-01T13:37:16z",
    "externalIdentifier": "string",
    "comments": "string"
  }
]
```
> Example Response

```json
{
	"insertedRowCount" : 2 , 
	"updatedRowCount" : 3 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update

```json
{
    "insertedRowCount" : 0 , 
    "updatedRowCount" : 0 ,
    "failureCount" : 1 ,
    "errorMessage" : [
	 "EquipmentAnalysis ID : 0, Error: An error occurred while saving the entity changes. See the inner exception for details "
	]
}

```

### 6. Equipment Attribute Table 

This section outlines the process of adding new entries or modifying existing records within the Equipment Attribute table using the dedicated API endpoint.

**Equipment Attribute POST Endpoint**

`POST` api/v1/equipmentattribute

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/equipmentattribute',
  headers: { 'content-type': 'application/json' },
  body:

       [
  { 
	 "equipmentAttributeId": "number",
    "equipmentId": "number",
    "attributeTypeId": "number",
    "equipmentAttribute":"string",
    "dataLockTypeId": "number",
    "lastModifiedDate": "2023-03-30T07:27:06.295Z",
    "externalIdentifier": "string",
    "comments":"string"
  }
],
          json: true };


request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/equipmentattribute");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", " [\r\n  { \r\n"equipmentAttributeId\": \"number\",\r\n    \"equipmentId\": \"number\",\r\n    \"attributeTypeId\": \"number\",\r\n    \"equipmentAttribute\":\"string\",\r\n    \"dataLockTypeId\": \"number\",\r\n    \"lastModifiedDate\": \"2023-03-30T07:27:06.295Z\",\r\n    \"externalIdentifier\": \"string\",\r\n    \"comments\":\"string\"\r\n  }\r\n]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body 

```json
 [
  { 
	"equipmentAttributeId": "number",
    "equipmentId": "number",
    "attributeTypeId": "number",
    "equipmentAttribute":"string",
    "dataLockTypeId": "number",
    "lastModifiedDate": "2023-03-30T07:27:06.295Z",
    "externalIdentifier": "string",
    "comments":"string"
  }
]
```
> Example Response

```json
{
	"insertedRowCount" : 2 , 
	"updatedRowCount" : 3 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update

```json
{
    "insertedRowCount" : 0 , 
    "updatedRowCount" : 1 ,
    "failureCount" : 1 ,
    "errorMessage" : [
	 "EquipmentAttribute ID : 0, Error: An error occurred while saving the entity changes. See the inner exception for details "
	]
}

```


### 7. Emissions Recalculate By Equipment  

This section guides you through the process of an on-demand update to the emissions calculation for a specific equipment using the designated API endpoint. While this API endpoint is a child of the Equipment table, adding or updating an equipment will not cause an update on its own. 

**Equipment/EmissionCalculation POST endpoint**

`POST` api/v1/equipment/emissioncalculation

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/equipment/emissioncalculation',
  headers: { 'content-type': 'application/json' },
  body:
    { [equipmentId1, equipmentId2, equipmentId3....]
	 },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/equipment/emissioncalculation");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n   [equipmentId1, equipmentId2, equipmentId3....]\r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body

```json
{
   [equipmentId1, equipmentId2, equipmentId3....]
	 }
```
> Example Response

```json
{
    "processedIds": [
        "34",
        "36"
    ],
    "invalidIds": [
        "1234"
    ],
    "errorMessages": []
}

```

> Example Output when data is missing

```json
{
    "processedIds": [],
    "invalidIds": [],
    "errorMessages": [
        "Equipment ids are missing."
    ]
}

```

### 8. Emissions Recalculate By Operation 

This section guides you through the process of an on-demand update to the emissions calculation for a specific operation using the designated API endpoint. While this API endpoint is a child of the Operation table, adding or updating an operation with the API will not cause an update on its own. 

**Operation/EmissionCalculation POST endpoint**

`POST` api/v1/operation/emissioncalculation

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/operation/emissioncalculation',
  headers: { 'content-type': 'application/json' },
  body:
  { [operationId1, operationId2, operationId3....]
	 },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/operation/emissioncalculation");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n   [operationId1, operationId2, operationId3....]\r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body

```json
{
   [operationId1, operationId2, operationId3....]
}
```
> Example Response

```json
{
    "processedIds": [
        "34",
        "36"
    ],
    "invalidIds": [
        "1234"
    ],
    "errorMessages": []
}

```

> Example Output when data is missing

```json
{
    "processedIds": [],
    "invalidIds": [],
    "errorMessages": [
        "Operation ids are missing."
    ]
}

```

### 9. Facility Table 

This section outlines the process of adding new entries or modifying existing records within the Facility table using the dedicated API endpoint.

**Facility POST Endpoint**

`POST` api/v1/facility

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/facility',
  headers: { 'content-type': 'application/json' },
  body:
   [{
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
  }],
     json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/facility");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "[{\r\n    \"facilityId\": \"number\",\r\n    \"facilityName\": \"string\",\r\n    \"areaId\": \"number\",\r\n    \"facilityTypeId\": \"number\",\r\n    \"facilityStatusId\": \"number\",\r\n    \"sortOrder\": \"number\",\r\n    \"facilityOwnershipId\": \"number\",\r\n    \"facilityOwnerId\": \"number\",\r\n    \"landOwnershipId\": \"number\",\r\n    \"landOwnerId\": \"number\",\r\n    \"operatorId\": \"number\",\r\n    \"countryId\": \"number\",\r\n    \"countyId\": \"number\",\r\n    \"offshoreBlockId\": \"number\",\r\n    \"meteorologicalId\": \"number\",\r\n    \"businessEntityId\": \"number\",\r\n    \"businessUnitId\": \"number\",\r\n    \"alternateName\": \"string\",\r\n    \"purchaseDate\": \"2023-06-25T04:00:00Z\",\r\n    \"previousOwnerId\": \"number\",\r\n    \"soldDate\": \"2023-06-25T04:00:00Z\",\r\n    \"soldToId\": \"number\",\r\n    \"activeDate\": \"2023-06-25T04:00:00Z\",\r\n    \"inactiveDate\": \"2023-06-25T04:00:00Z\",\r\n    \"dataLockTypeId\": \"number\",\r\n    \"lastModifiedDate\": \"2023-06-25T04:00:00Z\",\r\n    \"externalIdentifier\": \"string\",\r\n    \"comments\": \"string\"\r\n  }]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body 

```json
[
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
```

> Example Response

```json
{
	"insertedRowCount" : 2 , 
	"updatedRowCount" : 3 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update

```json
{
	"insertedRowCount" : 0 , 
	"updatedRowCount" : 1 ,
	"failureCount" : 1 ,
	"errorMessage" : [
	 "Facility ID : 0, Error: An error occurred while saving the entity changes. See the inner exception for details "
	]
}

```

### 10. Facility Attribute Table 

This section outlines the process of adding new entries or modifying existing records within the Facility Attribute table using the dedicated API endpoint.

**Facility Attribute POST Endpoint**

`POST` api/v1/facilityattribute

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/facilityattribute',
  headers: { 'content-type': 'application/json' },
  body:
   [
  { "facilityAttributeId": "number",
    "facilityId": "number",
    "attributeTypeId": "number",
    "facilityAttribute":"string",
    "dataLockTypeId": "number",
    "lastModifiedDate": "2023-03-30T07:27:06.295Z",
    "externalIdentifier": "string",
    "comments":"string"
  }
],
      json: true };


request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/facilityattribute");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "[\r\n  { \r\n"facilityAttributeId\": \"number\",\r\n    \"facilityId\": \"number\",\r\n    \"attributeTypeId\": \"number\",\r\n    \"facilityAttribute\":\"string\",\r\n    \"dataLockTypeId\": \"number\",\r\n    \"lastModifiedDate\": \"2023-03-30T07:27:06.295Z\",\r\n    \"externalIdentifier\": \"string\",\r\n    \"comments\":\"string\"\r\n  }\r\n]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body 

```json
[
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
```
> Example Response

```json
{
	"insertedRowCount" : 2 , 
	"updatedRowCount" : 3 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update

```json
{
	"insertedRowCount" : 0 , 
	"updatedRowCount" : 1 ,
	"failureCount" : 1 ,
	"errorMessage" : [
	 "FacilityAttribute ID : 0, Error: An error occurred while saving the entity changes. See the inner exception for details "
	]
}

```

### 11. Operation Table 

This section outlines the process of adding new entries or modifying existing records within the Operation table using the dedicated API endpoint.

**Operation POST Endpoint**

`POST` api/v1/operation

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/operation',
  headers: { 'content-type': 'application/json' },
  body:
 [
  {
    "operationId": "number",
    "equipmentId": "number",
    "emissionTypeId": "number",
    "emissionCategoryId": "number",
    "operationTypeId": "number",
    "activeDate": "2023-06-25T04:00:00Z",
    "unitId": "number",
    "controlledInd": "string",
    "estimatedInd": "string",
    "invalidInd": "string",
    "calculateEmissionsInd": "string",
    "collectionDate": "2023-06-25T04:00:00Z",
    "fieldEventId": "number",
    "inactiveDate": "2023-06-25T04:00:00Z",
    "dataLockTypeId": "number",
    "lastModifiedDate": "2023-06-25T04:00:00Z",
    "externalIdentifier": "string",
    "comments": "string",
    "badDataFlag": "number(1,0)",
    "operationAmount": "number"
  } 
],
     json: true };


request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/operation");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "[\r\n  {\r\n    \"operationId\": \"number\",\r\n    \"equipmentId\": \"number\",\r\n    \"emissionTypeId\": \"number\",\r\n    \"emissionCategoryId\": \"number\",\r\n    \"operationTypeId\": \"number\",\r\n    \"activeDate\": \"2023-06-25T04:00:00Z\",\r\n    \"unitId\": \"number\",\r\n    \"controlledInd\": \"string\",\r\n    \"estimatedInd\": \"string\",\r\n    \"invalidInd\": \"string\",\r\n    \"calculateEmissionsInd\": \"string\",\r\n    \"collectionDate\": \"2023-06-25T04:00:00Z\",\r\n    \"fieldEventId\": \"number\",\r\n    \"inactiveDate\": \"2023-06-25T04:00:00Z\",\r\n    \"dataLockTypeId\": \"number\",\r\n    \"lastModifiedDate\": \"2023-06-25T04:00:00Z\",\r\n    \"externalIdentifier\": \"string\",\r\n    \"comments\": \"string\",\r\n    \"badDataFlag\": \"number(1,0)\",\r\n    \"operationAmount\": \"number\"\r\n  } \r\n]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
> Input JSON Body

```json
[
  {
    "operationId": "number",
    "equipmentId": "number",
    "emissionTypeId": "number",
    "emissionCategoryId": "number",
    "operationTypeId": "number",
    "activeDate": "2023-06-25T04:00:00Z",
    "unitId": "number",
    "controlledInd": "string",
    "estimatedInd": "string",
    "invalidInd": "string",
    "calculateEmissionsInd": "string",
    "collectionDate": "2023-06-25T04:00:00Z",
    "fieldEventId": "number",
    "inactiveDate": "2023-06-25T04:00:00Z",
    "dataLockTypeId": "number",
    "lastModifiedDate": "2023-06-25T04:00:00Z",
    "externalIdentifier": "string",
    "comments": "string",
    "badDataFlag": "number(1,0)",
    "operationAmount": "number"
  } 
]

```

> Example Response

```json
{
	"insertedRowCount" : 2 , 
	"updatedRowCount" : 3 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update

```json
{
	"insertedRowCount" : 0 , 
	"updatedRowCount" : 1 ,
	"failureCount" : 1 ,
	"errorMessage" : [
	 "Operation ID : 0, Error: An error occurred while saving the entity changes. See the inner exception for details "
	]
}

```

### 12. Workflow Table 

This section outlines the process of adding new entries or modifying existing records within the Workflow table using the dedicated API endpoint.

**Workflow POST Endpoint**

`POST` api/v1/workflow

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/workflow',
  headers: { 'content-type': 'application/json' },
  body:
      [
  {
        "workflowId": "number",
        "workflowTypeId": "number",
        "workflowDate": "2024-01-03T08:16:24.155Z",
        "dataLockTypeId": "number",
        "lastModifiedDate": "2024-01-03T08:16:24.155Z",
        "externalIdentifier": "string",
        "comments": "string"
  }
],
  json: true };


request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/workflow");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", " [\r\n  {\r\n        \"workflowId\": \"number\",\r\n        \"workflowTypeId\": \"number\",\r\n        \"workflowDate\": \"2024-01-03T08:16:24.155Z\",\r\n        \"dataLockTypeId\": \"number\",\r\n        \"lastModifiedDate\": \"2024-01-03T08:16:24.155Z\",\r\n        \"externalIdentifier\": \"string\",\r\n        \"comments\": \"string\"\r\n  }\r\n]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body 

```json
[
  {
        "workflowId": "number",
        "workflowTypeId": "number",
        "workflowDate": "2024-01-03T08:16:24.155Z",
        "dataLockTypeId": "number",
        "lastModifiedDate": "2024-01-03T08:16:24.155Z",
        "externalIdentifier": "string",
        "comments": "string"
  }
]
```
> Example Response

```json
{
	"insertedRowCount" : 2 , 
	"updatedRowCount" : 3 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update

```json
{
    "insertedRowCount" : 0 , 
    "updatedRowCount" : 1 ,
    "failureCount" : 1 ,
    "errorMessage" : [
	 "Workflow Id : 0, Error: An error occurred while saving the entity changes. See the inner exception for details "
	]
}

```

### 13. Workflow Answer Table 

This section outlines the process of adding new entries or modifying existing records within the Workflow Answer table using the dedicated API endpoint.

**Workflow Answer POST Endpoint**

`POST` api/v1/workflowanswer

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/workflowanswer',
  headers: { 'content-type': 'application/json' },
  body:
      [{
        "workflowAnswerId": "number",
        "workflowId": "number",
        "workflowQuestionId": "number",
        "categoryAnswerIndex": "number",
        "categoryRevisionIndex": "number",
        "questionAnswerIndex": "number",
        "questionRevisionIndex": "number",
        "workflowAnswer": "string",
        "dataLockTypeId": "number",
        "personId": "number",
        "lastModifiedDate": "2024-01-03T08:16:24.155Z",
        "externalIdentifier": "string",
        "comments": "string"
      }],
  json: true };


request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/workflowanswer");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "[{\r\n        \"workflowAnswerId\": \"number\",\r\n        \"workflowId\": \"number\",\r\n        \"workflowQuestionId\": \"number\",\r\n        \"categoryAnswerIndex\": \"number\",\r\n        \"categoryRevisionIndex\": \"number\",\r\n        \"questionAnswerIndex\": \"number\",\r\n        \"questionRevisionIndex\": \"number\",\r\n        \"workflowAnswer\": \"string\",\r\n        \"dataLockTypeId\": \"number\",\r\n        \"personId\": \"number\",\r\n        \"lastModifiedDate\": \"2024-01-03T08:16:24.155Z\",\r\n        \"externalIdentifier\": \"string\",\r\n        \"comments\": \"string\"\r\n      }]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body 

```json
[{
        "workflowAnswerId": "number",
        "workflowId": "number",
        "workflowQuestionId": "number",
        "categoryAnswerIndex": "number",
        "categoryRevisionIndex": "number",
        "questionAnswerIndex": "number",
        "questionRevisionIndex": "number",
        "workflowAnswer": "string",
        "dataLockTypeId": "number",
        "personId": "number",
        "lastModifiedDate": "2024-01-03T08:16:24.155Z",
        "externalIdentifier": "string",
        "comments": "string"
      }]
```
> Example Response

```json
{
	"insertedRowCount" : 2 , 
	"updatedRowCount" : 3 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update

```json
{
    "insertedRowCount" : 0 , 
    "updatedRowCount" : 1 ,
    "failureCount" : 1 ,
    "errorMessage" : [
	 "Workflow Answer Id : 0, Error: An error occurred while saving the entity changes. See the inner exception for details "
	]
}

```

### 14. Workflow Equipment Table 

This section outlines the process of adding new entries or modifying existing records within the Workflow Equipment table using the dedicated API endpoint.

**Workflow Equipment POST Endpoint**

`POST` api/v1/workflowequipment

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/workflowequipment',
  headers: { 'content-type': 'application/json' },
  body:
      [
  {
        "workflowEquipmentId": "number",
        "workflowId": "number",
        "equipmentId": "number",
        "workflowQuestionId": "number",
        "lastModifiedDate": "2024-01-03T08:16:24.155Z",
        "externalIdentifier": "string",
        "comments": "string"
  }
],
  json: true };


request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/workflowequipment");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "[\r\n  {\r\n        \"workflowEquipmentId\": \"number\",\r\n        \"workflowId\": \"number\",\r\n        \"equipmentId\": \"number\",\r\n        \"workflowQuestionId\": \"number\",\r\n        \"lastModifiedDate\": \"2024-01-03T08:16:24.155Z\",\r\n        \"externalIdentifier\": \"string\",\r\n        \"comments\": \"string\"\r\n  }\r\n]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body 

```json
[
  {
        "workflowEquipmentId": "number",
        "workflowId": "number",
        "equipmentId": "number",
        "workflowQuestionId": "number",
        "lastModifiedDate": "2024-01-03T08:16:24.155Z",
        "externalIdentifier": "string",
        "comments": "string"
  }
]
```
> Example Response

```json
{
	"insertedRowCount" : 2 , 
	"updatedRowCount" : 3 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update

```json
{
    "insertedRowCount" : 0 , 
    "updatedRowCount" : 1 ,
    "failureCount" : 1 ,
    "errorMessage" : [
	 "Workflow Equipment Id : 0, Error: An error occurred while saving the entity changes. See the inner exception for details "
	]
}

```

### 15. Workflow Facility Table 

This section outlines the process of adding new entries or modifying existing records within the Workflow Facility table using the dedicated API endpoint.

**Workflow Facility POST Endpoint**

`POST` api/v1/workflowfacility

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/workflowfacility',
  headers: { 'content-type': 'application/json' },
  body:
      [
  {
        "workflowFacilityId": "number",
        "workflowId": "number",
        "facilityId": "number",
        "workflowQuestionId": "number",
        "lastModifiedDate": "2024-01-03T08:16:24.155Z",
        "externalIdentifier": "string",
        "comments": "string"
  }
],
  json: true };


request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/workflowfacility");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "[\r\n  {\r\n        \"workflowFacilityId\": \"number\",\r\n        \"workflowId\": \"number\",\r\n        \"facilityId\": \"number\",\r\n        \"workflowQuestionId\": \"number\",\r\n        \"lastModifiedDate\": \"2024-01-03T08:16:24.155Z\",\r\n        \"externalIdentifier\": \"string\",\r\n        \"comments\": \"string\"\r\n  }\r\n]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body 

```json
[
  {
        "workflowFacilityId": "number",
        "workflowId": "number",
        "facilityId": "number",
        "workflowQuestionId": "number",
        "lastModifiedDate": "2024-01-03T08:16:24.155Z",
        "externalIdentifier": "string",
        "comments": "string"
  }
]
```
> Example Response

```json
{
	"insertedRowCount" : 2 , 
	"updatedRowCount" : 3 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update

```json

{
    "insertedRowCount" : 0 , 
    "updatedRowCount" : 1 ,
    "failureCount" : 1 ,
    "errorMessage" : [
	 "Workflow Facility Id : 0, Error: An error occurred while saving the entity changes. See the inner exception for details "
	]
}

```

### 16. Workflow Person Table 

This section outlines the process of adding new entries or modifying existing records within the Workflow Person table using the dedicated API endpoint.

**Workflow Person POST Endpoint**

`POST` api/v1/workflowperson

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://[tenant].actsapi.intelex.com/v1/workflowperson',
  headers: { 'content-type': 'application/json' },
  body:
      [
  {
        "workflowPersonId": "number",
        "workflowId": "number",
        "personId": "number",
        "workflowQuestionId": "number",
        "lastModifiedDate": "2024-01-03T08:16:24.155Z",
        "externalIdentifier": "string",
        "comments": "string"
  }
],
  json: true };


request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/Workflowperson");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "[\r\n  {\r\n        \"workflowPersonId\": \"number\",\r\n        \"workflowId\": \"number\",\r\n        \"personId\": \"number\",\r\n        \"workflowQuestionId\": \"number\",\r\n        \"lastModifiedDate\": \"2024-01-03T08:16:24.155Z\",\r\n        \"externalIdentifier\": \"string\",\r\n        \"comments\": \"string\"\r\n  }\r\n]", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body 

```json
[
  {
        "workflowPersonId": "number",
        "workflowId": "number",
        "personId": "number",
        "workflowQuestionId": "number",
        "lastModifiedDate": "2024-01-03T08:16:24.155Z",
        "externalIdentifier": "string",
        "comments": "string"
  }
]
```
> Example Response

```json
{
	"insertedRowCount" : 2 , 
	"updatedRowCount" : 3 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update

```json

{
    "insertedRowCount" : 0 , 
    "updatedRowCount" : 1 ,
    "failureCount" : 1 ,
    "errorMessage" : [
	 "Workflow Person Id : 0, Error: An error occurred while saving the entity changes. See the inner exception for details "
	]
}

```

### JSON body for both Insert & Update 

#### JSON Input body for Insert 

If the primary id is zero - "0" then the data we are passing is handled as an insert, shown in the example below, where "equipmentAttributeId" is passed as "0". 

Parameter | Description
--------- | -----------
equipmentAttributeId  | equipmentAttributeId for insert we do pass the input as zero "0"
equipmentId  | equipmentId accepts the numbers as input 
attributeTypeId  | attributeTypeId accepts the numbers as input 
equipmentAttribute  | equipmentAttribute accepts the string data as input 
dataLockTypeId | dataLockTypeId accepts the numbers as input 
lastModifiedDate  | lastModifiedDate is given in a date and time format 
externalIdentifier  | externalIdentifier accepts the string data as input
comments  | comments accepts the string data as input

> Example Input JSON Body For Insert 

```json
[
    {
        "equipmentAttributeId": 0,
        "equipmentId": "number",
        "attributeTypeId": "number",
		    "equipmentAttribute":"string",
        "dataLockTypeId": "number",
        "lastModifiedDate": "datetime",
        "externalIdentifier": "string",
		    "comments":"string"
    }
]
```

> Example Input JSON Body For Update 

#### JSON Input body for Update

If the primary id is an existing ID - "#####" then the data we are passing is handled as an update, shown in the example below, where "equipmentAttributeId" is passed as "164". 

Parameter | Description
--------- | -----------
equipmentAttributeId  | equipmentAttributeId for update we do pass the input as integer like "164"
equipmentId  | equipmentId accepts the numbers as input 
attributeTypeId  | attributeTypeId accepts the numbers as input 
equipmentAttribute  | equipmentAttribute accepts the string data as input 
dataLockTypeId | dataLockTypeId accepts the numbers as input 
lastModifiedDate  | lastModifiedDate is given in a date and time format 
externalIdentifier  | externalIdentifier accepts the string data as input
comments  | comments accepts the string data as input


```json
[
    {
        "equipmentAttributeId": 164,
        "equipmentId": "number",
        "attributeTypeId": "number",
		    "equipmentAttribute":"string",
        "dataLockTypeId": "number",
        "lastModifiedDate": "datetime",
        "externalIdentifier": "string",
		    "comments":"string"
    }
]
```

> Example Output For Both Update and Insert 

```json
{
	"insertedRowCount" : 2 , 
	"updatedRowCount" : 3 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update

```json
{
	"insertedRowCount" : 0 , 
	"updatedRowCount" : 1 ,
	"failureCount" : 1 ,
	"errorMessage" : [
	 "Operation ID : 0, Error: An error occurred while saving the entity changes. See the inner exception for details "
	]
}

```

