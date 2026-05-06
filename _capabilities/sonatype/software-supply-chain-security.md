---
categories: []
consumed_apis: []
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
- search for a component by hash or purl to get vulnerability and policy data
- software supply chain
- policy waiver management
- list policy violations
- vulnerability management
- get vulnerability details by cve or reference id
- list scan reports for a specific application
- get application details from sonatype lifecycle
- list application reports
- list policy waivers for an owner
- list all applications in portfolio
- policy violation monitoring
- sbom
- generate spdx sbom
- search for a component by hash or purl
- security
- compliance
- application portfolio management
- register a new application
- scan reports and compliance metrics
- list reports
- list all applications in the sonatype lifecycle portfolio
- register a new application in sonatype lifecycle
- list violations
- list waivers
- sonatype
- generate an spdx software bill of materials for an application scan
- get application details by id
- vulnerability intelligence
- get detailed vulnerability information by cve or sonatype reference id
- delete application
- software bill of materials generation
- get vulnerability
- component and vulnerability search
- list policy waivers
- devsecops
- search component
- get application reports
- policy
- create application
- remove an application from portfolio
- get spdx report
- get application
- list applications
- list policy violations for an application
- generate spdx sbom for a scan
- get reports for a specific application
- list reports for all applications
- software composition analysis
slug: software-supply-chain-security
source_filename: software-supply-chain-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sonatype Software Supply Chain Security\n  description: Workflow capability for software supply chain security using Sonatype Lifecycle. Covers application portfolio\n    management, policy violation monitoring, vulnerability intelligence, component analysis, SBOM generation, and waiver management.\n    Used by DevSecOps engineers, security teams, and compliance officers.\n  tags:\n  - Sonatype\n  - Software Supply Chain\n  - Security\n  - Vulnerability Management\n  - SBOM\n  - DevSecOps\n  - Policy\n  - Compliance\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SONATYPE_USERNAME: SONATYPE_USERNAME\n    SONATYPE_PASSWORD: SONATYPE_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: sonatype-lifecycle\n    baseUri: https://{iq-server-host}\n    description: Sonatype Lifecycle Public REST API v1.201.0\n    authentication:\n      type: basic\n      username: '{{SONATYPE_USERNAME}}'\n\
  \      password: '{{SONATYPE_PASSWORD}}'\n    resources:\n    - name: applications\n      path: /api/v2/applications\n      description: Manage applications in the Sonatype Lifecycle portfolio\n      operations:\n      - name: list-applications\n        method: GET\n        description: List all applications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-application\n        method: POST\n        description: Create a new application\n        body:\n          type: json\n          data:\n            publicId: '{{tools.publicId}}'\n            name: '{{tools.name}}'\n            organizationId: '{{tools.organizationId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-application\n        method: GET\n        description: Get application by ID\n        inputParameters:\n        - name: applicationId\n\
  \          in: path\n          type: string\n          required: true\n          description: Application ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-application\n        method: DELETE\n        description: Delete an application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: Application ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policy-violations\n      path: /api/v2/policyViolations\n      description: Query and manage policy violations\n      operations:\n      - name: list-policy-violations\n        method: GET\n        description: List policy violations for an application report\n        inputParameters:\n        - name: applicationId\n          in: query\n          type: string\n\
  \          required: false\n          description: Application ID filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policy-waivers\n      path: /api/v2/policyWaivers\n      description: Manage policy waivers for violations\n      operations:\n      - name: list-waivers\n        method: GET\n        description: List policy waivers for an owner\n        inputParameters:\n        - name: ownerType\n          in: path\n          type: string\n          required: true\n          description: Owner type (application|organization|repository_manager)\n        - name: ownerId\n          in: path\n          type: string\n          required: true\n          description: Internal owner ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: component-search\n      path: /api/v2/search/component\n      description: Search\
  \ for components and vulnerabilities\n      operations:\n      - name: search-component\n        method: GET\n        description: Search for a component\n        inputParameters:\n        - name: hash\n          in: query\n          type: string\n          required: false\n          description: Component hash\n        - name: packageUrl\n          in: query\n          type: string\n          required: false\n          description: Package URL (PURL)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vulnerabilities\n      path: /api/v2/vulnerabilities\n      description: Vulnerability intelligence and lookups\n      operations:\n      - name: get-vulnerability\n        method: GET\n        description: Get vulnerability by reference ID\n        inputParameters:\n        - name: refId\n          in: path\n          type: string\n          required: true\n          description: Vulnerability reference\
  \ ID (CVE, SONATYPE, etc)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /api/v2/reports/applications\n      description: Application scan reports and metrics\n      operations:\n      - name: list-reports\n        method: GET\n        description: List reports for all applications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-application-reports\n        method: GET\n        description: Get reports for a specific application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: Application ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spdx\n      path: /api/v2/spdx\n      description:\
  \ Generate SPDX Software Bill of Materials\n      operations:\n      - name: get-spdx-report\n        method: GET\n        description: Generate SPDX SBOM for a scan report\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: Application ID\n        - name: scanId\n          in: path\n          type: string\n          required: true\n          description: Scan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /api/v2/users\n      description: User account management\n      operations:\n      - name: list-users\n        method: GET\n        description: List users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user\n \
  \       body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            password: '{{tools.password}}'\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sonatype-supply-chain-api\n    description: Unified REST API for software supply chain security with Sonatype Lifecycle.\n    resources:\n    - path: /v1/applications\n      name: applications\n      description: Application portfolio management\n      operations:\n      - method: GET\n        name: list-applications\n        description: List all applications in portfolio\n        call: sonatype-lifecycle.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-application\n\
  \        description: Register a new application\n        call: sonatype-lifecycle.create-application\n        with:\n          publicId: rest.publicId\n          name: rest.name\n          organizationId: rest.organizationId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-application\n        description: Get application details by ID\n        call: sonatype-lifecycle.get-application\n        with:\n          applicationId: rest.applicationId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-application\n        description: Remove an application from portfolio\n        call: sonatype-lifecycle.delete-application\n        with:\n          applicationId: rest.applicationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/violations\n      name: policy-violations\n      description: Policy violation monitoring\n\
  \      operations:\n      - method: GET\n        name: list-violations\n        description: List policy violations\n        call: sonatype-lifecycle.list-policy-violations\n        with:\n          applicationId: rest.applicationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/waivers\n      name: policy-waivers\n      description: Policy waiver management\n      operations:\n      - method: GET\n        name: list-waivers\n        description: List policy waivers\n        call: sonatype-lifecycle.list-waivers\n        with:\n          ownerType: rest.ownerType\n          ownerId: rest.ownerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: component-search\n      description: Component and vulnerability search\n      operations:\n      - method: GET\n        name: search-component\n        description: Search for a component by hash or PURL\n        call: sonatype-lifecycle.search-component\n\
  \        with:\n          hash: rest.hash\n          packageUrl: rest.packageUrl\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vulnerabilities\n      name: vulnerabilities\n      description: Vulnerability intelligence\n      operations:\n      - method: GET\n        name: get-vulnerability\n        description: Get vulnerability details by CVE or reference ID\n        call: sonatype-lifecycle.get-vulnerability\n        with:\n          refId: rest.refId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Scan reports and compliance metrics\n      operations:\n      - method: GET\n        name: list-reports\n        description: List reports for all applications\n        call: sonatype-lifecycle.list-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-application-reports\n        description:\
  \ Get reports for a specific application\n        call: sonatype-lifecycle.get-application-reports\n        with:\n          applicationId: rest.applicationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sbom\n      name: sbom\n      description: Software Bill of Materials generation\n      operations:\n      - method: GET\n        name: get-spdx-report\n        description: Generate SPDX SBOM for a scan\n        call: sonatype-lifecycle.get-spdx-report\n        with:\n          applicationId: rest.applicationId\n          scanId: rest.scanId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: sonatype-supply-chain-mcp\n    transport: http\n    description: MCP server for AI-assisted software supply chain security with Sonatype Lifecycle.\n    tools:\n    - name: list-applications\n      description: List all applications in the Sonatype Lifecycle portfolio\n      hints:\n\
  \        readOnly: true\n        idempotent: true\n      call: sonatype-lifecycle.list-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-application\n      description: Register a new application in Sonatype Lifecycle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sonatype-lifecycle.create-application\n      with:\n        publicId: tools.publicId\n        name: tools.name\n        organizationId: tools.organizationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application\n      description: Get application details from Sonatype Lifecycle\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sonatype-lifecycle.get-application\n      with:\n        applicationId: tools.applicationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-policy-violations\n      description: List policy\
  \ violations for an application\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sonatype-lifecycle.list-policy-violations\n      with:\n        applicationId: tools.applicationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-policy-waivers\n      description: List policy waivers for an owner\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sonatype-lifecycle.list-waivers\n      with:\n        ownerType: tools.ownerType\n        ownerId: tools.ownerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-component\n      description: Search for a component by hash or PURL to get vulnerability and policy data\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sonatype-lifecycle.search-component\n      with:\n        hash: tools.hash\n        packageUrl: tools.packageUrl\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-vulnerability\n      description: Get detailed vulnerability information by CVE or Sonatype reference ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sonatype-lifecycle.get-vulnerability\n      with:\n        refId: tools.refId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-application-reports\n      description: List scan reports for a specific application\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sonatype-lifecycle.get-application-reports\n      with:\n        applicationId: tools.applicationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-spdx-sbom\n      description: Generate an SPDX Software Bill of Materials for an application scan\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sonatype-lifecycle.get-spdx-report\n      with:\n        applicationId: tools.applicationId\n        scanId:\
  \ tools.scanId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
