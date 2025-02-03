## Add or Modify Data

This section outlines the available POST and PATCH endpoints designed for modifying employee and user data. These endpoints support updating existing records and inserting new records. Requests should be formatted in JSON.

> User Management API Endpoint - replace **intelex_object** with the system name of your object

```
https://intelex_url/api/v2/EmployeeUserAccess
```

### Add Data

> Example Request

```javascript
var request = require("request");

var options = { 
  method: 'POST',
  url: 'https://intelex_url/api/v2/EmployeeUserAccess',
  headers: { 'content-type': 'application/json' },
  body: 
  {
    "EmployeeNumber": "001",
    "HomeLocationCode": "001",
    "FirstName": "John",
    "LastName": "Doe",
    "UserId": "jdoe",
    "LoginLocationCode": "001",
    "LicenseType": "Full Access"
  }
};

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://intelex_url/api/v2/EmployeeUserAccess");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n    \"EmployeeNumber\": \"001\",\r\n    \"HomeLocationCode\": \"001\",\r\n    \"FirstName\": \"John\",\r\n    \"LastName\": \"Doe\",\r\n    \"UserId\": \"jdoe\",\r\n    \"LoginLocationCode\": \"001\",\r\n    \"LicenseType\": \"Full Access\"\r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

#### POST /EmployeeUserAccess

##### Body Parameters

| Parameter  | Description                                                                                                      |
| ---------- | ---------------------------------------------------------------------------------------------------------------- |
| field_name | The value you want to set for an employee or user field. Replace _field_name_ with the name of the employee or user field |

See [Request Payload Field Reference](#request-payload-field-reference) for detailed field information.

A successful POST to the EmployeeUserAccess endpoint will respond with a <code>201 Created</code> response code and a json body containing the Id for the created employee and user records.

> Example Response

```json
{
  "Id": "43d1b046-156a-4715-bf96-10f71690a528"
}
```

### Modify Data

> Example Request

```javascript
var request = require("request");

var options = { 
  method: 'PATCH',
  url: 'https://intelex_url/api/v2/EmployeeUserAccess',
  headers: { 'content-type': 'application/json' },
  body: 
  {
    "EmployeeNumber": "001",
    "FirstName": "Jon",
    "IsLocked": true
  }
};

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

