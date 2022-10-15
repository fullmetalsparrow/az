### CNAME Records
---
- Use CNAME records to point to custom domains in Azure Storage
- Use *asverify* to avoid downtimes in updating records

| CNAME record | Target |
| --- | --- |
| asverify.blobs.contoso.com | asverify.contosoblobs.blob.core.windows.net |
| blobs.contoso.com | contosoblobs.blob.core.windows.net |

*==blobs.contoso.com== is the custom domain and ==contosoblobs== is the storage account*
