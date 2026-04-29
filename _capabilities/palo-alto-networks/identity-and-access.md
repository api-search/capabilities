---
categories:
- identity-access
consumed_apis:
- sase-iam
- sase-tenancy
- sase-subscription
- cloud-identity-engine
description: Unified identity and access management capability for managing service accounts, access policies, roles, tenant service groups, and subscriptions across SASE IAM, Tenancy, and Subscription APIs.
layout: capability
name: Palo Alto Networks Identity and Access Management
operations:
- description: List all service accounts with optional filtering.
  method: GET
  name: list-service-accounts
  path: /v1/service-accounts
- description: Create a new service account.
  method: POST
  name: create-service-account
  path: /v1/service-accounts
- description: Get details of a specific service account.
  method: GET
  name: get-service-account
  path: /v1/service-accounts/{account_id}
- description: Update an existing service account.
  method: PUT
  name: update-service-account
  path: /v1/service-accounts/{account_id}
- description: Delete a service account.
  method: DELETE
  name: delete-service-account
  path: /v1/service-accounts/{account_id}
- description: Generate credentials for a service account.
  method: POST
  name: generate-service-account-credentials
  path: /v1/service-accounts/{account_id}/keys
- description: Revoke a specific key for a service account.
  method: DELETE
  name: revoke-service-account-key
  path: /v1/service-accounts/{account_id}/keys/{key_id}
- description: List all access policies with optional filtering.
  method: GET
  name: list-access-policies
  path: /v1/access-policies
- description: Create a new access policy.
  method: POST
  name: create-access-policy
  path: /v1/access-policies
- description: Get details of a specific access policy.
  method: GET
  name: get-access-policy
  path: /v1/access-policies/{policy_id}
- description: Update an existing access policy.
  method: PUT
  name: update-access-policy
  path: /v1/access-policies/{policy_id}
- description: Delete an access policy.
  method: DELETE
  name: delete-access-policy
  path: /v1/access-policies/{policy_id}
- description: List all available roles.
  method: GET
  name: list-roles
  path: /v1/roles
- description: List all tenant service groups with optional filtering.
  method: GET
  name: list-tenant-service-groups
  path: /v1/tenant-service-groups
- description: Create a new tenant service group.
  method: POST
  name: create-tenant-service-group
  path: /v1/tenant-service-groups
- description: Get details of a specific tenant service group.
  method: GET
  name: get-tenant-service-group
  path: /v1/tenant-service-groups/{tsg_id}
- description: Update an existing tenant service group.
  method: PUT
  name: update-tenant-service-group
  path: /v1/tenant-service-groups/{tsg_id}
- description: Delete a tenant service group.
  method: DELETE
  name: delete-tenant-service-group
  path: /v1/tenant-service-groups/{tsg_id}
- description: List child tenant service groups for a given parent.
  method: GET
  name: list-child-tenant-service-groups
  path: /v1/tenant-service-groups/{tsg_id}/children
- description: List all subscriptions for a tenant service group.
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions
- description: Get details of a specific subscription.
  method: GET
  name: get-subscription
  path: /v1/subscriptions/{subscription_id}
- description: Get entitlements for a specific subscription.
  method: GET
  name: get-subscription-entitlements
  path: /v1/subscriptions/{subscription_id}/entitlements
- description: Allocate licenses from a subscription to tenant service groups.
  method: PUT
  name: allocate-licenses
  path: /v1/subscriptions/{subscription_id}/allocation
personas:
- description: Manages service accounts, roles, and access policies for platform API access.
  id: iam-admin
  name: IAM Administrator
