### Azure Bastion
	An Azure Platform-as-a-Service (PaaS) that allows secure RDP and SSH connections to connected virtual machines (VM's) in the provisioned virtual network (vnet).
*Azure Bastion is automatically provisioned when creating vnets.*

- Azure Bastion is accessed internally through Azure via the Azure Portal.
- Azure Bastion ==MUST== be in a dedicated `/26` or larger subnet named `AzureBastionSubnet`.