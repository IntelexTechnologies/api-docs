## Retrieve Data

To retrieve data relevant to Employees and Users that are being managed through the User Management API, please refer to the [Object Data API](#object-data-api) section. 

The applicable User Management [System Objects](#system-objects) that can be accessed will be `SysEmployeeEntity` and `SysUserEntity`.

Please note: There are some SysUserEntity fields that can be set/updated but are marked as sensitive so they will not be returned when retrieving SysUserEntities. **This is not an exhaustive list and columns marked as sensitive could change in the future**:

* `SecondaryPassword`
* `DateSecondaryPasswordModified`