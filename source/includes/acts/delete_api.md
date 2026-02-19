## Remove or Delete data from Database Table

This section outlines the available Delete APIs designed for modifying ACTS data by deleteing or removing the data. These APIs offer options for removing existing records from the mentioned tables. 

* To remove the existing records, use the primary key of the record.

As per the current release, DELETE APIs End points are provided to delete from the following tables: 

* Analysis
* Analysis Attribute
* Analysis Compound
* Analysis Value
* Emission Factor
* Equipment Analysis
* Equipment Requirement
* Facility Analysis
* Facility Regulation
* Operation
* Regulation
* Regulation Attribute
* Requirement
* Requirement Limit
* Requirement Person

DELETE requests to these endpoints should be formatted in JSON.

### 1. Analysis Attribute Table 

This section guides you through the process of removing/deleting the existing records from the Analysis Attribute table using the designated API endpoint.

**Analysis Attribute DELETE endpoint**

`DELETE` /actsapi/v1/analysisattribute

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/analysisattribute',
  headers: { 'content-type': 'application/json' },
  body:
   { 
    [analysisAttributeId1, analysisAttributeId2, analysisAttributeId3....]
      },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp

var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/analysisattribute");
var request = new RestRequest(Method.DELETE);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n    [analysisAttributeId1, analysisAttributeId2, analysisAttributeId3....] \r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
> Input JSON Body

```json

  {
    [analysisAttributeId1, analysisAttributeId2, analysisAttributeId3....]
  }

```
> Example Response

```json
{
  "deletedRowCount": 1,
  "notFoundCount": 0,
  "failureCount": 0,
  "errorMessage" : []
}

```

### 2. Analysis Table 

This section guides you through the process of removing/deleting the existing records from the Analysis table using the designated API endpoint.

**Analysis DELETE endpoint**

`DELETE` /actsapi/v1/analysis

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/analysis',
  headers: { 'content-type': 'application/json' },
  body:
   { 
    [analysisId1, analysisId2, analysisId3....]
      },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp

var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/analysis");
var request = new RestRequest(Method.DELETE);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n    [operationId1, operationId2, operationId3....] \r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
> Input JSON Body

```json

  {
    [analysisId1, analysisId2, analysisId3....]
  }

```
> Example Response

```json
{
  "deletedRowCount": 1,
  "notFoundCount": 0,
  "failureCount": 0,
  "errorMessage" : []
}

```

### 3. Analysis Compound Table 

This section guides you through the process of removing/deleting the existing records from the Analysis Compound table using the designated API endpoint.

**Analysis Compound DELETE endpoint**

`DELETE` /actsapi/v1/analysiscompound

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/analysiscompound',
  headers: { 'content-type': 'application/json' },
  body:
   { 
    [analysisCompoundId1, analysisCompoundId2, analysisCompoundId3....]
      },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp

var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/analysiscompound");
var request = new RestRequest(Method.DELETE);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n    [analysisCompoundId1, analysisCompoundId2, analysisCompoundId3....] \r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
> Input JSON Body

```json

  {
    [analysisCompoundId1, analysisCompoundId2, analysisCompoundId3....]
  }

```
> Example Response

```json
{
  "deletedRowCount": 1,
  "notFoundCount": 0,
  "failureCount": 0,
  "errorMessage" : []
}

```


### 4. Analysis Value Table 

This section guides you through the process of removing/deleting the existing records from the Analysis Value table using the designated API endpoint.

**Analysis Value DELETE endpoint**

`DELETE` /actsapi/v1/analysisvalue

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/analysisvalue',
  headers: { 'content-type': 'application/json' },
  body:
   { 
    [analysisValueId1, analysisValueId2, analysisValueId3....]
      },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp

var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/analysisvalue");
var request = new RestRequest(Method.DELETE);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n    [analysisValueId1, analysisValueId2, analysisValueId3....] \r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
> Input JSON Body

```json

  {
    [analysisValueId1, analysisValueId2, analysisValueId3....]
  }

```
> Example Response

```json
{
  "deletedRowCount": 1,
  "notFoundCount": 0,
  "failureCount": 0,
  "errorMessage" : []
}

```


### 5. Emission Factor Table 

This section guides you through the process of removing/deleting the existing records from the Emission Factor table using the designated API endpoint.

**Emission Factor DELETE endpoint**

`DELETE` /actsapi/v1/emissionfactor

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/emissionfactor',
  headers: { 'content-type': 'application/json' },
  body:
   { 
    "emissionFactorId": "number"
      },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp

