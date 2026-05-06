---
categories: []
consumed_apis: []
description: Unified application security testing capability combining Synopsys Polaris platform APIs for project management, scan orchestration, security issue tracking, and report generation. Enables DevSecOps teams to automate security testing workflows across SAST, SCA, and IAST testing types.
layout: capability
name: Synopsys Application Security Testing
operations:
- description: List all application security projects.
  method: GET
  name: list-projects
  path: /v1/projects
- description: Get details for a specific security project.
  method: GET
  name: get-project
  path: /v1/projects
- description: List scan runs with status and issue counts.
  method: GET
  name: list-scans
  path: /v1/scans
- description: List security issues found by Polaris scans.
  method: GET
  name: list-issues
  path: /v1/issues
- description: Get details for a specific security issue.
  method: GET
  name: get-issue
  path: /v1/issues
- description: Generate a security report for a project.
  method: POST
  name: generate-report
  path: /v1/reports
personas: []
provider_name: Synopsys
provider_slug: synopsys
search_terms:
- get details for a specific security issue.
- list security scan runs for a project or branch with status tracking.
- list all application security projects.
- software security
- list scans
- get issue
- semiconductor design
- list issues
- list all application security projects in the synopsys polaris platform.
- get details for a specific polaris security project including branches.
- synopsys
- eda tools
- generate a security report for a project.
- sast
- security issues from scans.
- get full details for a specific security issue including cwe, file path, and line number.
- security scan management.
- generate report
- list scan runs with status and issue counts.
- get details for a specific security project.
- list security issues discovered by polaris scans, filterable by severity and type.
- security report generation.
- application security project management.
- generate security report
- static analysis
- list security issues found by polaris scans.
- generate a security report (pdf, json, or csv) for a polaris project.
- get project
- list projects
- devsecops
- sca
- application security testing
- software composition analysis
slug: application-security-testing
source_filename: application-security-testing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Synopsys Application Security Testing\n  description: Unified application security testing capability combining Synopsys Polaris platform APIs for project management,\n    scan orchestration, security issue tracking, and report generation. Enables DevSecOps teams to automate security testing\n    workflows across SAST, SCA, and IAST testing types.\n  tags:\n  - Synopsys\n  - Application Security Testing\n  - DevSecOps\n  - Static Analysis\n  - Software Composition Analysis\n  - SAST\n  - SCA\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    POLARIS_ACCESS_TOKEN: POLARIS_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: synopsys-polaris\n    baseUri: https://polaris.synopsys.com/api/v1\n    description: Synopsys Polaris application security testing API.\n    authentication:\n      type: bearer\n      token: '{{POLARIS_ACCESS_TOKEN}}'\n    resources:\n    - name: projects\n  \
  \    path: /portfolios/projects\n      description: Security project management.\n      operations:\n      - name: list-projects\n        method: GET\n        description: Retrieves a list of application security projects.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n        - name: filter\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-project\n        method: GET\n        description: Retrieves details for a specific security project.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n    - name: scans\n      path: /jobs/runs\n      description: Scan run management.\n      operations:\n      - name: list-scans\n        method: GET\n        description: Retrieves a list of scan runs with status and results.\n        inputParameters:\n        - name: projectId\n          in: query\n          type: string\n          required: false\n        - name: branchId\n          in: query\n          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issues\n      path: /issues\n      description: Security issue retrieval.\n      operations:\n      - name: list-issues\n        method: GET\n        description: Retrieves security issues found by Polaris scans.\n        inputParameters:\n        - name: projectId\n       \
  \   in: query\n          type: string\n          required: false\n        - name: branchId\n          in: query\n          type: string\n          required: false\n        - name: severity\n          in: query\n          type: string\n          required: false\n        - name: type\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-issue\n        method: GET\n        description: Retrieves details for a specific security issue.\n        inputParameters:\n        - name: issueId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: reports\n      path: /reports\n      description: Security report generation.\n      operations:\n      - name: generate-report\n        method: POST\n        description: Initiates generation of a security report.\n        inputParameters:\n        - name: projectId\n          in: body\n          type: string\n          required: true\n        - name: format\n          in: body\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            projectId: '{{tools.projectId}}'\n            format: '{{tools.format}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: synopsys-appsec-api\n    description: Unified REST API for Synopsys application security testing workflows.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description:\
  \ Application security project management.\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all application security projects.\n        call: synopsys-polaris.list-projects\n        with:\n          page: rest.page\n          pageSize: rest.pageSize\n          filter: rest.filter\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-project\n        description: Get details for a specific security project.\n        call: synopsys-polaris.get-project\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/scans\n      name: scans\n      description: Security scan management.\n      operations:\n      - method: GET\n        name: list-scans\n        description: List scan runs with status and issue counts.\n        call: synopsys-polaris.list-scans\n        with:\n          projectId: rest.projectId\n\
  \          branchId: rest.branchId\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/issues\n      name: issues\n      description: Security issues from scans.\n      operations:\n      - method: GET\n        name: list-issues\n        description: List security issues found by Polaris scans.\n        call: synopsys-polaris.list-issues\n        with:\n          projectId: rest.projectId\n          branchId: rest.branchId\n          severity: rest.severity\n          type: rest.type\n          page: rest.page\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-issue\n        description: Get details for a specific security issue.\n        call: synopsys-polaris.get-issue\n        with:\n          issueId: rest.issueId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n   \
  \   name: reports\n      description: Security report generation.\n      operations:\n      - method: POST\n        name: generate-report\n        description: Generate a security report for a project.\n        call: synopsys-polaris.generate-report\n        with:\n          projectId: rest.projectId\n          format: rest.format\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: synopsys-appsec-mcp\n    transport: http\n    description: MCP server for AI-assisted application security testing using Synopsys Polaris.\n    tools:\n    - name: list-projects\n      description: List all application security projects in the Synopsys Polaris platform.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: synopsys-polaris.list-projects\n      with:\n        page: tools.page\n        pageSize: tools.pageSize\n        filter: tools.filter\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-project\n      description: Get details for a specific Polaris security project including branches.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: synopsys-polaris.get-project\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-scans\n      description: List security scan runs for a project or branch with status tracking.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: synopsys-polaris.list-scans\n      with:\n        projectId: tools.projectId\n        branchId: tools.branchId\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-issues\n      description: List security issues discovered by Polaris scans, filterable by severity and type.\n      hints:\n        readOnly: true\n      \
  \  destructive: false\n        idempotent: true\n      call: synopsys-polaris.list-issues\n      with:\n        projectId: tools.projectId\n        branchId: tools.branchId\n        severity: tools.severity\n        type: tools.type\n        page: tools.page\n        pageSize: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-issue\n      description: Get full details for a specific security issue including CWE, file path, and line number.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: synopsys-polaris.get-issue\n      with:\n        issueId: tools.issueId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-security-report\n      description: Generate a security report (PDF, JSON, or CSV) for a Polaris project.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: synopsys-polaris.generate-report\n\
  \      with:\n        projectId: tools.projectId\n        format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/synopsys/refs/heads/main/capabilities/application-security-testing.yaml
tags:
- Synopsys
- Application Security Testing
- DevSecOps
- Static Analysis
- Software Composition Analysis
- SAST
- SCA
tools:
- description: List all application security projects in the Synopsys Polaris platform.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-projects
- description: Get details for a specific Polaris security project including branches.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-project
- description: List security scan runs for a project or branch with status tracking.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-scans
- description: List security issues discovered by Polaris scans, filterable by severity and type.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-issues
- description: Get full details for a specific security issue including CWE, file path, and line number.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-issue
- description: Generate a security report (PDF, JSON, or CSV) for a Polaris project.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generate-security-report
---
