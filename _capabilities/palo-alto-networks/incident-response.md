---
categories:
- incident-management
consumed_apis: []
description: Unified incident response capability for SOC analysts — investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface exposure across Cortex XDR, XSIAM, XSOAR, and Xpanse.
layout: capability
name: Palo Alto Networks Incident Response
operations:
- description: List XDR incidents.
  method: GET
  name: list-incidents
  path: /v1/incidents
- description: Create an incident in XSOAR.
  method: POST
  name: create-incident
  path: /v1/incidents
- description: Search XDR incidents with filters.
  method: POST
  name: search-incidents
  path: /v1/incidents/search
- description: Get incident details from XDR.
  method: GET
  name: get-incident-details
  path: /v1/incidents/{incident_id}
- description: Update an XDR incident.
  method: PUT
  name: update-incident
  path: /v1/incidents/{incident_id}
- description: Search XSIAM incidents with filters.
  method: POST
  name: search-xsiam-incidents
  path: /v1/xsiam-incidents/search
- description: Search XDR alerts with filters.
  method: POST
  name: search-xdr-alerts
  path: /v1/alerts/search
- description: Search XSIAM alerts with filters.
  method: POST
  name: search-xsiam-alerts
  path: /v1/xsiam-alerts/search
- description: List XDR endpoints with filters.
  method: POST
  name: search-endpoints
  path: /v1/endpoints/search
- description: Isolate endpoints.
  method: POST
  name: isolate-endpoints
  path: /v1/endpoints/isolate
- description: Unisolate endpoints.
  method: POST
  name: unisolate-endpoints
  path: /v1/endpoints/unisolate
- description: Initiate a scan on endpoints.
  method: POST
  name: scan-endpoints
  path: /v1/endpoints/scan
- description: List XSIAM endpoints with filters.
  method: POST
  name: search-xsiam-endpoints
  path: /v1/xsiam-endpoints/search
- description: Run a script on endpoints.
  method: POST
  name: run-script
  path: /v1/scripts/run
- description: Get script execution results.
  method: POST
  name: get-script-results
  path: /v1/scripts/results
- description: Start an XQL query on XDR.
  method: POST
  name: start-xql-query
  path: /v1/queries
- description: Get XQL query results from XDR.
  method: POST
  name: get-xql-query-results
  path: /v1/queries/results
- description: Start an XQL query on XSIAM.
  method: POST
  name: start-xsiam-xql-query
  path: /v1/xsiam-queries
- description: Get XQL query results from XSIAM.
  method: POST
  name: get-xsiam-xql-query-results
  path: /v1/xsiam-queries/results
- description: Get internet-exposed assets from Xpanse.
  method: POST
  name: search-exposed-assets
  path: /v1/attack-surface/assets/search
- description: Get internet exposure details for specific assets from Xpanse.
  method: POST
  name: get-asset-details
  path: /v1/attack-surface/assets/{asset_id}
- description: Search Xpanse incidents with filters.
  method: POST
  name: search-xpanse-incidents
  path: /v1/attack-surface/incidents/search
- description: Update an Xpanse incident.
  method: PUT
  name: update-xpanse-incident
  path: /v1/attack-surface/incidents/{incident_id}
- description: Get attack surface rules from Xpanse.
  method: POST
  name: search-attack-surface-rules
  path: /v1/attack-surface/rules/search
- description: Update an attack surface rule in Xpanse.
  method: PUT
  name: update-attack-surface-rule
  path: /v1/attack-surface/rules/{rule_id}
- description: Get exposed services from Xpanse.
  method: POST
  name: search-services
  path: /v1/attack-surface/services/search
- description: Get owned IP ranges from Xpanse.
  method: POST
  name: search-ip-ranges
  path: /v1/attack-surface/ip-ranges/search
- description: Create a new investigation in XSOAR.
  method: POST
  name: create-investigation
  path: /v1/investigations
- description: Retrieve a specific investigation by ID from XSOAR.
  method: GET
  name: get-investigation
  path: /v1/investigations/{investigation_id}
- description: Add an entry to an investigation in XSOAR.
  method: POST
  name: add-entry
  path: /v1/investigations/entries
- description: List available playbooks in XSOAR.
  method: GET
  name: list-playbooks
  path: /v1/playbooks
- description: Run a playbook on an investigation in XSOAR.
  method: POST
  name: run-playbook
  path: /v1/playbooks/run
- description: Search for available integrations in XSOAR.
  method: GET
  name: search-integrations
  path: /v1/integrations
- description: Search for integration instances in XSOAR.
  method: POST
  name: search-integration-instances
  path: /v1/integrations/instances/search
- description: List XSIAM assets with filters.
  method: POST
  name: search-xsiam-assets
  path: /v1/xsiam-assets/search
