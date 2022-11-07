### Installation and Operation Steps
---
1. Deploy the Storage Sync Service.
2. Prepare the Windows Server instance to use Azure File Sync.
3. Install the Azure File Sync Agent on the Windows Server instance.
4. Register the Windows Server instance with the Storage Sync Service.

![[azure_file_sync.png]]
*Azure File Sync*

*(see [[Azure Files]] for more information on terminology)*


### Azure File Sync Nuances
---
> - *A sync group contains a 1:M relationship between cloud endpoints to server endpoints.*
> - *Azure File Sync does ==NOT== support more than 1 server endpoint from the same server in the same sync group.*
> - *Multiple server endpoints can exist on the same volume as long as their namespace does not overlap with another (ex.: D:\Accounting and D:\Sales) and each endpoint is syncing to a unique sync group (ex.: D:\Sales ==CANNOT== be synced with both the Sales Sync Group and the Accounting Sync Group).*

