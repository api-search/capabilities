---
categories: []
consumed_apis:
- dlp
- email-dlp
- saas-security
- sspm
- identity-security-posture
description: Unified data protection capability for managing DLP incidents, email DLP events, SaaS security incidents and assets, and SaaS security posture checks across Enterprise DLP, Email DLP, SaaS Security, and SSPM APIs.
layout: capability
name: Palo Alto Networks Data Protection
operations:
- description: List DLP incidents with optional filters.
  method: GET
  name: list-dlp-incidents
  path: /v1/dlp-incidents
- description: Retrieve a specific DLP incident by ID.
  method: GET
  name: get-dlp-incident
  path: /v1/dlp-incidents/{incident_id}
- description: Update a DLP incident.
  method: PUT
  name: update-dlp-incident
  path: /v1/dlp-incidents/{incident_id}
- description: Get data snippets for a specific DLP incident.
  method: GET
  name: get-dlp-snippets
  path: /v1/dlp-incidents/{incident_id}/snippets
- description: List available data patterns.
  method: GET
  name: list-data-patterns
  path: /v1/data-patterns
- description: Retrieve a specific data pattern by ID.
  method: GET
  name: get-data-pattern
  path: /v1/data-patterns/{pattern_id}
- description: Get a DLP summary report for a given time range.
  method: GET
  name: get-dlp-report-summary
  path: /v1/dlp-reports/summary
- description: List email DLP incidents with optional filters.
  method: GET
  name: list-email-incidents
  path: /v1/email-incidents
- description: Retrieve a specific email DLP incident by ID.
  method: GET
  name: get-email-incident
  path: /v1/email-incidents/{incident_id}
- description: Update the verdict for an email DLP incident.
  method: PUT
  name: update-email-verdict
  path: /v1/email-incidents/{incident_id}/verdict
- description: Get attachments for a specific email DLP incident.
  method: GET
  name: get-email-attachments
  path: /v1/email-incidents/{incident_id}/attachments
- description: Get recipients for a specific email DLP incident.
  method: GET
  name: get-email-recipients
  path: /v1/email-incidents/{incident_id}/recipients
- description: List SaaS security incidents with optional filters.
  method: GET
  name: list-saas-incidents
  path: /v1/saas-incidents
- description: Retrieve details for a specific SaaS security incident.
  method: GET
  name: get-saas-incident
  path: /v1/saas-incidents/{incident_id}
- description: Update a specific SaaS security incident.
  method: PUT
  name: update-saas-incident
  path: /v1/saas-incidents/{incident_id}
- description: Retrieve a list of monitored SaaS assets.
  method: GET
  name: list-saas-assets
  path: /v1/saas-assets
- description: Retrieve details for a specific SaaS asset.
  method: GET
  name: get-saas-asset
  path: /v1/saas-assets/{asset_id}
- description: Retrieve a list of connected SaaS applications.
  method: GET
  name: list-saas-applications
  path: /v1/saas-applications
- description: Retrieve a list of users across SaaS applications.
  method: GET
  name: list-saas-users
  path: /v1/saas-users
- description: Retrieve activity log for a specific user.
  method: GET
  name: get-user-activities
  path: /v1/saas-users/{user_id}/activities
- description: Retrieve log forwarding configuration settings.
  method: GET
  name: get-log-forwarding-settings
  path: /v1/log-forwarding-settings
- description: List all onboarded SaaS applications.
  method: GET
  name: list-onboarded-apps
  path: /v1/sspm-apps
- description: Onboard a new SaaS application.
  method: POST
  name: onboard-app
  path: /v1/sspm-apps
- description: Remove an onboarded SaaS application.
  method: DELETE
  name: remove-app
  path: /v1/sspm-apps/{app_id}
- description: List posture checks with optional filters.
  method: GET
  name: list-posture-checks
  path: /v1/posture-checks
- description: Get a specific posture check by ID.
  method: GET
  name: get-posture-check
  path: /v1/posture-checks/{check_id}
