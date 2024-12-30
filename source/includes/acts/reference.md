## Reference

The Intelex ACTS API provides endpoints in ACTS, with it's own URL for access. If you currently use the Intelex API, you will not be able to use the ACTS API unless you have Admin access to ACTS. At the same time, you can use the ACTS API without any permission for Intelex V6.  

Our API has predictable, resource-oriented URLs, and uses HTTP response codes to indicate API errors. We use built-in HTTP features, Token based authentication and HTTP verbs, which are understood by off-the-shelf HTTP clients. JSON is returned by all API responses, including errors.

### Getting Started with ACTS API

>API Endpoint - In the URL the tenant is the individual unique tenants based on the tenants they are specifying 

```
https://[tenant].actsapi.intelex.com/actsapi/v1/
```

To begin using the Intelex API you will need:

* A valid Intelex ACTS user account
* The full URL to your Intelex ACTS API and system
* The full URL to authentication endpoint
* Understanding of the Intelex ACTS Application.

### ACTS API Authentication

>Example Requests:

```CSharp 
Body for Authentication Endpoint
{"client_id":"Client ID Data",
"client_secret":"Client Secret Data",
"audience":"https://*.intelex.com/ACTSAPI",
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

Intelex ACTS API uses tokens based authentication. Only ACTS Admin users can access the API. 

During the authentication process, the client provides the 'client id' and 'client secret' to the authentication endpoint, along with the audience and grant type, as demonstrated above. In response, the API furnishes an access token that comes with a specified time limit. This authentication is exclusively applicable to admin users. After successful authentication, users gain unrestricted access to all ACTS API endpoints till the token expiration.

All interactions with the API are required to occur via HTTPS, and any API requests lacking proper authentication will result in failure. Data security is meticulously overseen by the ACTS platform, ensuring that API requests grant identical administrative access as enjoyed by authenticated ACTS admin users.

The user authentication endpoint uses a POST to generate the access token [bearer token].

### ACTS API Versioning

When we make any new changes to the API, we release new versions. The current version of the ACTS API  is v1 and can be determined with our API base path /actsapi/v1/.

>Example API endpoint : https://[tenant].actsapi.intelex.com/actsapi/v1/[endpoint-name]

### ACTS API Software & Certificate Version Details
 
The ACTS API SSL Certification is incompatible with following version of the python 3.10 + . If we use the python version < 3.10 the SSL handshake works for ACTS API.Currently this is considered as one of the limitation.

### API's and Associated Database Tables 

This ACTS API release includes 23 GET enpoints and 16 POST endpoints, along with the authentication endpoint described earlier. The tables that can be queried and updated are as follows. 

Database Tables supporting GET requests 

1. Attribute Type					   
2. Compound 				    
3. Emission Category
4. Emission Factor Table			     
5. Emission Type
6. Equipment 
7. Equipment Attribute
8. Equipment Status
9. Equipment Type
10. Facility
11. Facility Attribute
12. Operation 
13. Operation Type
14. Query Results
15. Unit
16. Workflow 
17. Workflow Answer
18. Workflow Equipment
19. Workflow Facility
20. Workflow Person
21. Workflow Question
22. Workflow Question Category
23. Workflow Type

Database Tables supporting POST requests 

1. Analysis
2. Analysis Compound
3. Emission Factor
4. Emissions Recalculate By Equipment
5. Emissions Recalculate By Operation
6. Equipment
7. Equipment Analysis
8. Equipment Attribute
9. Facility
10. Facility Attribute
11. Operation
12. Workflow
13. Workflow Answer
14. Workflow Equipment
15. Workflow Facility
16. Workflow Person 
