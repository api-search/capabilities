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
- xsoar add entry
- firewall policy management, network objects, and cloud-native firewall configuration.
- get audit management logs from xpanse.
- search for available integrations in xsoar.
- search integration instances
- sase admin
- search incidents with filters in cortex xsoar.
- designs and implements network security architectures and policies.
- incident management — list, search, create, and update incidents.
- create investigation
- designs sase and sd-wan network architectures for secure remote access.
- run a script on endpoints via xdr.
- xdr list incidents
- add entry
- xsoar run playbook
- configure xsiam datasources.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- monitors and remediates cloud security misconfigurations and compliance violations.
- get xpanse audit logs.
- update an xdr incident.
- retrieve a specific investigation by id from xsoar.
- xdr scan endpoints
- xsoar search integrations
- create a new investigation in cortex xsoar.
- manages multi-tenant security operations at scale for managed service providers.
- xsoar search integration instances
- list xsiam endpoints with optional filters.
- initiate a scan on endpoints.
- mssp operator
- update an existing incident in cortex xsoar.
- search endpoints
- xsiam get xql results
- run a script on endpoints.
- update an attack surface rule.
- isolate endpoints
- threat hunter
- get audit management logs from xdr.
- get internet-exposed assets from xpanse.
- initiate a scan on endpoints via xdr.
- soc
- configure a datasource for xsiam ingestion.
- network architect
- manages multi-tenant hierarchies and service group configurations for mssps.
- search xsiam alerts.
- search xpanse incidents
- incident responder
- network operations
- sase
- list xdr incidents with optional filters, pagination, and sorting.
- create an incident in xsoar.
- update incident
- search xsiam endpoints
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- run a playbook on an investigation in xsoar.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- iam admin
- soar
- xsoar create investigation
- get script execution results.
- list and manage xsoar playbooks.
- get xsiam xql query results
- executes containment, eradication, and recovery actions during security incidents.
- xdr get xql results
- search owned ip ranges.
- xsiam get management logs
- search xdr alerts
- analyzes suspicious files and samples for malware characteristics.
- get details for a specific exposed asset.
- xsiam configure datasource
- update attack surface rule
- list xsiam assets with filters.
- manage enterprise browser policies, user sessions, and deployments.
- list xdr endpoints with filters.
- xdr isolate endpoints
- manages logging infrastructure, integrations, and platform automation.
- palo alto networks
- get incident details from xdr.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- get xpanse incidents.
- list xsiam endpoints with filters.
- xpanse update incident
- list xdr incidents.
- add entries to investigations.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- search xsiam incidents
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- xpanse list incidents
- vulnerability manager
- get xsiam management logs
- search ip ranges
- cybersecurity
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- malware researcher
- manages enterprise browser policies and secure browsing configurations.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- search xpanse incidents with filters.
- isolate endpoints from the network via xdr.
- list available playbooks in cortex xsoar.
- manages service accounts, roles, and access policies for platform api access.
- list available playbooks in xsoar.
- firewall
- cloud security engineer
- add an entry to an investigation in cortex xsoar.
- get script execution results from xdr.
- data protection analyst
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- get internet exposure details for specific assets from xpanse.
- search for integration instances in xsoar.
- isolate endpoints.
- list xdr endpoints with optional filters, pagination, and sorting.
- soc analyst
- xpanse get asset details
- search xsiam assets
- get xql query results from xsiam.
- proactively searches for threats and iocs across telemetry data.
- red team operator
- search xsiam endpoints.
- xpanse list services
- detection and response
- create a new investigation in xsoar.
- xdr get incident details
- xsoar search incidents
- search attack surface rules
- xpanse list exposed assets
- retrieve a specific investigation by id from cortex xsoar.
- search xsiam alerts
- digital experience monitoring, log management, and best practice assessment.
- threat intelligence
- xpanse list attack surface rules
- secures ai applications with runtime scanning and vulnerability assessment.
- search xdr alerts with filters.
- start an xql query on xdr.
- subscription manager
- start xql queries on xsiam.
- xsiam start xql query
- unisolate endpoints
- ai runtime security scanning and automated red teaming for ai applications.
- get incident details
- xdr get audit logs
- scan endpoints
- search services
- search xsiam assets.
- start xql query
- xsoar update incident
- run xsoar playbooks.
- compliance officer
- get xdr audit logs.
- network security engineer
- xsoar create incident
- xsoar get incident
- xdr list endpoints
- cloud security
- data loss prevention, saas security monitoring, and identity security posture.
- update xpanse incident
- search xdr alerts.
- unisolate endpoints and restore network connectivity via xdr.
- saas security admin
- search xsoar integration instances.
- xpanse get audit logs
- firewall admin
- tenant operator
- list xsiam assets with optional filters.
- enterprise browser policy management and secure browsing.
- threat intel analyst
- search xdr endpoints.
- get attack surface rules from xpanse.
- cloud security posture management, compliance monitoring, and workload protection.
- get a specific investigation.
- xsiam list assets
- xdr run script
- investigates dlp incidents and manages sensitive data protection policies.
- search incidents with filters.
- update an xpanse incident.
- isolate endpoints from the network.
- get investigation
- get script results
- get extra data for a specific xdr incident.
- compliance team
- search integrations
- search xdr incidents with filters.
- get xql query results from xdr.
- search for integration instances in cortex xsoar.
- get xpanse audit logs
- unisolate endpoints and restore network connectivity.
- get management logs from xsiam.
- get exposed services from xpanse.
- xsiam list alerts
- create incident
- scan endpoints.
- get or update a specific incident.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- investigates security incidents, triages alerts, and coordinates response actions.
- get asset details
- retrieve a specific incident by id from cortex xsoar.
- list xsiam incidents with optional filters and pagination.
- create xsoar investigations.
- xsiam list incidents
- run script
- xsoar get investigation
- search internet-exposed assets.
- conducts automated adversarial testing against ai systems and llm applications.
- list xsiam alerts with optional filters and pagination.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- add an entry to an investigation in xsoar.
- search attack surface rules.
- list xdr alerts with optional filters, pagination, and sorting.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- researches threat actors, malware campaigns, and vulnerability trends.
- network security
- xdr start xql query
- run a playbook on an investigation in cortex xsoar.
- ai security engineer
- search exposed assets
- run scripts on endpoints.
- search xsiam incidents.
- start an xql query on xsiam.
- browser security admin
- search xpanse incidents.
- get xdr audit logs
- monitors network health, performance, and digital experience metrics.
- start xsiam xql query
- configure datasource
- secure access service edge with remote networking, sd-wan, and zero trust access.
- incident response
- xdr
- xsiam list endpoints
- sd wan operator
- xdr update incident
- xdr unisolate endpoints
- search incidents
- get xql query results
- list incidents
- search xsoar integrations.
- start xql queries on xdr.
- search xsiam incidents with filters.
- xpanse list ip ranges
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- run playbook
- sre
- get owned ip ranges from xpanse.
- list playbooks
- search for available integrations in cortex xsoar.
- search exposed services.
- security operations
- xsoar list playbooks
- platform engineer
- enterprise it
- create a new incident in cortex xsoar.
- identity and access management, tenant hierarchies, and subscription management.
- xdr get script results
- search xsiam alerts with filters.
- update an attack surface rule in xpanse.
- unisolate endpoints.
- get xsiam management logs.
- xdr list alerts
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
