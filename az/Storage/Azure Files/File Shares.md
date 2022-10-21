- An Azure File share cannot be deleted without deleting all existing snapshots
- Azure File snapshots are captured at the file share level
- Azure File snapshots are incremental
- Azure File snapshot restores can be partial or full
- Azure File snapshot restores can full restore from last incremental snapshot


### File Share Create Example
---
![[az_file_share_create.png]]
*These commands create the [[Storage Accounts]], retrieve their access keys, set up the context for the file share, and maps a network drive on the Windows Server virtual machine (VM).*
