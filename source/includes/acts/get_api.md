## GET API's 

The following GET APIs are used to fetch the data from the respective tables. 

### 1. Attribute Type API GET Endpoint 

All data from the Attribute Type table will be returned from the endpoint below. You can optionally fetch specific data by including Attribute ID’s and Attribute Types. The Attribute Type endpoint supports pagination.

#### Attribute Type API's Filter Option 

Parameter | Description
--------- | -----------
AttributeID  | Attribute ID is one of the filter parameter is a integer data type 
AttributeTypes | Attribute Types is also one of the option for filter parameter is a string data type 

> Example Of AttributeType GET Endpoint Without Pagination: 

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/AttributeType
```

> Example Of AttributeType GET Endpoint With Pagination and Filter Option: 

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/AttributeType?PageNumber=1&PageSize=500&attributeTypeIDs="int data"&attributeTypes="string data" 
```

### 2.Compound API GET Endpoint

All data from the Compound table will be returned from the endpoint below. You can optionally fetch specific data by including compound ID’s, compound Type IDs, compound status IDs, compound Names, external identifiers, or CAS number. The Compound endpoint supports pagination.

##### Compound API's Filter Option

Parameter | Description
--------- | -----------
CompoundID  | Compound ID is one of the unique identifier for this compound record 
CompoundTypeIDs | Compound TYpe IDs is the unique identifier of the associated compound type and is a second filter parameter option 
CompoundStatusIDs | Compound Status IDs is the unique identifier of the associated compound status
CompoundNames | Compound Names The name of the compound which is a string type data and is one among the parameter for filter option
ExternalIdentifiers |  External Identifiers is a unique identifier for this record to an external data system 
CASNumber | CAS Number is a Chemical Abstract Service number for the compound 

> Example Of Compound GET Endpoint Without Pagination: 

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/Compound
```

> Example Of Compound GET Endpoint With Pagination and Filter Option: 

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/Compound? PageNumber=1&PageSize=500&compoundIDs="int data"&compoundTypeIDs="int data"&compoundstatusIDs="int data"&compoundNames="string data"&externalIdentifier="int"&CAS="string data"
```

### 3.Emission Category API GET Endpoint 

All data from the Emission Category table will be returned from the endpoint below. You can optionally fetch specific data by including the emission category ID. The Emission Category endpoint supports pagination.

#### Emission Category API's Filter Option 

Parameter | Description
--------- | -----------
EmissionCategoryID  | Emission Category ID is one of the unique identifier for this emission category record and is one of the filter option provided for Emission Category



> Example Of EmissionCategory GET Endpoint Without Pagination: 

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/EmissionCategory
```
> Example Of EmissionCategory GET Endpoint With Pagination and Filter Option:

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/EmissionCategory/{int data – Emission Category ID}
```

### 4.Emission Type API GET Endpoint

All data from the Emission type table will be returned from the endpoint below. You can optionally fetch specific data by including the emission type ID. The Emission Type endpoint supports pagination.

#### Emission Type API's Filter Option 

Parameter | Description
--------- | -----------
EmissionTypeID  | Emission Type ID is one of the type of emissions and is the one of the filter option provided for Emission Type 

> Example Of EmissionType GET Endpoint Without Pagination: 

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/EmissionType
```

> Example Of EmissionType GET Endpoint With Pagination and Filter Option:

```
https: //{tenant}.actsapi.intelex.com/API-develop/v1/EmissionType?PageNumber=1&PageSize=500&emissionTypeID={int data value}
```

### 5.Equipment API GET Endpoint 

All data from the Equipment table will be returned from the endpoint below. You can optionally fetch specific data by including the equipment ID. The Equipment endpoint supports pagination.

##### Equipment API's Filter Option

Parameter | Description
--------- | -----------
EquipmentID  | Equipment ID is one of the unique identifier for this equipment record

> Example Of Equipment GET Endpoint Without Pagination: 

```
https: //{tenant}.actsapi.intelex.com/API-develop/v1/Equipment
``` 

> Example Of Equipment GET Endpoint With Pagination and Filter Option:

```
https: //{tenant}.actsapi.intelex.com/API-develop/v1/Equipment?PageNumber=1&PageSize=500&equipmentID={int data value}
```

### 6.Equipment Status API GET Endpoint

All data from the Equipment Status table will be returned from the endpoint below. You can optionally fetch specific data by including the equipment status ID and equipment status value. The Equipment Status endpoint supports pagination.

##### Equipment Status API's Filter Option

Parameter | Description
--------- | -----------
EquipmentStatusID  | Equipment Status ID is one of the unique identifier for this equipment status record
EquipmentStatus  | Equipment Status is one of the identifier for the status of the equipment 

> Example Of EquipmentStatus GET Endpoint Without Pagination: 

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/EquipmentStatus
```

