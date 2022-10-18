![[vnet_svc_endpts.png]]
![[set-service-endpt.png]]
*`-Bypass AzureServices` allows other Azure services access the resource through the service endpoint.*


### Virtual Network Service Endpoint
	A network protocol that provides the identity of a vnet to the Azure service.

- VNet service endpoints are configured through the subnet.
	- *Network rules must be applied to the Azure resource being accessed to allow connections from subnet (in the above case, this would be the storage account).*
- VNet service endpoints extend the private IP address spaces of vnets to Azure resources and services.
- VNet service endpoints remove the need for public IP addresses to secure traffic through IP firewalls.
- VNet service endpoints remove public access to resources and allow only traffic from configured vnets.
- VNet service endpoints do not require NAT or gateway devices to set up.