---
api_specs:
- filename: acronis-account-management-openapi.yaml
  format: yaml
  label: acronis-account
  slug: acronis-account
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/acronis/refs/heads/main/openapi/acronis-account-management-openapi.yaml
- filename: acronis-agent-management-openapi.yaml
  format: yaml
  label: acronis-agents
  slug: acronis-agents
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/acronis/refs/heads/main/openapi/acronis-agent-management-openapi.yaml
- filename: acronis-task-manager-openapi.yaml
  format: yaml
  label: acronis-tasks
  slug: acronis-tasks
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/acronis/refs/heads/main/openapi/acronis-task-manager-openapi.yaml
categories:
- security
consumed_apis:
- acronis-account
- acronis-agents
- acronis-tasks
description: Unified workflow for managing Acronis Cyber Protect Cloud operations including tenant administration, agent monitoring, backup task tracking, and usage reporting. Used by MSPs, IT administrators, and security teams to automate Acronis cyber protection platform management.
layout: capability
name: Acronis Cyber Protection Operations
operations:
- description: List tenants
  method: GET
  name: list-tenants
  path: /v1/tenants
- description: Create tenant
  method: POST
  name: create-tenant
  path: /v1/tenants
- description: Get tenant details
  method: GET
  name: get-tenant
  path: /v1/tenants/{tenant_id}
- description: List users in a tenant
  method: GET
  name: list-tenant-users
  path: /v1/tenants/{tenant_id}/users
- description: Get usage metrics for a tenant
  method: GET
  name: get-tenant-usages
  path: /v1/tenants/{tenant_id}/usages
- description: List agents for a tenant
  method: GET
  name: list-agents
  path: /v1/agents
- description: List backup tasks
  method: GET
  name: list-tasks
  path: /v1/tasks
- description: Search tenants and users
  method: GET
  name: search
  path: /v1/search
