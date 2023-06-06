# SecureX-Workflow-PaloAltoCortexXDR-IncidentReport

This workflow is a simple example of reporting and summarizing major contents of Incidents of reported to Palo Alto Cortex XDR to Cisco SecureX Incident Manager and Cisco Webex Messaging room. The reporting destination could be changed as needed.

The workflow will create summary informations to Cisco SecureX and Cisco webex which is reported from Palo Alto Cortex XDR "Incident". Needed fileld would be customizable. Incident IDs, Descriptions, Assigned User Mail is provided, Changed and added as you needed.

<img width="1163" alt="スクリーンショット 2023-06-06 20 45 31" src="https://github.com/sig666/SecureX-Workflow-PaloAltoCortexXDR-IncidentReport/assets/45964305/5b18a3dc-1baa-497c-9488-7ebff6113d96">

# Change Log
- Jun, 6, 2023 : Initial Release

# Requirements

The following system atomics are used by this workflow:

- Threat Response - Generate Access Token
- Threat Response - Enrich Observable
- Threat Response - Create Casebook
- Set Variables
- JSONPath Query
    Send Email
