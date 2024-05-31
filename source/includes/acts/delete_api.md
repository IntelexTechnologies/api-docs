## Remove or Delete data from Database Table

This section outlines the available Delete APIs designed for modifying ACTS data by deleteing or removing the data. These APIs offer options for removing existing records from the mentioned tables. 

* To remove the existing records, use the primary key of the record.

In the current release, one DELETE API End point is provided to remove or delete from the following table 

* Emission Factor
* Operation

DELETE requests to these endpoints should be formatted in JSON.

### 1. Emission Factor Table 

This section guides you through the process of removing/deleting the existing records from the Emission Factor table using the designated API endpoint.

**Emission Factor DELETE endpoint**

`DELETE` /api/v1/emissionfactor

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/v1/emissionfactor',
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

var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/emissionfactor");
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


### 2. Operation Table 

This section guides you through the process of removing/deleting the existing records from the Operation table using the designated API endpoint.

**Operation DELETE endpoint**

`DELETE` /api/v1/operation

> Example Request & JSON Input Body 

```javascript
var request = require("request");

var options = { method: 'DELETE',
  url: 'https://[tenant].actsapi.intelex.com/v1/operation',
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

var client = new RestClient("https://[tenant].actsapi.intelex.com/v1/operation");
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