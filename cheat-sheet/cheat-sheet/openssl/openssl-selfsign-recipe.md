### Make OpenSSL Files and Directories
---
``` bash
#!/usr/bin/bash

dir=/etc/ssl

mkdir -p $dir/{root,intermediate,server,client}/{certs,private,secret}
mkdir -p $dir/config/ext/{server,client}
touch $dir/{root,intermediate}/index.txt

for cnf in server client; do
    touch $dir/config/ext/${cnf}.cnf
done

for ser in root intermediate; do
    echo 01 > $dir/$ser/serial
    echo 01 > $dir/$ser/crlnumber
    touch $dir/config/${ser}.cnf
done
```


### Create the CA Certificate Config
---
``` bash
$ cat << "EOF" > /etc/ssl/config/root.cnf

####################################################################
[ ca ]
default_ca	= CA_default		# The default ca section for openssl ca cmd

####################################################################
[ CA_default ]

dir		    = /etc/ssl/root		# Where everything is kept
certs		= $dir/certs		# Where the issued certs are kept
crl_dir		= $dir/crl		# Where the issued crl are kept
database	= $dir/index.txt	# database index file.
new_certs_dir	= $dir/newcerts		# default place for new certs.
certificate	= $dir/certs/root.crt 	        # The CA certificate
serial		= $dir/serial 		# The current serial number
crlnumber	= $dir/crlnumber	# the current crl number
crl		= $dir/crl.pem 		# The current CRL
private_key	= $dir/private/root.key   # The private key
x509_extensions	= usr_cert		# The extensions to add to the cert
crl_extensions	= crl_ext       # The extensions to add to the CRL
name_opt 	= ca_default		# Subject Name options
cert_opt 	= ca_default		# Certificate field options
default_days	= 365			# how long to certify for
default_crl_days= 30			# how long before next CRL
default_md	= sha256		# use public key default MD
preserve	= no			# keep passed DN ordering
policy		= policy_match


# For the root CA policy - MIGHT NEED FOR INTERMEDIATE IF GEO MATTERS
[ policy_match ]
countryName		= match # client CSRs must match CA
stateOrProvinceName	= match # client CSRs must match CA
organizationName	= match # client CSRs must match CA
organizationalUnitName	= optional
commonName		= supplied
emailAddress		= optional

####################################################################

[ req ] # for openssl req cmd
default_bits		= 2048
default_keyfile 	= privkey.pem
distinguished_name	= req_distinguished_name
attributes		= req_attributes
# x509_extensions	= v3_ca	# The extensions to add to the self signed cert
# req_extensions = v3_req # The extensions to add to a certificate request
string_mask = utf8only


[ req_distinguished_name ]
countryName			= Country Name (2 letter code)
countryName_default		= AU
countryName_min			= 2
countryName_max			= 2
stateOrProvinceName		= State or Province Name (full name)
stateOrProvinceName_default	= Some-State
localityName			= Locality Name (eg, city)
0.organizationName		= Organization Name (eg, company)
0.organizationName_default	= Internet Widgits Pty Ltd
organizationalUnitName		= Organizational Unit Name (eg, section)
organizationalUnitName_default	= Admin
commonName			= Common Name (e.g. server FQDN or YOUR name)
commonName_max			= 64
emailAddress			= Email Address
emailAddress_max		= 64


[ req_attributes ]
challengePassword		= A challenge password
challengePassword_min		= 4
challengePassword_max		= 20
unstructuredName		= An optional company name


# These extensions are added when 'ca' signs a request.
[ usr_cert ]

basicConstraints=CA:FALSE
subjectKeyIdentifier=hash
authorityKeyIdentifier=keyid,issuer
subjectAltName=email:copy
issuerAltName=issuer:copy


# Extensions to add to a certificate request - MUST BE MANUALLY SPECIFIED
[ v3_req ]

basicConstraints = CA:FALSE
keyUsage = nonRepudiation, digitalSignature, keyEncipherment


# Extensions for a typical CA - MUST BE MANUALLY SPECIFIED
[ v3_ca ]

basicConstraints = critical,CA:true
subjectKeyIdentifier=hash
authorityKeyIdentifier=keyid:always,issuer
# keyUsage = cRLSign, keyCertSign # does not work with self-signed certs
subjectAltName=email:copy
issuerAltName=issuer:copy


[ v3_intermediate_ca ]
subjectKeyIdentifier = hash
authorityKeyIdentifier = keyid:always,issuer
basicConstraints = critical,CA:true,pathlen:0
keyUsage = critical,digitalSignature,cRLSign,keyCertSign


[ crl_ext ]

issuerAltName=issuer:copy
authorityKeyIdentifier=keyid:always
EOF
```


