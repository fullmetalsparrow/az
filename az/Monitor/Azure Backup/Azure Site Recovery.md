![[az_site_recovery.png]]

### Azure Site Recovery
	An Azure service that replicates workloads running on physical and virtual machines (VM's) from a primary region to a secondary region.

### Azure Site Recovery Plan
	A list of tasks that allow automation of Azure Site Recovery jobs.
*Replication of VM's ==MUST== be configured prior to creating an Azure Site Recovery Plan.*

- Azure Site Recovery does ==NOT== replicate [[Network Security Groups (NSG)]].
- Azure Site Recovery does ==NOT== migrate public IP addresses.
- Azure Site Reovery uses [[Azure Traffic Manager]] profiles to monitor target and source site statuses and to provide failover in the case of region outages.