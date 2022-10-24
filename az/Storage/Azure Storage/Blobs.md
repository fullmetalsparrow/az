### Blob Types
---
Blob types:
	1. Block (storing text and binary data; default)
	2. Append (logs)
	3. Page (VM OS and data disks; up to 8 TB in size)


### Blob Storage Costs
---
Blob storage costs are tiered based on rate of access:
	1. Hot (frequent acces; default)
	2. Cool (stored 30+ days with infrequent access)
	3. Archive (stored 180+ days with seldom access)
		- *It may take up to (**15**) hours to upgrade archive to cool tier for ready access.*
*==Blobs will automatically **downgrade** tiers if conditions are met to save costs==*


### Blob Access
---
URI for a blob looks like `https://myaccount.blob.core.windows.net/mycontainer/myblob` or `https://myaccount.blob.core.windows.net/mycontainer/myvirtualdirectory/myblob`


### Blob Nuances
---
> - *Rehydrating a blob from Archive using a Copy Blob operation will create a standalone copy of the blob and leave the original unmodified in the Archive tier.*