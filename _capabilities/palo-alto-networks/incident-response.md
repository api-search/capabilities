---
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
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- xsoar search incidents
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- isolate endpoints.
- list playbooks
- investigates dlp incidents and manages sensitive data protection policies.
- get a specific investigation.
- xdr
- update xpanse incident
- list xsiam alerts with optional filters and pagination.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- scan endpoints.
- secures ai applications with runtime scanning and vulnerability assessment.
- xsiam get xql results
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- monitors network health, performance, and digital experience metrics.
- analyzes suspicious files and samples for malware characteristics.
- manages enterprise browser policies and secure browsing configurations.
- unisolate endpoints
- run a script on endpoints.
- xsoar search integrations
- firewall policy management, network objects, and cloud-native firewall configuration.
- update an attack surface rule.
- sre
- run xsoar playbooks.
- configure xsiam datasources.
- list xdr endpoints with filters.
- isolate endpoints from the network via xdr.
- list xsiam endpoints with optional filters.
- xpanse list incidents
- xsoar run playbook
- run a script on endpoints via xdr.
- search xpanse incidents with filters.
- update an attack surface rule in xpanse.
- xsiam list alerts
- get attack surface rules from xpanse.
- create incident
- add entries to investigations.
- xsiam list endpoints
- start xql queries on xsiam.
- xpanse list ip ranges
- get internet-exposed assets from xpanse.
- xdr get audit logs
- get or update a specific incident.
- designs sase and sd-wan network architectures for secure remote access.
- search attack surface rules.
- vulnerability manager
- retrieve a specific investigation by id from cortex xsoar.
- get xpanse audit logs
- update an existing incident in cortex xsoar.
- firewall admin
- monitors and remediates cloud security misconfigurations and compliance violations.
- soar
- configure datasource
- xdr get xql results
- search internet-exposed assets.
- get extra data for a specific xdr incident.
- tenant operator
- get incident details
- unisolate endpoints and restore network connectivity.
- list xsiam assets with optional filters.
- soc analyst
- incident management — list, search, create, and update incidents.
- search xdr endpoints.
- manages service accounts, roles, and access policies for platform api access.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- data loss prevention, saas security monitoring, and identity security posture.
- get xdr audit logs
- list available playbooks in xsoar.
- cloud security posture management, compliance monitoring, and workload protection.
- threat intelligence
- detection and response
- get xql query results from xdr.
- search for integration instances in xsoar.
- xdr start xql query
- create a new investigation in xsoar.
- xdr list endpoints
- create xsoar investigations.
- ai security engineer
- update an xpanse incident.
- add entry
- investigates security incidents, triages alerts, and coordinates response actions.
- search xsiam alerts.
- get script results
- get owned ip ranges from xpanse.
- compliance team
- update attack surface rule
- enterprise it
- get script execution results.
- get xpanse audit logs.
- create a new investigation in cortex xsoar.
- incident responder
- list incidents
- subscription manager
- xdr update incident
- start an xql query on xdr.
- search xsiam alerts with filters.
- list and manage xsoar playbooks.
- malware researcher
- network operations
- manage enterprise browser policies, user sessions, and deployments.
- conducts automated adversarial testing against ai systems and llm applications.
- xsiam list incidents
- search integration instances
- retrieve a specific incident by id from cortex xsoar.
- incident response
- search xdr alerts.
- create investigation
- list available playbooks in cortex xsoar.
- get incident details from xdr.
- threat intel analyst
- firewall
- xsoar create investigation
- browser security admin
- xsoar create incident
- security operations
- start xql query
- list xsiam endpoints with filters.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- threat hunter
- list xdr incidents.
- run script
- secure access service edge with remote networking, sd-wan, and zero trust access.
- compliance officer
- search incidents
- search xsiam incidents.
- initiate a scan on endpoints via xdr.
- get audit management logs from xdr.
- xpanse list services
- get xsiam management logs
- get asset details
- get xql query results from xsiam.
- xdr isolate endpoints
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- retrieve a specific investigation by id from xsoar.
- search incidents with filters.
- search xsiam incidents
- search xpanse incidents.
- xdr list incidents
- xpanse list exposed assets
- run a playbook on an investigation in cortex xsoar.
- xsoar add entry
- xsoar update incident
- xsiam list assets
- xpanse get audit logs
- add an entry to an investigation in xsoar.
- xpanse list attack surface rules
- search owned ip ranges.
- list xsiam assets with filters.
- search incidents with filters in cortex xsoar.
- search exposed assets
- xsoar search integration instances
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- ai runtime security scanning and automated red teaming for ai applications.
- saas security admin
- manages multi-tenant security operations at scale for managed service providers.
- configure a datasource for xsiam ingestion.
- list xdr endpoints with optional filters, pagination, and sorting.
- get xdr audit logs.
- search integrations
- digital experience monitoring, log management, and best practice assessment.
- data protection analyst
- xdr get script results
- cloud security
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- platform engineer
- proactively searches for threats and iocs across telemetry data.
- network architect
- list xdr incidents with optional filters, pagination, and sorting.
- run a playbook on an investigation in xsoar.
- red team operator
- get management logs from xsiam.
- add an entry to an investigation in cortex xsoar.
- xdr get incident details
- get audit management logs from xpanse.
- create a new incident in cortex xsoar.
- xsiam start xql query
- get investigation
- search xsoar integration instances.
- search xdr alerts
- isolate endpoints from the network.
- start an xql query on xsiam.
- xsiam configure datasource
- get internet exposure details for specific assets from xpanse.
- executes containment, eradication, and recovery actions during security incidents.
- researches threat actors, malware campaigns, and vulnerability trends.
- update an xdr incident.
- sase
- get xpanse incidents.
- xsoar get incident
- create an incident in xsoar.
- get xsiam xql query results
- list xdr alerts with optional filters, pagination, and sorting.
- soc
- cybersecurity
- update incident
- search xdr alerts with filters.
- isolate endpoints
- xpanse update incident
- search xsiam incidents with filters.
- manages multi-tenant hierarchies and service group configurations for mssps.
- search ip ranges
- search xsiam assets
- search for integration instances in cortex xsoar.
- palo alto networks
- start xsiam xql query
- list xsiam incidents with optional filters and pagination.
- identity and access management, tenant hierarchies, and subscription management.
- scan endpoints
- run scripts on endpoints.
- get xsiam management logs.
- get details for a specific exposed asset.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- search xsiam endpoints.
- xdr unisolate endpoints
- search exposed services.
- cloud security engineer
- designs and implements network security architectures and policies.
- xpanse update attack surface rule
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- mssp operator
- xdr list alerts
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- xsoar get investigation
- sase admin
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- search services
- search xdr incidents with filters.
- iam admin
- initiate a scan on endpoints.
- run playbook
- search xsoar integrations.
- search xsiam assets.
- enterprise browser policy management and secure browsing.
- network security
- sd wan operator
- start xql queries on xdr.
- manages logging infrastructure, integrations, and platform automation.
- xsiam get management logs
- search xsiam alerts
- search for available integrations in cortex xsoar.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- get script execution results from xdr.
- xpanse get asset details
- search attack surface rules
- unisolate endpoints and restore network connectivity via xdr.
- get exposed services from xpanse.
- search xpanse incidents
- xdr scan endpoints
- xdr run script
- xsoar list playbooks
- search for available integrations in xsoar.
- search endpoints
- unisolate endpoints.
- get xql query results
- search xsiam endpoints
- network security engineer
slug: incident-response
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
