---
consumed_apis:
- prisma-cloud-cspm
- prisma-cloud-code-security
- prisma-cloud-dspm
- prisma-cloud-mssp
description: Unified cloud security posture capability for managing alerts, policies, compliance, code security scanning, and data security posture across Prisma Cloud CSPM, Code Security, and DSPM.
layout: capability
name: Palo Alto Networks Cloud Security Posture
operations:
- description: ''
  method: POST
  name: login
  path: /v1/auth/login
- description: ''
  method: GET
  name: get-alerts
  path: /v1/alerts
- description: ''
  method: GET
  name: get-alert
  path: /v1/alerts/{id}
- description: ''
  method: POST
  name: dismiss-alerts
  path: /v1/alerts/dismiss
- description: ''
  method: POST
  name: reopen-alerts
  path: /v1/alerts/reopen
- description: ''
  method: GET
  name: list-data-security-alerts
  path: /v1/data-security-alerts
- description: ''
  method: GET
  name: list-policies
  path: /v1/policies
- description: ''
  method: POST
  name: create-policy
  path: /v1/policies
- description: ''
  method: GET
  name: get-policy
  path: /v1/policies/{policyId}
- description: ''
  method: PUT
  name: update-policy
  path: /v1/policies/{policyId}
- description: ''
  method: GET
  name: list-dspm-policies
  path: /v1/dspm-policies
- description: ''
  method: GET
  name: list-cloud-accounts
  path: /v1/cloud-accounts
- description: ''
  method: POST
  name: add-cloud-account
  path: /v1/cloud-accounts/{cloudType}
- description: ''
  method: DELETE
  name: remove-cloud-account
  path: /v1/cloud-accounts/{cloudType}/{id}
- description: ''
  method: POST
  name: search-asset
  path: /v1/search/assets
- description: ''
  method: POST
  name: search-config
  path: /v1/search/config
- description: ''
  method: GET
  name: list-compliance-standards
  path: /v1/compliance-standards
- description: ''
  method: GET
  name: list-reports
  path: /v1/reports
- description: ''
  method: GET
  name: list-repositories
  path: /v1/repositories
- description: ''
  method: POST
  name: add-repository
  path: /v1/repositories
- description: ''
  method: DELETE
  name: remove-repository
  path: /v1/repositories
- description: ''
  method: GET
  name: list-scan-integrations
  path: /v1/scan-integrations
- description: ''
  method: POST
  name: trigger-scan
  path: /v1/scans
- description: ''
  method: GET
  name: get-scan-status
  path: /v1/scans/{scan_id}
- description: ''
  method: GET
  name: list-suppressions
  path: /v1/suppressions
- description: ''
  method: POST
  name: create-suppression
  path: /v1/suppressions
- description: ''
  method: DELETE
  name: delete-suppression
  path: /v1/suppressions/{suppression_id}
- description: ''
  method: GET
  name: get-errors-by-branch
  path: /v1/code-errors
- description: ''
  method: GET
  name: get-fix-suggestions-for-pr
  path: /v1/fix-suggestions
- description: ''
  method: GET
  name: list-data-assets
  path: /v1/data-assets
- description: ''
  method: GET
  name: get-data-asset
  path: /v1/data-assets/{id}
- description: ''
  method: GET
  name: list-risks
  path: /v1/data-risks
- description: ''
  method: GET
  name: get-risk
  path: /v1/data-risks/{id}
- description: ''
  method: PUT
  name: update-risk-status
  path: /v1/data-risks/{id}/status
- description: ''
  method: GET
  name: list-data-stores
  path: /v1/data-stores
- description: ''
  method: GET
  name: list-classifications
  path: /v1/classifications
personas:
- description: Monitors and remediates cloud security misconfigurations and compliance violations.
  id: cloud-security-engineer
  name: Cloud Security Engineer
- description: Ensures cloud infrastructure meets regulatory and industry compliance standards.
  id: compliance-officer
  name: Compliance Officer
