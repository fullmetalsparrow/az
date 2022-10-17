![[aks_summary.png]]
- Pods are networked via:
	1. Cluster IP's: access for other internal applications.
	2. NodePort: direct access using a port and IP mapping.
	3. LoadBalancer: internal or external.
	4. ExternalName: access using DNS.

### Cluster/Master Node
	An Azure-managed node that orchestrates the other worker/agent nodes.

### kubelet
	The Kubernetes agent that processes the orchestration requests from the master node and schedules the running of requested container.

### kube-proxy
	The Kubernetes agent that handles the virtual networking on each node.

### Container Runtime
	The component that allows containerized applications to run and interact with other Azure resources.

### Default Node Pool
	The initial number of nodes and sizes defined for an AKS cluster that run the agent nodes.