> Example Of EquipmentStatus GET Endpoint With Pagination and Filter Option:

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/EquipmentStatus?PageNumber=1&PageSize=500&EquipmentStatusIDs="int data"&EquipmentStatus="string data"
```

### 7.Equipment Type API GET Endpoint

All data from the Equipment Type table will be returned from the endpoint below. You can optionally fetch specific data by including the equipment type ID and equipment types value. The Equipment type endpoint supports pagination.

##### Equipment Type API's Filter Option

Parameter | Description
--------- | -----------
EquipmentTypeID  | Equipment Type ID is one of the unique identifier for this equipment type record
EquipmentTypes  | Equipment Types is one of the filter option and the parameter is for the type of the equipment 

> Example Of EquipmentType GET Endpoint Without Pagination: 

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/EquipmentType
```

> Example Of EquipmentType GET Endpoint With Pagination and Filter Option:

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/EquipmentType?PageNumber=1&PageSize=500&EquipmentTypeIDs="int data"&EquipmentType="string data"
```

### 8.Operation API GET Endpoint 

All data from the Operation table will be returned from the endpoint below. You can optionally fetch specific data by including the operation ids, operation type ids, emission type ids, emission category ids, unit ids, equipment ids, last modified start date and last modified end date. The Operation endpoint supports pagination.

> Example Of Operation GET Endpoint Without Pagination: 

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/Operation
```

> Example Of Operation GET Endpoint With Pagination and Filter Option:

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/ Operation?PageNumber =1&PageSize=500&OperationIDs="int data"&OperationTypeIDs=”string data "&EmissionTypeIDs="int data”&EmissionCategoryIDs="int data”&UnitIDs="int data"&EquipmentIDs="int data"&LastModifiedStartDate=”string format – date time data"&LastModifiedEndDate="string format – date time data" 
```

### 9.Unit API GET Endpoint 

All data from the Unit table will be returned from the endpoint below. You can optionally fetch specific data by including the unit ids, unit type ids and units. The Unit type endpoint supports pagination.

##### Unit API's Filter Option

Parameter | Description
--------- | -----------
UnitID  | Unit ID is one of the unique identifier for this Unit record
UnitTypeIDs  | Unit Type IDs is the unique identifier of the associated unit type 
Units  | Units is one of the filter option and the parameter is for the Name of the Unit 

> Example Of Unit GET Endpoint Without Pagination: 

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/Unit
```

> Example Of Unit GET Endpoint With Pagination and Filter Option:

```
https: // {tenant}.actsapi.intelex.com/API-develop/v1/Unit?PageNumber=1&PageSize=500&UnitIDs="int data"&UnitTypeIDs="int data" &Units="string data"
```

### Sample Result Set Of One Of the API Endpoint 

> Example Output Response

```json
{
    "currentPage": 1,
    "totalPages": "int",
    "currentPageSize": 500,
    "maxAPIPageSize": 500,
    "totalCount": "int",
    "hasPrevious": "boolean",
    "hasNext": "boolean",
    "data":
[
    {
        "EquipmentAttributeId": "int",
        "EquipmentId": "int",
        "AttributeTypeId": "int",
		"EquipmentAttribute":"string",
        "DataLockTypeId": "datetime",
        "LastModifiedDate": "datetime",
        "ExternalIdentifier": "string",
		"Comments":"string"
    }
]
}
```