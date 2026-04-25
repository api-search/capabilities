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
- isolate endpoints from the network via xdr.
- update attack surface rule
- xsoar list playbooks
- search incidents
- scan endpoints.
- vulnerability manager
- configure datasource
- start xsiam xql query
- sd wan operator
- enterprise browser policy management and secure browsing.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- xpanse list exposed assets
- search xsiam assets.
- designs and implements network security architectures and policies.
- firewall
- xpanse list attack surface rules
- compliance officer
- get script results
- search xsiam incidents
- search attack surface rules.
- list xsiam alerts with optional filters and pagination.
- manages enterprise browser policies and secure browsing configurations.
- search xdr alerts.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- data protection analyst
- mssp operator
- create investigation
- isolate endpoints from the network.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- xsoar get incident
- xsiam get management logs
- run playbook
- executes containment, eradication, and recovery actions during security incidents.
- search for available integrations in cortex xsoar.
- retrieve a specific investigation by id from cortex xsoar.
- monitors network health, performance, and digital experience metrics.
- xdr get audit logs
- manages service accounts, roles, and access policies for platform api access.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- create xsoar investigations.
- search endpoints
- add an entry to an investigation in cortex xsoar.
- cybersecurity
- threat intelligence
- get incident details from xdr.
- get attack surface rules from xpanse.
- incident response
- malware researcher
- xpanse get audit logs
- data loss prevention, saas security monitoring, and identity security posture.
- xdr run script
- search xsiam assets
- run script
- xsiam start xql query
- list playbooks
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- analyzes suspicious files and samples for malware characteristics.
- search for available integrations in xsoar.
- get script execution results from xdr.
- search xsiam incidents with filters.
- get extra data for a specific xdr incident.
- start xql query
- saas security admin
- add entry
- get owned ip ranges from xpanse.
- platform engineer
- get a specific investigation.
- run scripts on endpoints.
- designs sase and sd-wan network architectures for secure remote access.
- configure a datasource for xsiam ingestion.
- firewall admin
- secures ai applications with runtime scanning and vulnerability assessment.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- red team operator
- get xpanse audit logs.
- run xsoar playbooks.
- search xsoar integrations.
- search ip ranges
- list xsiam endpoints with optional filters.
- xpanse list services
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- search xsiam alerts.
- search integration instances
- create a new incident in cortex xsoar.
- list xdr endpoints with optional filters, pagination, and sorting.
- list xdr endpoints with filters.
- xsoar add entry
- initiate a scan on endpoints via xdr.
- xsoar run playbook
- sase
- get xql query results from xdr.
- list xsiam incidents with optional filters and pagination.
- get audit management logs from xpanse.
- xdr get incident details
- get xdr audit logs.
- xsoar search integration instances
- list available playbooks in xsoar.
- search integrations
- ai runtime security scanning and automated red teaming for ai applications.
- search incidents with filters.
- xpanse get asset details
- list xsiam endpoints with filters.
- get script execution results.
- xdr unisolate endpoints
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- network security engineer
- browser security admin
- configure xsiam datasources.
- start xql queries on xdr.
- get investigation
- get xql query results from xsiam.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- xsiam list assets
- detection and response
- xdr list endpoints
- tenant operator
- xsiam list incidents
- investigates dlp incidents and manages sensitive data protection policies.
- threat intel analyst
- search for integration instances in xsoar.
- start an xql query on xsiam.
- get xsiam management logs.
- create an incident in xsoar.
- start an xql query on xdr.
- search exposed assets
- retrieve a specific incident by id from cortex xsoar.
- xdr list incidents
- xpanse update incident
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- search internet-exposed assets.
- get xql query results
- unisolate endpoints.
- search services
- xsiam get xql results
- subscription manager
- search xsiam incidents.
- manages multi-tenant security operations at scale for managed service providers.
- network operations
- get xpanse incidents.
- cloud security
- xpanse update attack surface rule
- search attack surface rules
- identity and access management, tenant hierarchies, and subscription management.
- soar
- get asset details
- search xdr endpoints.
- run a script on endpoints via xdr.
- incident responder
- update an existing incident in cortex xsoar.
- search xdr incidents with filters.
- update xpanse incident
- xdr get xql results
- search for integration instances in cortex xsoar.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- xdr isolate endpoints
- get audit management logs from xdr.
- search owned ip ranges.
- soc analyst
- update an attack surface rule in xpanse.
- isolate endpoints.
- get xsiam management logs
- xdr
- get or update a specific incident.
- add entries to investigations.
- unisolate endpoints
- search xsiam endpoints
- get management logs from xsiam.
- update incident
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- get xpanse audit logs
- search xsiam alerts
- xdr update incident
- ai security engineer
- investigates security incidents, triages alerts, and coordinates response actions.
- get details for a specific exposed asset.
- xsoar create investigation
- xsiam configure datasource
- list xsiam assets with filters.
- create a new investigation in cortex xsoar.
- incident management — list, search, create, and update incidents.
- update an xpanse incident.
- search exposed services.
- compliance team
- enterprise it
- xdr get script results
- cloud security engineer
- researches threat actors, malware campaigns, and vulnerability trends.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- get internet exposure details for specific assets from xpanse.
- search xpanse incidents
- xdr list alerts
- manages logging infrastructure, integrations, and platform automation.
- network security
- palo alto networks
- threat hunter
- search xsiam endpoints.
- search xpanse incidents with filters.
- get incident details
- add an entry to an investigation in xsoar.
- get internet-exposed assets from xpanse.
- xsiam list alerts
- xpanse list incidents
- monitors and remediates cloud security misconfigurations and compliance violations.
- list xdr incidents.
- proactively searches for threats and iocs across telemetry data.
- run a script on endpoints.
- xpanse list ip ranges
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- scan endpoints
- list xdr incidents with optional filters, pagination, and sorting.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- xsoar create incident
- list available playbooks in cortex xsoar.
- firewall policy management, network objects, and cloud-native firewall configuration.
- get xsiam xql query results
- run a playbook on an investigation in xsoar.
- soc
- update an attack surface rule.
- sase admin
- cloud security posture management, compliance monitoring, and workload protection.
- network architect
- initiate a scan on endpoints.
- update an xdr incident.
- xdr scan endpoints
- security operations
- unisolate endpoints and restore network connectivity.
- get xdr audit logs
- xsoar update incident
- manage enterprise browser policies, user sessions, and deployments.
- list xdr alerts with optional filters, pagination, and sorting.
- iam admin
- get exposed services from xpanse.
- search incidents with filters in cortex xsoar.
- xsoar get investigation
- sre
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- digital experience monitoring, log management, and best practice assessment.
- unisolate endpoints and restore network connectivity via xdr.
- create incident
- list and manage xsoar playbooks.
- search xpanse incidents.
- xsiam list endpoints
- start xql queries on xsiam.
- xdr start xql query
- conducts automated adversarial testing against ai systems and llm applications.
- search xsiam alerts with filters.
- run a playbook on an investigation in cortex xsoar.
- xsoar search integrations
- search xsoar integration instances.
- isolate endpoints
- list incidents
- create a new investigation in xsoar.
- xsoar search incidents
- list xsiam assets with optional filters.
- search xdr alerts with filters.
- manages multi-tenant hierarchies and service group configurations for mssps.
- retrieve a specific investigation by id from xsoar.
- search xdr alerts
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
