### Network Security Group (NSG)
	A list of security rules that allow or deny inbound/outbound network traffic.
*Security rules with low priority numbers have higher precedence*

### Application Security Group (ASG)
	A logical grouping of nodes (VM's) that allows NSG's be defined for the group instead of at the individual Network Interface Card (NIC) or subnet levels.

- NSG can be associated with 1+ subnet(s) *OR* 1+ network interface(s).
	- *Each subnet can ==only== have **ONE** NSG*.
- NSG can be applied based on service tags:
	1. *VirtualNetwork*
	2. *Internet*
	3. *SQL*
	4. *Storage*
	5. *AzureLoadBalancer*
	6. *AzureTrafficManager*
- NSG have (`3`) unchangeable inbound rules for access within the virtual network (vnet) and dropping all other traffic.
- NSG have (`3`) unchangeable outbound rules for access within the vnet, as well as the Internet, and dropping all other traffic.