---
categories: []
consumed_apis: []
description: Unified workflow capability for integrating Veracode application security into DevSecOps pipelines. Enables development teams and security engineers to automate application onboarding, trigger security scans, retrieve findings filtered by severity and policy compliance, and generate compliance reports — all through a single unified API. Combines the Applications, Findings, and Reporting APIs.
layout: capability
name: Veracode DevSecOps Pipeline
operations:
- description: List all applications with policy compliance filtering
  method: GET
  name: list-applications
  path: /v1/applications
- description: Create a new application profile
  method: POST
  name: create-application
  path: /v1/applications
- description: Get application details
  method: GET
  name: get-application
  path: /v1/applications/{applicationGuid}
- description: Get policy compliance for an application
  method: GET
  name: get-policy-compliance
  path: /v1/applications/{applicationGuid}/policy-compliance
- description: List findings with severity and scan type filtering
  method: GET
  name: list-findings
  path: /v1/applications/{applicationGuid}/findings
- description: Generate an async security report
  method: POST
  name: generate-report
  path: /v1/reports
- description: Get report results by ID
  method: GET
  name: get-report
  path: /v1/reports/{reportId}
personas: []
provider_name: Veracode
provider_slug: veracode
search_terms:
- get policy compliance evaluation status for an application
- security compliance reports
- get report
- generate an asynchronous security findings or compliance report
- security testing
- get report results by id
- list veracode applications, optionally filtered by policy compliance status or name
- sast
- get details for a specific veracode application by guid
- generate report
- veracode
- application security
- application portfolio management
- individual application management
- list security findings for a veracode application, filterable by scan type, severity, cwe, and policy violations
- retrieve a generated security report by id
- security findings from all scan types
- get policy compliance
- get static analysis flaw code path details for a specific finding
- ci/cd
- get policy compliance for an application
- get static flaw info
- list findings with severity and scan type filtering
- dast
- get security report
- generate security report
- list all applications with policy compliance filtering
- get application details
- devsecops
- create a new application profile in the veracode platform
- generate an async security report
- create application
- get application
- list findings
- list applications
- create a new application profile
- sca
- retrieve generated reports
- policy compliance status
slug: devsecops-pipeline
source_filename: devsecops-pipeline.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Veracode DevSecOps Pipeline\n  description: Unified workflow capability for integrating Veracode application security into DevSecOps pipelines. Enables\n    development teams and security engineers to automate application onboarding, trigger security scans, retrieve findings\n    filtered by severity and policy compliance, and generate compliance reports — all through a single unified API. Combines\n    the Applications, Findings, and Reporting APIs.\n  tags:\n  - Veracode\n  - DevSecOps\n  - Application Security\n  - SAST\n  - DAST\n  - CI/CD\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VERACODE_API_ID: VERACODE_API_ID\n    VERACODE_API_KEY: VERACODE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: veracode-applications\n    baseUri: https://api.veracode.com\n    description: Veracode Applications REST API\n    authentication:\n      type: hmac\n      apiId: '{{VERACODE_API_ID}}'\n\
  \      apiKey: '{{VERACODE_API_KEY}}'\n    resources:\n    - name: applications\n      path: /appsec/v1/applications\n      description: Application portfolio management\n      operations:\n      - name: list-applications\n        method: GET\n        description: List all applications in portfolio with filtering\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Filter by application name\n        - name: policy_compliance\n          in: query\n          type: string\n          required: false\n          description: Filter by policy compliance status\n        - name: tag\n          in: query\n          type: string\n          required: false\n          description: Filter by tag\n        - name: modified_after\n          in: query\n          type: string\n          required: false\n          description: Filter by modification date\n        - name: page\n          in: query\n          type: integer\n\
  \          required: false\n          description: Page number\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-application\n        method: POST\n        description: Create a new application profile\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            profile: '{{tools.profile}}'\n    - name: application-by-id\n      path: /appsec/v1/applications/{applicationGuid}\n      description: Individual application management\n      operations:\n      - name: get-application\n        method: GET\n        description: Get details for a specific application\n        inputParameters:\n        - name: applicationGuid\n\
  \          in: path\n          type: string\n          required: true\n          description: Application GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-application\n        method: PUT\n        description: Update an application profile\n        inputParameters:\n        - name: applicationGuid\n          in: path\n          type: string\n          required: true\n          description: Application GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            profile: '{{tools.profile}}'\n      - name: delete-application\n        method: DELETE\n        description: Delete an application profile\n        inputParameters:\n        - name: applicationGuid\n          in: path\n          type: string\n          required: true\n          description:\
  \ Application GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policy-compliance\n      path: /appsec/v1/applications/{applicationGuid}/policy_compliance\n      description: Application policy compliance status\n      operations:\n      - name: get-policy-compliance\n        method: GET\n        description: Get policy compliance evaluation for an application\n        inputParameters:\n        - name: applicationGuid\n          in: path\n          type: string\n          required: true\n          description: Application GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: veracode-findings\n    baseUri: https://api.veracode.com\n    description: Veracode Findings REST API\n    authentication:\n      type: hmac\n      apiId: '{{VERACODE_API_ID}}'\n      apiKey: '{{VERACODE_API_KEY}}'\n\
  \    resources:\n    - name: findings\n      path: /appsec/v2/applications/{applicationGuid}/findings\n      description: Application security findings\n      operations:\n      - name: list-findings\n        method: GET\n        description: List security findings for an application with filtering\n        inputParameters:\n        - name: applicationGuid\n          in: path\n          type: string\n          required: true\n          description: Application GUID\n        - name: scan_type\n          in: query\n          type: array\n          required: false\n          description: 'Filter by scan type: STATIC, DYNAMIC, MANUAL, SCA'\n        - name: severity\n          in: query\n          type: integer\n          required: false\n          description: Filter by severity level 0-5\n        - name: severity_gte\n          in: query\n          type: integer\n          required: false\n          description: Minimum severity level\n        - name: cwe\n          in: query\n          type:\
  \ string\n          required: false\n          description: Filter by CWE ID\n        - name: violates_policy\n          in: query\n          type: boolean\n          required: false\n          description: Only policy-violating findings\n        - name: new\n          in: query\n          type: boolean\n          required: false\n          description: Only new findings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dynamic-flaw-info\n      path: /appsec/v2/applications/{applicationGuid}/findings/{issueId}/dynamic_flaw_info\n      description: Dynamic analysis flaw details\n      operations:\n      - name: get-dynamic-flaw-info\n        method: GET\n        description: Get detailed dynamic analysis vulnerability information\n        inputParameters:\n        - name: applicationGuid\n          in: path\n          type: string\n          required: true\n          description: Application GUID\n\
  \        - name: issueId\n          in: path\n          type: integer\n          required: true\n          description: Finding issue ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: static-flaw-info\n      path: /appsec/v2/applications/{applicationGuid}/findings/{findingId}/static_flaw_info\n      description: Static analysis flaw code paths\n      operations:\n      - name: get-static-flaw-info\n        method: GET\n        description: Get static analysis flaw code path data\n        inputParameters:\n        - name: applicationGuid\n          in: path\n          type: string\n          required: true\n          description: Application GUID\n        - name: findingId\n          in: path\n          type: integer\n          required: true\n          description: Finding ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n  - type: http\n    namespace: veracode-reporting\n    baseUri: https://api.veracode.com\n    description: Veracode Reporting REST API\n    authentication:\n      type: hmac\n      apiId: '{{VERACODE_API_ID}}'\n      apiKey: '{{VERACODE_API_KEY}}'\n    resources:\n    - name: reports\n      path: /appsec/v1/analytics/report\n      description: Asynchronous security report generation\n      operations:\n      - name: generate-report\n        method: POST\n        description: Submit a report generation request\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            report_type: '{{tools.report_type}}'\n            scan_type: '{{tools.scan_type}}'\n            status: '{{tools.status}}'\n            severity: '{{tools.severity}}'\n    - name: report-by-id\n      path: /appsec/v1/analytics/report/{reportId}\n      description:\
  \ Report retrieval\n      operations:\n      - name: get-report\n        method: GET\n        description: Retrieve a generated report by ID\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Report ID from generate request\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: veracode-devsecops-api\n    description: Unified REST API for DevSecOps pipeline security automation.\n    resources:\n    - path: /v1/applications\n      name: applications\n      description: Application portfolio management\n     \
  \ operations:\n      - method: GET\n        name: list-applications\n        description: List all applications with policy compliance filtering\n        call: veracode-applications.list-applications\n        with:\n          name: rest.name\n          policy_compliance: rest.policy_compliance\n          tag: rest.tag\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-application\n        description: Create a new application profile\n        call: veracode-applications.create-application\n        with:\n          profile: rest.profile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{applicationGuid}\n      name: application-by-id\n      description: Individual application management\n      operations:\n      - method: GET\n        name: get-application\n        description: Get application details\n        call: veracode-applications.get-application\n        with:\n\
  \          applicationGuid: rest.applicationGuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{applicationGuid}/policy-compliance\n      name: policy-compliance\n      description: Policy compliance status\n      operations:\n      - method: GET\n        name: get-policy-compliance\n        description: Get policy compliance for an application\n        call: veracode-applications.get-policy-compliance\n        with:\n          applicationGuid: rest.applicationGuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{applicationGuid}/findings\n      name: findings\n      description: Security findings from all scan types\n      operations:\n      - method: GET\n        name: list-findings\n        description: List findings with severity and scan type filtering\n        call: veracode-findings.list-findings\n        with:\n          applicationGuid: rest.applicationGuid\n     \
  \     scan_type: rest.scan_type\n          severity_gte: rest.severity_gte\n          violates_policy: rest.violates_policy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Security compliance reports\n      operations:\n      - method: POST\n        name: generate-report\n        description: Generate an async security report\n        call: veracode-reporting.generate-report\n        with:\n          report_type: rest.report_type\n          scan_type: rest.scan_type\n          status: rest.status\n          severity: rest.severity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/{reportId}\n      name: report-by-id\n      description: Retrieve generated reports\n      operations:\n      - method: GET\n        name: get-report\n        description: Get report results by ID\n        call: veracode-reporting.get-report\n        with:\n          reportId:\
  \ rest.reportId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: veracode-devsecops-mcp\n    transport: http\n    description: MCP server for AI-assisted DevSecOps security automation and vulnerability triage.\n    tools:\n    - name: list-applications\n      description: List Veracode applications, optionally filtered by policy compliance status or name\n      hints:\n        readOnly: true\n        openWorld: true\n      call: veracode-applications.list-applications\n      with:\n        name: tools.name\n        policy_compliance: tools.policy_compliance\n        tag: tools.tag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application\n      description: Get details for a specific Veracode application by GUID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: veracode-applications.get-application\n      with:\n        applicationGuid: tools.applicationGuid\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-application\n      description: Create a new application profile in the Veracode Platform\n      hints:\n        readOnly: false\n        idempotent: false\n      call: veracode-applications.create-application\n      with:\n        profile: tools.profile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-policy-compliance\n      description: Get policy compliance evaluation status for an application\n      hints:\n        readOnly: true\n        idempotent: true\n      call: veracode-applications.get-policy-compliance\n      with:\n        applicationGuid: tools.applicationGuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-findings\n      description: List security findings for a Veracode application, filterable by scan type, severity, CWE, and policy violations\n      hints:\n        readOnly: true\n        openWorld: true\n\
  \      call: veracode-findings.list-findings\n      with:\n        applicationGuid: tools.applicationGuid\n        scan_type: tools.scan_type\n        severity_gte: tools.severity_gte\n        cwe: tools.cwe\n        violates_policy: tools.violates_policy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-static-flaw-info\n      description: Get static analysis flaw code path details for a specific finding\n      hints:\n        readOnly: true\n        idempotent: true\n      call: veracode-findings.get-static-flaw-info\n      with:\n        applicationGuid: tools.applicationGuid\n        findingId: tools.findingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-security-report\n      description: Generate an asynchronous security findings or compliance report\n      hints:\n        readOnly: false\n        idempotent: false\n      call: veracode-reporting.generate-report\n      with:\n        report_type: tools.report_type\n\
  \        scan_type: tools.scan_type\n        status: tools.status\n        severity: tools.severity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-security-report\n      description: Retrieve a generated security report by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: veracode-reporting.get-report\n      with:\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/veracode/refs/heads/main/capabilities/devsecops-pipeline.yaml
tags:
- Veracode
- DevSecOps
- Application Security
- SAST
- DAST
- CI/CD
tools:
- description: List Veracode applications, optionally filtered by policy compliance status or name
  hints:
    openWorld: true
    readOnly: true
  name: list-applications
- description: Get details for a specific Veracode application by GUID
  hints:
    idempotent: true
    readOnly: true
  name: get-application
- description: Create a new application profile in the Veracode Platform
  hints:
    idempotent: false
    readOnly: false
  name: create-application
- description: Get policy compliance evaluation status for an application
  hints:
    idempotent: true
    readOnly: true
  name: get-policy-compliance
- description: List security findings for a Veracode application, filterable by scan type, severity, CWE, and policy violations
  hints:
    openWorld: true
    readOnly: true
  name: list-findings
- description: Get static analysis flaw code path details for a specific finding
  hints:
    idempotent: true
    readOnly: true
  name: get-static-flaw-info
- description: Generate an asynchronous security findings or compliance report
  hints:
    idempotent: false
    readOnly: false
  name: generate-security-report
- description: Retrieve a generated security report by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-security-report
---
