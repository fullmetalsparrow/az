### App Service Plan
	Defines a set of compute resources for a web application to run.

![[app_serv_plan_pricing.png]]

- App Service Plans define a region, number of VM's, and size of VM's.
- App Service Plans share the same compute resources with all web apps configured under the plan.
- App Service Plans support true auto-scaling:
	1. Schedule-Based: meet peak demand times.
	2. Metric-Based: scale based on performance thresholds.
- App Service Plans can scale up or scale out:
	1. Scale Up: upgrading to a higher price tier.
	2. Scale Out: increase number of VM instances.