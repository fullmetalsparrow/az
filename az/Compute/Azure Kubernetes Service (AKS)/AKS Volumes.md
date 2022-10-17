![[aks_storage.png]]

### Persistent Volume (PV)
	A storage resource created and managed by the Kubernetes API that can exist beyond the lifetime of an individual pod using Azure Disks or Azure Files.
*A PV can statically created by a cluster admin or dynamically created by the Kubernetes API server.*

### Persistent Volume Claim
	An Azure Disks or Azure Files request that defines the storage class, access mode, and size for a one-to-one mapping to a created persistent volume.

- AKS data volumes for a single pod can be created in [[Azure Disks]] via a Kubernete DataDisk resource.
- AKS data volumes for multiple pods can be persisted using a Server Message Block (SMB) 3.0 file share backed by a [[Storage Accounts]] in [[Azure Files]].