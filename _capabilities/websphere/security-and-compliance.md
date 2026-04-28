---
categories:
- security
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
- list fixes
- get overall health status
- list known security vulnerabilities
- vulnerability management
- get server health
- microservices
- list managed servers
- list available fixes
- security user management
- list servers managed by websphere automation
- health monitoring
- initiate vulnerability resolution
- apply a fix to managed servers
- compliance
- get individual server health
- middleware
- get overall health
- get vulnerability
- list security users
- enterprise java
- application server
- list users
- fix and patch management
- ibm websphere
- get overall environment health
- list compliance reports
- resolve vulnerability
- apply fix
- vulnerability tracking and remediation
- cloud native
- j2ee
- list vulnerabilities
- compliance reporting
- get vulnerability details
- list available security fixes
- list known vulnerabilities
- security
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
