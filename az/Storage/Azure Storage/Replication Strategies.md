### Regional Replication
---
[[Regions]] 
![[replication_strategies.png]]
*==Zone = GPv2==                                                              GPv1 does not support [[Blobs]] storage tiers*


### Blob Replication
---
- `BlobBlockStorage` only support premium [[Storage Accounts]] for LRS or GRS.
- Block [[Blobs]] (content, metadata, versioning) are asynchronously replicated based on [[Containers]] rules.
- Blob versioning must be enabled on both the source and destination [[Storage Accounts]].
- Blob change feeds only need to be enabled on the source storage account.
- Blob storage must be in either the hot or cool tier for both the source and destination storage accounts.
- Blob snapshots are unsupported.


### Replication Nuances
---
> - *Azure Portal and Azure PowerShell can only migrate LRS to GRS variants.*
> - *Live migrations are not support for [[Azure Files]] Network File Shares (NFS) version 4.1.*






