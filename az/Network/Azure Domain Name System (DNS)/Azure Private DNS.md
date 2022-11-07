### Azure Private DNS
	An Azure service that manages and resolves domain names in a virtual network (vnet) without adding a custom DNS solution through the use of vnet links.

- Azure Private DNS records are not viewable or retrievable.
- Azure Private DNS and [[Azure DNS]] zones can share the same names using split-horizon view.
- Azure Private DNS zone links with autoregistration enabled become registration zones for linked vnets.
	- *DNS records are created automatically only if the primary virtual machine NIC is using DHCP.*
	- *Autoregistration for IPv6 (AAAA records) isn't supported.*
	- *Azure Private DNS zones can have multiple registration vnets.*
	- *Every vnet can ==ONLY== have (`1`) registration zone associated with it.*
	- *Every virtual machine (VM) currently deployed and will be deployed will generate a DNS record in the private DNS zone.*
	- *Registration vnets also resolve domain names.*
- Azure Private DNS zones links without autoregistration enabled become resolution zones for linked vnets.
	- *Azure Private DNS zones can have multiple resolution vnets.*
	- *Every vnet can have multiple resolution zones associated with it.*



