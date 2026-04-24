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
- tenant user management
- list backup tasks
- search acronis platform for tenants and users by name or email
- list users in an acronis tenant
- search
- managed service provider admin managing multiple customer tenants, licensing, and usage
- endpoint management
- acronis
- IT Administrator
- unified tenant, agent, and task management for msps and it admins
- tenant usage monitoring
- list hardware nodes
- search tenants and users
- get tenant
- monitoring
- list hardware nodes managed by acronis for a tenant
- get task
- get details about a specific acronis backup agent including online status
- cross-tenant search
- list tasks
- cybersecurity
- get current usage metrics for an acronis tenant across all services
- list acronis backup tasks with filtering by state, result, policy, and resource
- create tenant
- Security Analyst
- list acronis protection agents registered for a tenant
- protection agent management
- protection policy creation and application
- get details about a specific acronis backup task
- get usage metrics for a tenant
- get details about a specific acronis tenant
- list agents for a tenant
- data protection
- list acronis tenant hierarchy - companies, partners, and customer accounts
- account management
- tenant hierarchy management
- msp
- list tenant users
- individual tenant operations
- backup agent deployment and management across endpoints
- multi-tier tenant hierarchy and licensing management
- security professional monitoring edr events and threat response
- list tenants
- get agent
- get tenant details
- get tenant usages
- list users in a tenant
- list agents
- MSP Administrator
- enterprise it admin managing backup agents, policies, and task monitoring
- backup task monitoring
- backup and recovery task execution tracking
- backup
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
