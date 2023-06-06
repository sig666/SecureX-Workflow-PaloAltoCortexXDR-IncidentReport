# SecureX-Workflow-PaloAltoCortexXDR-IncidentReport

This workflow is a simple example of generating the summary report which includes major contents of some of filtered Incidents informations of  Palo Alto Cortex XDR solutions to <B>Cisco SecureX Ribbon Incident Manager</B> and to <B>Cisco Webex Messaging room</B>. The reporting destination could be changed as you would like to configure as followed.

The workflow will create summary informations "Cisco SecureX Incident Manager Report" and "Cisco webex Message" which is reported from Palo Alto Cortex XDR "Incident". Needed fileld which includes Incident IDs, Descriptions, Assigned User Mail and others will be provided and becustomizable.

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
