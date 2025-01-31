## Add or Modify Data

### Payload Validation

Fields in the payload will be checked for validity befor creating the employee and user records.

Some validations for Create (POST) include:
- Required fields that are not included in the payload
- Invalid external identifiers that do not exist (E.g. <code>SupervisorNumber</code>, <code>LoginLocationCode</code>)
- Duplicate primary key identifiers (E.g. duplicate <code>EmployeeNumber</code> or <code>DisplayName</code>)

> Example POST response with validation errors

```json
{
    "error": {
        "messages": [
            "There is an existing employee with the same employee number."
        ]
    }
}
```

Some validations for Update (PATCH) include:
- Required identifier fields (Id, EmployeeNumber) not included in the request

> Example PATCH response with validation errors

```json
{
    "error": {
        "messages": [
            "There is an existing employee with the same employee number."
        ]
    }
}
```

### Payload Field Reference

#### Settings Flags

Settings flags are payload fields that configure the behavior of the user management API request. 

Some settings flags may be ignored if the flag is not relevant to the request type. For example, <code>RevokeUserAccess</code> is only applicable to an existing user, so is only applicable in a update (PATCH) request.

All flags default to <code>false</code> unless otherwise noted.

<table>
  <tr>
    <th>Property</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>IgnoreUserAccess</td>
    <td>
      Skips user access creation. Employee record will still be created.
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
      <li>Existing employees only</li>
      <li>Remove employee membership from any previously assigned groups that are not specified in the <code>Groups</code> field.</li>
      <li>This field is still respected if <code>DoNotAddGroupAssignments</code> is set.</li>
    </td>
  </tr>
</table>

### Employee Fields

Payload fields that are associated with the employee record to be created or updated. Properties denoted with a <code>*</code> are required and must be included in the payload.

<table>
  <tr>
    <th>Property</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>Flag</td>
    <td>
      <li>Indicates whether employe should be archived in the system:</li>
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
      Primary Key; Unique identifier of employee.
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
      Prefix of employee (e.g., Mr., Mrs., Ms.)
    </td>
  </tr>
  <tr>
    <td><b>FirstName*</b></td>
    <td>
      First name of employee.
    </td>
  </tr>
  <tr>
    <td><b>LastName*</b></td>
    <td>
      Last name of employee.
    </td>
  </tr>
  <tr>
    <td>MiddleName</td>
    <td>
      Middle name of employee
    </td>
  </tr>
  <tr>
    <td>DisplayName</td>
    <td>
      Last name of employee.
    </td>
  </tr>
  <tr>
    <td>Suffix</td>
    <td>
      Suffix of employee (e.g., Jr., Sr.)
    </td>
  </tr>
  <tr>
    <td>Email</td>
    <td>
      Email address of employee.
    </td>
  </tr>
  <tr>
    <td>IsSupervisor</td>
    <td>
      Indicates whether employee has direct reports or not.
    </td>
  </tr>
  <tr>
    <td>EmployeeType</td>
    <td>
      Type of employee.
    </td>
  </tr>
  <tr>
    <td>Date_Of_Hire</td>
    <td>
      <li>Date of hire of employee.</li>
      <li>Please speak with your consultant to confirm the date format for your subdomain.</li>
    </td>
  </tr>
  <tr>
    <td>SupervisorNumber</td>
    <td>
      Employee Number of supervisor of employee.
    </td>
  </tr>
  <tr>
    <td>PositionTitle</td>
    <td>
      Job title of employee.
    </td>
  </tr>
  <tr>
    <td>Notes</td>
    <td>
      Open text field found in employee profile.
    </td>
  </tr>
  <tr>
    <td>Contractor</td>
    <td>
      Indicates whether employee is a contractor.
    </td>
  </tr>
  <tr>
    <td>Company</td>
    <td>
      Company name of employee.
    </td>
  </tr>
  <tr>
    <td>ContractorName</td>
    <td>
      Contractor company name of employee.
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
      Open text field found in employee profile.
    </td>
  </tr>
  <tr>
    <td>StreetAddress</td>
    <td>
      Street address of employee.
    </td>
  </tr>
  <tr>
    <td>City</td>
    <td>
      City of employee.
    </td>
  </tr>
  <tr>
    <td>State</td>
    <td>
      State of employee.
    </td>
  </tr>
  <tr>
    <td>ZipCode</td>
    <td>
      Zip code (or postal code) of employee.
    </td>
  </tr>
  <tr>
    <td>Gender</td>
    <td>
      Gender of employee.
    </td>
  </tr>
  <tr>
    <td>Date_Of_Birth</td>
    <td>
      <li>Date of birth of employee.</li>
      <li>Please speak with your consultant to confirm the date format for your subdomain.</li>
    </td>
  </tr>
  <tr>
    <td>SSN</td>
    <td>
      Social security number of employee.
    </td>
  </tr>
  <tr>
    <td>EmergencyContact</td>
    <td>
      Emergency contact information of employee.
    </td>
  </tr>
  <tr>
    <td>EmergencyPhone</td>
    <td>
      Emergency phone number of employee.
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
      Phone number of employee.
    </td>
  </tr>
  <tr>
    <td>HourlyWage</td>
    <td>
      Hourly wage of employee.
    </td>
  </tr>
  <tr>
    <td>JobCode</td>
    <td>
      Job Code for employee.
    </td>
  </tr>
  <tr>
    <td>WorkStatus</td>
    <td>
      [Legal] Work status of employee.
    </td>
  </tr>
  <tr>
    <td>Groups</td>
    <td>
      <li>Semicolon (;) delimited list of elements that this employee is a member of (excluding Everyone group).</li>
      <li>Each element can be the Caption or GUID of any Group or Location Role.</li>
      <li>Groups includes Security Groups, Roles, Location Roles and Training Workgroups.</li>
      <li>If an element is invalid, then the processing of this particular element is skipped; other elements for the employee are not skipped.</li>
      <li>Notation for Location Role: RoleCaption(LocationCodeOrGUID)</li>
    </td>
  </tr>
