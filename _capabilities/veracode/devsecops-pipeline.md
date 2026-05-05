---
api_specs:
- filename: veracode-applications-openapi.yml
  format: yaml
  label: veracode-applications
  slug: veracode-applications
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/veracode/refs/heads/main/openapi/veracode-applications-openapi.yml
- filename: veracode-findings-openapi.yml
  format: yaml
  label: veracode-findings
  slug: veracode-findings
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/veracode/refs/heads/main/openapi/veracode-findings-openapi.yml
- filename: veracode-reporting-openapi.yml
  format: yaml
  label: veracode-reporting
  slug: veracode-reporting
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/veracode/refs/heads/main/openapi/veracode-reporting-openapi.yml
categories: []
consumed_apis:
- veracode-applications
- veracode-findings
- veracode-reporting
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
- generate report
- veracode
- get application
- devsecops
- get static analysis flaw code path details for a specific finding
- retrieve generated reports
- create a new application profile
- sast
- get application details
- create a new application profile in the veracode platform
- application portfolio management
- security testing
- create application
- get policy compliance evaluation status for an application
- generate an asynchronous security findings or compliance report
- policy compliance status
- get policy compliance for an application
- list findings
- application security
- list security findings for a veracode application, filterable by scan type, severity, cwe, and policy violations
- get static flaw info
- get security report
- generate security report
- retrieve a generated security report by id
- get policy compliance
- list applications
- generate an async security report
- ci/cd
- security compliance reports
- list findings with severity and scan type filtering
- dast
- get report
- get details for a specific veracode application by guid
- list veracode applications, optionally filtered by policy compliance status or name
- security findings from all scan types
- sca
- list all applications with policy compliance filtering
- get report results by id
- individual application management
slug: devsecops-pipeline
source_filename: devsecops-pipeline.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Veracode DevSecOps Pipeline\"\n  description: >-\n    Unified workflow capability for integrating Veracode application security into\n    DevSecOps pipelines. Enables development teams and security engineers to automate\n    application onboarding, trigger security scans, retrieve findings filtered by\n    severity and policy compliance, and generate compliance reports — all through\n    a single unified API. Combines the Applications, Findings, and Reporting APIs.\n  tags:\n    - Veracode\n    - DevSecOps\n    - Application Security\n    - SAST\n    - DAST\n    - CI/CD\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VERACODE_API_ID: VERACODE_API_ID\n      VERACODE_API_KEY: VERACODE_API_KEY\n\ncapability:\n  consumes:\n    - import: veracode-applications\n      location: ./shared/veracode-applications.yaml\n    - import: veracode-findings\n      location: ./shared/veracode-findings.yaml\n\
  \    - import: veracode-reporting\n      location: ./shared/veracode-reporting.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: veracode-devsecops-api\n      description: \"Unified REST API for DevSecOps pipeline security automation.\"\n      resources:\n        - path: /v1/applications\n          name: applications\n          description: \"Application portfolio management\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List all applications with policy compliance filtering\"\n              call: \"veracode-applications.list-applications\"\n              with:\n                name: \"rest.name\"\n                policy_compliance: \"rest.policy_compliance\"\n                tag: \"rest.tag\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-application\n              description: \"Create\
  \ a new application profile\"\n              call: \"veracode-applications.create-application\"\n              with:\n                profile: \"rest.profile\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications/{applicationGuid}\n          name: application-by-id\n          description: \"Individual application management\"\n          operations:\n            - method: GET\n              name: get-application\n              description: \"Get application details\"\n              call: \"veracode-applications.get-application\"\n              with:\n                applicationGuid: \"rest.applicationGuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications/{applicationGuid}/policy-compliance\n          name: policy-compliance\n          description: \"Policy compliance status\"\n          operations:\n            - method:\
  \ GET\n              name: get-policy-compliance\n              description: \"Get policy compliance for an application\"\n              call: \"veracode-applications.get-policy-compliance\"\n              with:\n                applicationGuid: \"rest.applicationGuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications/{applicationGuid}/findings\n          name: findings\n          description: \"Security findings from all scan types\"\n          operations:\n            - method: GET\n              name: list-findings\n              description: \"List findings with severity and scan type filtering\"\n              call: \"veracode-findings.list-findings\"\n              with:\n                applicationGuid: \"rest.applicationGuid\"\n                scan_type: \"rest.scan_type\"\n                severity_gte: \"rest.severity_gte\"\n                violates_policy: \"rest.violates_policy\"\n       \
  \       outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/reports\n          name: reports\n          description: \"Security compliance reports\"\n          operations:\n            - method: POST\n              name: generate-report\n              description: \"Generate an async security report\"\n              call: \"veracode-reporting.generate-report\"\n              with:\n                report_type: \"rest.report_type\"\n                scan_type: \"rest.scan_type\"\n                status: \"rest.status\"\n                severity: \"rest.severity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/reports/{reportId}\n          name: report-by-id\n          description: \"Retrieve generated reports\"\n          operations:\n            - method: GET\n              name: get-report\n              description: \"Get report results by ID\"\n        \
  \      call: \"veracode-reporting.get-report\"\n              with:\n                reportId: \"rest.reportId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: veracode-devsecops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted DevSecOps security automation and vulnerability triage.\"\n      tools:\n        - name: list-applications\n          description: \"List Veracode applications, optionally filtered by policy compliance status or name\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"veracode-applications.list-applications\"\n          with:\n            name: \"tools.name\"\n            policy_compliance: \"tools.policy_compliance\"\n            tag: \"tools.tag\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-application\n          description:\
  \ \"Get details for a specific Veracode application by GUID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"veracode-applications.get-application\"\n          with:\n            applicationGuid: \"tools.applicationGuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-application\n          description: \"Create a new application profile in the Veracode Platform\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"veracode-applications.create-application\"\n          with:\n            profile: \"tools.profile\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-policy-compliance\n          description: \"Get policy compliance evaluation status for an application\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"veracode-applications.get-policy-compliance\"\
  \n          with:\n            applicationGuid: \"tools.applicationGuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-findings\n          description: \"List security findings for a Veracode application, filterable by scan type, severity, CWE, and policy violations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"veracode-findings.list-findings\"\n          with:\n            applicationGuid: \"tools.applicationGuid\"\n            scan_type: \"tools.scan_type\"\n            severity_gte: \"tools.severity_gte\"\n            cwe: \"tools.cwe\"\n            violates_policy: \"tools.violates_policy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-static-flaw-info\n          description: \"Get static analysis flaw code path details for a specific finding\"\n          hints:\n            readOnly: true\n           \
  \ idempotent: true\n          call: \"veracode-findings.get-static-flaw-info\"\n          with:\n            applicationGuid: \"tools.applicationGuid\"\n            findingId: \"tools.findingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: generate-security-report\n          description: \"Generate an asynchronous security findings or compliance report\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"veracode-reporting.generate-report\"\n          with:\n            report_type: \"tools.report_type\"\n            scan_type: \"tools.scan_type\"\n            status: \"tools.status\"\n            severity: \"tools.severity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-security-report\n          description: \"Retrieve a generated security report by ID\"\n          hints:\n            readOnly: true\n           \
  \ idempotent: true\n          call: \"veracode-reporting.get-report\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
