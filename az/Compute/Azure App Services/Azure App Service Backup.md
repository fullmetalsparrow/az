### [[Azure App Services]] Backup
	An Azure App Services feature that backs up app configurations, file content, and connected databases.

![[app_svc_backup_overview.png]]
*A database is considered linked if the the app has a valid conection string configured.*

- Azure App Service Backup requires a [[Storage Accounts]] and [[Containers]] in the same [[Subscriptions]] as the app.
	- *Storage account cannot be firewall-enabled.*
	- *Backups are stored as `.zip` files in a container of the specified storage account.*
	- *Cross-region and cross-subscription restores can be done by uploading the backup `.zip` files to the storage account source of the target app in the specified subscription and region.*
- Azure App Service Backup can be automated via Azure CLI or Azure PowerShell scripts.
- Azure App Service Backup stops target app or slot when restoring backups.
- Azure App Service Backup excludes folders and files from backups via a `_backup.filter` file in the [`%HOME%\site\wwwroot` folder](https://learn.microsoft.com/en-us/azure/app-service/operating-system-functionality#network-drives-unc-shares) of the app.
