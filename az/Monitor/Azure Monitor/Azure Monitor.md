![[az_monitor.png]]

### Azure Monitor
	An Azure service that collects log data from applications, virtual machines (VM's), resourrcs, subscriptions, and tenants.
*Azure Monitor can collect log data from any REST client using the Data Collector API*

### Logs
	A recording of time-stamped information about changes made to resources.
*Log data is organized in table records and stored in a [[Log Analytics Workspace]].*

### Platform Logs
	A log that provides diagnostic and auditing information for Azure resources.

### Schema
	A set of tables of logically grouped together.

### Metric
	A numerical value that describes some aspect of a system at a point in time.

### Action Group
	A collection of notification preferences made by the subscription owner.

- Action group actions can be:
	1. E-mail notification to Azure AD members.
	2. E-mail, SMS, Push, or Voice notification.
	3. Automated runbook.
	4. Azure Function.
	5. ITSM.
	6. Logic App.
	7. Webhook.

### Webhook
	A HTTP/HTTPS endpoint that allows external applications to communicate.

### Smart Group
	A machine-learning generated group of alerts.
*The name of the smart group is assigned based on the name of the first alert in the group.*

### Dimensions
	Define metric alert rules and apply them to multiple instances.
*Dimensions support wildcard declarations.*