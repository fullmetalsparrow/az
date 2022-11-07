### Azure Import/Export Service
---
- A secure method to ship data disks to and from an Azure datacenter for importing into Azure [[Blobs]] and Azure [[File Shares]].

- Azure Import/Export Service mandates the shipping only internal SATA II/III HDD's or SSD's containing a single BitLocker-encrypted NTFS volume.
- Azure Import/Export Service utilizes the WA ImportExport tool for preparing data disks for shipping using a 64-bit Windows Operating System (OS).
- Azure Import/Export Service utilizes a *`driveset.csv`* and a *`dataset.csv`* file for preparing the drives for the import .


### Azure Import/Export Service Nuances
---
> - *Import service supports blob and file storage.*
> - *Export service supports ==ONLY== blob storage.*

