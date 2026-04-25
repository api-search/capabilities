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
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- manages service accounts, roles, and access policies for platform api access.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- create xsoar investigations.
- search xpanse incidents.
- get audit management logs from xdr.
- search incidents with filters.
- xdr isolate endpoints
- xdr get audit logs
- get a specific investigation.
- xdr list incidents
- manage enterprise browser policies, user sessions, and deployments.
- cloud security posture management, compliance monitoring, and workload protection.
- list available playbooks in xsoar.
- compliance team
- xsoar search integrations
- xsoar update incident
- subscription manager
- incident responder
- retrieve a specific investigation by id from cortex xsoar.
- enterprise browser policy management and secure browsing.
- start an xql query on xsiam.
- search incidents with filters in cortex xsoar.
- get xql query results from xdr.
- tenant operator
- get script execution results from xdr.
- red team operator
- mssp operator
- search xsoar integrations.
- sase admin
- run scripts on endpoints.
- get xpanse audit logs.
- list xsiam endpoints with optional filters.
- investigates dlp incidents and manages sensitive data protection policies.
- get xsiam management logs
- monitors network health, performance, and digital experience metrics.
- isolate endpoints from the network.
- get script results
- xsiam list alerts
- get internet-exposed assets from xpanse.
- search xdr alerts.
- create investigation
- search for integration instances in xsoar.
- update attack surface rule
- run playbook
- get audit management logs from xpanse.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- create a new investigation in xsoar.
- configure xsiam datasources.
- xsoar get incident
- start xsiam xql query
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- unisolate endpoints and restore network connectivity.
- cloud security
- proactively searches for threats and iocs across telemetry data.
- conducts automated adversarial testing against ai systems and llm applications.
- run a script on endpoints via xdr.
- incident management — list, search, create, and update incidents.
- get script execution results.
- create a new investigation in cortex xsoar.
- sre
- search incidents
- create a new incident in cortex xsoar.
- list xdr endpoints with optional filters, pagination, and sorting.
- data loss prevention, saas security monitoring, and identity security posture.
- isolate endpoints
- search xsiam alerts with filters.
- unisolate endpoints and restore network connectivity via xdr.
- manages enterprise browser policies and secure browsing configurations.
- start an xql query on xdr.
- search xdr alerts with filters.
- search xsiam assets
- manages logging infrastructure, integrations, and platform automation.
- ai runtime security scanning and automated red teaming for ai applications.
- get xsiam xql query results
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- firewall
- list xdr incidents.
- update an attack surface rule in xpanse.
- get xdr audit logs
- xdr unisolate endpoints
- run a playbook on an investigation in cortex xsoar.
- search exposed assets
- get xpanse incidents.
- network security
- create incident
- search xsoar integration instances.
- manages multi-tenant security operations at scale for managed service providers.
- xsoar run playbook
- search integrations
- search xpanse incidents
- xsoar search incidents
- search xsiam incidents with filters.
- security operations
- list xdr endpoints with filters.
- get owned ip ranges from xpanse.
- add an entry to an investigation in xsoar.
- xsiam configure datasource
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- xdr update incident
- list incidents
- executes containment, eradication, and recovery actions during security incidents.
- data protection analyst
- search xdr endpoints.
- get management logs from xsiam.
- palo alto networks
- get incident details from xdr.
- add entry
- xpanse update attack surface rule
- vulnerability manager
- search xdr alerts
- xdr
- list xsiam endpoints with filters.
- xpanse list ip ranges
- sase
- get extra data for a specific xdr incident.
- soc analyst
- researches threat actors, malware campaigns, and vulnerability trends.
- monitors and remediates cloud security misconfigurations and compliance violations.
- search endpoints
- xdr list endpoints
- xdr scan endpoints
- digital experience monitoring, log management, and best practice assessment.
- soar
- xpanse get audit logs
- run script
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- xdr list alerts
- xsoar create investigation
- search for available integrations in cortex xsoar.
- search xpanse incidents with filters.
- list playbooks
- run xsoar playbooks.
- get xpanse audit logs
- xpanse update incident
- search for integration instances in cortex xsoar.
- search attack surface rules
- xsiam list assets
- detection and response
- xsoar create incident
- xdr get script results
- get xsiam management logs.
- xdr run script
- search attack surface rules.
- xpanse list services
- sd wan operator
- search xsiam endpoints.
- xpanse get asset details
- secures ai applications with runtime scanning and vulnerability assessment.
- update an xpanse incident.
- list xsiam alerts with optional filters and pagination.
- investigates security incidents, triages alerts, and coordinates response actions.
- network architect
- xdr start xql query
- iam admin
- update an xdr incident.
- search xsiam alerts
- saas security admin
- xpanse list incidents
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- configure a datasource for xsiam ingestion.
- search xdr incidents with filters.
- list xdr alerts with optional filters, pagination, and sorting.
- get xql query results from xsiam.
- xsoar add entry
- list available playbooks in cortex xsoar.
- get incident details
- run a playbook on an investigation in xsoar.
- xsoar search integration instances
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- browser security admin
- unisolate endpoints
- isolate endpoints from the network via xdr.
- get or update a specific incident.
- isolate endpoints.
- network operations
- ai security engineer
- secure access service edge with remote networking, sd-wan, and zero trust access.
- threat intelligence
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- designs sase and sd-wan network architectures for secure remote access.
- update xpanse incident
- get internet exposure details for specific assets from xpanse.
- xsoar get investigation
- enterprise it
- incident response
- get asset details
- update an existing incident in cortex xsoar.
- cybersecurity
- xsiam list incidents
- search xsiam endpoints
- search xsiam incidents.
- soc
- xsoar list playbooks
- get xql query results
- update an attack surface rule.
- scan endpoints.
- list and manage xsoar playbooks.
- xdr get xql results
- xpanse list exposed assets
- compliance officer
- xsiam get xql results
- list xsiam assets with filters.
- create an incident in xsoar.
- list xdr incidents with optional filters, pagination, and sorting.
- start xql queries on xdr.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- xsiam list endpoints
- scan endpoints
- unisolate endpoints.
- add an entry to an investigation in cortex xsoar.
- retrieve a specific incident by id from cortex xsoar.
- search xsiam assets.
- search integration instances
- retrieve a specific investigation by id from xsoar.
- initiate a scan on endpoints via xdr.
- search owned ip ranges.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- initiate a scan on endpoints.
- get exposed services from xpanse.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- xdr get incident details
- network security engineer
- get investigation
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- search internet-exposed assets.
- xpanse list attack surface rules
- search ip ranges
- platform engineer
- search xsiam incidents
- designs and implements network security architectures and policies.
- list xsiam assets with optional filters.
- manages multi-tenant hierarchies and service group configurations for mssps.
- analyzes suspicious files and samples for malware characteristics.
- search exposed services.
- xsiam start xql query
- run a script on endpoints.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- update incident
- search xsiam alerts.
- get attack surface rules from xpanse.
- add entries to investigations.
- firewall policy management, network objects, and cloud-native firewall configuration.
- list xsiam incidents with optional filters and pagination.
- start xql query
- start xql queries on xsiam.
- search services
- xsiam get management logs
- configure datasource
- threat intel analyst
- firewall admin
- threat hunter
- identity and access management, tenant hierarchies, and subscription management.
- malware researcher
- cloud security engineer
- get xdr audit logs.
- search for available integrations in xsoar.
- get details for a specific exposed asset.
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