- description: Configure a datasource for XSIAM ingestion.
  method: POST
  name: configure-datasource
  path: /v1/xsiam-datasources
- description: Get audit management logs from XDR.
  method: POST
  name: get-xdr-audit-logs
  path: /v1/audit-logs/xdr
- description: Get audit management logs from Xpanse.
  method: POST
  name: get-xpanse-audit-logs
  path: /v1/audit-logs/xpanse
- description: Get management logs from XSIAM.
  method: POST
  name: get-xsiam-management-logs
  path: /v1/audit-logs/xsiam
personas:
- description: Investigates security incidents, triages alerts, and coordinates response actions.
  id: soc-analyst
  name: SOC Analyst
- description: Executes containment, eradication, and recovery actions during security incidents.
  id: incident-responder
  name: Incident Responder
- description: Proactively searches for threats and IOCs across telemetry data.
  id: threat-hunter
  name: Threat Hunter
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- list xsiam assets with optional filters.
- analyzes suspicious files and samples for malware characteristics.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- unisolate endpoints and restore network connectivity via xdr.
- start an xql query on xdr.
- get owned ip ranges from xpanse.
- configure xsiam datasources.
- xdr scan endpoints
- malware researcher
- threat intelligence
- xsoar create incident
- identity and access management, tenant hierarchies, and subscription management.
- get xql query results from xdr.
- run a script on endpoints via xdr.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- get internet exposure details for specific assets from xpanse.
- enterprise browser policy management and secure browsing.
- search xdr alerts.
- get internet-exposed assets from xpanse.
- manage enterprise browser policies, user sessions, and deployments.
- cloud security
- search incidents with filters.
- xpanse list attack surface rules
- search xsiam assets.
- proactively searches for threats and iocs across telemetry data.
- xdr get incident details
- sre
- search for available integrations in cortex xsoar.
- xpanse update incident
- data loss prevention, saas security monitoring, and identity security posture.
- get management logs from xsiam.
- isolate endpoints.
- run playbook
- xdr get script results
- get details for a specific exposed asset.
- update xpanse incident
- search attack surface rules.
- create a new investigation in xsoar.
- xpanse list incidents
- xpanse update attack surface rule
- search owned ip ranges.
- get extra data for a specific xdr incident.
- palo alto networks
- get script execution results from xdr.
- get xdr audit logs
- designs and implements network security architectures and policies.
- detection and response
- get or update a specific incident.
- update attack surface rule
- xpanse list services
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- get xpanse incidents.
- list available playbooks in xsoar.
- update an xpanse incident.
- search xsoar integrations.
- get xql query results from xsiam.
- run script
- soc
- add entry
- compliance team
- search xsiam incidents with filters.
- get investigation
- get xpanse audit logs.
- get xdr audit logs.
- xsoar create investigation
- search integrations
- xsiam start xql query
- threat hunter
- enterprise it
- create xsoar investigations.
- search xdr alerts with filters.
- network operations
- get attack surface rules from xpanse.
- update an xdr incident.
- data protection analyst
- search internet-exposed assets.
- xsoar search integration instances
- update an existing incident in cortex xsoar.
- search xsiam assets
- list xdr incidents.
- tenant operator
- ai runtime security scanning and automated red teaming for ai applications.
- get asset details
- search xsiam incidents.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- mssp operator
- secures ai applications with runtime scanning and vulnerability assessment.
- search exposed assets
- digital experience monitoring, log management, and best practice assessment.
- search services
- unisolate endpoints.
- isolate endpoints from the network.
- iam admin
- xsiam list alerts
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- search xpanse incidents.
- xsiam get xql results
- search integration instances
- list available playbooks in cortex xsoar.
- create a new incident in cortex xsoar.
- get xql query results
- run a playbook on an investigation in xsoar.
- scan endpoints.
- xdr get audit logs
- search xsoar integration instances.
- conducts automated adversarial testing against ai systems and llm applications.
- firewall
- manages service accounts, roles, and access policies for platform api access.
- researches threat actors, malware campaigns, and vulnerability trends.
- xsiam get management logs
- network security engineer
- browser security admin
- search xsiam alerts.
- create investigation
- list xdr incidents with optional filters, pagination, and sorting.
- xdr start xql query
- search xsiam endpoints.
- incident management — list, search, create, and update incidents.
- get xsiam xql query results
- xsoar update incident
- list xdr endpoints with filters.
- get xsiam management logs
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- start xql queries on xsiam.
- add entries to investigations.
- red team operator
- compliance officer
- manages logging infrastructure, integrations, and platform automation.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- incident response
- investigates security incidents, triages alerts, and coordinates response actions.
- get audit management logs from xpanse.
- network architect
- subscription manager
- create incident
- cloud security posture management, compliance monitoring, and workload protection.
- xdr list incidents
- saas security admin
- search xpanse incidents with filters.
- firewall admin
- start xsiam xql query
- list xsiam incidents with optional filters and pagination.
- xsoar search integrations
- xpanse list exposed assets
- manages multi-tenant hierarchies and service group configurations for mssps.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- get xsiam management logs.
- configure datasource
- retrieve a specific incident by id from cortex xsoar.
- list xdr alerts with optional filters, pagination, and sorting.
- xdr isolate endpoints
- search for available integrations in xsoar.
- xpanse list ip ranges
- get incident details from xdr.
- search for integration instances in cortex xsoar.
- soc analyst
- xdr get xql results
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- create a new investigation in cortex xsoar.
- start an xql query on xsiam.
- ai security engineer
- sase
- search attack surface rules
- xdr unisolate endpoints
- start xql query
- xsiam list endpoints
- xsoar run playbook
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- manages multi-tenant security operations at scale for managed service providers.
- list xsiam alerts with optional filters and pagination.
- configure a datasource for xsiam ingestion.
- run xsoar playbooks.
- xsoar list playbooks
- monitors and remediates cloud security misconfigurations and compliance violations.
- cybersecurity
- retrieve a specific investigation by id from xsoar.
- create an incident in xsoar.
- search xsiam alerts
- search xdr incidents with filters.
- start xql queries on xdr.
- run a script on endpoints.
- get script execution results.
- list xsiam endpoints with filters.
- search ip ranges
- update incident
- search for integration instances in xsoar.
- scan endpoints
- retrieve a specific investigation by id from cortex xsoar.
- add an entry to an investigation in xsoar.
- initiate a scan on endpoints.
- xsiam list assets
- sase admin
- platform engineer
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- cloud security engineer
- xdr run script
- unisolate endpoints
- run a playbook on an investigation in cortex xsoar.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- xpanse get audit logs
- search xsiam alerts with filters.
- xdr list endpoints
- xsoar add entry
- list xsiam assets with filters.
- xdr list alerts
- get exposed services from xpanse.
- xdr update incident
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get script results
- run scripts on endpoints.
- search exposed services.
- search xsiam endpoints
- sd wan operator
- search incidents
- get a specific investigation.
- update an attack surface rule.
- search endpoints
- threat intel analyst
- vulnerability manager
- isolate endpoints from the network via xdr.
- incident responder
- network security
- list incidents
- xdr
- security operations
- update an attack surface rule in xpanse.
- initiate a scan on endpoints via xdr.
- search xpanse incidents
- executes containment, eradication, and recovery actions during security incidents.
- soar
- search incidents with filters in cortex xsoar.
- get audit management logs from xdr.
- get incident details
- xsoar get investigation
- list xsiam endpoints with optional filters.
- search xdr endpoints.
- isolate endpoints
- add an entry to an investigation in cortex xsoar.
- designs sase and sd-wan network architectures for secure remote access.
- manages enterprise browser policies and secure browsing configurations.
- xsoar search incidents
- list and manage xsoar playbooks.
- xsiam configure datasource
- xsoar get incident
- search xdr alerts
- investigates dlp incidents and manages sensitive data protection policies.
- monitors network health, performance, and digital experience metrics.
- xpanse get asset details
- list xdr endpoints with optional filters, pagination, and sorting.
- list playbooks
- get xpanse audit logs
- unisolate endpoints and restore network connectivity.
- firewall policy management, network objects, and cloud-native firewall configuration.
- search xsiam incidents
- xsiam list incidents
slug: incident-response
source_filename: incident-response.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Palo Alto Networks Incident Response\n  description: Unified incident response capability for SOC analysts — investigate incidents, triage alerts, manage endpoints,\n    execute response playbooks, and assess attack surface exposure across Cortex XDR, XSIAM, XSOAR, and Xpanse.\n  tags:\n  - Palo Alto Networks\n  - Incident Response\n  - SOC\n  - Security Operations\n  - Detection And Response\n  created: '2026-04-16'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CORTEX_XDR_API_KEY_ID: CORTEX_XDR_API_KEY_ID\n    CORTEX_XDR_API_KEY: CORTEX_XDR_API_KEY\n    CORTEX_XDR_FQDN: CORTEX_XDR_FQDN\n    CORTEX_XSIAM_API_KEY_ID: CORTEX_XSIAM_API_KEY_ID\n    CORTEX_XSIAM_API_KEY: CORTEX_XSIAM_API_KEY\n    CORTEX_XSIAM_FQDN: CORTEX_XSIAM_FQDN\n    CORTEX_XSOAR_API_KEY: CORTEX_XSOAR_API_KEY\n    CORTEX_XSOAR_FQDN: CORTEX_XSOAR_FQDN\n    CORTEX_XPANSE_API_KEY_ID: CORTEX_XPANSE_API_KEY_ID\n    CORTEX_XPANSE_API_KEY: CORTEX_XPANSE_API_KEY\n\
  \    CORTEX_XPANSE_FQDN: CORTEX_XPANSE_FQDN\ncapability:\n  consumes:\n  - type: http\n    namespace: cortex-xdr\n    baseUri: https://{fqdn}/public_api/v1\n    description: Palo Alto Networks Cortex XDR API for extended detection and response.\n    authentication:\n      type: apikey\n      key: x-xdr-auth-id\n      value: '{{CORTEX_XDR_API_KEY_ID}}'\n      placement: header\n    resources:\n    - name: incidents\n      path: /incidents\n      description: Incident management operations.\n      operations:\n      - name: get-incidents\n        method: POST\n        description: Get a list of incidents.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: filters\n          in: body\n          type: array\n          required: false\n          description: Array of filter objects.\n        - name: search_from\n          in: body\n         \
  \ type: integer\n          required: false\n          description: Start index for pagination.\n        - name: search_to\n          in: body\n          type: integer\n          required: false\n          description: End index for pagination.\n        - name: sort\n          in: body\n          type: object\n          required: false\n          description: Sort configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: incidents\n          type: array\n          value: $.reply.incidents\n        body:\n          type: json\n          data:\n            request_data:\n              filters: '{{tools.filters}}'\n              search_from: '{{tools.search_from}}'\n              search_to: '{{tools.search_to}}'\n              sort: '{{tools.sort}}'\n      - name: get-incident-extra-data\n        method: POST\n        description: Get extra data for a specific incident.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n        \
  \  type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: incident_id\n          in: body\n          type: string\n          required: true\n          description: The incident ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: incident\n          type: object\n          value: $.reply\n        body:\n          type: json\n          data:\n            request_data:\n              incident_id: '{{tools.incident_id}}'\n      - name: update-incident\n        method: POST\n        description: Update an incident.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: incident_id\n          in: body\n          type: string\n          required: true\n          description: The incident ID.\n        - name: update_data\n          in: body\n          type: object\n\
  \          required: true\n          description: Data to update on the incident.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.reply\n        body:\n          type: json\n          data:\n            request_data:\n              incident_id: '{{tools.incident_id}}'\n              update_data: '{{tools.update_data}}'\n    - name: alerts\n      path: /alerts\n      description: Alert operations.\n      operations:\n      - name: get-alerts\n        method: POST\n        description: Get a list of alerts.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: filters\n          in: body\n          type: array\n          required: false\n          description: Array of filter objects.\n        - name: search_from\n          in: body\n          type: integer\n      \
  \    required: false\n          description: Start index for pagination.\n        - name: search_to\n          in: body\n          type: integer\n          required: false\n          description: End index for pagination.\n        - name: sort\n          in: body\n          type: object\n          required: false\n          description: Sort configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: alerts\n          type: array\n          value: $.reply.alerts\n        body:\n          type: json\n          data:\n            request_data:\n              filters: '{{tools.filters}}'\n              search_from: '{{tools.search_from}}'\n              search_to: '{{tools.search_to}}'\n              sort: '{{tools.sort}}'\n    - name: endpoints\n      path: /endpoints\n      description: Endpoint operations.\n      operations:\n      - name: get-endpoints\n        method: POST\n        description: Get a list of endpoints.\n        inputParameters:\n       \
  \ - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: filters\n          in: body\n          type: array\n          required: false\n          description: Array of filter objects.\n        - name: search_from\n          in: body\n          type: integer\n          required: false\n          description: Start index for pagination.\n        - name: search_to\n          in: body\n          type: integer\n          required: false\n          description: End index for pagination.\n        - name: sort\n          in: body\n          type: object\n          required: false\n          description: Sort configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: endpoints\n          type: array\n          value: $.reply.endpoints\n        body:\n          type: json\n          data:\n            request_data:\n              filters: '{{tools.filters}}'\n\
  \              search_from: '{{tools.search_from}}'\n              search_to: '{{tools.search_to}}'\n              sort: '{{tools.sort}}'\n      - name: isolate-endpoints\n        method: POST\n        description: Isolate endpoints.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: filters\n          in: body\n          type: array\n          required: true\n          description: Array of filter objects to identify endpoints.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.reply\n        body:\n          type: json\n          data:\n            request_data:\n              filters: '{{tools.filters}}'\n      - name: unisolate-endpoints\n        method: POST\n        description: Unisolate endpoints.\n        inputParameters:\n        - name: x-xdr-api-key\n\
  \          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: filters\n          in: body\n          type: array\n          required: true\n          description: Array of filter objects to identify endpoints.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.reply\n        body:\n          type: json\n          data:\n            request_data:\n              filters: '{{tools.filters}}'\n      - name: scan-endpoints\n        method: POST\n        description: Scan endpoints.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: filters\n          in: body\n          type: array\n          required: true\n          description: Array of filter objects to identify endpoints.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.reply\n        body:\n          type: json\n          data:\n            request_data:\n              filters: '{{tools.filters}}'\n    - name: scripts\n      path: /scripts\n      description: Script execution operations.\n      operations:\n      - name: run-script\n        method: POST\n        description: Run a script on endpoints.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: script_uid\n          in: body\n          type: string\n          required: true\n          description: UID of the script to run.\n        - name: timeout\n          in: body\n          type: integer\n          required: false\n          description: Script execution timeout in seconds.\n        - name: endpoint_ids\n          in: body\n          type: array\n\
  \          required: true\n          description: List of endpoint IDs.\n        - name: parameters\n          in: body\n          type: object\n          required: false\n          description: Script parameters.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.reply\n        body:\n          type: json\n          data:\n            request_data:\n              script_uid: '{{tools.script_uid}}'\n              timeout: '{{tools.timeout}}'\n              endpoint_ids: '{{tools.endpoint_ids}}'\n              parameters: '{{tools.parameters}}'\n      - name: get-script-execution-results\n        method: POST\n        description: Get script execution results.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: action_id\n          in: body\n          type: string\n\
  \          required: true\n          description: The action ID from the script execution.\n        outputRawFormat: json\n        outputParameters:\n        - name: results\n          type: array\n          value: $.reply.results\n        body:\n          type: json\n          data:\n            request_data:\n              action_id: '{{tools.action_id}}'\n    - name: xql\n      path: /xql\n      description: XQL query operations.\n      operations:\n      - name: start-xql-query\n        method: POST\n        description: Start an XQL query.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The XQL query string.\n        - name: timeframe\n          in: body\n          type: object\n          required: false\n          description: Timeframe\
  \ for the query.\n        outputRawFormat: json\n        outputParameters:\n        - name: query_id\n          type: string\n          value: $.reply.query_id\n        body:\n          type: json\n          data:\n            request_data:\n              query: '{{tools.query}}'\n              timeframe: '{{tools.timeframe}}'\n      - name: get-xql-query-results\n        method: POST\n        description: Get XQL query results.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: query_id\n          in: body\n          type: string\n          required: true\n          description: The query ID from a started XQL query.\n        outputRawFormat: json\n        outputParameters:\n        - name: results\n          type: object\n          value: $.reply\n        body:\n          type: json\n          data:\n            request_data:\n       \
  \       query_id: '{{tools.query_id}}'\n    - name: audit\n      path: /audit\n      description: Audit log operations.\n      operations:\n      - name: get-audit-management-logs\n        method: POST\n        description: Get audit management logs.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: filters\n          in: body\n          type: array\n          required: false\n          description: Array of filter objects.\n        - name: search_from\n          in: body\n          type: integer\n          required: false\n          description: Start index for pagination.\n        - name: search_to\n          in: body\n          type: integer\n          required: false\n          description: End index for pagination.\n        - name: sort\n          in: body\n          type: object\n          required: false\n          description: Sort\
  \ configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: logs\n          type: array\n          value: $.reply.data\n        body:\n          type: json\n          data:\n            request_data:\n              filters: '{{tools.filters}}'\n              search_from: '{{tools.search_from}}'\n              search_to: '{{tools.search_to}}'\n              sort: '{{tools.sort}}'\n  - type: http\n    namespace: cortex-xsiam\n    baseUri: https://{fqdn}/public_api/v1\n    description: Palo Alto Networks Cortex XSIAM API for autonomous security operations.\n    authentication:\n      type: apikey\n      key: x-xdr-auth-id\n      value: '{{CORTEX_XSIAM_API_KEY_ID}}'\n      placement: header\n    resources:\n    - name: incidents\n      path: /incidents\n      description: Incident management operations.\n      operations:\n      - name: get-incidents\n        method: POST\n        description: Get a list of incidents.\n        inputParameters:\n        - name:\
  \ x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XSIAM API key for authentication.\n        - name: filters\n          in: body\n          type: array\n          required: false\n          description: Array of filter objects.\n        - name: search_from\n          in: body\n          type: integer\n          required: false\n          description: Start index for pagination.\n        - name: search_to\n          in: body\n          type: integer\n          required: false\n          description: End index for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: incidents\n          type: array\n          value: $.reply.incidents\n        body:\n          type: json\n          data:\n            request_data:\n              filters: '{{tools.filters}}'\n              search_from: '{{tools.search_from}}'\n              search_to: '{{tools.search_to}}'\n    - name: alerts\n      path: /alerts\n\
  \      description: Alert operations.\n      operations:\n      - name: get-alerts\n        method: POST\n        description: Get a list of alerts.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XSIAM API key for authentication.\n        - name: filters\n          in: body\n          type: array\n          required: false\n          description: Array of filter objects.\n        - name: search_from\n          in: body\n          type: integer\n          required: false\n          description: Start index for pagination.\n        - name: search_to\n          in: body\n          type: integer\n          required: false\n          description: End index for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: alerts\n          type: array\n          value: $.reply.alerts\n        body:\n          type: json\n          data:\n            request_data:\n\
  \              filters: '{{tools.filters}}'\n              search_from: '{{tools.search_from}}'\n              search_to: '{{tools.search_to}}'\n    - name: xql\n      path: /xql\n      description: XQL query operations.\n      operations:\n      - name: start-xql-query\n        method: POST\n        description: Start an XQL query.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XSIAM API key for authentication.\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The XQL query string.\n        - name: timeframe\n          in: body\n          type: object\n          required: false\n          description: Timeframe for the query.\n        outputRawFormat: json\n        outputParameters:\n        - name: query_id\n          type: string\n          value: $.reply.query_id\n        body:\n          type: json\n          data:\n\
  \            request_data:\n              query: '{{tools.query}}'\n              timeframe: '{{tools.timeframe}}'\n      - name: get-xql-query-results\n        method: POST\n        description: Get XQL query results.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XSIAM API key for authentication.\n        - name: query_id\n          in: body\n          type: string\n          required: true\n          description: The query ID from a started XQL query.\n        outputRawFormat: json\n        outputParameters:\n        - name: results\n          type: object\n          value: $.reply\n        body:\n          type: json\n          data:\n            request_data:\n              query_id: '{{tools.query_id}}'\n    - name: assets\n      path: /assets\n      description: Asset management operations.\n      operations:\n      - name: list-assets\n        method: POST\n        description:\
  \ List assets.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XSIAM API key for authentication.\n        - name: filters\n          in: body\n          type: array\n          required: false\n          description: Array of filter objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: assets\n          type: array\n          value: $.reply.assets\n        body:\n          type: json\n          data:\n            request_data:\n              filters: '{{tools.filters}}'\n    - name: endpoints\n      path: /endpoints\n      description: Endpoint operations.\n      operations:\n      - name: get-endpoints\n        method: POST\n        description: Get a list of endpoints.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XSIAM API key for authentication.\n\
  \        - name: filters\n          in: body\n          type: array\n          required: false\n          description: Array of filter objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: endpoints\n          type: array\n          value: $.reply.endpoints\n        body:\n          type: json\n          data:\n            request_data:\n              filters: '{{tools.filters}}'\n    - name: audits\n      path: /audits/management_logs\n      description: Management log operations.\n      operations:\n      - name: get-management-logs\n        method: POST\n        description: Get management logs.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XSIAM API key for authentication.\n        - name: filters\n          in: body\n          type: array\n          required: false\n          description: Array of filter objects.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: logs\n          type: array\n          value: $.reply.data\n        body:\n          type: json\n          data:\n            request_data:\n              filters: '{{tools.filters}}'\n    - name: ingestion\n      path: /ingestion\n      description: Data ingestion and datasource operations.\n      operations:\n      - name: configure-datasource\n        method: POST\n        description: Configure a datasource for ingestion.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XSIAM API key for authentication.\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: Name of the datasource.\n        - name: type\n          in: body\n          type: string\n          required: true\n          description: Type of the datasource.\n        - name: config\n          in: body\n          type:\
  \ object\n          required: true\n          description: Datasource configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.reply\n        body:\n          type: json\n          data:\n            request_data:\n              name: '{{tools.name}}'\n              type: '{{tools.type}}'\n              config: '{{tools.config}}'\n  - type: http\n    namespace: cortex-xsoar-api\n    baseUri: https://{fqdn}\n    description: Cortex XSOAR API for incident management, investigations, playbooks, and integrations.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{CORTEX_XSOAR_API_KEY}}'\n    resources:\n    - name: incidents\n      path: /incident\n      description: Manage XSOAR incidents.\n      operations:\n      - name: create-incident\n        method: POST\n        description: Create a new incident in Cortex XSOAR.\n        inputParameters:\n       \
  \ - name: name\n          in: body\n          type: string\n          required: true\n          description: Name of the incident.\n        - name: type\n          in: body\n          type: string\n          required: true\n          description: Type of the incident.\n        - name: severity\n          in: body\n          type: integer\n          required: false\n          description: Severity level of the incident.\n        - name: details\n          in: body\n          type: string\n          required: false\n          description: Details of the incident.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n            severity: '{{tools.severity}}'\n            details: '{{tools.details}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-incident\n        method: GET\n        description: Retrieve a specific incident\
  \ by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The incident ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: incidents-search\n      path: /incidents/search\n      description: Search for incidents.\n      operations:\n      - name: search-incidents\n        method: POST\n        description: Search incidents with filters.\n        inputParameters:\n        - name: filter\n          in: body\n          type: object\n          required: false\n          description: Filter criteria for the search.\n        - name: page\n          in: body\n          type: integer\n          required: false\n          description: Page number for pagination.\n        - name: size\n          in: body\n          type: integer\n          required: false\n          description: Number of results per page.\n       \
  \ body:\n          type: json\n          data:\n            filter: '{{tools.filter}}'\n            page: '{{tools.page}}'\n            size: '{{tools.size}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: incident-update\n      path: /incident/update\n      description: Update an existing incident.\n      operations:\n      - name: update-incident\n        method: POST\n        description: Update an incident with new data.\n        inputParameters:\n        - name: id\n          in: body\n          type: string\n          required: true\n          description: The incident ID to update.\n        - name: update_data\n          in: body\n          type: object\n          required: true\n          description: Data to update on the incident.\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n            update_data: '{{tools.update_data}}'\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entries\n      path: /entry\n      description: Manage investigation entries.\n      operations:\n      - name: add-entry\n        method: POST\n        description: Add an entry to an investigation.\n        inputParameters:\n        - name: investigationId\n          in: body\n          type: string\n          required: true\n          description: The investigation ID to add the entry to.\n        - name: data\n          in: body\n          type: string\n          required: true\n          description: The entry data content.\n        - name: markdown\n          in: body\n          type: boolean\n          required: false\n          description: Whether the data is markdown formatted.\n        body:\n          type: json\n          data:\n            investigationId: '{{tools.investigationId}}'\n            data: '{{tools.data}}'\n            markdown: '{{tools.markdown}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: investigations\n      path: /investigations\n      description: Manage investigations.\n      operations:\n      - name: get-investigation\n        method: GET\n        description: Retrieve a specific investigation by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The investigation ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: investigation-add\n      path: /investigation/add\n      description: Create new investigations.\n      operations:\n      - name: create-investigation\n        method: POST\n        description: Create a new investigation.\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required:\
  \ true\n          description: Name of the investigation.\n        - name: type\n          in: body\n          type: string\n          required: false\n          description: Type of the investigation.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: playbooks\n      path: /playbook\n      description: Manage playbooks.\n      operations:\n      - name: list-playbooks\n        method: GET\n        description: List available playbooks.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination.\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: playbook-run\n      path: /playbook/run\n      description: Run playbooks.\n      operations:\n      - name: run-playbook\n        method: POST\n        description: Run a playbook on an investigation.\n        inputParameters:\n        - name: playbookId\n          in: body\n          type: string\n          required: true\n          description: The playbook ID to run.\n        - name: investigationId\n          in: body\n          type: string\n          required: true\n          description: The investigation ID to run the playbook on.\n        body:\n          type: json\n          data:\n            playbookId: '{{tools.playbookId}}'\n            investigationId: '{{tools.investigationId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrations\n      path: /integration/search\n\
  \      description: Search integrations.\n      operations:\n      - name: search-integrations\n        method: GET\n        description: Search for available integrations.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search query string.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integration-instances\n      path: /settings/integration/search\n      description: Search integration instances.\n      operations:\n      - name: search-integration-instances\n        method: POST\n        description: Search for integration instances.\n        inputParameters:\n        - name: filter\n          in: body\n          type: object\n          required: false\n          description: Filter criteria for the search.\n        body:\n          type: json\n          data:\n            filter: '{{tools.filter}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cortex-xpanse\n    baseUri: https://{fqdn}/public_api/v1\n    description: Palo Alto Networks Cortex Xpanse API for attack surface management.\n    authentication:\n      type: apikey\n      key: x-xdr-auth-id\n      value: '{{CORTEX_XDR_API_KEY_ID}}'\n      placement: header\n    resources:\n    - name: assets\n      path: /assets\n      description: Asset exposure operations.\n      operations:\n      - name: get-assets-internet-exposure\n        method: POST\n        description: Get assets with internet exposure.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: filters\n          in: body\n          type: array\n          required: false\n          description: Array of filter\
  \ objects.\n        - name: search_from\n          in: body\n          type: integer\n          required: false\n          description: Start index for pagination.\n        - name: search_to\n          in: body\n          type: integer\n          required: false\n          description: End index for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: assets\n          type: array\n          value: $.reply.assets\n        body:\n          type: json\n          data:\n            request_data:\n              filters: '{{tools.filters}}'\n              search_from: '{{tools.search_from}}'\n              search_to: '{{tools.search_to}}'\n      - name: get-asset-internet-exposure\n        method: POST\n        description: Get internet exposure details for specific assets.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n\
  \        - name: asm_id_list\n          in: body\n          type: array\n          required: true\n          description: List of ASM IDs to query.\n        outputRawFormat: json\n        outputParameters:\n        - name: assets\n          type: array\n          value: $.reply.assets\n        body:\n          type: json\n          data:\n            request_data:\n              asm_id_list: '{{tools.asm_id_list}}'\n    - name: incident-management\n      path: /incident_management\n      description: Incident management operations.\n      operations:\n      - name: get-incidents\n        method: POST\n        description: Get Xpanse incidents.\n        inputParameters:\n        - name: x-xdr-api-key\n          in: header\n          type: string\n          required: true\n          description: XDR API key for authentication.\n        - name: fil\n\n# --- truncated at 32 KB (96 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/incident-response.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/incident-response.yaml
tags:
- Palo Alto Networks
- Incident Response
- SOC
- Security Operations
- Detection And Response
tools:
- description: List XDR incidents with optional filters, pagination, and sorting.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xdr-list-incidents
- description: Get extra data for a specific XDR incident.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xdr-get-incident-details
- description: Update an XDR incident.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: xdr-update-incident
- description: List XSIAM incidents with optional filters and pagination.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xsiam-list-incidents
- description: Create a new incident in Cortex XSOAR.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: xsoar-create-incident
- description: Search incidents with filters in Cortex XSOAR.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xsoar-search-incidents
- description: Retrieve a specific incident by ID from Cortex XSOAR.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xsoar-get-incident
- description: Update an existing incident in Cortex XSOAR.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: xsoar-update-incident
- description: List XDR alerts with optional filters, pagination, and sorting.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xdr-list-alerts
- description: List XSIAM alerts with optional filters and pagination.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xsiam-list-alerts
- description: List XDR endpoints with optional filters, pagination, and sorting.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xdr-list-endpoints
- description: Isolate endpoints from the network via XDR.
  hints:
    destructive: true
    idempotent: false
    openWorld: true
    readOnly: false
  name: xdr-isolate-endpoints
- description: Unisolate endpoints and restore network connectivity via XDR.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: xdr-unisolate-endpoints
- description: Initiate a scan on endpoints via XDR.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: xdr-scan-endpoints
- description: List XSIAM endpoints with optional filters.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xsiam-list-endpoints
- description: Run a script on endpoints via XDR.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: xdr-run-script
- description: Get script execution results from XDR.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xdr-get-script-results
- description: Start an XQL query on XDR.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: xdr-start-xql-query
- description: Get XQL query results from XDR.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xdr-get-xql-results
- description: Start an XQL query on XSIAM.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: xsiam-start-xql-query
- description: Get XQL query results from XSIAM.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xsiam-get-xql-results
- description: Get internet-exposed assets from Xpanse.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xpanse-list-exposed-assets
- description: Get internet exposure details for specific assets from Xpanse.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xpanse-get-asset-details
- description: Get Xpanse incidents.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xpanse-list-incidents
- description: Update an Xpanse incident.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: xpanse-update-incident
- description: Get attack surface rules from Xpanse.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xpanse-list-attack-surface-rules
- description: Update an attack surface rule in Xpanse.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: xpanse-update-attack-surface-rule
- description: Get exposed services from Xpanse.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xpanse-list-services
- description: Get owned IP ranges from Xpanse.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xpanse-list-ip-ranges
- description: Create a new investigation in Cortex XSOAR.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: xsoar-create-investigation
- description: Retrieve a specific investigation by ID from Cortex XSOAR.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xsoar-get-investigation
- description: Add an entry to an investigation in Cortex XSOAR.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: xsoar-add-entry
- description: List available playbooks in Cortex XSOAR.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xsoar-list-playbooks
- description: Run a playbook on an investigation in Cortex XSOAR.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: xsoar-run-playbook
- description: Search for available integrations in Cortex XSOAR.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xsoar-search-integrations
- description: Search for integration instances in Cortex XSOAR.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xsoar-search-integration-instances
- description: List XSIAM assets with optional filters.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xsiam-list-assets
- description: Configure a datasource for XSIAM ingestion.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: xsiam-configure-datasource
- description: Get audit management logs from XDR.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xdr-get-audit-logs
- description: Get audit management logs from Xpanse.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xpanse-get-audit-logs
- description: Get management logs from XSIAM.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: xsiam-get-management-logs
---
