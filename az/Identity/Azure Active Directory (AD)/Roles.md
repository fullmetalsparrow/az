### Azure AD Built-In Roles
---
| Role | Description |
| --- | --- |
|[Global Administrator](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference#global-administrator) | Can manage all aspects of Azure AD and Microsoft services that use Azure AD identities. |
|[User Administrator](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference#user-administrator) | Can manage all aspects of users and groups, including resetting passwords for limited admins. |
|[Groups Administrator](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference#groups-administrator) | Members of this role can create/manage groups, create/manage groups settings like naming and expiration policies, and view groups activity and audit reports. |
|[Security Administrator](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference#security-administrator) | Can read security information and reports, and manage configuration in Azure AD and Office 365. |


Each role is defined by a list of `Actions`, `NotActions`, `DataActions`, and `NotDataActions` it can or cannot take for specified resources.

Effective permissions are determined by subtracting the `NotActions` operations from the `Actions` operations.

Full list located in Microsoft's reference documentation [here](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)
