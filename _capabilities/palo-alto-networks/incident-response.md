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
- xsoar create incident
- start xql queries on xdr.
- start xsiam xql query
- detection and response
- update attack surface rule
- palo alto networks
- search xsiam alerts with filters.
- get xql query results from xsiam.
- update an xpanse incident.
- get investigation
- xsiam list endpoints
- xdr list endpoints
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- incident response
- search exposed services.
- get owned ip ranges from xpanse.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- red team operator
- xdr scan endpoints
- tenant operator
- xsiam start xql query
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- xsiam configure datasource
- xdr list alerts
- xsiam list alerts
- initiate a scan on endpoints via xdr.
- get xdr audit logs
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- xpanse list services
- xsoar create investigation
- get xpanse audit logs
- search xdr incidents with filters.
- search services
- researches threat actors, malware campaigns, and vulnerability trends.
- saas security admin
- get extra data for a specific xdr incident.
- get xdr audit logs.
- start an xql query on xsiam.
- unisolate endpoints
- create investigation
- get xpanse incidents.
- compliance team
- enterprise browser policy management and secure browsing.
- run a script on endpoints.
- create a new incident in cortex xsoar.
- unisolate endpoints and restore network connectivity.
- search xpanse incidents with filters.
- xsoar add entry
- sd wan operator
- sase
- xsoar list playbooks
- xdr get script results
- xdr run script
- search xdr endpoints.
- get xpanse audit logs.
- get script execution results from xdr.
- isolate endpoints from the network.
- isolate endpoints.
- isolate endpoints from the network via xdr.
- xdr get xql results
- get xql query results from xdr.
- threat hunter
- get incident details from xdr.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- search xsoar integration instances.
- list xsiam assets with optional filters.
- run xsoar playbooks.
- data protection analyst
- proactively searches for threats and iocs across telemetry data.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- get xsiam management logs.
- investigates security incidents, triages alerts, and coordinates response actions.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- list xdr endpoints with filters.
- security operations
- manages enterprise browser policies and secure browsing configurations.
- update an xdr incident.
- incident responder
- cloud security posture management, compliance monitoring, and workload protection.
- run playbook
- list xdr incidents with optional filters, pagination, and sorting.
- get script execution results.
- ai security engineer
- isolate endpoints
- add entries to investigations.
- manage enterprise browser policies, user sessions, and deployments.
- list playbooks
- get audit management logs from xdr.
- compliance officer
- designs and implements network security architectures and policies.
- run script
- list xsiam endpoints with filters.
- start xql queries on xsiam.
- sase admin
- network operations
- xsoar update incident
- xsiam get management logs
- search internet-exposed assets.
- configure datasource
- malware researcher
- monitors and remediates cloud security misconfigurations and compliance violations.
- retrieve a specific investigation by id from xsoar.
- xpanse get audit logs
- search exposed assets
- investigates dlp incidents and manages sensitive data protection policies.
- network security
- search xsiam endpoints.
- scan endpoints
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- xpanse get asset details
- xsoar search integrations
- search xsiam alerts
- list available playbooks in xsoar.
- subscription manager
- list incidents
- threat intelligence
- manages multi-tenant security operations at scale for managed service providers.
- configure xsiam datasources.
- search xsiam incidents with filters.
- get asset details
- data loss prevention, saas security monitoring, and identity security posture.
- search xdr alerts
- get or update a specific incident.
- search for integration instances in xsoar.
- update an attack surface rule.
- xdr start xql query
- create a new investigation in xsoar.
- unisolate endpoints and restore network connectivity via xdr.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- initiate a scan on endpoints.
- xsoar get investigation
- search xsoar integrations.
- xdr unisolate endpoints
- configure a datasource for xsiam ingestion.
- unisolate endpoints.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- get internet-exposed assets from xpanse.
- search xsiam alerts.
- designs sase and sd-wan network architectures for secure remote access.
- search attack surface rules.
- search xsiam assets.
- list available playbooks in cortex xsoar.
- conducts automated adversarial testing against ai systems and llm applications.
- search for available integrations in xsoar.
- get xql query results
- analyzes suspicious files and samples for malware characteristics.
- xdr
- network architect
- get management logs from xsiam.
- list xsiam assets with filters.
- cybersecurity
- search xdr alerts.
- secures ai applications with runtime scanning and vulnerability assessment.
- retrieve a specific investigation by id from cortex xsoar.
- sre
- add an entry to an investigation in xsoar.
- firewall admin
- soc analyst
- get script results
- xpanse update attack surface rule
- get xsiam xql query results
- vulnerability manager
- network security engineer
- get exposed services from xpanse.
- mssp operator
- list xdr incidents.
- manages service accounts, roles, and access policies for platform api access.
- list and manage xsoar playbooks.
- create incident
- update incident
- executes containment, eradication, and recovery actions during security incidents.
- monitors network health, performance, and digital experience metrics.
- add entry
- xsoar search incidents
- firewall
- search incidents
- list xsiam incidents with optional filters and pagination.
- retrieve a specific incident by id from cortex xsoar.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- get incident details
- search xsiam assets
- list xdr alerts with optional filters, pagination, and sorting.
- xdr get audit logs
- soc
- enterprise it
- ai runtime security scanning and automated red teaming for ai applications.
- get attack surface rules from xpanse.
- search xsiam incidents
- xpanse list incidents
- soar
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- start xql query
- search xsiam incidents.
- xsoar search integration instances
- get a specific investigation.
- list xsiam endpoints with optional filters.
- search for available integrations in cortex xsoar.
- search xdr alerts with filters.
- search xsiam endpoints
- identity and access management, tenant hierarchies, and subscription management.
- start an xql query on xdr.
- search integrations
- list xdr endpoints with optional filters, pagination, and sorting.
- xsiam list incidents
- update an existing incident in cortex xsoar.
- xsiam get xql results
- add an entry to an investigation in cortex xsoar.
- manages logging infrastructure, integrations, and platform automation.
- list xsiam alerts with optional filters and pagination.
- iam admin
- search incidents with filters.
- update an attack surface rule in xpanse.
- xpanse list attack surface rules
- scan endpoints.
- xpanse list exposed assets
- manages multi-tenant hierarchies and service group configurations for mssps.
- firewall policy management, network objects, and cloud-native firewall configuration.
- search attack surface rules
- search endpoints
- get details for a specific exposed asset.
- xsoar run playbook
- run a playbook on an investigation in xsoar.
- xdr update incident
- threat intel analyst
- xpanse update incident
- xpanse list ip ranges
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- search ip ranges
- xdr list incidents
- create xsoar investigations.
- xsiam list assets
- get audit management logs from xpanse.
- search xpanse incidents
- create a new investigation in cortex xsoar.
- update xpanse incident
- search integration instances
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get internet exposure details for specific assets from xpanse.
- search incidents with filters in cortex xsoar.
- run a playbook on an investigation in cortex xsoar.
- browser security admin
- digital experience monitoring, log management, and best practice assessment.
- search owned ip ranges.
- search for integration instances in cortex xsoar.
- run a script on endpoints via xdr.
- create an incident in xsoar.
- search xpanse incidents.
- get xsiam management logs
- xsoar get incident
- cloud security
- run scripts on endpoints.
- xdr isolate endpoints
- cloud security engineer
- xdr get incident details
- platform engineer
- incident management — list, search, create, and update incidents.
slug: incident-response
source_filename: incident-response.yaml
source_heading: Capability Spec
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
  \                  in: body\n                  type: string\n                  required: true\n    \n\n# --- truncated at 32 KB (76 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/incident-response.yaml\n"
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
