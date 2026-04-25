---
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
- onboard app
- saas security
- list posture checks with optional filters.
- list saas assets
- list available applications in the catalog.
- list all sspm jira integrations.
- vulnerability manager
- sd wan operator
- enterprise browser policy management and secure browsing.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- designs and implements network security architectures and policies.
- firewall
- update dlp incident
- retrieve activity log for a specific user.
- compliance officer
- retrieve details for a specific saas security incident.
- manages enterprise browser policies and secure browsing configurations.
- list email incidents
- list saas users
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- update a specific saas security incident.
- data protection analyst
- update the status of an sspm posture check.
- retrieve log forwarding configuration settings.
- mssp operator
- retrieve a list of monitored saas assets.
- list jira integrations
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- executes containment, eradication, and recovery actions during security incidents.
- manage dlp incidents.
- get data pattern
- list available data patterns.
- create jira integration
- list app catalog
- retrieve a list of saas security incidents.
- monitors network health, performance, and digital experience metrics.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- manages service accounts, roles, and access policies for platform api access.
- get email recipients
- cybersecurity
- threat intelligence
- update a dlp incident.
- get data snippets for a specific dlp incident.
- malware researcher
- list users across saas applications.
- data loss prevention, saas security monitoring, and identity security posture.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- update email verdict
- analyzes suspicious files and samples for malware characteristics.
- list dlp incidents
- saas security admin
- list saas incidents
- designs sase and sd-wan network architectures for secure remote access.
- access email incident recipients.
- firewall admin
- secures ai applications with runtime scanning and vulnerability assessment.
- get log forwarding configuration settings.
- remove app
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- red team operator
- update posture check status.
- identity security posture
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- list posture checks
- sase
- get posture check
- ai runtime security scanning and automated red teaming for ai applications.
- manage sspm posture checks.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- network security engineer
- list connected saas applications.
- browser security admin
- list data patterns
- get a specific sspm posture check by id.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- list available dlp data patterns.
- tenant operator
- investigates dlp incidents and manages sensitive data protection policies.
- threat intel analyst
- get a specific posture check by id.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- list sspm posture checks with optional filters.
- sspm
- update a dlp incident status or assignee.
- get log forwarding settings
- create a new jira integration for sspm.
- list all onboarded saas applications.
- subscription manager
- list email dlp incidents with optional filters.
- list onboarded apps
- list dlp data patterns.
- network operations
- manages multi-tenant security operations at scale for managed service providers.
- cloud security
- update the verdict for an email dlp incident.
- identity and access management, tenant hierarchies, and subscription management.
- soar
- incident responder
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- get a specific data pattern.
- retrieve a specific dlp data pattern by id.
- soc analyst
- manage onboarded sspm applications.
- update posture check status
- list saas applications
- xdr
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- ai security engineer
- investigates security incidents, triages alerts, and coordinates response actions.
- retrieve a specific data pattern by id.
- access dlp incident data snippets.
- dlp
- data protection
- access dlp report summaries.
- get email attachments
- compliance team
- enterprise it
- list all jira integrations.
- cloud security engineer
- researches threat actors, malware campaigns, and vulnerability trends.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- get saas asset
- manages logging infrastructure, integrations, and platform automation.
- network security
- palo alto networks
- threat hunter
- list email dlp incidents.
- get dlp snippets
- retrieve a specific dlp incident by id.
- list saas security incidents with optional filters.
- monitors and remediates cloud security misconfigurations and compliance violations.
- access email incident attachments.
- get or update a specific saas security incident.
- remove an onboarded saas application from sspm.
- retrieve a list of users across saas applications.
- get user activities
- get a dlp summary report for a given time range.
- proactively searches for threats and iocs across telemetry data.
- retrieve a list of connected saas applications.
- manage email incident verdicts.
- manage saas security incidents.
- list dlp incidents with optional filters for severity and status.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get saas incident
- remove an onboarded saas application.
- remove an onboarded sspm application.
- get a specific posture check.
- list dlp incidents with optional filters.
- firewall policy management, network objects, and cloud-native firewall configuration.
- sase admin
- cloud security posture management, compliance monitoring, and workload protection.
- network architect
- get recipients for a specific email dlp incident.
- manage enterprise browser policies, user sessions, and deployments.
- onboard a new saas application in sspm.
- update saas incident
- get attachments for a specific email dlp incident.
- update the status of a posture check.
- manage sspm jira integrations.
- iam admin
- sre
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- digital experience monitoring, log management, and best practice assessment.
- list all onboarded saas applications in sspm.
- get a specific saas asset.
- get user activity log.
- onboard a new saas application.
- get dlp report summary
- get email incident
- get a specific email dlp incident.
- list monitored saas assets.
- create a new jira integration.
- list available applications in the sspm catalog.
- retrieve details for a specific saas asset.
- conducts automated adversarial testing against ai systems and llm applications.
- browse the sspm application catalog.
- retrieve a specific email dlp incident by id.
- get or update a specific dlp incident.
- platform engineer
- manages multi-tenant hierarchies and service group configurations for mssps.
- get dlp incident
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
