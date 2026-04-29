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
- get vulnerability details
- compliance reporting
- list available security fixes
- security
- list vulnerabilities
- get vulnerability
- cloud native
- compliance
- get server health
- resolve vulnerability
- vulnerability tracking and remediation
- list security users
- microservices
- get overall health status
- list servers managed by websphere automation
- list managed servers
- ibm websphere
- list users
- health monitoring
- initiate vulnerability resolution
- get individual server health
- middleware
- application server
- j2ee
- list fixes
- vulnerability management
- list known security vulnerabilities
- get overall environment health
- enterprise java
- list known vulnerabilities
- get overall health
- security user management
- list available fixes
- list compliance reports
- apply a fix to managed servers
- fix and patch management
- apply fix
slug: security-and-compliance
source_filename: security-and-compliance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WebSphere Security and Compliance\"\n  description: \"Workflow for security vulnerability management, automated patching, compliance reporting, and health monitoring across WebSphere environments for security engineers and compliance teams.\"\n  tags:\n    - IBM WebSphere\n    - Security\n    - Compliance\n    - Vulnerability Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      WEBSPHERE_AUTOMATION_TOKEN: WEBSPHERE_AUTOMATION_TOKEN\n      WEBSPHERE_USERNAME: WEBSPHERE_USERNAME\n      WEBSPHERE_PASSWORD: WEBSPHERE_PASSWORD\n\ncapability:\n  consumes:\n    - import: automation\n      location: ./shared/automation.yaml\n    - import: admin-rest\n      location: ./shared/admin-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: security-compliance-api\n      description: \"Unified REST API for WebSphere security and compliance operations.\"\n   \
  \   resources:\n        - path: /v1/vulnerabilities\n          name: vulnerabilities\n          description: \"Vulnerability tracking and remediation\"\n          operations:\n            - method: GET\n              name: list-vulnerabilities\n              description: \"List known vulnerabilities\"\n              call: \"automation.list-vulnerabilities\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-vulnerability\n              description: \"Get vulnerability details\"\n              call: \"automation.get-vulnerability\"\n              with:\n                vulnerabilityId: \"rest.vulnerabilityId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/fixes\n          name: fixes\n          description: \"Fix and patch management\"\n          operations:\n            - method: GET\n              name: list-fixes\n\
  \              description: \"List available fixes\"\n              call: \"automation.list-fixes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compliance\n          name: compliance\n          description: \"Compliance reporting\"\n          operations:\n            - method: GET\n              name: list-compliance-reports\n              description: \"List compliance reports\"\n              call: \"automation.list-compliance-reports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/health\n          name: health\n          description: \"Health monitoring\"\n          operations:\n            - method: GET\n              name: get-overall-health\n              description: \"Get overall health status\"\n              call: \"automation.get-overall-health\"\n              outputParameters:\n                - type: object\n            \
  \      mapping: \"$.\"\n        - path: /v1/security-users\n          name: security-users\n          description: \"Security user management\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List security users\"\n              call: \"admin-rest.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: security-compliance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WebSphere security and compliance.\"\n      tools:\n        - name: list-vulnerabilities\n          description: \"List known security vulnerabilities\"\n          hints:\n            readOnly: true\n          call: \"automation.list-vulnerabilities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vulnerability\n          description: \"Get vulnerability details\"\
  \n          hints:\n            readOnly: true\n          call: \"automation.get-vulnerability\"\n          with:\n            vulnerabilityId: \"tools.vulnerabilityId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: resolve-vulnerability\n          description: \"Initiate vulnerability resolution\"\n          hints:\n            readOnly: false\n          call: \"automation.resolve-vulnerability\"\n          with:\n            vulnerabilityId: \"tools.vulnerabilityId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-fixes\n          description: \"List available security fixes\"\n          hints:\n            readOnly: true\n          call: \"automation.list-fixes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: apply-fix\n          description: \"Apply a fix to managed servers\"\n          hints:\n          \
  \  readOnly: false\n          call: \"automation.apply-fix\"\n          with:\n            fixId: \"tools.fixId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-overall-health\n          description: \"Get overall environment health\"\n          hints:\n            readOnly: true\n          call: \"automation.get-overall-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-server-health\n          description: \"Get individual server health\"\n          hints:\n            readOnly: true\n          call: \"automation.get-server-health\"\n          with:\n            serverId: \"tools.serverId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-compliance-reports\n          description: \"List compliance reports\"\n          hints:\n            readOnly: true\n          call: \"automation.list-compliance-reports\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-managed-servers\n          description: \"List servers managed by WebSphere Automation\"\n          hints:\n            readOnly: true\n          call: \"automation.list-managed-servers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/websphere/refs/heads/main/capabilities/security-and-compliance.yaml
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
