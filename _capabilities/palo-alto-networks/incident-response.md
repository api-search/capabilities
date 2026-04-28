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
- xpanse update attack surface rule
- threat intel analyst
- xsiam get management logs
- unisolate endpoints.
- isolate endpoints.
- analyzes suspicious files and samples for malware characteristics.
- search xdr incidents with filters.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- search for available integrations in cortex xsoar.
- search xpanse incidents
- add an entry to an investigation in xsoar.
- xsoar get incident
- search attack surface rules
- get a specific investigation.
- xsoar list playbooks
- enterprise browser policy management and secure browsing.
- search exposed assets
- compliance team
- update incident
- conducts automated adversarial testing against ai systems and llm applications.
- scan endpoints
- get asset details
- run scripts on endpoints.
- browser security admin
- get internet-exposed assets from xpanse.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- get xpanse incidents.
- search xsiam incidents
- get xql query results from xdr.
- search xsiam endpoints.
- detection and response
- search integration instances
- get xql query results
- xpanse list attack surface rules
- xsoar create investigation
- sre
- designs sase and sd-wan network architectures for secure remote access.
- incident management — list, search, create, and update incidents.
- cloud security posture management, compliance monitoring, and workload protection.
- ai runtime security scanning and automated red teaming for ai applications.
- saas security admin
- search incidents
- create a new investigation in cortex xsoar.
- get management logs from xsiam.
- scan endpoints.
- firewall admin
- unisolate endpoints and restore network connectivity.
- xsiam list endpoints
- xsiam list assets
- xsiam list alerts
- platform engineer
- xdr get incident details
- get xsiam management logs.
- xdr start xql query
- list xsiam alerts with optional filters and pagination.
- researches threat actors, malware campaigns, and vulnerability trends.
- add entry
- xdr list endpoints
- add entries to investigations.
- search xsiam alerts
- list xdr incidents.
- red team operator
- isolate endpoints from the network via xdr.
- sd wan operator
- manages multi-tenant hierarchies and service group configurations for mssps.
- network security engineer
- start an xql query on xsiam.
- get xdr audit logs.
- monitors network health, performance, and digital experience metrics.
- get or update a specific incident.
- security operations
- cloud security
- mssp operator
- list available playbooks in xsoar.
- cloud security engineer
- get exposed services from xpanse.
- create an incident in xsoar.
- get xsiam xql query results
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- update an xpanse incident.
- get script results
- create a new incident in cortex xsoar.
- get details for a specific exposed asset.
- start an xql query on xdr.
- run playbook
- xsoar run playbook
- firewall
- threat hunter
- xsoar search integration instances
- secures ai applications with runtime scanning and vulnerability assessment.
- list xdr incidents with optional filters, pagination, and sorting.
- network security
- network operations
- incident response
- search xsiam alerts.
- get internet exposure details for specific assets from xpanse.
- start xql query
- create xsoar investigations.
- create a new investigation in xsoar.
- data protection analyst
- xdr list incidents
- enterprise it
- update an attack surface rule.
- get xpanse audit logs
- xsiam list incidents
- xpanse get asset details
- xdr unisolate endpoints
- list available playbooks in cortex xsoar.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- search xsoar integrations.
- start xsiam xql query
- search xsiam assets
- soc analyst
- xpanse update incident
- xdr update incident
- xpanse list ip ranges
- run xsoar playbooks.
- network architect
- search xsoar integration instances.
- xdr isolate endpoints
- start xql queries on xsiam.
- search xsiam incidents with filters.
- get incident details
- search for integration instances in cortex xsoar.
- list and manage xsoar playbooks.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- xsoar get investigation
- run a script on endpoints.
- run a playbook on an investigation in xsoar.
- run a playbook on an investigation in cortex xsoar.
- tenant operator
- manage enterprise browser policies, user sessions, and deployments.
- get xql query results from xsiam.
- soc
- retrieve a specific investigation by id from xsoar.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- list xdr endpoints with optional filters, pagination, and sorting.
- xdr list alerts
- ai security engineer
- list xsiam endpoints with filters.
- list xsiam incidents with optional filters and pagination.
- xdr run script
- xsiam configure datasource
- search xsiam incidents.
- search xdr alerts
- proactively searches for threats and iocs across telemetry data.
- search for integration instances in xsoar.
- sase admin
- get audit management logs from xpanse.
- search xsiam alerts with filters.
- isolate endpoints
- xsiam start xql query
- configure a datasource for xsiam ingestion.
- add an entry to an investigation in cortex xsoar.
- search incidents with filters.
- investigates dlp incidents and manages sensitive data protection policies.
- unisolate endpoints and restore network connectivity via xdr.
- list xsiam assets with optional filters.
- monitors and remediates cloud security misconfigurations and compliance violations.
- get audit management logs from xdr.
- xdr get xql results
- initiate a scan on endpoints via xdr.
- subscription manager
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- search incidents with filters in cortex xsoar.
- xsiam get xql results
- xdr get audit logs
- start xql queries on xdr.
- run a script on endpoints via xdr.
- xpanse list exposed assets
- xpanse get audit logs
- search xdr endpoints.
- get script execution results.
- list playbooks
- firewall policy management, network objects, and cloud-native firewall configuration.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- retrieve a specific incident by id from cortex xsoar.
- get xpanse audit logs.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- xsoar create incident
- search endpoints
- get owned ip ranges from xpanse.
- iam admin
- palo alto networks
- search integrations
- malware researcher
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- run script
- get attack surface rules from xpanse.
- unisolate endpoints
- update an attack surface rule in xpanse.
- initiate a scan on endpoints.
- xsoar add entry
- xpanse list services
- update an existing incident in cortex xsoar.
- soar
- search xsiam assets.
- threat intelligence
- get investigation
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- get xdr audit logs
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- sase
- manages multi-tenant security operations at scale for managed service providers.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- search xpanse incidents.
- list incidents
- list xdr alerts with optional filters, pagination, and sorting.
- xsoar search integrations
- xdr scan endpoints
- incident responder
- list xdr endpoints with filters.
- manages service accounts, roles, and access policies for platform api access.
- xsoar search incidents
- xdr get script results
- isolate endpoints from the network.
- vulnerability manager
- xsoar update incident
- cybersecurity
- get incident details from xdr.
- search xsiam endpoints
- update xpanse incident
- search exposed services.
- configure xsiam datasources.
- create investigation
- list xsiam assets with filters.
- digital experience monitoring, log management, and best practice assessment.
- search internet-exposed assets.
- manages logging infrastructure, integrations, and platform automation.
- xdr
- executes containment, eradication, and recovery actions during security incidents.
- search services
- get xsiam management logs
- compliance officer
- xpanse list incidents
- search xdr alerts with filters.
- search ip ranges
- list xsiam endpoints with optional filters.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- designs and implements network security architectures and policies.
- identity and access management, tenant hierarchies, and subscription management.
- search xpanse incidents with filters.
- retrieve a specific investigation by id from cortex xsoar.
- manages enterprise browser policies and secure browsing configurations.
- search attack surface rules.
- update attack surface rule
- search owned ip ranges.
- get extra data for a specific xdr incident.
- data loss prevention, saas security monitoring, and identity security posture.
- search for available integrations in xsoar.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- create incident
- update an xdr incident.
- search xdr alerts.
- configure datasource
- get script execution results from xdr.
- investigates security incidents, triages alerts, and coordinates response actions.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
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
