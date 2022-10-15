### Shared Access Signature
	A Uniformed Resource Identifier (URI) that grants restricted access rights to Azure Storage resources.

- SAS are secured through the storage account keys or Azure AD credentials.
	- *Only way to revoke a SAS token without a [[Stored Access Policy]] is to regenerate the storage account keys.*
	- *SAS's secured through Azure AD credentials are called **user delegation SAS's** ([[Blobs]] level only)*


- SAS provides **account-level** and **service-level** access control:
	1. Account-level: multiple resources in 1+ storage services (blobs, messages, tables, etc...)
	2. Service-level: single resource in a single storage service (blobs, messages, tables, etc...)