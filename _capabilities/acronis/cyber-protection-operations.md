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
- tenant hierarchy management
- list hardware nodes managed by acronis for a tenant
- backup and recovery task execution tracking
- cross-tenant search
- get agent
- list agents
- list tasks
- acronis
- get details about a specific acronis tenant
- protection agent management
- get details about a specific acronis backup task
- search
- data protection
- enterprise it admin managing backup agents, policies, and task monitoring
- get tenant details
- create tenant
- MSP Administrator
- search acronis platform for tenants and users by name or email
- list acronis protection agents registered for a tenant
- security professional monitoring edr events and threat response
- msp
- get details about a specific acronis backup agent including online status
- account management
- list acronis backup tasks with filtering by state, result, policy, and resource
- Security Analyst
- unified tenant, agent, and task management for msps and it admins
- get tenant usages
- list hardware nodes
- managed service provider admin managing multiple customer tenants, licensing, and usage
- IT Administrator
- multi-tier tenant hierarchy and licensing management
- list tenants
- get task
- list backup tasks
- individual tenant operations
- get current usage metrics for an acronis tenant across all services
- list acronis tenant hierarchy - companies, partners, and customer accounts
- endpoint management
- protection policy creation and application
- list tenant users
- tenant user management
- monitoring
- get usage metrics for a tenant
- backup
- cybersecurity
- list users in an acronis tenant
- list agents for a tenant
- tenant usage monitoring
- get tenant
- backup task monitoring
- list users in a tenant
- backup agent deployment and management across endpoints
- search tenants and users
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
