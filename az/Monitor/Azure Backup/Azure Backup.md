![[az_backup1.png]]
![[az_backup_soft_delete.png]]


### Azure Backup
	An Azure service used to backup data to a Recovery Services vault.

### Application-Consistent Backup
	A recovery point that has all required data to restore a backup copy.

- Azure Backup provide application-consistent backup.
	- *Restores can full or partial.*
- Azure Backup does not limit the amount of inbound or outbound data transferred.
- Azure Backup encrypts data-at-rest with a locally stored passphrase or key.
- Azure Backup automatically allocates and manages backup storage.
- Azure Backup is billed on a consumption basis.
- Azure Backup can be used with Local Redudant Storage (LRS) or Geographic Redundant Storage (GRS).