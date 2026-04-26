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
- compliance officer
- xdr get xql results
- xpanse list incidents
- add an entry to an investigation in xsoar.
- xpanse update attack surface rule
- vulnerability manager
- run xsoar playbooks.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- get audit management logs from xdr.
- threat intelligence
- run a script on endpoints via xdr.
- xdr unisolate endpoints
- xpanse get audit logs
- get exposed services from xpanse.
- incident response
- isolate endpoints.
- search ip ranges
- list and manage xsoar playbooks.
- analyzes suspicious files and samples for malware characteristics.
- monitors network health, performance, and digital experience metrics.
- xsoar search integrations
- get xpanse audit logs.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- firewall
- xdr
- isolate endpoints from the network.
- get extra data for a specific xdr incident.
- create xsoar investigations.
- get xql query results from xsiam.
- get management logs from xsiam.
- search exposed services.
- incident responder
- manage enterprise browser policies, user sessions, and deployments.
- soc
- start xql queries on xsiam.
- xdr run script
- add an entry to an investigation in cortex xsoar.
- add entries to investigations.
- get xsiam management logs.
- xpanse list ip ranges
- subscription manager
- threat intel analyst
- list xdr incidents.
- list xdr endpoints with optional filters, pagination, and sorting.
- xsoar get investigation
- start xsiam xql query
- search integrations
- soc analyst
- tenant operator
- ai runtime security scanning and automated red teaming for ai applications.
- search xsiam alerts with filters.
- soar
- secures ai applications with runtime scanning and vulnerability assessment.
- get xsiam management logs
- xdr get script results
- secure access service edge with remote networking, sd-wan, and zero trust access.
- run playbook
- enterprise browser policy management and secure browsing.
- get incident details
- search endpoints
- enterprise it
- xdr list endpoints
- xpanse list services
- update an existing incident in cortex xsoar.
- network security engineer
- xsoar update incident
- list available playbooks in cortex xsoar.
- xpanse list attack surface rules
- sase admin
- search xsiam incidents.
- run scripts on endpoints.
- list xsiam alerts with optional filters and pagination.
- investigates dlp incidents and manages sensitive data protection policies.
- xpanse list exposed assets
- get details for a specific exposed asset.
- xsiam get xql results
- manages multi-tenant hierarchies and service group configurations for mssps.
- search xsoar integrations.
- search xdr endpoints.
- search for available integrations in xsoar.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- search xsiam assets
- search xsiam incidents
- search xsiam endpoints.
- data loss prevention, saas security monitoring, and identity security posture.
- malware researcher
- xsiam list incidents
- cloud security
- ai security engineer
- get owned ip ranges from xpanse.
- configure a datasource for xsiam ingestion.
- firewall policy management, network objects, and cloud-native firewall configuration.
- xdr list alerts
- list xdr alerts with optional filters, pagination, and sorting.
- run script
- compliance team
- search xdr alerts.
- xsiam configure datasource
- sre
- search for integration instances in cortex xsoar.
- conducts automated adversarial testing against ai systems and llm applications.
- list incidents
- create an incident in xsoar.
- detection and response
- get investigation
- create a new incident in cortex xsoar.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- manages multi-tenant security operations at scale for managed service providers.
- unisolate endpoints.
- data protection analyst
- unisolate endpoints and restore network connectivity via xdr.
- create investigation
- start xql query
- list xsiam endpoints with optional filters.
- update xpanse incident
- xpanse update incident
- run a playbook on an investigation in xsoar.
- search exposed assets
- get xpanse incidents.
- isolate endpoints from the network via xdr.
- run a playbook on an investigation in cortex xsoar.
- xdr scan endpoints
- sase
- unisolate endpoints
- security operations
- update an xdr incident.
- xsoar run playbook
- manages enterprise browser policies and secure browsing configurations.
- identity and access management, tenant hierarchies, and subscription management.
- list xsiam assets with filters.
- search incidents with filters in cortex xsoar.
- xsoar get incident
- list playbooks
- create a new investigation in xsoar.
- initiate a scan on endpoints via xdr.
- xsoar search integration instances
- monitors and remediates cloud security misconfigurations and compliance violations.
- get a specific investigation.
- search xsoar integration instances.
- configure datasource
- xsiam list assets
- get incident details from xdr.
- search xsiam alerts
- run a script on endpoints.
- manages service accounts, roles, and access policies for platform api access.
- search xpanse incidents with filters.
- list available playbooks in xsoar.
- get xql query results
- search xdr alerts
- create a new investigation in cortex xsoar.
- unisolate endpoints and restore network connectivity.
- red team operator
- researches threat actors, malware campaigns, and vulnerability trends.
- iam admin
- search incidents with filters.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- xdr get incident details
- list xsiam assets with optional filters.
- cloud security engineer
- xsoar create investigation
- manages logging infrastructure, integrations, and platform automation.
- start an xql query on xsiam.
- search services
- mssp operator
- scan endpoints.
- get xdr audit logs
- search for integration instances in xsoar.
- investigates security incidents, triages alerts, and coordinates response actions.
- palo alto networks
- network security
- add entry
- search integration instances
- xsoar list playbooks
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- search internet-exposed assets.
- list xdr endpoints with filters.
- proactively searches for threats and iocs across telemetry data.
- xdr get audit logs
- search xpanse incidents.
- retrieve a specific incident by id from cortex xsoar.
- search xsiam endpoints
- get internet exposure details for specific assets from xpanse.
- get audit management logs from xpanse.
- executes containment, eradication, and recovery actions during security incidents.
- cloud security posture management, compliance monitoring, and workload protection.
- start an xql query on xdr.
- get xsiam xql query results
- xdr start xql query
- threat hunter
- get asset details
- create incident
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- get script results
- network operations
- get xpanse audit logs
- search incidents
- designs and implements network security architectures and policies.
- saas security admin
- list xdr incidents with optional filters, pagination, and sorting.
- initiate a scan on endpoints.
- update an attack surface rule.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- configure xsiam datasources.
- digital experience monitoring, log management, and best practice assessment.
- search for available integrations in cortex xsoar.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- get script execution results from xdr.
- xpanse get asset details
- update an xpanse incident.
- search xsiam assets.
- xdr list incidents
- search owned ip ranges.
- get xdr audit logs.
- update an attack surface rule in xpanse.
- designs sase and sd-wan network architectures for secure remote access.
- get or update a specific incident.
- network architect
- browser security admin
- cybersecurity
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- get xql query results from xdr.
- list xsiam endpoints with filters.
- get attack surface rules from xpanse.
- update attack surface rule
- search attack surface rules
- xsoar search incidents
- search xsiam alerts.
- retrieve a specific investigation by id from cortex xsoar.
- incident management — list, search, create, and update incidents.
- update incident
- xsoar create incident
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- firewall admin
- search attack surface rules.
- xsiam get management logs
- list xsiam incidents with optional filters and pagination.
- xsiam start xql query
- search xsiam incidents with filters.
- search xpanse incidents
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- isolate endpoints
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- search xdr incidents with filters.
- xdr update incident
- xsoar add entry
- get internet-exposed assets from xpanse.
- xsiam list alerts
- xdr isolate endpoints
- sd wan operator
- get script execution results.
- platform engineer
- search xdr alerts with filters.
- retrieve a specific investigation by id from xsoar.
- scan endpoints
- xsiam list endpoints
- start xql queries on xdr.
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
