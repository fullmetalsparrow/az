![[vnet_peering1.png]]
![[vnet_peering2.png]]
*(see [[NVA]])*


### Virtual Network Peer
	A unilateral coupling to allow network traffic between two virtual networks.
*Azure Portal creates (`2`) vnet peers for bidirectional communications when configuring vnet peering for a vnet to another vnet.*

- VNet peering traffic is kept on the private Microsoft backbone network
- VNet peering can access on-premises resources via Gateway Transit through the [[VPN Gateway]] in the hub vnet's gateway subnet.
	- *Gateway Transit is supported in both regional and global vnet peers.*
