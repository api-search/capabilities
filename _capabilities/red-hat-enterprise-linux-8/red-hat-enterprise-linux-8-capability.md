---
categories: []
consumed_apis: []
description: The Red Hat Security Data API provides public access to Red Hat's security advisory and CVE data. It enables operators to query CVEs affecting RHEL products, retrieve CVSS scores, list security advisories (RHSA), bug fix advisories (RHBA), and enhancement advisories (RHEA), and obtain OVAL XML data for vulnerability scanning integration. No authentication is required for public data access.
layout: capability
name: Red Hat Security Data API
operations:
- description: List CVEs
  method: GET
  name: listcves
  path: /cve.json
- description: Get CVE Details
  method: GET
  name: getcve
  path: /cve/{CVE}.json
- description: List Security Advisories
  method: GET
  name: listadvisories
  path: /advisory.json
- description: Get Advisory Details
  method: GET
  name: getadvisory
  path: /advisory/{advisory}.json
- description: Get OVAL Definitions
  method: GET
  name: getovaldefinitions
  path: /oval/{product}.xml
personas: []
provider_name: Red Hat Enterprise Linux 8
provider_slug: red-hat-enterprise-linux-8
search_terms:
- hat
- rhel
- get cve details
- list cves
- red hat
- api
- getcve
- list security advisories
- linux
- operating system
- get advisory details
- getovaldefinitions
- enterprise
- listcves
- getadvisory
- get oval definitions
- listadvisories
- red
slug: red-hat-enterprise-linux-8-capability
source_filename: red-hat-enterprise-linux-8-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Red Hat Security Data API\n  description: The Red Hat Security Data API provides public access to Red Hat's security advisory and CVE data. It enables\n    operators to query CVEs affecting RHEL products, retrieve CVSS scores, list security advisories (RHSA), bug fix advisories\n    (RHBA), and enhancement advisories (RHEA), and obtain OVAL XML data for vulnerability scanning integration. No authentication\n    is required for public data access.\n  tags:\n  - Red\n  - Hat\n  - Enterprise\n  - Linux\n  - '8'\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: red-hat-enterprise-linux-8\n    baseUri: https://access.redhat.com/labs/securitydataapi\n    description: Red Hat Security Data API HTTP API.\n    resources:\n    - name: cve-json\n      path: /cve.json\n      operations:\n      - name: listcves\n        method: GET\n        description: List CVEs\n        inputParameters:\n\
  \        - name: before\n          in: query\n          type: string\n          description: Filter CVEs published before this date (YYYY-MM-DD)\n        - name: after\n          in: query\n          type: string\n          description: Filter CVEs published after this date (YYYY-MM-DD)\n        - name: ids_only\n          in: query\n          type: boolean\n          description: Return only CVE IDs instead of full objects\n        - name: bug\n          in: query\n          type: string\n          description: Filter by associated Bugzilla bug ID\n        - name: advisory\n          in: query\n          type: string\n          description: Filter by associated security advisory ID\n        - name: severity\n          in: query\n          type: string\n          description: Filter by severity level\n        - name: package\n          in: query\n          type: string\n          description: Filter by affected package name\n        - name: product\n          in: query\n          type:\
  \ string\n          description: Filter by affected product name\n        - name: cvss_score\n          in: query\n          type: number\n          description: Minimum CVSS score\n        - name: cvss3_score\n          in: query\n          type: number\n          description: Minimum CVSS v3 score\n        - name: page\n          in: query\n          type: integer\n        - name: per_page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cve-cve-json\n      path: /cve/{CVE}.json\n      operations:\n      - name: getcve\n        method: GET\n        description: Get CVE Details\n        inputParameters:\n        - name: CVE\n          in: path\n          type: string\n          required: true\n          description: The CVE identifier (e.g., CVE-2024-12345)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: advisory-json\n      path: /advisory.json\n      operations:\n      - name: listadvisories\n        method: GET\n        description: List Security Advisories\n        inputParameters:\n        - name: before\n          in: query\n          type: string\n          description: Filter advisories issued before this date (YYYY-MM-DD)\n        - name: after\n          in: query\n          type: string\n          description: Filter advisories issued after this date (YYYY-MM-DD)\n        - name: type\n          in: query\n          type: string\n          description: Filter by advisory type\n        - name: severity\n          in: query\n          type: string\n          description: Filter by severity (RHSA only)\n        - name: package\n          in: query\n          type: string\n          description: Filter by affected package name\n        - name: product\n          in: query\n          type: string\n          description: Filter by affected\
  \ product\n        - name: cve\n          in: query\n          type: string\n          description: Filter by associated CVE ID\n        - name: page\n          in: query\n          type: integer\n        - name: per_page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: advisory-advisory-json\n      path: /advisory/{advisory}.json\n      operations:\n      - name: getadvisory\n        method: GET\n        description: Get Advisory Details\n        inputParameters:\n        - name: advisory\n          in: path\n          type: string\n          required: true\n          description: The advisory ID (e.g., RHSA-2024:1234)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oval-product-xml\n      path: /oval/{product}.xml\n      operations:\n      - name: getovaldefinitions\n\
  \        method: GET\n        description: Get OVAL Definitions\n        inputParameters:\n        - name: product\n          in: path\n          type: string\n          required: true\n          description: The product identifier (e.g., rhel8, rhel9)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: red-hat-enterprise-linux-8-rest\n    description: REST adapter for Red Hat Security Data API.\n    resources:\n    - path: /cve.json\n      name: listcves\n      operations:\n      - method: GET\n        name: listcves\n        description: List CVEs\n        call: red-hat-enterprise-linux-8.listcves\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cve/{CVE}.json\n      name: getcve\n      operations:\n      - method: GET\n        name: getcve\n        description: Get CVE Details\n        call: red-hat-enterprise-linux-8.getcve\n\
  \        with:\n          CVE: rest.CVE\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /advisory.json\n      name: listadvisories\n      operations:\n      - method: GET\n        name: listadvisories\n        description: List Security Advisories\n        call: red-hat-enterprise-linux-8.listadvisories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /advisory/{advisory}.json\n      name: getadvisory\n      operations:\n      - method: GET\n        name: getadvisory\n        description: Get Advisory Details\n        call: red-hat-enterprise-linux-8.getadvisory\n        with:\n          advisory: rest.advisory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oval/{product}.xml\n      name: getovaldefinitions\n      operations:\n      - method: GET\n        name: getovaldefinitions\n        description: Get OVAL Definitions\n        call: red-hat-enterprise-linux-8.getovaldefinitions\n\
  \        with:\n          product: rest.product\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: red-hat-enterprise-linux-8-mcp\n    transport: http\n    description: MCP adapter for Red Hat Security Data API for AI agent use.\n    tools:\n    - name: listcves\n      description: List CVEs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: red-hat-enterprise-linux-8.listcves\n      with:\n        before: tools.before\n        after: tools.after\n        ids_only: tools.ids_only\n        bug: tools.bug\n        advisory: tools.advisory\n        severity: tools.severity\n        package: tools.package\n        product: tools.product\n        cvss_score: tools.cvss_score\n        cvss3_score: tools.cvss3_score\n        page: tools.page\n        per_page: tools.per_page\n      inputParameters:\n      - name: before\n        type: string\n        description: Filter\
  \ CVEs published before this date (YYYY-MM-DD)\n      - name: after\n        type: string\n        description: Filter CVEs published after this date (YYYY-MM-DD)\n      - name: ids_only\n        type: boolean\n        description: Return only CVE IDs instead of full objects\n      - name: bug\n        type: string\n        description: Filter by associated Bugzilla bug ID\n      - name: advisory\n        type: string\n        description: Filter by associated security advisory ID\n      - name: severity\n        type: string\n        description: Filter by severity level\n      - name: package\n        type: string\n        description: Filter by affected package name\n      - name: product\n        type: string\n        description: Filter by affected product name\n      - name: cvss_score\n        type: number\n        description: Minimum CVSS score\n      - name: cvss3_score\n        type: number\n        description: Minimum CVSS v3 score\n      - name: page\n        type: integer\n\
  \        description: page\n      - name: per_page\n        type: integer\n        description: per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcve\n      description: Get CVE Details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: red-hat-enterprise-linux-8.getcve\n      with:\n        CVE: tools.CVE\n      inputParameters:\n      - name: CVE\n        type: string\n        description: The CVE identifier (e.g., CVE-2024-12345)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listadvisories\n      description: List Security Advisories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: red-hat-enterprise-linux-8.listadvisories\n      with:\n        before: tools.before\n        after: tools.after\n        type: tools.type\n        severity: tools.severity\n        package: tools.package\n\
  \        product: tools.product\n        cve: tools.cve\n        page: tools.page\n        per_page: tools.per_page\n      inputParameters:\n      - name: before\n        type: string\n        description: Filter advisories issued before this date (YYYY-MM-DD)\n      - name: after\n        type: string\n        description: Filter advisories issued after this date (YYYY-MM-DD)\n      - name: type\n        type: string\n        description: Filter by advisory type\n      - name: severity\n        type: string\n        description: Filter by severity (RHSA only)\n      - name: package\n        type: string\n        description: Filter by affected package name\n      - name: product\n        type: string\n        description: Filter by affected product\n      - name: cve\n        type: string\n        description: Filter by associated CVE ID\n      - name: page\n        type: integer\n        description: page\n      - name: per_page\n        type: integer\n        description: per_page\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getadvisory\n      description: Get Advisory Details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: red-hat-enterprise-linux-8.getadvisory\n      with:\n        advisory: tools.advisory\n      inputParameters:\n      - name: advisory\n        type: string\n        description: The advisory ID (e.g., RHSA-2024:1234)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getovaldefinitions\n      description: Get OVAL Definitions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: red-hat-enterprise-linux-8.getovaldefinitions\n      with:\n        product: tools.product\n      inputParameters:\n      - name: product\n        type: string\n        description: The product identifier (e.g., rhel8, rhel9)\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/red-hat-enterprise-linux-8/refs/heads/main/capabilities/red-hat-enterprise-linux-8-capability.yaml
tags:
- Red
- Hat
- Enterprise
- Linux
- '8'
- API
tools:
- description: List CVEs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcves
- description: Get CVE Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcve
- description: List Security Advisories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listadvisories
- description: Get Advisory Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getadvisory
- description: Get OVAL Definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getovaldefinitions
---
