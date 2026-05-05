---
categories: []
consumed_apis:
- vanta
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
- soc 2
- endpoint device compliance monitoring
- update vendor risk level and review status
- add a new third-party vendor to vanta for security review tracking
- list endpoint devices that are failing compliance checks
- list personnel with security training completion and overdue task status
- list failing controls
- query automated test results for compliance evidence
- security
- list vendors
- create vendor
- list security vulnerabilities with severity and remediation status filters
- vanta
- list compliance evidence documents
- automated compliance test results
- list people with security task and training status
- cybersecurity
- query compliance controls with optional framework and status filters to identify gaps
- risk management
- compliance framework status and management
- update a vendor's risk level or review status after security assessment
- list controls
- add a new vendor for security review
- get all critical severity open vulnerabilities for immediate remediation
- query controls with status and framework filters
- compliance controls oversight
- list compliance frameworks (soc 2, iso 27001, hipaa, pci dss, gdpr) and their readiness status
- upload compliance evidence document
- update vendor review
- list vendors and security review status
- get all failing controls to prioritize remediation efforts
- list compliance evidence documents uploaded to vanta
- iso 27001
- query automated compliance test results to identify evidence gaps
- list all configured integrations and their connection health
- hipaa
- individual vendor management
- get detailed information about a specific vendor's security review
- list vulnerabilities
- list computers
- list integrations
- list critical vulnerabilities
- governance
- upload document
- integration status monitoring
- list configured integrations and connection status
- third-party vendor security reviews
- update vendor
- compliance evidence document management
- personnel security task tracking
- list non compliant computers
- get vendor details and security review status
- list monitored computers and compliance status
- compliance
- list all configured compliance frameworks and their readiness
- list frameworks
- list documents
- vulnerability tracking and remediation management
- list people
- list tests
- get vendor
- list vulnerabilities with severity and sla filters
- query third-party vendors and their security review status
slug: compliance-management
source_filename: compliance-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vanta Compliance Management\"\n  description: >-\n    Unified compliance management workflow combining Vanta's vulnerability tracking,\n    control monitoring, framework oversight, and vendor security reviews. Designed for\n    compliance managers and security engineers managing SOC 2, ISO 27001, HIPAA, PCI DSS,\n    and GDPR programs.\n  tags:\n    - Vanta\n    - Compliance\n    - Cybersecurity\n    - Governance\n    - Risk Management\n    - SOC 2\n    - ISO 27001\n    - HIPAA\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VANTA_ACCESS_TOKEN: VANTA_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: vanta\n      location: ./shared/vanta-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: vanta-compliance-api\n      description: \"Unified REST API for Vanta compliance management workflows.\"\n      resources:\n        - path: /v1/frameworks\n \
  \         name: frameworks\n          description: \"Compliance framework status and management\"\n          operations:\n            - method: GET\n              name: list-frameworks\n              description: \"List all configured compliance frameworks and their readiness\"\n              call: \"vanta.list-frameworks\"\n              with:\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/controls\n          name: controls\n          description: \"Compliance controls oversight\"\n          operations:\n            - method: GET\n              name: list-controls\n              description: \"Query controls with status and framework filters\"\n              call: \"vanta.list-controls\"\n              with:\n                frameworkId: \"rest.frameworkId\"\n                status: \"rest.status\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tests\n          name: tests\n          description: \"Automated compliance test results\"\n          operations:\n            - method: GET\n              name: list-tests\n              description: \"Query automated test results for compliance evidence\"\n              call: \"vanta.list-tests\"\n              with:\n                status: \"rest.status\"\n                frameworkId: \"rest.frameworkId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vulnerabilities\n          name: vulnerabilities\n          description: \"Vulnerability tracking and remediation management\"\n          operations:\n            - method: GET\n              name: list-vulnerabilities\n              description: \"List vulnerabilities with severity and SLA filters\"\n              call: \"vanta.list-vulnerabilities\"\n              with:\n\
  \                severity: \"rest.severity\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vendors\n          name: vendors\n          description: \"Third-party vendor security reviews\"\n          operations:\n            - method: GET\n              name: list-vendors\n              description: \"List vendors and security review status\"\n              call: \"vanta.list-vendors\"\n              with:\n                riskLevel: \"rest.riskLevel\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-vendor\n              description: \"Add a new vendor for security review\"\n              call: \"vanta.create-vendor\"\n              with:\n                name: \"rest.name\"\n                url: \"rest.url\"\n                riskLevel: \"rest.riskLevel\"\n       \
  \         description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vendors/{id}\n          name: vendor-detail\n          description: \"Individual vendor management\"\n          operations:\n            - method: GET\n              name: get-vendor\n              description: \"Get vendor details and security review status\"\n              call: \"vanta.get-vendor\"\n              with:\n                vendorId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-vendor\n              description: \"Update vendor risk level and review status\"\n              call: \"vanta.update-vendor\"\n              with:\n                vendorId: \"rest.id\"\n                riskLevel: \"rest.riskLevel\"\n                reviewStatus: \"rest.reviewStatus\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/documents\n          name: documents\n          description: \"Compliance evidence document management\"\n          operations:\n            - method: GET\n              name: list-documents\n              description: \"List compliance evidence documents\"\n              call: \"vanta.list-documents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: upload-document\n              description: \"Upload compliance evidence document\"\n              call: \"vanta.upload-document\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/people\n          name: people\n          description: \"Personnel security task tracking\"\n          operations:\n            - method: GET\n              name: list-people\n              description:\
  \ \"List people with security task and training status\"\n              call: \"vanta.list-people\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/computers\n          name: computers\n          description: \"Endpoint device compliance monitoring\"\n          operations:\n            - method: GET\n              name: list-computers\n              description: \"List monitored computers and compliance status\"\n              call: \"vanta.list-computers\"\n              with:\n                complianceStatus: \"rest.complianceStatus\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/integrations\n          name: integrations\n          description: \"Integration status monitoring\"\n          operations:\n            - method: GET\n              name: list-integrations\n              description: \"List configured integrations and connection\
  \ status\"\n              call: \"vanta.list-integrations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vanta-compliance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted compliance management and security posture monitoring.\"\n      tools:\n        - name: list-frameworks\n          description: \"List compliance frameworks (SOC 2, ISO 27001, HIPAA, PCI DSS, GDPR) and their readiness status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vanta.list-frameworks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-controls\n          description: \"Query compliance controls with optional framework and status filters to identify gaps\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vanta.list-controls\"\
  \n          with:\n            frameworkId: \"tools.frameworkId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-failing-controls\n          description: \"Get all FAILING controls to prioritize remediation efforts\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vanta.list-controls\"\n          with:\n            status: \"FAILING\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-tests\n          description: \"Query automated compliance test results to identify evidence gaps\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vanta.list-tests\"\n          with:\n            status: \"tools.status\"\n            frameworkId: \"tools.frameworkId\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n\n        - name: list-vulnerabilities\n          description: \"List security vulnerabilities with severity and remediation status filters\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vanta.list-vulnerabilities\"\n          with:\n            severity: \"tools.severity\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-critical-vulnerabilities\n          description: \"Get all CRITICAL severity open vulnerabilities for immediate remediation\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vanta.list-vulnerabilities\"\n          with:\n            severity: \"CRITICAL\"\n            status: \"OPEN\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-vendors\n          description: \"Query third-party vendors and their security\
  \ review status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vanta.list-vendors\"\n          with:\n            riskLevel: \"tools.riskLevel\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-vendor\n          description: \"Add a new third-party vendor to Vanta for security review tracking\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"vanta.create-vendor\"\n          with:\n            name: \"tools.name\"\n            url: \"tools.url\"\n            riskLevel: \"tools.riskLevel\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-vendor\n          description: \"Get detailed information about a specific vendor's security review\"\n          hints:\n            readOnly: true\n            openWorld: false\n   \
  \       call: \"vanta.get-vendor\"\n          with:\n            vendorId: \"tools.vendorId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-vendor-review\n          description: \"Update a vendor's risk level or review status after security assessment\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"vanta.update-vendor\"\n          with:\n            vendorId: \"tools.vendorId\"\n            riskLevel: \"tools.riskLevel\"\n            reviewStatus: \"tools.reviewStatus\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-people\n          description: \"List personnel with security training completion and overdue task status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vanta.list-people\"\n          outputParameters:\n         \
  \   - type: object\n              mapping: \"$.\"\n\n        - name: list-non-compliant-computers\n          description: \"List endpoint devices that are failing compliance checks\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vanta.list-computers\"\n          with:\n            complianceStatus: \"NON_COMPLIANT\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-integrations\n          description: \"List all configured integrations and their connection health\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vanta.list-integrations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-documents\n          description: \"List compliance evidence documents uploaded to Vanta\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"\
  vanta.list-documents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
