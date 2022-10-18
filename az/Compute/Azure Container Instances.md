![[az_vm_vs_contain.png]]
![[az_contain1.png]]

- Container group containers share a lifecycle, resources, local network, and storage volumes.
- Container groups do ==NOT== support auto-scaling.
- Container groups are ==ONLY== supported in Linux currently
- Container group resources are additive in the resource pool.
- Container groups can be deployed using ARM templates or YAML files.
	- *YAML files are preferred for container-only deployments.*
