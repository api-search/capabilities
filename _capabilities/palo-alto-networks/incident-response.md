---
categories:
- incident-management
consumed_apis:
- cortex-xdr
- cortex-xsiam
- cortex-xsoar
- cortex-xpanse
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
- network security engineer
- configure a datasource for xsiam ingestion.
- add an entry to an investigation in cortex xsoar.
- xpanse get audit logs
- start an xql query on xdr.
- create incident
- search services
- retrieve a specific incident by id from cortex xsoar.
- search internet-exposed assets.
- xsiam get management logs
- cloud security
- list xsiam alerts with optional filters and pagination.
- get management logs from xsiam.
- search owned ip ranges.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- get exposed services from xpanse.
- sase
- run a script on endpoints via xdr.
- get audit management logs from xdr.
- update an attack surface rule.
- get audit management logs from xpanse.
- get xsiam management logs.
- xdr scan endpoints
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- designs and implements network security architectures and policies.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- xpanse update attack surface rule
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- xpanse list exposed assets
- get owned ip ranges from xpanse.
- run a playbook on an investigation in cortex xsoar.
- soc analyst
- sre
- search xdr alerts with filters.
- network security
- unisolate endpoints and restore network connectivity via xdr.
- data loss prevention, saas security monitoring, and identity security posture.
- xpanse list ip ranges
- xsiam list incidents
- get script execution results.
- xdr get incident details
- xdr update incident
- xsiam configure datasource
- xdr unisolate endpoints
- xdr get xql results
- search for available integrations in cortex xsoar.
- xsoar list playbooks
- isolate endpoints from the network.
- search xpanse incidents with filters.
- run a playbook on an investigation in xsoar.
- run script
- xsoar create incident
- manages enterprise browser policies and secure browsing configurations.
- xsiam list endpoints
- manages service accounts, roles, and access policies for platform api access.
- researches threat actors, malware campaigns, and vulnerability trends.
- create a new investigation in xsoar.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- incident response
- retrieve a specific investigation by id from xsoar.
- cybersecurity
- get a specific investigation.
- manages multi-tenant security operations at scale for managed service providers.
- xpanse list incidents
- xpanse get asset details
- search xsiam assets.
- search incidents with filters in cortex xsoar.
- xsoar create investigation
- conducts automated adversarial testing against ai systems and llm applications.
- xsoar add entry
- proactively searches for threats and iocs across telemetry data.
- update an xpanse incident.
- get xpanse audit logs.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- unisolate endpoints
- search xsiam incidents with filters.
- search xsiam endpoints
- get xdr audit logs
- retrieve a specific investigation by id from cortex xsoar.
- list xsiam assets with filters.
- list available playbooks in cortex xsoar.
- scan endpoints.
- sd wan operator
- start xql queries on xsiam.
- monitors and remediates cloud security misconfigurations and compliance violations.
- search xpanse incidents.
- update an existing incident in cortex xsoar.
- search exposed assets
- get or update a specific incident.
- search xsiam incidents.
- update xpanse incident
- list xsiam incidents with optional filters and pagination.
- compliance officer
- start xql queries on xdr.
- network architect
- search for integration instances in cortex xsoar.
- search xsoar integrations.
- incident responder
- xdr
- search xsiam alerts
- xsiam get xql results
- start xsiam xql query
- soc
- search xsiam incidents
- add an entry to an investigation in xsoar.
- search xsiam alerts with filters.
- create a new investigation in cortex xsoar.
- list xsiam endpoints with filters.
- xpanse list services
- investigates security incidents, triages alerts, and coordinates response actions.
- threat intel analyst
- isolate endpoints.
- start xql query
- get xql query results from xsiam.
- list xsiam endpoints with optional filters.
- analyzes suspicious files and samples for malware characteristics.
- ai runtime security scanning and automated red teaming for ai applications.
- xdr get script results
- xdr start xql query
- search attack surface rules.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- search integration instances
- configure xsiam datasources.
- investigates dlp incidents and manages sensitive data protection policies.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- list xdr incidents.
- get attack surface rules from xpanse.
- list xdr incidents with optional filters, pagination, and sorting.
- scan endpoints
- isolate endpoints
- xsoar search incidents
- xsiam start xql query
- malware researcher
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- get xql query results from xdr.
- cloud security engineer
- incident management — list, search, create, and update incidents.
- secures ai applications with runtime scanning and vulnerability assessment.
- cloud security posture management, compliance monitoring, and workload protection.
- threat intelligence
- start an xql query on xsiam.
- iam admin
- initiate a scan on endpoints.
- create investigation
- saas security admin
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- configure datasource
- manage enterprise browser policies, user sessions, and deployments.
- search xdr endpoints.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- unisolate endpoints and restore network connectivity.
- xsiam list assets
- unisolate endpoints.
- add entry
- list and manage xsoar playbooks.
- get extra data for a specific xdr incident.
- search xsiam assets
- xsoar get incident
- xdr isolate endpoints
- xdr get audit logs
- tenant operator
- get xql query results
- get incident details
- get details for a specific exposed asset.
- xpanse list attack surface rules
- get investigation
- enterprise it
- xpanse update incident
- monitors network health, performance, and digital experience metrics.
- search endpoints
- run scripts on endpoints.
- update incident
- update attack surface rule
- isolate endpoints from the network via xdr.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- xsoar search integrations
- list xdr alerts with optional filters, pagination, and sorting.
- update an xdr incident.
- update an attack surface rule in xpanse.
- run xsoar playbooks.
- manages multi-tenant hierarchies and service group configurations for mssps.
- identity and access management, tenant hierarchies, and subscription management.
- get internet exposure details for specific assets from xpanse.
- search attack surface rules
- ai security engineer
- search ip ranges
- palo alto networks
- search xsoar integration instances.
- list xsiam assets with optional filters.
- vulnerability manager
- subscription manager
- browser security admin
- get xsiam xql query results
- get script results
- get asset details
- firewall policy management, network objects, and cloud-native firewall configuration.
- run a script on endpoints.
- list incidents
- list xdr endpoints with optional filters, pagination, and sorting.
- firewall admin
- get xsiam management logs
- create an incident in xsoar.
- run playbook
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- search incidents
- search xdr alerts.
- search for available integrations in xsoar.
- security operations
- network operations
- designs sase and sd-wan network architectures for secure remote access.
- search incidents with filters.
- xsoar run playbook
- search xsiam endpoints.
- xdr list alerts
- get incident details from xdr.
- search xsiam alerts.
- get script execution results from xdr.
- data protection analyst
- search xdr alerts
- list playbooks
- digital experience monitoring, log management, and best practice assessment.
- get internet-exposed assets from xpanse.
- list xdr endpoints with filters.
- threat hunter
- add entries to investigations.
- get xdr audit logs.
- xdr list incidents
- xdr list endpoints
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- search integrations
- search for integration instances in xsoar.
- sase admin
- soar
- xsoar get investigation
- red team operator
- create xsoar investigations.
- xsiam list alerts
- search xpanse incidents
- detection and response
- platform engineer
- search xdr incidents with filters.
- xsoar update incident
- xsoar search integration instances
- manages logging infrastructure, integrations, and platform automation.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- xdr run script
- create a new incident in cortex xsoar.
- firewall
- initiate a scan on endpoints via xdr.
- executes containment, eradication, and recovery actions during security incidents.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- enterprise browser policy management and secure browsing.
- get xpanse incidents.
- get xpanse audit logs
- search exposed services.
- compliance team
- list available playbooks in xsoar.
- mssp operator
slug: incident-response
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Palo Alto Networks Incident Response\"\n  description: \"Unified incident response capability for SOC analysts — investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface exposure across Cortex XDR, XSIAM, XSOAR, and Xpanse.\"\n  tags:\n    - Palo Alto Networks\n    - Incident Response\n    - SOC\n    - Security Operations\n    - Detection And Response\n  created: \"2026-04-16\"\n  modified: \"2026-04-16\"\n\nbinds:\n  - namespace: env\n    keys:\n      CORTEX_XDR_API_KEY_ID: CORTEX_XDR_API_KEY_ID\n      CORTEX_XDR_API_KEY: CORTEX_XDR_API_KEY\n      CORTEX_XDR_FQDN: CORTEX_XDR_FQDN\n      CORTEX_XSIAM_API_KEY_ID: CORTEX_XSIAM_API_KEY_ID\n      CORTEX_XSIAM_API_KEY: CORTEX_XSIAM_API_KEY\n      CORTEX_XSIAM_FQDN: CORTEX_XSIAM_FQDN\n      CORTEX_XSOAR_API_KEY: CORTEX_XSOAR_API_KEY\n      CORTEX_XSOAR_FQDN: CORTEX_XSOAR_FQDN\n      CORTEX_XPANSE_API_KEY_ID: CORTEX_XPANSE_API_KEY_ID\n\
  \      CORTEX_XPANSE_API_KEY: CORTEX_XPANSE_API_KEY\n      CORTEX_XPANSE_FQDN: CORTEX_XPANSE_FQDN\n\ncapability:\n  consumes:\n    - import: cortex-xdr\n      location: ./shared/cortex-xdr.yaml\n    - import: cortex-xsiam\n      location: ./shared/cortex-xsiam.yaml\n    - import: cortex-xsoar\n      location: ./shared/cortex-xsoar.yaml\n    - import: cortex-xpanse\n      location: ./shared/cortex-xpanse.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: incident-response-api\n      description: \"Unified REST API for incident response workflows across Cortex XDR, XSIAM, XSOAR, and Xpanse.\"\n      resources:\n\n        # -------------------------------------------------------\n        # /v1/incidents — Incident Management (XDR + XSOAR)\n        # -------------------------------------------------------\n        - path: /v1/incidents\n          name: incidents\n          description: \"Incident management — list, search, create, and update incidents.\"\n          operations:\n\
  \            - method: GET\n              name: list-incidents\n              description: \"List XDR incidents.\"\n              inputParameters:\n                - name: filters\n                  in: query\n                  type: array\n                  required: false\n                  description: \"Array of filter objects.\"\n                - name: search_from\n                  in: query\n                  type: integer\n                  required: false\n                  description: \"Start index for pagination.\"\n                - name: search_to\n                  in: query\n                  type: integer\n                  required: false\n                  description: \"End index for pagination.\"\n                - name: sort\n                  in: query\n                  type: object\n                  required: false\n                  description: \"Sort configuration.\"\n              call: \"cortex-xdr.get-incidents\"\n              with:\n                x-xdr-api-key:\
  \ \"{{CORTEX_XDR_API_KEY}}\"\n                filters: \"rest.filters\"\n                search_from: \"rest.search_from\"\n                search_to: \"rest.search_to\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-incident\n              description: \"Create an incident in XSOAR.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Name of the incident.\"\n                - name: type\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Type of the incident.\"\n                - name: severity\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Severity\
  \ level of the incident.\"\n                - name: details\n                  in: body\n                  type: string\n                  required: false\n                  description: \"Details of the incident.\"\n              call: \"cortex-xsoar-api.create-incident\"\n              with:\n                name: \"rest.name\"\n                type: \"rest.type\"\n                severity: \"rest.severity\"\n                details: \"rest.details\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/incidents/search\n          name: incidents-search\n          description: \"Search incidents with filters.\"\n          operations:\n            - method: POST\n              name: search-incidents\n              description: \"Search XDR incidents with filters.\"\n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: false\n\
  \                  description: \"Array of filter objects.\"\n                - name: search_from\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Start index for pagination.\"\n                - name: search_to\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"End index for pagination.\"\n                - name: sort\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Sort configuration.\"\n              call: \"cortex-xdr.get-incidents\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n                filters: \"rest.filters\"\n                search_from: \"rest.search_from\"\n                search_to: \"rest.search_to\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: array\n\
  \                  mapping: \"$.\"\n\n        - path: /v1/incidents/{incident_id}\n          name: incident-detail\n          description: \"Get or update a specific incident.\"\n          operations:\n            - method: GET\n              name: get-incident-details\n              description: \"Get incident details from XDR.\"\n              inputParameters:\n                - name: incident_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The incident ID.\"\n              call: \"cortex-xdr.get-incident-extra-data\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n                incident_id: \"rest.incident_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-incident\n              description: \"Update an XDR incident.\"\n              inputParameters:\n      \
  \          - name: incident_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The incident ID.\"\n                - name: update_data\n                  in: body\n                  type: object\n                  required: true\n                  description: \"Data to update on the incident.\"\n              call: \"cortex-xdr.update-incident\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n                incident_id: \"rest.incident_id\"\n                update_data: \"rest.update_data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # /v1/xsiam-incidents — XSIAM Incidents\n        # -------------------------------------------------------\n        - path: /v1/xsiam-incidents/search\n          name: xsiam-incidents-search\n          description:\
  \ \"Search XSIAM incidents.\"\n          operations:\n            - method: POST\n              name: search-xsiam-incidents\n              description: \"Search XSIAM incidents with filters.\"\n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: false\n                  description: \"Array of filter objects.\"\n                - name: search_from\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Start index for pagination.\"\n                - name: search_to\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"End index for pagination.\"\n              call: \"cortex-xsiam.get-incidents\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n                filters: \"rest.filters\"\n                search_from:\
  \ \"rest.search_from\"\n                search_to: \"rest.search_to\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # /v1/alerts — Alert Management\n        # -------------------------------------------------------\n        - path: /v1/alerts/search\n          name: alerts-search\n          description: \"Search XDR alerts.\"\n          operations:\n            - method: POST\n              name: search-xdr-alerts\n              description: \"Search XDR alerts with filters.\"\n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: false\n                  description: \"Array of filter objects.\"\n                - name: search_from\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"\
  Start index for pagination.\"\n                - name: search_to\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"End index for pagination.\"\n                - name: sort\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Sort configuration.\"\n              call: \"cortex-xdr.get-alerts\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n                filters: \"rest.filters\"\n                search_from: \"rest.search_from\"\n                search_to: \"rest.search_to\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/xsiam-alerts/search\n          name: xsiam-alerts-search\n          description: \"Search XSIAM alerts.\"\n          operations:\n            - method: POST\n          \
  \    name: search-xsiam-alerts\n              description: \"Search XSIAM alerts with filters.\"\n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: false\n                  description: \"Array of filter objects.\"\n                - name: search_from\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Start index for pagination.\"\n                - name: search_to\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"End index for pagination.\"\n              call: \"cortex-xsiam.get-alerts\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n                filters: \"rest.filters\"\n                search_from: \"rest.search_from\"\n                search_to: \"rest.search_to\"\n              outputParameters:\n\
  \                - type: array\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # /v1/endpoints — Endpoint Management\n        # -------------------------------------------------------\n        - path: /v1/endpoints/search\n          name: endpoints-search\n          description: \"Search XDR endpoints.\"\n          operations:\n            - method: POST\n              name: search-endpoints\n              description: \"List XDR endpoints with filters.\"\n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: false\n                  description: \"Array of filter objects.\"\n                - name: search_from\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Start index for pagination.\"\n                - name: search_to\n                  in:\
  \ body\n                  type: integer\n                  required: false\n                  description: \"End index for pagination.\"\n                - name: sort\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Sort configuration.\"\n              call: \"cortex-xdr.get-endpoints\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n                filters: \"rest.filters\"\n                search_from: \"rest.search_from\"\n                search_to: \"rest.search_to\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/endpoints/isolate\n          name: endpoints-isolate\n          description: \"Isolate endpoints from the network.\"\n          operations:\n            - method: POST\n              name: isolate-endpoints\n              description: \"Isolate endpoints.\"\
  \n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: true\n                  description: \"Array of filter objects to identify endpoints.\"\n              call: \"cortex-xdr.isolate-endpoints\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n                filters: \"rest.filters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/endpoints/unisolate\n          name: endpoints-unisolate\n          description: \"Unisolate endpoints and restore network connectivity.\"\n          operations:\n            - method: POST\n              name: unisolate-endpoints\n              description: \"Unisolate endpoints.\"\n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: true\n              \
  \    description: \"Array of filter objects to identify endpoints.\"\n              call: \"cortex-xdr.unisolate-endpoints\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n                filters: \"rest.filters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/endpoints/scan\n          name: endpoints-scan\n          description: \"Scan endpoints.\"\n          operations:\n            - method: POST\n              name: scan-endpoints\n              description: \"Initiate a scan on endpoints.\"\n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: true\n                  description: \"Array of filter objects to identify endpoints.\"\n              call: \"cortex-xdr.scan-endpoints\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n               \
  \ filters: \"rest.filters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/xsiam-endpoints/search\n          name: xsiam-endpoints-search\n          description: \"Search XSIAM endpoints.\"\n          operations:\n            - method: POST\n              name: search-xsiam-endpoints\n              description: \"List XSIAM endpoints with filters.\"\n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: false\n                  description: \"Array of filter objects.\"\n              call: \"cortex-xsiam.get-endpoints\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n                filters: \"rest.filters\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n     \
  \   # /v1/scripts — Script Execution\n        # -------------------------------------------------------\n        - path: /v1/scripts/run\n          name: scripts-run\n          description: \"Run scripts on endpoints.\"\n          operations:\n            - method: POST\n              name: run-script\n              description: \"Run a script on endpoints.\"\n              inputParameters:\n                - name: script_uid\n                  in: body\n                  type: string\n                  required: true\n                  description: \"UID of the script to run.\"\n                - name: timeout\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Script execution timeout in seconds.\"\n                - name: endpoint_ids\n                  in: body\n                  type: array\n                  required: true\n                  description: \"List of endpoint IDs.\"\n                - name:\
  \ parameters\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Script parameters.\"\n              call: \"cortex-xdr.run-script\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n                script_uid: \"rest.script_uid\"\n                timeout: \"rest.timeout\"\n                endpoint_ids: \"rest.endpoint_ids\"\n                parameters: \"rest.parameters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/scripts/results\n          name: scripts-results\n          description: \"Get script execution results.\"\n          operations:\n            - method: POST\n              name: get-script-results\n              description: \"Get script execution results.\"\n              inputParameters:\n                - name: action_id\n                  in: body\n                  type: string\n    \
  \              required: true\n                  description: \"The action ID from the script execution.\"\n              call: \"cortex-xdr.get-script-execution-results\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n                action_id: \"rest.action_id\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # /v1/queries — XQL Queries (XDR)\n        # -------------------------------------------------------\n        - path: /v1/queries\n          name: xql-queries\n          description: \"Start XQL queries on XDR.\"\n          operations:\n            - method: POST\n              name: start-xql-query\n              description: \"Start an XQL query on XDR.\"\n              inputParameters:\n                - name: query\n                  in: body\n                  type: string\n                  required: true\n     \
  \             description: \"The XQL query string.\"\n                - name: timeframe\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Timeframe for the query.\"\n              call: \"cortex-xdr.start-xql-query\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n                query: \"rest.query\"\n                timeframe: \"rest.timeframe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/queries/results\n          name: xql-query-results\n          description: \"Get XQL query results from XDR.\"\n          operations:\n            - method: POST\n              name: get-xql-query-results\n              description: \"Get XQL query results from XDR.\"\n              inputParameters:\n                - name: query_id\n                  in: body\n                  type: string\n                  required:\
  \ true\n                  description: \"The query ID from a started XQL query.\"\n              call: \"cortex-xdr.get-xql-query-results\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n                query_id: \"rest.query_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # /v1/xsiam-queries — XQL Queries (XSIAM)\n        # -------------------------------------------------------\n        - path: /v1/xsiam-queries\n          name: xsiam-xql-queries\n          description: \"Start XQL queries on XSIAM.\"\n          operations:\n            - method: POST\n              name: start-xsiam-xql-query\n              description: \"Start an XQL query on XSIAM.\"\n              inputParameters:\n                - name: query\n                  in: body\n                  type: string\n                  required: true\n        \
  \          description: \"The XQL query string.\"\n                - name: timeframe\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Timeframe for the query.\"\n              call: \"cortex-xsiam.start-xql-query\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n                query: \"rest.query\"\n                timeframe: \"rest.timeframe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/xsiam-queries/results\n          name: xsiam-xql-query-results\n          description: \"Get XQL query results from XSIAM.\"\n          operations:\n            - method: POST\n              name: get-xsiam-xql-query-results\n              description: \"Get XQL query results from XSIAM.\"\n              inputParameters:\n                - name: query_id\n                  in: body\n                  type: string\n\
  \                  required: true\n                  description: \"The query ID from a started XQL query.\"\n              call: \"cortex-xsiam.get-xql-query-results\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n                query_id: \"rest.query_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # /v1/attack-surface — Attack Surface (Xpanse)\n        # -------------------------------------------------------\n        - path: /v1/attack-surface/assets/search\n          name: attack-surface-assets-search\n          description: \"Search internet-exposed assets.\"\n          operations:\n            - method: POST\n              name: search-exposed-assets\n              description: \"Get internet-exposed assets from Xpanse.\"\n              inputParameters:\n                - name: filters\n                  in: body\n\
  \                  type: array\n                  required: false\n                  description: \"Array of filter objects.\"\n                - name: search_from\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Start index for pagination.\"\n                - name: search_to\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"End index for pagination.\"\n              call: \"cortex-xpanse.get-assets-internet-exposure\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n                filters: \"rest.filters\"\n                search_from: \"rest.search_from\"\n                search_to: \"rest.search_to\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/attack-surface/assets/{asset_id}\n          name: attack-surface-asset-detail\n\
  \          description: \"Get details for a specific exposed asset.\"\n          operations:\n            - method: POST\n              name: get-asset-details\n              description: \"Get internet exposure details for specific assets from Xpanse.\"\n              inputParameters:\n                - name: asm_id_list\n                  in: body\n                  type: array\n                  required: true\n                  description: \"List of ASM IDs to query.\"\n              call: \"cortex-xpanse.get-asset-internet-exposure\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n                asm_id_list: \"rest.asm_id_list\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/attack-surface/incidents/search\n          name: attack-surface-incidents-search\n          description: \"Search Xpanse incidents.\"\n          operations:\n            - method: POST\n           \
  \   name: search-xpanse-incidents\n              description: \"Search Xpanse incidents with filters.\"\n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: false\n                  description: \"Array of filter objects.\"\n                - name: search_from\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Start index for pagination.\"\n                - name: search_to\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"End index for pagination.\"\n              call: \"cortex-xpanse.get-incidents\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n                filters: \"rest.filters\"\n                search_from: \"rest.search_from\"\n                search_to: \"rest.search_to\"\n       \
  \       outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/attack-surface/incidents/{incident_id}\n          name: attack-surface-incident-update\n          description: \"Update an Xpanse incident.\"\n          operations:\n            - method: PUT\n              name: update-xpanse-incident\n              description: \"Update an Xpanse incident.\"\n              inputParameters:\n                - name: incident_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The incident ID.\"\n                - name: update_data\n                  in: body\n                  type: object\n                  required: true\n                  description: \"Data to update on the incident.\"\n              call: \"cortex-xpanse.update-incident\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n                incident_id: \"rest.incident_id\"\
  \n                update_data: \"rest.update_data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/attack-surface/rules/search\n          name: attack-surface-rules-search\n          description: \"Search attack surface rules.\"\n          operations:\n            - method: POST\n              name: search-attack-surface-rules\n              description: \"Get attack surface rules from Xpanse.\"\n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: false\n                  description: \"Array of filter objects.\"\n              call: \"cortex-xpanse.get-attack-surface-rules\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n                filters: \"rest.filters\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path:\
  \ /v1/attack-surface/rules/{rule_id}\n          name: attack-surface-rule-update\n          description: \"Update an attack surface rule.\"\n          operations:\n            - method: PUT\n              name: update-attack-surface-rule\n              description: \"Update an attack surface rule in Xpanse.\"\n              inputParameters:\n                - name: rule_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The rule ID.\"\n                - name: update_data\n                  in: body\n                  type: object\n                  required: true\n                  description: \"Data to update on the rule.\"\n              call: \"cortex-xpanse.update-attack-surface-rule\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n                rule_id: \"rest.rule_id\"\n                update_data: \"rest.update_data\"\n              outputParameters:\n        \
  \        - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/attack-surface/services/search\n          name: attack-surface-services-search\n          description: \"Search exposed services.\"\n          operations:\n            - method: POST\n              name: search-services\n              description: \"Get exposed services from Xpanse.\"\n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: false\n                  description: \"Array of filter objects.\"\n              call: \"cortex-xpanse.get-services\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n                filters: \"rest.filters\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/attack-surface/ip-ranges/search\n          name: attack-surface-ip-ranges-search\n          description: \"Search\
  \ owned IP ranges.\"\n          operations:\n            - method: POST\n              name: search-ip-ranges\n              description: \"Get owned IP ranges from Xpanse.\"\n              inputParameters:\n                - name: search_params\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Search parameters for IP ranges.\"\n              call: \"cortex-xpanse.get-owned-ip-ranges\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n                search_params: \"rest.search_params\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # /v1/investigations — XSOAR Investigations\n        # -------------------------------------------------------\n        - path: /v1/investigations\n          name: investigations\n          description: \"Create XSOAR\
  \ investigations.\"\n          operations:\n            - method: POST\n              name: create-investigation\n              description: \"Create a new investigation in XSOAR.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Name of the investigation.\"\n                - name: type\n                  in: body\n                  type: string\n                  required: false\n                  description: \"Type of the investigation.\"\n              call: \"cortex-xsoar-api.create-investigation\"\n              with:\n                name: \"rest.name\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/investigations/{investigation_id}\n          name: investigation-detail\n          description: \"Get a specific investigation.\"\n\
  \          operations:\n            - method: GET\n              name: get-investigation\n              description: \"Retrieve a specific investigation by ID from XSOAR.\"\n              inputParameters:\n                - name: investigation_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The investigation ID.\"\n              call: \"cortex-xsoar-api.get-investigation\"\n              with:\n                id: \"rest.investigation_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/investigations/entries\n          name: investigation-entries\n          description: \"Add entries to investigations.\"\n          operations:\n            - method: POST\n              name: add-entry\n              description: \"Add an entry to an investigation in XSOAR.\"\n              inputParameters:\n                - name: investigationId\n\
  \                  in: body\n                  type: string\n                  required: true\n                  description: \"The investigation ID to add the entry to.\"\n                - name: data\n                  in: body\n                  type: string\n                  required: true\n                  description: \"The entry data content.\"\n                - name: markdown\n                  in: body\n                  type: boolean\n                  required: false\n                  description: \"Whether the data is markdown formatted.\"\n              call: \"cortex-xsoar-api.add-entry\"\n              with:\n                investigationId: \"rest.investigationId\"\n                data: \"rest.data\"\n                markdown: \"rest.markdown\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # /v1/playbooks — XSOAR Playbooks\n        # -------------------------------------------------------\n\
  \        - path: /v1/playbooks\n          name: playbooks\n          description: \"List and manage XSOAR playbooks.\"\n          operations:\n            - method: GET\n              name: list-playbooks\n              description: \"List available playbooks in XSOAR.\"\n              inputParameters:\n                - name: page\n                  in: query\n                  type: integer\n                  required: false\n                  description: \"Page number for pagination.\"\n                - name: size\n                  in: query\n                  type: integer\n                  required: false\n                  description: \"Number of results per page.\"\n              call: \"cortex-xsoar-api.list-playbooks\"\n              with:\n                page: \"rest.page\"\n                size: \"rest.size\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/playbooks/run\n          name: playbooks-run\n\
  \          description: \"Run XSOAR playbooks.\"\n          operations:\n            - method: POST\n              name: run-playbook\n              description: \"Run a playbook on an investigation in XSOAR.\"\n              inputParameters:\n                - name: playbookId\n                  in: body\n                  type: string\n                  required: true\n                  description: \"The playbook ID to run.\"\n                - name: investigationId\n                  in: body\n                  type: string\n                  required: true\n                  description: \"The investigation ID to run the playbook on.\"\n              call: \"cortex-xsoar-api.run-playbook\"\n              with:\n                playbookId: \"rest.playbookId\"\n                investigationId: \"rest.investigationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n\
  \        # /v1/integrations — XSOAR Integrations\n        # -------------------------------------------------------\n        - path: /v1/integrations\n          name: integrations\n          description: \"Search XSOAR integrations.\"\n          operations:\n            - method: GET\n              name: search-integrations\n              description: \"Search for available integrations in XSOAR.\"\n              inputParameters:\n                - name: query\n                  in: query\n                  type: string\n                  required: false\n                  description: \"Search query string.\"\n              call: \"cortex-xsoar-api.search-integrations\"\n              with:\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/integrations/instances/search\n          name: integration-instances-search\n          description: \"Search XSOAR integration instances.\"\
  \n          operations:\n            - method: POST\n              name: search-integration-instances\n              description: \"Search for integration instances in XSOAR.\"\n              inputParameters:\n                - name: filter\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Filter criteria for the search.\"\n              call: \"cortex-xsoar-api.search-integration-instances\"\n              with:\n                filter: \"rest.filter\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # /v1/xsiam-assets — XSIAM Assets\n        # -------------------------------------------------------\n        - path: /v1/xsiam-assets/search\n          name: xsiam-assets-search\n          description: \"Search XSIAM assets.\"\n          operations:\n            - method: POST\n    \
  \          name: search-xsiam-assets\n              description: \"List XSIAM assets with filters.\"\n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: false\n                  description: \"Array of filter objects.\"\n              call: \"cortex-xsiam.list-assets\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n                filters: \"rest.filters\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # /v1/xsiam-datasources — XSIAM Data Sources\n        # -------------------------------------------------------\n        - path: /v1/xsiam-datasources\n          name: xsiam-datasources\n          description: \"Configure XSIAM datasources.\"\n          operations:\n            - method: POST\n              name: configure-datasource\n\
  \              description: \"Configure a datasource for XSIAM ingestion.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Name of the datasource.\"\n                - name: type\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Type of the datasource.\"\n                - name: config\n                  in: body\n                  type: object\n                  required: true\n                  description: \"Datasource configuration.\"\n              call: \"cortex-xsiam.configure-datasource\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n                name: \"rest.name\"\n                type: \"rest.type\"\n                config: \"rest.config\"\n              outputParameters:\n                - type: object\n             \
  \     mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # /v1/audit-logs — Audit Logs\n        # -------------------------------------------------------\n        - path: /v1/audit-logs/xdr\n          name: audit-logs-xdr\n          description: \"Get XDR audit logs.\"\n          operations:\n            - method: POST\n              name: get-xdr-audit-logs\n              description: \"Get audit management logs from XDR.\"\n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: false\n                  description: \"Array of filter objects.\"\n                - name: search_from\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Start index for pagination.\"\n                - name: search_to\n                  in: body\n                  type: integer\n             \
  \     required: false\n                  description: \"End index for pagination.\"\n                - name: sort\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Sort configuration.\"\n              call: \"cortex-xdr.get-audit-management-logs\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n                filters: \"rest.filters\"\n                search_from: \"rest.search_from\"\n                search_to: \"rest.search_to\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/audit-logs/xpanse\n          name: audit-logs-xpanse\n          description: \"Get Xpanse audit logs.\"\n          operations:\n            - method: POST\n              name: get-xpanse-audit-logs\n              description: \"Get audit management logs from Xpanse.\"\n              inputParameters:\n\
  \                - name: filters\n                  in: body\n                  type: array\n                  required: false\n                  description: \"Array of filter objects.\"\n                - name: search_from\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Start index for pagination.\"\n                - name: search_to\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"End index for pagination.\"\n              call: \"cortex-xpanse.get-audit-management-logs\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n                filters: \"rest.filters\"\n                search_from: \"rest.search_from\"\n                search_to: \"rest.search_to\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/audit-logs/xsiam\n\
  \          name: audit-logs-xsiam\n          description: \"Get XSIAM management logs.\"\n          operations:\n            - method: POST\n              name: get-xsiam-management-logs\n              description: \"Get management logs from XSIAM.\"\n              inputParameters:\n                - name: filters\n                  in: body\n                  type: array\n                  required: false\n                  description: \"Array of filter objects.\"\n              call: \"cortex-xsiam.get-management-logs\"\n              with:\n                x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n                filters: \"rest.filters\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    # =============================================================\n    # MCP Server — AI-assisted incident response\n    # =============================================================\n    - type: mcp\n      port: 9090\n      namespace: incident-response-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted incident response across the Cortex platform.\"\n      tools:\n\n        # ---------------------------------------------------------\n        # Incident Investigation\n        # ---------------------------------------------------------\n        - name: xdr-list-incidents\n          description: \"List XDR incidents with optional filters, pagination, and sorting.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of filter objects.\"\n              required: false\n            - name: search_from\n              type: integer\n              description: \"Start index for pagination.\"\n              required: false\n            - name: search_to\n              type: integer\n              description: \"End index\
  \ for pagination.\"\n              required: false\n            - name: sort\n              type: object\n              description: \"Sort configuration.\"\n              required: false\n          call: \"cortex-xdr.get-incidents\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n            filters: \"tools.filters\"\n            search_from: \"tools.search_from\"\n            search_to: \"tools.search_to\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: xdr-get-incident-details\n          description: \"Get extra data for a specific XDR incident.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: incident_id\n              type: string\n              description: \"The incident ID.\"\n              required: true\n          call: \"\
  cortex-xdr.get-incident-extra-data\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n            incident_id: \"tools.incident_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xdr-update-incident\n          description: \"Update an XDR incident.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: incident_id\n              type: string\n              description: \"The incident ID.\"\n              required: true\n            - name: update_data\n              type: object\n              description: \"Data to update on the incident.\"\n              required: true\n          call: \"cortex-xdr.update-incident\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n            incident_id: \"tools.incident_id\"\n            update_data: \"tools.update_data\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xsiam-list-incidents\n          description: \"List XSIAM incidents with optional filters and pagination.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of filter objects.\"\n              required: false\n            - name: search_from\n              type: integer\n              description: \"Start index for pagination.\"\n              required: false\n            - name: search_to\n              type: integer\n              description: \"End index for pagination.\"\n              required: false\n          call: \"cortex-xsiam.get-incidents\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n            filters: \"tools.filters\"\n         \
  \   search_from: \"tools.search_from\"\n            search_to: \"tools.search_to\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: xsoar-create-incident\n          description: \"Create a new incident in Cortex XSOAR.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the incident.\"\n              required: true\n            - name: type\n              type: string\n              description: \"Type of the incident.\"\n              required: true\n            - name: severity\n              type: integer\n              description: \"Severity level of the incident.\"\n              required: false\n            - name: details\n              type: string\n              description: \"Details of the incident.\"\n         \
  \     required: false\n          call: \"cortex-xsoar-api.create-incident\"\n          with:\n            name: \"tools.name\"\n            type: \"tools.type\"\n            severity: \"tools.severity\"\n            details: \"tools.details\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xsoar-search-incidents\n          description: \"Search incidents with filters in Cortex XSOAR.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filter\n              type: object\n              description: \"Filter criteria for the search.\"\n              required: false\n            - name: page\n              type: integer\n              description: \"Page number for pagination.\"\n              required: false\n            - name: size\n              type: integer\n              description: \"Number\
  \ of results per page.\"\n              required: false\n          call: \"cortex-xsoar-api.search-incidents\"\n          with:\n            filter: \"tools.filter\"\n            page: \"tools.page\"\n            size: \"tools.size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xsoar-get-incident\n          description: \"Retrieve a specific incident by ID from Cortex XSOAR.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              description: \"The incident ID.\"\n              required: true\n          call: \"cortex-xsoar-api.get-incident\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xsoar-update-incident\n          description: \"Update an\
  \ existing incident in Cortex XSOAR.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              description: \"The incident ID to update.\"\n              required: true\n            - name: update_data\n              type: object\n              description: \"Data to update on the incident.\"\n              required: true\n          call: \"cortex-xsoar-api.update-incident\"\n          with:\n            id: \"tools.id\"\n            update_data: \"tools.update_data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # ---------------------------------------------------------\n        # Alert Triage\n        # ---------------------------------------------------------\n        - name: xdr-list-alerts\n          description: \"List XDR alerts with optional filters,\
  \ pagination, and sorting.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of filter objects.\"\n              required: false\n            - name: search_from\n              type: integer\n              description: \"Start index for pagination.\"\n              required: false\n            - name: search_to\n              type: integer\n              description: \"End index for pagination.\"\n              required: false\n            - name: sort\n              type: object\n              description: \"Sort configuration.\"\n              required: false\n          call: \"cortex-xdr.get-alerts\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n            filters: \"tools.filters\"\n            search_from: \"tools.search_from\"\n            search_to:\
  \ \"tools.search_to\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: xsiam-list-alerts\n          description: \"List XSIAM alerts with optional filters and pagination.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of filter objects.\"\n              required: false\n            - name: search_from\n              type: integer\n              description: \"Start index for pagination.\"\n              required: false\n            - name: search_to\n              type: integer\n              description: \"End index for pagination.\"\n              required: false\n          call: \"cortex-xsiam.get-alerts\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n    \
  \        filters: \"tools.filters\"\n            search_from: \"tools.search_from\"\n            search_to: \"tools.search_to\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        # ---------------------------------------------------------\n        # Endpoint Response\n        # ---------------------------------------------------------\n        - name: xdr-list-endpoints\n          description: \"List XDR endpoints with optional filters, pagination, and sorting.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of filter objects.\"\n              required: false\n            - name: search_from\n              type: integer\n              description: \"Start index for pagination.\"\n              required: false\n            - name: search_to\n\
  \              type: integer\n              description: \"End index for pagination.\"\n              required: false\n            - name: sort\n              type: object\n              description: \"Sort configuration.\"\n              required: false\n          call: \"cortex-xdr.get-endpoints\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n            filters: \"tools.filters\"\n            search_from: \"tools.search_from\"\n            search_to: \"tools.search_to\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: xdr-isolate-endpoints\n          description: \"Isolate endpoints from the network via XDR.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of\
  \ filter objects to identify endpoints.\"\n              required: true\n          call: \"cortex-xdr.isolate-endpoints\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n            filters: \"tools.filters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xdr-unisolate-endpoints\n          description: \"Unisolate endpoints and restore network connectivity via XDR.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of filter objects to identify endpoints.\"\n              required: true\n          call: \"cortex-xdr.unisolate-endpoints\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n            filters: \"tools.filters\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n\n        - name: xdr-scan-endpoints\n          description: \"Initiate a scan on endpoints via XDR.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of filter objects to identify endpoints.\"\n              required: true\n          call: \"cortex-xdr.scan-endpoints\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n            filters: \"tools.filters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xsiam-list-endpoints\n          description: \"List XSIAM endpoints with optional filters.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n\
  \            - name: filters\n              type: array\n              description: \"Array of filter objects.\"\n              required: false\n          call: \"cortex-xsiam.get-endpoints\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n            filters: \"tools.filters\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        # ---------------------------------------------------------\n        # Script Execution\n        # ---------------------------------------------------------\n        - name: xdr-run-script\n          description: \"Run a script on endpoints via XDR.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: script_uid\n              type: string\n              description: \"UID of the script to run.\"\n              required: true\n            - name: timeout\n\
  \              type: integer\n              description: \"Script execution timeout in seconds.\"\n              required: false\n            - name: endpoint_ids\n              type: array\n              description: \"List of endpoint IDs.\"\n              required: true\n            - name: parameters\n              type: object\n              description: \"Script parameters.\"\n              required: false\n          call: \"cortex-xdr.run-script\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n            script_uid: \"tools.script_uid\"\n            timeout: \"tools.timeout\"\n            endpoint_ids: \"tools.endpoint_ids\"\n            parameters: \"tools.parameters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xdr-get-script-results\n          description: \"Get script execution results from XDR.\"\n          hints:\n            readOnly: true\n            destructive: false\n          \
  \  idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: action_id\n              type: string\n              description: \"The action ID from the script execution.\"\n              required: true\n          call: \"cortex-xdr.get-script-execution-results\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n            action_id: \"tools.action_id\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        # ---------------------------------------------------------\n        # Threat Hunting (XQL)\n        # ---------------------------------------------------------\n        - name: xdr-start-xql-query\n          description: \"Start an XQL query on XDR.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: query\n              type: string\n         \
  \     description: \"The XQL query string.\"\n              required: true\n            - name: timeframe\n              type: object\n              description: \"Timeframe for the query.\"\n              required: false\n          call: \"cortex-xdr.start-xql-query\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n            query: \"tools.query\"\n            timeframe: \"tools.timeframe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xdr-get-xql-results\n          description: \"Get XQL query results from XDR.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: query_id\n              type: string\n              description: \"The query ID from a started XQL query.\"\n              required: true\n          call: \"cortex-xdr.get-xql-query-results\"\n          with:\n\
  \            x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n            query_id: \"tools.query_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xsiam-start-xql-query\n          description: \"Start an XQL query on XSIAM.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: query\n              type: string\n              description: \"The XQL query string.\"\n              required: true\n            - name: timeframe\n              type: object\n              description: \"Timeframe for the query.\"\n              required: false\n          call: \"cortex-xsiam.start-xql-query\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n            query: \"tools.query\"\n            timeframe: \"tools.timeframe\"\n          outputParameters:\n            - type: object\n \
  \             mapping: \"$.\"\n\n        - name: xsiam-get-xql-results\n          description: \"Get XQL query results from XSIAM.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: query_id\n              type: string\n              description: \"The query ID from a started XQL query.\"\n              required: true\n          call: \"cortex-xsiam.get-xql-query-results\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n            query_id: \"tools.query_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # ---------------------------------------------------------\n        # Attack Surface (Xpanse)\n        # ---------------------------------------------------------\n        - name: xpanse-list-exposed-assets\n          description: \"Get internet-exposed assets from Xpanse.\"\
  \n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of filter objects.\"\n              required: false\n            - name: search_from\n              type: integer\n              description: \"Start index for pagination.\"\n              required: false\n            - name: search_to\n              type: integer\n              description: \"End index for pagination.\"\n              required: false\n          call: \"cortex-xpanse.get-assets-internet-exposure\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n            filters: \"tools.filters\"\n            search_from: \"tools.search_from\"\n            search_to: \"tools.search_to\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: xpanse-get-asset-details\n\
  \          description: \"Get internet exposure details for specific assets from Xpanse.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: asm_id_list\n              type: array\n              description: \"List of ASM IDs to query.\"\n              required: true\n          call: \"cortex-xpanse.get-asset-internet-exposure\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n            asm_id_list: \"tools.asm_id_list\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: xpanse-list-incidents\n          description: \"Get Xpanse incidents.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n         \
  \     description: \"Array of filter objects.\"\n              required: false\n            - name: search_from\n              type: integer\n              description: \"Start index for pagination.\"\n              required: false\n            - name: search_to\n              type: integer\n              description: \"End index for pagination.\"\n              required: false\n          call: \"cortex-xpanse.get-incidents\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n            filters: \"tools.filters\"\n            search_from: \"tools.search_from\"\n            search_to: \"tools.search_to\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: xpanse-update-incident\n          description: \"Update an Xpanse incident.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n           \
  \ - name: incident_id\n              type: string\n              description: \"The incident ID.\"\n              required: true\n            - name: update_data\n              type: object\n              description: \"Data to update on the incident.\"\n              required: true\n          call: \"cortex-xpanse.update-incident\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n            incident_id: \"tools.incident_id\"\n            update_data: \"tools.update_data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xpanse-list-attack-surface-rules\n          description: \"Get attack surface rules from Xpanse.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of filter objects.\"\n        \
  \      required: false\n          call: \"cortex-xpanse.get-attack-surface-rules\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n            filters: \"tools.filters\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: xpanse-update-attack-surface-rule\n          description: \"Update an attack surface rule in Xpanse.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: rule_id\n              type: string\n              description: \"The rule ID.\"\n              required: true\n            - name: update_data\n              type: object\n              description: \"Data to update on the rule.\"\n              required: true\n          call: \"cortex-xpanse.update-attack-surface-rule\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n     \
  \       rule_id: \"tools.rule_id\"\n            update_data: \"tools.update_data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xpanse-list-services\n          description: \"Get exposed services from Xpanse.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of filter objects.\"\n              required: false\n          call: \"cortex-xpanse.get-services\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n            filters: \"tools.filters\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: xpanse-list-ip-ranges\n          description: \"Get owned IP ranges from Xpanse.\"\n          hints:\n            readOnly: true\n            destructive:\
  \ false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: search_params\n              type: object\n              description: \"Search parameters for IP ranges.\"\n              required: false\n          call: \"cortex-xpanse.get-owned-ip-ranges\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n            search_params: \"tools.search_params\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        # ---------------------------------------------------------\n        # Automation (XSOAR)\n        # ---------------------------------------------------------\n        - name: xsoar-create-investigation\n          description: \"Create a new investigation in Cortex XSOAR.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n\
  \              type: string\n              description: \"Name of the investigation.\"\n              required: true\n            - name: type\n              type: string\n              description: \"Type of the investigation.\"\n              required: false\n          call: \"cortex-xsoar-api.create-investigation\"\n          with:\n            name: \"tools.name\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xsoar-get-investigation\n          description: \"Retrieve a specific investigation by ID from Cortex XSOAR.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              description: \"The investigation ID.\"\n              required: true\n          call: \"cortex-xsoar-api.get-investigation\"\n          with:\n \
  \           id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xsoar-add-entry\n          description: \"Add an entry to an investigation in Cortex XSOAR.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: investigationId\n              type: string\n              description: \"The investigation ID to add the entry to.\"\n              required: true\n            - name: data\n              type: string\n              description: \"The entry data content.\"\n              required: true\n            - name: markdown\n              type: boolean\n              description: \"Whether the data is markdown formatted.\"\n              required: false\n          call: \"cortex-xsoar-api.add-entry\"\n          with:\n            investigationId: \"tools.investigationId\"\n         \
  \   data: \"tools.data\"\n            markdown: \"tools.markdown\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xsoar-list-playbooks\n          description: \"List available playbooks in Cortex XSOAR.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: page\n              type: integer\n              description: \"Page number for pagination.\"\n              required: false\n            - name: size\n              type: integer\n              description: \"Number of results per page.\"\n              required: false\n          call: \"cortex-xsoar-api.list-playbooks\"\n          with:\n            page: \"tools.page\"\n            size: \"tools.size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xsoar-run-playbook\n          description:\
  \ \"Run a playbook on an investigation in Cortex XSOAR.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: playbookId\n              type: string\n              description: \"The playbook ID to run.\"\n              required: true\n            - name: investigationId\n              type: string\n              description: \"The investigation ID to run the playbook on.\"\n              required: true\n          call: \"cortex-xsoar-api.run-playbook\"\n          with:\n            playbookId: \"tools.playbookId\"\n            investigationId: \"tools.investigationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xsoar-search-integrations\n          description: \"Search for available integrations in Cortex XSOAR.\"\n          hints:\n            readOnly: true\n            destructive: false\n\
  \            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: query\n              type: string\n              description: \"Search query string.\"\n              required: false\n          call: \"cortex-xsoar-api.search-integrations\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: xsoar-search-integration-instances\n          description: \"Search for integration instances in Cortex XSOAR.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filter\n              type: object\n              description: \"Filter criteria for the search.\"\n              required: false\n          call: \"cortex-xsoar-api.search-integration-instances\"\n          with:\n            filter: \"tools.filter\"\n   \
  \       outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # ---------------------------------------------------------\n        # XSIAM Management\n        # ---------------------------------------------------------\n        - name: xsiam-list-assets\n          description: \"List XSIAM assets with optional filters.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of filter objects.\"\n              required: false\n          call: \"cortex-xsiam.list-assets\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n            filters: \"tools.filters\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: xsiam-configure-datasource\n          description: \"Configure a datasource\
  \ for XSIAM ingestion.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the datasource.\"\n              required: true\n            - name: type\n              type: string\n              description: \"Type of the datasource.\"\n              required: true\n            - name: config\n              type: object\n              description: \"Datasource configuration.\"\n              required: true\n          call: \"cortex-xsiam.configure-datasource\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n            name: \"tools.name\"\n            type: \"tools.type\"\n            config: \"tools.config\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # ---------------------------------------------------------\n\
  \        # Audit\n        # ---------------------------------------------------------\n        - name: xdr-get-audit-logs\n          description: \"Get audit management logs from XDR.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of filter objects.\"\n              required: false\n            - name: search_from\n              type: integer\n              description: \"Start index for pagination.\"\n              required: false\n            - name: search_to\n              type: integer\n              description: \"End index for pagination.\"\n              required: false\n            - name: sort\n              type: object\n              description: \"Sort configuration.\"\n              required: false\n          call: \"cortex-xdr.get-audit-management-logs\"\n      \
  \    with:\n            x-xdr-api-key: \"{{CORTEX_XDR_API_KEY}}\"\n            filters: \"tools.filters\"\n            search_from: \"tools.search_from\"\n            search_to: \"tools.search_to\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: xpanse-get-audit-logs\n          description: \"Get audit management logs from Xpanse.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of filter objects.\"\n              required: false\n            - name: search_from\n              type: integer\n              description: \"Start index for pagination.\"\n              required: false\n            - name: search_to\n              type: integer\n              description: \"End index for pagination.\"\
  \n              required: false\n          call: \"cortex-xpanse.get-audit-management-logs\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XPANSE_API_KEY}}\"\n            filters: \"tools.filters\"\n            search_from: \"tools.search_from\"\n            search_to: \"tools.search_to\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: xsiam-get-management-logs\n          description: \"Get management logs from XSIAM.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: filters\n              type: array\n              description: \"Array of filter objects.\"\n              required: false\n          call: \"cortex-xsiam.get-management-logs\"\n          with:\n            x-xdr-api-key: \"{{CORTEX_XSIAM_API_KEY}}\"\n            filters: \"tools.filters\"\n          outputParameters:\n\
  \            - type: array\n              mapping: \"$.\"\n"
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