</table>

### User Fields

Payload fields that are associated with the user record to be created or updated if requested (<code>IgnoreUserAccess</code> = <code>false</code>). <b>If user access is requested,</b> properties denoted with a <code>*</code> are required and must be included in the payload.

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
      Locks or unlocks the user
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
      <li>Time Zone for the User. In the EDIS template the user can select the Time Zone from a select control, in the default template downloaded from the Data Import user have to enter the value manually. </li>
      <li>Example: (UTC-05:00) Eastern Time (US & Canada)</li>
    </td>
  </tr>
  <tr>
    <td><b>LicenseType*</b></td>
    <td>
      <li>Must map correctly to SecurityGroupName column:</li>
      <ul>
        <li>IF (SecurityGroupName) Limited Access THEN SET (LicenseType) TO Concurrent Access</li>
        <li>IF (SecurityGroupName) Supervisor Access THEN SET (LicenseType) TO Concurrent Access</li>
        <li>IF (SecurityGroupName) Full Access THEN SET (LicenseType) TO Full Access</li>
        <li>IF (SecurityGroupName) System Administrator THEN SET (LicenseType) TO System Administrator</li>
      </ul>
      <li>Identifies specific V6 license type assigned in License Type field in user profile.</li>
    </td>
  </tr>
  <tr>
    <td>CultureName</td>
    <td>
      <li>For clients who have purchased additional languages.</li>
      <li>Identifies culture assigned in Culture field in user profile. If the value in this staging table is "Automatic" will set to "Determine Automatically".</li>
      <li>Inactive cultures won't be assigned to a user.</li>
    </td>
  </tr>
  <tr>
    <td>LongDate</td>
    <td>
      d, dd = day; ddd, dddd = day of week; M, MM = month; yy, yyyy = year
    </td>
  </tr>
  <tr>
    <td>LongTime</td>
    <td>
      h, hh = hour (12-hour format); H, HH = hour (24-hour format); m = minutes; s = seconds; tt = A.M. or P.M.
    </td>
  </tr>
  <tr>
    <td>ShortDate</td>
    <td>
      d, dd = day; ddd, dddd = day of week; M, MM = month; yy, yyyy = year
    </td>
  </tr>
  <tr>
    <td>ShortTime</td>
    <td>
      h, hh = hour (12-hour format); H, HH = hour (24-hour format); m = minutes; s = seconds; tt = A.M. or P.M.
    </td>
  </tr>
</table>

> Example request body payload

```json
{
    // IUserMgmtSettings (EDIS Settings) Fields
    "SendEmail": true,
    "IgnoreUserAccess": false,

    // Employee Fields
    "Flag": "AAA", // Must be A or I
    "EmployeeNumber": "0011144", // Required, checked for uniqueness
    "HomeLocationCode": "001", // Required, checked for existence
    "Prefix": "pre",
    "FirstName": "AAAJohn", // Required
    "LastName": "Doe", // Required
    "MiddleName": "Joe",
    "DisplayName": "John Doe44", // If blank, will be set as "{FirstName} {LastName}"
    "Suffix": "suf",
    "Email": "john.doe@intelex.com",
    "IsSupervisor": "Y", // Must be Y or N
    "EmployeeType": "Hourly", // Converted to EmployeeTypeId
    "Date_Of_Hire": "2019-11-25",
    "SupervisorNumber": "001", // Checked for existence
    "PositionTitle": "Line Worker",
    "Notes": "dfghdfghdfg",
    "Contractor": "Y", // Must be Y or N
    "Company": "Intelex",
    "ContractorName": "Sears",
    "ContractExpiry": "2026-12-30",
    "InsuranceExpiry": "2026-12-31",
    "ContractorNotes": "zdgsdf",
    "StreetAddress": "5613 DTC Pkwy Suite 320",
    "City": "Greenwood Village",
    "State": "Colorado",
    "ZipCode": "80111",
    "Gender": "M",
    "Date_Of_Birth": "1999-06-23",
    "SSN": "111-11-1111",
    "EmergencyContact": "Jane Doe",
    "EmergencyPhone": "123-456-7890",
    "PersonResponsible": 1, // Not currently used
    "PhoneNumber": "111-111-1111",
    "HourlyWage": "25",
    "JobCode": "jc12",
    "WorkStatus": "full time",

    // User Fields
    "UserId": "jdoe41", // Required if user access is requested
    "IsLocked": false,
    "Password": "1234",
    "SecondaryPassword": "5678",
    "ForcePasswordChange": false,
    "LoginLocationCode": "001",  // Required if user access is requested
    "TimeZone": "Eastern Standard Time", // Checked for existence
    "LicenseType": "Full Access",  // Required if user access is requested. Checked for existence
    "CultureName": "English (United States)",
    "LongDate": "",
    "LongTime": "",
    "ShortDate": "",
    "ShortTime": "",

    "Groups": "Claims Administrator(01E4C606-2F03-4044-B6B1-079AE288D82A);7F50AC4D-93F4-4DF9-90AF-00D7DF663720",

}
```

## Add Data

This section outlines the blah blah blah

## Modify Data

This section outlines the blah blah blah
