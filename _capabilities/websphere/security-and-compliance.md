---
consumed_apis:
- automation
- admin-rest
description: Workflow for security vulnerability management, automated patching, compliance reporting, and health monitoring across WebSphere environments for security engineers and compliance teams.
layout: capability
name: WebSphere Security and Compliance
operations:
- description: List known vulnerabilities
  method: GET
  name: list-vulnerabilities
  path: /v1/vulnerabilities
- description: Get vulnerability details
  method: GET
  name: get-vulnerability
  path: /v1/vulnerabilities
- description: List available fixes
  method: GET
  name: list-fixes
  path: /v1/fixes
- description: List compliance reports
  method: GET
  name: list-compliance-reports
  path: /v1/compliance
- description: Get overall health status
  method: GET
  name: get-overall-health
  path: /v1/health
- description: List security users
  method: GET
  name: list-users
  path: /v1/security-users
personas: []
provider_name: IBM WebSphere
provider_slug: websphere
search_terms:
- health monitoring
- security user management
- get overall health
- cloud native
- ibm websphere
- list available security fixes
- list security users
- middleware
- list managed servers
- compliance reporting
- list known vulnerabilities
- resolve vulnerability
- get overall health status
- fix and patch management
- vulnerability tracking and remediation
- get vulnerability details
- apply a fix to managed servers
- enterprise java
- apply fix
- list available fixes
- compliance
- list compliance reports
- security
- list users
- vulnerability management
- list fixes
- list known security vulnerabilities
- list vulnerabilities
- initiate vulnerability resolution
- j2ee
- get overall environment health
- get vulnerability
- get server health
- list servers managed by websphere automation
- application server
- get individual server health
- microservices
slug: security-and-compliance
tags:
- IBM WebSphere
- Security
- Compliance
- Vulnerability Management
tools:
- description: List known security vulnerabilities
  hints:
    readOnly: true
  name: list-vulnerabilities
- description: Get vulnerability details
  hints:
    readOnly: true
  name: get-vulnerability
- description: Initiate vulnerability resolution
  hints:
    readOnly: false
  name: resolve-vulnerability
- description: List available security fixes
  hints:
    readOnly: true
  name: list-fixes
- description: Apply a fix to managed servers
  hints:
    readOnly: false
  name: apply-fix
- description: Get overall environment health
  hints:
    readOnly: true
  name: get-overall-health
- description: Get individual server health
  hints:
    readOnly: true
  name: get-server-health
- description: List compliance reports
  hints:
    readOnly: true
  name: list-compliance-reports
- description: List servers managed by WebSphere Automation
  hints:
    readOnly: true
  name: list-managed-servers
---
