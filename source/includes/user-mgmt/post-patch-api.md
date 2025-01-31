## Add or Modify Data

## Field Reference

### Employee Fields

Property | Description
--------- | -----------
Flag|TBD
EmployeeNumber*|TBD
HomeLocationCode*|TBD
Prefix|TBD
FirstName*|TBD
LastName*|TBD
MiddleName|TBD
DisplayName|TBD
Suffix|TBD
Email|TBD
IsSupervisor|TBD
EmployeeType|TBD
Date_Of_Hire|TBD
SupervisorNumber|TBD
PositionTitle|TBD
Notes|TBD
Contractor|TBD
Company|TBD
ContractorName|TBD
ContractExpiry|TBD
InsuranceExpiry|TBD
ContractorNotes|TBD
StreetAddress|TBD
City|TBD
State|TBD
ZipCode|TBD
Gender|TBD
Date_Of_Birth|TBD
SSN|TBD
EmergencyContact|TBD
EmergencyPhone|TBD
PersonResponsible|TBD
PhoneNumber|TBD
HourlyWage|TBD
JobCode|TBD
WorkStatus|TBD
Groups|TBD

### User Fields

Property | Description
--------- | -----------
UserId*|TBD
IsLocked|TBD
Password|TBD
SecondaryPassword|TBD
ForcePasswordChange|TBD
LoginLocationCode*|TBD
TimeZone|TBD
LicenseType*|TBD
CultureName|TBD
LongDate|TBD
LongTime|TBD
ShortDate|TBD
ShortTime|TBD

> Example response with record metadata

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
