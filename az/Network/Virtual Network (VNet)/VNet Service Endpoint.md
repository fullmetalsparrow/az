![[vnet_svc_endpts.png]]


### Virtual Network Service Endpoint
	A network protocol that provides the identity of a vnet to the Azure service.

- VNet service endpoints are configured through the subnet.
- VNet service endpoints extend the private IP address spaces of vnets to Azure resources and services.
- VNet service endpoints remove the need for public IP addresses to secure traffic through IP firewalls.
- VNet service endpoints remove public access to resources and allow only traffic from configured vnets.
- VNet service endpoints do not require NAT or gateway devices to set up.