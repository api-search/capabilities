---
categories: []
consumed_apis: []
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
- update dlp incident
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- mssp operator
- executes containment, eradication, and recovery actions during security incidents.
- get log forwarding configuration settings.
- platform engineer
- update saas incident
- get a specific saas asset.
- manage enterprise browser policies, user sessions, and deployments.
- list available applications in the sspm catalog.
- manage email incident verdicts.
- list dlp data patterns.
- red team operator
- xdr
- access email incident recipients.
- update the status of an sspm posture check.
- onboard a new saas application in sspm.
- get a specific posture check.
- get a specific posture check by id.
- list app catalog
- digital experience monitoring, log management, and best practice assessment.
- update a dlp incident status or assignee.
- cloud security
- list posture checks with optional filters.
- monitors network health, performance, and digital experience metrics.
- list saas incidents
- palo alto networks
- get posture check
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- malware researcher
- get recipients for a specific email dlp incident.
- get saas asset
- list monitored saas assets.
- secures ai applications with runtime scanning and vulnerability assessment.
- sase
- remove an onboarded saas application.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- data loss prevention, saas security monitoring, and identity security posture.
- list onboarded apps
- conducts automated adversarial testing against ai systems and llm applications.
- network architect
- manage saas security incidents.
- retrieve details for a specific saas asset.
- access email incident attachments.
- manage sspm jira integrations.
- list available data patterns.
- sre
- update a specific saas security incident.
- list posture checks
- compliance team
- list all onboarded saas applications.
- retrieve a list of users across saas applications.
- get a specific data pattern.
- manages service accounts, roles, and access policies for platform api access.
- ai runtime security scanning and automated red teaming for ai applications.
- subscription manager
- list dlp incidents with optional filters.
- manage dlp incidents.
- get email recipients
- retrieve a list of monitored saas assets.
- list users across saas applications.
- list sspm posture checks with optional filters.
- list available applications in the catalog.
- list saas users
- update the status of a posture check.
- get email incident
- firewall
- onboard app
- list all jira integrations.
- manages multi-tenant security operations at scale for managed service providers.
- retrieve a specific dlp incident by id.
- list dlp incidents with optional filters for severity and status.
- retrieve a list of connected saas applications.
- sspm
- update a dlp incident.
- analyzes suspicious files and samples for malware characteristics.
- get dlp snippets
- cloud security posture management, compliance monitoring, and workload protection.
- list connected saas applications.
- saas security admin
- soc analyst
- list available dlp data patterns.
- get a specific sspm posture check by id.
- sd wan operator
- investigates security incidents, triages alerts, and coordinates response actions.
- tenant operator
- remove an onboarded saas application from sspm.
- list data patterns
- access dlp report summaries.
- identity security posture
- data protection analyst
- get data pattern
- iam admin
- get or update a specific dlp incident.
- create a new jira integration for sspm.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- list saas security incidents with optional filters.
- network operations
- designs and implements network security architectures and policies.
- list saas assets
- get data snippets for a specific dlp incident.
- browse the sspm application catalog.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- threat intel analyst
- monitors and remediates cloud security misconfigurations and compliance violations.
- enterprise it
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- data protection
- threat hunter
- update email verdict
- dlp
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- researches threat actors, malware campaigns, and vulnerability trends.
- manage sspm posture checks.
- get or update a specific saas security incident.
- sase admin
- update posture check status
- retrieve a list of saas security incidents.
- proactively searches for threats and iocs across telemetry data.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- vulnerability manager
- manages logging infrastructure, integrations, and platform automation.
- list email dlp incidents with optional filters.
- list dlp incidents
- saas security
- access dlp incident data snippets.
- remove app
- incident responder
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- identity and access management, tenant hierarchies, and subscription management.
- retrieve details for a specific saas security incident.
- cybersecurity
- onboard a new saas application.
- network security engineer
- get user activities
- investigates dlp incidents and manages sensitive data protection policies.
- list jira integrations
- get email attachments
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- manages multi-tenant hierarchies and service group configurations for mssps.
- ai security engineer
- get dlp incident
- browser security admin
- get saas incident
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- compliance officer
- enterprise browser policy management and secure browsing.
- get a dlp summary report for a given time range.
- firewall policy management, network objects, and cloud-native firewall configuration.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- get attachments for a specific email dlp incident.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- get a specific email dlp incident.
- soar
- list email incidents
- get user activity log.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- retrieve activity log for a specific user.
- network security
- update the verdict for an email dlp incident.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- firewall admin
- get dlp report summary
- list all sspm jira integrations.
- list saas applications
- get log forwarding settings
- retrieve a specific email dlp incident by id.
- designs sase and sd-wan network architectures for secure remote access.
- retrieve log forwarding configuration settings.
- cloud security engineer
- update posture check status.
- list all onboarded saas applications in sspm.
- retrieve a specific data pattern by id.
- threat intelligence
- list email dlp incidents.
- create jira integration
- remove an onboarded sspm application.
- create a new jira integration.
- retrieve a specific dlp data pattern by id.
- manage onboarded sspm applications.
- manages enterprise browser policies and secure browsing configurations.
slug: data-protection
source_filename: data-protection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Palo Alto Networks Data Protection\n  description: Unified data protection capability for managing DLP incidents, email DLP events, SaaS security incidents and\n    assets, and SaaS security posture checks across Enterprise DLP, Email DLP, SaaS Security, and SSPM APIs.\n  tags:\n  - Palo Alto Networks\n  - Data Protection\n  - DLP\n  - SaaS Security\n  - SSPM\n  - Identity Security Posture\n  created: '2026-04-16'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PALO_ALTO_DLP_TOKEN: PALO_ALTO_DLP_TOKEN\n    SAAS_SECURITY_TOKEN: SAAS_SECURITY_TOKEN\n    PALO_ALTO_OAUTH_TOKEN: PALO_ALTO_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: dlp-api\n    baseUri: https://api.dlp.paloaltonetworks.com\n    description: Enterprise DLP API for managing data loss prevention incidents, data patterns, and reports.\n    authentication:\n      type: bearer\n      token: '{{PALO_ALTO_DLP_TOKEN}}'\n    resources:\n  \
  \  - name: incidents\n      path: /incidents\n      description: Manage DLP incidents.\n      operations:\n      - name: list-incidents\n        method: GET\n        description: List DLP incidents with optional filters.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Offset for pagination.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        - name: severity\n          in: query\n          type: string\n          required: false\n          description: Filter by severity level.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by incident status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-incident\n\
  \        method: GET\n        description: Retrieve a specific DLP incident by ID.\n        inputParameters:\n        - name: incident_id\n          in: path\n          type: string\n          required: true\n          description: The incident ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-incident\n        method: PUT\n        description: Update a DLP incident.\n        inputParameters:\n        - name: incident_id\n          in: path\n          type: string\n          required: true\n          description: The incident ID to update.\n        - name: status\n          in: body\n          type: string\n          required: false\n          description: New status for the incident.\n        - name: assignee\n          in: body\n          type: string\n          required: false\n          description: New assignee for the incident.\n        body:\n          type: json\n          data:\n\
  \            status: '{{tools.status}}'\n            assignee: '{{tools.assignee}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: incident-snippets\n      path: /incidents/{incident_id}/snippets\n      description: Access incident data snippets.\n      operations:\n      - name: get-incident-snippets\n        method: GET\n        description: Get data snippets for a specific incident.\n        inputParameters:\n        - name: incident_id\n          in: path\n          type: string\n          required: true\n          description: The incident ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-patterns\n      path: /data-patterns\n      description: Manage DLP data patterns.\n      operations:\n      - name: list-data-patterns\n        method: GET\n        description: List available data patterns.\n\
  \        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Offset for pagination.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-data-pattern\n        method: GET\n        description: Retrieve a specific data pattern by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The data pattern ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /reports/summary\n      description: Access DLP report summaries.\n      operations:\n      - name: get-report-summary\n\
  \        method: GET\n        description: Get a summary report for a given time range.\n        inputParameters:\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Start date for the report period.\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: End date for the report period.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: email-dlp-api\n    baseUri: https://api.dlp.paloaltonetworks.com\n    description: Email DLP API for managing email-based data loss prevention incidents.\n    authentication:\n      type: bearer\n      token: '{{PALO_ALTO_DLP_TOKEN}}'\n    resources:\n    - name: email-incidents\n      path: /email-incidents\n      description: Manage email DLP incidents.\n      operations:\n      - name: list-email-incidents\n\
  \        method: GET\n        description: List email DLP incidents with optional filters.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Offset for pagination.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by incident status.\n        - name: severity\n          in: query\n          type: string\n          required: false\n          description: Filter by severity level.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-email-incident\n        method: GET\n        description: Retrieve a specific email DLP incident by ID.\n        inputParameters:\n        -\
  \ name: id\n          in: path\n          type: string\n          required: true\n          description: The email incident ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: email-incident-verdict\n      path: /email-incidents/{id}/verdict\n      description: Manage email incident verdicts.\n      operations:\n      - name: update-email-incident-verdict\n        method: PUT\n        description: Update the verdict for an email DLP incident.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The email incident ID.\n        - name: verdict\n          in: body\n          type: string\n          required: true\n          description: The verdict to set.\n        - name: reason\n          in: body\n          type: string\n          required: false\n          description: Reason for the verdict.\n        body:\n\
  \          type: json\n          data:\n            verdict: '{{tools.verdict}}'\n            reason: '{{tools.reason}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: email-incident-attachments\n      path: /email-incidents/{id}/attachments\n      description: Access email incident attachments.\n      operations:\n      - name: get-email-incident-attachments\n        method: GET\n        description: Get attachments for a specific email DLP incident.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The email incident ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: email-incident-recipients\n      path: /email-incidents/{id}/recipients\n      description: Access email incident recipients.\n      operations:\n \
  \     - name: get-email-incident-recipients\n        method: GET\n        description: Get recipients for a specific email DLP incident.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The email incident ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: saas-security\n    baseUri: https://api.aperture.paloaltonetworks.com\n    authentication:\n      type: bearer\n      token: '{{env.SAAS_SECURITY_TOKEN}}'\n    resources:\n    - name: incidents\n      path: /api/incidents\n      operations:\n      - name: list-incidents\n        method: GET\n        description: Retrieve a list of security incidents\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n\
  \          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: severity\n          in: query\n          type: string\n          required: false\n        - name: app_id\n          in: query\n          type: string\n          required: false\n        - name: start_date\n          in: query\n          type: string\n          required: false\n        - name: end_date\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: incident-by-id\n      path: /api/incidents/{id}\n      operations:\n      - name: get-incident\n        method: GET\n        description: Retrieve details for a specific incident\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: update-incident\n        method: PUT\n        description: Update a specific incident\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n            assignee_id: '{{tools.assignee_id}}'\n            note: '{{tools.note}}'\n    - name: assets\n      path: /api/assets\n      operations:\n      - name: list-assets\n        method: GET\n        description: Retrieve a list of monitored assets\n        inputParameters:\n        - name: app_id\n          in: query\n          type: string\n          required: false\n        - name: type\n          in: query\n          type: string\n          required: false\n        - name: exposure\n\
  \          in: query\n          type: string\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: asset-by-id\n      path: /api/assets/{id}\n      operations:\n      - name: get-asset\n        method: GET\n        description: Retrieve details for a specific asset\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /api/applications\n      operations:\n      - name: list-applications\n        method: GET\n        description: Retrieve a list of connected SaaS\
  \ applications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /api/users\n      operations:\n      - name: list-users\n        method: GET\n        description: Retrieve a list of users across SaaS applications\n        inputParameters:\n        - name: app_id\n          in: query\n          type: string\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-activities\n      path: /api/user/{id}/activities\n      operations:\n      - name: get-user-activities\n        method: GET\n        description: Retrieve activity log for a specific user\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: string\n          required: true\n        - name: start_date\n          in: query\n          type: string\n          required: false\n        - name: end_date\n          in: query\n          type: string\n          required: false\n        - name: app_id\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: log-forwarding-settings\n      path: /api/settings/log-forwarding\n      operations:\n      - name: get-log-forwarding-settings\n        method: GET\n        description: Retrieve log forwarding configuration settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: sspm\n\
  \    baseUri: https://api.sase.paloaltonetworks.com/sspm\n    description: SaaS Security Posture Management API for onboarding apps, managing posture checks, browsing the app catalog,\n      and configuring Jira integrations.\n    authentication:\n      type: bearer\n      token: '{{env.PALO_ALTO_OAUTH_TOKEN}}'\n    resources:\n    - name: apps\n      path: /v1/apps\n      operations:\n      - name: list-onboarded-apps\n        method: GET\n        description: List all onboarded SaaS applications.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: onboard-app\n        method: POST\n   \
  \     description: Onboard a new SaaS application.\n        inputParameters:\n        - name: app_type\n          in: body\n          type: string\n          required: true\n        - name: display_name\n          in: body\n          type: string\n          required: true\n        - name: credentials\n          in: body\n          type: object\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            app_type: '{{tools.app_type}}'\n            display_name: '{{tools.display_name}}'\n            credentials: '{{tools.credentials}}'\n    - name: app\n      path: /v1/apps/{app_id}\n      operations:\n      - name: remove-app\n        method: DELETE\n        description: Remove an onboarded SaaS application.\n        inputParameters:\n        - name: app_id\n          in: path\n          type: string\n          required: true\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: posture-checks\n      path: /v1/posture-checks\n      operations:\n      - name: list-posture-checks\n        method: GET\n        description: List posture checks with optional filters.\n        inputParameters:\n        - name: app_id\n          in: query\n          type: string\n          required: false\n        - name: check_type\n          in: query\n          type: string\n          required: false\n        - name: severity\n          in: query\n          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: posture-check\n      path: /v1/posture-checks/{check_id}\n      operations:\n      - name: get-posture-check\n        method: GET\n        description: Get a specific posture check by ID.\n        inputParameters:\n        - name: check_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: posture-check-status\n      path: /v1/posture-checks/{check_id}/status\n      operations:\n      - name: update-posture-check-status\n        method: PUT\n        description: Update the status of a posture check.\n        inputParameters:\n        - name: check_id\n          in: path\n          type: string\n          required: true\n        - name: status\n          in: body\n          type: string\n          required: true\n        - name: justification\n          in:\
  \ body\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n            justification: '{{tools.justification}}'\n    - name: app-catalog\n      path: /v1/app-catalog\n      operations:\n      - name: list-app-catalog\n        method: GET\n        description: List available applications in the catalog.\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jira-integrations\n\
  \      path: /v1/jira-integrations\n      operations:\n      - name: list-jira-integrations\n        method: GET\n        description: List all Jira integrations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-jira-integration\n        method: POST\n        description: Create a new Jira integration.\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n        - name: jira_url\n          in: body\n          type: string\n          required: true\n        - name: project_key\n          in: body\n          type: string\n          required: true\n        - name: api_token\n          in: body\n          type: string\n          required: true\n        - name: email\n          in: body\n          type: string\n          required: true\n        - name: issue_type\n          in: body\n          type: string\n          required:\
  \ true\n        - name: severity_mapping\n          in: body\n          type: object\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            jira_url: '{{tools.jira_url}}'\n            project_key: '{{tools.project_key}}'\n            api_token: '{{tools.api_token}}'\n            email: '{{tools.email}}'\n            issue_type: '{{tools.issue_type}}'\n            severity_mapping: '{{tools.severity_mapping}}'\n  - type: http\n    namespace: identity-security-posture\n    baseUri: https://api.sase.paloaltonetworks.com\n    authentication:\n      type: bearer\n      token: '{{env.PALO_ALTO_SASE_ACCESS_TOKEN}}'\n    resources:\n    - name: catalog\n      path: /sspm/identity/v1/catalog\n      operations:\n      - name: get-application-catalog\n        method: GET\n        description: Retrieve\
  \ application catalog details based on the specified application type.\n        path: /{appType}\n        inputParameters:\n        - name: appType\n          in: path\n          type: string\n          required: true\n        - name: feature\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: idps\n      path: /sspm/identity/v1/idps\n      operations:\n      - name: list-identity-providers\n        method: GET\n        description: Retrieve a list of identity providers configured for the tenant.\n        inputParameters:\n        - name: designated\n          in: query\n          type: boolean\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-identity-provider\n        method: POST\n        description:\
  \ Create a new identity provider entry for the tenant.\n        inputParameters:\n        - name: designated\n          in: query\n          type: boolean\n          required: false\n        - name: idpId\n          in: query\n          type: string\n          required: false\n        - name: idpType\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-logout-status\n        method: GET\n        description: Retrieve logout status of user accounts for an IDP.\n        path: /{idpId}/accounts/logout\n        inputParameters:\n        - name: idpId\n          in: path\n          type: string\n          required: true\n        - name: batch_id\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n      - name: trigger-account-logout\n        method: POST\n        description: Initiate a logout request for user accounts associated with an IDP.\n        path: /{idpId}/accounts/logout\n        inputParameters:\n        - name: idpId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            users: '{{tools.users}}'\n      - name: get-idp-feature-state\n        method: GET\n        description: Retrieve the current status and last scan timestamp of a feature for an IDP.\n        path: /{idpId}/feature_state\n        inputParameters:\n        - name: idpId\n          in: path\n          type: string\n          required: true\n        - name: feature\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-idp-account-count\n        method: GET\n        description: Return the number of user accounts linked to an IDP.\n        path: /{idpId}/idp_accounts/count\n        inputParameters:\n        - name: idpId\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: generate-idp-account-csv\n        method: POST\n        description: Generate a CSV report of accounts associated with an IDP.\n        path: /{idpId}/idp_accounts/csv_report\n        inputParameters:\n        - name: idpId\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          required: false\n      \
  \  - name: sortBy\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userFullName: '{{tools.userFullName}}'\n            userEmail: '{{tools.userEmail}}'\n            service: '{{tools.service}}'\n      - name: get-mfa-activity\n        method: GET\n        description: Retrieve MFA activity logs for an IDP.\n        path: /{idpId}/mfa_activity\n        inputParameters:\n        - name: idpId\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: sortBy\n      \
  \    in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-mfa-activity-count\n        method: GET\n        description: Return the number of MFA activities for an IDP.\n        path: /{idpId}/mfa_activity/count\n        inputParameters:\n        - name: idpId\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-mfa-activity-count-by-app-type\n        method: GET\n        description: Return MFA activity count grouped by application type.\n        path: /{idpId}/mfa_activity/count_by_app_type\n        inputParameters:\n        - name: idpId\n          in: path\n          type: string\n\
  \          required: true\n        - name: filter\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: generate-mfa-activity-csv\n        method: POST\n        description: Generate a CSV report of MFA activities for an IDP.\n        path: /{idpId}/mfa_activity/csv_report\n        inputParameters:\n        - name: idpId\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          required: false\n        - name: sortBy\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userFullName: '{{tools.userFullName}}'\n            userEmail: '{{tools.userEmail}}'\n            service: '{{tools.service}}'\n    - name: saas-instances\n      path: /sspm/identity/v1/saas_instances\n      operations:\n      - name: list-saas-instances\n        method: GET\n        description: Retrieve a list of SaaS instances configured for the tenant.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-saas-accounts\n        method: GET\n        description: Retrieve a list of user accounts for a SaaS instance.\n        path: /{saasInstanceId}/saas_accounts\n        inputParameters:\n        - name: saasInstanceId\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n     \
  \     required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: sortBy\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-saas-account-count\n        method: GET\n        description: Return the number of user accounts for a SaaS instance.\n        path: /{saasInstanceId}/saas_accounts/count\n        inputParameters:\n        - name: saasInstanceId\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: generate-saas-account-csv\n\
  \        method: POST\n        description: Generate a CSV report of accounts for a SaaS instance.\n        path: /{saasInstanceId}/saas_accounts/csv_report\n        inputParameters:\n        - name: saasInstanceId\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          required: false\n        - name: sortBy\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userFullName: '{{tools.userFullName}}'\n            userEmail: '{{tools.userEmail}}'\n            service: '{{tools.service}}'\n      - name: get-saas-activity\n        method: GET\n        description: Retrieve activity logs for a SaaS instance.\n        path: /{saasInstanceId}/saas_activity\n        inputParameters:\n       \
  \ - name: saasInstanceId\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: sortBy\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets\n      path: /sspm/identity/v1/{saasInstanceId}/tickets\n      operations:\n      - name: list-saas-tickets\n        method: GET\n        description: Retrieve tickets associated with a SaaS instance.\n        inputParameters:\n        - name: saasInstanceId\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n\
  \          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: sortBy\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-saas-ticket\n        method: POST\n        description: Create a new ticket for a SaaS instance.\n        inputParameters:\n        - name: saasInstanceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            resourceIds: '{{tools.resourceI\n\n# --- truncated at 32 KB (75 KB total) ---\n# Full source:\
  \ https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/data-protection.yaml\n"
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
