### Azure Storage
	An Azure service that is used for storing files (blobs, data lake stores, VM disks, and file shares), messages (Azure Queues),tables, and other types of information

- Azure Storage encrypts all data-at-rest using AES-256 Storage Service Encryption (SSE) by default
- Azure Storage creates two 512-bit root access keys for every created [[Storage Accounts]].
	- *If using Azure Key Vault to store access keys, the storage account and key vault must be in the same Azure region.*
	- *If using personally-generated keys, Azure requires at least 2048-bit key length for public-private key pairs.*
- Azure Storage can encrypt data-in-transit using Client-Side Encryption, HTTPS, or Server Message Block (SMB) 3.0.
- Azure Storage data can be accessed via a URL using HTTP/HTTPS
- Azure Storage does ==NOT== support SSL for custom domain names.