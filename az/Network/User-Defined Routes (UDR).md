###  System Routes
	A network route table that directs network traffic between virtual machines (VM's), on-premises networks, and the Internet.

- System routes manage traffic between:
	1. VM's in the same subnet.
	2. VM's in different subnets of the same virtual network (vnet).
	3. VM's to the Internet.


### User-Defined Routes (UDR)
	A network route table that overrides system routes and specifies the next hop of network traffic.

- UDR choices:
	1. [[NVA]].
	2. VNet gateway.
	3. VNet.
	4. Internet.
	5. None.


*==Subnets can only be associated with a single route table.==*
