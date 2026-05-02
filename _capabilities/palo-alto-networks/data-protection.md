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
- soc analyst
- list dlp data patterns.
- list available dlp data patterns.
- retrieve a list of users across saas applications.
- xdr
- get saas asset
- get dlp incident
- firewall admin
- list app catalog
- get saas incident
- monitors network health, performance, and digital experience metrics.
- data protection
- update a specific saas security incident.
- update a dlp incident.
- get a specific email dlp incident.
- manages multi-tenant hierarchies and service group configurations for mssps.
- retrieve a list of connected saas applications.
- manages enterprise browser policies and secure browsing configurations.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get data snippets for a specific dlp incident.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- get a specific posture check.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- saas security
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- list available data patterns.
- threat hunter
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- remove an onboarded sspm application.
- iam admin
- onboard app
- list saas assets
- create jira integration
- retrieve a specific dlp incident by id.
- update posture check status.
- get a specific data pattern.
- list data patterns
- sre
- designs sase and sd-wan network architectures for secure remote access.
- vulnerability manager
- remove app
- network operations
- get dlp report summary
- conducts automated adversarial testing against ai systems and llm applications.
- access email incident attachments.
- get or update a specific dlp incident.
- get user activities
- cloud security engineer
- retrieve a list of saas security incidents.
- get dlp snippets
- cybersecurity
- compliance officer
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- identity and access management, tenant hierarchies, and subscription management.
- retrieve activity log for a specific user.
- list email dlp incidents with optional filters.
- manage sspm posture checks.
- saas security admin
- list saas security incidents with optional filters.
- list saas applications
- enterprise it
- retrieve a specific dlp data pattern by id.
- sspm
- secures ai applications with runtime scanning and vulnerability assessment.
- researches threat actors, malware campaigns, and vulnerability trends.
- remove an onboarded saas application from sspm.
- retrieve details for a specific saas security incident.
- retrieve a list of monitored saas assets.
- list email incidents
- network security engineer
- cloud security
- list jira integrations
- platform engineer
- list all onboarded saas applications in sspm.
- list dlp incidents
- list dlp incidents with optional filters.
- mssp operator
- get or update a specific saas security incident.
- dlp
- get recipients for a specific email dlp incident.
- update the verdict for an email dlp incident.
- list posture checks with optional filters.
- list email dlp incidents.
- list saas incidents
- update dlp incident
- update the status of an sspm posture check.
- manages logging infrastructure, integrations, and platform automation.
- identity security posture
- ai runtime security scanning and automated red teaming for ai applications.
- analyzes suspicious files and samples for malware characteristics.
- data protection analyst
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- sase
- list sspm posture checks with optional filters.
- list all sspm jira integrations.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- update the status of a posture check.
- investigates security incidents, triages alerts, and coordinates response actions.
- get a specific sspm posture check by id.
- compliance team
- update saas incident
- subscription manager
- red team operator
- designs and implements network security architectures and policies.
- threat intel analyst
- incident responder
- proactively searches for threats and iocs across telemetry data.
- executes containment, eradication, and recovery actions during security incidents.
- get email recipients
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- firewall
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- ai security engineer
- get a specific saas asset.
- create a new jira integration.
- get email attachments
- digital experience monitoring, log management, and best practice assessment.
- get a specific posture check by id.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- manage enterprise browser policies, user sessions, and deployments.
- get log forwarding configuration settings.
- list onboarded apps
- data loss prevention, saas security monitoring, and identity security posture.
- access dlp report summaries.
- update a dlp incident status or assignee.
- create a new jira integration for sspm.
- manages multi-tenant security operations at scale for managed service providers.
- firewall policy management, network objects, and cloud-native firewall configuration.
- manages service accounts, roles, and access policies for platform api access.
- list monitored saas assets.
- list available applications in the catalog.
- list dlp incidents with optional filters for severity and status.
- update email verdict
- secure access service edge with remote networking, sd-wan, and zero trust access.
- retrieve a specific data pattern by id.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- list users across saas applications.
- access dlp incident data snippets.
- retrieve log forwarding configuration settings.
- browse the sspm application catalog.
- onboard a new saas application in sspm.
- malware researcher
- palo alto networks
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- manage saas security incidents.
- get email incident
- retrieve details for a specific saas asset.
- list connected saas applications.
- get user activity log.
- enterprise browser policy management and secure browsing.
- network security
- get log forwarding settings
- list posture checks
- network architect
- get data pattern
- monitors and remediates cloud security misconfigurations and compliance violations.
- get a dlp summary report for a given time range.
- remove an onboarded saas application.
- investigates dlp incidents and manages sensitive data protection policies.
- soar
- retrieve a specific email dlp incident by id.
- manage dlp incidents.
- sd wan operator
- list available applications in the sspm catalog.
- threat intelligence
- browser security admin
- update posture check status
- tenant operator
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- access email incident recipients.
- onboard a new saas application.
- manage sspm jira integrations.
- list saas users
- sase admin
- list all jira integrations.
- list all onboarded saas applications.
- manage onboarded sspm applications.
- get posture check
- cloud security posture management, compliance monitoring, and workload protection.
- get attachments for a specific email dlp incident.
- manage email incident verdicts.
slug: data-protection
source_filename: data-protection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Palo Alto Networks Data Protection\"\n  description: \"Unified data protection capability for managing DLP incidents, email DLP events, SaaS security incidents and assets, and SaaS security posture checks across Enterprise DLP, Email DLP, SaaS Security, and SSPM APIs.\"\n  tags:\n    - Palo Alto Networks\n    - Data Protection\n    - DLP\n    - SaaS Security\n    - SSPM\n    - Identity Security Posture\n  created: \"2026-04-16\"\n  modified: \"2026-04-16\"\n\nbinds:\n  - namespace: env\n    keys:\n      PALO_ALTO_DLP_TOKEN: PALO_ALTO_DLP_TOKEN\n      SAAS_SECURITY_TOKEN: SAAS_SECURITY_TOKEN\n      PALO_ALTO_OAUTH_TOKEN: PALO_ALTO_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: dlp\n      location: ./shared/dlp.yaml\n    - import: email-dlp\n      location: ./shared/email-dlp.yaml\n    - import: saas-security\n      location: ./shared/saas-security.yaml\n    - import: sspm\n      location: ./shared/sspm.yaml\n    - import:\
  \ identity-security-posture\n      location: ./shared/identity-security-posture.yaml\n\n  exposes:\n    - type: rest\n      port: 8085\n      namespace: data-protection-api\n      description: \"Unified REST API for data protection workflows across Enterprise DLP, Email DLP, SaaS Security, and SSPM.\"\n      resources:\n\n        # -------------------------------------------------------\n        # DLP Incidents\n        # -------------------------------------------------------\n        - path: /v1/dlp-incidents\n          name: dlp-incidents\n          description: \"Manage DLP incidents.\"\n          operations:\n            - method: GET\n              name: list-dlp-incidents\n              description: \"List DLP incidents with optional filters.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n               \
  \   type: integer\n                  required: false\n                - name: severity\n                  in: query\n                  type: string\n                  required: false\n                - name: status\n                  in: query\n                  type: string\n                  required: false\n              call: \"dlp-api.list-incidents\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n                severity: \"rest.severity\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/dlp-incidents/{incident_id}\n          name: dlp-incident-detail\n          description: \"Get or update a specific DLP incident.\"\n          operations:\n            - method: GET\n              name: get-dlp-incident\n              description: \"Retrieve a specific DLP incident by ID.\"\n              inputParameters:\n     \
  \           - name: incident_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"dlp-api.get-incident\"\n              with:\n                incident_id: \"rest.incident_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: PUT\n              name: update-dlp-incident\n              description: \"Update a DLP incident.\"\n              inputParameters:\n                - name: incident_id\n                  in: path\n                  type: string\n                  required: true\n                - name: status\n                  in: body\n                  type: string\n                  required: false\n                - name: assignee\n                  in: body\n                  type: string\n                  required: false\n              call: \"dlp-api.update-incident\"\n              with:\n                incident_id: \"rest.incident_id\"\
  \n                status: \"rest.status\"\n                assignee: \"rest.assignee\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/dlp-incidents/{incident_id}/snippets\n          name: dlp-incident-snippets\n          description: \"Access DLP incident data snippets.\"\n          operations:\n            - method: GET\n              name: get-dlp-snippets\n              description: \"Get data snippets for a specific DLP incident.\"\n              inputParameters:\n                - name: incident_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"dlp-api.get-incident-snippets\"\n              with:\n                incident_id: \"rest.incident_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # DLP Data Patterns\n\
  \        # -------------------------------------------------------\n        - path: /v1/data-patterns\n          name: data-patterns\n          description: \"List DLP data patterns.\"\n          operations:\n            - method: GET\n              name: list-data-patterns\n              description: \"List available data patterns.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"dlp-api.list-data-patterns\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/data-patterns/{pattern_id}\n          name: data-pattern-detail\n          description: \"Get a specific\
  \ data pattern.\"\n          operations:\n            - method: GET\n              name: get-data-pattern\n              description: \"Retrieve a specific data pattern by ID.\"\n              inputParameters:\n                - name: pattern_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"dlp-api.get-data-pattern\"\n              with:\n                id: \"rest.pattern_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # DLP Reports\n        # -------------------------------------------------------\n        - path: /v1/dlp-reports/summary\n          name: dlp-report-summary\n          description: \"Access DLP report summaries.\"\n          operations:\n            - method: GET\n              name: get-dlp-report-summary\n              description: \"Get a DLP summary report for a\
  \ given time range.\"\n              inputParameters:\n                - name: start_date\n                  in: query\n                  type: string\n                  required: false\n                - name: end_date\n                  in: query\n                  type: string\n                  required: false\n              call: \"dlp-api.get-report-summary\"\n              with:\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # Email DLP\n        # -------------------------------------------------------\n        - path: /v1/email-incidents\n          name: email-incidents\n          description: \"List email DLP incidents.\"\n          operations:\n            - method: GET\n              name: list-email-incidents\n              description: \"List email DLP\
  \ incidents with optional filters.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n                - name: status\n                  in: query\n                  type: string\n                  required: false\n                - name: severity\n                  in: query\n                  type: string\n                  required: false\n              call: \"email-dlp-api.list-email-incidents\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n                status: \"rest.status\"\n                severity: \"rest.severity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/email-incidents/{incident_id}\n          name:\
  \ email-incident-detail\n          description: \"Get a specific email DLP incident.\"\n          operations:\n            - method: GET\n              name: get-email-incident\n              description: \"Retrieve a specific email DLP incident by ID.\"\n              inputParameters:\n                - name: incident_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"email-dlp-api.get-email-incident\"\n              with:\n                id: \"rest.incident_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/email-incidents/{incident_id}/verdict\n          name: email-incident-verdict\n          description: \"Manage email incident verdicts.\"\n          operations:\n            - method: PUT\n              name: update-email-verdict\n              description: \"Update the verdict for an email DLP incident.\"\n              inputParameters:\n\
  \                - name: incident_id\n                  in: path\n                  type: string\n                  required: true\n                - name: verdict\n                  in: body\n                  type: string\n                  required: true\n                - name: reason\n                  in: body\n                  type: string\n                  required: false\n              call: \"email-dlp-api.update-email-incident-verdict\"\n              with:\n                id: \"rest.incident_id\"\n                verdict: \"rest.verdict\"\n                reason: \"rest.reason\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/email-incidents/{incident_id}/attachments\n          name: email-incident-attachments\n          description: \"Access email incident attachments.\"\n          operations:\n            - method: GET\n              name: get-email-attachments\n              description: \"Get\
  \ attachments for a specific email DLP incident.\"\n              inputParameters:\n                - name: incident_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"email-dlp-api.get-email-incident-attachments\"\n              with:\n                id: \"rest.incident_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/email-incidents/{incident_id}/recipients\n          name: email-incident-recipients\n          description: \"Access email incident recipients.\"\n          operations:\n            - method: GET\n              name: get-email-recipients\n              description: \"Get recipients for a specific email DLP incident.\"\n              inputParameters:\n                - name: incident_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"email-dlp-api.get-email-incident-recipients\"\
  \n              with:\n                id: \"rest.incident_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # SaaS Security Incidents\n        # -------------------------------------------------------\n        - path: /v1/saas-incidents\n          name: saas-incidents\n          description: \"Manage SaaS security incidents.\"\n          operations:\n            - method: GET\n              name: list-saas-incidents\n              description: \"List SaaS security incidents with optional filters.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n                - name: status\n                  in: query\n          \
  \        type: string\n                  required: false\n                - name: severity\n                  in: query\n                  type: string\n                  required: false\n                - name: app_id\n                  in: query\n                  type: string\n                  required: false\n                - name: start_date\n                  in: query\n                  type: string\n                  required: false\n                - name: end_date\n                  in: query\n                  type: string\n                  required: false\n              call: \"saas-security.list-incidents\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n                status: \"rest.status\"\n                severity: \"rest.severity\"\n                app_id: \"rest.app_id\"\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n            \
  \    - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/saas-incidents/{incident_id}\n          name: saas-incident-detail\n          description: \"Get or update a specific SaaS security incident.\"\n          operations:\n            - method: GET\n              name: get-saas-incident\n              description: \"Retrieve details for a specific SaaS security incident.\"\n              inputParameters:\n                - name: incident_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"saas-security.get-incident\"\n              with:\n                id: \"rest.incident_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: PUT\n              name: update-saas-incident\n              description: \"Update a specific SaaS security incident.\"\n              inputParameters:\n                - name: incident_id\n        \
  \          in: path\n                  type: string\n                  required: true\n                - name: status\n                  in: body\n                  type: string\n                  required: false\n                - name: assignee_id\n                  in: body\n                  type: string\n                  required: false\n                - name: note\n                  in: body\n                  type: string\n                  required: false\n              call: \"saas-security.update-incident\"\n              with:\n                id: \"rest.incident_id\"\n                status: \"rest.status\"\n                assignee_id: \"rest.assignee_id\"\n                note: \"rest.note\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # SaaS Assets\n        # -------------------------------------------------------\n        - path: /v1/saas-assets\n\
  \          name: saas-assets\n          description: \"List monitored SaaS assets.\"\n          operations:\n            - method: GET\n              name: list-saas-assets\n              description: \"Retrieve a list of monitored SaaS assets.\"\n              inputParameters:\n                - name: app_id\n                  in: query\n                  type: string\n                  required: false\n                - name: type\n                  in: query\n                  type: string\n                  required: false\n                - name: exposure\n                  in: query\n                  type: string\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"saas-security.list-assets\"\n              with:\n      \
  \          app_id: \"rest.app_id\"\n                type: \"rest.type\"\n                exposure: \"rest.exposure\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/saas-assets/{asset_id}\n          name: saas-asset-detail\n          description: \"Get a specific SaaS asset.\"\n          operations:\n            - method: GET\n              name: get-saas-asset\n              description: \"Retrieve details for a specific SaaS asset.\"\n              inputParameters:\n                - name: asset_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"saas-security.get-asset\"\n              with:\n                id: \"rest.asset_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n\
  \        # SaaS Applications & Users\n        # -------------------------------------------------------\n        - path: /v1/saas-applications\n          name: saas-applications\n          description: \"List connected SaaS applications.\"\n          operations:\n            - method: GET\n              name: list-saas-applications\n              description: \"Retrieve a list of connected SaaS applications.\"\n              call: \"saas-security.list-applications\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/saas-users\n          name: saas-users\n          description: \"List users across SaaS applications.\"\n          operations:\n            - method: GET\n              name: list-saas-users\n              description: \"Retrieve a list of users across SaaS applications.\"\n              inputParameters:\n                - name: app_id\n                  in: query\n                  type: string\n      \
  \            required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"saas-security.list-users\"\n              with:\n                app_id: \"rest.app_id\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/saas-users/{user_id}/activities\n          name: saas-user-activities\n          description: \"Get user activity log.\"\n          operations:\n            - method: GET\n              name: get-user-activities\n              description: \"Retrieve activity log for a specific user.\"\n              inputParameters:\n                - name: user_id\n                  in: path\n                  type:\
  \ string\n                  required: true\n                - name: start_date\n                  in: query\n                  type: string\n                  required: false\n                - name: end_date\n                  in: query\n                  type: string\n                  required: false\n                - name: app_id\n                  in: query\n                  type: string\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"saas-security.get-user-activities\"\n              with:\n                id: \"rest.user_id\"\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n                app_id: \"rest.app_id\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n\
  \        # SaaS Settings\n        # -------------------------------------------------------\n        - path: /v1/log-forwarding-settings\n          name: log-forwarding-settings\n          description: \"Get log forwarding configuration settings.\"\n          operations:\n            - method: GET\n              name: get-log-forwarding-settings\n              description: \"Retrieve log forwarding configuration settings.\"\n              call: \"saas-security.get-log-forwarding-settings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # SSPM App Management\n        # -------------------------------------------------------\n        - path: /v1/sspm-apps\n          name: sspm-apps\n          description: \"Manage onboarded SSPM applications.\"\n          operations:\n            - method: GET\n              name: list-onboarded-apps\n              description:\
  \ \"List all onboarded SaaS applications.\"\n              inputParameters:\n                - name: status\n                  in: query\n                  type: string\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"sspm.list-onboarded-apps\"\n              with:\n                status: \"rest.status\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: onboard-app\n              description: \"Onboard a new SaaS application.\"\n              inputParameters:\n                - name: app_type\n                  in: body\n                  type: string\n\
  \                  required: true\n                - name: display_name\n                  in: body\n                  type: string\n                  required: true\n                - name: credentials\n                  in: body\n                  type: object\n                  required: true\n              call: \"sspm.onboard-app\"\n              with:\n                app_type: \"rest.app_type\"\n                display_name: \"rest.display_name\"\n                credentials: \"rest.credentials\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sspm-apps/{app_id}\n          name: sspm-app-detail\n          description: \"Remove an onboarded SSPM application.\"\n          operations:\n            - method: DELETE\n              name: remove-app\n              description: \"Remove an onboarded SaaS application.\"\n              inputParameters:\n                - name: app_id\n                  in: path\n \
  \                 type: string\n                  required: true\n              call: \"sspm.remove-app\"\n              with:\n                app_id: \"rest.app_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # SSPM Posture\n        # -------------------------------------------------------\n        - path: /v1/posture-checks\n          name: posture-checks\n          description: \"Manage SSPM posture checks.\"\n          operations:\n            - method: GET\n              name: list-posture-checks\n              description: \"List posture checks with optional filters.\"\n              inputParameters:\n                - name: app_id\n                  in: query\n                  type: string\n                  required: false\n                - name: check_type\n                  in: query\n                  type: string\n                  required:\
  \ false\n                - name: severity\n                  in: query\n                  type: string\n                  required: false\n                - name: status\n                  in: query\n                  type: string\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"sspm.list-posture-checks\"\n              with:\n                app_id: \"rest.app_id\"\n                check_type: \"rest.check_type\"\n                severity: \"rest.severity\"\n                status: \"rest.status\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/posture-checks/{check_id}\n\
  \          name: posture-check-detail\n          description: \"Get a specific posture check.\"\n          operations:\n            - method: GET\n              name: get-posture-check\n              description: \"Get a specific posture check by ID.\"\n              inputParameters:\n                - name: check_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sspm.get-posture-check\"\n              with:\n                check_id: \"rest.check_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/posture-checks/{check_id}/status\n          name: posture-check-status\n          description: \"Update posture check status.\"\n          operations:\n            - method: PUT\n              name: update-posture-check-status\n              description: \"Update the status of a posture check.\"\n              inputParameters:\n                - name:\
  \ check_id\n                  in: path\n                  type: string\n                  required: true\n                - name: status\n                  in: body\n                  type: string\n                  required: true\n                - name: justification\n                  in: body\n                  type: string\n                  required: true\n              call: \"sspm.update-posture-check-status\"\n              with:\n                check_id: \"rest.check_id\"\n                status: \"rest.status\"\n                justification: \"rest.justification\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # SSPM Catalog & Integrations\n        # -------------------------------------------------------\n        - path: /v1/sspm-app-catalog\n          name: sspm-app-catalog\n          description: \"Browse the SSPM application catalog.\"\n  \
  \        operations:\n            - method: GET\n              name: list-app-catalog\n              description: \"List available applications in the catalog.\"\n              inputParameters:\n                - name: category\n                  in: query\n                  type: string\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"sspm.list-app-catalog\"\n              with:\n                category: \"rest.category\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jira-integrations\n          name: jira-integrations\n          description: \"Manage SSPM Jira integrations.\"\
  \n          operations:\n            - method: GET\n              name: list-jira-integrations\n              description: \"List all Jira integrations.\"\n              call: \"sspm.list-jira-integrations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-jira-integration\n              description: \"Create a new Jira integration.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: jira_url\n                  in: body\n                  type: string\n                  required: true\n                - name: project_key\n                  in: body\n                  type: string\n                  required: true\n                - name: api_token\n                  in: body\n                  type: string\n                  required: true\n        \
  \        - name: email\n                  in: body\n                  type: string\n                  required: true\n                - name: issue_type\n                  in: body\n                  type: string\n                  required: true\n                - name: severity_mapping\n                  in: body\n                  type: object\n                  required: true\n              call: \"sspm.create-jira-integration\"\n              with:\n                name: \"rest.name\"\n                jira_url: \"rest.jira_url\"\n                project_key: \"rest.project_key\"\n                api_token: \"rest.api_token\"\n                email: \"rest.email\"\n                issue_type: \"rest.issue_type\"\n                severity_mapping: \"rest.severity_mapping\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    # =============================================================\n    # MCP Server — AI-assisted data protection\n\
  \    # =============================================================\n    - type: mcp\n      port: 9095\n      namespace: data-protection-mcp\n      transport: http\n      description: \"MCP server for AI-assisted data protection across Enterprise DLP, Email DLP, SaaS Security, and SSPM.\"\n      tools:\n\n        # ---------------------------------------------------------\n        # DLP\n        # ---------------------------------------------------------\n        - name: list-dlp-incidents\n          description: \"List DLP incidents with optional filters for severity and status.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: offset\n              type: integer\n              description: \"Offset for pagination.\"\n              required: false\n            - name: limit\n              type: integer\n              description: \"Maximum number of\
  \ results to return.\"\n              required: false\n            - name: severity\n              type: string\n              description: \"Filter by severity level.\"\n              required: false\n            - name: status\n              type: string\n              description: \"Filter by incident status.\"\n              required: false\n          call: \"dlp-api.list-incidents\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n            severity: \"tools.severity\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-dlp-incident\n          description: \"Retrieve a specific DLP incident by ID.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: incident_id\n              type: string\n              description:\
  \ \"The DLP incident ID.\"\n              required: true\n          call: \"dlp-api.get-incident\"\n          with:\n            incident_id: \"tools.incident_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-dlp-incident\n          description: \"Update a DLP incident status or assignee.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: incident_id\n              type: string\n              description: \"The DLP incident ID to update.\"\n              required: true\n            - name: status\n              type: string\n              description: \"New status for the incident.\"\n              required: false\n            - name: assignee\n              type: string\n              description: \"New assignee for the incident.\"\n              required: false\n          call: \"\
  dlp-api.update-incident\"\n          with:\n            i\n\n# --- truncated at 32 KB (55 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/data-protection.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/data-protection.yaml
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
