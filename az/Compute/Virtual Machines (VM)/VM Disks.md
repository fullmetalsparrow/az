- Azure VM's have an OS disk (C:\\) and a temp disk (D:\\).
	- Azure VM's have 1+ data disks.
	- Azure VM's are stored using Virtual Hard Disks (VHDs), which are page [[Blobs]].
	- Azure VM's temp disk stores the pagefile (swap partition).
- Azure VM's have an OS disk (C:\\) has a max capacity of 2TB.
- Azure VM OS and data disks can be secured using Azure Disk Encryption.
- Azure VM data disks require the use of the `Update-AzVM` command when transferring or exchanging data disks to a new VM.
	- *This does ==NOT== require the VM to be powered down and the data within the disk will be inaccessible until remounted.*
- Azure VM disks are still persisted after the VM is deleted.


### VM Disks Nuance
---
> - *VM disks ==MUST== be in the VHD format to be templated.*