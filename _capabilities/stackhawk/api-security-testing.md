---
categories: []
consumed_apis: []
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
- trigger a new dast scan
- get finding details
- list all security vulnerabilities discovered in a scan
- list policies
- single security finding
- check the current status of a running or completed scan
- get status of a running scan
- list scans
- scan status
- get finding
- vulnerability management
- scans for an application
- scan policies
- managed applications
- list security scan history for an application environment
- trigger a new dast security scan for an application via stackhawk perch
- list security scan policies configured for an organization
- scan details
- application security
- get scan
- list all applications configured in stackhawk for security testing
- list scan policies
- list all security findings
- security findings from a scan
- dast
- get detailed results for a specific security scan
- get scan details
- get full details for a specific security vulnerability finding
- get scan status
- devsecops
- get perch scan status
- list all scans for an application
- list all applications
- api security
- list findings
- list applications
- security testing
- trigger scan
slug: api-security-testing
source_filename: api-security-testing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: StackHawk API Security Testing\n  description: Unified workflow capability for API security testing and vulnerability management with StackHawk. Covers application\n    and environment management, scan orchestration via Perch, security finding triage, report generation, scan policy enforcement,\n    and repository management. Designed for AppSec engineers, DevSecOps teams, and security program managers.\n  tags:\n  - API Security\n  - DAST\n  - DevSecOps\n  - Security Testing\n  - Vulnerability Management\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STACKHAWK_API_KEY: STACKHAWK_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: stackhawk\n    baseUri: https://api.stackhawk.com\n    description: StackHawk API security testing platform\n    authentication:\n      type: bearer\n      token: '{{STACKHAWK_API_KEY}}'\n    resources:\n    - name: auth\n      path: /api/v1/auth\n   \
  \   description: Authentication and token management\n      operations:\n      - name: login\n        method: GET\n        description: Authenticate with API key to obtain JWT token\n        inputParameters:\n        - name: X-ApiKey\n          in: header\n          type: string\n          required: true\n          description: StackHawk API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /api/v2/org/{orgId}/apps\n      description: Manage applications\n      operations:\n      - name: list-applications\n        method: GET\n        description: List all applications for an organization\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-application\n        method: GET\n        description: Get application details\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scans\n      path: /api/v1/app/{appId}/env/{envId}/scan\n      description: Scan results and findings\n      operations:\n      - name: list-scans\n        method: GET\n        description: List scans for an application environment\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: envId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-scan\n        method: GET\n        description: Get details for a specific scan\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: envId\n          in: path\n          type: string\n          required: true\n        - name: scanId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-findings\n        method: GET\n        description: List all security findings from a scan\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: envId\n          in: path\n          type: string\n          required: true\n        - name: scanId\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-finding\n        method: GET\n        description: Get details for a specific security finding\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: envId\n          in: path\n          type: string\n          required: true\n        - name: scanId\n          in: path\n          type: string\n          required: true\n        - name: findingId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies\n      path: /api/v1/org/{orgId}/policy\n      description: Scan policy management\n      operations:\n      - name: list-policies\n    \
  \    method: GET\n        description: List all scan policies\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: perch\n      path: /api/v1/perch\n      description: Perch scan control\n      operations:\n      - name: request-perch-scan\n        method: POST\n        description: Trigger a scan via Perch\n        body:\n          type: json\n          data:\n            appId: '{{tools.app_id}}'\n            envId: '{{tools.env_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-perch-scan-status\n        method: GET\n        description: Get status of a Perch-initiated scan\n        inputParameters:\n        - name: scanId\n          in: path\n          type: string\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: stackhawk-appsec-api\n    description: Unified REST API for StackHawk application security testing.\n    resources:\n    - path: /v1/applications\n      name: applications\n      description: Managed applications\n      operations:\n      - method: GET\n        name: list-applications\n        description: List all applications\n        call: stackhawk.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{appId}/scans\n      name: scans\n      description: Scans for an application\n      operations:\n      - method: GET\n        name: list-scans\n        description: List all scans for an application\n        call: stackhawk.list-scans\n        with:\n          appId: rest.appId\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: POST\n        name: trigger-scan\n        description: Trigger a new DAST scan\n        call: stackhawk.request-perch-scan\n        with:\n          appId: rest.appId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{appId}/scans/{scanId}\n      name: scan\n      description: Scan details\n      operations:\n      - method: GET\n        name: get-scan\n        description: Get scan details\n        call: stackhawk.get-scan\n        with:\n          appId: rest.appId\n          scanId: rest.scanId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{appId}/scans/{scanId}/findings\n      name: findings\n      description: Security findings from a scan\n      operations:\n      - method: GET\n        name: list-findings\n        description: List all security findings\n        call: stackhawk.list-findings\n        with:\n          appId: rest.appId\n\
  \          scanId: rest.scanId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{appId}/scans/{scanId}/findings/{findingId}\n      name: finding\n      description: Single security finding\n      operations:\n      - method: GET\n        name: get-finding\n        description: Get finding details\n        call: stackhawk.get-finding\n        with:\n          appId: rest.appId\n          scanId: rest.scanId\n          findingId: rest.findingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies\n      name: policies\n      description: Scan policies\n      operations:\n      - method: GET\n        name: list-policies\n        description: List scan policies\n        call: stackhawk.list-policies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/scans/{scanId}/status\n      name: scan-status\n      description: Scan status\n      operations:\n  \
  \    - method: GET\n        name: get-perch-scan-status\n        description: Get status of a running scan\n        call: stackhawk.get-perch-scan-status\n        with:\n          scanId: rest.scanId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: stackhawk-appsec-mcp\n    transport: http\n    description: MCP server for AI-assisted API security testing with StackHawk.\n    tools:\n    - name: list-applications\n      description: List all applications configured in StackHawk for security testing\n      hints:\n        readOnly: true\n      call: stackhawk.list-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-scans\n      description: List security scan history for an application environment\n      hints:\n        readOnly: true\n      call: stackhawk.list-scans\n      with:\n        appId: tools.app_id\n        envId: tools.env_id\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: get-scan\n      description: Get detailed results for a specific security scan\n      hints:\n        readOnly: true\n      call: stackhawk.get-scan\n      with:\n        appId: tools.app_id\n        envId: tools.env_id\n        scanId: tools.scan_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-findings\n      description: List all security vulnerabilities discovered in a scan\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stackhawk.list-findings\n      with:\n        appId: tools.app_id\n        envId: tools.env_id\n        scanId: tools.scan_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-finding\n      description: Get full details for a specific security vulnerability finding\n      hints:\n        readOnly: true\n      call: stackhawk.get-finding\n      with:\n        appId: tools.app_id\n        envId: tools.env_id\n      \
  \  scanId: tools.scan_id\n        findingId: tools.finding_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: trigger-scan\n      description: Trigger a new DAST security scan for an application via StackHawk Perch\n      hints:\n        readOnly: false\n      call: stackhawk.request-perch-scan\n      with:\n        app_id: tools.app_id\n        env_id: tools.env_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-scan-status\n      description: Check the current status of a running or completed scan\n      hints:\n        readOnly: true\n      call: stackhawk.get-perch-scan-status\n      with:\n        scanId: tools.scan_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-scan-policies\n      description: List security scan policies configured for an organization\n      hints:\n        readOnly: true\n      call: stackhawk.list-policies\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n"
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
