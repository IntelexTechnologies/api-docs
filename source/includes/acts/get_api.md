## GET API's Endpoints

This section outlines the various GET APIs available for fetching data from different tables. Each API provides the capability to retrieve specific data based on provided parameters. Pagination support is available for managing large datasets effectively.

### 1. Attribute Type Data Retrieval 

This section outlines the process of retrieving data from the Attribute Type table using the dedicated API endpoint. The endpoint facilitates the retrieval of all data from the Attribute Type table or enables the selection of specific information by including Attribute IDs and Attribute Types. Additionally, the Attribute Type endpoint supports pagination to effectively manage larger datasets.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://intelex_acts_api_url/api/v1/attributetype' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://intelex_acts_api_url/api/v1/attributetype");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Example Response

```json
{
	"value": [
	  {
		"name": "string",
		"kind": "string",
		"url": "string"
	  }
	]
}
```

**API Endpoints**

`GET` /api/v1/AttributeType

**API Endpoints with pagination and filters**

`GET` /api/v1/AttributeType?pagenumber={int data value}&pagesize={int data value}&attributeTypeIDs={int data value}&attributeTypes={string data value}

***Query parameters***<br />

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
attributeTypeIDs | int |
attributeTypes | string |

### 2. Compound API Data Retrieval

This section guides you through the process of fetching data from the Compound table using the dedicated API endpoint. The endpoint offers the flexibility to retrieve all data from the Compound table or selectively acquire information by including Compound IDs, Compound Type IDs, Compound Status IDs, Compound Names, External Identifiers, or CAS Numbers. Additionally, the Compound endpoint is equipped with pagination capabilities to facilitate efficient management of substantial datasets.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://intelex_acts_api_url/api/v1/compound' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://intelex_acts_api_url/api/v1/compound");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Example Response

```json
{
	"value": [
	  {
		"name": "string",
		"kind": "string",
		"url": "string"
	  }
	]
}
```

**API Endpoints**

`GET` /api/v1/compound

**API Endpoints with pagination and filters**

`GET` /api/v1/compound?pagenumber={int data value}&pagesize={int data value}&compoundIDs={int data value}&compoundTypeIDs={int data value}&compoundstatusIDs={int data value}&compoundNames={string data value}&externalIdentifier={int data value}&CAS={string data value}

***Query parameters***<br />

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
compoundIDs | int |
compoundTypeIDs | int |
compoundstatusIDs | int |
compoundNames | string |
externalIdentifier | int |
CAS | string |

### 3. Emission Category Data Retrieval

This section elaborates on how to obtain data from the Emission Category table using the designated API endpoint. The endpoint allows you to retrieve all data from the Emission Category table or selectively acquire information by providing the Emission Category ID. Moreover, the Emission Category endpoint features pagination to facilitate efficient management of substantial datasets.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://intelex_acts_api_url/api/v1/emissioncategory' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);
```

```csharp
var client = new RestClient("https://intelex_acts_api_url/api/v1/emissioncategory");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Example Response

```json
{
	"value": [
	  {
		"name": "string",
		"kind": "string",
		"url": "string"
	  }
	]
}
```

**API Endpoints**

`GET` /api/v1/emissioncategory

**API Endpoints with pagination and filters**

`GET` /api/v1/emissioncategory/pagenumber={int data value}&pagesize={int data value}&emissionCategoryID={int data value}

***Query parameters***<br />

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
emissionCategoryID | int |

### 4. Emission Type Data Retrieval

This section guides you through the process of fetching data from the Emission Type table using the dedicated API endpoint. The endpoint enables you to retrieve data from the entire Emission Type table or selectively obtain information by including Emission Type IDs. Additionally, the Emission Type endpoint is equipped with pagination capabilities to facilitate the handling of extensive datasets.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://intelex_acts_api_url/api/v1/emissiontype' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://intelex_acts_api_url/api/v1/emissiontype");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Example Response

```json
{
	"value": [
	  {
		"name": "string",
		"kind": "string",
		"url": "string"
	  }
	]
}
```

**API Endpoints**

`GET` /api/v1/emissiontype

**API Endpoints with pagination and filters**

`GET` /api/v1/emissiontype?pagenumber={int data value}&pagesize={int data value}&emissionTypeID={int data value}

***Query parameters***<br />

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
emissionTypeID | int |

### 5. Equipment Data Retrieval

This section provides guidance on retrieving data from the Equipment table using the designated API endpoint. The endpoint allows you to retrieve all data from the Equipment table or specify specific data based on equipment IDs. Additionally, the Equipment endpoint offers pagination support to facilitate the handling of substantial datasets.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://intelex_acts_api_url/api/v1/equipment' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://intelex_acts_api_url/api/v1/equipment");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Example Response

