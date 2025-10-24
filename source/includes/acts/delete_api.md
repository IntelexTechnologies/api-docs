## Remove or Delete data from Database Table

This section outlines the available Delete APIs designed for modifying ACTS data by deleteing or removing the data. These APIs offer options for removing existing records from the mentioned tables. 

* To remove the existing records, use the primary key of the record.

As per the current release, DELETE APIs End points are provided to delete from the following tables: 

* Analysis
* Analysis Compound
* Emission Factor
* Equipment Analysis
* Operation
* Regulation
* Requirement
* Requirement Limit

DELETE requests to these endpoints should be formatted in JSON.

### 1. Analysis Table 

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

### 2. Analysis Compound Table 

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


### 3. Emission Factor Table 

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

### 4. Equipment Analysis Table 

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
    [equipmentanalysisId1, equipmentanalysisId2, equipmentanalysisId3....]
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
request.AddParameter("application/json", "{\r\n    [equipmentanalysisId1, equipmentanalysisId2, equipmentanalysisId3....] \r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
> Input JSON Body

```json

  {
    [equipmentanalysisId1, equipmentanalysisId2, equipmentanalysisId3....]
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

### 5. Operation Table 

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

### 6. Regulation Table 

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

### 7. Requirement Table 

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

### 8. Requirement Limit Table 

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