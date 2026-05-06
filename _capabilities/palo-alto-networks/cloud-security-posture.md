---
categories:
- compliance
consumed_apis: []
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
- mssp operator
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- executes containment, eradication, and recovery actions during security incidents.
- platform engineer
- reopen cspm alerts
- manage enterprise browser policies, user sessions, and deployments.
- remove cloud account
- get risk
- get fix suggestions for pr
- red team operator
- xdr
- add a new repository for code security scanning
- retrieve a list of data classifications
- digital experience monitoring, log management, and best practice assessment.
- cloud security
- dismiss alerts
- monitors network health, performance, and digital experience metrics.
- palo alto networks
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- malware researcher
- retrieve a list of data stores
- list risks
- login
- list cspm alerts
- create a new cspm security policy
- list dspm policies
- add cloud account
- search config
- secures ai applications with runtime scanning and vulnerability assessment.
- sase
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- data loss prevention, saas security monitoring, and identity security posture.
- conducts automated adversarial testing against ai systems and llm applications.
- mssp
- get policy
- network architect
- get code security errors for a specific repository branch
- retrieve a list of data security risks
- sre
- get fix suggestions for a pull request
- compliance team
- manages service accounts, roles, and access policies for platform api access.
- get alerts
- list policies
- ai runtime security scanning and automated red teaming for ai applications.
- subscription manager
- create suppression
- firewall
- get data risk
- delete suppression
- manages multi-tenant security operations at scale for managed service providers.
- dismiss one or more cspm alerts
- analyzes suspicious files and samples for malware characteristics.
- get code errors
- dismiss cspm alerts
- search asset
- cloud security posture management, compliance monitoring, and workload protection.
- saas security admin
- soc analyst
- remove a repository from code security scanning
- list classifications
- get cspm alert
- sd wan operator
- list data stores
- update the status of a specific data security risk
- investigates security incidents, triages alerts, and coordinates response actions.
- tenant operator
- retrieve a list of discovered data assets
- data protection analyst
- iam admin
- list all code security suppressions with pagination and filtering
- list all code security repositories with pagination and filtering
- get alert
- secure access service edge with remote networking, sd-wan, and zero trust access.
- network operations
- designs and implements network security architectures and policies.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- list data assets
- threat intel analyst
- manages enterprise browser policies and secure browsing configurations.
- monitors and remediates cloud security misconfigurations and compliance violations.
- retrieve a list of dspm policies
- enterprise it
- delete a specific code security suppression by id
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- threat hunter
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- authenticate to prisma cloud and retrieve a jwt token
- compliance
- reopen alerts
- researches threat actors, malware campaigns, and vulnerability trends.
- get data asset
- retrieve a list of all onboarded cloud accounts
- trigger a new code security scan for a repository
- list all ci/cd scan integrations with pagination
- sase admin
- list cloud accounts
- proactively searches for threats and iocs across telemetry data.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- vulnerability manager
- remove repository
- manages logging infrastructure, integrations, and platform automation.
- retrieve details for a specific data asset
- data security
- search assets
- update data risk status
- update policy
- incident responder
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- onboard a new cloud account
- retrieve details for a specific cspm policy
- identity and access management, tenant hierarchies, and subscription management.
- list data security alerts
- add repository
- cspm
- network security engineer
- cybersecurity
- get fix suggestions
- investigates dlp incidents and manages sensitive data protection policies.
- retrieve a list of cspm alerts based on filters
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- manages multi-tenant hierarchies and service group configurations for mssps.
- create a new code security suppression
- retrieve a list of dspm data security alerts
- ai security engineer
- browser security admin
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- compliance officer
- enterprise browser policy management and secure browsing.
- firewall policy management, network objects, and cloud-native firewall configuration.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- list data risks
- retrieve a list of all compliance standards
- list repositories
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- soar
- reopen one or more previously dismissed cspm alerts
- list scan integrations
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- list suppressions
- network security
- list reports
- get the status of a code security scan
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- firewall admin
- retrieve details for a specific data security risk
- search for cloud assets using rql queries
- authenticate
- retrieve details for a specific cspm alert
- create policy
- get scan status
- designs sase and sd-wan network architectures for secure remote access.
- update risk status
- cloud security engineer
- search for cloud configuration data using rql queries
- update an existing cspm security policy
- retrieve a list of all cspm policies
- threat intelligence
- list compliance standards
- retrieve a list of all compliance reports
- get errors by branch
- remove an onboarded cloud account
- trigger scan
slug: cloud-security-posture
source_filename: cloud-security-posture.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Palo Alto Networks Cloud Security Posture\n  description: Unified cloud security posture capability for managing alerts, policies, compliance, code security scanning,\n    and data security posture across Prisma Cloud CSPM, Code Security, and DSPM.\n  tags:\n  - Palo Alto Networks\n  - Cloud Security\n  - CSPM\n  - Compliance\n  - Data Security\n  - MSSP\n  created: '2026-04-16'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PRISMA_CLOUD_USERNAME: PRISMA_CLOUD_USERNAME\n    PRISMA_CLOUD_PASSWORD: PRISMA_CLOUD_PASSWORD\n    PRISMA_CLOUD_JWT_TOKEN: PRISMA_CLOUD_JWT_TOKEN\n    PRISMA_CLOUD_TOKEN: PRISMA_CLOUD_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: prisma-cloud-cspm\n    baseUri: https://api.prismacloud.io\n    authentication:\n      type: bearer\n      token: '{{env.PRISMA_CLOUD_JWT_TOKEN}}'\n    resources:\n    - name: login\n      path: /login\n      operations:\n      - name: login\n        method:\
  \ POST\n        description: Authenticate to Prisma Cloud and retrieve a JWT token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            password: '{{tools.password}}'\n            customerName: '{{tools.customer_name}}'\n    - name: alerts\n      path: /alert\n      operations:\n      - name: get-alerts\n        method: GET\n        description: Retrieve a list of alerts based on filters\n        inputParameters:\n        - name: timeType\n          in: query\n          type: string\n          required: false\n        - name: timeAmount\n          in: query\n          type: integer\n          required: false\n        - name: timeUnit\n          in: query\n          type: string\n          required: false\n        - name: startTime\n          in: query\n          type: string\n          required: false\n\
  \        - name: endTime\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: severity\n          in: query\n          type: string\n          required: false\n        - name: policy.id\n          in: query\n          type: string\n          required: false\n        - name: detailed\n          in: query\n          type: boolean\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alert-by-id\n      path: /alert/{id}\n      operations:\n      - name: get-alert\n        method: GET\n        description: Retrieve details for a specific alert\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alert-dismiss\n      path: /alert/dismiss\n      operations:\n      - name: dismiss-alerts\n        method: POST\n        description: Dismiss one or more alerts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            alerts: '{{tools.alerts}}'\n            dismissalNote: '{{tools.dismissal_note}}'\n            dismissalTimeRange: '{{tools.dismissal_time_range}}'\n            filter: '{{tools.filter}}'\n    - name: alert-reopen\n      path: /alert/reopen\n      operations:\n      - name: reopen-alerts\n        method: POST\n        description: Reopen one or more previously dismissed alerts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        body:\n          type: json\n          data:\n            alerts: '{{tools.alerts}}'\n    - name: policies\n      path: /policy\n      operations:\n      - name: list-policies\n        method: GET\n        description: Retrieve a list of all policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-policy\n        method: POST\n        description: Create a new security policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            policyType: '{{tools.policy_type}}'\n            severity: '{{tools.severity}}'\n            rule: '{{tools.rule}}'\n            description: '{{tools.description}}'\n            recommendation: '{{tools.recommendation}}'\n            cloudType: '{{tools.cloud_type}}'\n     \
  \       enabled: '{{tools.enabled}}'\n    - name: policy-by-id\n      path: /policy/{policyId}\n      operations:\n      - name: get-policy\n        method: GET\n        description: Retrieve details for a specific policy\n        inputParameters:\n        - name: policyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-policy\n        method: PUT\n        description: Update an existing security policy\n        inputParameters:\n        - name: policyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            policyType: '{{tools.policy_type}}'\n            severity: '{{tools.severity}}'\n\
  \            rule: '{{tools.rule}}'\n            description: '{{tools.description}}'\n            recommendation: '{{tools.recommendation}}'\n            cloudType: '{{tools.cloud_type}}'\n            enabled: '{{tools.enabled}}'\n    - name: cloud-accounts\n      path: /cloud\n      operations:\n      - name: list-cloud-accounts\n        method: GET\n        description: Retrieve a list of all onboarded cloud accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-account-by-type\n      path: /cloud/{cloudType}\n      operations:\n      - name: add-cloud-account\n        method: POST\n        description: Onboard a new cloud account\n        inputParameters:\n        - name: cloudType\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      \
  \  body:\n          type: json\n          data:\n            accountId: '{{tools.account_id}}'\n            name: '{{tools.name}}'\n            enabled: '{{tools.enabled}}'\n            groupIds: '{{tools.group_ids}}'\n    - name: cloud-account-by-type-and-id\n      path: /cloud/{cloudType}/{id}\n      operations:\n      - name: remove-cloud-account\n        method: DELETE\n        description: Remove an onboarded cloud account\n        inputParameters:\n        - name: cloudType\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-asset\n      path: /search/asset\n      operations:\n      - name: search-asset\n        method: POST\n        description: Search for cloud assets using RQL queries\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            timeRange: '{{tools.time_range}}'\n            limit: '{{tools.limit}}'\n            withResourceJson: '{{tools.with_resource_json}}'\n    - name: search-config\n      path: /search/config\n      operations:\n      - name: search-config\n        method: POST\n        description: Search for cloud configuration data using RQL queries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            timeRange: '{{tools.time_range}}'\n            limit: '{{tools.limit}}'\n            withResourceJson: '{{tools.with_resource_json}}'\n    - name: compliance-standards\n      path: /compliance\n      operations:\n      - name: list-compliance-standards\n    \
  \    method: GET\n        description: Retrieve a list of all compliance standards\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /report\n      operations:\n      - name: list-reports\n        method: GET\n        description: Retrieve a list of all reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: prisma-cloud-code-security\n    baseUri: https://api.prismacloud.io/bridgecrew\n    description: Prisma Cloud Code Security API for managing repositories, scans, suppressions, errors, and fix suggestions.\n    authentication:\n      type: apikey\n      name: x-redlock-auth\n      in: header\n      value: '{{env.PRISMA_CLOUD_TOKEN}}'\n    resources:\n    - name: repositories\n      path: /repositories\n      operations:\n      - name: list-repositories\n        method:\
  \ GET\n        description: List all repositories with pagination and filtering.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: search\n          in: query\n          type: string\n          required: false\n        - name: sourceType\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-repository\n        method: POST\n        description: Add a new repository.\n        inputParameters:\n        - name: id\n          in: body\n          type: string\n          required: true\n        - name: sourceType\n          in: body\n          type: string\n          required: true\n        - name: owner\n          in: body\n          type: string\n\
  \          required: true\n        - name: name\n          in: body\n          type: string\n          required: true\n        - name: defaultBranch\n          in: body\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n            sourceType: '{{tools.sourceType}}'\n            owner: '{{tools.owner}}'\n            name: '{{tools.name}}'\n            defaultBranch: '{{tools.defaultBranch}}'\n      - name: remove-repository\n        method: DELETE\n        description: Remove a repository.\n        inputParameters:\n        - name: id\n          in: body\n          type: string\n          required: true\n        - name: sourceType\n          in: body\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n            sourceType: '{{tools.sourceType}}'\n    - name: scan-integrations\n      path: /scans/integrations\n      operations:\n      - name: list-scan-integrations\n        method: GET\n        description: List all scan integrations with pagination.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scans\n      path: /scans\n      operations:\n      - name: trigger-scan\n        method: POST\n        description: Trigger a new scan for a repository.\n        inputParameters:\n        - name: repositoryId\n          in: body\n          type: string\n\
  \          required: true\n        - name: branch\n          in: body\n          type: string\n          required: true\n        - name: scanTypes\n          in: body\n          type: object\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            repositoryId: '{{tools.repositoryId}}'\n            branch: '{{tools.branch}}'\n            scanTypes: '{{tools.scanTypes}}'\n    - name: scan-status\n      path: /scans/{scan_id}\n      operations:\n      - name: get-scan-status\n        method: GET\n        description: Get the status of a scan.\n        inputParameters:\n        - name: scan_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: suppressions\n      path: /suppressions\n\
  \      operations:\n      - name: list-suppressions\n        method: GET\n        description: List all suppressions with pagination and filtering.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: policyId\n          in: query\n          type: string\n          required: false\n        - name: suppressionType\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-suppression\n        method: POST\n        description: Create a new suppression.\n        inputParameters:\n        - name: policyId\n          in: body\n          type: string\n          required: true\n        - name: suppressionType\n          in: body\n          type: string\n\
  \          required: true\n        - name: justification\n          in: body\n          type: string\n          required: true\n        - name: expirationDate\n          in: body\n          type: string\n          required: false\n        - name: resources\n          in: body\n          type: object\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            policyId: '{{tools.policyId}}'\n            suppressionType: '{{tools.suppressionType}}'\n            justification: '{{tools.justification}}'\n            expirationDate: '{{tools.expirationDate}}'\n            resources: '{{tools.resources}}'\n    - name: suppression\n      path: /suppressions/{suppression_id}\n      operations:\n      - name: delete-suppression\n        method: DELETE\n        description: Delete a specific suppression by ID.\n        inputParameters:\n\
  \        - name: suppression_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: errors-by-branch\n      path: /errors/branch\n      operations:\n      - name: get-errors-by-branch\n        method: GET\n        description: Get errors for a specific repository branch.\n        inputParameters:\n        - name: repositoryId\n          in: query\n          type: string\n          required: true\n        - name: branch\n          in: query\n          type: string\n          required: true\n        - name: severity\n          in: query\n          type: string\n          required: false\n        - name: errorType\n          in: query\n          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: offset\n          in: query\n        \
  \  type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fix-suggestions\n      path: /fixes/pull_request\n      operations:\n      - name: get-fix-suggestions-for-pr\n        method: GET\n        description: Get fix suggestions for a pull request.\n        inputParameters:\n        - name: repositoryId\n          in: query\n          type: string\n          required: true\n        - name: branch\n          in: query\n          type: string\n          required: true\n        - name: filePath\n          in: query\n          type: string\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: prisma-cloud-dspm\n    baseUri: https://api.prismacloud.io\n    authentication:\n      type: bearer\n      token: '{{env.PRISMA_CLOUD_JWT_TOKEN}}'\n    resources:\n    - name: data-assets\n      path: /dspm/api/v1/data-assets\n      operations:\n      - name: list-data-assets\n        method: GET\n        description: Retrieve a list of discovered data assets\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: dataStoreId\n          in: query\n          type: string\n          required: false\n        - name: classificationLabel\n          in: query\n          type: string\n          required: false\n        - name: sensitivityLevel\n          in: query\n          type: string\n\
  \          required: false\n        - name: search\n          in: query\n          type: string\n          required: false\n        - name: sortBy\n          in: query\n          type: string\n          required: false\n        - name: sortOrder\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-asset-by-id\n      path: /dspm/api/v1/data-assets/{id}\n      operations:\n      - name: get-data-asset\n        method: GET\n        description: Retrieve details for a specific data asset\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: risks\n      path: /dspm/api/v1/risks\n      operations:\n      - name: list-risks\n      \
  \  method: GET\n        description: Retrieve a list of data security risks\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: riskLevel\n          in: query\n          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: cloudProvider\n          in: query\n          type: string\n          required: false\n        - name: search\n          in: query\n          type: string\n          required: false\n        - name: sortBy\n          in: query\n          type: string\n          required: false\n        - name: sortOrder\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n    - name: risk-by-id\n      path: /dspm/api/v1/risks/{id}\n      operations:\n      - name: get-risk\n        method: GET\n        description: Retrieve details for a specific risk\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: risk-status\n      path: /dspm/api/v1/risks/{id}/status\n      operations:\n      - name: update-risk-status\n        method: PUT\n        description: Update the status of a specific risk\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n            comment:\
  \ '{{tools.comment}}'\n    - name: data-stores\n      path: /dspm/api/v1/data-stores\n      operations:\n      - name: list-data-stores\n        method: GET\n        description: Retrieve a list of data stores\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: cloudProvider\n          in: query\n          type: string\n          required: false\n        - name: region\n          in: query\n          type: string\n          required: false\n        - name: serviceType\n          in: query\n          type: string\n          required: false\n        - name: riskLevel\n          in: query\n          type: string\n          required: false\n        - name: hasSensitiveData\n          in: query\n          type: boolean\n          required: false\n        - name: search\n          in: query\n          type: string\n\
  \          required: false\n        - name: sortBy\n          in: query\n          type: string\n          required: false\n        - name: sortOrder\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: classifications\n      path: /dspm/api/v1/classifications\n      operations:\n      - name: list-classifications\n        method: GET\n        description: Retrieve a list of data classifications\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: category\n          in: query\n          type: string\n          required: false\n        - name: isBuiltIn\n          in: query\n          type: boolean\n          required: false\n        - name: search\n\
  \          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dspm-policies\n      path: /dspm/api/v1/policies\n      operations:\n      - name: list-dspm-policies\n        method: GET\n        description: Retrieve a list of DSPM policies\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: enabled\n          in: query\n          type: boolean\n          required: false\n        - name: search\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-security-alerts\n      path: /dspm/api/v1/alerts\n \
  \     operations:\n      - name: list-data-security-alerts\n        method: GET\n        description: Retrieve a list of data security alerts\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: severity\n          in: query\n          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: cloudProvider\n          in: query\n          type: string\n          required: false\n        - name: start_time\n          in: query\n          type: string\n          required: false\n        - name: end_time\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n\
  \    namespace: prisma-cloud-mssp\n    baseUri: https://api.prismacloud.io\n    authentication:\n      type: bearer\n      token: '{{env.PALO_ALTO_PRISMA_CLOUD_TOKEN}}'\n    resources:\n    - name: login\n      path: /api/v1/login\n      operations:\n      - name: login\n        method: POST\n        description: Login with username and password.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            password: '{{tools.password}}'\n    - name: mssp-account\n      path: /api/v1/mssp/{mssp_id}\n      operations:\n      - name: get-mssp\n        method: GET\n        description: Get the details of an existing MSSP account.\n        inputParameters:\n        - name: mssp_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: mssp-tos\n      path: /api/v1/mssp/{mssp_id}/tos\n      operations:\n      - name: accept-terms-of-service\n        method: POST\n        description: Accept terms of service for an MSSP.\n        inputParameters:\n        - name: mssp_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mssp-token-refresh\n      path: /api/v1/mssp/{mssp_id}/token-refresh\n      operations:\n      - name: refresh-token\n        method: GET\n        description: Refresh user JWT token.\n        inputParameters:\n        - name: mssp_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mssp-operations\n      path: /api/v1/mssp/{mssp_id}/operation\n\
  \      operations:\n      - name: list-operations\n        method: GET\n        description: Get the operation list for an MSSP.\n        inputParameters:\n        - name: mssp_id\n          in: path\n          type: string\n          required: true\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: show_retried\n          in: query\n          type: boolean\n          required: false\n        - name: nextPageToken\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mssp-operation-retry\n      path: /api/v1/mssp/{mssp_id}/operation/{request_id}/retry\n      operations:\n      - name: retry-operation\n        method: POST\n        description: Retry a failed MSSP operation.\n        inputParameters:\n        - name: mssp_id\n          in: path\n          type: string\n\
  \          required: true\n        - name: request_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            acknowledged: '{{tools.acknowledged}}'\n    - name: mssp-license-pool\n      path: /api/v1/mssp/{mssp_id}/license-pool\n      operations:\n      - name: get-license-pools\n        method: GET\n        description: Get the license pool details of an existing MSSP.\n        inputParameters:\n        - name: mssp_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: license-usage\n      path: /api/v1/license/usage\n      operations:\n      - name: get-license-usage\n        method: POST\n        description: Get the license\
  \ usage for an MSSP.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            timeRange: '{{tools.timeRange}}'\n    - name: license-info\n      path: /api/v1/license/info\n      operations:\n      - name: get-license-info\n        method: GET\n        description: Get the license info for an MSSP.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stack-mapping\n      path: /api/v1/stack-mapping\n      operations:\n      - name: get-stack-mapping\n        method: GET\n        description: Get list of stacks, API hosts, and plan types.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /api/v1/mssp/{mssp_id}/user\n      operations:\n      - name: list-users\n\
  \        method: GET\n        description: List users for a given MSSP console.\n        inputParameters:\n        - name: mssp_id\n          in: path\n          type: string\n          required: true\n        - name: next_page_token\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user under a specific MSSP account.\n        inputParameters:\n        - name: mssp_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n         \
  \   role: '{{tools.role}}'\n      - name: get-user\n        method: GET\n        description: Get user by username.\n        path: /{username}\n        inputParameters:\n        - name: mssp_id\n          in: path\n          type: string\n          required: true\n        - name: username\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PUT\n        description: Update an existing user.\n        path: /{username}\n        inputParameters:\n        - name: mssp_id\n          in: path\n          type: string\n          required: true\n        - name: username\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n        \
  \  data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            role: '{{tools.role}}'\n      - name: delete-user\n        method: DELETE\n        description: Delete an existing user.\n        path: /{username}\n        inputParameters:\n        - name: mssp_id\n          in: path\n          type: string\n          required: true\n        - name: username\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-credential\n      path: /api/v1/user/{username}/credential\n      operations:\n      - name: change-password\n        method: PUT\n        description: Change password for a user.\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n        outputRa\n\n# --- truncated at 32 KB (82 KB total) ---\n# Full source:\
  \ https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/cloud-security-posture.yaml\n"
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
