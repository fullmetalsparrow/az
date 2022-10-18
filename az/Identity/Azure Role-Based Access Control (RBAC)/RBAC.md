### Azure RBAC
	An authorization system built on Azure Resource Manager that provides fine-grained access management to Azure resources.

*See [[Resource Management Tools]] for ARM*

### Security Principal
	An object to be authenticated against.
	ex.: user, group, service principal, managed identity.

### Role Defintion
	A collection of permissions that list operations that can or cannot be performed by the security principal.

### Scope
	The boundary for the level of access that is requested by the security principal.
	ex.: management group, subscription, resource group, resource.

### Role Assignment
	The application of a role definition to a security principal at a specified scope.
>*Role assignments on resource groups are kept when migrating subscriptions, but orphaned on individuals resources.*
