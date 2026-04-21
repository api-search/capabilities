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
- xsoar update incident
- investigates dlp incidents and manages sensitive data protection policies.
- ai security engineer
- list playbooks
- get investigation
- manages logging infrastructure, integrations, and platform automation.
- search xsoar integration instances.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- xpanse list ip ranges
- list available playbooks in cortex xsoar.
- get xdr audit logs.
- unisolate endpoints and restore network connectivity.
- xsoar create incident
- firewall policy management, network objects, and cloud-native firewall configuration.
- search xdr alerts with filters.
- search for available integrations in xsoar.
- threat hunter
- malware researcher
- get xpanse audit logs.
- get xsiam management logs
- search xsiam alerts
- retrieve a specific incident by id from cortex xsoar.
- xdr run script
- enterprise it
- cloud security posture management, compliance monitoring, and workload protection.
- xsiam start xql query
- get xsiam xql query results
- get xql query results from xdr.
- analyzes suspicious files and samples for malware characteristics.
- manages service accounts, roles, and access policies for platform api access.
- xsoar search integration instances
- xdr list alerts
- get a specific investigation.
- xsiam list incidents
- get xpanse incidents.
- search xpanse incidents.
- get extra data for a specific xdr incident.
- get or update a specific incident.
- digital experience monitoring, log management, and best practice assessment.
- xsoar create investigation
- get xpanse audit logs
- red team operator
- search xsiam endpoints.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- search xsiam alerts with filters.
- palo alto networks
- secures ai applications with runtime scanning and vulnerability assessment.
- list incidents
- start an xql query on xsiam.
- search endpoints
- cloud security
- get audit management logs from xpanse.
- get xql query results from xsiam.
- search attack surface rules
- create a new investigation in xsoar.
- run a playbook on an investigation in xsoar.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- cybersecurity
- xdr
- search xsiam incidents
- xdr list endpoints
- list xdr alerts with optional filters, pagination, and sorting.
- xsoar search integrations
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- sase admin
- xsiam get management logs
- search xsoar integrations.
- update an xdr incident.
- network architect
- data loss prevention, saas security monitoring, and identity security posture.
- run xsoar playbooks.
- list xsiam endpoints with filters.
- search internet-exposed assets.
- xpanse update incident
- create xsoar investigations.
- create a new incident in cortex xsoar.
- investigates security incidents, triages alerts, and coordinates response actions.
- subscription manager
- search xsiam assets.
- proactively searches for threats and iocs across telemetry data.
- xpanse list attack surface rules
- run script
- unisolate endpoints.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- isolate endpoints from the network.
- create a new investigation in cortex xsoar.
- browser security admin
- retrieve a specific investigation by id from cortex xsoar.
- get script execution results.
- update an attack surface rule in xpanse.
- run playbook
- sd wan operator
- xdr unisolate endpoints
- isolate endpoints.
- update attack surface rule
- list xdr incidents.
- start xsiam xql query
- start an xql query on xdr.
- list xdr endpoints with optional filters, pagination, and sorting.
- search attack surface rules.
- xsiam list endpoints
- search xsiam alerts.
- manage enterprise browser policies, user sessions, and deployments.
- monitors network health, performance, and digital experience metrics.
- start xql queries on xsiam.
- xpanse list services
- manages enterprise browser policies and secure browsing configurations.
- iam admin
- list xsiam assets with optional filters.
- list available playbooks in xsoar.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- designs and implements network security architectures and policies.
- get incident details
- soar
- scan endpoints.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- platform engineer
- executes containment, eradication, and recovery actions during security incidents.
- saas security admin
- xdr update incident
- xdr list incidents
- search for integration instances in xsoar.
- list xsiam endpoints with optional filters.
- search xpanse incidents with filters.
- get xsiam management logs.
- search xsiam assets
- create incident
- get incident details from xdr.
- search integration instances
- list xsiam alerts with optional filters and pagination.
- xpanse list exposed assets
- initiate a scan on endpoints.
- list xsiam incidents with optional filters and pagination.
- xdr get script results
- list xdr incidents with optional filters, pagination, and sorting.
- designs sase and sd-wan network architectures for secure remote access.
- run scripts on endpoints.
- search xdr alerts.
- xsiam list alerts
- search xsiam incidents.
- xdr isolate endpoints
- xdr scan endpoints
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- sre
- xdr get incident details
- update an existing incident in cortex xsoar.
- unisolate endpoints
- unisolate endpoints and restore network connectivity via xdr.
- xsoar run playbook
- get attack surface rules from xpanse.
- get internet exposure details for specific assets from xpanse.
- xpanse get audit logs
- list xdr endpoints with filters.
- update xpanse incident
- incident response
- search exposed assets
- search services
- get script execution results from xdr.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- configure a datasource for xsiam ingestion.
- isolate endpoints from the network via xdr.
- xsiam get xql results
- secure access service edge with remote networking, sd-wan, and zero trust access.
- threat intel analyst
- search incidents with filters.
- run a script on endpoints.
- detection and response
- xsoar add entry
- search for available integrations in cortex xsoar.
- firewall
- xpanse get asset details
- cloud security engineer
- threat intelligence
- enterprise browser policy management and secure browsing.
- search xdr alerts
- search incidents
- get internet-exposed assets from xpanse.
- retrieve a specific investigation by id from xsoar.
- incident management — list, search, create, and update incidents.
- list and manage xsoar playbooks.
- get xql query results
- xsoar get incident
- incident responder
- add entry
- conducts automated adversarial testing against ai systems and llm applications.
- xsiam configure datasource
- search xdr endpoints.
- manages multi-tenant security operations at scale for managed service providers.
- security operations
- configure xsiam datasources.
- mssp operator
- ai runtime security scanning and automated red teaming for ai applications.
- data protection analyst
- search for integration instances in cortex xsoar.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- create an incident in xsoar.
- list xsiam assets with filters.
- update an attack surface rule.
- scan endpoints
- xsoar list playbooks
- xdr get audit logs
- get xdr audit logs
- xpanse list incidents
- update incident
- search owned ip ranges.
- search xpanse incidents
- network security engineer
- xpanse update attack surface rule
- sase
- configure datasource
- isolate endpoints
- xsiam list assets
- run a script on endpoints via xdr.
- add an entry to an investigation in cortex xsoar.
- monitors and remediates cloud security misconfigurations and compliance violations.
- network security
- soc
- identity and access management, tenant hierarchies, and subscription management.
- xsoar search incidents
- get script results
- get asset details
- update an xpanse incident.
- search ip ranges
- manages multi-tenant hierarchies and service group configurations for mssps.
- get management logs from xsiam.
- get exposed services from xpanse.
- run a playbook on an investigation in cortex xsoar.
- vulnerability manager
- firewall admin
- search integrations
- start xql query
- search incidents with filters in cortex xsoar.
- soc analyst
- network operations
- start xql queries on xdr.
- create investigation
- xdr get xql results
- compliance team
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- search xsiam endpoints
- get details for a specific exposed asset.
- tenant operator
- get owned ip ranges from xpanse.
- get audit management logs from xdr.
- initiate a scan on endpoints via xdr.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- search xsiam incidents with filters.
- add an entry to an investigation in xsoar.
- xdr start xql query
- compliance officer
- search exposed services.
- researches threat actors, malware campaigns, and vulnerability trends.
- search xdr incidents with filters.
- xsoar get investigation
- add entries to investigations.
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