### Create the Intermediate CA Config
---
``` bash
$ cat << "EOF" > /etc/ssl/config/intermediate.cnf

####################################################################
[ ca ]
default_ca	= CA_default		# The default ca section for openssl ca cmd

####################################################################
[ CA_default ]

dir		    = /etc/ssl/intermediate		# Where everything is kept
certs		= $dir/certs		# Where the issued certs are kept
crl_dir		= $dir/crl		# Where the issued crl are kept
database	= $dir/index.txt	# database index file.
new_certs_dir	= $dir/newcerts		# default place for new certs.
certificate	= $dir/certs/intermediate.crt 	        # The CA certificate
serial		= $dir/serial 		# The current serial number
crlnumber	= $dir/crlnumber	# the current crl number
crl		= $dir/crl.pem 		# The current CRL
private_key	= $dir/private/intermediate.key   # The private key
x509_extensions	= usr_cert		# The extensions to add to the cert
crl_extensions	= crl_ext       # The extensions to add to the CRL
name_opt 	= ca_default		# Subject Name options
cert_opt 	= ca_default		# Certificate field options
default_days	= 365			# how long to certify for
default_crl_days= 30			# how long before next CRL
default_md	= sha256		# use public key default MD
preserve	= no			# keep passed DN ordering
policy		= policy_anything


# For the intermediate CA policy - MIGHT NEED MATCH IF GEO MATTERS
[ policy_anything ]
countryName		= optional
stateOrProvinceName	= optional
localityName		= optional
organizationName	= optional
organizationalUnitName	= optional
commonName		= supplied
emailAddress		= optional

####################################################################

[ req ] # for openssl req cmd
default_bits		= 2048
default_keyfile 	= privkey.pem
distinguished_name	= req_distinguished_name
attributes		= req_attributes
# x509_extensions	= v3_ca	# The extensions to add to the self signed cert
# req_extensions = v3_req # The extensions to add to a certificate request
string_mask = utf8only


[ req_distinguished_name ]
countryName			= Country Name (2 letter code)
countryName_default		= AU
countryName_min			= 2
countryName_max			= 2
stateOrProvinceName		= State or Province Name (full name)
stateOrProvinceName_default	= Some-State
localityName			= Locality Name (eg, city)
0.organizationName		= Organization Name (eg, company)
0.organizationName_default	= Internet Widgits Pty Ltd
organizationalUnitName		= Organizational Unit Name (eg, section)
organizationalUnitName_default	= Admin
commonName			= Common Name (e.g. server FQDN or YOUR name)
commonName_max			= 64
emailAddress			= Email Address
emailAddress_max		= 64


[ req_attributes ]
challengePassword		= A challenge password
challengePassword_min		= 4
challengePassword_max		= 20
unstructuredName		= An optional company name


# These extensions are added when 'ca' signs a request.
[ usr_cert ]

basicConstraints=CA:FALSE
subjectKeyIdentifier=hash
authorityKeyIdentifier=keyid,issuer
subjectAltName=email:copy
issuerAltName=issuer:copy


# Extensions to add to a certificate request - MUST BE MANUALLY SPECIFIED
[ v3_req ]

basicConstraints = CA:FALSE
keyUsage = nonRepudiation, digitalSignature, keyEncipherment


# Extensions for a typical CA - MUST BE MANUALLY SPECIFIED
[ v3_ca ]

basicConstraints = critical,CA:true
subjectKeyIdentifier=hash
authorityKeyIdentifier=keyid:always,issuer
# keyUsage = cRLSign, keyCertSign # does not work with self-signed certs
subjectAltName=email:copy
issuerAltName=issuer:copy


[ v3_intermediate_ca ]

subjectKeyIdentifier = hash
authorityKeyIdentifier = keyid:always,issuer
basicConstraints = critical,CA:true,pathlen:0
keyUsage = critical,digitalSignature,cRLSign,keyCertSign


[ crl_ext ]

issuerAltName=issuer:copy
authorityKeyIdentifier=keyid:always
EOF
```


### Create the Server Certificate Config
---
``` bash
$ cat << "EOF" > /etc/ssl/config/ext/server.cnf

basicConstraints = CA:FALSE
nsCertType = server
nsComment = "OpenSSL Generated Server Certificate"
subjectKeyIdentifier = hash
authorityKeyIdentifier = keyid,issuer:always
keyUsage = critical, digitalSignature, keyEncipherment
extendedKeyUsage = serverAuth
# subjectAltName = @alt_names

[alt_names]
# IP.1 = 192.168.0.114 # TODO: change to an applicable value
# IP.2 = 10.0.2.15 # TODO: change to an applicable value
# DNS.1 = *.example.com # TODO: change to an applicable value
# DNS.2 = example.com # TODO: change to an applicable value
EOF
```
*==The above config is using a wildcard SAN for the DNS values, but can be changed to a single server==*



