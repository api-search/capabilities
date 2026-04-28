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
- list xdr endpoints with optional filters, pagination, and sorting.
- configure xsiam datasources.
- sase
- xsiam get management logs
- scan endpoints.
- analyzes suspicious files and samples for malware characteristics.
- start xql query
- get xdr audit logs.
- get attack surface rules from xpanse.
- run script
- get script execution results.
- search xpanse incidents with filters.
- run a playbook on an investigation in cortex xsoar.
- firewall admin
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- xsoar create incident
- search endpoints
- xdr get incident details
- search for available integrations in cortex xsoar.
- get xsiam management logs.
- initiate a scan on endpoints.
- xsiam list endpoints
- xsiam get xql results
- xdr get audit logs
- update an attack surface rule in xpanse.
- identity and access management, tenant hierarchies, and subscription management.
- xsiam list incidents
- soc analyst
- search xsiam alerts.
- run scripts on endpoints.
- retrieve a specific investigation by id from cortex xsoar.
- search xdr alerts with filters.
- search xsiam assets.
- search integrations
- create a new incident in cortex xsoar.
- xdr unisolate endpoints
- get owned ip ranges from xpanse.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- retrieve a specific investigation by id from xsoar.
- search xsoar integration instances.
- get xql query results
- get xdr audit logs
- sre
- platform engineer
- isolate endpoints
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- get xql query results from xdr.
- list xsiam assets with filters.
- start an xql query on xdr.
- search incidents
- xdr update incident
- isolate endpoints from the network via xdr.
- get investigation
- get xpanse audit logs
- get a specific investigation.
- tenant operator
- threat intelligence
- ai runtime security scanning and automated red teaming for ai applications.
- get extra data for a specific xdr incident.
- manages multi-tenant hierarchies and service group configurations for mssps.
- run playbook
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- xsoar get investigation
- cloud security
- isolate endpoints.
- xdr scan endpoints
- get script execution results from xdr.
- xdr get script results
- update incident
- xpanse list exposed assets
- get or update a specific incident.
- search xsiam endpoints
- search xdr alerts.
- xpanse list ip ranges
- malware researcher
- search attack surface rules
- data protection analyst
- search for available integrations in xsoar.
- saas security admin
- enterprise browser policy management and secure browsing.
- monitors network health, performance, and digital experience metrics.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- search xdr alerts
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- network security
- search internet-exposed assets.
- search xpanse incidents.
- list xdr alerts with optional filters, pagination, and sorting.
- xdr get xql results
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- search xdr incidents with filters.
- proactively searches for threats and iocs across telemetry data.
- compliance officer
- update an attack surface rule.
- create a new investigation in xsoar.
- xpanse list services
- compliance team
- unisolate endpoints and restore network connectivity via xdr.
- get asset details
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- designs and implements network security architectures and policies.
- update an xpanse incident.
- update an existing incident in cortex xsoar.
- manages enterprise browser policies and secure browsing configurations.
- palo alto networks
- cloud security engineer
- investigates security incidents, triages alerts, and coordinates response actions.
- xsiam list assets
- data loss prevention, saas security monitoring, and identity security posture.
- run a script on endpoints via xdr.
- run a script on endpoints.
- search exposed assets
- search xsiam incidents with filters.
- xdr
- search services
- start xsiam xql query
- cloud security posture management, compliance monitoring, and workload protection.
- update attack surface rule
- retrieve a specific incident by id from cortex xsoar.
- search for integration instances in xsoar.
- xsoar run playbook
- sd wan operator
- get internet exposure details for specific assets from xpanse.
- list xdr endpoints with filters.
- get xpanse audit logs.
- start an xql query on xsiam.
- create investigation
- get audit management logs from xpanse.
- xpanse get asset details
- xpanse list attack surface rules
- xdr start xql query
- search xsiam incidents.
- run a playbook on an investigation in xsoar.
- incident responder
- researches threat actors, malware campaigns, and vulnerability trends.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- search xpanse incidents
- list xsiam incidents with optional filters and pagination.
- get xpanse incidents.
- configure datasource
- search attack surface rules.
- xdr isolate endpoints
- search exposed services.
- add entry
- search owned ip ranges.
- executes containment, eradication, and recovery actions during security incidents.
- xsiam start xql query
- iam admin
- manages service accounts, roles, and access policies for platform api access.
- cybersecurity
- security operations
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- firewall
- conducts automated adversarial testing against ai systems and llm applications.
- xsoar update incident
- initiate a scan on endpoints via xdr.
- network architect
- subscription manager
- unisolate endpoints
- create an incident in xsoar.
- get xsiam xql query results
- create xsoar investigations.
- search xsiam alerts
- list available playbooks in xsoar.
- xpanse get audit logs
- list xdr incidents.
- search xsiam alerts with filters.
- xdr list alerts
- sase admin
- search incidents with filters.
- start xql queries on xdr.
- red team operator
- xsoar list playbooks
- configure a datasource for xsiam ingestion.
- manage enterprise browser policies, user sessions, and deployments.
- get management logs from xsiam.
- xsiam list alerts
- ai security engineer
- search integration instances
- list xsiam endpoints with optional filters.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- search incidents with filters in cortex xsoar.
- xsoar get incident
- manages logging infrastructure, integrations, and platform automation.
- xsoar create investigation
- detection and response
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get script results
- search xsoar integrations.
- list xsiam endpoints with filters.
- investigates dlp incidents and manages sensitive data protection policies.
- create incident
- start xql queries on xsiam.
- update an xdr incident.
- xpanse update attack surface rule
- list xsiam assets with optional filters.
- incident response
- scan endpoints
- xdr list endpoints
- list incidents
- unisolate endpoints.
- add entries to investigations.
- create a new investigation in cortex xsoar.
- enterprise it
- isolate endpoints from the network.
- search xsiam endpoints.
- list playbooks
- xsiam configure datasource
- unisolate endpoints and restore network connectivity.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- add an entry to an investigation in xsoar.
- list and manage xsoar playbooks.
- xsoar search integrations
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- browser security admin
- xsoar add entry
- monitors and remediates cloud security misconfigurations and compliance violations.
- xpanse list incidents
- get internet-exposed assets from xpanse.
- xsoar search integration instances
- search xsiam assets
- digital experience monitoring, log management, and best practice assessment.
- search ip ranges
- run xsoar playbooks.
- threat intel analyst
- vulnerability manager
- get incident details from xdr.
- xsoar search incidents
- firewall policy management, network objects, and cloud-native firewall configuration.
- list available playbooks in cortex xsoar.
- get incident details
- threat hunter
- secure access service edge with remote networking, sd-wan, and zero trust access.
- list xsiam alerts with optional filters and pagination.
- get details for a specific exposed asset.
- list xdr incidents with optional filters, pagination, and sorting.
- get xsiam management logs
- get exposed services from xpanse.
- network security engineer
- secures ai applications with runtime scanning and vulnerability assessment.
- search xdr endpoints.
- soar
- xdr run script
- get xql query results from xsiam.
- add an entry to an investigation in cortex xsoar.
- mssp operator
- network operations
- soc
- search xsiam incidents
- get audit management logs from xdr.
- xdr list incidents
- designs sase and sd-wan network architectures for secure remote access.
- manages multi-tenant security operations at scale for managed service providers.
- xpanse update incident
- update xpanse incident
- search for integration instances in cortex xsoar.
- incident management — list, search, create, and update incidents.
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