- description: Manages multi-tenant hierarchies and service group configurations for MSSPs.
  id: tenant-operator
  name: Tenant Operator
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- saas security admin
- network architect
- subscription manager
- allocate licenses from a subscription.
- list all sase service accounts with optional filtering by tsg.
- manage sase access policies.
- researches threat actors, malware campaigns, and vulnerability trends.
- get entitlements for a specific subscription.
- network security
- delete a service account.
- tenant operator
- delete a tenant service group.
- list subscriptions
- sre
- list roles
- compliance team
- delete tenant service group
- get details of a specific tenant service group.
- threat intelligence
- create tenant service group
- soc analyst
- revoke a specific key for a service account.
- conducts automated adversarial testing against ai systems and llm applications.
- monitors and remediates cloud security misconfigurations and compliance violations.
- monitors network health, performance, and digital experience metrics.
- list all service accounts with optional filtering.
- list child tenant service groups.
- firewall policy management, network objects, and cloud-native firewall configuration.
- mssp operator
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- delete access policy
- enterprise it
- delete an access policy by id.
- manages multi-tenant hierarchies and service group configurations for mssps.
- palo alto networks
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- manage sase tenant service groups.
- subscriptions
- sd wan operator
- create access policy
- proactively searches for threats and iocs across telemetry data.
- create a new sase service account.
- get details of a specific access policy by id.
- investigates security incidents, triages alerts, and coordinates response actions.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- network operations
- list tenant service groups
- update tenant service group
- manages multi-tenant security operations at scale for managed service providers.
- list available sase roles.
- cybersecurity
- update an existing service account.
- manages service accounts, roles, and access policies for platform api access.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- network security engineer
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- get, update, or delete a specific tenant service group.
- delete an access policy.
- update an existing access policy.
- sase
- get, update, or delete a specific service account.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- manages enterprise browser policies and secure browsing configurations.
- list all available sase roles.
- incident responder
- get subscription
- firewall
- create a new tenant service group.
- identity
- get details of a specific service account.
- get details of a specific access policy.
- threat intel analyst
- create service account
- platform engineer
- data protection analyst
- get tenant service group
- investigates dlp incidents and manages sensitive data protection policies.
- list all tenant service groups with optional filtering.
- cloud security posture management, compliance monitoring, and workload protection.
- get details of a specific subscription.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- manage sase service accounts.
- cloud security
- get access policy
- list all available roles.
- delete a service account by id.
- get, update, or delete a specific access policy.
- list child tenant service groups
- allocate licenses
- revoke service account key
- update service account
- get subscription entitlements
- list all subscriptions for a tenant service group.
- ai runtime security scanning and automated red teaming for ai applications.
- executes containment, eradication, and recovery actions during security incidents.
- get service account
- secures ai applications with runtime scanning and vulnerability assessment.
- firewall admin
- browser security admin
- data loss prevention, saas security monitoring, and identity security posture.
- digital experience monitoring, log management, and best practice assessment.
- iam admin
- designs and implements network security architectures and policies.
- update access policy
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- tenancy
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- designs sase and sd-wan network architectures for secure remote access.
- allocate licenses from a subscription to tenant service groups.
- enterprise browser policy management and secure browsing.
- xdr
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- malware researcher
- create a new service account.
- list access policies
- threat hunter
- ai security engineer
- manages logging infrastructure, integrations, and platform automation.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- generate credentials for a service account.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- update an existing tenant service group.
- get details of a specific service account by id.
- list service accounts
- access management
- vulnerability manager
- cloud identity engine
- compliance officer
- list all access policies with optional filtering.
- red team operator
- create a new access policy.
- list child tenant service groups for a given parent.
- sase admin
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- cloud security engineer
- analyzes suspicious files and samples for malware characteristics.
- manage enterprise browser policies, user sessions, and deployments.
- delete service account
- soar
- generate service account credentials
- identity and access management, tenant hierarchies, and subscription management.
- list sase subscriptions.
slug: identity-and-access
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Palo Alto Networks Identity and Access Management\"\n  description: \"Unified identity and access management capability for managing service accounts, access policies, roles, tenant service groups, and subscriptions across SASE IAM, Tenancy, and Subscription APIs.\"\n  tags:\n    - Palo Alto Networks\n    - Identity\n    - Access Management\n    - Tenancy\n    - Subscriptions\n    - Cloud Identity Engine\n  created: \"2026-04-16\"\n  modified: \"2026-04-16\"\n\nbinds:\n  - namespace: env\n    keys:\n      PALO_ALTO_OAUTH_TOKEN: PALO_ALTO_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: sase-iam\n      location: ./shared/sase-iam.yaml\n    - import: sase-tenancy\n      location: ./shared/sase-tenancy.yaml\n    - import: sase-subscription\n      location: ./shared/sase-subscription.yaml\n    - import: cloud-identity-engine\n      location: ./shared/cloud-identity-engine.yaml\n\n  exposes:\n    - type: rest\n      port: 8086\n\
  \      namespace: identity-access-api\n      description: \"Unified REST API for identity, access, tenancy, and subscription management.\"\n      resources:\n\n        # ── Service Accounts (SASE IAM) ──────────────────────────────────\n        - path: /v1/service-accounts\n          name: service-accounts\n          description: \"Manage SASE service accounts.\"\n          operations:\n            - method: GET\n              name: list-service-accounts\n              description: \"List all service accounts with optional filtering.\"\n              inputParameters:\n                - name: tsg_id\n                  in: query\n                  type: string\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"sase-iam.list-service-accounts\"\
  \n              with:\n                tsg_id: \"rest.tsg_id\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-service-account\n              description: \"Create a new service account.\"\n              call: \"sase-iam.create-service-account\"\n              with:\n                name: \"rest.name\"\n                tsg_id: \"rest.tsg_id\"\n                display_name: \"rest.display_name\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/service-accounts/{account_id}\n          name: service-account-detail\n          description: \"Get, update, or delete a specific service account.\"\n          operations:\n            - method: GET\n              name: get-service-account\n\
  \              description: \"Get details of a specific service account.\"\n              inputParameters:\n                - name: account_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-iam.get-service-account\"\n              with:\n                id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-service-account\n              description: \"Update an existing service account.\"\n              inputParameters:\n                - name: account_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-iam.update-service-account\"\n              with:\n                id: \"rest.account_id\"\n                display_name: \"rest.display_name\"\n                description: \"rest.description\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-service-account\n              description: \"Delete a service account.\"\n              inputParameters:\n                - name: account_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-iam.delete-service-account\"\n              with:\n                id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/service-accounts/{account_id}/keys\n          name: service-account-keys\n          description: \"Generate credentials for a service account.\"\n          operations:\n            - method: POST\n              name: generate-service-account-credentials\n              description: \"Generate credentials for a service account.\"\n              inputParameters:\n                - name: account_id\n\
  \                  in: path\n                  type: string\n                  required: true\n              call: \"sase-iam.generate-service-account-credentials\"\n              with:\n                id: \"rest.account_id\"\n                description: \"rest.description\"\n                expires_in_days: \"rest.expires_in_days\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/service-accounts/{account_id}/keys/{key_id}\n          name: service-account-key-detail\n          description: \"Revoke a specific key for a service account.\"\n          operations:\n            - method: DELETE\n              name: revoke-service-account-key\n              description: \"Revoke a specific key for a service account.\"\n              inputParameters:\n                - name: account_id\n                  in: path\n                  type: string\n                  required: true\n                - name: key_id\n     \
  \             in: path\n                  type: string\n                  required: true\n              call: \"sase-iam.revoke-service-account-key\"\n              with:\n                id: \"rest.account_id\"\n                key_id: \"rest.key_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── Access Policies (SASE IAM) ───────────────────────────────────\n        - path: /v1/access-policies\n          name: access-policies\n          description: \"Manage SASE access policies.\"\n          operations:\n            - method: GET\n              name: list-access-policies\n              description: \"List all access policies with optional filtering.\"\n              inputParameters:\n                - name: principal_id\n                  in: query\n                  type: string\n                  required: false\n                - name: tsg_id\n                  in: query\n                  type: string\n      \
  \            required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"sase-iam.list-access-policies\"\n              with:\n                principal_id: \"rest.principal_id\"\n                tsg_id: \"rest.tsg_id\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-access-policy\n              description: \"Create a new access policy.\"\n              call: \"sase-iam.create-access-policy\"\n              with:\n                principal_id: \"rest.principal_id\"\n                principal_type: \"rest.principal_type\"\n                role_id: \"rest.role_id\"\n    \
  \            tsg_id: \"rest.tsg_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/access-policies/{policy_id}\n          name: access-policy-detail\n          description: \"Get, update, or delete a specific access policy.\"\n          operations:\n            - method: GET\n              name: get-access-policy\n              description: \"Get details of a specific access policy.\"\n              inputParameters:\n                - name: policy_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-iam.get-access-policy\"\n              with:\n                id: \"rest.policy_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-access-policy\n              description: \"Update an existing access policy.\"\n              inputParameters:\n\
  \                - name: policy_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-iam.update-access-policy\"\n              with:\n                id: \"rest.policy_id\"\n                principal_id: \"rest.principal_id\"\n                principal_type: \"rest.principal_type\"\n                role_id: \"rest.role_id\"\n                tsg_id: \"rest.tsg_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-access-policy\n              description: \"Delete an access policy.\"\n              inputParameters:\n                - name: policy_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-iam.delete-access-policy\"\n              with:\n                id: \"rest.policy_id\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n        # ── Roles (SASE IAM) ─────────────────────────────────────────────\n        - path: /v1/roles\n          name: roles\n          description: \"List available SASE roles.\"\n          operations:\n            - method: GET\n              name: list-roles\n              description: \"List all available roles.\"\n              call: \"sase-iam.list-roles\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        # ── Tenant Service Groups (SASE Tenancy) ─────────────────────────\n        - path: /v1/tenant-service-groups\n          name: tenant-service-groups\n          description: \"Manage SASE tenant service groups.\"\n          operations:\n            - method: GET\n              name: list-tenant-service-groups\n              description: \"List all tenant service groups with optional filtering.\"\n              inputParameters:\n                - name: parent_id\n         \
  \         in: query\n                  type: string\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"sase-tenancy.list-tenant-service-groups\"\n              with:\n                parent_id: \"rest.parent_id\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-tenant-service-group\n              description: \"Create a new tenant service group.\"\n              call: \"sase-tenancy.create-tenant-service-group\"\n              with:\n                display_name: \"rest.display_name\"\n                parent_id: \"rest.parent_id\"\n           \
  \     description: \"rest.description\"\n                support_account_id: \"rest.support_account_id\"\n                vertical: \"rest.vertical\"\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tenant-service-groups/{tsg_id}\n          name: tenant-service-group-detail\n          description: \"Get, update, or delete a specific tenant service group.\"\n          operations:\n            - method: GET\n              name: get-tenant-service-group\n              description: \"Get details of a specific tenant service group.\"\n              inputParameters:\n                - name: tsg_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-tenancy.get-tenant-service-group\"\n              with:\n                tsg_id: \"rest.tsg_id\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n            - method: PUT\n              name: update-tenant-service-group\n              description: \"Update an existing tenant service group.\"\n              inputParameters:\n                - name: tsg_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-tenancy.update-tenant-service-group\"\n              with:\n                tsg_id: \"rest.tsg_id\"\n                display_name: \"rest.display_name\"\n                description: \"rest.description\"\n                vertical: \"rest.vertical\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-tenant-service-group\n              description: \"Delete a tenant service group.\"\n              inputParameters:\n                - name: tsg_id\n                  in: path\n                  type: string\n             \
  \     required: true\n              call: \"sase-tenancy.delete-tenant-service-group\"\n              with:\n                tsg_id: \"rest.tsg_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tenant-service-groups/{tsg_id}/children\n          name: tenant-service-group-children\n          description: \"List child tenant service groups.\"\n          operations:\n            - method: GET\n              name: list-child-tenant-service-groups\n              description: \"List child tenant service groups for a given parent.\"\n              inputParameters:\n                - name: tsg_id\n                  in: path\n                  type: string\n                  required: true\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n        \
  \          required: false\n              call: \"sase-tenancy.list-child-tenant-service-groups\"\n              with:\n                tsg_id: \"rest.tsg_id\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        # ── Subscriptions (SASE Subscription) ────────────────────────────\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: \"List SASE subscriptions.\"\n          operations:\n            - method: GET\n              name: list-subscriptions\n              description: \"List all subscriptions for a tenant service group.\"\n              inputParameters:\n                - name: tsg_id\n                  in: query\n                  type: string\n                  required: true\n                - name: product\n                  in: query\n                  type: string\n                  required: false\n\
  \                - name: status\n                  in: query\n                  type: string\n                  required: false\n              call: \"sase-subscription.list-subscriptions\"\n              with:\n                tsg_id: \"rest.tsg_id\"\n                product: \"rest.product\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/subscriptions/{subscription_id}\n          name: subscription-detail\n          description: \"Get details of a specific subscription.\"\n          operations:\n            - method: GET\n              name: get-subscription\n              description: \"Get details of a specific subscription.\"\n              inputParameters:\n                - name: subscription_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-subscription.get-subscription\"\n              with:\n\
  \                subscription_id: \"rest.subscription_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/subscriptions/{subscription_id}/entitlements\n          name: subscription-entitlements\n          description: \"Get entitlements for a specific subscription.\"\n          operations:\n            - method: GET\n              name: get-subscription-entitlements\n              description: \"Get entitlements for a specific subscription.\"\n              inputParameters:\n                - name: subscription_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-subscription.get-subscription-entitlements\"\n              with:\n                subscription_id: \"rest.subscription_id\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/subscriptions/{subscription_id}/allocation\n\
  \          name: subscription-allocation\n          description: \"Allocate licenses from a subscription.\"\n          operations:\n            - method: PUT\n              name: allocate-licenses\n              description: \"Allocate licenses from a subscription to tenant service groups.\"\n              inputParameters:\n                - name: subscription_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-subscription.allocate-licenses\"\n              with:\n                subscription_id: \"rest.subscription_id\"\n                allocations: \"rest.allocations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9096\n      namespace: identity-access-mcp\n      transport: http\n      description: \"MCP server for AI-assisted identity, access, tenancy, and subscription management.\"\n      tools:\n\n        # ── Service Accounts\
  \ ─────────────────────────────────────────────\n        - name: list-service-accounts\n          description: \"List all SASE service accounts with optional filtering by TSG.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: tsg_id\n              type: string\n              required: false\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"sase-iam.list-service-accounts\"\n          with:\n            tsg_id: \"tools.tsg_id\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-service-account\n          description: \"Create a new SASE service account.\"\n          hints:\n  \
  \          readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n            - name: tsg_id\n              type: string\n              required: true\n            - name: display_name\n              type: string\n              required: false\n            - name: description\n              type: string\n              required: false\n          call: \"sase-iam.create-service-account\"\n          with:\n            name: \"tools.name\"\n            tsg_id: \"tools.tsg_id\"\n            display_name: \"tools.display_name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-service-account\n          description: \"Get details of a specific service account by ID.\"\n          hints:\n            readOnly: true\n      \
  \      destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n          call: \"sase-iam.get-service-account\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-service-account\n          description: \"Update an existing service account.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n            - name: display_name\n              type: string\n              required: false\n            - name: description\n              type: string\n              required: false\n          call: \"sase-iam.update-service-account\"\n          with:\n         \
  \   id: \"tools.id\"\n            display_name: \"tools.display_name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-service-account\n          description: \"Delete a service account by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n          call: \"sase-iam.delete-service-account\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: generate-service-account-credentials\n          description: \"Generate credentials for a service account.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld:\
  \ true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n            - name: description\n              type: string\n              required: false\n            - name: expires_in_days\n              type: integer\n              required: false\n          call: \"sase-iam.generate-service-account-credentials\"\n          with:\n            id: \"tools.id\"\n            description: \"tools.description\"\n            expires_in_days: \"tools.expires_in_days\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: revoke-service-account-key\n          description: \"Revoke a specific key for a service account.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n            - name: key_id\n\
  \              type: string\n              required: true\n          call: \"sase-iam.revoke-service-account-key\"\n          with:\n            id: \"tools.id\"\n            key_id: \"tools.key_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # ── Access Policies ──────────────────────────────────────────────\n        - name: list-access-policies\n          description: \"List all access policies with optional filtering.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: principal_id\n              type: string\n              required: false\n            - name: tsg_id\n              type: string\n              required: false\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n\
  \          call: \"sase-iam.list-access-policies\"\n          with:\n            principal_id: \"tools.principal_id\"\n            tsg_id: \"tools.tsg_id\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-access-policy\n          description: \"Create a new access policy.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: principal_id\n              type: string\n              required: true\n            - name: principal_type\n              type: string\n              required: true\n            - name: role_id\n              type: string\n              required: true\n            - name: tsg_id\n              type: string\n              required: true\n          call: \"sase-iam.create-access-policy\"\n        \
  \  with:\n            principal_id: \"tools.principal_id\"\n            principal_type: \"tools.principal_type\"\n            role_id: \"tools.role_id\"\n            tsg_id: \"tools.tsg_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-access-policy\n          description: \"Get details of a specific access policy by ID.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n          call: \"sase-iam.get-access-policy\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-access-policy\n          description: \"Update an existing access policy.\"\n          hints:\n            readOnly: false\n            destructive: false\n\
  \            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n            - name: principal_id\n              type: string\n              required: false\n            - name: principal_type\n              type: string\n              required: false\n            - name: role_id\n              type: string\n              required: false\n            - name: tsg_id\n              type: string\n              required: false\n          call: \"sase-iam.update-access-policy\"\n          with:\n            id: \"tools.id\"\n            principal_id: \"tools.principal_id\"\n            principal_type: \"tools.principal_type\"\n            role_id: \"tools.role_id\"\n            tsg_id: \"tools.tsg_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-access-policy\n          description: \"Delete an access policy by ID.\"\n\
  \          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n          call: \"sase-iam.delete-access-policy\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # ── Roles ────────────────────────────────────────────────────────\n        - name: list-roles\n          description: \"List all available SASE roles.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters: []\n          call: \"sase-iam.list-roles\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        # ── Tenant Service Groups ────────────────────────────────────────\n        - name: list-tenant-service-groups\n\
  \          description: \"List all tenant service groups with optional filtering.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: parent_id\n              type: string\n              required: false\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"sase-tenancy.list-tenant-service-groups\"\n          with:\n            parent_id: \"tools.parent_id\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-tenant-service-group\n          description: \"Create a new tenant service group.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent:\
  \ false\n            openWorld: true\n          inputParameters:\n            - name: display_name\n              type: string\n              required: true\n            - name: parent_id\n              type: string\n              required: true\n            - name: description\n              type: string\n              required: false\n            - name: support_account_id\n              type: string\n              required: false\n            - name: vertical\n              type: string\n              required: false\n            - name: region\n              type: string\n              required: false\n          call: \"sase-tenancy.create-tenant-service-group\"\n          with:\n            display_name: \"tools.display_name\"\n            parent_id: \"tools.parent_id\"\n            description: \"tools.description\"\n            support_account_id: \"tools.support_account_id\"\n            vertical: \"tools.vertical\"\n            region: \"tools.region\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-tenant-service-group\n          description: \"Get details of a specific tenant service group.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: tsg_id\n              type: string\n              required: true\n          call: \"sase-tenancy.get-tenant-service-group\"\n          with:\n            tsg_id: \"tools.tsg_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-tenant-service-group\n          description: \"Update an existing tenant service group.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: tsg_id\n              type: string\n              required: true\n\
  \            - name: display_name\n              type: string\n              required: false\n            - name: description\n              type: string\n              required: false\n            - name: vertical\n              type: string\n              required: false\n          call: \"sase-tenancy.update-tenant-service-group\"\n          with:\n            tsg_id: \"tools.tsg_id\"\n            display_name: \"tools.display_name\"\n            description: \"tools.description\"\n            vertical: \"tools.vertical\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-tenant-service-group\n          description: \"Delete a tenant service group.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: tsg_id\n              type: string\n              required: true\n          call: \"sase-tenancy.delete-tenant-service-group\"\
  \n          with:\n            tsg_id: \"tools.tsg_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-child-tenant-service-groups\n          description: \"List child tenant service groups for a given parent.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: tru\n\n# --- truncated at 32 KB (35 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/identity-and-access.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/identity-and-access.yaml
