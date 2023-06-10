# SecureX-Workflow-PaloAltoCortexXDR-IncidentReport

This workflow is a simple example to generate the summary report of Palo Alto Cortex XDR which includes major contents of some of filtered Incidents information to <B>Cisco SecureX Ribbon Incident Manager</B> and to <B>Cisco Webex Messaging room</B>. The reporting destination could be changed as you would like to configure.

Needed fileld which like Incident IDs, Incident Names, Status, Severity, Descriptions, XDR_Report URLs, Alert Counts, Assigned User Mail and other Incident information will be provided and be customizable.

This workflow sample is used of Scheduled Triger and set of Incident Scope in 1st API Call (HTTP Service) to Cortex XDR API endpoint but is could be changed. If it needs to configure real-time alerting, it should be set and change to Webhook Triger co-working with Cortex XDR.

<img width="1163" alt="スクリーンショット 2023-06-06 20 45 31" src="https://github.com/sig666/SecureX-Workflow-PaloAltoCortexXDR-IncidentReport/img/workflow2.png">

# Change Log
- Jun, 6, 2023 : Initial Release

# Requirements

The following system atomics are used by this workflow:
- Web Service - HTTP Request
- Table - Read Table from JSON
- Core - Set Variables
- Core - Convert Json to Xml
- Core - Replace String
- Threat Response - Create Incident
- Webex - Search for Room
- Webex - Post Message to Room

The following atomic actions must be imported before you can import this workflow:
- None

The Targets and account keys listed at the bottom of the page
- <B>Cortex XDR</B> : HTTP Target
- <B>Private_CTIA_Target</B> : HTTP Target (Default Created)
  - This workflow use New SecureX Token. To change <B>No Account Keys</B> to <B>False</B> with your New SecureX Token authentication.
  - https://ciscosecurity.github.io/sxo-05-security-workflows/account-keys/securex-token

# Workflow Steps
- Request and confirm needed Variables
- Request to call Palo Alto Cortex XDR Incident
- Filtering and creating Incident Text
- Create SecureX Threat Response Incident
- Create & post Webex Incident message

# Installation
- Browse to your SecureX orchestration instance. This wille be a different URL depending on the region your account is in:
  - US: https://securex-ao.us.security.cisco.com/orch-ui/workflows/
  - EU: https://securex-ao.eu.security.cisco.com/orch-ui/workflows/
  - APJC: https://securex-ao.apjc.security.cisco.com/orch-ui/workflows/

- Click on <B>Import</B> to import the workflow.
- Select <B>Browse</B> from Import From
- Open <B> SecureX-Workflow-PaloAltoCortexXDR-IncidentReport.json</B> and Copy text
- Paste to <B>Paste JSON or upload the workflow to import</B> and click <B>Import
</B>
<img width="726" alt="install" src="https://github.com/sig666/SecureX-Workflow-PaloAltoCortexXDR-IncidentReport/assets/45964305/cc77f62d-1673-4ca7-bdfa-d2bfcc38f237">

# Configuration
- Set the Workflow Variable of `Palo Alto Cortex XDR Key` to your Palo Alto Cortex XDR API Key - ex: XZ2QnfySy1yL....
- Set the Workflow Variable of `Palo Alto Cortex XDR Key ID` to your Palo Alto Cortex XDR API Key ID - ex: 12
- Set the Workflow Variable of `Webex Access Token` to your Webex Messaging Access Token (Bearer) - ex: ZGQ5OWVmZ...
- Set the Workflow Variable of `Webex Room Name` to your Webex Space name which you want to post
- Set and Change `R. OPERAND` in `Conditions` setting to your apporopriate CTR Endpoint - ex: CTR_API
- (Optional) change `search_from` and `search_to` count to the scope number that you want to fetch the incidents
  - Palo Alto Cortex XDR API Document
  - https://cortex-panw.stoplight.io/docs/cortex-xdr/axpm6b98x4p18-cortex-xdr-api-overview

# Targets
Target Group: `Default TargetGroup`

|Target Name|Type|Details|Account Keys|Notes|
|:---|:---|:---|:---|:---|
|CTR_For_Access_Token_New|HTTP Endpoint|Protocol: HTTPS,　Host: `visibility.apjc.amp.cisco.com`,　Path: `/iroh`|`False` with New SecureX Token Credential|Need to Configure|
|Cortex XDR|HTTP Endpoint|Protocol: HTTPS,　Host: `<your_api_host>.xdr.jp.paloaltonetworks.com`,　Path: None|`True`|Need to Create|
|Private_CTIA_Target|HTTP Endpoint|Protocol: HTTPS,　Host: `private.intel.apjc.amp.cisco.com`,　Path: None|CTR_Credentials|Created by Default|

By default, the Default TargetGroup may doesn't have Cortex XDR targets. You will need to update the target group and add New HTTP Endpoint to the target types included. More information about target groups can be found here https://ciscosecurity.github.io/sxo-05-security-workflows/targets/groups.

# Account Keys
|Account Key Name|Type|Details|Notes|
|:---|:---|:---|:---|
|SecureX-Token-1|SecureX Token|Your valid SecureX Token. This is needed for get Threat Response Token and post Message to Casebook|https://ciscosecurity.github.io/sxo-05-security-workflows/account-keys/securex-token|