```json
{
	"value": [
	  {
		"name": "string",
		"kind": "string",
		"url": "string"
	  }
	]
}
```

**API Endpoints**

`GET` /api/v1/equipment

**API Endpoints with pagination and filters**

`GET` /api/v1/equipment?pagenumber={int data value}&pagesize={int data value}&equipmentID={int data value}

***Query parameters***<br />

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
equipmentID | int |


### 6. Equipment Status Data Retrieval

All data from the Equipment Status table will be returned from the endpoint below. You can optionally fetch specific data by including the equipment status ID and equipment status value. The Equipment Status endpoint supports pagination.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://intelex_acts_api_url/api/v1/equipmentstatus' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://intelex_acts_api_url/api/v1/equipmentstatus");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Example Response

```json
{
	"value": [
	  {
		"name": "string",
		"kind": "string",
		"url": "string"
	  }
	]
}
```

**API Endpoints**

`GET` /api/v1/equipmentstatus

**API Endpoints with pagination and filters**

`GET` /api/v1/equipmentstatus?pagenumber={int data value}&pagesize={int data value}&equipmentStatusIDs={int data value}&equipmentStatus="{string data value}

***Query parameters***<br />

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
equipmentStatusIDs | int |
equipmentStatus | string |

### 7. Equipment Type Data Retrieval

All data from the Equipment Type table will be returned from the endpoint below. You can optionally fetch specific data by including the equipment type ID and equipment types value. The Equipment type endpoint supports pagination.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://intelex_acts_api_url/api/v1/equipmenttype' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://intelex_acts_api_url/api/v1/equipmenttype");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Example Response

```json
{
	"value": [
	  {
		"name": "string",
		"kind": "string",
		"url": "string"
	  }
	]
}
```

**API Endpoints**

`GET` /api/v1/equipmenttype

**API Endpoints with pagination and filters**

`GET` /api/v1/equipmenttype?pagenumber={int data value}&pagesize={int data value}&equipmentTypeIDs={int data value}&equipmentType={string data value}

***Query parameters***<br />

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
equipmentTypeIDs | int |
equipmentType | string |

### 8. Operation Data Retrieval

All data from the Operation table will be returned from the endpoint below. You can optionally fetch specific data by including the operation ids, operation type ids, emission type ids, emission category ids, unit ids, equipment ids, last modified start date and last modified end date. The Operation endpoint supports pagination.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://intelex_acts_api_url/api/v1/operation' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://intelex_acts_api_url/api/v1/operation");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Example Response

```json
{
	"value": [
	  {
		"name": "string",
		"kind": "string",
		"url": "string"
	  }
	]
}
```

**API Endpoints**

`GET` /api/v1/operation

**API Endpoints with pagination and filters**

`GET` /api/v1/operation?pagenumber={int data value}&pagesize={int data value}&operationIDs={int data value}&operationTypeIDs={string data value}&emissionTypeIDs={int data value}&emissionCategoryIDs={int data value}&unitIDs={int data value}&equipmentIDs={int data value}&lastModifiedStartDate={string data value}&lastModifiedEndDate={string data value}

***Query parameters***<br />

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
operationIDs | int |
operationTypeIDs | string |
emissionTypeIDs | int |
emissionCategoryIDs | int |
unitIDs | int |
equipmentIDs | int |
lastModifiedStartDate | string | Date time format "mm/dd/yyyy"
lastModifiedEndDate | string | Date time format "mm/dd/yyyy"

### 9. Unit Data Retrieval

This section outlines how to retrieve data from the Unit table using the provided endpoint. You have the flexibility to fetch specific data by including unit IDs, unit type IDs, and units. The Unit type endpoint also supports pagination for managing large datasets effectively.

> Example Request

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'https://intelex_acts_api_url/api/v1/unit' };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://intelex_acts_api_url/api/v1/unit");
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
```

> Example Response

```json
{
	"value": [
	  {
		"name": "string",
		"kind": "string",
		"url": "string"
	  }
	]
}
```

**API Endpoints**

`GET` /api/v1/unit

**API Endpoints with pagination and filters**

`GET` /api/v1/unit?pagenumber={int data value}&pagesize={int data value}&unitIDs={int data value}&unitTypeIDs={int data value}&units={string data value}

***Query parameters***<br />

Attribute | Type | Description
--------- | ---- | -----------
PageNumber | int | Page number of the results to fetch.
PageSize | int | The number of results per page
unitIDs | int |
unitTypeIDs | int |
units | string |