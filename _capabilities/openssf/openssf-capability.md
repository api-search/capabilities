---
categories: []
consumed_apis: []
description: OSV is a distributed open source vulnerability database and triage infrastructure project hosted by the Open Source Security Foundation (OpenSSF). The OSV API exposes vulnerability records keyed to specific package versions or commits across multiple ecosystems (npm, PyPI, Maven, Go, NuGet, RubyGems, Cargo, Packagist, Hex, OSS-Fuzz, Linux, Android, GitHub Actions, etc.).
layout: capability
name: OSV (Open Source Vulnerabilities) API
operations:
- description: Query vulnerabilities for a package or commit
  method: POST
  name: queryvulnerabilities
  path: /v1/query
- description: Batched vulnerability query
  method: POST
  name: queryvulnerabilitiesbatch
  path: /v1/querybatch
- description: Get vulnerability by OSV ID
  method: GET
  name: getvulnerability
  path: /v1/vulns/{id}
- description: Determine probable versions of a C/C++ project (experimental)
  method: POST
  name: determineversion
  path: /v1experimental/determineversion
- description: Import-time quality check findings (experimental)
  method: GET
  name: importfindings
  path: /v1experimental/importfindings
personas: []
provider_name: OpenSSF
provider_slug: openssf
search_terms:
- queryvulnerabilities
- batched vulnerability query
- determine probable versions of a c/c++ project (experimental)
- linux foundation
- open source
- query vulnerabilities for a package or commit
- importfindings
- import-time quality check findings (experimental)
- openssf
- getvulnerability
- get vulnerability by osv id
- security
- api
- vulnerabilities
- determineversion
- queryvulnerabilitiesbatch
- supply chain
slug: openssf-capability
source_filename: openssf-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OSV (Open Source Vulnerabilities) API\n  description: OSV is a distributed open source vulnerability database and triage infrastructure project hosted by the Open\n    Source Security Foundation (OpenSSF). The OSV API exposes vulnerability records keyed to specific package versions or\n    commits across multiple ecosystems (npm, PyPI, Maven, Go, NuGet, RubyGems, Cargo, Packagist, Hex, OSS-Fuzz, Linux, Android,\n    GitHub Actions, etc.).\n  tags:\n  - Openssf\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: openssf\n    baseUri: https://api.osv.dev\n    description: OSV (Open Source Vulnerabilities) API HTTP API.\n    resources:\n    - name: v1-query\n      path: /v1/query\n      operations:\n      - name: queryvulnerabilities\n        method: POST\n        description: Query vulnerabilities for a package or commit\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v1-querybatch\n      path: /v1/querybatch\n      operations:\n      - name: queryvulnerabilitiesbatch\n        method: POST\n        description: Batched vulnerability query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-vulns-id\n      path: /v1/vulns/{id}\n      operations:\n      - name: getvulnerability\n        method: GET\n        description: Get vulnerability by OSV ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1experimental-determineversion\n      path: /v1experimental/determineversion\n      operations:\n      - name: determineversion\n        method: POST\n        description: Determine probable\
  \ versions of a C/C++ project (experimental)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1experimental-importfindings\n      path: /v1experimental/importfindings\n      operations:\n      - name: importfindings\n        method: GET\n        description: Import-time quality check findings (experimental)\n        inputParameters:\n        - name: source\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: openssf-rest\n    description: REST adapter for OSV (Open Source Vulnerabilities) API.\n    resources:\n    - path: /v1/query\n      name: queryvulnerabilities\n      operations:\n      - method: POST\n        name: queryvulnerabilities\n        description: Query vulnerabilities for a package\
  \ or commit\n        call: openssf.queryvulnerabilities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/querybatch\n      name: queryvulnerabilitiesbatch\n      operations:\n      - method: POST\n        name: queryvulnerabilitiesbatch\n        description: Batched vulnerability query\n        call: openssf.queryvulnerabilitiesbatch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vulns/{id}\n      name: getvulnerability\n      operations:\n      - method: GET\n        name: getvulnerability\n        description: Get vulnerability by OSV ID\n        call: openssf.getvulnerability\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1experimental/determineversion\n      name: determineversion\n      operations:\n      - method: POST\n        name: determineversion\n        description: Determine probable versions of a C/C++ project\
  \ (experimental)\n        call: openssf.determineversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1experimental/importfindings\n      name: importfindings\n      operations:\n      - method: GET\n        name: importfindings\n        description: Import-time quality check findings (experimental)\n        call: openssf.importfindings\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: openssf-mcp\n    transport: http\n    description: MCP adapter for OSV (Open Source Vulnerabilities) API for AI agent use.\n    tools:\n    - name: queryvulnerabilities\n      description: Query vulnerabilities for a package or commit\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openssf.queryvulnerabilities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: queryvulnerabilitiesbatch\n      description:\
  \ Batched vulnerability query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openssf.queryvulnerabilitiesbatch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvulnerability\n      description: Get vulnerability by OSV ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openssf.getvulnerability\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: determineversion\n      description: Determine probable versions of a C/C++ project (experimental)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openssf.determineversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: importfindings\n\
  \      description: Import-time quality check findings (experimental)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openssf.importfindings\n      with:\n        source: tools.source\n      inputParameters:\n      - name: source\n        type: string\n        description: source\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/openssf/refs/heads/main/capabilities/openssf-capability.yaml
tags:
- Openssf
- API
tools:
- description: Query vulnerabilities for a package or commit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: queryvulnerabilities
- description: Batched vulnerability query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: queryvulnerabilitiesbatch
- description: Get vulnerability by OSV ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvulnerability
- description: Determine probable versions of a C/C++ project (experimental)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: determineversion
- description: Import-time quality check findings (experimental)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: importfindings
---
