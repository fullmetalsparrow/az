### App Service Plan
	Defines a set of compute resources for a web application to run.

![[app_serv_plan_pricing.png]]
*(see [[Deployment Slots]])*

### App Service Plan Deployment Steps
---
> *New-AzResourceGroup > New-AzAppServicePlan > New-AzWebApp > New-AzWebAppSlot* 

- [[Azure App Services]] Plans define a region, number of VM's, and size of VM's.
- App Service Plans share the same compute resources with all web apps configured under the plan.
- App Service Plans require a paid tier to use custom [[Azure DNS]] names.
- App Service Plans support true auto-scaling:
	1. Schedule-Based: meet peak demand times.
	2. Metric-Based: scale based on performance thresholds.
- App Service Plans can scale up or scale out:
	1. Scale Up: upgrading to a higher price tier.
	2. Scale Out: increase number of VM instances.



### App Service Plan Nuances
---
> - *Both Windows and Linux platform plans support PHP and .NET Core runtime stacks.*
> - *ASP .Net 4.7 runtime stack is only supported on the Windows platform.*
> - *Ruby 2.6 runtime stack is only supported on the Linux platform.*
> - *There are no restrictions on custom domain names based on pricing tier.*