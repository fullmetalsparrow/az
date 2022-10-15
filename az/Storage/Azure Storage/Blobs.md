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

*==Blobs will automatically **downgrade** tiers if conditions are met to save costs==*


### Blob Access
---
URI for a blob looks like `https://myaccount.blob.core.windows.net/mycontainer/myblob` or `https://myaccount.blob.core.windows.net/mycontainer/myvirtualdirectory/myblob`