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
- subscription manager
- list xsiam incidents with optional filters and pagination.
- search exposed services.
- browser security admin
- get incident details from xdr.
- retrieve a specific investigation by id from xsoar.
- firewall admin
- xsiam list alerts
- run script
- network architect
- researches threat actors, malware campaigns, and vulnerability trends.
- search endpoints
- get script execution results from xdr.
- enterprise browser policy management and secure browsing.
- platform engineer
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- list xsiam assets with filters.
- isolate endpoints from the network.
- retrieve a specific incident by id from cortex xsoar.
- executes containment, eradication, and recovery actions during security incidents.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- security operations
- red team operator
- cloud security
- xsiam list endpoints
- xpanse list ip ranges
- search for available integrations in xsoar.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- start xql query
- get audit management logs from xpanse.
- xpanse get audit logs
- search incidents with filters in cortex xsoar.
- initiate a scan on endpoints.
- xsiam list assets
- get script execution results.
- analyzes suspicious files and samples for malware characteristics.
- unisolate endpoints and restore network connectivity.
- list incidents
- scan endpoints.
- run a playbook on an investigation in cortex xsoar.
- enterprise it
- get xdr audit logs.
- start xql queries on xsiam.
- search xsoar integrations.
- list playbooks
- retrieve a specific investigation by id from cortex xsoar.
- manages multi-tenant hierarchies and service group configurations for mssps.
- sd wan operator
- configure a datasource for xsiam ingestion.
- compliance officer
- firewall
- list xsiam endpoints with filters.
- run scripts on endpoints.
- create xsoar investigations.
- add entries to investigations.
- search services
- create incident
- threat hunter
- search xdr alerts with filters.
- isolate endpoints from the network via xdr.
- get owned ip ranges from xpanse.
- get xql query results
- get extra data for a specific xdr incident.
- update an existing incident in cortex xsoar.
- search owned ip ranges.
- xsoar search integrations
- list xdr incidents.
- get or update a specific incident.
- xdr update incident
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- search xsoar integration instances.
- get xpanse audit logs.
- xpanse list services
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- search xpanse incidents with filters.
- search for integration instances in cortex xsoar.
- get exposed services from xpanse.
- data protection analyst
- xdr scan endpoints
- manages logging infrastructure, integrations, and platform automation.
- xpanse update attack surface rule
- search incidents with filters.
- xdr start xql query
- search ip ranges
- search xpanse incidents.
- update an xpanse incident.
- create an incident in xsoar.
- update an attack surface rule in xpanse.
- xsiam get management logs
- search xsiam assets.
- search for integration instances in xsoar.
- xdr get incident details
- manages service accounts, roles, and access policies for platform api access.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- sre
- xdr run script
- palo alto networks
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- compliance team
- search xpanse incidents
- list xsiam alerts with optional filters and pagination.
- search xsiam alerts with filters.
- update attack surface rule
- xsoar get incident
- cloud security engineer
- xpanse get asset details
- add entry
- xdr list incidents
- investigates security incidents, triages alerts, and coordinates response actions.
- search xsiam alerts
- get attack surface rules from xpanse.
- create a new incident in cortex xsoar.
- start xsiam xql query
- network operations
- monitors and remediates cloud security misconfigurations and compliance violations.
- sase admin
- start an xql query on xsiam.
- xsoar get investigation
- isolate endpoints.
- manage enterprise browser policies, user sessions, and deployments.
- ai security engineer
- search attack surface rules.
- get audit management logs from xdr.
- get asset details
- run a script on endpoints.
- create investigation
- manages enterprise browser policies and secure browsing configurations.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- ai runtime security scanning and automated red teaming for ai applications.
- soar
- unisolate endpoints
- xsoar list playbooks
- configure datasource
- run a script on endpoints via xdr.
- investigates dlp incidents and manages sensitive data protection policies.
- search xsiam alerts.
- get xsiam management logs
- conducts automated adversarial testing against ai systems and llm applications.
- malware researcher
- cybersecurity
- create a new investigation in xsoar.
- list xsiam assets with optional filters.
- incident responder
- get internet exposure details for specific assets from xpanse.
- get xpanse audit logs
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- xsiam configure datasource
- list available playbooks in xsoar.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- detection and response
- xsoar create incident
- search xsiam incidents.
- start xql queries on xdr.
- get xsiam xql query results
- get investigation
- soc
- search integration instances
- xdr get audit logs
- threat intel analyst
- iam admin
- start an xql query on xdr.
- search xdr incidents with filters.
- list xdr alerts with optional filters, pagination, and sorting.
- xdr get script results
- xsoar search integration instances
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- proactively searches for threats and iocs across telemetry data.
- search for available integrations in cortex xsoar.
- xsoar update incident
- xdr list endpoints
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- digital experience monitoring, log management, and best practice assessment.
- list available playbooks in cortex xsoar.
- list xdr incidents with optional filters, pagination, and sorting.
- xsoar add entry
- mssp operator
- isolate endpoints
- xpanse list incidents
- add an entry to an investigation in xsoar.
- xpanse list exposed assets
- incident response
- list xdr endpoints with filters.
- xdr list alerts
- get xpanse incidents.
- network security
- threat intelligence
- incident management — list, search, create, and update incidents.
- run playbook
- xdr get xql results
- get details for a specific exposed asset.
- get xdr audit logs
- monitors network health, performance, and digital experience metrics.
- manages multi-tenant security operations at scale for managed service providers.
- update xpanse incident
- list xsiam endpoints with optional filters.
- search xsiam incidents with filters.
- search incidents
- xsiam list incidents
- secures ai applications with runtime scanning and vulnerability assessment.
- get incident details
- get xql query results from xdr.
- tenant operator
- list xdr endpoints with optional filters, pagination, and sorting.
- identity and access management, tenant hierarchies, and subscription management.
- get management logs from xsiam.
- update an attack surface rule.
- xdr unisolate endpoints
- update an xdr incident.
- scan endpoints
- run xsoar playbooks.
- search attack surface rules
- get xsiam management logs.
- soc analyst
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- designs and implements network security architectures and policies.
- add an entry to an investigation in cortex xsoar.
- search xdr endpoints.
- search xsiam endpoints.
- search integrations
- xpanse update incident
- create a new investigation in cortex xsoar.
- xpanse list attack surface rules
- xsoar search incidents
- secure access service edge with remote networking, sd-wan, and zero trust access.
- sase
- search xdr alerts
- search xsiam endpoints
- search xsiam incidents
- get a specific investigation.
- initiate a scan on endpoints via xdr.
- saas security admin
- configure xsiam datasources.
- get internet-exposed assets from xpanse.
- run a playbook on an investigation in xsoar.
- xsiam get xql results
- xdr
- unisolate endpoints.
- update incident
- vulnerability manager
- search xdr alerts.
- xsoar run playbook
- search exposed assets
- unisolate endpoints and restore network connectivity via xdr.
- get xql query results from xsiam.
- cloud security posture management, compliance monitoring, and workload protection.
- firewall policy management, network objects, and cloud-native firewall configuration.
- xsoar create investigation
- network security engineer
- xsiam start xql query
- search internet-exposed assets.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- designs sase and sd-wan network architectures for secure remote access.
- list and manage xsoar playbooks.
- xdr isolate endpoints
- get script results
- data loss prevention, saas security monitoring, and identity security posture.
- search xsiam assets
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