### Create the Client Certificate Config
---
``` bash
$ cat << "EOF" > /etc/ssl/config/ext/client.cnf

basicConstraints = CA:FALSE
nsCertType = client, email
nsComment = "OpenSSL Generated Client Certificate"
subjectKeyIdentifier = hash
authorityKeyIdentifier = keyid,issuer
keyUsage = critical, nonRepudiation, digitalSignature, keyEncipherment
extendedKeyUsage = clientAuth, emailProtection
EOF
```


### Generate a CA Private Key (RSA)
---
``` bash
$ openssl genpkey \
	-algorithm RSA \
	-pkeyopt rsa_keygen_bits:4096 \
	-out /etc/ssl/root/private/root.key
```
*Output is in PKCS #8 format*
**==Secure after entire certificate creation process==**


### Generate a Self-Signed CA Certificate
---
``` bash
$ openssl req \
	-new -x509 \
	-config /etc/ssl/config/root.cnf \
	-extensions v3_ca
	-days 3650 \
	-key /etc/ssl/root/private/root.key \
	-out /etc/ssl/root/certs/root.crt \
	-outform PEM
```


### Generate an Intermediate CA Private Key (RSA)
---
``` bash
$ openssl genpkey \
	-algorithm RSA \
	-pkeyopt rsa_keygen_bits:2048 \
	-pass file:/etc/ssl/intermediate/secret/intermediate.enc
	-out /etc/ssl/intermediate/private/intermediate.key
```
*Output is in PKCS #8 format*


### Generate an Intermediate CA Certificate Signing Request (CSR)
---
``` bash
$ openssl req \
	-new -sha256 \
	-config /etc/ssl/config/intermediate.cnf \
	-passin file:/etc/ssl/intermediate/secret/intermediate.enc \
	-key /etc/ssl/intermediate/private/intermediate.key \
	-out /etc/ssl/intermediate/certs/intermediate.csr \
	-outform PEM
```


### Generate an Intermediate CA Certificate
---
``` bash
$ openssl ca \
	-config /etc/ssl/config/root.cnf \
	-extensions v3_intermediate_ca \
	-days 1825 \
	-notext \
	-batch \
	-in /etc/ssl/intermediate/certs/intermediate.csr \
	-out /etc/ssl/intermediate/certs/intermediate.crt \
	-outform PEM
```


### Create the Certificate Chain Bundle
``` bash
$ cat /etc/ssl/intermediate/certs/intermediate.crt /etc/ssl/root/certs/root.crt > /etc/ssl/intermediate/certs/ca-chain-bundle.crt
```


### Generate a Server Private Key (RSA)
---
``` bash
$ openssl genpkey \
	-algorithm RSA \
	-pkeyopt rsa_keygen_bits:2048 \
	-pass file:/etc/ssl/server/secret/server.enc \
	-out /etc/ssl/server/private/server.key
```
*Output is in PKCS #8 format*


### Generate a Server Certificate Signing Request (CSR)
---
``` bash
$ openssl req \
	-new -sha256 \
	-config /etc/ssl/config/intermediate.cnf \
	-passin file:/etc/ssl/server/secret/server.enc \
	-key /etc/ssl/server/private/server.key \
	-out /etc/ssl/server/certs/server.csr \
	-outform PEM
```


### Generate a Server Certificate
---
``` bash
$ openssl ca \
	-config /etc/ssl/config/intermediate.cnf \
	-extfile /etc/ssl/config/ext/server.cnf \
	-days 365 \
	-notext \
	-batch \
	-passin file:/etc/ssl/intermediate/secret/intermediate.enc \
	-in /etc/ssl/server/certs/server.csr \
	-out /etc/ssl/server/certs/server.crt \
	-outform PEM
```


### Generate a Client Private Key (RSA)
---
``` bash
$ openssl genpkey \
	-algorithm RSA \
	-pkeyopt rsa_keygen_bits:2048 \
	-passout file:/etc/ssl/client/secret/client.enc \
	-out /etc/ssl/client/private/client.key
```
*Output is in PKCS #8 format*


### Generate a Client Certificate Signing Request (CSR)
---
``` bash
$ openssl req \
	-new -sha256 \
	-config /etc/ssl/config/intermediate.cnf \
	-passin file:/etc/ssl/client/secret/client.enc \
	-key /etc/ssl/client/private/client.key \
	-out /etc/ssl/client/certs/client.csr \
	-outform PEM
```


### Generate a Client Certificate
---
``` bash
$ openssl ca \
	-config /etc/ssl/config/intermediate.cnf \
	-extfile /etc/ssl/config/ext/client.cnf \
	-days 365 \
	-notext \
	-batch \
	-passin file:/etc/ssl/intermediate/secret/intermediate.enc \
	-in /etc/ssl/client/certs/client.csr \
	-out /etc/ssl/client/certs/client.crt \
	-outform PEM
```