![[az_backup1.png]]
![[az_backup_soft_delete.png]]


### Azure Backup
	An Azure service used to make application-consistent backups to a Recovery Services vault.

### Application-Consistent Backup
	A recovery point that has all required data to restore a backup copy.

- Azure Backup restores can full or partial.
- Azure Backup is ==NOT== bandwidth-limited.
- Azure Backup encrypts data-at-rest with a locally stored passphrase or key.
- Azure Backup is billed on a consumption basis.
- Azure Backup ==CANNOT== be used with Zone Redundant Storage (ZRS).
- Azure Backup of VM disks can be done live or offline.
- Azure Backup supports 64-bit VM backups of:
	1. *Windows 10 OS or later.*
	2. *Windows Server 2008 or later.*
	3. *Ubuntu Server 12.04 LTS or later.*
- Azure Backup retention periods:
	1. *Default: 30 days.*
	2. *Max: 9,999 days.*
	3. *Min: 7 days.*
	4. *Soft delete: 14 days.*



### Azure Backup Nuances
---
> - *Soft delete feature ==MUST== be disabled in order to delete items from a [[Azure Recovery Services]] vault.*
> - *Backing up data ==ONLY== requires a Recovery Services Vault, but report logging requires a [[Storage Accounts]] in the same region.*
> - *Backups logs can be analyzed in an [[Azure Monitor]] Log Analytics Workspace in ANY region.*