var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/emissionfactor");
var request = new RestRequest(Method.DELETE);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n    \"emissionFactorId\": \"number\"\r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
> Input JSON Body

```json

  {
    "emissionFactorId": "number"
  }

```
> Example Response

```json
{
	"insertedRowCount" : 0 , 
	"updatedRowCount" : 0 ,
	"deletedRowCount" : 1 ,
	"failureCount" : 0 ,
	"errorMessage" : []
}

```

### 6. Equipment Analysis Table 

This section guides you through the process of removing/deleting the existing records from the Equipment Analysis table using the designated API endpoint.

**Equipment Analysis DELETE endpoint**

`DELETE` /actsapi/v1/equipmentanalysis

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/equipmentanalysis',
  headers: { 'content-type': 'application/json' },
  body:
   { 
    [equipmentAnalysisId1, equipmentAnalysisId2, equipmentAnalysisId3....]
      },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp

var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/equipmentanalysis");
var request = new RestRequest(Method.DELETE);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n    [equipmentAnalysisId1, equipmentAnalysisId2, equipmentAnalysisId3....] \r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
> Input JSON Body

```json

  {
    [equipmentAnalysisId1, equipmentAnalysisId2, equipmentAnalysisId3....]
  }

```
> Example Response

```json
{
  "deletedRowCount": 1,
  "notFoundCount": 0,
  "failureCount": 0,
  "errorMessage" : []
}

```

### 7. Equipment Requirement Table 

This section guides you through the process of removing/deleting the existing records from the Equipment Requirement table using the designated API endpoint.

**Equipment Requirement DELETE endpoint**

`DELETE` /actsapi/v1/equipmentrequirement

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/equipmentrequirement',
  headers: { 'content-type': 'application/json' },
  body:
   { 
    [equipmentRequirementId1, equipmentRequirementId2, equipmentRequirementId3....]
      },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp

var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/equipmentrequirement");
var request = new RestRequest(Method.DELETE);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n    [equipmentRequirementId1, equipmentRequirementId2, equipmentRequirementId3....] \r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
> Input JSON Body

```json

  {
    [equipmentRequirementId1, equipmentRequirementId2, equipmentRequirementId3....]
  }

```
> Example Response

```json
{
  "deletedRowCount": 1,
  "notFoundCount": 0,
  "failureCount": 0,
  "errorMessage" : []
}

```

### 8. Facility Analysis Table 

This section guides you through the process of removing/deleting the existing records from the Facility Analysis table using the designated API endpoint.

**Facility Analysis DELETE endpoint**

`DELETE` /actsapi/v1/facilityanalysis

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/facilityanalysis',
  headers: { 'content-type': 'application/json' },
  body:
   { 
    [facilityAnalysisId1, facilityAnalysisId2, facilityAnalysisId3....]
      },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp

var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/facilityanalysis");
var request = new RestRequest(Method.DELETE);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n    [facilityAnalysisId1, facilityAnalysisId2, facilityAnalysisId3....] \r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
> Input JSON Body

```json

  {
    [facilityAnalysisId1, facilityAnalysisId2, facilityAnalysisId3....]
  }

```
> Example Response

```json
{
  "deletedRowCount": 1,
  "notFoundCount": 0,
  "failureCount": 0,
  "errorMessage" : []
}

```

### 9. Facility Regulation Table 

This section guides you through the process of removing/deleting the existing records from the Facility Regulation table using the designated API endpoint.

**Facility Regulation DELETE endpoint**

`DELETE` /actsapi/v1/facilityregulation

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/facilityregulation',
  headers: { 'content-type': 'application/json' },
  body:
   { 
    [facilityRegulationId1, facilityRegulationId2, facilityRegulationId3....]
      },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp

var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/facilityregulation");
var request = new RestRequest(Method.DELETE);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n    [facilityRegulationId1, facilityRegulationId2, facilityRegulationId3....] \r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
> Input JSON Body

```json

  {
    [facilityRegulationId1, facilityRegulationId2, facilityRegulationId3....]
  }

```
> Example Response

```json
{
  "deletedRowCount": 1,
  "notFoundCount": 0,
  "failureCount": 0,
  "errorMessage" : []
}

```

### 10. Operation Table 

This section guides you through the process of removing/deleting the existing records from the Operation table using the designated API endpoint.

**Operation DELETE endpoint**

