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
- get asset details
- get investigation
- add entries to investigations.
- red team operator
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- xdr list alerts
- start xql queries on xdr.
- network architect
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- data loss prevention, saas security monitoring, and identity security posture.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- get exposed services from xpanse.
- get management logs from xsiam.
- xsiam list alerts
- get audit management logs from xpanse.
- search integrations
- xsoar search incidents
- search xpanse incidents.
- retrieve a specific incident by id from cortex xsoar.
- xsiam start xql query
- executes containment, eradication, and recovery actions during security incidents.
- search xsiam alerts with filters.
- list xsiam assets with optional filters.
- xdr get xql results
- configure datasource
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- vulnerability manager
- scan endpoints.
- firewall policy management, network objects, and cloud-native firewall configuration.
- xpanse get asset details
- start an xql query on xdr.
- update attack surface rule
- run xsoar playbooks.
- sase admin
- secures ai applications with runtime scanning and vulnerability assessment.
- search owned ip ranges.
- xdr unisolate endpoints
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- detection and response
- search incidents with filters in cortex xsoar.
- start an xql query on xsiam.
- cybersecurity
- update an attack surface rule.
- configure a datasource for xsiam ingestion.
- configure xsiam datasources.
- run a playbook on an investigation in xsoar.
- update an existing incident in cortex xsoar.
- xsoar add entry
- run scripts on endpoints.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- get owned ip ranges from xpanse.
- monitors and remediates cloud security misconfigurations and compliance violations.
- list xsiam endpoints with optional filters.
- investigates dlp incidents and manages sensitive data protection policies.
- create a new investigation in xsoar.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- analyzes suspicious files and samples for malware characteristics.
- get incident details from xdr.
- search xsiam endpoints.
- search exposed services.
- search for integration instances in xsoar.
- xsoar get incident
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- conducts automated adversarial testing against ai systems and llm applications.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- search attack surface rules
- search xdr alerts
- search for integration instances in cortex xsoar.
- xsoar list playbooks
- xsiam configure datasource
- get audit management logs from xdr.
- search internet-exposed assets.
- xpanse list services
- network security engineer
- manages enterprise browser policies and secure browsing configurations.
- list and manage xsoar playbooks.
- initiate a scan on endpoints via xdr.
- xdr
- search xsiam assets.
- ai runtime security scanning and automated red teaming for ai applications.
- enterprise browser policy management and secure browsing.
- start xql queries on xsiam.
- list xsiam endpoints with filters.
- threat intel analyst
- xpanse update attack surface rule
- xpanse list ip ranges
- soar
- search xsiam incidents.
- platform engineer
- create incident
- unisolate endpoints
- list xsiam assets with filters.
- xdr update incident
- update an xdr incident.
- manages multi-tenant hierarchies and service group configurations for mssps.
- get script execution results from xdr.
- manages logging infrastructure, integrations, and platform automation.
- xsiam list incidents
- get xdr audit logs
- get xql query results from xsiam.
- xsoar search integration instances
- investigates security incidents, triages alerts, and coordinates response actions.
- retrieve a specific investigation by id from xsoar.
- subscription manager
- add entry
- xsoar get investigation
- incident responder
- ai security engineer
- xsoar update incident
- run a script on endpoints.
- list available playbooks in xsoar.
- xdr get incident details
- update incident
- start xql query
- designs and implements network security architectures and policies.
- list incidents
- search ip ranges
- search endpoints
- secure access service edge with remote networking, sd-wan, and zero trust access.
- cloud security
- get xsiam xql query results
- list xdr incidents with optional filters, pagination, and sorting.
- unisolate endpoints.
- xsiam get management logs
- xdr isolate endpoints
- saas security admin
- xpanse list incidents
- isolate endpoints
- run a playbook on an investigation in cortex xsoar.
- xpanse update incident
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- run playbook
- search for available integrations in cortex xsoar.
- get or update a specific incident.
- search attack surface rules.
- manages multi-tenant security operations at scale for managed service providers.
- xpanse get audit logs
- manages service accounts, roles, and access policies for platform api access.
- search for available integrations in xsoar.
- search xsoar integration instances.
- xdr get script results
- get xpanse audit logs.
- soc analyst
- identity and access management, tenant hierarchies, and subscription management.
- get script execution results.
- xdr scan endpoints
- mssp operator
- unisolate endpoints and restore network connectivity.
- network operations
- xdr start xql query
- xsoar search integrations
- create investigation
- list available playbooks in cortex xsoar.
- threat intelligence
- get xsiam management logs.
- xsoar create incident
- get details for a specific exposed asset.
- sre
- get attack surface rules from xpanse.
- list xsiam incidents with optional filters and pagination.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- search xdr incidents with filters.
- get a specific investigation.
- search xdr alerts.
- proactively searches for threats and iocs across telemetry data.
- designs sase and sd-wan network architectures for secure remote access.
- create a new investigation in cortex xsoar.
- get script results
- digital experience monitoring, log management, and best practice assessment.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- xpanse list exposed assets
- cloud security engineer
- isolate endpoints from the network.
- scan endpoints
- list playbooks
- get xsiam management logs
- xsoar run playbook
- get incident details
- search xsiam incidents with filters.
- list xdr endpoints with optional filters, pagination, and sorting.
- xsiam get xql results
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- run script
- security operations
- create an incident in xsoar.
- soc
- search incidents
- search xsiam assets
- list xdr alerts with optional filters, pagination, and sorting.
- run a script on endpoints via xdr.
- xdr get audit logs
- data protection analyst
- enterprise it
- search incidents with filters.
- firewall
- get internet-exposed assets from xpanse.
- get xql query results from xdr.
- create a new incident in cortex xsoar.
- retrieve a specific investigation by id from cortex xsoar.
- search xpanse incidents
- search services
- search xsiam alerts
- search xdr endpoints.
- search exposed assets
- add an entry to an investigation in xsoar.
- palo alto networks
- firewall admin
- isolate endpoints.
- browser security admin
- update an attack surface rule in xpanse.
- iam admin
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- search xsoar integrations.
- search xsiam endpoints
- researches threat actors, malware campaigns, and vulnerability trends.
- network security
- get xpanse audit logs
- get extra data for a specific xdr incident.
- xdr list endpoints
- threat hunter
- incident response
- cloud security posture management, compliance monitoring, and workload protection.
- get internet exposure details for specific assets from xpanse.
- xdr list incidents
- xdr run script
- tenant operator
- list xdr endpoints with filters.
- unisolate endpoints and restore network connectivity via xdr.
- sase
- start xsiam xql query
- isolate endpoints from the network via xdr.
- initiate a scan on endpoints.
- sd wan operator
- get xpanse incidents.
- create xsoar investigations.
- xsiam list endpoints
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- search xdr alerts with filters.
- compliance team
- update an xpanse incident.
- manage enterprise browser policies, user sessions, and deployments.
- get xql query results
- list xsiam alerts with optional filters and pagination.
- xsiam list assets
- xpanse list attack surface rules
- search integration instances
- search xpanse incidents with filters.
- list xdr incidents.
- compliance officer
- search xsiam alerts.
- xsoar create investigation
- search xsiam incidents
- add an entry to an investigation in cortex xsoar.
- monitors network health, performance, and digital experience metrics.
- incident management — list, search, create, and update incidents.
- update xpanse incident
- malware researcher
- get xdr audit logs.
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