tags:
- Palo Alto Networks
- Identity
- Access Management
- Tenancy
- Subscriptions
- Cloud Identity Engine
tools:
- description: List all SASE service accounts with optional filtering by TSG.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-service-accounts
- description: Create a new SASE service account.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-service-account
- description: Get details of a specific service account by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-service-account
- description: Update an existing service account.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-service-account
- description: Delete a service account by ID.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-service-account
- description: Generate credentials for a service account.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: generate-service-account-credentials
- description: Revoke a specific key for a service account.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: revoke-service-account-key
- description: List all access policies with optional filtering.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-access-policies
- description: Create a new access policy.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-access-policy
- description: Get details of a specific access policy by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-access-policy
- description: Update an existing access policy.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-access-policy
- description: Delete an access policy by ID.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-access-policy
- description: List all available SASE roles.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-roles
- description: List all tenant service groups with optional filtering.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-tenant-service-groups
- description: Create a new tenant service group.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-tenant-service-group
- description: Get details of a specific tenant service group.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-tenant-service-group
- description: Update an existing tenant service group.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-tenant-service-group
- description: Delete a tenant service group.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-tenant-service-group
- description: List child tenant service groups for a given parent.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-child-tenant-service-groups
- description: List all subscriptions for a tenant service group.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-subscriptions
- description: Get details of a specific subscription.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-subscription
- description: Get entitlements for a specific subscription.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-subscription-entitlements
- description: Allocate licenses from a subscription to tenant service groups.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: allocate-licenses
---