- description: Manages multi-tenant security operations at scale for managed service providers.
  id: mssp-operator
  name: MSSP Operator
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- retrieve a list of all onboarded cloud accounts
- mssp
- vulnerability manager
- delete a specific code security suppression by id
- sd wan operator
- enterprise browser policy management and secure browsing.
- trigger a new code security scan for a repository
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- designs and implements network security architectures and policies.
- firewall
- create policy
- retrieve details for a specific data asset
- compliance officer
- manages enterprise browser policies and secure browsing configurations.
- search for cloud assets using rql queries
- reopen cspm alerts
- data protection analyst
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- mssp operator
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- get risk
- retrieve a list of dspm policies
- executes containment, eradication, and recovery actions during security incidents.
- search assets
- get cspm alert
- list all code security repositories with pagination and filtering
- retrieve a list of data stores
- add repository
- list classifications
- monitors network health, performance, and digital experience metrics.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- manages service accounts, roles, and access policies for platform api access.
- add cloud account
- cybersecurity
- list data security alerts
- threat intelligence
- list risks
- malware researcher
- data loss prevention, saas security monitoring, and identity security posture.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- analyzes suspicious files and samples for malware characteristics.
- create suppression
- search for cloud configuration data using rql queries
- saas security admin
- list suppressions
- dismiss one or more cspm alerts
- get fix suggestions for a pull request
- list data stores
- designs sase and sd-wan network architectures for secure remote access.
- create a new code security suppression
- get fix suggestions
- list data risks
- firewall admin
- secures ai applications with runtime scanning and vulnerability assessment.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- red team operator
- remove a repository from code security scanning
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- sase
- get code security errors for a specific repository branch
- update the status of a specific data security risk
- ai runtime security scanning and automated red teaming for ai applications.
- get alert
- retrieve a list of cspm alerts based on filters
- list data assets
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- network security engineer
- browser security admin
- remove repository
- list scan integrations
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- create a new cspm security policy
- retrieve a list of data classifications
- tenant operator
- investigates dlp incidents and manages sensitive data protection policies.
- threat intel analyst
- list all ci/cd scan integrations with pagination
- list reports
- dismiss cspm alerts
- update policy
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- get data risk
- retrieve a list of discovered data assets
- subscription manager
- manages multi-tenant security operations at scale for managed service providers.
- cspm
- get data asset
- network operations
- cloud security
- list repositories
- identity and access management, tenant hierarchies, and subscription management.
- soar
- incident responder
- get policy
- list cloud accounts
- update an existing cspm security policy
- get the status of a code security scan
- trigger scan
- update risk status
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- soc analyst
- dismiss alerts
- retrieve a list of dspm data security alerts
- xdr
- onboard a new cloud account
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- ai security engineer
- get errors by branch
- investigates security incidents, triages alerts, and coordinates response actions.
- remove cloud account
- authenticate to prisma cloud and retrieve a jwt token
- compliance team
- enterprise it
- cloud security engineer
- researches threat actors, malware campaigns, and vulnerability trends.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- list policies
- update data risk status
- manages logging infrastructure, integrations, and platform automation.
- network security
- search config
- palo alto networks
- list cspm alerts
- retrieve details for a specific cspm policy
- threat hunter
- monitors and remediates cloud security misconfigurations and compliance violations.
- get scan status
- proactively searches for threats and iocs across telemetry data.
- retrieve a list of all cspm policies
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- data security
- login
- firewall policy management, network objects, and cloud-native firewall configuration.
- list all code security suppressions with pagination and filtering
- sase admin
- list dspm policies
- retrieve a list of all compliance standards
- retrieve details for a specific data security risk
- reopen alerts
- cloud security posture management, compliance monitoring, and workload protection.
- network architect
- compliance
- retrieve details for a specific cspm alert
- add a new repository for code security scanning
- manage enterprise browser policies, user sessions, and deployments.
- get code errors
- get alerts
- search asset
- retrieve a list of all compliance reports
- retrieve a list of data security risks
- iam admin
- remove an onboarded cloud account
- sre
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- digital experience monitoring, log management, and best practice assessment.
- get fix suggestions for pr
- delete suppression
- conducts automated adversarial testing against ai systems and llm applications.
- authenticate
- reopen one or more previously dismissed cspm alerts
- list compliance standards
- platform engineer
- manages multi-tenant hierarchies and service group configurations for mssps.
slug: cloud-security-posture
tags:
- Palo Alto Networks
- Cloud Security
- CSPM
- Compliance
- Data Security
- MSSP
tools:
- description: Authenticate to Prisma Cloud and retrieve a JWT token
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: authenticate
- description: Retrieve a list of CSPM alerts based on filters
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-cspm-alerts
- description: Retrieve details for a specific CSPM alert
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-cspm-alert
- description: Dismiss one or more CSPM alerts
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: dismiss-cspm-alerts
- description: Reopen one or more previously dismissed CSPM alerts
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: reopen-cspm-alerts
- description: Retrieve a list of DSPM data security alerts
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-data-security-alerts
- description: Retrieve a list of all CSPM policies
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-policies
- description: Create a new CSPM security policy
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-policy
- description: Retrieve details for a specific CSPM policy
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-policy
- description: Update an existing CSPM security policy
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-policy
- description: Retrieve a list of DSPM policies
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-dspm-policies
- description: Retrieve a list of all onboarded cloud accounts
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-cloud-accounts
- description: Onboard a new cloud account
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: add-cloud-account
- description: Remove an onboarded cloud account
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: remove-cloud-account
- description: Search for cloud assets using RQL queries
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: search-assets
- description: Search for cloud configuration data using RQL queries
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: search-config
- description: Retrieve a list of all compliance standards
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-compliance-standards
- description: Retrieve a list of all compliance reports
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-reports
- description: List all code security repositories with pagination and filtering
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-repositories
- description: Add a new repository for code security scanning
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: add-repository
- description: Remove a repository from code security scanning
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: remove-repository
- description: List all CI/CD scan integrations with pagination
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-scan-integrations
- description: Trigger a new code security scan for a repository
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: trigger-scan
- description: Get the status of a code security scan
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-scan-status
- description: List all code security suppressions with pagination and filtering
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-suppressions
- description: Create a new code security suppression
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-suppression
- description: Delete a specific code security suppression by ID
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-suppression
- description: Get code security errors for a specific repository branch
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-code-errors
- description: Get fix suggestions for a pull request
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-fix-suggestions
- description: Retrieve a list of discovered data assets
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-data-assets
- description: Retrieve details for a specific data asset
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-data-asset
- description: Retrieve a list of data security risks
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-data-risks
- description: Retrieve details for a specific data security risk
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-data-risk
- description: Update the status of a specific data security risk
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-data-risk-status
- description: Retrieve a list of data stores
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-data-stores
- description: Retrieve a list of data classifications
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-classifications
---
