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
- monitors and remediates cloud security misconfigurations and compliance violations.
- xdr list incidents
- search xdr alerts.
- list xsiam endpoints with filters.
- xsoar update incident
- search exposed assets
- search xsiam assets.
- get script execution results from xdr.
- network security
- get xsiam xql query results
- xsoar get incident
- xsoar create incident
- start xql queries on xsiam.
- xpanse get audit logs
- firewall
- search for available integrations in xsoar.
- get xpanse audit logs
- compliance team
- designs sase and sd-wan network architectures for secure remote access.
- palo alto networks
- saas security admin
- incident response
- unisolate endpoints
- search xpanse incidents with filters.
- xsoar create investigation
- investigates security incidents, triages alerts, and coordinates response actions.
- search xpanse incidents
- search xsiam incidents.
- xdr scan endpoints
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- cloud security
- start xsiam xql query
- get xdr audit logs
- ai security engineer
- list and manage xsoar playbooks.
- retrieve a specific incident by id from cortex xsoar.
- update an attack surface rule in xpanse.
- create investigation
- executes containment, eradication, and recovery actions during security incidents.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- data loss prevention, saas security monitoring, and identity security posture.
- network architect
- manages enterprise browser policies and secure browsing configurations.
- search xsoar integration instances.
- xsoar run playbook
- create an incident in xsoar.
- search xsiam incidents
- run scripts on endpoints.
- add entries to investigations.
- xsoar search incidents
- xpanse list ip ranges
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- digital experience monitoring, log management, and best practice assessment.
- search for available integrations in cortex xsoar.
- list incidents
- xsiam get management logs
- tenant operator
- xdr isolate endpoints
- iam admin
- enterprise it
- xpanse get asset details
- get xdr audit logs.
- list xdr endpoints with optional filters, pagination, and sorting.
- xsoar search integrations
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- xsoar add entry
- list xdr alerts with optional filters, pagination, and sorting.
- manages multi-tenant security operations at scale for managed service providers.
- search xsiam alerts
- add an entry to an investigation in cortex xsoar.
- search xdr incidents with filters.
- list xsiam endpoints with optional filters.
- xsiam list incidents
- get script execution results.
- firewall policy management, network objects, and cloud-native firewall configuration.
- create a new investigation in cortex xsoar.
- get investigation
- update attack surface rule
- search ip ranges
- conducts automated adversarial testing against ai systems and llm applications.
- red team operator
- update an existing incident in cortex xsoar.
- run a playbook on an investigation in cortex xsoar.
- analyzes suspicious files and samples for malware characteristics.
- sd wan operator
- xdr run script
- search services
- proactively searches for threats and iocs across telemetry data.
- get xsiam management logs.
- xpanse list attack surface rules
- firewall admin
- list available playbooks in cortex xsoar.
- xsiam configure datasource
- platform engineer
- manage enterprise browser policies, user sessions, and deployments.
- start xql query
- search integration instances
- search xdr alerts with filters.
- search for integration instances in cortex xsoar.
- retrieve a specific investigation by id from cortex xsoar.
- search xdr alerts
- list xdr endpoints with filters.
- isolate endpoints.
- xsiam start xql query
- xsoar search integration instances
- list xdr incidents.
- get script results
- add an entry to an investigation in xsoar.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- data protection analyst
- sase
- xpanse list exposed assets
- secures ai applications with runtime scanning and vulnerability assessment.
- get management logs from xsiam.
- xdr start xql query
- search exposed services.
- sre
- unisolate endpoints and restore network connectivity via xdr.
- get incident details
- run a playbook on an investigation in xsoar.
- soc
- create incident
- search xsiam alerts.
- get owned ip ranges from xpanse.
- configure a datasource for xsiam ingestion.
- cloud security engineer
- list playbooks
- run a script on endpoints via xdr.
- get internet exposure details for specific assets from xpanse.
- xsoar get investigation
- manages multi-tenant hierarchies and service group configurations for mssps.
- enterprise browser policy management and secure browsing.
- initiate a scan on endpoints via xdr.
- xpanse list incidents
- scan endpoints.
- monitors network health, performance, and digital experience metrics.
- manages logging infrastructure, integrations, and platform automation.
- search xsiam alerts with filters.
- mssp operator
- update an xdr incident.
- search xsiam incidents with filters.
- threat intel analyst
- researches threat actors, malware campaigns, and vulnerability trends.
- xsiam get xql results
- get audit management logs from xdr.
- update incident
- xpanse update attack surface rule
- create a new investigation in xsoar.
- start an xql query on xsiam.
- update an xpanse incident.
- threat intelligence
- configure datasource
- ai runtime security scanning and automated red teaming for ai applications.
- get xpanse incidents.
- create xsoar investigations.
- run script
- retrieve a specific investigation by id from xsoar.
- xsiam list assets
- search integrations
- list xsiam assets with filters.
- run playbook
- list xdr incidents with optional filters, pagination, and sorting.
- isolate endpoints from the network.
- run a script on endpoints.
- update xpanse incident
- threat hunter
- malware researcher
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- identity and access management, tenant hierarchies, and subscription management.
- start xql queries on xdr.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- vulnerability manager
- isolate endpoints
- get or update a specific incident.
- search xsoar integrations.
- isolate endpoints from the network via xdr.
- xsoar list playbooks
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- incident responder
- xpanse list services
- search xsiam endpoints.
- browser security admin
- search xdr endpoints.
- xdr get audit logs
- search xsiam assets
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- xsiam list alerts
- soar
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- configure xsiam datasources.
- get xpanse audit logs.
- detection and response
- get xql query results
- run xsoar playbooks.
- create a new incident in cortex xsoar.
- investigates dlp incidents and manages sensitive data protection policies.
- cloud security posture management, compliance monitoring, and workload protection.
- xsiam list endpoints
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- subscription manager
- list xsiam alerts with optional filters and pagination.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- unisolate endpoints and restore network connectivity.
- get asset details
- get attack surface rules from xpanse.
- xdr get script results
- search incidents
- get extra data for a specific xdr incident.
- sase admin
- get xql query results from xdr.
- network security engineer
- start an xql query on xdr.
- xdr list alerts
- incident management — list, search, create, and update incidents.
- list xsiam assets with optional filters.
- get internet-exposed assets from xpanse.
- get audit management logs from xpanse.
- security operations
- search incidents with filters.
- search xpanse incidents.
- add entry
- get details for a specific exposed asset.
- get incident details from xdr.
- network operations
- search attack surface rules
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- xdr
- search for integration instances in xsoar.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- manages service accounts, roles, and access policies for platform api access.
- xdr get incident details
- search internet-exposed assets.
- soc analyst
- cybersecurity
- designs and implements network security architectures and policies.
- unisolate endpoints.
- xdr get xql results
- search incidents with filters in cortex xsoar.
- xpanse update incident
- get xql query results from xsiam.
- scan endpoints
- search owned ip ranges.
- compliance officer
- get exposed services from xpanse.
- get xsiam management logs
- search endpoints
- xdr unisolate endpoints
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- search attack surface rules.
- xdr list endpoints
- xdr update incident
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- search xsiam endpoints
- get a specific investigation.
- initiate a scan on endpoints.
- list xsiam incidents with optional filters and pagination.
- list available playbooks in xsoar.
- update an attack surface rule.
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
