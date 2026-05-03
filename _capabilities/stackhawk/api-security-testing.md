---
categories: []
consumed_apis:
- stackhawk
description: Unified workflow capability for API security testing and vulnerability management with StackHawk. Covers application and environment management, scan orchestration via Perch, security finding triage, report generation, scan policy enforcement, and repository management. Designed for AppSec engineers, DevSecOps teams, and security program managers.
layout: capability
name: StackHawk API Security Testing
operations:
- description: List all applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: List all scans for an application
  method: GET
  name: list-scans
  path: /v1/applications/{appId}/scans
- description: Trigger a new DAST scan
  method: POST
  name: trigger-scan
  path: /v1/applications/{appId}/scans
- description: Get scan details
  method: GET
  name: get-scan
  path: /v1/applications/{appId}/scans/{scanId}
- description: List all security findings
  method: GET
  name: list-findings
  path: /v1/applications/{appId}/scans/{scanId}/findings
- description: Get finding details
  method: GET
  name: get-finding
  path: /v1/applications/{appId}/scans/{scanId}/findings/{findingId}
- description: List scan policies
  method: GET
  name: list-policies
  path: /v1/policies
- description: Get status of a running scan
  method: GET
  name: get-perch-scan-status
  path: /v1/scans/{scanId}/status
