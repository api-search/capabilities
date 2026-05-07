---
categories: []
consumed_apis: []
description: Unified compliance management workflow combining Vanta's vulnerability tracking, control monitoring, framework oversight, and vendor security reviews. Designed for compliance managers and security engineers managing SOC 2, ISO 27001, HIPAA, PCI DSS, and GDPR programs.
layout: capability
name: Vanta Compliance Management
operations:
- description: List all configured compliance frameworks and their readiness
  method: GET
  name: list-frameworks
  path: /v1/frameworks
- description: Query controls with status and framework filters
  method: GET
  name: list-controls
  path: /v1/controls
- description: Query automated test results for compliance evidence
  method: GET
  name: list-tests
  path: /v1/tests
- description: List vulnerabilities with severity and SLA filters
  method: GET
  name: list-vulnerabilities
  path: /v1/vulnerabilities
- description: List vendors and security review status
  method: GET
  name: list-vendors
  path: /v1/vendors
- description: Add a new vendor for security review
  method: POST
  name: create-vendor
  path: /v1/vendors
- description: Get vendor details and security review status
  method: GET
  name: get-vendor
  path: /v1/vendors/{id}
- description: Update vendor risk level and review status
  method: PATCH
  name: update-vendor
  path: /v1/vendors/{id}
- description: List compliance evidence documents
  method: GET
  name: list-documents
  path: /v1/documents
- description: Upload compliance evidence document
  method: POST
  name: upload-document
  path: /v1/documents
- description: List people with security task and training status
  method: GET
  name: list-people
  path: /v1/people
- description: List monitored computers and compliance status
  method: GET
  name: list-computers
  path: /v1/computers
- description: List configured integrations and connection status
  method: GET
  name: list-integrations
  path: /v1/integrations
