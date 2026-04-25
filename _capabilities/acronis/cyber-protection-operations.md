---
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
- list backup tasks
- get current usage metrics for an acronis tenant across all services
- multi-tier tenant hierarchy and licensing management
- get details about a specific acronis backup agent including online status
- MSP Administrator
- data protection
- security professional monitoring edr events and threat response
- search
- backup
- get tenant
- search tenants and users
- get tenant details
- tenant usage monitoring
- IT Administrator
- list tenant users
- create tenant
- list acronis backup tasks with filtering by state, result, policy, and resource
- msp
- account management
- tenant hierarchy management
- monitoring
- unified tenant, agent, and task management for msps and it admins
- backup agent deployment and management across endpoints
- individual tenant operations
- list acronis protection agents registered for a tenant
- acronis
- list agents
- get details about a specific acronis backup task
- endpoint management
- list tasks
- list agents for a tenant
- cybersecurity
- list users in an acronis tenant
- tenant user management
- get agent
- list acronis tenant hierarchy - companies, partners, and customer accounts
- Security Analyst
- managed service provider admin managing multiple customer tenants, licensing, and usage
- enterprise it admin managing backup agents, policies, and task monitoring
- list users in a tenant
- protection agent management
- get details about a specific acronis tenant
- list hardware nodes managed by acronis for a tenant
- protection policy creation and application
- get tenant usages
- cross-tenant search
- get usage metrics for a tenant
- backup task monitoring
- backup and recovery task execution tracking
- search acronis platform for tenants and users by name or email
- list hardware nodes
- list tenants
- get task
slug: cyber-protection-operations
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
