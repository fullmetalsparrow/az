After running [[genssl.sh]], use the following commands to verify certificate content and mutual TLS authentication:


### Verify the Certificate Chain Bundle
---
``` bash
$ openssl verify \
	-CAfile /etc/ssl/root/certs/root.crt \
	/etc/ssl/intermediate/certs/ca-chain-bundle.crt
```