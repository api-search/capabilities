---
api_specs:
- filename: sonatype-lifecycle-openapi.yml
  format: yaml
  label: sonatype-lifecycle
  slug: sonatype-lifecycle
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sonatype/refs/heads/main/openapi/sonatype-lifecycle-openapi.yml
categories: []
consumed_apis:
- sonatype-lifecycle
description: Workflow capability for software supply chain security using Sonatype Lifecycle. Covers application portfolio management, policy violation monitoring, vulnerability intelligence, component analysis, SBOM generation, and waiver management. Used by DevSecOps engineers, security teams, and compliance officers.
layout: capability
name: Sonatype Software Supply Chain Security
operations:
- description: List all applications in portfolio
  method: GET
  name: list-applications
  path: /v1/applications
- description: Register a new application
  method: POST
  name: create-application
  path: /v1/applications
- description: Get application details by ID
  method: GET
  name: get-application
  path: /v1/applications
- description: Remove an application from portfolio
  method: DELETE
  name: delete-application
  path: /v1/applications
- description: List policy violations
  method: GET
  name: list-violations
  path: /v1/violations
- description: List policy waivers
  method: GET
  name: list-waivers
  path: /v1/waivers
- description: Search for a component by hash or PURL
  method: GET
  name: search-component
  path: /v1/search
- description: Get vulnerability details by CVE or reference ID
  method: GET
  name: get-vulnerability
  path: /v1/vulnerabilities
- description: List reports for all applications
  method: GET
  name: list-reports
  path: /v1/reports
- description: Get reports for a specific application
  method: GET
  name: get-application-reports
  path: /v1/reports
- description: Generate SPDX SBOM for a scan
  method: GET
  name: get-spdx-report
  path: /v1/sbom
