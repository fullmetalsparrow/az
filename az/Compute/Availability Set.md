### Availability Set
	A logical grouping that is used to isolate VM resources from each other during deployment and protects against single server failure.
*Availability sets are not supported for all VM sizes and Azure regions*

![[avail_set1.png]]

### Availability Zone
	Groups of 1+ datacenters in a regional pair have independent power, cooling, and networking.

![[avail_zone1.png]]
*Each VM is placed in one fault domain and one update domain*

### Update Domain
	A group of VM nodes that are upgraded together during the process of a service upgrade.
- Update domains are rebooted one at a time during planned maintenance.
- There are (`5`) unconfigureable update domain by default, but up to (`20`) are available to be configured.


### Fault Domain
	A group of VM nodes that share a common set of hardware that share a single point of failure.
