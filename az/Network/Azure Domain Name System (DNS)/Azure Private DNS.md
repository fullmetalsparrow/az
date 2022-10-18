### Azure Private DNS
	An Azure service that manages and resolves domain names in a virtual network (vnet) without adding a custom DNS solution through the use of vnet links.

- Azure Private DNS records are not viewable or retrievable.
- Azure Private DNS and [[Azure DNS]] zones can share the same names using split-horizon view.
- Azure Private DNS zones can be applied to multiple vnets.


### Azure Private DNS Nuances
---
> 1. *When adding a new private DNS zone to an existing vnet that already has a private zone assigned to it, all that is required is to add the zone to the vnet.*
> 2. *VNets that do not already have a private DNS zone will need all of the existing VM's re-added after configuring the vnet with a private DNS zone as VM hostname discovery only occurs after creation.*

