### Azure Portal
---
- Web-based GUI management tool for single resource management tasks
- Hosts the Azure Cloud Shell


### Azure Cloud Shell
---
- Web-based CLI that runs on a per-session and per-user basis
- Requires a resource group, storage account, and Azure File share to use
- Home directory is persisted through a 5GB image held in the Azure File share
- Uses BASH or PowerShell commands based on mode selected


### Azure Command Line Interface (CLI)
---
- Cross-platform CLI that can be run as a standalone application or in the Azure Cloud Shell
- Uses BASH syntax


### Azure Resource Manager (ARM)
---
- Deploy, update, and delete resources in resource groups using JSON or BICEP declarative templates
- ARM templates are linkable
- ARM templates can only contain 256 parameters
- ARM templates are idempotent

### ARM Nuances
---
> 1. *Exporting a resource group deployment to an ARM template will encompass all deployments made on that resource group; if you only export a single resource, only the latest deployment will be captured.*
> 2. *Use `-TemplateURI` for `New-AzResourceGroupDeployment` when use a remote repository for an ARM deployment; `-TemplateFile` is for locally-stored files.*

