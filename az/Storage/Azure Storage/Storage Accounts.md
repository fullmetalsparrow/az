### Storage Account
---
1. A container for grouping Azure Storage ([[az/Storage/Azure Storage/Azure Storage]]) services
2. An Azure resource

- Storage account names must be globally unique in Azure
- Storage accounts incur no financial cost (only when storage is used)
- Storage accounts are capped at 20K IOPS
- Storage accounts cannot include other Azure data services, such as Azure SQL or Azure Cosmos DB
- Storage accounts can either be Standard (backed by magnetic Hard Disk Drives (HDD)) or Premium (backed by Solid-State Drives (SSD))

![[storage_account_types.png]]
*Storage Account Types*


- Storage accounts can have an unlimited amount of [[Containers]].
- Storage accounts can have data transferred between on-premises and Azure using the PowerShell command: `AzCopy`.
	- *`AzCopy` can be used with [[Azure AD]] credentials for transfers to [[Blobs]] storage, Azure Queue storage, or table storage.*

- Storage account have an "Enable large file shares" option that provides up to 100 TiB of storage with the following limitations:
	1. Upgrades to large file shares are permanent.
	2. Accounts upgraded cannot be replicated using a GRS offering.
	3. Azure File service connections will fail without encryption.


