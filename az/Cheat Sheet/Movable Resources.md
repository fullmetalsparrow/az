| Resource | Movable? |
| --- | --- |
| Microsoft.AppService | Yes* (regional only using ARM template) |
| Microsoft.AzureActiveDirectory.Tenants | No |
| Microsoft.AzureActiveDirectory.Directories | Yes* (RG and sub only) |
| Microsoft.Compute.AvailabilitySets | Yes |
| Microsoft.Compute.Disks | Yes |
| Microsoft.Compute.Images | Yes* (RG and sub only) |
| Microsoft.Compute.Snapshots | Yes* (Full snapshots for RG and sub only) |
| Microsoft.Compute.VirtualMachines | Yes |
| Microsoft.Compute.VirtualMachineExtensions | Yes* (RG and sub only) |
| Microsoft.Compute.Vmss | Yes* (RG and sub only) |
| Microsoft.ContainerInstances | No |
| Microsoft.KeyVault | Yes* (RG and sub only) |
| Microsoft.Kubernetes | No |
| Microsoft.Network.ApplicationGateways | No |
| Microsoft.Network.ApplicationSecurityGroups | Yes* (RG and sub only) |
| Microsoft.Network.AzureFirewalls | No |
| Microsoft.Network.BastionHosts | No |
| Microsoft.Network.Connections | Yes* (RG and sub only) |
| Microsoft.Network.DNSZones | Yes* (RG and sub only) |
| Microsoft.Network.ExpressRoute | No |
| Microsoft.Network.FrontDoor | No |
| Microsoft.Network.LoadBalancers | Yes* (except for Standard SKU in sub only) |
| Microsoft.Network.NetworkInterfaces | Yes |
| Microsoft.Network.NetworkSecurityGroups | Yes
| Microsoft.Network.NetworkWatchers | No |
| Microsoft.Network.NetworkWatcher.Components | Yes* (RG only) |
| Microsoft.Network.PrivateDNSZones | Yes* (RG and sub only) |
| Microsoft.Network.RouteTables | Yes* (RG and sub only) |
| Microsoft.Network.VirtualNetworks | Yes* (RG and sub only) |
| Microsoft.Network.ClassicVirtualNetworks | No |
| Microsoft.Network.VPNGateways | No |
| Microsoft.Peerings | No |
| Microsoft.SQL.Servers | Yes |
| Microsoft.Storage.StorageAccounts | Yes* (RG and sub only) |

> - *Most DB's support cross-read replication to a new region as well as being moved to a new RG or sub.*
> - *Managed services are generally ==NOT== moveable.*