personas: []
provider_name: Sonatype
provider_slug: sonatype
search_terms:
- get application
- register a new application
- get application details from sonatype lifecycle
- list policy waivers for an owner
- list policy waivers
- generate spdx sbom
- devsecops
- list all applications in portfolio
- security
- search for a component by hash or purl
- list policy violations for an application
- software bill of materials generation
- application portfolio management
- create application
- vulnerability intelligence
- get detailed vulnerability information by cve or sonatype reference id
- delete application
- get application details by id
- policy violation monitoring
- list waivers
- generate an spdx software bill of materials for an application scan
- list reports for all applications
- get reports for a specific application
- list violations
- get spdx report
- register a new application in sonatype lifecycle
- sonatype
- generate spdx sbom for a scan
- list all applications in the sonatype lifecycle portfolio
- software composition analysis
- list application reports
- scan reports and compliance metrics
- list applications
- component and vulnerability search
- policy waiver management
- get vulnerability details by cve or reference id
- vulnerability management
- search component
- get vulnerability
- list policy violations
- get application reports
- list scan reports for a specific application
- sbom
- compliance
- search for a component by hash or purl to get vulnerability and policy data
- list reports
- remove an application from portfolio
- software supply chain
- policy
slug: software-supply-chain-security
source_filename: software-supply-chain-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sonatype Software Supply Chain Security\"\n  description: >-\n    Workflow capability for software supply chain security using Sonatype Lifecycle.\n    Covers application portfolio management, policy violation monitoring, vulnerability\n    intelligence, component analysis, SBOM generation, and waiver management. Used by\n    DevSecOps engineers, security teams, and compliance officers.\n  tags:\n    - Sonatype\n    - Software Supply Chain\n    - Security\n    - Vulnerability Management\n    - SBOM\n    - DevSecOps\n    - Policy\n    - Compliance\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SONATYPE_USERNAME: SONATYPE_USERNAME\n      SONATYPE_PASSWORD: SONATYPE_PASSWORD\n\ncapability:\n  consumes:\n    - import: sonatype-lifecycle\n      location: ./shared/sonatype-lifecycle.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sonatype-supply-chain-api\n\
  \      description: \"Unified REST API for software supply chain security with Sonatype Lifecycle.\"\n      resources:\n        - path: /v1/applications\n          name: applications\n          description: \"Application portfolio management\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List all applications in portfolio\"\n              call: \"sonatype-lifecycle.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-application\n              description: \"Register a new application\"\n              call: \"sonatype-lifecycle.create-application\"\n              with:\n                publicId: \"rest.publicId\"\n                name: \"rest.name\"\n                organizationId: \"rest.organizationId\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n            - method: GET\n              name: get-application\n              description: \"Get application details by ID\"\n              call: \"sonatype-lifecycle.get-application\"\n              with:\n                applicationId: \"rest.applicationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-application\n              description: \"Remove an application from portfolio\"\n              call: \"sonatype-lifecycle.delete-application\"\n              with:\n                applicationId: \"rest.applicationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/violations\n          name: policy-violations\n          description: \"Policy violation monitoring\"\n          operations:\n            - method: GET\n              name: list-violations\n              description: \"List policy\
  \ violations\"\n              call: \"sonatype-lifecycle.list-policy-violations\"\n              with:\n                applicationId: \"rest.applicationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/waivers\n          name: policy-waivers\n          description: \"Policy waiver management\"\n          operations:\n            - method: GET\n              name: list-waivers\n              description: \"List policy waivers\"\n              call: \"sonatype-lifecycle.list-waivers\"\n              with:\n                ownerType: \"rest.ownerType\"\n                ownerId: \"rest.ownerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search\n          name: component-search\n          description: \"Component and vulnerability search\"\n          operations:\n            - method: GET\n              name: search-component\n         \
  \     description: \"Search for a component by hash or PURL\"\n              call: \"sonatype-lifecycle.search-component\"\n              with:\n                hash: \"rest.hash\"\n                packageUrl: \"rest.packageUrl\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vulnerabilities\n          name: vulnerabilities\n          description: \"Vulnerability intelligence\"\n          operations:\n            - method: GET\n              name: get-vulnerability\n              description: \"Get vulnerability details by CVE or reference ID\"\n              call: \"sonatype-lifecycle.get-vulnerability\"\n              with:\n                refId: \"rest.refId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports\n          name: reports\n          description: \"Scan reports and compliance metrics\"\n          operations:\n          \
  \  - method: GET\n              name: list-reports\n              description: \"List reports for all applications\"\n              call: \"sonatype-lifecycle.list-reports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-application-reports\n              description: \"Get reports for a specific application\"\n              call: \"sonatype-lifecycle.get-application-reports\"\n              with:\n                applicationId: \"rest.applicationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sbom\n          name: sbom\n          description: \"Software Bill of Materials generation\"\n          operations:\n            - method: GET\n              name: get-spdx-report\n              description: \"Generate SPDX SBOM for a scan\"\n              call: \"sonatype-lifecycle.get-spdx-report\"\n              with:\n\
  \                applicationId: \"rest.applicationId\"\n                scanId: \"rest.scanId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: sonatype-supply-chain-mcp\n      transport: http\n      description: \"MCP server for AI-assisted software supply chain security with Sonatype Lifecycle.\"\n      tools:\n        - name: list-applications\n          description: \"List all applications in the Sonatype Lifecycle portfolio\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sonatype-lifecycle.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-application\n          description: \"Register a new application in Sonatype Lifecycle\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call:\
  \ \"sonatype-lifecycle.create-application\"\n          with:\n            publicId: \"tools.publicId\"\n            name: \"tools.name\"\n            organizationId: \"tools.organizationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application\n          description: \"Get application details from Sonatype Lifecycle\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sonatype-lifecycle.get-application\"\n          with:\n            applicationId: \"tools.applicationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-policy-violations\n          description: \"List policy violations for an application\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sonatype-lifecycle.list-policy-violations\"\n          with:\n            applicationId: \"tools.applicationId\"\n   \
  \       outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-policy-waivers\n          description: \"List policy waivers for an owner\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sonatype-lifecycle.list-waivers\"\n          with:\n            ownerType: \"tools.ownerType\"\n            ownerId: \"tools.ownerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-component\n          description: \"Search for a component by hash or PURL to get vulnerability and policy data\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sonatype-lifecycle.search-component\"\n          with:\n            hash: \"tools.hash\"\n            packageUrl: \"tools.packageUrl\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vulnerability\n      \
  \    description: \"Get detailed vulnerability information by CVE or Sonatype reference ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sonatype-lifecycle.get-vulnerability\"\n          with:\n            refId: \"tools.refId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-application-reports\n          description: \"List scan reports for a specific application\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sonatype-lifecycle.get-application-reports\"\n          with:\n            applicationId: \"tools.applicationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: generate-spdx-sbom\n          description: \"Generate an SPDX Software Bill of Materials for an application scan\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call:\
  \ \"sonatype-lifecycle.get-spdx-report\"\n          with:\n            applicationId: \"tools.applicationId\"\n            scanId: \"tools.scanId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sonatype/refs/heads/main/capabilities/software-supply-chain-security.yaml
tags:
- Sonatype
- Software Supply Chain
- Security
- Vulnerability Management
- SBOM
- DevSecOps
- Policy
- Compliance
tools:
- description: List all applications in the Sonatype Lifecycle portfolio
  hints:
    idempotent: true
    readOnly: true
  name: list-applications
- description: Register a new application in Sonatype Lifecycle
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-application
- description: Get application details from Sonatype Lifecycle
  hints:
    idempotent: true
    readOnly: true
  name: get-application
- description: List policy violations for an application
  hints:
    idempotent: true
    readOnly: true
  name: list-policy-violations
- description: List policy waivers for an owner
  hints:
    idempotent: true
    readOnly: true
  name: list-policy-waivers
- description: Search for a component by hash or PURL to get vulnerability and policy data
  hints:
    idempotent: true
    readOnly: true
  name: search-component
- description: Get detailed vulnerability information by CVE or Sonatype reference ID
  hints:
    idempotent: true
    readOnly: true
  name: get-vulnerability
- description: List scan reports for a specific application
  hints:
    idempotent: true
    readOnly: true
  name: list-application-reports
- description: Generate an SPDX Software Bill of Materials for an application scan
  hints:
    idempotent: true
    readOnly: true
  name: generate-spdx-sbom
---
