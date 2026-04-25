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
- monitors and remediates cloud security misconfigurations and compliance violations.
- retrieve details for a specific cspm alert
- network security
- reopen one or more previously dismissed cspm alerts
- firewall
- compliance team
- designs sase and sd-wan network architectures for secure remote access.
- get fix suggestions
- palo alto networks
- saas security admin
- investigates security incidents, triages alerts, and coordinates response actions.
- cloud security
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- dismiss one or more cspm alerts
- get code security errors for a specific repository branch
- trigger a new code security scan for a repository
- create suppression
- list data security alerts
- list repositories
- ai security engineer
- search assets
- get alerts
- search for cloud assets using rql queries
- executes containment, eradication, and recovery actions during security incidents.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- network architect
- data loss prevention, saas security monitoring, and identity security posture.
- manages enterprise browser policies and secure browsing configurations.
- dismiss alerts
- get errors by branch
- retrieve details for a specific cspm policy
- list cloud accounts
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- digital experience monitoring, log management, and best practice assessment.
- reopen cspm alerts
- get cspm alert
- get the status of a code security scan
- tenant operator
- iam admin
- retrieve a list of data security risks
- enterprise it
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- add cloud account
- manages multi-tenant security operations at scale for managed service providers.
- firewall policy management, network objects, and cloud-native firewall configuration.
- compliance
- list compliance standards
- retrieve a list of dspm data security alerts
- conducts automated adversarial testing against ai systems and llm applications.
- trigger scan
- list classifications
- red team operator
- analyzes suspicious files and samples for malware characteristics.
- remove cloud account
- sd wan operator
- proactively searches for threats and iocs across telemetry data.
- firewall admin
- platform engineer
- manage enterprise browser policies, user sessions, and deployments.
- get scan status
- update data risk status
- get data risk
- add repository
- get code errors
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- list dspm policies
- data protection analyst
- sase
- retrieve a list of all cspm policies
- secures ai applications with runtime scanning and vulnerability assessment.
- search asset
- list all code security suppressions with pagination and filtering
- list data risks
- sre
- login
- retrieve details for a specific data security risk
- cloud security engineer
- manages multi-tenant hierarchies and service group configurations for mssps.
- enterprise browser policy management and secure browsing.
- retrieve details for a specific data asset
- authenticate
- delete suppression
- update policy
- monitors network health, performance, and digital experience metrics.
- mssp operator
- manages logging infrastructure, integrations, and platform automation.
- researches threat actors, malware campaigns, and vulnerability trends.
- threat intel analyst
- mssp
- create a new code security suppression
- threat intelligence
- remove an onboarded cloud account
- ai runtime security scanning and automated red teaming for ai applications.
- authenticate to prisma cloud and retrieve a jwt token
- list data assets
- threat hunter
- malware researcher
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- identity and access management, tenant hierarchies, and subscription management.
- get alert
- secure access service edge with remote networking, sd-wan, and zero trust access.
- vulnerability manager
- retrieve a list of all compliance standards
- remove a repository from code security scanning
- get policy
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- retrieve a list of data classifications
- incident responder
- browser security admin
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- list all ci/cd scan integrations with pagination
- reopen alerts
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- soar
- get risk
- retrieve a list of discovered data assets
- get fix suggestions for pr
- update risk status
- create policy
- investigates dlp incidents and manages sensitive data protection policies.
- cloud security posture management, compliance monitoring, and workload protection.
- list cspm alerts
- retrieve a list of all onboarded cloud accounts
- get fix suggestions for a pull request
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- subscription manager
- search for cloud configuration data using rql queries
- create a new cspm security policy
- list reports
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- list data stores
- retrieve a list of cspm alerts based on filters
- data security
- sase admin
- retrieve a list of dspm policies
- list policies
- network security engineer
- onboard a new cloud account
- update an existing cspm security policy
- delete a specific code security suppression by id
- network operations
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- xdr
- remove repository
- list all code security repositories with pagination and filtering
- list suppressions
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- manages service accounts, roles, and access policies for platform api access.
- soc analyst
- retrieve a list of data stores
- cybersecurity
- designs and implements network security architectures and policies.
- dismiss cspm alerts
- list risks
- list scan integrations
- compliance officer
- retrieve a list of all compliance reports
- cspm
- add a new repository for code security scanning
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- update the status of a specific data security risk
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- get data asset
- search config
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