```csharp
var client = new RestClient("https://intelex_url/api/v2/EmployeeUserAccess");
var request = new RestRequest(Method.POST);
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\r\n    \"EmployeeNumber\": \"001\",\r\n    \"FirstName\": \"Jon\",\r\n    \"IsLocked\": true\r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

#### PATCH /EmployeeUserAccess({id})

##### URL Parameters

| Parameter              | Description                                        |
| ---------------------- | -------------------------------------------------- |
| employee_id _(optional)_ | The Intelex UID of the employee/user being updated |

<b>NOTE:</b> You may also provide a valid <code>Id</code> <i>or</i> <code>EmployeeNumber</code> in the payload as the identifier used to update the record.

##### Body Parameters

| Parameter  | Description                                                                                                      |
| ---------- | ---------------------------------------------------------------------------------------------------------------- |
| field_name | The value you want to set for and employee or user field. Replace _field_name_ with the name of the employee or user field |

See [Request Payload Field Reference](#request-payload-field-reference) for detailed field information.

A successful PATCH to the EmployeeUserAccess endpoint will respond with a <code>204 No Content</code> response code.

### Request Payload Field Reference

#### Settings Flags

Settings flags are payload fields that configure various behaviors of the user management API request.

Some settings flags may be ignored if the flag is not relevant to the request type. For example, <code>RevokeUserAccess</code> is only applicable to an existing user, so is only applicable in an update (PATCH) request.

<b>All flags default to <code>false</code> unless otherwise noted.</b>

<table>
  <tr>
    <th>Property</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>IgnoreUserAccess</td>
    <td>
      <li>Skips user access creation. Employee record will still be created.</li>
    </td>
  </tr>
  <tr>
    <td>SendEmail</td>
    <td>
      <li>Send a password reset email upon successful user creation.</li>
      <li>Only respected if user access is requested. I.e. <code>IgnoreUserAccess</code> = <code>false</code></li>
    </td>
  </tr>
  <tr>
    <td>RevokeUserAccess</td>
    <td>
      <li>Existing users only. Only respected if user access is requested. </li>
      <li>Revokes access for the specified user.</li>
      <li></li>
    </td>
  </tr>
  <tr>
    <td>ArchiveIfTasksAssigned</td>
    <td>
      <li>Existing users only. Only respected if user access is requested.</li>
      <li></li>
    </td>
  </tr>
  <tr>
    <td>DoNotAddGroupAssignments</td>
    <td>
      <li>Existing employees only.</li>
      <li>Do not assign employee membership to the groups specified in the <code>Groups</code> field.</li>
    </td>
  </tr>
  <tr>
    <td>RemoveFromUnlistedGroups</td>
    <td>
      <li>Existing employees only.</li>
      <li>Remove employee membership from any previously assigned groups that are not specified in the <code>Groups</code> field.</li>
      <li>This field is still respected if <code>DoNotAddGroupAssignments</code> is set.</li>
    </td>
  </tr>
</table>

#### Employee Fields

Payload fields that are associated with the employee record to be created or updated.

Properties denoted with a <code>\*</code> are required and must be included in the payload.

<table>
  <tr>
    <th>Property</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>Flag</td>
    <td>
      <li>Indicates whether employee should be archived in the system:</li>
      <ul>
        <li><code>A</code> = Active employee (default)</li>
        <li><code>I</code> = Inactive (archived) employee</li>
      </ul>
      <li>Archiving an an employee will also remove the associated user's access, if available.</li>
    </td>
  </tr>
  <tr>
    <td><b>EmployeeNumber*</b></td>
    <td>
      <li>Primary Key; Unique identifier of employee.</li>
    </td>
  </tr>
  <tr>
    <td><b>HomeLocationCode*</b></td>
    <td>
      <li>Location Code of the home location of this employee.</li>
      <li>This is the Location field on the employee profile.</li>
    </td>
  </tr>
  <tr>
    <td>Prefix</td>
    <td>
      <li>Prefix of employee (e.g., Mr., Mrs., Ms.)</li>
    </td>
  </tr>
  <tr>
    <td><b>FirstName*</b></td>
    <td>
      <li>First name of employee.</li>
    </td>
  </tr>
  <tr>
    <td><b>LastName*</b></td>
    <td>
      <li>Last name of employee.</li>
    </td>
  </tr>
  <tr>
    <td>MiddleName</td>
    <td>
      <li>Middle name of employee.</li>
    </td>
  </tr>
  <tr>
    <td>DisplayName</td>
    <td>
      <li>Last name of employee.</li>
    </td>
  </tr>
  <tr>
    <td>Suffix</td>
    <td>
      <li>Suffix of employee (e.g., Jr., Sr.)</li>
    </td>
  </tr>
  <tr>
    <td>Email</td>
    <td>
      <li>Email address of employee.</li>
    </td>
  </tr>
  <tr>
    <td>IsSupervisor</td>
    <td>
      <li>Indicates whether employee has direct reports or not.</li>
      <li>Valid values are <code>Y</code> or <code>N</code></li>
    </td>
  </tr>
  <tr>
    <td>EmployeeType</td>
    <td>
      <li>Type of Employee.</li>
      <li>Must be the <code>Name</code> of a valid <code>SysEmployeeType</code> record.</li>
    </td>
  </tr>
  <tr>
    <td>DateOfHire</td>
    <td>
      <li>Date of hire of employee.</li>
      <li>Please speak with your consultant to confirm the date format for your subdomain.</li>
    </td>
  </tr>
  <tr>
    <td>SupervisorNumber</td>
    <td>
      <li>Employee Number of supervisor of employee.</li>
    </td>
  </tr>
  <tr>
    <td>PositionTitle</td>
    <td>
      <li>Job title of employee.</li>
    </td>
  </tr>
  <tr>
    <td>Notes</td>
    <td>
      <li>Open text field found in employee profile.</li>
    </td>
  </tr>
  <tr>
    <td>Contractor</td>
    <td>
      <li>Indicates whether employee is a contractor.</li>
      <li>Valid values are <code>Y</code> or <code>N</code></li>
    </td>
  </tr>
  <tr>
    <td>Company</td>
    <td>
      <li>Company name of employee.</li>
    </td>
  </tr>
  <tr>
    <td>ContractorName</td>
    <td>
      <li>Contractor company name of employee.</li>
    </td>
  </tr>
  <tr>
    <td>ContractExpiry</td>
    <td>
      <li>Contract expiration date of employee.</li>
      <li>Please speak with your consultant to confirm the date format for your subdomain.</li>
    </td>
  </tr>
  <tr>
    <td>InsuranceExpiry</td>
    <td>
      <li>Insurance expiration date of employee.</li>
      <li>Please speak with your consultant to confirm the date format for your subdomain.</li>
    </td>
  </tr>
  <tr>
    <td>ContractorNotes</td>
    <td>
      <li>Open text field found in employee profile.</li>
    </td>
  </tr>
  <tr>
    <td>StreetAddress</td>
    <td>
      <li>Street address of employee.</li>
    </td>
  </tr>
  <tr>
    <td>City</td>
    <td>
      <li>City of employee.</li>
    </td>
  </tr>
  <tr>
    <td>State</td>
    <td>
      <li>State of employee.</li>
    </td>
  </tr>
  <tr>
    <td>ZipCode</td>
    <td>
      <li>Zip code (or postal code) of employee.</li>
    </td>
  </tr>
  <tr>
    <td>Gender</td>
    <td>
      <li>Gender of employee.</li>
    </td>
  </tr>
  <tr>
    <td>DateOfBirth</td>
    <td>
      <li>Date of birth of employee.</li>
      <li>Please speak with your consultant to confirm the date format for your subdomain.</li>
    </td>
  </tr>
  <tr>
    <td>SSN</td>
    <td>
      <li>Social security number of employee.</li>
    </td>
  </tr>
  <tr>
    <td>EmergencyContact</td>
    <td>
      <li>Emergency contact information of employee.</li>
    </td>
  </tr>
  <tr>
    <td>EmergencyPhone</td>
    <td>
      <li>Emergency phone number of employee.</li>
    </td>
  </tr>
  <tr>
    <td>PersonResponsible</td>
    <td>
      <li>Mandatory for Document Control (all platform versions) and Reassign Task (6.2.5 or lower) feature.</li>
      <li>For clients on 6.2.5 or lower, it is recommended to default this value to 1, if not being used.</li>
      <li>See V6 System Administrator User Guide on Intelex Exchange for additional details.</li>
      <li>For New Employee:</li>
      <ul>
        <li>1: Add to Home Locations & all Locations below</li>
        <li>2: Add to Home Location only</li>
        <li>3: Do not add to Person Responsible List (PRL)</li>
      </ul>
      <li>For Existing Employee:</li>
      <ul>
        <li>1: Clear PRL for this employee then add employee to Home Location & all Locations below</li>
        <li>2: Clear PRL for this employee then add employee to Home Location only (does not keep manually added Locations)</li>
        <li>3: Clear PRL for this employee (do not add)</li>
        <li>4: Leave PRL as is (no change)</li>
        <li>5: Replace current Home Location with new Home Location (and keep manually added locations)</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>PhoneNumber</td>
    <td>
      <li>Phone number of employee.</li>
    </td>
  </tr>
  <tr>
    <td>HourlyWage</td>
    <td>
      <li>Hourly wage of employee.</li>
    </td>
  </tr>
  <tr>
    <td>JobCode</td>
    <td>
      <li>Job Code for employee.</li>
    </td>
  </tr>
  <tr>
    <td>WorkStatus</td>
    <td>
      <li>[Legal] Work status of employee.</li>
    </td>
  </tr>
  <tr>
    <td>Groups</td>
    <td>
      <li>Semicolon (;) delimited list of elements that this employee is a member of (excluding Everyone group).</li>
      <li>Each element can be the Caption or GUID of any Group or Location Role.</li>
      <li>Groups includes Security Groups, Roles, Location Roles and Training Workgroups.</li>
      <li>If an element is invalid, the request will fail with validation errors in the response.</li>
      <li>Notation for Location Role: RoleNameOrGUID(LocationCodeOrGUID)</li>
    </td>
  </tr>
</table>

#### User Fields

Payload fields that are associated with the user record to be created or updated if requested (<code>IgnoreUserAccess</code> = <code>false</code>).

<i>If user access is requested,</i> properties denoted with a <code>\*</code> are required and must be included in the payload.

<table>
  <tr>
    <th>Property</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><b>UserId*</b></td>
    <td>
      <li>Used by employee to login to the Intelex system; must be unique.</li>
      <li>Recommendation: Email address of employee.</li>
      <li>Set to email ID for SSO.</li>
    </td>
  </tr>
  <tr>
    <td>IsLocked</td>
    <td>
      <li>Locks or unlocks the user</li>
    </td>
  </tr>
  <tr>
    <td>Password</td>
    <td>
      <li>Password that employee users to log in to the Intelex system.</li>
      <li>Ignores Account Policy rules.</li>
      <li>Password is not required if implementing SSO.</li>
    </td>
  </tr>
  <tr>
    <td>SecondaryPassword</td>
    <td>
      <li>For Electronic Signatures only.</li>
      <li>Stores a secondary password that can be used by electronic signatures.</li>
    </td>
  </tr>
  <tr>
    <td>ForcePasswordChange</td>
    <td>
      <li>If set to true, user will be forced to change his/her password upon his/her next successful log in.</li>
      <li>User access updated through EDIS will leave Force Password Change untouched if it the flag is anything other than the characters mentioned above.</li>
      <li>1 = User will be forced to change his/her password on next log in (also accepts values "Y", "y", "T", "t").</li>
      <li>0 (or null) = User will NOT be forced to change his/her password (also accepts values "N", "n", "F", "f").</li>
    </td>
  </tr>
  <tr>
    <td><b>LoginLocationCode*</b></td>
    <td>
      <li>Location Code of the login location of this employee.</li>
      <li>This is the Logon Location field on the user profile.</li>
    </td>
  </tr>
  <tr>
    <td>TimeZone</td>
    <td>
      <li>Time Zone for the User.</li>
      <li>Example: (UTC-05:00) Eastern Time (US & Canada)</li>
    </td>
  </tr>
  <tr>
    <td><b>LicenseType*</b></td>
    <td>
      <li>Identifies specific V6 license type assigned in License Type field in user profile.</li>
      <li>Valid values are:</li>
      <ul>
        <li>Concurrent Access</li>
        <li>Full Access</li>
        <li>System Administrator</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>CultureName</td>
    <td>
      <li>For clients who have purchased additional languages.</li>
      <li>Identifies culture assigned in Culture field in user profile.</li>
      <li>"Automatic" will set to "Determine Automatically".</li>
      <li>Inactive cultures won't be assigned to a user.</li>
    </td>
  </tr>
  <tr>
    <td>LongDate</td>
    <td>
      <li>d, dd = day; ddd, dddd = day of week; M, MM = month; yy, yyyy = year</li>
    </td>
  </tr>
  <tr>
    <td>LongTime</td>
    <td>
      <li>h, hh = hour (12-hour format); H, HH = hour (24-hour format); m = minutes; s = seconds; tt = A.M. or P.M.</li>
    </td>
  </tr>
  <tr>
    <td>ShortDate</td>
    <td>
      <li>d, dd = day; ddd, dddd = day of week; M, MM = month; yy, yyyy = year</li>
    </td>
  </tr>
  <tr>
    <td>ShortTime</td>
    <td>
      <li>h, hh = hour (12-hour format); H, HH = hour (24-hour format); m = minutes; s = seconds; tt = A.M. or P.M.</li>
    </td>
  </tr>
</table>

> Example Request Body

```json
{
  "SendEmail": true,
  "IgnoreUserAccess": false,

  "Flag": "A",
  "EmployeeNumber": "001",
  "HomeLocationCode": "001",
  "Prefix": "Mr.",
  "FirstName": "John",
  "LastName": "Doe",
  "MiddleName": "Joe",
  "DisplayName": "John Doe",
  "Suffix": "III",
  "Email": "john.doe@intelex.com",
  "IsSupervisor": "Y",
  "EmployeeType": "Hourly",
  "Date_Of_Hire": "2019-11-25",
  "SupervisorNumber": "001",
  "PositionTitle": "Line Worker",
  "Notes": "Notes for me",
  "Contractor": "Y",
  "Company": "Intelex",
  "ContractorName": "Sears",
  "ContractExpiry": "2026-12-30",
  "InsuranceExpiry": "2026-12-31",
  "ContractorNotes": "Notes for the Contractor",
  "StreetAddress": "5613 DTC Pkwy Suite 320",
  "City": "Greenwood Village",
  "State": "Colorado",
  "ZipCode": "80111",
  "Gender": "M",
  "Date_Of_Birth": "1999-06-23",
  "SSN": "111-11-1111",
  "EmergencyContact": "Jane Doe",
  "EmergencyPhone": "123-456-7890",
  "PersonResponsible": 1,
  "PhoneNumber": "111-111-1111",
  "HourlyWage": "25",
  "JobCode": "jc12",
  "WorkStatus": "full time",

  "UserId": "jdoe",
  "IsLocked": false,
  "Password": "1234",
  "SecondaryPassword": "5678",
  "ForcePasswordChange": false,
  "LoginLocationCode": "001",
  "TimeZone": "Eastern Standard Time",
  "LicenseType": "Full Access",
  "CultureName": "English (United States)",
  "LongDate": "",
  "LongTime": "",
  "ShortDate": "",
  "ShortTime": "",

  "Groups": "Claims Administrator(01E4C606-2F03-4044-B6B1-079AE288D82A);7F50AC4D-93F4-4DF9-90AF-00D7DF663720"
}
```

### Payload Validation

Fields in the payload will be checked for validity before creating or updating the employee and user records.

#### Create (POST) Payload Validation

Example payload validations for creation include:

<ul>
    <li>Required fields that are not included in the payload</li>
    <li>Invalid external identifiers that do not exist (E.g. <code>SupervisorNumber</code>, <code>LoginLocationCode</code>)</li>
    <li>Duplicate primary key identifiers (E.g. <code>EmployeeNumber</code>, <code>DisplayName</code>)</li>
</ul>

#### Update (PATCH) Payload Validation

Example payload validations for modification include:

<ul>
    <li>Required identifier fields (<code>Id</code>, <code>EmployeeNumber</code>) not included in the request</li>
    <li>Required fields that are empty (<code>""</code>) in the payload</li>
    <li>Invalid external identifiers that do not exist (E.g. <code>SupervisorNumber</code>, <code>LoginLocationCode</code>)</li>
    <li>Duplicate primary key identifiers (E.g. <code>EmployeeNumber</code>, <code>DisplayName</code>)</li>
</ul>

> Example Response With Validation Errors

```json
{
  "error": {
    "messages": [
      "Cannot create employee - Invalid value for IsSupervisor. Please use either 'Y' or 'N'",
      "There is an existing employee with the same employee number.",
      "Home location with code 001 is not found."
    ]
  }
}
```

### Group Membership

Group membership for an employee may also be managed via the User Management API with use of the <code>Groups</code> field. The <code>Groups</code> field expects a semi-colon delimited list of groups in one of the following formats:
<ul>
  <li><code>GroupId</code></li>
  <li><code>GroupName</code></li>
  <li><code>RoleId(LocationId)</code> (for a Location Role)</li>
  <li><code>RoleId(LocationCode)</code> (for a Location Role)</li>
  <li><code>RoleName(LocationId)</code> (for a Location Role)</li>
  <li><code>RoleName(LocationCode)</code> (for a Location Role)</li>
</ul>

"Groups" include Security Groups, Roles, Location Roles and Training Workgroups, or any object that inherits from the Group Entity.

#### Roles and Location Roles

If an entry is a role and no location is defined for the entry (E.g. As <code>RoleId(LocationId)</code>), a location role will be assigned using the <code>LoginLocationCode</code> value. If <code>LoginLocationCode</code> is invalid or not present in the payload, the Role will be assigned without a location.

Roles with <code>AllowManySubjects</code> set to <code>false</code> will unassign any existing members from the role before assigning membership to the target employee.

#### Group Membership Settings

See [Settings Flags](#settings-flags) for details on <code>DoNotAddGroupAssignments</code> and <code>RemoveFromUnlistedGroups</code> fields.

#### Group Validation

Groups are validated before membership is assigned. If any validations fail, error messages will be returned in the response.

Example group validations include:
<ul>
  <li>Group Id or Name does not exist.</li>
  <li>Group for a LocationRole (GroupId(LocationId), in this case GroupId) does not exist.</li>
  <li>Group Id or Name for a location role (<code>Role(Location)</code>), is not a Role. E.g. If you try to use the ID of a SysSecurityGroup as a role in a location role, the parsing will fail.</li>
  <li>Location code does not exist or is invalid.</li>
</ul>

> Example Groups Payload

```json
{
  "Groups": "7F50AC4D-93F4-4DF9-90AF-00D7DF663720;Insurance;36D48405-36EA-42C8-B11B-CA50DAB377DD(01E4C606-2F03-4044-B6B1-079AE288D82A);BD5797DD-D015-429C-89E6-1A79C3EB7B79(056);Claims Administrator(01E4C606-2F03-4044-B6B1-079AE288D82A);Claims Administrator(001)"
}
```

> Example Response With Group Validation Errors

```json
{
  "error": {
    "messages": [
      "The Location Role 'Role123(Loc123)' is invalid. Please ensure that the Role (Role123) is the Name or ID of a valid and existing Role.",
      "Group '36D48405-36EA-42C8-B11B-CA50DAB377DD' is invalid. Group with ID '36D48405-36EA-42C8-B11B-CA50DAB377DD' does not exist.",
      "Group 'Role456(Loc456)' is invalid. Location with Code 'Loc456' is archived or does not exist."
    ]
  }
}
```