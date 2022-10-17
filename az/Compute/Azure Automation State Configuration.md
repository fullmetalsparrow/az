![[az_automation_config_flow.png]]
*(see [[VM Extensions]])*

### Azure Automatation State Configuration
	An Azure service used to write, manage, and compile PowerShell Desired State Configuration (DSC) configurations, import DSC resources, and assign configurations to target nodes (VM's).
*Supports Windows 7 and up as well as Windows Server 2008 and up.*


### Desired State Configuration (DSC)
	A declarative management platform that Azure Automation State Configuration uses to configure, deploy, and control systems.
*DSC makes VM deployments idempotent.*


### Local Configuration Manager (LCM)
	A component of the Windows Management Framework (WMF) responsible for updating the state of a node to match a desired state.
*LCM runs in Push Mode or Pull Mode*

- LCM in Pull Mode polls the Pull Server every 15 minutes by default for changes in node configuration state.