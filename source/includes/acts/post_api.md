## Add or Modify Database Table

This section outlines the available POST APIs designed for modifying ACTS data. These APIs offer options for updating existing records and inserting new ones. 

* To insert new records, set the primary key to 0
* To updates to existing records, use the primary key of the record. 

<aside class="notice">
For efficient handling of larger data inserts, it is recommended to perform batch POSTs containing up to 500 rows each. 

Note that excessively large batch POSTs may encounter throttling or failure, depending on system resources.
</aside>

In the current release, four POST APIs End points are provided to add or update following table 

* Equipment
* Operation
* Facility
* Facility Attribute 
 
POST requests to these endpoints should be formatted in JSON.

### 1. Equipment Table 

This section guides you through the process of modifying existing equipment records or adding new entries to the Equipment table using the designated API endpoint.

**Equipment POST endpoint**

`POST` api/development/v1/equipment

### 2. Operation Table 

This section outlines the process of adding new entries or modifying existing records within the Operation table using the dedicated API endpoint.

**Operation POST Endpoint**

`POST` api/development/v1/Operation

### 3. Facility Table 

This section outlines the process of adding new entries or modifying existing records within the Facility table using the dedicated API endpoint.

**Facility POST Endpoint**

`POST` api/deelopment/v1/Facility

### 4. Facility Attribute Table 

This section outlines the process of adding new entries or modifying existing records within the Facility Attribute table using the dedicated API endpoint.

**Facility Attribute POST Endpoint**

`POST` api/DEVELOPMENT/v1/FacilityAttribute

### JSON body for both Insert & Update 

If the primary id is zero - "0" then the data we are passing is handled as an insert, shown in the example below, where "EquipmentAttributeId" is passed as "0". 

> Example Input JSON Body For Insert 

```json

[
    {
        "EquipmentAttributeId": 0,
        "EquipmentId": "int",
        "AttributeTypeId": "int",
		"EquipmentAttribute":"string",
        "DataLockTypeId": "datetime",
        "LastModifiedDate": "datetime",
        "ExternalIdentifier": "string",
		"Comments":"string"
    }
]
```

> Example Input JSON Body For Update 

If the primary id is an existing ID - "#####" then the data we are passing is handled as an update, shown in the example below, where "EquipmentAttributeId" is passed as "164". 


```json

[
    {
        "EquipmentAttributeId": 164,
        "EquipmentId": "int",
        "AttributeTypeId": "int",
		"EquipmentAttribute":"string",
        "DataLockTypeId": "datetime",
        "LastModifiedDate": "datetime",
        "ExternalIdentifier": "string",
		"Comments":"string"
    }
]
```

> Example Output For Both Update and Insert 
```
{
	"insertedRowCount" : 2 , 
	"updatedRowCount" : 3 ,
	"failureCount" : 0 ,
	"errorMessage" : []

}

```

> Example Output For When Data Get's Failed To Insert or Update
```
{
	"insertedRowCount" : 0 , 
	"updatedRowCount" : 1 ,
	"failureCount" : 1 ,
	"errorMessage" : [
	 "Operation ID : 0, Error: An error occurred while saving the entity changes. See the inner exception for details "
	]
}

```