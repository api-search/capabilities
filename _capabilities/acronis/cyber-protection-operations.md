---
categories:
- security
consumed_apis: []
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
- msp
- IT Administrator
- get usage metrics for a tenant
- protection policy creation and application
- search tenants and users
- list tenant users
- list hardware nodes managed by acronis for a tenant
- Security Analyst
- get details about a specific acronis tenant
- endpoint management
- account management
- get tenant
- get agent
- search acronis platform for tenants and users by name or email
- monitoring
- get task
- list acronis tenant hierarchy - companies, partners, and customer accounts
- backup task monitoring
- individual tenant operations
- get current usage metrics for an acronis tenant across all services
- list tasks
- data protection
- backup and recovery task execution tracking
- get tenant details
- list users in an acronis tenant
- tenant hierarchy management
- backup
- tenant user management
- cross-tenant search
- tenant usage monitoring
- list acronis protection agents registered for a tenant
- multi-tier tenant hierarchy and licensing management
- list tenants
- unified tenant, agent, and task management for msps and it admins
- list users in a tenant
- acronis
- protection agent management
- MSP Administrator
- list hardware nodes
- get tenant usages
- get details about a specific acronis backup task
- cybersecurity
- search
- list agents
- managed service provider admin managing multiple customer tenants, licensing, and usage
- list agents for a tenant
- security professional monitoring edr events and threat response
- backup agent deployment and management across endpoints
- list acronis backup tasks with filtering by state, result, policy, and resource
- enterprise it admin managing backup agents, policies, and task monitoring
- create tenant
- get details about a specific acronis backup agent including online status
- list backup tasks
slug: cyber-protection-operations
source_filename: cyber-protection-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Acronis Cyber Protection Operations\n  description: Unified workflow for managing Acronis Cyber Protect Cloud operations including tenant administration, agent\n    monitoring, backup task tracking, and usage reporting. Used by MSPs, IT administrators, and security teams to automate\n    Acronis cyber protection platform management.\n  tags:\n  - Acronis\n  - Account Management\n  - Backup\n  - Cybersecurity\n  - Monitoring\n  - MSP\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ACRONIS_ACCESS_TOKEN: ACRONIS_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: acronis-account\n    baseUri: https://eu2-cloud.acronis.com/api/2\n    description: Acronis Account Management API v2\n    authentication:\n      type: bearer\n      token: '{{ACRONIS_ACCESS_TOKEN}}'\n    resources:\n    - name: tenants\n      path: /tenants\n      description: Tenant hierarchy management\n      operations:\n\
  \      - name: list-tenants\n        method: GET\n        description: List tenants in the hierarchy\n        inputParameters:\n        - name: parent_id\n          in: query\n          type: string\n          required: false\n          description: Parent tenant UUID filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-tenant\n        method: POST\n        description: Create a new tenant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            kind: '{{tools.kind}}'\n            parent_id: '{{tools.parent_id}}'\n    - name: tenant-by-id\n      path: /tenants/{tenant_id}\n      description: Single tenant operations\n      operations:\n      - name: get-tenant\n        method: GET\n        description: Get tenant details\n\
  \        inputParameters:\n        - name: tenant_id\n          in: path\n          type: string\n          required: true\n          description: Tenant UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tenant-users\n      path: /tenants/{tenant_id}/users\n      description: Tenant user management\n      operations:\n      - name: list-tenant-users\n        method: GET\n        description: List users in a tenant\n        inputParameters:\n        - name: tenant_id\n          in: path\n          type: string\n          required: true\n          description: Tenant UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: offering-items\n      path: /tenants/{tenant_id}/offering_items\n      description: Tenant licensing management\n      operations:\n      - name: list-offering-items\n        method: GET\n\
  \        description: List offering items for a tenant\n        inputParameters:\n        - name: tenant_id\n          in: path\n          type: string\n          required: true\n          description: Tenant UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: usages\n      path: /tenants/{tenant_id}/usages\n      description: Tenant usage metrics\n      operations:\n      - name: get-tenant-usages\n        method: GET\n        description: Get usage metrics for a tenant\n        inputParameters:\n        - name: tenant_id\n          in: path\n          type: string\n          required: true\n          description: Tenant UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clients\n      path: /clients\n      description: OAuth client management\n      operations:\n      - name: list-clients\n        method:\
  \ GET\n        description: List OAuth2 clients\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: Cross-tenant search\n      operations:\n      - name: search\n        method: GET\n        description: Search tenants and users\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: acronis-agents\n    baseUri: https://eu2-cloud.acronis.com/api/agent_manager/v2\n    description: Acronis Agent Management API v2\n    authentication:\n      type: bearer\n      token: '{{ACRONIS_ACCESS_TOKEN}}'\n    resources:\n    - name: agents\n      path: /agents\n      description: Protection agent registry\n\
  \      operations:\n      - name: list-agents\n        method: GET\n        description: List all registered Acronis protection agents\n        inputParameters:\n        - name: tenant_id\n          in: query\n          type: string\n          required: true\n          description: Tenant UUID\n        - name: os_family\n          in: query\n          type: string\n          required: false\n          description: Filter by OS family\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-agent\n        method: GET\n        description: Get specific agent details\n        inputParameters:\n        - name: agent_id\n          in: path\n          type: string\n          required: true\n          description: Agent identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hardware-nodes\n      path: /hardware_nodes\n\
  \      description: Hardware node management\n      operations:\n      - name: list-hardware-nodes\n        method: GET\n        description: List hardware nodes visible from a tenant\n        inputParameters:\n        - name: tenant_id\n          in: query\n          type: string\n          required: true\n          description: Tenant UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: acronis-tasks\n    baseUri: https://eu2-cloud.acronis.com/api/task_manager/v2\n    description: Acronis Task Manager API v2\n    authentication:\n      type: bearer\n      token: '{{ACRONIS_ACCESS_TOKEN}}'\n    resources:\n    - name: tasks\n      path: /tasks\n      description: Backup and protection task monitoring\n      operations:\n      - name: list-tasks\n        method: GET\n        description: List backup tasks with filtering and pagination\n        inputParameters:\n        - name:\
  \ tenant_id\n          in: query\n          type: string\n          required: false\n          description: Tenant UUID filter\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Filter by task state\n        - name: result_code\n          in: query\n          type: string\n          required: false\n          description: Filter by result code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-task\n        method: GET\n        description: Get task details by ID\n        inputParameters:\n        - name: task_id\n          in: path\n          type: string\n          required: true\n          description: Task identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activities\n      path: /activities\n      description: Task activity\
  \ monitoring\n      operations:\n      - name: list-activities\n        method: GET\n        description: List task activities\n        inputParameters:\n        - name: task_id\n          in: query\n          type: string\n          required: false\n          description: Parent task ID filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: acronis-cyber-protection-api\n    description: Unified REST API for Acronis Cyber Protect Cloud platform management.\n    resources:\n    - path: /v1/tenants\n      name: tenants\n      description: Tenant hierarchy management\n      operations:\n      - method: GET\n        name: list-tenants\n        description: List tenants\n        call: acronis-account.list-tenants\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-tenant\n        description:\
  \ Create tenant\n        call: acronis-account.create-tenant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tenants/{tenant_id}\n      name: tenant\n      description: Individual tenant operations\n      operations:\n      - method: GET\n        name: get-tenant\n        description: Get tenant details\n        call: acronis-account.get-tenant\n        with:\n          tenant_id: rest.tenant_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tenants/{tenant_id}/users\n      name: tenant-users\n      description: Tenant user management\n      operations:\n      - method: GET\n        name: list-tenant-users\n        description: List users in a tenant\n        call: acronis-account.list-tenant-users\n        with:\n          tenant_id: rest.tenant_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tenants/{tenant_id}/usages\n      name: tenant-usages\n      description:\
  \ Tenant usage monitoring\n      operations:\n      - method: GET\n        name: get-tenant-usages\n        description: Get usage metrics for a tenant\n        call: acronis-account.get-tenant-usages\n        with:\n          tenant_id: rest.tenant_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/agents\n      name: agents\n      description: Protection agent management\n      operations:\n      - method: GET\n        name: list-agents\n        description: List agents for a tenant\n        call: acronis-agents.list-agents\n        with:\n          tenant_id: rest.tenant_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks\n      name: tasks\n      description: Backup task monitoring\n      operations:\n      - method: GET\n        name: list-tasks\n        description: List backup tasks\n        call: acronis-tasks.list-tasks\n        with:\n          tenant_id: rest.tenant_id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: Cross-tenant search\n      operations:\n      - method: GET\n        name: search\n        description: Search tenants and users\n        call: acronis-account.search\n        with:\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: acronis-cyber-protection-mcp\n    transport: http\n    description: MCP server for AI-assisted Acronis Cyber Protect Cloud management.\n    tools:\n    - name: list-tenants\n      description: List Acronis tenant hierarchy - companies, partners, and customer accounts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: acronis-account.list-tenants\n      with:\n        parent_id: tools.parent_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tenant\n      description: Get details about a specific\
  \ Acronis tenant\n      hints:\n        readOnly: true\n        idempotent: true\n      call: acronis-account.get-tenant\n      with:\n        tenant_id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tenant-users\n      description: List users in an Acronis tenant\n      hints:\n        readOnly: true\n        openWorld: true\n      call: acronis-account.list-tenant-users\n      with:\n        tenant_id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tenant-usages\n      description: Get current usage metrics for an Acronis tenant across all services\n      hints:\n        readOnly: true\n        idempotent: true\n      call: acronis-account.get-tenant-usages\n      with:\n        tenant_id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-agents\n      description: List Acronis protection agents registered for a tenant\n   \
  \   hints:\n        readOnly: true\n        openWorld: true\n      call: acronis-agents.list-agents\n      with:\n        tenant_id: tools.tenant_id\n        os_family: tools.os_family\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-agent\n      description: Get details about a specific Acronis backup agent including online status\n      hints:\n        readOnly: true\n        idempotent: true\n      call: acronis-agents.get-agent\n      with:\n        agent_id: tools.agent_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tasks\n      description: List Acronis backup tasks with filtering by state, result, policy, and resource\n      hints:\n        readOnly: true\n        openWorld: true\n      call: acronis-tasks.list-tasks\n      with:\n        tenant_id: tools.tenant_id\n        state: tools.state\n        result_code: tools.result_code\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: get-task\n      description: Get details about a specific Acronis backup task\n      hints:\n        readOnly: true\n        idempotent: true\n      call: acronis-tasks.get-task\n      with:\n        task_id: tools.task_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search\n      description: Search Acronis platform for tenants and users by name or email\n      hints:\n        readOnly: true\n        openWorld: true\n      call: acronis-account.search\n      with:\n        query: tools.query\n        tenant_id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-hardware-nodes\n      description: List hardware nodes managed by Acronis for a tenant\n      hints:\n        readOnly: true\n        openWorld: true\n      call: acronis-agents.list-hardware-nodes\n      with:\n        tenant_id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
