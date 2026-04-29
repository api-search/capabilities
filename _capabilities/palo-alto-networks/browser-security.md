---
categories: []
consumed_apis:
- prisma-access-browser
description: Browser security capability for managing enterprise browser policies, user sessions, and deployments through the Prisma Access Browser API.
layout: capability
name: Palo Alto Networks Browser Security
operations:
- description: List all browser policies with pagination.
  method: GET
  name: list-browser-policies
  path: /v1/browser-policies
- description: Create a new browser policy.
  method: POST
  name: create-browser-policy
  path: /v1/browser-policies
- description: Get a specific browser policy by ID.
  method: GET
  name: get-browser-policy
  path: /v1/browser-policies/{policy_id}
- description: Update a specific browser policy by ID.
  method: PUT
  name: update-browser-policy
  path: /v1/browser-policies/{policy_id}
- description: Delete a specific browser policy by ID.
  method: DELETE
  name: delete-browser-policy
  path: /v1/browser-policies/{policy_id}
- description: List all browser users with pagination.
  method: GET
  name: list-browser-users
  path: /v1/browser-users
- description: Get sessions for a specific user.
  method: GET
  name: get-user-sessions
  path: /v1/browser-users/{user_id}/sessions
- description: List all browser deployments with pagination.
  method: GET
  name: list-browser-deployments
  path: /v1/browser-deployments
- description: Create a new browser deployment.
  method: POST
  name: create-browser-deployment
  path: /v1/browser-deployments
