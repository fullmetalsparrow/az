![[app_gateway_overview.png]]
![[app_gateway_config.png]]


### Azure Application Gateway
	An Azure service that manages the requests that client applications send to web applications.

- Azure App Gateway uses application layer routing.
- Azure App Gateway uses round robin load balancing for servers in each backend pool.
- Azure App Gateway supports path-based (URL) or multi-site (hostname) routing.
- Azure App Gateway supports HTTP, HTTPS, HTTP/2, and WebSocket protocols.
- Azure App Gateway support true auto-scaling.
- Azure App Gateway has an optional Web Application Firewall (WAF).
- Azure App Gateway performs health checks every 30 seconds by default.
- Azure App Gateway uses 1+ listeners to receive incoming requests.


### Listeners
	An Azure App Gateway component that accepts traffic arriving on a specified combination of protocol, port, host, and IP address.

- Listeners route requests to a backend pool of servers based on routing rules.
- Listeners can be basic (URL) or multi-site (hostname).
- Listeners handle Transport Layer Security (TLS) / Secure Sockets Layer (SSL) certificates for the Azure App Gateway.

### Routing Rules
	An Azure App Gateway that binds the listener to backend pools.

- Routing rules have an associated set of HTTP settings.
- Routing rules specify the method of End-to-End (E2E) encryption.