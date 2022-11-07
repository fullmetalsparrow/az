![[mars_v_mabs.png]]

### Azure Recovery Services Vault
	An Azure storage entity that holds backup data.
*Azure Recovery Services Vault does ==NOT== require a [[Storage Accounts]] for holding data.*


- Azure Recovery Services has (`3`) default policy templates for [[Azure Backup]]:
	1. *Azure Virtual Machine (VM).*
	2. *Azure File Share.*
	3. *SQL Server in VM.*


### Cross-Region Restore (CRR)
	An Azure service that allows restoring VM's to a secondary paired Azure region. 
*Recovery to an alternate region is only supported between East US and West US; otherwise, the restore can only happen in the region where the Recovery Services Vault is located.*
