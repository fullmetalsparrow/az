- Azure App Services support authentication and authorization using federation, encryption, JSON web tokens (JWT) management, and grant types.
- Azure App Services pass along authentication information in the HTTP headers when using authenticated requests.
- Azure App Services can allow anonymous requests to defer authorization of unauthenticated traffic to application code.
	- ***Log in with \<provider\>** configuration option redirects all anonymous requests to **/.auth/login/\<provider\>** when using **Allow only authenticated requests***
- Azure authentication and authorization traces are referenced as *EasyAuthModule_32/64* in log files.



### Azure App Service Nuances
---
> - *Azure App Service ==CANNOT== be migrated to a new [[Resource Groups]] with SSL certificates configured.*