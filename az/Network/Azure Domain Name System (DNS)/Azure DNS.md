- An initial [[Azure AD]] domain is created with an Azure [[Subscriptions]]:
	- *The initial domain name is ==\<domain\>.onmicrosoft.com==.*
	- *The initial domain is used until a custom domain has been verified.*
*Domain names in Azure AD must be globally unique in Azure.*

- Azure DNS verifies domain ownersip via a `MX` or `TXT` DNS record.
- Azure DNS root domains are registered with a third-party registrar and pointed to the Azure DNS nameservers.
	- *Changing the nameserver (NS) record to Azure DNS is called ==domain delegation==.*
	- *Azure DNS child domains are registered directly in Azure.*


### DNS Zone
	An administrative section that hosts the DNS records for a domain.
*DNS zone names must be unique with the resource group.*

- Azure DNS allocates (`4`) nameservers per DNS zone created and automatically generates the apex (root) NS and Statement of Authority (SOA) records for the zone.
	- *SOA records represent the domain and are used as a reference by other DNS servers.*


### Apex Domain
---
1. The highest level of a domain.
2. Often referred to as the *zone apex* or *root apex*.
3. Often represented with an `@` symbol in the DNS Zone records. 


### Azure Alias Records
---
1. Enable a zone apex reference other Azure resources from a DNS zone:
	- *Azure Traffic Manager profile.*
	- *Azure Content Delivery Network (CDN) endpoint.*
	- *Public IP resource.*
	- *Front door profile.*
	- *Load balancer.*
2. Provide lifecycle tracking and automatic updating on target resources.
3. Support *A*, *AAAA*, and *CNAME* records.