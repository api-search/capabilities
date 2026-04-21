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
- search attack surface rules
- xsiam get xql results
- run a playbook on an investigation in cortex xsoar.
- firewall policy management, network objects, and cloud-native firewall configuration.
- proactively searches for threats and iocs across telemetry data.
- search services
- xsoar add entry
- search xsiam endpoints
- search owned ip ranges.
- create an incident in xsoar.
- get or update a specific incident.
- list xdr endpoints with filters.
- xsoar create incident
- search xsoar integrations.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- get xdr audit logs.
- xdr get xql results
- get owned ip ranges from xpanse.
- search xsiam incidents with filters.
- list xsiam alerts with optional filters and pagination.
- xdr isolate endpoints
- threat intel analyst
- xdr list incidents
- retrieve a specific investigation by id from xsoar.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- get details for a specific exposed asset.
- enterprise browser policy management and secure browsing.
- create a new investigation in xsoar.
- data loss prevention, saas security monitoring, and identity security posture.
- list xdr incidents.
- list xdr endpoints with optional filters, pagination, and sorting.
- mssp operator
- search xsiam incidents.
- saas security admin
- search xdr incidents with filters.
- enterprise it
- data protection analyst
- xsiam get management logs
- get xpanse incidents.
- get investigation
- soc
- list xdr incidents with optional filters, pagination, and sorting.
- xdr run script
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- search for integration instances in cortex xsoar.
- browser security admin
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- network security
- start xql queries on xdr.
- incident management — list, search, create, and update incidents.
- xsoar create investigation
- search xdr alerts with filters.
- retrieve a specific incident by id from cortex xsoar.
- search xpanse incidents with filters.
- secures ai applications with runtime scanning and vulnerability assessment.
- create investigation
- search xsiam incidents
- unisolate endpoints.
- list incidents
- get script execution results.
- update attack surface rule
- get xpanse audit logs.
- get script execution results from xdr.
- xsiam start xql query
- sd wan operator
- xsiam list incidents
- search xsiam endpoints.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- threat hunter
- configure a datasource for xsiam ingestion.
- initiate a scan on endpoints via xdr.
- xdr update incident
- incident response
- start an xql query on xsiam.
- get a specific investigation.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- isolate endpoints from the network.
- search integration instances
- search internet-exposed assets.
- run a script on endpoints.
- tenant operator
- manages enterprise browser policies and secure browsing configurations.
- xsoar search integration instances
- get management logs from xsiam.
- firewall
- cloud security
- cloud security posture management, compliance monitoring, and workload protection.
- search incidents
- cybersecurity
- xdr start xql query
- network security engineer
- initiate a scan on endpoints.
- add entries to investigations.
- xpanse list exposed assets
- xsiam list alerts
- search xdr alerts
- start an xql query on xdr.
- get internet-exposed assets from xpanse.
- search endpoints
- xsoar run playbook
- isolate endpoints from the network via xdr.
- subscription manager
- xdr get incident details
- sase
- compliance team
- get xql query results from xsiam.
- start xsiam xql query
- update an existing incident in cortex xsoar.
- list xsiam assets with filters.
- analyzes suspicious files and samples for malware characteristics.
- designs and implements network security architectures and policies.
- xdr list alerts
- get audit management logs from xdr.
- update incident
- search xsiam assets
- configure datasource
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- xpanse list attack surface rules
- update an xdr incident.
- get xsiam management logs.
- ai security engineer
- vulnerability manager
- manages multi-tenant hierarchies and service group configurations for mssps.
- search xsiam alerts with filters.
- search attack surface rules.
- run script
- search xsoar integration instances.
- search xsiam assets.
- xdr
- manages multi-tenant security operations at scale for managed service providers.
- search for integration instances in xsoar.
- firewall admin
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- run playbook
- search for available integrations in xsoar.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- get xsiam xql query results
- investigates security incidents, triages alerts, and coordinates response actions.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- search integrations
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- xsoar get investigation
- manages service accounts, roles, and access policies for platform api access.
- list and manage xsoar playbooks.
- list available playbooks in xsoar.
- isolate endpoints.
- search xdr alerts.
- list playbooks
- incident responder
- compliance officer
- sase admin
- scan endpoints.
- get xql query results
- search xpanse incidents
- update an xpanse incident.
- update an attack surface rule in xpanse.
- red team operator
- search xsiam alerts
- designs sase and sd-wan network architectures for secure remote access.
- xsoar search incidents
- add an entry to an investigation in xsoar.
- add an entry to an investigation in cortex xsoar.
- xsiam list endpoints
- xsoar search integrations
- soc analyst
- update an attack surface rule.
- soar
- palo alto networks
- investigates dlp incidents and manages sensitive data protection policies.
- list xsiam incidents with optional filters and pagination.
- list xdr alerts with optional filters, pagination, and sorting.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- xpanse get audit logs
- detection and response
- configure xsiam datasources.
- xsoar get incident
- update xpanse incident
- create incident
- executes containment, eradication, and recovery actions during security incidents.
- unisolate endpoints
- get internet exposure details for specific assets from xpanse.
- get extra data for a specific xdr incident.
- unisolate endpoints and restore network connectivity.
- xsoar update incident
- xdr get script results
- ai runtime security scanning and automated red teaming for ai applications.
- conducts automated adversarial testing against ai systems and llm applications.
- sre
- list xsiam endpoints with optional filters.
- search ip ranges
- start xql queries on xsiam.
- get incident details from xdr.
- search xsiam alerts.
- run xsoar playbooks.
- get xdr audit logs
- xdr unisolate endpoints
- search for available integrations in cortex xsoar.
- search incidents with filters in cortex xsoar.
- network operations
- get audit management logs from xpanse.
- xsiam list assets
- list xsiam endpoints with filters.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- monitors network health, performance, and digital experience metrics.
- create a new incident in cortex xsoar.
- threat intelligence
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- xsoar list playbooks
- security operations
- identity and access management, tenant hierarchies, and subscription management.
- run scripts on endpoints.
- get xql query results from xdr.
- scan endpoints
- xdr scan endpoints
- xpanse update incident
- retrieve a specific investigation by id from cortex xsoar.
- get exposed services from xpanse.
- xdr get audit logs
- isolate endpoints
- xsiam configure datasource
- run a script on endpoints via xdr.
- manage enterprise browser policies, user sessions, and deployments.
- get script results
- start xql query
- search exposed services.
- manages logging infrastructure, integrations, and platform automation.
- get incident details
- add entry
- get xsiam management logs
- xpanse update attack surface rule
- search xpanse incidents.
- create a new investigation in cortex xsoar.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- search xdr endpoints.
- xdr list endpoints
- xpanse get asset details
- malware researcher
- search exposed assets
- network architect
- get attack surface rules from xpanse.
- get xpanse audit logs
- list available playbooks in cortex xsoar.
- create xsoar investigations.
- digital experience monitoring, log management, and best practice assessment.
- unisolate endpoints and restore network connectivity via xdr.
- xpanse list ip ranges
- xpanse list services
- run a playbook on an investigation in xsoar.
- search incidents with filters.
- platform engineer
- iam admin
- get asset details
- list xsiam assets with optional filters.
- xpanse list incidents
- monitors and remediates cloud security misconfigurations and compliance violations.
- researches threat actors, malware campaigns, and vulnerability trends.
- cloud security engineer
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
