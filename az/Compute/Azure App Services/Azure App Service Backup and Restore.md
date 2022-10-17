### Azure App Service Backup and Restore
	An Azure App Services feature that backs up app configurations, file content, and connected databases.

- Azure App Service Backup and Restore requires at least a Standard [[az/Compute/Azure App Services/Azure App Service Plans]] pricing tier.
- Azure App Service Backup and Restore requires a [[Storage Accounts]] and [[Containers]] in the same [[Subscriptions]] as the web app.
	- *Storage account cannot be firewall-enabled.*
- Azure App Service Backup and Restore performs full backups by default, but partial backups are supported.
- Azure App Service Backup and Restore can backup up to 10 GB of app data and database content.