personas: []
provider_name: StackHawk
provider_slug: stackhawk
search_terms:
- list security scan history for an application environment
- scan details
- list policies
- list all security vulnerabilities discovered in a scan
- application security
- list applications
- get scan details
- check the current status of a running or completed scan
- devsecops
- single security finding
- list all scans for an application
- list scan policies
- trigger a new dast security scan for an application via stackhawk perch
- dast
- scans for an application
- get detailed results for a specific security scan
- list all security findings
- list security scan policies configured for an organization
- trigger a new dast scan
- scan status
- managed applications
- get scan
- get perch scan status
- get scan status
- get finding details
- get status of a running scan
- scan policies
- list scans
- get finding
- list all applications configured in stackhawk for security testing
- vulnerability management
- security findings from a scan
- list findings
- api security
- get full details for a specific security vulnerability finding
- trigger scan
- security testing
- list all applications
slug: api-security-testing
source_filename: api-security-testing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"StackHawk API Security Testing\"\n  description: >-\n    Unified workflow capability for API security testing and vulnerability\n    management with StackHawk. Covers application and environment management,\n    scan orchestration via Perch, security finding triage, report generation,\n    scan policy enforcement, and repository management. Designed for AppSec\n    engineers, DevSecOps teams, and security program managers.\n  tags:\n    - API Security\n    - DAST\n    - DevSecOps\n    - Security Testing\n    - Vulnerability Management\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STACKHAWK_API_KEY: STACKHAWK_API_KEY\n\ncapability:\n  consumes:\n    - import: stackhawk\n      location: ./shared/stackhawk-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: stackhawk-appsec-api\n      description: \"Unified REST API for StackHawk application security\
  \ testing.\"\n      resources:\n        - path: /v1/applications\n          name: applications\n          description: \"Managed applications\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List all applications\"\n              call: \"stackhawk.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications/{appId}/scans\n          name: scans\n          description: \"Scans for an application\"\n          operations:\n            - method: GET\n              name: list-scans\n              description: \"List all scans for an application\"\n              call: \"stackhawk.list-scans\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: trigger-scan\n              description:\
  \ \"Trigger a new DAST scan\"\n              call: \"stackhawk.request-perch-scan\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications/{appId}/scans/{scanId}\n          name: scan\n          description: \"Scan details\"\n          operations:\n            - method: GET\n              name: get-scan\n              description: \"Get scan details\"\n              call: \"stackhawk.get-scan\"\n              with:\n                appId: \"rest.appId\"\n                scanId: \"rest.scanId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications/{appId}/scans/{scanId}/findings\n          name: findings\n          description: \"Security findings from a scan\"\n          operations:\n            - method: GET\n              name: list-findings\n              description:\
  \ \"List all security findings\"\n              call: \"stackhawk.list-findings\"\n              with:\n                appId: \"rest.appId\"\n                scanId: \"rest.scanId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications/{appId}/scans/{scanId}/findings/{findingId}\n          name: finding\n          description: \"Single security finding\"\n          operations:\n            - method: GET\n              name: get-finding\n              description: \"Get finding details\"\n              call: \"stackhawk.get-finding\"\n              with:\n                appId: \"rest.appId\"\n                scanId: \"rest.scanId\"\n                findingId: \"rest.findingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/policies\n          name: policies\n          description: \"Scan policies\"\n          operations:\n     \
  \       - method: GET\n              name: list-policies\n              description: \"List scan policies\"\n              call: \"stackhawk.list-policies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/scans/{scanId}/status\n          name: scan-status\n          description: \"Scan status\"\n          operations:\n            - method: GET\n              name: get-perch-scan-status\n              description: \"Get status of a running scan\"\n              call: \"stackhawk.get-perch-scan-status\"\n              with:\n                scanId: \"rest.scanId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: stackhawk-appsec-mcp\n      transport: http\n      description: \"MCP server for AI-assisted API security testing with StackHawk.\"\n      tools:\n        - name: list-applications\n          description:\
  \ \"List all applications configured in StackHawk for security testing\"\n          hints:\n            readOnly: true\n          call: \"stackhawk.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-scans\n          description: \"List security scan history for an application environment\"\n          hints:\n            readOnly: true\n          call: \"stackhawk.list-scans\"\n          with:\n            appId: \"tools.app_id\"\n            envId: \"tools.env_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-scan\n          description: \"Get detailed results for a specific security scan\"\n          hints:\n            readOnly: true\n          call: \"stackhawk.get-scan\"\n          with:\n            appId: \"tools.app_id\"\n            envId: \"tools.env_id\"\n            scanId: \"tools.scan_id\"\n          outputParameters:\n        \
  \    - type: object\n              mapping: \"$.\"\n\n        - name: list-findings\n          description: \"List all security vulnerabilities discovered in a scan\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stackhawk.list-findings\"\n          with:\n            appId: \"tools.app_id\"\n            envId: \"tools.env_id\"\n            scanId: \"tools.scan_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-finding\n          description: \"Get full details for a specific security vulnerability finding\"\n          hints:\n            readOnly: true\n          call: \"stackhawk.get-finding\"\n          with:\n            appId: \"tools.app_id\"\n            envId: \"tools.env_id\"\n            scanId: \"tools.scan_id\"\n            findingId: \"tools.finding_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: trigger-scan\n\
  \          description: \"Trigger a new DAST security scan for an application via StackHawk Perch\"\n          hints:\n            readOnly: false\n          call: \"stackhawk.request-perch-scan\"\n          with:\n            app_id: \"tools.app_id\"\n            env_id: \"tools.env_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-scan-status\n          description: \"Check the current status of a running or completed scan\"\n          hints:\n            readOnly: true\n          call: \"stackhawk.get-perch-scan-status\"\n          with:\n            scanId: \"tools.scan_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-scan-policies\n          description: \"List security scan policies configured for an organization\"\n          hints:\n            readOnly: true\n          call: \"stackhawk.list-policies\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stackhawk/refs/heads/main/capabilities/api-security-testing.yaml
tags:
- API Security
- DAST
- DevSecOps
- Security Testing
- Vulnerability Management
tools:
- description: List all applications configured in StackHawk for security testing
  hints:
    readOnly: true
  name: list-applications
- description: List security scan history for an application environment
  hints:
    readOnly: true
  name: list-scans
- description: Get detailed results for a specific security scan
  hints:
    readOnly: true
  name: get-scan
- description: List all security vulnerabilities discovered in a scan
  hints:
    openWorld: true
    readOnly: true
  name: list-findings
- description: Get full details for a specific security vulnerability finding
  hints:
    readOnly: true
  name: get-finding
- description: Trigger a new DAST security scan for an application via StackHawk Perch
  hints:
    readOnly: false
  name: trigger-scan
- description: Check the current status of a running or completed scan
  hints:
    readOnly: true
  name: get-scan-status
- description: List security scan policies configured for an organization
  hints:
    readOnly: true
  name: list-scan-policies
---
