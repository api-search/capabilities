---
categories:
- compliance
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
- get data asset
- xdr
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- list risks
- update the status of a specific data security risk
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- secures ai applications with runtime scanning and vulnerability assessment.
- tenant operator
- red team operator
- firewall policy management, network objects, and cloud-native firewall configuration.
- get errors by branch
- authenticate
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- soar
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- ai security engineer
- list policies
- get data risk
- list reports
- compliance officer
- dismiss alerts
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- sre
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- retrieve details for a specific cspm alert
- cloud security
- get fix suggestions for a pull request
- list data stores
- firewall
- search for cloud configuration data using rql queries
- retrieve a list of all compliance reports
- get code security errors for a specific repository branch
- platform engineer
- search for cloud assets using rql queries
- dismiss one or more cspm alerts
- compliance
- sase
- analyzes suspicious files and samples for malware characteristics.
- get fix suggestions for pr
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- designs and implements network security architectures and policies.
- incident responder
- identity and access management, tenant hierarchies, and subscription management.
- retrieve a list of all cspm policies
- list all code security repositories with pagination and filtering
- retrieve details for a specific data asset
- list classifications
- retrieve a list of dspm data security alerts
- list compliance standards
- data security
- get alert
- vulnerability manager
- add repository
- list data risks
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- compliance team
- get fix suggestions
- list suppressions
- reopen alerts
- trigger a new code security scan for a repository
- get code errors
- cloud security engineer
- saas security admin
- retrieve a list of all onboarded cloud accounts
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- manages multi-tenant security operations at scale for managed service providers.
- sd wan operator
- retrieve a list of all compliance standards
- list data assets
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- remove repository
- subscription manager
- retrieve a list of data security risks
- delete suppression
- ai runtime security scanning and automated red teaming for ai applications.
- login
- executes containment, eradication, and recovery actions during security incidents.
- proactively searches for threats and iocs across telemetry data.
- create a new cspm security policy
- dismiss cspm alerts
- trigger scan
- investigates security incidents, triages alerts, and coordinates response actions.
- search assets
- list cloud accounts
- add cloud account
- retrieve a list of data classifications
- list dspm policies
- researches threat actors, malware campaigns, and vulnerability trends.
- list data security alerts
- list repositories
- soc analyst
- network security
- network operations
- enterprise browser policy management and secure browsing.
- manages multi-tenant hierarchies and service group configurations for mssps.
- update an existing cspm security policy
- list scan integrations
- authenticate to prisma cloud and retrieve a jwt token
- get the status of a code security scan
- remove cloud account
- threat intel analyst
- monitors and remediates cloud security misconfigurations and compliance violations.
- retrieve details for a specific data security risk
- manages service accounts, roles, and access policies for platform api access.
- remove a repository from code security scanning
- threat hunter
- enterprise it
- browser security admin
- get risk
- network security engineer
- update data risk status
- malware researcher
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- manages enterprise browser policies and secure browsing configurations.
- update policy
- cspm
- create suppression
- get scan status
- retrieve a list of dspm policies
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- retrieve a list of data stores
- manage enterprise browser policies, user sessions, and deployments.
- search config
- mssp operator
- cybersecurity
- network architect
- create policy
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- reopen cspm alerts
- mssp
- delete a specific code security suppression by id
- digital experience monitoring, log management, and best practice assessment.
- sase admin
- designs sase and sd-wan network architectures for secure remote access.
- get policy
- get cspm alert
- data protection analyst
- remove an onboarded cloud account
- monitors network health, performance, and digital experience metrics.
- add a new repository for code security scanning
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- palo alto networks
- retrieve a list of cspm alerts based on filters
- update risk status
- create a new code security suppression
- data loss prevention, saas security monitoring, and identity security posture.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- investigates dlp incidents and manages sensitive data protection policies.
- retrieve a list of discovered data assets
- firewall admin
- list all code security suppressions with pagination and filtering
- search asset
- iam admin
- manages logging infrastructure, integrations, and platform automation.
- reopen one or more previously dismissed cspm alerts
- list cspm alerts
- threat intelligence
- onboard a new cloud account
- cloud security posture management, compliance monitoring, and workload protection.
- conducts automated adversarial testing against ai systems and llm applications.
- list all ci/cd scan integrations with pagination
- get alerts
- retrieve details for a specific cspm policy
slug: cloud-security-posture
source_filename: cloud-security-posture.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Palo Alto Networks Cloud Security Posture\"\n  description: \"Unified cloud security posture capability for managing alerts, policies, compliance, code security scanning, and data security posture across Prisma Cloud CSPM, Code Security, and DSPM.\"\n  tags:\n    - Palo Alto Networks\n    - Cloud Security\n    - CSPM\n    - Compliance\n    - Data Security\n    - MSSP\n  created: \"2026-04-16\"\n  modified: \"2026-04-16\"\n\nbinds:\n  - namespace: env\n    keys:\n      PRISMA_CLOUD_USERNAME: PRISMA_CLOUD_USERNAME\n      PRISMA_CLOUD_PASSWORD: PRISMA_CLOUD_PASSWORD\n      PRISMA_CLOUD_JWT_TOKEN: PRISMA_CLOUD_JWT_TOKEN\n      PRISMA_CLOUD_TOKEN: PRISMA_CLOUD_TOKEN\n\ncapability:\n  consumes:\n    - import: prisma-cloud-cspm\n      location: ./shared/prisma-cloud-cspm.yaml\n    - import: prisma-cloud-code-security\n      location: ./shared/prisma-cloud-code-security.yaml\n    - import: prisma-cloud-dspm\n      location: ./shared/prisma-cloud-dspm.yaml\n\
  \    - import: prisma-cloud-mssp\n      location: ./shared/prisma-cloud-mssp.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: rest-cloud-security-posture\n      resources:\n\n        # ── Authentication ──────────────────────────────────────────────\n        - path: /v1/auth/login\n          operations:\n            - method: POST\n              name: login\n              call: \"prisma-cloud-cspm.login\"\n              with:\n                username: \"rest.username\"\n                password: \"rest.password\"\n                customer_name: \"rest.customer_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── Alerts & Incidents ──────────────────────────────────────────\n        - path: /v1/alerts\n          operations:\n            - method: GET\n              name: get-alerts\n              call: \"prisma-cloud-cspm.get-alerts\"\n              with:\n                timeType: \"rest.timeType\"\
  \n                timeAmount: \"rest.timeAmount\"\n                timeUnit: \"rest.timeUnit\"\n                startTime: \"rest.startTime\"\n                endTime: \"rest.endTime\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n                severity: \"rest.severity\"\n                policy.id: \"rest.policy.id\"\n                detailed: \"rest.detailed\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/alerts/{id}\n          operations:\n            - method: GET\n              name: get-alert\n              call: \"prisma-cloud-cspm.get-alert\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alerts/dismiss\n          operations:\n            - method: POST\n              name: dismiss-alerts\n              call: \"prisma-cloud-cspm.dismiss-alerts\"\
  \n              with:\n                alerts: \"rest.alerts\"\n                dismissal_note: \"rest.dismissal_note\"\n                dismissal_time_range: \"rest.dismissal_time_range\"\n                filter: \"rest.filter\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alerts/reopen\n          operations:\n            - method: POST\n              name: reopen-alerts\n              call: \"prisma-cloud-cspm.reopen-alerts\"\n              with:\n                alerts: \"rest.alerts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/data-security-alerts\n          operations:\n            - method: GET\n              name: list-data-security-alerts\n              call: \"prisma-cloud-dspm.list-data-security-alerts\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n               \
  \ severity: \"rest.severity\"\n                status: \"rest.status\"\n                cloudProvider: \"rest.cloudProvider\"\n                start_time: \"rest.start_time\"\n                end_time: \"rest.end_time\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        # ── Policies ────────────────────────────────────────────────────\n        - path: /v1/policies\n          operations:\n            - method: GET\n              name: list-policies\n              call: \"prisma-cloud-cspm.list-policies\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-policy\n              call: \"prisma-cloud-cspm.create-policy\"\n              with:\n                name: \"rest.name\"\n                policy_type: \"rest.policy_type\"\n                severity: \"rest.severity\"\n                rule: \"rest.rule\"\n                description:\
  \ \"rest.description\"\n                recommendation: \"rest.recommendation\"\n                cloud_type: \"rest.cloud_type\"\n                enabled: \"rest.enabled\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/policies/{policyId}\n          operations:\n            - method: GET\n              name: get-policy\n              call: \"prisma-cloud-cspm.get-policy\"\n              with:\n                policyId: \"rest.policyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: PUT\n              name: update-policy\n              call: \"prisma-cloud-cspm.update-policy\"\n              with:\n                policyId: \"rest.policyId\"\n                name: \"rest.name\"\n                policy_type: \"rest.policy_type\"\n                severity: \"rest.severity\"\n                rule: \"rest.rule\"\n                description:\
  \ \"rest.description\"\n                recommendation: \"rest.recommendation\"\n                cloud_type: \"rest.cloud_type\"\n                enabled: \"rest.enabled\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/dspm-policies\n          operations:\n            - method: GET\n              name: list-dspm-policies\n              call: \"prisma-cloud-dspm.list-dspm-policies\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n                enabled: \"rest.enabled\"\n                search: \"rest.search\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        # ── Cloud Accounts ──────────────────────────────────────────────\n        - path: /v1/cloud-accounts\n          operations:\n            - method: GET\n              name: list-cloud-accounts\n              call: \"prisma-cloud-cspm.list-cloud-accounts\"\
  \n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/cloud-accounts/{cloudType}\n          operations:\n            - method: POST\n              name: add-cloud-account\n              call: \"prisma-cloud-cspm.add-cloud-account\"\n              with:\n                cloudType: \"rest.cloudType\"\n                account_id: \"rest.account_id\"\n                name: \"rest.name\"\n                enabled: \"rest.enabled\"\n                group_ids: \"rest.group_ids\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cloud-accounts/{cloudType}/{id}\n          operations:\n            - method: DELETE\n              name: remove-cloud-account\n              call: \"prisma-cloud-cspm.remove-cloud-account\"\n              with:\n                cloudType: \"rest.cloudType\"\n                id: \"rest.id\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n\n        # ── Search & Query ──────────────────────────────────────────────\n        - path: /v1/search/assets\n          operations:\n            - method: POST\n              name: search-asset\n              call: \"prisma-cloud-cspm.search-asset\"\n              with:\n                query: \"rest.query\"\n                time_range: \"rest.time_range\"\n                limit: \"rest.limit\"\n                with_resource_json: \"rest.with_resource_json\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/search/config\n          operations:\n            - method: POST\n              name: search-config\n              call: \"prisma-cloud-cspm.search-config\"\n              with:\n                query: \"rest.query\"\n                time_range: \"rest.time_range\"\n                limit: \"rest.limit\"\n                with_resource_json: \"rest.with_resource_json\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── Compliance ──────────────────────────────────────────────────\n        - path: /v1/compliance-standards\n          operations:\n            - method: GET\n              name: list-compliance-standards\n              call: \"prisma-cloud-cspm.list-compliance-standards\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/reports\n          operations:\n            - method: GET\n              name: list-reports\n              call: \"prisma-cloud-cspm.list-reports\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        # ── Code Security ───────────────────────────────────────────────\n        - path: /v1/repositories\n          operations:\n            - method: GET\n              name: list-repositories\n              call: \"prisma-cloud-code-security.list-repositories\"\
  \n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n                search: \"rest.search\"\n                sourceType: \"rest.sourceType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: add-repository\n              call: \"prisma-cloud-code-security.add-repository\"\n              with:\n                id: \"rest.id\"\n                sourceType: \"rest.sourceType\"\n                owner: \"rest.owner\"\n                name: \"rest.name\"\n                defaultBranch: \"rest.defaultBranch\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: DELETE\n              name: remove-repository\n              call: \"prisma-cloud-code-security.remove-repository\"\n              with:\n                id: \"rest.id\"\n                sourceType: \"rest.sourceType\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/scan-integrations\n          operations:\n            - method: GET\n              name: list-scan-integrations\n              call: \"prisma-cloud-code-security.list-scan-integrations\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/scans\n          operations:\n            - method: POST\n              name: trigger-scan\n              call: \"prisma-cloud-code-security.trigger-scan\"\n              with:\n                repositoryId: \"rest.repositoryId\"\n                branch: \"rest.branch\"\n                scanTypes: \"rest.scanTypes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/scans/{scan_id}\n      \
  \    operations:\n            - method: GET\n              name: get-scan-status\n              call: \"prisma-cloud-code-security.get-scan-status\"\n              with:\n                scan_id: \"rest.scan_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/suppressions\n          operations:\n            - method: GET\n              name: list-suppressions\n              call: \"prisma-cloud-code-security.list-suppressions\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n                policyId: \"rest.policyId\"\n                suppressionType: \"rest.suppressionType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-suppression\n              call: \"prisma-cloud-code-security.create-suppression\"\n              with:\n                policyId:\
  \ \"rest.policyId\"\n                suppressionType: \"rest.suppressionType\"\n                justification: \"rest.justification\"\n                expirationDate: \"rest.expirationDate\"\n                resources: \"rest.resources\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/suppressions/{suppression_id}\n          operations:\n            - method: DELETE\n              name: delete-suppression\n              call: \"prisma-cloud-code-security.delete-suppression\"\n              with:\n                suppression_id: \"rest.suppression_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/code-errors\n          operations:\n            - method: GET\n              name: get-errors-by-branch\n              call: \"prisma-cloud-code-security.get-errors-by-branch\"\n              with:\n                repositoryId: \"rest.repositoryId\"\
  \n                branch: \"rest.branch\"\n                severity: \"rest.severity\"\n                errorType: \"rest.errorType\"\n                status: \"rest.status\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/fix-suggestions\n          operations:\n            - method: GET\n              name: get-fix-suggestions-for-pr\n              call: \"prisma-cloud-code-security.get-fix-suggestions-for-pr\"\n              with:\n                repositoryId: \"rest.repositoryId\"\n                branch: \"rest.branch\"\n                filePath: \"rest.filePath\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── Data Security Posture ───────────────────────────────────────\n        -\
  \ path: /v1/data-assets\n          operations:\n            - method: GET\n              name: list-data-assets\n              call: \"prisma-cloud-dspm.list-data-assets\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n                dataStoreId: \"rest.dataStoreId\"\n                classificationLabel: \"rest.classificationLabel\"\n                sensitivityLevel: \"rest.sensitivityLevel\"\n                search: \"rest.search\"\n                sortBy: \"rest.sortBy\"\n                sortOrder: \"rest.sortOrder\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/data-assets/{id}\n          operations:\n            - method: GET\n              name: get-data-asset\n              call: \"prisma-cloud-dspm.get-data-asset\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n               \
  \   mapping: \"$.\"\n\n        - path: /v1/data-risks\n          operations:\n            - method: GET\n              name: list-risks\n              call: \"prisma-cloud-dspm.list-risks\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n                riskLevel: \"rest.riskLevel\"\n                status: \"rest.status\"\n                cloudProvider: \"rest.cloudProvider\"\n                search: \"rest.search\"\n                sortBy: \"rest.sortBy\"\n                sortOrder: \"rest.sortOrder\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/data-risks/{id}\n          operations:\n            - method: GET\n              name: get-risk\n              call: \"prisma-cloud-dspm.get-risk\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        -\
  \ path: /v1/data-risks/{id}/status\n          operations:\n            - method: PUT\n              name: update-risk-status\n              call: \"prisma-cloud-dspm.update-risk-status\"\n              with:\n                id: \"rest.id\"\n                status: \"rest.status\"\n                comment: \"rest.comment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/data-stores\n          operations:\n            - method: GET\n              name: list-data-stores\n              call: \"prisma-cloud-dspm.list-data-stores\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n                cloudProvider: \"rest.cloudProvider\"\n                region: \"rest.region\"\n                serviceType: \"rest.serviceType\"\n                riskLevel: \"rest.riskLevel\"\n                hasSensitiveData: \"rest.hasSensitiveData\"\n                search: \"rest.search\"\
  \n                sortBy: \"rest.sortBy\"\n                sortOrder: \"rest.sortOrder\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/classifications\n          operations:\n            - method: GET\n              name: list-classifications\n              call: \"prisma-cloud-dspm.list-classifications\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n                category: \"rest.category\"\n                isBuiltIn: \"rest.isBuiltIn\"\n                search: \"rest.search\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: mcp-cloud-security-posture\n      transport: http\n      tools:\n\n        # ── Authentication ──────────────────────────────────────────────\n        - name: authenticate\n          description: \"Authenticate to Prisma Cloud and\
  \ retrieve a JWT token\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: username\n              type: string\n              required: true\n            - name: password\n              type: string\n              required: true\n            - name: customer_name\n              type: string\n              required: true\n          call: \"prisma-cloud-cspm.login\"\n          with:\n            username: \"tools.username\"\n            password: \"tools.password\"\n            customer_name: \"tools.customer_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # ── Cloud Posture Alerts ────────────────────────────────────────\n        - name: list-cspm-alerts\n          description: \"Retrieve a list of CSPM alerts based on filters\"\n          hints:\n            readOnly: true\n            destructive:\
  \ false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: timeType\n              type: string\n              required: false\n            - name: timeAmount\n              type: integer\n              required: false\n            - name: timeUnit\n              type: string\n              required: false\n            - name: startTime\n              type: string\n              required: false\n            - name: endTime\n              type: string\n              required: false\n            - name: limit\n              type: integer\n              required: false\n            - name: offset\n              type: integer\n              required: false\n            - name: severity\n              type: string\n              required: false\n            - name: policy_id\n              type: string\n              required: false\n            - name: detailed\n              type: boolean\n              required: false\n          call:\
  \ \"prisma-cloud-cspm.get-alerts\"\n          with:\n            timeType: \"tools.timeType\"\n            timeAmount: \"tools.timeAmount\"\n            timeUnit: \"tools.timeUnit\"\n            startTime: \"tools.startTime\"\n            endTime: \"tools.endTime\"\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n            severity: \"tools.severity\"\n            policy.id: \"tools.policy_id\"\n            detailed: \"tools.detailed\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-cspm-alert\n          description: \"Retrieve details for a specific CSPM alert\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n          call: \"prisma-cloud-cspm.get-alert\"\n          with:\n            id: \"tools.id\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: dismiss-cspm-alerts\n          description: \"Dismiss one or more CSPM alerts\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: alerts\n              type: object\n              required: true\n            - name: dismissal_note\n              type: string\n              required: false\n            - name: dismissal_time_range\n              type: object\n              required: false\n            - name: filter\n              type: object\n              required: false\n          call: \"prisma-cloud-cspm.dismiss-alerts\"\n          with:\n            alerts: \"tools.alerts\"\n            dismissal_note: \"tools.dismissal_note\"\n            dismissal_time_range: \"tools.dismissal_time_range\"\n            filter: \"tools.filter\"\n       \
  \   outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: reopen-cspm-alerts\n          description: \"Reopen one or more previously dismissed CSPM alerts\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: alerts\n              type: object\n              required: true\n          call: \"prisma-cloud-cspm.reopen-alerts\"\n          with:\n            alerts: \"tools.alerts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-data-security-alerts\n          description: \"Retrieve a list of DSPM data security alerts\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: offset\n              type: integer\n          \
  \    required: false\n            - name: limit\n              type: integer\n              required: false\n            - name: severity\n              type: string\n              required: false\n            - name: status\n              type: string\n              required: false\n            - name: cloudProvider\n              type: string\n              required: false\n            - name: start_time\n              type: string\n              required: false\n            - name: end_time\n              type: string\n              required: false\n          call: \"prisma-cloud-dspm.list-data-security-alerts\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n            severity: \"tools.severity\"\n            status: \"tools.status\"\n            cloudProvider: \"tools.cloudProvider\"\n            start_time: \"tools.start_time\"\n            end_time: \"tools.end_time\"\n          outputParameters:\n            - type: array\n        \
  \      mapping: \"$.\"\n\n        # ── Policy Management ───────────────────────────────────────────\n        - name: list-policies\n          description: \"Retrieve a list of all CSPM policies\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"prisma-cloud-cspm.list-policies\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-policy\n          description: \"Create a new CSPM security policy\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n            - name: policy_type\n              type: string\n              required: true\n            - name: severity\n              type: string\n              required: true\n\
  \            - name: rule\n              type: object\n              required: true\n            - name: description\n              type: string\n              required: false\n            - name: recommendation\n              type: string\n              required: false\n            - name: cloud_type\n              type: string\n              required: false\n            - name: enabled\n              type: boolean\n              required: false\n          call: \"prisma-cloud-cspm.create-policy\"\n          with:\n            name: \"tools.name\"\n            policy_type: \"tools.policy_type\"\n            severity: \"tools.severity\"\n            rule: \"tools.rule\"\n            description: \"tools.description\"\n            recommendation: \"tools.recommendation\"\n            cloud_type: \"tools.cloud_type\"\n            enabled: \"tools.enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-policy\n          description:\
  \ \"Retrieve details for a specific CSPM policy\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: policyId\n              type: string\n              required: true\n          call: \"prisma-cloud-cspm.get-policy\"\n          with:\n            policyId: \"tools.policyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-policy\n          description: \"Update an existing CSPM security policy\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: policyId\n              type: string\n              required: true\n            - name: name\n              type: string\n              required: true\n            - name: policy_type\n              type: string\n\
  \              required: true\n            - name: severity\n              type: string\n              required: true\n            - name: rule\n              type: object\n              required: true\n            - name: description\n              type: string\n              required: false\n            - name: recommendation\n              type: string\n              required: false\n            - name: cloud_type\n              type: string\n              required: false\n            - name: enabled\n              type: boolean\n              required: false\n          call: \"prisma-cloud-cspm.update-policy\"\n          with:\n            policyId: \"tools.policyId\"\n            name: \"tools.name\"\n            policy_type: \"tools.policy_type\"\n            severity: \"tools.severity\"\n            rule: \"tools.rule\"\n            description: \"tools.description\"\n            recommendation: \"tools.recommendation\"\n            cloud_type: \"tools.cloud_type\"\n           \
  \ enabled: \"tools.enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-dspm-policies\n          description: \"Retrieve a list of DSPM policies\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n            - name: enabled\n              type: boolean\n              required: false\n            - name: search\n              type: string\n              required: false\n          call: \"prisma-cloud-dspm.list-dspm-policies\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n            enabled: \"tools.enabled\"\n            search: \"tools.search\"\n          outputParameters:\n          \
  \  - type: array\n              mapping: \"$.\"\n\n        # ── Cloud Accounts ──────────────────────────────────────────────\n        - name: list-cloud-accounts\n          description: \"Retrieve a list of all onboarded cloud accounts\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"prisma-cloud-cspm.list-cloud-accounts\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: add-cloud-account\n          description: \"Onboard a new cloud account\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: cloudType\n              type: string\n              required: true\n            - name: account_id\n              type: string\n              required: true\n            - name: name\n           \
  \   type: string\n              required: true\n            - name: enabled\n              type: boolean\n              required: false\n            - name: group_ids\n              type: object\n              required: false\n          call: \"prisma-cloud-cspm.add-cloud-account\"\n          with:\n            cloudType: \"tools.cloudType\"\n            account_id: \"tools.account_id\"\n            name: \"tools.name\"\n            enabled: \"tools.enabled\"\n            group_ids: \"tools.group_ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: remove-cloud-account\n          description: \"Remove an onboarded cloud account\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: cloudType\n              type: string\n              required: true\n            - name: id\n              type: string\n\
  \              required: true\n          call: \"prisma-cloud-cspm.remove-cloud-account\"\n          with:\n            cloudType: \"tools.cloudType\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # ── Asset Search ────────────────────────────────────────────────\n        - name: search-assets\n          description: \"Search for cloud assets using RQL queries\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: query\n              type: string\n              required: true\n            - name: time_range\n              type: object\n              required: false\n            - name: limit\n              type: integer\n              required: false\n            - name: with_resource_json\n              type: boolean\n              required: false\n          call: \"prisma-cloud-cspm.search-asset\"\
  \n          wi\n\n# --- truncated at 32 KB (50 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/cloud-security-posture.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/cloud-security-posture.yaml
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
