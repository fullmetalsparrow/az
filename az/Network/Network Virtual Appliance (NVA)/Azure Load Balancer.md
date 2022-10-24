### Load Balancer
---
1. A network appliance that delivers high availability and network performance to applications.
2. A network appliance that distributes inbound traffic to backend resources using rules and health probes.
*Load balancers can be public-facing or internal.*

### Backend Address Pool
	A network pool that contains the IP address of the virtual Network Interface Cards (NIC's) that are connected to the load balancer.

### Load Balancer Rule
	A network procedure that defines how traffic is distributed to the backend pool.

### Health Probe
	A network procedure that dynamically adds or removes nodes (VM's) from the load balancer rotation based on response to HTTP or TCP health checks.


- Azure Load Balancer uses a five-tuple hash to map traffic to available servers.
	- *If wanting to use session affinity to map the same source IP to the same target node (VM) every time the client connects, Azure Load Balancer can configured for a two-tuple or three-tuple hash.*
- Azure Load Balancer provides session persistence only within a transport session by default.
	- *Session persistence can be configured for:*
		1. *Client IP.*
		2. *Client IP and Protocol.*
		3. *None.*
- Azure Load Balancer can be used with Network Address Translation (NAT) rules.


### Azure Load Balancer Nuances
---
> - *Azure Load Balancers ==CANNOT== be migrated once created.*