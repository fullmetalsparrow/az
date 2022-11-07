### Azure Files
	A fully managed cloud file share accessible over port 445 (SMB), NFS mappings, or REST API's over HTTPS.
*(see [[File Shares]])*

### Azure File Sync
	A downloadable package that enables Windows Server instances to sync with an Azure File share.

### Storage Sync Service
	A top-level Azure resource for Azure File Sync that creates sync relations with multiple storage accounts via multiple sync groups.
*(see [[Storage Accounts]])*

### Sync Group
	Defines the sync topology for a set of files.

### Cloud Endpoint
	An Azure File share that is part of a sync group.

### Server Endpoint
	A specific location on an Azure File Sync registered server.



### Azure Files Nuances
---
> - *Azure FileStorage accounts ==ONLY== support LRS or ZRS.*