personas: []
provider_name: Acronis
provider_slug: acronis
search_terms:
- IT Administrator
- get tenant usages
- backup task monitoring
- monitoring
- list users in an acronis tenant
- managed service provider admin managing multiple customer tenants, licensing, and usage
- tenant hierarchy management
- get details about a specific acronis tenant
- backup and recovery task execution tracking
- get current usage metrics for an acronis tenant across all services
- list tenant users
- individual tenant operations
- list tenants
- get agent
- list users in a tenant
- get details about a specific acronis backup task
- list agents for a tenant
- list acronis backup tasks with filtering by state, result, policy, and resource
- search acronis platform for tenants and users by name or email
- tenant user management
- MSP Administrator
- backup agent deployment and management across endpoints
- list backup tasks
- unified tenant, agent, and task management for msps and it admins
- search
- cross-tenant search
- list agents
- enterprise it admin managing backup agents, policies, and task monitoring
- security professional monitoring edr events and threat response
- account management
- list hardware nodes managed by acronis for a tenant
- data protection
- acronis
- search tenants and users
- get task
- cybersecurity
- get tenant
- Security Analyst
- msp
- protection agent management
- list tasks
- multi-tier tenant hierarchy and licensing management
- list hardware nodes
- list acronis protection agents registered for a tenant
- list acronis tenant hierarchy - companies, partners, and customer accounts
- create tenant
- get tenant details
- backup
- get details about a specific acronis backup agent including online status
- endpoint management
- tenant usage monitoring
- get usage metrics for a tenant
- protection policy creation and application
slug: cyber-protection-operations
source_filename: cyber-protection-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Acronis Cyber Protection Operations\n  description: >-\n    Unified workflow for managing Acronis Cyber Protect Cloud operations including tenant administration,\n    agent monitoring, backup task tracking, and usage reporting. Used by MSPs, IT administrators, and\n    security teams to automate Acronis cyber protection platform management.\n  tags:\n    - Acronis\n    - Account Management\n    - Backup\n    - Cybersecurity\n    - Monitoring\n    - MSP\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ACRONIS_ACCESS_TOKEN: ACRONIS_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: acronis-account\n      location: ./shared/acronis-account-management.yaml\n    - import: acronis-agents\n      location: ./shared/acronis-agent-management.yaml\n    - import: acronis-tasks\n      location: ./shared/acronis-task-manager.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n    \
  \  namespace: acronis-cyber-protection-api\n      description: Unified REST API for Acronis Cyber Protect Cloud platform management.\n      resources:\n        - path: /v1/tenants\n          name: tenants\n          description: Tenant hierarchy management\n          operations:\n            - method: GET\n              name: list-tenants\n              description: List tenants\n              call: \"acronis-account.list-tenants\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-tenant\n              description: Create tenant\n              call: \"acronis-account.create-tenant\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tenants/{tenant_id}\n          name: tenant\n          description: Individual tenant operations\n          operations:\n            - method: GET\n              name: get-tenant\n  \
  \            description: Get tenant details\n              call: \"acronis-account.get-tenant\"\n              with:\n                tenant_id: \"rest.tenant_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tenants/{tenant_id}/users\n          name: tenant-users\n          description: Tenant user management\n          operations:\n            - method: GET\n              name: list-tenant-users\n              description: List users in a tenant\n              call: \"acronis-account.list-tenant-users\"\n              with:\n                tenant_id: \"rest.tenant_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tenants/{tenant_id}/usages\n          name: tenant-usages\n          description: Tenant usage monitoring\n          operations:\n            - method: GET\n              name: get-tenant-usages\n              description:\
  \ Get usage metrics for a tenant\n              call: \"acronis-account.get-tenant-usages\"\n              with:\n                tenant_id: \"rest.tenant_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/agents\n          name: agents\n          description: Protection agent management\n          operations:\n            - method: GET\n              name: list-agents\n              description: List agents for a tenant\n              call: \"acronis-agents.list-agents\"\n              with:\n                tenant_id: \"rest.tenant_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tasks\n          name: tasks\n          description: Backup task monitoring\n          operations:\n            - method: GET\n              name: list-tasks\n              description: List backup tasks\n              call: \"acronis-tasks.list-tasks\"\n   \
  \           with:\n                tenant_id: \"rest.tenant_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search\n          name: search\n          description: Cross-tenant search\n          operations:\n            - method: GET\n              name: search\n              description: Search tenants and users\n              call: \"acronis-account.search\"\n              with:\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: acronis-cyber-protection-mcp\n      transport: http\n      description: MCP server for AI-assisted Acronis Cyber Protect Cloud management.\n      tools:\n        - name: list-tenants\n          description: List Acronis tenant hierarchy - companies, partners, and customer accounts\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"acronis-account.list-tenants\"\n          with:\n            parent_id: \"tools.parent_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-tenant\n          description: Get details about a specific Acronis tenant\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"acronis-account.get-tenant\"\n          with:\n            tenant_id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tenant-users\n          description: List users in an Acronis tenant\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"acronis-account.list-tenant-users\"\n          with:\n            tenant_id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-tenant-usages\n          description:\
  \ Get current usage metrics for an Acronis tenant across all services\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"acronis-account.get-tenant-usages\"\n          with:\n            tenant_id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-agents\n          description: List Acronis protection agents registered for a tenant\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"acronis-agents.list-agents\"\n          with:\n            tenant_id: \"tools.tenant_id\"\n            os_family: \"tools.os_family\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-agent\n          description: Get details about a specific Acronis backup agent including online status\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"acronis-agents.get-agent\"\
  \n          with:\n            agent_id: \"tools.agent_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tasks\n          description: List Acronis backup tasks with filtering by state, result, policy, and resource\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"acronis-tasks.list-tasks\"\n          with:\n            tenant_id: \"tools.tenant_id\"\n            state: \"tools.state\"\n            result_code: \"tools.result_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-task\n          description: Get details about a specific Acronis backup task\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"acronis-tasks.get-task\"\n          with:\n            task_id: \"tools.task_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \        - name: search\n          description: Search Acronis platform for tenants and users by name or email\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"acronis-account.search\"\n          with:\n            query: \"tools.query\"\n            tenant_id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-hardware-nodes\n          description: List hardware nodes managed by Acronis for a tenant\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"acronis-agents.list-hardware-nodes\"\n          with:\n            tenant_id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/acronis/refs/heads/main/capabilities/cyber-protection-operations.yaml
tags:
- Acronis
- Account Management
- Backup
- Cybersecurity
- Monitoring
- MSP
tools:
- description: List Acronis tenant hierarchy - companies, partners, and customer accounts
  hints:
    openWorld: true
    readOnly: true
  name: list-tenants
- description: Get details about a specific Acronis tenant
  hints:
    idempotent: true
    readOnly: true
  name: get-tenant
- description: List users in an Acronis tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-tenant-users
- description: Get current usage metrics for an Acronis tenant across all services
  hints:
    idempotent: true
    readOnly: true
  name: get-tenant-usages
- description: List Acronis protection agents registered for a tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-agents
- description: Get details about a specific Acronis backup agent including online status
  hints:
    idempotent: true
    readOnly: true
  name: get-agent
- description: List Acronis backup tasks with filtering by state, result, policy, and resource
  hints:
    openWorld: true
    readOnly: true
  name: list-tasks
- description: Get details about a specific Acronis backup task
  hints:
    idempotent: true
    readOnly: true
  name: get-task
- description: Search Acronis platform for tenants and users by name or email
  hints:
    openWorld: true
    readOnly: true
  name: search
- description: List hardware nodes managed by Acronis for a tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-hardware-nodes
---
