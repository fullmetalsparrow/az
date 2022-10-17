![[aks_scaling.png]]
![[aks_aci.png]]

### Kubernetes Horizontal Pod Autoscaler (HPA)
	A Kubernetes component that monitors resource demand and auto-scales replicas.

- HPA checks the Kubernetes Metrics API every 30 seconds by default for any required changes in replica counts.
- HPA scale up delay is 3 minutes by default whenever a scale up event is called.
- HPA scale down delay is 5 minutes by default whenever a scale down event is called.


### Kubernetes Cluster Autoscaler
	A Kubernetes component that autoscales node instances based on requested compute reources in the node pool.

- Cluster autoscaler checks the Kubernetes Metrics API every 10 seconds by default for any required changes in node count.
- Cluster autoscaler deprovisions inactive nodes every 10 minutes by default and pods are transferred to an active node.