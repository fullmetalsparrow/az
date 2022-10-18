- An initial [[Azure AD]] domain is created with an Azure [[Subscriptions]]:
	- *The initial domain name is ==\<domain\>.onmicrosoft.com==.*
	- *The initial domain is used until a custom domain has been verified.*
*Domain names in Azure AD must be globally unique in Azure.*

- Azure DNS verifies domain ownersip via a `MX` or `TXT` DNS record.
- Azure DNS root domains are registered with a third-party registrar and pointed to the Azure DNS nameservers.
	- *Changing the nameserver (NS) record to Azure DNS is called ==domain delegation==.*
	- *Azure DNS child domains are registered directly in Azure.*

### DNS Zone
	An administrative section that hosts the DNS records used by a nameserver for a domain.
*DNS zone names must be unique with the resource group and must match the domain name it holds records for (except in cases where the zone holds records for a subdomain and the subdomain has not been delegated to a different nameserver from the parent domain).*

- Azure DNS allocates (`4`) nameservers per DNS zone created and automatically generates the apex (root) NS and Statement of Authority (SOA) records for the zone.
	- *SOA records represent the domain and are used as a reference by other DNS servers.*

### Record Set
	A collection of zone DNS records that have the same name and type.

### Apex Domain
---
1. The highest level of a domain.
2. Often referred to as the *zone apex* or *root apex*.
3. Often represented with an `@` symbol in the DNS Zone records. 


### DNS Overexplain Example
---
**Domain name:** contoso.com

``` PowerShell
New-AzDnsRecordSet -Name "@" -RecordType "A" -ZoneName "contoso.com" `
 -ResourceGroupName "MyAzureResourceGroup" -Ttl 600 `
 -DnsRecords (New-AzDnsRecordConfig -IPv4Address "<ip of web app service>")
```
>- *This command creates a DNS "A" record set that points "contoso.com" to all IPv4 addresses under that domain.*
>- *The "@" is a reference to "contoso.com" itself as the root domain.*
>- *The "contoso.com" zone name matches the domain name and becomes the authortative zone for the domain in the 4 deployed nameservers.*

``` PowerShell
New-AzDnsRecordSet -ZoneName contoso.com `
 -ResourceGroupName MyAzureResourceGroup `
 -Name "@" -RecordType "txt" -Ttl 600 `
 -DnsRecords (New-AzDnsRecordConfig -Value  "contoso.azurewebsites.net")
```
>- *This command creates the "TXT" record set that provides domain verification for the zone apex, which is "contoso.com" in this case.*
>- *The "New-AzDnsRecordConfig" line verifies the domain ownership to Azure App Services for a web app called "contoso" on Azure's default domain for deployed web apps: "azurewebsites.net".*
>
 (see [[Azure App Services]])

``` PowerShell
New-AzDnsRecordSet -ZoneName contoso.com -ResourceGroupName "MyAzureResourceGroup" `
 -Name "www" -RecordType "CNAME" -Ttl 600 `
 -DnsRecords (New-AzDnsRecordConfig -cname "contoso.azurewebsites.net")
```
>- *This command create a "CNAME" record set that points the subdomain "www.contoso.com" to the web app: "contoso.azurewebsites.net".*


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