- description: Update the status of a posture check.
  method: PUT
  name: update-posture-check-status
  path: /v1/posture-checks/{check_id}/status
- description: List available applications in the catalog.
  method: GET
  name: list-app-catalog
  path: /v1/sspm-app-catalog
- description: List all Jira integrations.
  method: GET
  name: list-jira-integrations
  path: /v1/jira-integrations
- description: Create a new Jira integration.
  method: POST
  name: create-jira-integration
  path: /v1/jira-integrations
personas:
- description: Investigates DLP incidents and manages sensitive data protection policies.
  id: data-protection-analyst
  name: Data Protection Analyst
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- threat intel analyst
- analyzes suspicious files and samples for malware characteristics.
- retrieve log forwarding configuration settings.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- manage email incident verdicts.
- list all sspm jira integrations.
- browse the sspm application catalog.
- enterprise browser policy management and secure browsing.
- get a specific email dlp incident.
- compliance team
- access dlp incident data snippets.
- conducts automated adversarial testing against ai systems and llm applications.
- manage sspm jira integrations.
- browser security admin
- get posture check
- get user activity log.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- create jira integration
- list saas applications
- get a specific posture check.
- list saas users
- sre
- cloud security posture management, compliance monitoring, and workload protection.
- designs sase and sd-wan network architectures for secure remote access.
- ai runtime security scanning and automated red teaming for ai applications.
- list email dlp incidents.
- saas security admin
- get dlp snippets
- onboard a new saas application.
- list dlp data patterns.
- retrieve a list of connected saas applications.
- get email incident
- list email dlp incidents with optional filters.
- get user activities
- update the status of a posture check.
- firewall admin
- get saas asset
- platform engineer
- remove an onboarded saas application from sspm.
- update posture check status
- researches threat actors, malware campaigns, and vulnerability trends.
- update email verdict
- red team operator
- sd wan operator
- manages multi-tenant hierarchies and service group configurations for mssps.
- list available dlp data patterns.
- network security engineer
- list jira integrations
- monitors network health, performance, and digital experience metrics.
- get recipients for a specific email dlp incident.
- get a specific sspm posture check by id.
- cloud security
- mssp operator
- investigates security incidents, triages alerts, and coordinates response actions.
- list available applications in the sspm catalog.
- cloud security engineer
- list all onboarded saas applications.
- manage sspm posture checks.
- get data snippets for a specific dlp incident.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- list saas security incidents with optional filters.
- list all onboarded saas applications in sspm.
- get log forwarding settings
- firewall
- get email attachments
- threat hunter
- get dlp incident
- update a specific saas security incident.
- secures ai applications with runtime scanning and vulnerability assessment.
- retrieve a list of users across saas applications.
- list saas assets
- network operations
- network security
- data protection analyst
- list all jira integrations.
- enterprise it
- update saas incident
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- soc analyst
- retrieve a list of monitored saas assets.
- network architect
- remove an onboarded saas application.
- access dlp report summaries.
- sspm
- list dlp incidents with optional filters.
- get data pattern
- get or update a specific saas security incident.
- list available applications in the catalog.
- retrieve details for a specific saas asset.
- get a specific data pattern.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- saas security
- update the verdict for an email dlp incident.
- get a specific posture check by id.
- get a dlp summary report for a given time range.
- tenant operator
- manage enterprise browser policies, user sessions, and deployments.
- dlp
- list users across saas applications.
- update the status of an sspm posture check.
- update dlp incident
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- retrieve a specific email dlp incident by id.
- retrieve details for a specific saas security incident.
- list connected saas applications.
- ai security engineer
- get dlp report summary
- list dlp incidents
- proactively searches for threats and iocs across telemetry data.
- sase admin
- get email recipients
- retrieve activity log for a specific user.
- manage saas security incidents.
- investigates dlp incidents and manages sensitive data protection policies.
- monitors and remediates cloud security misconfigurations and compliance violations.
- update a dlp incident.
- subscription manager
- onboard app
- remove app
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- list email incidents
- access email incident recipients.
- firewall policy management, network objects, and cloud-native firewall configuration.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- create a new jira integration for sspm.
- update a dlp incident status or assignee.
- retrieve a list of saas security incidents.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- iam admin
- palo alto networks
- retrieve a specific dlp data pattern by id.
- malware researcher
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- get attachments for a specific email dlp incident.
- list monitored saas assets.
- remove an onboarded sspm application.
- soar
- list app catalog
- threat intelligence
- get a specific saas asset.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- sase
- manages multi-tenant security operations at scale for managed service providers.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- identity security posture
- list posture checks with optional filters.
- incident responder
- manages service accounts, roles, and access policies for platform api access.
- list posture checks
- vulnerability manager
- list sspm posture checks with optional filters.
- get or update a specific dlp incident.
- cybersecurity
- get saas incident
- list available data patterns.
- digital experience monitoring, log management, and best practice assessment.
- list data patterns
- manage onboarded sspm applications.
- retrieve a specific dlp incident by id.
- list onboarded apps
- list dlp incidents with optional filters for severity and status.
- list saas incidents
- manages logging infrastructure, integrations, and platform automation.
- xdr
- get log forwarding configuration settings.
- executes containment, eradication, and recovery actions during security incidents.
- compliance officer
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- access email incident attachments.
- designs and implements network security architectures and policies.
- identity and access management, tenant hierarchies, and subscription management.
- data protection
- manages enterprise browser policies and secure browsing configurations.
- data loss prevention, saas security monitoring, and identity security posture.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- retrieve a specific data pattern by id.
- onboard a new saas application in sspm.
- create a new jira integration.
- update posture check status.
- manage dlp incidents.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
slug: data-protection
tags:
- Palo Alto Networks
- Data Protection
- DLP
- SaaS Security
- SSPM
- Identity Security Posture
tools:
- description: List DLP incidents with optional filters for severity and status.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-dlp-incidents
- description: Retrieve a specific DLP incident by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-dlp-incident
- description: Update a DLP incident status or assignee.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-dlp-incident
- description: Get data snippets for a specific DLP incident.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-dlp-snippets
- description: List available DLP data patterns.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-data-patterns
- description: Retrieve a specific DLP data pattern by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-data-pattern
- description: Get a DLP summary report for a given time range.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-dlp-report-summary
- description: List email DLP incidents with optional filters.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-email-incidents
- description: Retrieve a specific email DLP incident by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-email-incident
- description: Update the verdict for an email DLP incident.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-email-verdict
- description: Get attachments for a specific email DLP incident.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-email-attachments
- description: Get recipients for a specific email DLP incident.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-email-recipients
- description: Retrieve a list of SaaS security incidents.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-saas-incidents
- description: Retrieve details for a specific SaaS security incident.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-saas-incident
- description: Update a specific SaaS security incident.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-saas-incident
- description: Retrieve a list of monitored SaaS assets.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-saas-assets
- description: Retrieve details for a specific SaaS asset.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-saas-asset
- description: Retrieve a list of connected SaaS applications.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-saas-applications
- description: Retrieve a list of users across SaaS applications.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-saas-users
- description: Retrieve activity log for a specific user.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-user-activities
- description: Retrieve log forwarding configuration settings.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-log-forwarding-settings
- description: List all onboarded SaaS applications in SSPM.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-onboarded-apps
- description: Onboard a new SaaS application in SSPM.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: onboard-app
- description: Remove an onboarded SaaS application from SSPM.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: remove-app
- description: List SSPM posture checks with optional filters.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-posture-checks
- description: Get a specific SSPM posture check by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-posture-check
- description: Update the status of an SSPM posture check.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-posture-check-status
- description: List available applications in the SSPM catalog.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-app-catalog
- description: List all SSPM Jira integrations.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-jira-integrations
- description: Create a new Jira integration for SSPM.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-jira-integration
---
