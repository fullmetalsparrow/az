### Azure Built-In Roles
---
[Azure role-based access control (Azure RBAC)](https://learn.microsoft.com/en-us/azure/role-based-access-control/overview) has several Azure built-in roles that you can assign to users, groups, service principals, and managed identities.

| Role | Description |
| --- | ---|
|[Contributor](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#contributor)|Grants full access to manage all resources, but does not allow you to assign roles in Azure RBAC, manage assignments in Azure Blueprints, or share image galleries.|
|[Owner](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#owner)|Grants full access to manage all resources, including the ability to assign roles in Azure RBAC.|
|[Reader](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#reader)|View all resources, but does not allow you to make any changes.|
|[User Access Administrator](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#user-access-administrator)|Lets you manage user access to Azure resources.|


Each role is defined by a list of `Actions`, `NotActions`, `DataActions`, and `NotDataActions` it can or cannot take for specified resources.

Effective permissions are determined by subtracting the `NotActions` operations from the `Actions` operations.

Role assignments ([[Identity/Azure Role-Based Access Control (RBAC)/Definitions]]) are reviewable through the [[Activity Log]].

Full list located in Microsoft reference documentation [here](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles)