personas:
- description: Manages enterprise browser policies and secure browsing configurations.
  id: browser-security-admin
  name: Browser Security Admin
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- get user sessions
- executes containment, eradication, and recovery actions during security incidents.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- list browser deployments
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- list enterprise browser users.
- firewall policy management, network objects, and cloud-native firewall configuration.
- tenant operator
- cloud security engineer
- digital experience monitoring, log management, and best practice assessment.
- network security engineer
- threat intelligence
- malware researcher
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- manage a specific browser policy by id.
- network operations
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- browser security
- ai runtime security scanning and automated red teaming for ai applications.
- enterprise browser
- cloud security posture management, compliance monitoring, and workload protection.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- threat intel analyst
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- list browser users
- prisma access
- get a specific browser policy by id.
- get sessions for a specific browser user.
- monitors network health, performance, and digital experience metrics.
- secures ai applications with runtime scanning and vulnerability assessment.
- manage enterprise browser security policies.
- compliance officer
- create a new browser deployment.
- firewall admin
- red team operator
- conducts automated adversarial testing against ai systems and llm applications.
- xdr
- saas security admin
- platform engineer
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- manages logging infrastructure, integrations, and platform automation.
- delete a specific browser policy by id.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- iam admin
- incident responder
- subscription manager
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- designs and implements network security architectures and policies.
- investigates security incidents, triages alerts, and coordinates response actions.
- mssp operator
- compliance team
- manages service accounts, roles, and access policies for platform api access.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- identity and access management, tenant hierarchies, and subscription management.
- analyzes suspicious files and samples for malware characteristics.
- manages enterprise browser policies and secure browsing configurations.
- soc analyst
- vulnerability manager
- designs sase and sd-wan network architectures for secure remote access.
- enterprise browser policy management and secure browsing.
- palo alto networks
- update a specific browser policy by id.
- sre
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- create browser deployment
- list all browser policies with pagination.
- network security
- ai security engineer
- threat hunter
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- enterprise it
- soar
- data protection analyst
- list all browser users with pagination.
- manage enterprise browser policies, user sessions, and deployments.
- list all browser deployments with pagination.
- investigates dlp incidents and manages sensitive data protection policies.
- get sessions for a specific user.
- list browser policies
- cybersecurity
- network architect
- delete browser policy
- data loss prevention, saas security monitoring, and identity security posture.
- monitors and remediates cloud security misconfigurations and compliance violations.
- manages multi-tenant hierarchies and service group configurations for mssps.
- browser security admin
- sase
- sd wan operator
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- firewall
- manages multi-tenant security operations at scale for managed service providers.
- cloud security
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- update browser policy
- researches threat actors, malware campaigns, and vulnerability trends.
- create a new browser policy.
- get browser policy
- sase admin
- proactively searches for threats and iocs across telemetry data.
- manage browser deployments across platforms.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- create browser policy
slug: browser-security
source_filename: browser-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Palo Alto Networks Browser Security\"\n  description: \"Browser security capability for managing enterprise browser policies, user sessions, and deployments through the Prisma Access Browser API.\"\n  tags:\n    - Palo Alto Networks\n    - Browser Security\n    - Enterprise Browser\n    - Prisma Access\n  created: \"2026-04-16\"\n  modified: \"2026-04-16\"\n\nbinds:\n  - namespace: env\n    keys:\n      PALO_ALTO_OAUTH_TOKEN: PALO_ALTO_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: prisma-access-browser\n      location: ./shared/prisma-access-browser.yaml\n\n  exposes:\n    - type: rest\n      port: 8089\n      namespace: browser-security-rest\n      description: \"REST API for managing enterprise browser security policies, users, and deployments.\"\n      resources:\n\n        # -- Browser Policies ------------------------------------------------\n        - path: /v1/browser-policies\n          name: browser-policies\n\
  \          description: \"Manage enterprise browser security policies.\"\n          operations:\n            - method: GET\n              name: list-browser-policies\n              description: \"List all browser policies with pagination.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"prisma-access-browser.list-browser-policies\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-browser-policy\n              description: \"Create a new browser policy.\"\n              inputParameters:\n                - name: name\n    \
  \              in: body\n                  type: string\n                  required: true\n                - name: rules\n                  in: body\n                  type: object\n                  required: true\n                - name: enabled\n                  in: body\n                  type: boolean\n                  required: true\n              call: \"prisma-access-browser.create-browser-policy\"\n              with:\n                name: \"rest.name\"\n                rules: \"rest.rules\"\n                enabled: \"rest.enabled\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/browser-policies/{policy_id}\n          name: browser-policy\n          description: \"Manage a specific browser policy by ID.\"\n          operations:\n            - method: GET\n              name: get-browser-policy\n              description: \"Get a specific browser policy by ID.\"\n              inputParameters:\n   \
  \             - name: policy_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-access-browser.get-browser-policy\"\n              with:\n                policy_id: \"rest.policy_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-browser-policy\n              description: \"Update a specific browser policy by ID.\"\n              inputParameters:\n                - name: policy_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-access-browser.update-browser-policy\"\n              with:\n                policy_id: \"rest.policy_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-browser-policy\n              description:\
  \ \"Delete a specific browser policy by ID.\"\n              inputParameters:\n                - name: policy_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-access-browser.delete-browser-policy\"\n              with:\n                policy_id: \"rest.policy_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -- Browser Users ---------------------------------------------------\n        - path: /v1/browser-users\n          name: browser-users\n          description: \"List enterprise browser users.\"\n          operations:\n            - method: GET\n              name: list-browser-users\n              description: \"List all browser users with pagination.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n\
  \                  in: query\n                  type: integer\n                  required: false\n              call: \"prisma-access-browser.list-browser-users\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/browser-users/{user_id}/sessions\n          name: user-sessions\n          description: \"Get sessions for a specific browser user.\"\n          operations:\n            - method: GET\n              name: get-user-sessions\n              description: \"Get sessions for a specific user.\"\n              inputParameters:\n                - name: user_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-access-browser.get-user-sessions\"\n              with:\n                user_id: \"rest.user_id\"\n              outputParameters:\n \
  \               - type: object\n                  mapping: \"$.\"\n\n        # -- Deployments -----------------------------------------------------\n        - path: /v1/browser-deployments\n          name: browser-deployments\n          description: \"Manage browser deployments across platforms.\"\n          operations:\n            - method: GET\n              name: list-browser-deployments\n              description: \"List all browser deployments with pagination.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"prisma-access-browser.list-deployments\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n      \
  \            mapping: \"$.\"\n            - method: POST\n              name: create-browser-deployment\n              description: \"Create a new browser deployment.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: platform\n                  in: body\n                  type: string\n                  required: true\n                - name: settings\n                  in: body\n                  type: object\n                  required: true\n              call: \"prisma-access-browser.create-deployment\"\n              with:\n                name: \"rest.name\"\n                platform: \"rest.platform\"\n                settings: \"rest.settings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9099\n      namespace: browser-security-mcp\n      transport: http\n     \
  \ description: \"MCP server for AI-assisted enterprise browser security management.\"\n      tools:\n\n        # -- Browser Policies ------------------------------------------------\n        - name: list-browser-policies\n          description: \"List all browser policies with pagination.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"prisma-access-browser.list-browser-policies\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-browser-policy\n          description: \"Create a new browser policy.\"\n          hints:\n      \
  \      readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n            - name: rules\n              type: object\n              required: true\n            - name: enabled\n              type: boolean\n              required: true\n          call: \"prisma-access-browser.create-browser-policy\"\n          with:\n            name: \"tools.name\"\n            rules: \"tools.rules\"\n            enabled: \"tools.enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-browser-policy\n          description: \"Get a specific browser policy by ID.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: policy_id\n              type:\
  \ string\n              required: true\n          call: \"prisma-access-browser.get-browser-policy\"\n          with:\n            policy_id: \"tools.policy_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-browser-policy\n          description: \"Update a specific browser policy by ID.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: policy_id\n              type: string\n              required: true\n          call: \"prisma-access-browser.update-browser-policy\"\n          with:\n            policy_id: \"tools.policy_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-browser-policy\n          description: \"Delete a specific browser policy by ID.\"\n          hints:\n            readOnly: false\n            destructive:\
  \ true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: policy_id\n              type: string\n              required: true\n          call: \"prisma-access-browser.delete-browser-policy\"\n          with:\n            policy_id: \"tools.policy_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # -- Browser Users ---------------------------------------------------\n        - name: list-browser-users\n          description: \"List all browser users with pagination.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"prisma-access-browser.list-browser-users\"\n          with:\n\
  \            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user-sessions\n          description: \"Get sessions for a specific user.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: user_id\n              type: string\n              required: true\n          call: \"prisma-access-browser.get-user-sessions\"\n          with:\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # -- Deployments -----------------------------------------------------\n        - name: list-browser-deployments\n          description: \"List all browser deployments with pagination.\"\n          hints:\n            readOnly: true\n            destructive: false\n   \
  \         idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"prisma-access-browser.list-deployments\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-browser-deployment\n          description: \"Create a new browser deployment.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n            - name: platform\n              type: string\n              required: true\n            - name: settings\n              type: object\n\
  \              required: true\n          call: \"prisma-access-browser.create-deployment\"\n          with:\n            name: \"tools.name\"\n            platform: \"tools.platform\"\n            settings: \"tools.settings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/browser-security.yaml
tags:
- Palo Alto Networks
- Browser Security
- Enterprise Browser
- Prisma Access
tools:
- description: List all browser policies with pagination.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-browser-policies
- description: Create a new browser policy.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-browser-policy
- description: Get a specific browser policy by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-browser-policy
- description: Update a specific browser policy by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-browser-policy
- description: Delete a specific browser policy by ID.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-browser-policy
- description: List all browser users with pagination.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-browser-users
- description: Get sessions for a specific user.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-user-sessions
- description: List all browser deployments with pagination.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-browser-deployments
- description: Create a new browser deployment.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-browser-deployment
---