`DELETE` /actsapi/v1/operation

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/operation',
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

var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/operation");
var request = new RestRequest(Method.DELETE);
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
  "deletedRowCount": 1,
  "notFoundCount": 0,
  "failureCount": 0,
	"errorMessage" : []
}

```

### 11. Regulation Table 

This section guides you through the process of removing/deleting the existing records from the Regulation table using the designated API endpoint.

**Regulation DELETE endpoint**

`DELETE` /actsapi/v1/regulation

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/regulation',
  headers: { 'content-type': 'application/json' },
  body:
   { [regulationId1, regulationId2, regulationId3....]
	 },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/regulation");
var request = new RestRequest(Method.DELETE);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n   [regulationId1, regulationId2, regulationId3....]\r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body

```json
  {
    [regulationId1, regulationId2, regulationId3....]
  }
```
> Example Response

```json
{
  "deletedRowCount": 1,
  "notFoundCount": 0,
  "failureCount": 0,
  "errorMessage" : []
}
```

### 12. Regulation Attribute Table 

This section guides you through the process of removing/deleting the existing records from the Regulation Attribute table using the designated API endpoint.

**Regulation Attribute DELETE endpoint**

`DELETE` /actsapi/v1/regulationattribute

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/regulationattribute',
  headers: { 'content-type': 'application/json' },
  body:
   { 
    [regulationAttributeId1, regulationAttributeId2, regulationAttributeId3....]
      },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp

var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/regulationattribute");
var request = new RestRequest(Method.DELETE);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n    [regulationAttributeId1, regulationAttributeId2, regulationAttributeId3....] \r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
> Input JSON Body

```json

  {
    [regulationAttributeId1, regulationAttributeId2, regulationAttributeId3....]
  }

```
> Example Response

```json
{
  "deletedRowCount": 1,
  "notFoundCount": 0,
  "failureCount": 0,
  "errorMessage" : []
}

```

### 13. Requirement Table 

This section guides you through the process of removing/deleting the existing records from the Requirement table using the designated API endpoint.

**Requirement DELETE endpoint**

`DELETE` /actsapi/v1/requirement

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/requirement',
  headers: { 'content-type': 'application/json' },
  body:
   { [requirementId1, requirementId2, requirementId3....]
	 },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/requirement");
var request = new RestRequest(Method.DELETE);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n   [requirementId1, requirementId2, requirementId3....]\r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body

```json
  {
    [requirementId1, requirementId2, requirementId3....]
  }
```
> Example Response

```json
{
  "deletedRowCount": 1,
  "notFoundCount": 0,
  "failureCount": 0,
  "errorMessage" : []
}
```

### 14. Requirement Limit Table 

This section guides you through the process of removing/deleting the existing records from the Requirement Limit table using the designated API endpoint.

**Requirement Limit DELETE endpoint**

`DELETE` /actsapi/v1/requirementlimit

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/requirementlimit',
  headers: { 'content-type': 'application/json' },
  body:
   { [requirementLimitId1, requirementLimitId2, requirementLimitId3....]
	 },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/requirementlimit");
var request = new RestRequest(Method.DELETE);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n   [requirementLimitId1, requirementLimitId2, requirementLimitId3....]\r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> Input JSON Body

```json
  {
    [requirementLimitId1, requirementLimitId2, requirementLimitId3....]
  }
```
> Example Response

```json
{
  "deletedRowCount": 1,
  "notFoundCount": 0,
  "failureCount": 0,
  "errorMessage" : []
}
```

### 15. Requirement Person Table 

This section guides you through the process of removing/deleting the existing records from the Requirement Person table using the designated API endpoint.

**Requirement Person DELETE endpoint**

`DELETE` /actsapi/v1/requirementperson

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/actsapi/v1/requirementperson',
  headers: { 'content-type': 'application/json' },
  body:
   { 
    [requirementPersonId1, requirementPersonId2, requirementPersonId3....]
      },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp

var client = new RestClient("https://[tenant].actsapi.intelex.com/actsapi/v1/requirementperson");
var request = new RestRequest(Method.DELETE);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n    [requirementPersonId1, requirementPersonId2, requirementPersonId3....] \r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
> Input JSON Body

```json

  {
    [requirementPersonId1, requirementPersonId2, requirementPersonId3....]
  }

```
> Example Response

```json
{
  "deletedRowCount": 1,
  "notFoundCount": 0,
  "failureCount": 0,
  "errorMessage" : []
}

```