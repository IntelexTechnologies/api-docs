## ACTS API Reference

The Intelex ACTS API provides endpoints in ACTS, with it's own URL for access. If you currently use the Intelex API, you will not be able to use the ACTS API unless you have Admin access to ACTS. At the same time, you can use the ACTS API without any permission for Intelex V6.  

Our API has predictable, resource-oriented URLs, and uses HTTP response codes to indicate API errors. We use built-in HTTP features, Token based authentication and HTTP verbs, which are understood by off-the-shelf HTTP clients. JSON is returned by all API responses, including errors.

### Getting Started with ACTS API

To begin using the Intelex API you will need:

* A valid Intelex ACTS user account
* The full URL to your Intelex ACTS API and system
* A basic understanding of the Intelex ACTS API Application.

### ACTS API Authentication

>API Endpoint - replace **intelex_ACTS API url** with the full URL path to your Intelex system

```
https://{tenant}.actsapi.intelex.com
```

>Example Requests:

```CSharp 
//JSON Body for Authentication Endpoint
{"client_id":"Client ID Data",
"client_secret":"Client Secret Data",
"audience":"https://{tenant}.intelex.com/API-release",
"grant_type":"client_credentials"}
```
>Example Response:

```json
{
    "access_token": "Generated Bearer Access Token Used For Validation",
    "expires_in": "Token Expiry Time In Seconds",
    "token_type": "Bearer"
}
```

Intelex's ACTS API uses tokens based authentication. Only ACTS Admin users can access the API. 

During the authentication process, the client provides the 'client id' and 'client secret' to the authentication endpoint, along with the audience and grant type, as demonstrated above. In response, the API furnishes an access token that comes with a specified time limit. This authentication is exclusively applicable to admin users. After successful authentication, users gain unrestricted access to all ACTS API endpoints.

All interactions with the API are required to occur via HTTPS, and any API requests lacking proper authentication will result in failure. Data security is meticulously overseen by the ACTS platform, ensuring that API requests grant identical administrative access as enjoyed by authenticated ACTS admin users.

The user authentication endpoint uses a POST to generate the access token [bearer token]. 

>Authentication API Endpoint - https: // dev-intelex.us.auth0.com/oauth/token 

### ACTS Versioning

When we make backwards-incompatible changes to the API, we release new versions. The current version of the ACTS API  is v1 and can be determined with our API base path /api/v1/.

>Example API Endpoint : https://{tenant}.actsapi.intelex.com/API/**/v1/TableName

### API's and Associated Database Tables 

This ACTS API release includes 11 GET enpoints and 4 POST endpoints, along with the authentication endpoint described above. The tables you can query and update are as follows. 

Database Tables Supporting GET requests 

1. Operation 					   
2. Equipment				    
3. Emission Type			     
4. Emission Category
5. Equipment Status
6. Unit
7. Attribute Type 
8. Equipment Type
9. Compound

Database Tables Supporting POST requests 

1. Equipment
2. Operation
3. Facility
4. Facility Attribute

### Types Of API's and General URL 

GET API’s In the current ACTS – API release overall there have been planned for 11 GET API’s 

> Example GET API Endpoint : https://{tenant}.actsapi.intelex.com/API-develop/v1/{Table Object}/{Fetch_Based_On_ID’s} 



POST API’s in the current release we are including 4 POST API’s. These API’s helps to edit and make updates in the respective tables. In the POST API the user needs to pass on the input in JSON Format.

The Input JSON body would be something like this 

 >Example Input JSON Body

```json

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
```

> Example POST API Endpoint : https : // {tenant}.actsapi.intelex.com/API-develop/v1/{Table Object}

{Table Object} : Unit , Operation , Emission , Emission Category tables etc 

{API-develop} : develop is the environment 

v1 : Version , First version of the ACTS - API


1. GET API's With Pagination Option 
In this case user can specify the page number and page size where 500 is maximum size of the page. Example output with the page number and page size 

> Example GET API Endpoint : https ://{tenant}.actsapi.intelex.com/API-develop/v1/{Table Object}/{Fetch_Based_On_ID’s}/ ?PageNumber=1&PageSize=50 

{Table Object} : Unit , Operation , Emission , Emission Category tables etc 

{API-develop} : develop is the environment 

v1 : Version , First version of the ACTS - API

{Fetched_Based_On_ID's} : User can specify the mentioned specific ID to get that particular data

{Page Number} and {Page Size} : User can specify the page number and page size 

> Example OutPut Response 

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