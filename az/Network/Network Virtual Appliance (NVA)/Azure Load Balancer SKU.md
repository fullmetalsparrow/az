### [[Azure Load Balancer]] SKU
---
![[load_balancer_skus.png]]

- Basic SKU's can be upgraded to Standard SKU's
- Basic SKU's can only generate backend pool endpoints for a single availability set or scale set.


### Azure Load Balancer SKU Nuances
---
> - *Basic load balancers can ==ONLY== balance for a single __VM [[Availability Set]]__ or __VM [[Scale Sets]]__.*
> - *Standard load balancers can balance VM's created in the same __virtual network__ across a blend of single machines, availability sets, and scale sets.*

