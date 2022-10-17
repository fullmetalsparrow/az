![[vpn_gateway1.png]]
![[vpn_gateway_steps.png]]


### VPN Gateway
	A specific type of virtual network (vnet) gateway that is used to encrypted traffic between an Azure vnet and an on-premises locations over the Internet.
*Each vnet can ==only== have **ONE** VPN Gateway.*

- VPN Gateway tunnels all share the available gateway bandwidth.
- VPN Gateway is configured in an active-passive failover configuration by default, but can be configured for an active-active configuration.
- VPN Gateway must be in a gateway subnet named ==*GatewaySubnet*==.
- VPN Gateway types can either be ==route-based== (preferred) or ==policy-based==:
	- Route-based VPN Gateways can used alonogside an [[Azure ExpressRoute]] gateway.
	- Policy-based VPN Gateways only support Internet Key Exchange Version 1 (IKEv1) and can only have one IPSec tunnel active at a time.
	- Policy-based VPN Gateways are only supported on the Basic [[VPN Gateway SKU]] and for Site-to-Site (S2S) connections.
*VPN Gateway type cannot be changeed after the vnet gateway has been created.*