personas: []
provider_name: Vanta
provider_slug: vanta
search_terms:
- list vulnerabilities
- governance
- list integrations
- get all failing controls to prioritize remediation efforts
- list endpoint devices that are failing compliance checks
- compliance evidence document management
- list computers
- add a new third-party vendor to vanta for security review tracking
- update vendor risk level and review status
- individual vendor management
- integration status monitoring
- update a vendor's risk level or review status after security assessment
- add a new vendor for security review
- list failing controls
- list all configured compliance frameworks and their readiness
- list configured integrations and connection status
- iso 27001
- query third-party vendors and their security review status
- compliance
- hipaa
- update vendor
- query controls with status and framework filters
- endpoint device compliance monitoring
- get detailed information about a specific vendor's security review
- list non compliant computers
- vanta
- upload document
- compliance framework status and management
- list controls
- list people with security task and training status
- compliance controls oversight
- third-party vendor security reviews
- list personnel with security training completion and overdue task status
- vulnerability tracking and remediation management
- update vendor review
- list frameworks
- get vendor details and security review status
- list vendors and security review status
- get vendor
- upload compliance evidence document
- personnel security task tracking
- list vendors
- list people
- list compliance evidence documents
- soc 2
- list vulnerabilities with severity and sla filters
- list monitored computers and compliance status
- list security vulnerabilities with severity and remediation status filters
- get all critical severity open vulnerabilities for immediate remediation
- list all configured integrations and their connection health
- list compliance evidence documents uploaded to vanta
- create vendor
- list compliance frameworks (soc 2, iso 27001, hipaa, pci dss, gdpr) and their readiness status
- cybersecurity
- list documents
- list critical vulnerabilities
- list tests
- query compliance controls with optional framework and status filters to identify gaps
- security
- risk management
- automated compliance test results
- query automated compliance test results to identify evidence gaps
- query automated test results for compliance evidence
slug: compliance-management
source_filename: compliance-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vanta Compliance Management\n  description: Unified compliance management workflow combining Vanta's vulnerability tracking, control monitoring, framework\n    oversight, and vendor security reviews. Designed for compliance managers and security engineers managing SOC 2, ISO 27001,\n    HIPAA, PCI DSS, and GDPR programs.\n  tags:\n  - Vanta\n  - Compliance\n  - Cybersecurity\n  - Governance\n  - Risk Management\n  - SOC 2\n  - ISO 27001\n  - HIPAA\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VANTA_ACCESS_TOKEN: VANTA_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: vanta\n    baseUri: https://api.vanta.com\n    description: Vanta compliance management API\n    authentication:\n      type: bearer\n      token: '{{VANTA_ACCESS_TOKEN}}'\n    resources:\n    - name: users\n      path: /v1/users\n      description: Active user management\n      operations:\n      - name: list-users\n\
  \        method: GET\n        description: List active users in the organization\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of items per page (1-100)\n        - name: pageCursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people\n      path: /v1/people\n      description: Personnel management and security task tracking\n      operations:\n      - name: list-people\n        method: GET\n        description: List people with employment status and training completion\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of items per page\n        - name: pageCursor\n    \
  \      in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vulnerabilities\n      path: /v1/vulnerabilities\n      description: Vulnerability tracking and remediation\n      operations:\n      - name: list-vulnerabilities\n        method: GET\n        description: List all vulnerabilities with severity and SLA filters\n        inputParameters:\n        - name: severity\n          in: query\n          type: string\n          required: false\n          description: Filter by severity (CRITICAL, HIGH, MEDIUM, LOW)\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status (OPEN, REMEDIATED, ACCEPTED)\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number\
  \ of items per page\n        - name: pageCursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: controls\n      path: /v1/controls\n      description: Compliance controls and framework management\n      operations:\n      - name: list-controls\n        method: GET\n        description: Query compliance controls with status and framework filters\n        inputParameters:\n        - name: frameworkId\n          in: query\n          type: string\n          required: false\n          description: Filter by framework identifier\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by control status\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description:\
  \ Number of items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: frameworks\n      path: /v1/frameworks\n      description: Compliance framework management\n      operations:\n      - name: list-frameworks\n        method: GET\n        description: List all configured compliance frameworks\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tests\n      path: /v1/tests\n      description: Automated compliance test results\n      operations:\n      - name: list-tests\n        method: GET\n        description: Query and filter automated compliance test results\n        inputParameters:\n        - name: status\n          in: query\n\
  \          type: string\n          required: false\n          description: Filter by test status (PASS, FAIL, DISABLED, NA)\n        - name: frameworkId\n          in: query\n          type: string\n          required: false\n          description: Filter tests by framework\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents\n      path: /v1/documents\n      description: Compliance evidence document management\n      operations:\n      - name: list-documents\n        method: GET\n        description: Retrieve compliance evidence documents\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of items per page\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upload-document\n        method: POST\n        description: Upload a compliance evidence document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vendors\n      path: /v1/vendors\n      description: Third-party vendor security review management\n      operations:\n      - name: list-vendors\n        method: GET\n        description: Query vendors and security review information\n        inputParameters:\n        - name: riskLevel\n          in: query\n          type: string\n          required: false\n          description: Filter by risk level (CRITICAL, HIGH, MEDIUM, LOW)\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of items per page\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: create-vendor\n        method: POST\n        description: Create a new vendor for security review tracking\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            url: '{{tools.url}}'\n            riskLevel: '{{tools.riskLevel}}'\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vendor-detail\n      path: /v1/vendors/{vendorId}\n      description: Individual vendor management\n      operations:\n      - name: get-vendor\n        method: GET\n        description: Get vendor details and security review status\n        inputParameters:\n        - name: vendorId\n          in: path\n          type: string\n          required: true\n          description: Vendor identifier\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n      - name: update-vendor\n        method: PATCH\n        description: Update vendor security review information\n        inputParameters:\n        - name: vendorId\n          in: path\n          type: string\n          required: true\n          description: Vendor identifier\n        body:\n          type: json\n          data:\n            riskLevel: '{{tools.riskLevel}}'\n            reviewStatus: '{{tools.reviewStatus}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resources\n      path: /v1/resources\n      description: Monitored resource scoping\n      operations:\n      - name: list-resources\n        method: GET\n        description: List all monitored resources in compliance scope\n        inputParameters:\n        - name: resourceType\n          in: query\n          type: string\n          required: false\n          description:\
  \ Filter by resource type\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: computers\n      path: /v1/computers\n      description: Endpoint device compliance monitoring\n      operations:\n      - name: list-computers\n        method: GET\n        description: List monitored computers with compliance status\n        inputParameters:\n        - name: complianceStatus\n          in: query\n          type: string\n          required: false\n          description: Filter by compliance status (COMPLIANT, NON_COMPLIANT)\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n    - name: integrations\n      path: /v1/integrations\n      description: Integration configuration management\n      operations:\n      - name: list-integrations\n        method: GET\n        description: List all configured integrations and their status\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vanta-compliance-api\n    description: Unified REST API for Vanta compliance management workflows.\n    resources:\n    - path: /v1/frameworks\n      name: frameworks\n      description: Compliance framework status and management\n      operations:\n      - method: GET\n        name: list-frameworks\n        description: List all configured compliance\
  \ frameworks and their readiness\n        call: vanta.list-frameworks\n        with:\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/controls\n      name: controls\n      description: Compliance controls oversight\n      operations:\n      - method: GET\n        name: list-controls\n        description: Query controls with status and framework filters\n        call: vanta.list-controls\n        with:\n          frameworkId: rest.frameworkId\n          status: rest.status\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tests\n      name: tests\n      description: Automated compliance test results\n      operations:\n      - method: GET\n        name: list-tests\n        description: Query automated test results for compliance evidence\n        call: vanta.list-tests\n        with:\n          status: rest.status\n          frameworkId:\
  \ rest.frameworkId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vulnerabilities\n      name: vulnerabilities\n      description: Vulnerability tracking and remediation management\n      operations:\n      - method: GET\n        name: list-vulnerabilities\n        description: List vulnerabilities with severity and SLA filters\n        call: vanta.list-vulnerabilities\n        with:\n          severity: rest.severity\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vendors\n      name: vendors\n      description: Third-party vendor security reviews\n      operations:\n      - method: GET\n        name: list-vendors\n        description: List vendors and security review status\n        call: vanta.list-vendors\n        with:\n          riskLevel: rest.riskLevel\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name:\
  \ create-vendor\n        description: Add a new vendor for security review\n        call: vanta.create-vendor\n        with:\n          name: rest.name\n          url: rest.url\n          riskLevel: rest.riskLevel\n          description: rest.description\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vendors/{id}\n      name: vendor-detail\n      description: Individual vendor management\n      operations:\n      - method: GET\n        name: get-vendor\n        description: Get vendor details and security review status\n        call: vanta.get-vendor\n        with:\n          vendorId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-vendor\n        description: Update vendor risk level and review status\n        call: vanta.update-vendor\n        with:\n          vendorId: rest.id\n          riskLevel: rest.riskLevel\n          reviewStatus: rest.reviewStatus\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents\n      name: documents\n      description: Compliance evidence document management\n      operations:\n      - method: GET\n        name: list-documents\n        description: List compliance evidence documents\n        call: vanta.list-documents\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: upload-document\n        description: Upload compliance evidence document\n        call: vanta.upload-document\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/people\n      name: people\n      description: Personnel security task tracking\n      operations:\n      - method: GET\n        name: list-people\n        description: List people with security task and training status\n        call: vanta.list-people\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/computers\n\
  \      name: computers\n      description: Endpoint device compliance monitoring\n      operations:\n      - method: GET\n        name: list-computers\n        description: List monitored computers and compliance status\n        call: vanta.list-computers\n        with:\n          complianceStatus: rest.complianceStatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/integrations\n      name: integrations\n      description: Integration status monitoring\n      operations:\n      - method: GET\n        name: list-integrations\n        description: List configured integrations and connection status\n        call: vanta.list-integrations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vanta-compliance-mcp\n    transport: http\n    description: MCP server for AI-assisted compliance management and security posture monitoring.\n    tools:\n    - name: list-frameworks\n      description:\
  \ List compliance frameworks (SOC 2, ISO 27001, HIPAA, PCI DSS, GDPR) and their readiness status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vanta.list-frameworks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-controls\n      description: Query compliance controls with optional framework and status filters to identify gaps\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vanta.list-controls\n      with:\n        frameworkId: tools.frameworkId\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-failing-controls\n      description: Get all FAILING controls to prioritize remediation efforts\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vanta.list-controls\n      with:\n        status: FAILING\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tests\n      description:\
  \ Query automated compliance test results to identify evidence gaps\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vanta.list-tests\n      with:\n        status: tools.status\n        frameworkId: tools.frameworkId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vulnerabilities\n      description: List security vulnerabilities with severity and remediation status filters\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vanta.list-vulnerabilities\n      with:\n        severity: tools.severity\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-critical-vulnerabilities\n      description: Get all CRITICAL severity open vulnerabilities for immediate remediation\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vanta.list-vulnerabilities\n      with:\n        severity: CRITICAL\n        status: OPEN\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vendors\n      description: Query third-party vendors and their security review status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vanta.list-vendors\n      with:\n        riskLevel: tools.riskLevel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-vendor\n      description: Add a new third-party vendor to Vanta for security review tracking\n      hints:\n        readOnly: false\n        destructive: false\n      call: vanta.create-vendor\n      with:\n        name: tools.name\n        url: tools.url\n        riskLevel: tools.riskLevel\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vendor\n      description: Get detailed information about a specific vendor's security review\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vanta.get-vendor\n\
  \      with:\n        vendorId: tools.vendorId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-vendor-review\n      description: Update a vendor's risk level or review status after security assessment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: vanta.update-vendor\n      with:\n        vendorId: tools.vendorId\n        riskLevel: tools.riskLevel\n        reviewStatus: tools.reviewStatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-people\n      description: List personnel with security training completion and overdue task status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vanta.list-people\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-non-compliant-computers\n      description: List endpoint devices that are failing compliance checks\n      hints:\n        readOnly: true\n\
  \        openWorld: false\n      call: vanta.list-computers\n      with:\n        complianceStatus: NON_COMPLIANT\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-integrations\n      description: List all configured integrations and their connection health\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vanta.list-integrations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-documents\n      description: List compliance evidence documents uploaded to Vanta\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vanta.list-documents\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vanta/refs/heads/main/capabilities/compliance-management.yaml
tags:
- Vanta
- Compliance
- Cybersecurity
- Governance
- Risk Management
- SOC 2
- ISO 27001
- HIPAA
tools:
- description: List compliance frameworks (SOC 2, ISO 27001, HIPAA, PCI DSS, GDPR) and their readiness status
  hints:
    openWorld: false
    readOnly: true
  name: list-frameworks
- description: Query compliance controls with optional framework and status filters to identify gaps
  hints:
    openWorld: false
    readOnly: true
  name: list-controls
- description: Get all FAILING controls to prioritize remediation efforts
  hints:
    openWorld: false
    readOnly: true
  name: list-failing-controls
- description: Query automated compliance test results to identify evidence gaps
  hints:
    openWorld: false
    readOnly: true
  name: list-tests
- description: List security vulnerabilities with severity and remediation status filters
  hints:
    openWorld: false
    readOnly: true
  name: list-vulnerabilities
- description: Get all CRITICAL severity open vulnerabilities for immediate remediation
  hints:
    openWorld: false
    readOnly: true
  name: list-critical-vulnerabilities
- description: Query third-party vendors and their security review status
  hints:
    openWorld: false
    readOnly: true
  name: list-vendors
- description: Add a new third-party vendor to Vanta for security review tracking
  hints:
    destructive: false
    readOnly: false
  name: create-vendor
- description: Get detailed information about a specific vendor's security review
  hints:
    openWorld: false
    readOnly: true
  name: get-vendor
- description: Update a vendor's risk level or review status after security assessment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-vendor-review
- description: List personnel with security training completion and overdue task status
  hints:
    openWorld: false
    readOnly: true
  name: list-people
- description: List endpoint devices that are failing compliance checks
  hints:
    openWorld: false
    readOnly: true
  name: list-non-compliant-computers
- description: List all configured integrations and their connection health
  hints:
    openWorld: false
    readOnly: true
  name: list-integrations
- description: List compliance evidence documents uploaded to Vanta
  hints:
    openWorld: false
    readOnly: true
  name: list-documents
---
